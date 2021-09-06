---
title: Připojení k účtu Azure Data Lake Storage pomocí instančního objektu
description: Pro připojení k vašemu vlastnímu datovému jezeru použijte instanční objekt Azure.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461140"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatizované nástroje, které používají služby Azure, by vždy měly mít omezená oprávnění. Místo toho, aby se aplikace přihlašovaly jako plně privilegovaný uživatel, Azure nabízí instanční objekty. Přečtěte si, jak propojit Dynamics 365 Customer Insights s účtem Azure Data Lake Storage pomocí instančního objektu Azure namísto klíčů účtu úložiště. 

Instanční objekt můžete použít k bezpečnému [přidání nebo upravení složky Common Data Model jako zdroje dat](connect-common-data-model.md), nebo [vytvoření či aktualizaci prostředí](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Účet Data Lake Storage, který budete používat<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> Instanční objekt musí mít [povolen hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).
> - K vytvoření instančního objektu potřebujete oprávnění správce pro vaše předplatné Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvoření instančního objektu Azure pro Customer Insights

Před vytvořením nového instančního objektu pro přehledy cílových skupin nebo přehledy cílových zapojení zkontrolujte, zda již ve vaší organizaci existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhledání existujícího instančního objektu

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

2. Ze **služeb Azure** vyberte **Azure Active Directory**.

3. Pod **Spravovat** vyberte **Podnikové aplikace**.

4. Vyhledejte Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID aplikace:
   - Přehledy cílových skupin: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` s názvem `Dynamics 365 AI for Customer Insights`
   - Přehledy zapojení: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` s názvem `Dynamics 365 AI for Customer Insights engagement insights`

5. Pokud najdete odpovídající záznam, znamená to, že instanční objekt již existuje. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímek obrazovky zobrazující existující instanční objekt.":::
   
6. Pokud nejsou vráceny žádné výsledky, vytvořte nový instanční objekt.

>[!NOTE]
>Chcete-li využít plný výkon Dynamics 365 Customer Insights, doporučujeme přidat obě aplikace do instančního objektu.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Vytvoření nového instančního objektu
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Nainstalujte nejnovější verzi Azure Active Directory PowerShell pro Graph. Další informace najdete v části [Instalace Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači vyberte klávesu Windows na klávesnicivy, hledejte **Windows PowerShell** a vyberte **Spustit jako správce**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.

2. Vytvořte instanční objekt pro Customer Insights pomocí modulu Azure AD PowerShell.

   1. V okně PowerShell, zadejte `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Nahraďte *"[své ID klienta]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> skutečným ID vašeho klienta, kde chcete vytvořit instanční objekt. Parametr názvu prostředí `AzureEnvironmentName` je volitelný.
  
   1. Zadejte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento příkaz vytvoří instanční objekt pro přehledy cílové skupiny u vybraného klienta. 

   1. Zadejte `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Tento příkaz vytvoří instanční objekt pro přehledy zapojení<!--note from editor: Edit okay?--> na vybraném klientovi.

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

Můžete<!--note from editor: Edit suggested only if this section is optional.--> připojit účet Data Lake Storage v přehledech cílových skupin k [uložení výstupních dat](manage-environments.md) nebo [ho použít jej jako zdroj dat](connect-common-data-service-lake.md). Tato možnost vám umožňuje vybrat si mezi přístupem založeným na zdrojích nebo předplatným. V závislosti na zvoleném přístupu postupujte podle postupu v jedné z následujících částí.<!--note from editor: Suggested.-->

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