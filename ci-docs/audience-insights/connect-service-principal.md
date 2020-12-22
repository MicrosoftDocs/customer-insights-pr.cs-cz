---
title: Připojení k účtu Azure Data Lake Storage Gen2 s instančním objektem
description: Použití instančního objektu Azure přehledů cílové skupiny pro připojení k vlastnímu datovému jezeru při jeho připojení k přehledům cílové skupiny.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644080"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Připojení k účtu Azure Data Lake Storage Gen2 s instančním objektem Azure pro přehledy cílové skupiny

Automatizované nástroje, které používají služby Azure, by vždy měly mít omezená oprávnění. Místo toho, aby se aplikace přihlašovaly jako plně privilegovaný uživatel, Azure nabízí instanční objekty. Čtěte dále a dozvíte se, jak propojit přehledy cílové skupiny s účtem Azure Data Lake Storage Gen2 pomocí instančního objektu Azure namísto klíčů účtu úložiště. 

Instanční objekt můžete použít pro bezpečné [přidání nebo úpravu složky Common Data Model jako zdroje dat](connect-common-data-model.md) nebo [vytvoření nového nebo aktualizaci stávajícího prostředí](manage-environments.md#create-an-environment-in-an-existing-organization).

K vytvoření instančního objektu potřebujete oprávnění správce pro vaše předplatné Azure.

## <a name="create-azure-service-principal-for-audience-insights"></a>Vytvoření instančního objektu Azure pro přehledy cílové skupiny

Před vytvořením nového instančního objektu pro přehledy cílové skupiny zkontrolujte, zda ve vaší organizaci již existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhledání existujícího instančního objektu

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

2. Vyberte **Azure Active Directory** ze služeb Azure.

3. Pod **Spravovat** vyberte **Podnikové aplikace**.

4. Vyhledejte ID aplikace první strany pro přehledy cílové skupiny `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nebo název `Dynamics 365 AI for Customer Insights`.

5. Pokud najdete odpovídající záznam, znamená to, že instanční objekt pro přehledy cílové skupiny existuje. Nemusíte jej znovu vytvářet.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot zobrazující existující instanční objekt.":::
   
6. Pokud nejsou vráceny žádné výsledky, vytvořte nový instanční objekt.

### <a name="create-a-new-service-principal"></a>Vytvoření nového instančního objektu

1. Nainstalujte si nejnovější verzi **Azure Active Directory PowerShell for Graph**. Další informace viz [Instalace Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Na počítači vyberte klávesu Windows na klávesnici a vyhledejte **Windows PowerShell** a **Spustit jako správce**.
   
   - V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.

2. Vytvořte instanční objekt pro přehledy cílové skupiny pomocí modulu Azure AD PowerShell.
   - V okně PowerShell, zadejte `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Místo ID vašeho klienta zadejte ID klienta, ve kterém chcete vytvořit instanční objekt. Parametr názvu prostředí `AzureEnvironmentName` je volitelný.
  
   - Zadejte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento příkaz vytvoří instanční objekt pro přehledy cílové skupiny u vybraného klienta.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udělení oprávnění instančnímu objektu pro přístup k účtu úložiště

Přejděte na portál Azure a udělte oprávnění instančnímu objektu pro účet úložiště, který chcete použít v přehledech cílové skupiny.

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

1. Otevřete účet úložiště, ke kterému má mít přístup instanční objekt pro přehledy cílové skupiny.

1. Vyberte **Řízení přístupu (IAM)** z navigačního podokna a vyberte **Přidat** > **Přidat přiřazení role**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot portálu Azure při výběru přiřazení rolí.":::
   
1. V podokně **Přidání přiřazení role** nastavte následující vlastnosti:
   - Role: *Přispěvatel dat objektů blob úložiště*
   - Přiřaďte přístup pro: *Uživatel, skupina nebo instanční objekt*
   - Vyberte: *Dynamics 365 AI for Customer Insights* (dále jen [instanční objekt, který jste vytvořili](#create-a-new-service-principal))

1.  Zvolte **Uložit**.

Změny se mohou projevit až za 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Zadejte ID prostředku Azure nebo podrobnosti předplatného Azure v příloze účtu úložiště k přehledům cílové skupiny.

Připojte účet úložiště Azure Data Lake v přehledech cílové skupiny, abyste mohli [ukládat výstupní data](manage-environments.md) nebo jej [použít jako zdroj dat](connect-common-data-service-lake.md). Možnost Azure Data Lake vám umožní vybrat si mezi přístupem založeným na prostředcích nebo na základě předplatného.

Podle níže uvedených kroků poskytněte požadované informace o vybraném přístupu.

### <a name="resounce-based-storage-account-connection"></a>Připojení k účtu úložiště založené na prostředcích

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. Přejděte na **Nastavení** > **Vlastnosti** v navigačním podokně.

1. Zkopírujte hodnotu ID prostředku účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopírování ID prostředku účtu úložiště.":::

1. V přehledech cílové skupiny vložte ID prostředku do pole prostředku zobrazeného na obrazovce připojení účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadání informací o ID prostředku účtu úložiště.":::   
   
1. Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.

### <a name="subscription-based-storage-account-connection"></a>Připojení k účtu úložiště založené na předplatném

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. Přejděte na **Nastavení** > **Vlastnosti** v navigačním podokně.

1. Zkontrolujte **Předplatné**, **Skupinu prostředků** a **Název** účtu úložiště a ujistěte se, že v přehledech cílové skupiny vyberete správné hodnoty.

1. V přehledech cílové skupiny vyberte hodnoty pro odpovídající pole při připojování účtu úložiště.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Zadání informací o ID prostředku účtu úložiště.":::
   
1. Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.
