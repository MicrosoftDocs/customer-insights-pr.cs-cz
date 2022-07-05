---
title: Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure
description: Pro připojení k vašemu vlastnímu datovému jezeru použijte instanční objekt Azure.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080856"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure

Tento článek popisuje, jak propojit Dynamics 365 Customer Insights s účtem Azure Data Lake Storage pomocí instančního objektu Azure namísto klíčů účtu úložiště.

Automatizované nástroje, které používají služby Azure, by vždy měly mít omezená oprávnění. Místo toho, aby se aplikace přihlašovaly jako plně privilegovaný uživatel, Azure nabízí instanční objekty. Pomocí instančních objektů můžete bezpečně [přidat nebo upravit složku Common Data Model jako zdroj dat](connect-common-data-model.md) nebo [vytvořit nebo aktualizovat prostředí](create-environment.md).

> [!IMPORTANT]
>
> - Účet Data Lake Storage, který bude používat instanční objekt, musí být Gen2 a musí mít [povolený hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace). Účty úložiště Azure Data Lake Gen1 nejsou podporovány.
> - K vytvoření instančního objektu potřebujete oprávnění správce pro klienta Azure.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Vytvoření instančního objektu Azure pro Customer Insights

Před vytvořením nového instančního objektu pro Customer Insights zkontrolujte, zda již ve vaší organizaci existuje.

### <a name="look-for-an-existing-service-principal"></a>Vyhledání existujícího instančního objektu

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

2. Ze **služeb Azure** vyberte **Azure Active Directory**.

3. V možnosti **Spravovat** vyberte **Aplikace Microsoft**.

4. Přidání filtru pro **ID aplikace začíná** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nebo vyhledejte jméno `Dynamics 365 AI for Customer Insights`.

5. Pokud najdete odpovídající záznam, znamená to, že instanční objekt již existuje.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Snímek obrazovky zobrazující existující instanční objekt.":::

6. Pokud nejsou vráceny žádné výsledky, můžete [vytvořit nový instanční objekt](#create-a-new-service-principal). Ve většině případů již existuje a pro přístup k účtu úložiště musíte pouze udělit oprávnění pro instanční objekt.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Udělení oprávnění instančnímu objektu pro přístup k účtu úložiště

Přejděte na Azure Portal a udělte oprávnění instančnímu objektu pro účet úložiště, který chcete použít v Customer Insights. K účtu úložiště nebo kontejneru musí být přiřazena jedna z následujících rolí:

|Přihlašovací údaje|Požadavky|
|----------|------------|
|Aktuálně přihlášený uživatel|**Role**: Storage Blob Data Čtenář, Storage Blob přispěvatel nebo Storage Blob Vlastník.<br>**Úroveň**: Oprávnění lze udělit účtu úložiště nebo kontejneru.</br>|
|Instanční objekt Customer Insights -<br>Používání Azure Data Lake Storage jako zdroje dat</br>|Možnost 1<ul><li>**Role**: Storage Blob Data Čtenář, Storage Blob Data přispěvatel nebo Storage Blob Data Vlastník.</li><li>**Úroveň**: Oprávnění by se mělo udělit účtu úložiště nebo kontejneru.</li></ul>Možnost 2 *(bez sdílení přístupu Principal Service k účtu úložiště)*<ul><li>**Role 1**: Storage Blob Data Čtenář, Storage Blob Data přispěvatel nebo Storage Blob Data Vlastník.</li><li>**Úroveň**: Oprávnění by se mělo udělit kontejneru.</li><li>**Role 2**: Delegátor dat Storage Blob.</li><li>**Úroveň**: Oprávnění by se mělo udělit účtu úložiště nebo kontejneru.</li></ul>|
|Instanční objekt Customer Insights - <br>Použití Azure Data Lake Storage jako výstupu nebo cíle</br>|Možnost 1<ul><li>**Role**: Storage Blob Data přispěvatel nebo Storage Blob Vlastník.</li><li>**Úroveň**: Oprávnění by se mělo udělit účtu úložiště nebo kontejneru.</li></ul>Možnost 2 *(bez sdílení přístupu Principal Service k účtu úložiště)*<ul><li>**Role**: Storage Blob Data přispěvatel nebo Storage Blob Vlastník.</li><li>**Úroveň**: Oprávnění by se mělo udělit kontejneru.</li><li>**Role 2**: Storage Blob Delegátor.</li><li>**Úroveň**: Oprávnění by se mělo udělit účtu úložiště nebo kontejneru.</li></ul>|

1. Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.

1. Otevřete účet úložiště, ke kterému má mít hlavní objekt služby pro Customer Insights přístup.

1. V levém podokně vyberte **Řízení přístupu (IAM)** a poté vyberte **Přidat** > **Přidat přiřazení rolí**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Snímek obrazovky ukazující portál Azure při přidávání přiřazení role.":::

1. V podokně **Přidat přiřazení rolí** nastavte následující vlastnosti:
   - Role: Storage Blob Data Čtenář, Storage Blob Data přispěvatel nebo Storage Blob Data Vlastník na základě výše uvedených přihlašovacích údajů.
   - Přiřaďte přístup pro: **Uživatel, skupina nebo instanční objekt**
   - Vyberte členy: **Dynamics 365 AI pro Customer Insights** ([instanční objekt](#create-a-new-service-principal), který jste vyhledali dříve v tomto postupu)

1. Vyberte **Zkontrolovat + přiřadit**.

Změny se mohou projevit až za 15 minut.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Zadejte ID prostředku Azure nebo podrobnosti o předplatném Azure v příloze účtu úložiště k Customer Insights

Účet Data Lake Storage v Customer Insights můžete připojit a [uložit výstupní data](manage-environments.md) nebo [jej použijte jako zdroj dat](connect-dataverse-managed-lake.md). Tato možnost vám umožňuje vybrat si mezi přístupem založeným na zdrojích nebo předplatným. V závislosti na zvoleném přístupu postupujte podle postupu v jedné z následujících částí.

### <a name="resource-based-storage-account-connection"></a>Připojení k účtu úložiště založené na prostředcích

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. V levém podokně přejděte na **Nastavení** > **Koncové body**.

1. Zkopírujte hodnotu ID prostředku účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopírování ID prostředku účtu úložiště.":::

1. V Customer Insights vložte ID prostředku do pole prostředku zobrazeného na obrazovce připojení účtu úložiště.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadání informací o ID prostředku účtu úložiště.":::   

1. Pokračujte zbývajícími kroky v Customer Insights a připojte účet úložiště.

### <a name="subscription-based-storage-account-connection"></a>Připojení k účtu úložiště založené na předplatném

1. Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.

1. V levém podokně přejděte na **Nastavení** > **Vlastnosti**.

1. Zkontrolujte **Předplatné**, **Skupina prostředků** a **Název** účtu úložiště, abyste se ujistili, že v Customer Insights vyberete správné hodnoty.

1. V Customer Insights vyberte při připojování účtu úložiště hodnoty pro odpovídající pole.

1. Pokračujte zbývajícími kroky v Customer Insights a připojte účet úložiště.

### <a name="create-a-new-service-principal"></a>Vytvoření nového instančního objektu

1. Nainstalujte nejnovější verzi Azure Active Directory PowerShell pro Graph. Další informace najdete v části [Instalace Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).

   1. Na počítači stiskněte klávesu Windows na klávesnici a vyhledejte **Windows PowerShell** a vyberte **Spustit jako správce**.

   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.

2. Vytvořte instanční objekt pro Customer Insights pomocí modulu Azure AD PowerShell.

   1. V okně PowerShell, zadejte `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Nahraďte *[ID vašeho adresáře]* skutečným ID adresáře vašeho předplatného Azure, kde chcete vytvořit instanční objekt. Parametr názvu prostředí `AzureEnvironmentName` je volitelný.
  
   1. Zadejte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Tento příkaz vytvoří instanční objekt pro Customer Insights ve vybraném předplatném Azure.

[!INCLUDE [footer-include](includes/footer-banner.md)]
