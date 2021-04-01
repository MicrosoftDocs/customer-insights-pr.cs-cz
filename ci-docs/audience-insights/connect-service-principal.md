---
title: Připojení k účtu Azure Data Lake Storage Gen2 s instančním objektem
description: Použití instančního objektu Azure přehledů cílové skupiny pro připojení k vlastnímu datovému jezeru při jeho připojení k přehledům cílové skupiny.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596491"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0bcde-103">Připojení k účtu Azure Data Lake Storage Gen2 s instančním objektem Azure pro přehledy cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="0bcde-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="0bcde-104">Automatizované nástroje, které používají služby Azure, by vždy měly mít omezená oprávnění.</span><span class="sxs-lookup"><span data-stu-id="0bcde-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="0bcde-105">Místo toho, aby se aplikace přihlašovaly jako plně privilegovaný uživatel, Azure nabízí instanční objekty.</span><span class="sxs-lookup"><span data-stu-id="0bcde-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="0bcde-106">Čtěte dále a dozvíte se, jak propojit přehledy cílové skupiny s účtem Azure Data Lake Storage Gen2 pomocí instančního objektu Azure namísto klíčů účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="0bcde-107">Instanční objekt můžete použít pro bezpečné [přidání nebo úpravu složky Common Data Model jako zdroje dat](connect-common-data-model.md) nebo [vytvoření nového nebo aktualizaci stávajícího prostředí](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="0bcde-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="0bcde-108">Účet úložiště Azure Data Lake Gen2, který chce použít instanční objekt, musí mít [povolenu funkci Hierarchický prostor názvů (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="0bcde-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="0bcde-109">K vytvoření instančního objektu potřebujete oprávnění správce pro vaše předplatné Azure.</span><span class="sxs-lookup"><span data-stu-id="0bcde-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="0bcde-110">Vytvoření instančního objektu Azure pro přehledy cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="0bcde-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="0bcde-111">Před vytvořením nového instančního objektu pro přehledy cílové skupiny zkontrolujte, zda ve vaší organizaci již existuje.</span><span class="sxs-lookup"><span data-stu-id="0bcde-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="0bcde-112">Vyhledání existujícího instančního objektu</span><span class="sxs-lookup"><span data-stu-id="0bcde-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="0bcde-113">Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.</span><span class="sxs-lookup"><span data-stu-id="0bcde-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="0bcde-114">Vyberte **Azure Active Directory** ze služeb Azure.</span><span class="sxs-lookup"><span data-stu-id="0bcde-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="0bcde-115">Pod **Spravovat** vyberte **Podnikové aplikace**.</span><span class="sxs-lookup"><span data-stu-id="0bcde-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="0bcde-116">Vyhledejte ID aplikace první strany pro přehledy cílové skupiny `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nebo název `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="0bcde-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="0bcde-117">Pokud najdete odpovídající záznam, znamená to, že instanční objekt pro přehledy cílové skupiny existuje.</span><span class="sxs-lookup"><span data-stu-id="0bcde-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="0bcde-118">Nemusíte jej znovu vytvářet.</span><span class="sxs-lookup"><span data-stu-id="0bcde-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot zobrazující existující instanční objekt.":::
   
6. <span data-ttu-id="0bcde-120">Pokud nejsou vráceny žádné výsledky, vytvořte nový instanční objekt.</span><span class="sxs-lookup"><span data-stu-id="0bcde-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="0bcde-121">Vytvoření nového instančního objektu</span><span class="sxs-lookup"><span data-stu-id="0bcde-121">Create a new service principal</span></span>

1. <span data-ttu-id="0bcde-122">Nainstalujte si nejnovější verzi **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="0bcde-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="0bcde-123">Další informace viz [Instalace Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="0bcde-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="0bcde-124">Na počítači vyberte klávesu Windows na klávesnici a vyhledejte **Windows PowerShell** a **Spustit jako správce**.</span><span class="sxs-lookup"><span data-stu-id="0bcde-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="0bcde-125">V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="0bcde-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="0bcde-126">Vytvořte instanční objekt pro přehledy cílové skupiny pomocí modulu Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bcde-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="0bcde-127">V okně PowerShell, zadejte `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="0bcde-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="0bcde-128">Místo ID vašeho klienta zadejte ID klienta, ve kterém chcete vytvořit instanční objekt.</span><span class="sxs-lookup"><span data-stu-id="0bcde-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="0bcde-129">Parametr názvu prostředí `AzureEnvironmentName` je volitelný.</span><span class="sxs-lookup"><span data-stu-id="0bcde-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="0bcde-130">Zadejte `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="0bcde-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="0bcde-131">Tento příkaz vytvoří instanční objekt pro přehledy cílové skupiny u vybraného klienta.</span><span class="sxs-lookup"><span data-stu-id="0bcde-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="0bcde-132">Udělení oprávnění instančnímu objektu pro přístup k účtu úložiště</span><span class="sxs-lookup"><span data-stu-id="0bcde-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="0bcde-133">Přejděte na portál Azure a udělte oprávnění instančnímu objektu pro účet úložiště, který chcete použít v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="0bcde-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="0bcde-134">Přejděte na [portál pro správu Azure](https://portal.azure.com) a přihlaste se do své organizace.</span><span class="sxs-lookup"><span data-stu-id="0bcde-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="0bcde-135">Otevřete účet úložiště, ke kterému má mít přístup instanční objekt pro přehledy cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="0bcde-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="0bcde-136">Vyberte **Řízení přístupu (IAM)** z navigačního podokna a vyberte **Přidat** > **Přidat přiřazení role**.</span><span class="sxs-lookup"><span data-stu-id="0bcde-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screenshot portálu Azure při výběru přiřazení rolí.":::
   
1. <span data-ttu-id="0bcde-138">V podokně **Přidání přiřazení role** nastavte následující vlastnosti:</span><span class="sxs-lookup"><span data-stu-id="0bcde-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="0bcde-139">Role: *Přispěvatel dat objektů blob úložiště*</span><span class="sxs-lookup"><span data-stu-id="0bcde-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="0bcde-140">Přiřaďte přístup pro: *Uživatel, skupina nebo instanční objekt*</span><span class="sxs-lookup"><span data-stu-id="0bcde-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="0bcde-141">Vyberte: *Dynamics 365 AI for Customer Insights* (dále jen [instanční objekt, který jste vytvořili](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="0bcde-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="0bcde-142">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="0bcde-142">Select **Save**.</span></span>

<span data-ttu-id="0bcde-143">Změny se mohou projevit až za 15 minut.</span><span class="sxs-lookup"><span data-stu-id="0bcde-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="0bcde-144">Zadejte ID prostředku Azure nebo podrobnosti předplatného Azure v příloze účtu úložiště k přehledům cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="0bcde-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="0bcde-145">Připojte účet úložiště Azure Data Lake v přehledech cílové skupiny, abyste mohli [ukládat výstupní data](manage-environments.md) nebo jej [použít jako zdroj dat](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0bcde-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="0bcde-146">Možnost Azure Data Lake vám umožní vybrat si mezi přístupem založeným na prostředcích nebo na základě předplatného.</span><span class="sxs-lookup"><span data-stu-id="0bcde-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="0bcde-147">Podle níže uvedených kroků poskytněte požadované informace o vybraném přístupu.</span><span class="sxs-lookup"><span data-stu-id="0bcde-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="0bcde-148">Připojení k účtu úložiště založené na prostředcích</span><span class="sxs-lookup"><span data-stu-id="0bcde-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="0bcde-149">Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0bcde-150">Přejděte na **Nastavení** > **Vlastnosti** v navigačním podokně.</span><span class="sxs-lookup"><span data-stu-id="0bcde-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0bcde-151">Zkopírujte hodnotu ID prostředku účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopírování ID prostředku účtu úložiště.":::

1. <span data-ttu-id="0bcde-153">V přehledech cílové skupiny vložte ID prostředku do pole prostředku zobrazeného na obrazovce připojení účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Zadání informací o ID prostředku účtu úložiště.":::   
   
1. <span data-ttu-id="0bcde-155">Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="0bcde-156">Připojení k účtu úložiště založené na předplatném</span><span class="sxs-lookup"><span data-stu-id="0bcde-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="0bcde-157">Přejděte na [portál pro správu Azure](https://portal.azure.com), přihlaste se k předplatnému a otevřete účet úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="0bcde-158">Přejděte na **Nastavení** > **Vlastnosti** v navigačním podokně.</span><span class="sxs-lookup"><span data-stu-id="0bcde-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="0bcde-159">Zkontrolujte **Předplatné**, **Skupinu prostředků** a **Název** účtu úložiště a ujistěte se, že v přehledech cílové skupiny vyberete správné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="0bcde-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="0bcde-160">V přehledech cílové skupiny vyberte hodnoty pro odpovídající pole při připojování účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="0bcde-161">Pokračujte zbývajícími kroky v přehledech cílové skupiny pro připojení účtu úložiště.</span><span class="sxs-lookup"><span data-stu-id="0bcde-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]