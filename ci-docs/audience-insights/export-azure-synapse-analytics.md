---
title: Export údajů ze služby Customer Insights do Azure Synapse Analytics
description: Zjistěte, jak nakonfigurovat připojení a exportovat je do Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977369"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="762c1-103">Export dat do Azure Synapse Analytics (Preview)</span><span class="sxs-lookup"><span data-stu-id="762c1-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="762c1-104">Azure Synapse je analytická služba, která zrychluje čas na nahlédnutí napříč datovými sklady a systémy velkých objemů dat.</span><span class="sxs-lookup"><span data-stu-id="762c1-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="762c1-105">Data služby Customer Insights můžete přijímat a používat v [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="762c1-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="762c1-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="762c1-106">Prerequisites</span></span>

<span data-ttu-id="762c1-107">Pro konfiguraci připojení z Customer Insights je nutné splnit následující předpoklady Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="762c1-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="762c1-108">Nezapomeňte nastavit všechna **přiřazení rolí**, jak je popsáno.</span><span class="sxs-lookup"><span data-stu-id="762c1-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="762c1-109">Předpoklady v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="762c1-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="762c1-110">V přehledech cílové skupiny máte roli **Administrátor**.</span><span class="sxs-lookup"><span data-stu-id="762c1-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="762c1-111">Přečtěte si více o [nastavení uživatelských oprávnění ve statistikách cílové skupiny](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="762c1-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="762c1-112">V Azure:</span><span class="sxs-lookup"><span data-stu-id="762c1-112">In Azure:</span></span> 

- <span data-ttu-id="762c1-113">Aktivní předplatné Azure.</span><span class="sxs-lookup"><span data-stu-id="762c1-113">An active Azure subscription.</span></span>

- <span data-ttu-id="762c1-114">Pokud používáte nový účet Azure Data Lake Storage Gen2, *objekt zabezpečení služby* pro přehledy cílové skupiny vyžaduje oprávnění **Přispěvatel dat v objektu blob úložiště**.</span><span class="sxs-lookup"><span data-stu-id="762c1-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="762c1-115">Více informací získáte v tématu [Připojení účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure pro přehledy cílové skupiny](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="762c1-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="762c1-116">Úložiště Data Lake Gen2 **musí mít** povolen [hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="762c1-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="762c1-117">Ve skupině prostředků je umístěn pracovní prostor Azure Synapse ,*instanční objekt služby* a *uživatel pro přehledy cílové skupiny* musí mít přiděleno alespoň jedno oprávnění **Čtenář**.</span><span class="sxs-lookup"><span data-stu-id="762c1-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="762c1-118">Další informace viz [Přiřazení rolí Azure pomocí webu Azure Portal](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="762c1-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="762c1-119">*Uživatel* potřebuje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a propojena s pracovním prostorem Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="762c1-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="762c1-120">Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="762c1-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="762c1-121">*[Spravovaná identita pracovního prostoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vyžaduje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a připojena k pracovnímu prostoru Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="762c1-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="762c1-122">Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="762c1-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="762c1-123">V pracovním prostoru Azure Synapse musí mít *instanční objekt pro přehledy cílové skupiny* přiřazenou roli **Správce Synapse**.</span><span class="sxs-lookup"><span data-stu-id="762c1-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="762c1-124">Další informace viz [Jak nastavit řízení přístupu pro pracovní prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="762c1-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="762c1-125">Nastavení propojení a exportu do Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="762c1-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="762c1-126">Konfigurace připojení</span><span class="sxs-lookup"><span data-stu-id="762c1-126">Configure a connection</span></span>

1. <span data-ttu-id="762c1-127">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="762c1-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="762c1-128">Vyberte **Přidat připojení** a zvolte **Azure Synapse Analytics** nebo vyberte **Nastavit** v dlaždici **Azure Synapse Analytics** ke konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="762c1-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="762c1-129">Dejte propojení rozpoznatelný název do pole Zobrazovaný název.</span><span class="sxs-lookup"><span data-stu-id="762c1-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="762c1-130">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="762c1-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="762c1-131">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="762c1-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="762c1-132">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="762c1-132">Choose who can use this connection.</span></span> <span data-ttu-id="762c1-133">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="762c1-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="762c1-134">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="762c1-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="762c1-135">Vyberte nebo vyhledejte předplatné, ve kterém chcete použít data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="762c1-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="762c1-136">Jakmile je vybráno předplatné, můžete také vybrat **Pracovní prostor**, **Účet úložiště** a **Kontejner**.</span><span class="sxs-lookup"><span data-stu-id="762c1-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="762c1-137">Propojení uložte výběrem tlačítka **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="762c1-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="762c1-138">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="762c1-138">Configure an export</span></span>

<span data-ttu-id="762c1-139">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="762c1-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="762c1-140">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="762c1-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="762c1-141">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="762c1-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="762c1-142">Pokud chcete vytvořit nový export, vyberte **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="762c1-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="762c1-143">V poli **Připojení pro export** vyberte připojení v části **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="762c1-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="762c1-144">Pokud nevidíte název této sekce, nemáte k dispozici žádná [připojení tohoto typu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="762c1-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="762c1-145">Poskytují rozpoznatelné **zobrazované jméno** pro váš export a **název databáze**.</span><span class="sxs-lookup"><span data-stu-id="762c1-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="762c1-146">Vyberte entity, do kterých chcete exportovat Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="762c1-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="762c1-147">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="762c1-147">Select **Save**.</span></span>

<span data-ttu-id="762c1-148">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="762c1-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="762c1-149">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="762c1-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="762c1-150">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="762c1-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="762c1-151">Aktualizace exportu</span><span class="sxs-lookup"><span data-stu-id="762c1-151">Update an export</span></span>

1. <span data-ttu-id="762c1-152">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="762c1-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="762c1-153">V žádosti, kterou chcete aktualizovat, vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="762c1-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="762c1-154">**Přidejte** nebo **Odeberte** entity z výběru.</span><span class="sxs-lookup"><span data-stu-id="762c1-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="762c1-155">Pokud jsou entity z výběru odebrány, nebudou odstraněny z databáze Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="762c1-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="762c1-156">Budoucí aktualizace dat však neaktualizuje odebrané entity v této databázi.</span><span class="sxs-lookup"><span data-stu-id="762c1-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="762c1-157">**Změna názvu databáze** vytvoří novou databázi Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="762c1-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="762c1-158">Databáze s názvem, který byl nakonfigurován dříve, neobdrží žádné aktualizace v budoucích aktualizacích.</span><span class="sxs-lookup"><span data-stu-id="762c1-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
