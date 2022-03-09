---
title: Připojení k účtu Azure Data Lake Storage pomocí instančního objektu
description: Pro připojení k vašemu vlastnímu datovému jezeru použijte instanční objekt Azure.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d593880b06bd21e96826039a67382b75a4296a87
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354180"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure

Tento článek popisuje, jak propojit Dynamics 365 Customer Insights s účtem Azure Data Lake Storage pomocí instančního objektu Azure namísto klíčů účtu úložiště. 

Automatizované nástroje, které používají služby Azure, by vždy měly mít omezená oprávnění. Místo toho, aby se aplikace přihlašovaly jako plně privilegovaný uživatel, Azure nabízí instanční objekty. Pomocí instančních objektů můžete bezpečně [přidat nebo upravit složku Common Data Model jako zdroj dat](connect-common-data-model.md) nebo [vytvořit nebo aktualizovat prostředí](create-environment.md).

> [!IMPORTANT]
> - Účet Data Lake Storage, který bude používat instanční objekt, musí být Gen2 a musí mít [povolený hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace). Účty úložiště Azure Data Lake Gen1 nejsou podporovány.
> - K vytvoření instančního objektu potřebujete oprávnění správce pro své předplatné Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvoření instančního objektu Azure pro Customer Insights

Před vytvořením nového instančního objektu pro Customer Insights zkontrolujte, zda již ve vaší organizaci existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhledání existujícího instančního objektu

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

2. Ze **služeb Azure** vyberte **Azure Active Directory**.

3. Pod **Spravovat** vyberte **Podnikové aplikace**.

4. Vyhledejte ID aplikace Microsoft:
   - Přehledy cílových skupin: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s názvem `Dynamics 365 AI for Customer Insights`
   - Přehledy zapojení: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` s názvem `Dynamics 365 AI for Customer Insights engagement insights`

5. Pokud najdete odpovídající záznam, znamená to, že instanční objekt již existuje. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímek obrazovky zobrazující existující instanční objekt.":::
   
6. Pokud nejsou vráceny žádné výsledky, vytvořte nový instanční objekt.

>[!NOTE]
>Chcete-li využít plný výkon Dynamics 365 Customer Insights, doporučujeme přidat obě aplikace do instančního objektu.

### <a name="create-a-new-service-principal"></a>Vytvoření nového instančního objektu

1. Nainstalujte nejnovější verzi Azure Active Directory PowerShell pro Graph. Další informace najdete v části [Instalace Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači vyberte klávesu Windows na klávesnicivy, hledejte **Windows PowerShell** a vyberte **Spustit jako správce**.
   
   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.

2. Vytvořte instanční objekt pro Customer Insights pomocí modulu Azure AD PowerShell.

   1. V okně PowerShell, zadejte `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Místo *[ID vašeho klienta]* zadejte ID klienta, ve kterém chcete vytvořit instanční objekt. Parametr názvu prostředí `AzureEnvironmentName` je volitelný.
  
   1. Zadejte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento příkaz vytvoří instanční objekt pro přehledy cílové skupiny u vybraného klienta. 

   1. Zadejte `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Tento příkaz vytvoří instanční objekt pro přehledy zapojení na zvoleném klientovi.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udělení oprávnění instančnímu objektu pro přístup k účtu úložiště

Přejděte na portál Azure a udělte oprávnění instančnímu objektu pro účet úložiště, který chcete použít v přehledech cílové skupiny.

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

1. Otevřete účet úložiště, ke kterému má mít přístup instanční objekt pro přehledy cílové skupiny.

1. V levém podokně vyberte **Řízení přístupu (IAM)** a poté vyberte **Přidat** > **Přidat přiřazení rolí**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímek obrazovky ukazující portál Azure při přidávání přiřazení role.":::

1. V podokně **Přidat přiřazení rolí** nastavte následující vlastnosti:
   - Role: **Přispěvatel dat objektů blob úložiště**
   - Přiřaďte přístup pro: **Uživatel, skupina nebo instanční objekt**
   - Vyberte: **Dynamics 365 AI for Customer Insights** a **Přehledy zapojení Dynamics 365 AI pro Customer Insights** (dva [instanční objekty](#create-a-new-service-principal) vytvořené v tomto postupu)

1.  Zvolte **Uložit**.

Změny se mohou projevit až za 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Zadejte ID prostředku Azure nebo podrobnosti předplatného Azure v příloze účtu úložiště k přehledům cílové skupiny.

Můžete připojit účet Data Lake Storage v přehledech cílových skupin k [uložení výstupních dat](manage-environments.md) nebo [ho použít jej jako zdroj dat](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). Tato možnost vám umožňuje vybrat si mezi přístupem založeným na zdrojích nebo předplatným. V závislosti na zvoleném přístupu postupujte podle postupu v jedné z následujících částí.

### <a name="resource-based-storage-account-connection"></a>Připojení k účtu úložiště založené na prostředcích

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. V levém podokně přejděte na **Nastavení** > **Vlastnosti**.

1. Zkopírujte hodnotu ID prostředku účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopírování ID prostředku účtu úložiště.":::

1. V přehledech cílových skupin vložte ID prostředku do pole zdroje prostředku na obrazovce připojení účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadání informací o ID prostředku účtu úložiště.":::   

1. Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.

### <a name="subscription-based-storage-account-connection"></a>Připojení k účtu úložiště založené na předplatném

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. V levém podokně přejděte na **Nastavení** > **Vlastnosti**.

1. Zkontrolujte **Předplatné**, **Skupinu prostředků** a **Název** účtu úložiště a ujistěte se, že v přehledech cílové skupiny vyberete správné hodnoty.

1. V přehledech cílových skupin zvolte při připojování účtu úložiště hodnoty pro odpovídající pole.

1. Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.


[!INCLUDE[footer-include](../includes/footer-banner.md)]