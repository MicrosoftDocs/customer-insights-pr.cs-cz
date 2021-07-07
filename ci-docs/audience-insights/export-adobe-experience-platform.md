---
title: Export dat Customer Insights do Adobe Experience Platform
description: Naučte se používat segmenty přehledů cílové skupiny v Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305516"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="92f79-103">Použití segmentů Customer Insights v Adobe Experience Platform (Preview)</span><span class="sxs-lookup"><span data-stu-id="92f79-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="92f79-104">Jako uživatel přehledů cílové skupiny v Dynamics 365 Customer Insights jste možná vytvořili segmenty, které vám pomohou zefektivnit marketingové kampaně cílením na relevantní cílovou skupinu.</span><span class="sxs-lookup"><span data-stu-id="92f79-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="92f79-105">Chcete-li použít segment z přehledů cílových skupin v Adobe Experience Platform a aplikacích, jako je Adobe Campaign Standard, musíte postupovat podle několika kroků uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="92f79-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="92f79-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="92f79-107">Prerequisites</span></span>

-   <span data-ttu-id="92f79-108">Licence služby Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="92f79-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="92f79-109">Licence Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="92f79-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="92f79-110">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92f79-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="92f79-111">Účet Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="92f79-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="92f79-112">Přehled kampaně</span><span class="sxs-lookup"><span data-stu-id="92f79-112">Campaign Overview</span></span>

<span data-ttu-id="92f79-113">Abyste lépe pochopili, jak můžete použít segmenty z přehledů cílových skupin v Adobe Experience Platform, pojďme se podívat na fiktivní ukázkovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="92f79-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="92f79-114">Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném.</span><span class="sxs-lookup"><span data-stu-id="92f79-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="92f79-115">Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné.</span><span class="sxs-lookup"><span data-stu-id="92f79-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="92f79-116">Chcete-li si tyto zákazníky udržet, chcete jim zaslat propagační nabídku e-mailem pomocí aplikace Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="92f79-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="92f79-117">V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="92f79-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="92f79-118">Tento článek se nezabývá případem použití kampaně vícekrát.</span><span class="sxs-lookup"><span data-stu-id="92f79-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="92f79-119">Identifikace cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="92f79-119">Identify your target audience</span></span>

<span data-ttu-id="92f79-120">V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou k dispozici v přehledech cílové skupiny a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="92f79-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="92f79-121">[Segment, který jste definovali v přehledech cílové skupiny](segments.md), má název **ChurnProneCustomers** a těmto zákazníkům plánujete poslat e-mailovou propagaci.</span><span class="sxs-lookup"><span data-stu-id="92f79-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

<span data-ttu-id="92f79-123">E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="92f79-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="92f79-124">Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.</span><span class="sxs-lookup"><span data-stu-id="92f79-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="92f79-125">Export cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="92f79-125">Export your target audience</span></span>

<span data-ttu-id="92f79-126">S identifikovanou cílovou skupinou můžeme nakonfigurovat export z přehledů cílové skupiny do účtu Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="92f79-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="92f79-127">Konfigurace připojení</span><span class="sxs-lookup"><span data-stu-id="92f79-127">Configure a connection</span></span>

1. <span data-ttu-id="92f79-128">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="92f79-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92f79-129">Vyberte **Přidat připojení** a zvolte **Azure Blob Storage** nebo vyberte **Nastavit** v dlaždici **Azure Blob Storage** ke konfiguraci propojení.</span><span class="sxs-lookup"><span data-stu-id="92f79-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Dlaždice konfigurace pro Azure Blob Storage."::: 

1. <span data-ttu-id="92f79-131">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="92f79-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92f79-132">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="92f79-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92f79-133">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="92f79-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92f79-134">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="92f79-134">Choose who can use this connection.</span></span> <span data-ttu-id="92f79-135">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="92f79-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="92f79-136">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="92f79-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="92f79-137">Zadejte **Jméno účtu**, **Klíč účtu** a **Kontejner** pro účet Blob Storage, kam chcete segment exportovat.</span><span class="sxs-lookup"><span data-stu-id="92f79-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. "::: 
   
    - <span data-ttu-id="92f79-139">Další informace o vyhledání účtu Blob Storage a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="92f79-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="92f79-140">Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="92f79-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="92f79-141">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="92f79-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="92f79-142">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="92f79-142">Configure an export</span></span>

<span data-ttu-id="92f79-143">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="92f79-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="92f79-144">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="92f79-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92f79-145">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="92f79-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92f79-146">Pokud chcete vytvořit nový export, vyberte **Přidat export**.</span><span class="sxs-lookup"><span data-stu-id="92f79-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="92f79-147">V poli **propojení pro export** vyberte propojení z části Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="92f79-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="92f79-148">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="92f79-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="92f79-149">Zvolte segment, který chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="92f79-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="92f79-150">V tomto příkladu je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="92f79-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="92f79-152">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="92f79-152">Select **Save**.</span></span>

<span data-ttu-id="92f79-153">Po uložení cíle exportu jej najdete v části **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="92f79-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="92f79-154">Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92f79-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="92f79-155">Export bude spuštěn také s každou [plánovanou aktualizací](system.md).</span><span class="sxs-lookup"><span data-stu-id="92f79-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="92f79-156">Zajistěte, aby počet záznamů v exportovaném segmentu byl v povoleném limitu vaší licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92f79-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="92f79-157">Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše.</span><span class="sxs-lookup"><span data-stu-id="92f79-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="92f79-158">Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:</span><span class="sxs-lookup"><span data-stu-id="92f79-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="92f79-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="92f79-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="92f79-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="92f79-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="92f79-161">Soubor *model.json* pro exportované entity se nachází na úrovni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="92f79-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="92f79-162">Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="92f79-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="92f79-163">Definování datového modelu prostředí (XDM) v Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="92f79-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="92f79-164">Než lze data exportovaná z přehledů cílové skupiny použít v rámci Adobe Experience Platform, musíme definovat schéma datového modelu prostředí a [konfigurovat data pro profil zákazníka v reálném čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="92f79-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="92f79-165">Zjistěte, [co je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a seznamte se se [základy kompozice schématu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="92f79-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="92f79-166">Import dat do Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="92f79-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="92f79-167">Nyní, když je vše připraveno, musíme importovat připravená data cílové skupiny z přehledů cílové skupiny do Adobe Experience Platform, čímž vytvoříme profily.</span><span class="sxs-lookup"><span data-stu-id="92f79-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="92f79-168">Nejprve [vytvořte připojení zdroje Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="92f79-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="92f79-169">Po definování zdrojového připojení [nakonfigurujte tok dat](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pro dávkové připojení cloudového úložiště kvůli importu výstupu segmentu z přehledů cílové skupiny do Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="92f79-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="92f79-170">Vytvoření cílové skupiny v Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92f79-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="92f79-171">K odeslání e-mailu pro tuto kampaň použijeme Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92f79-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="92f79-172">Po importu dat do Adobe Experience Platform musíme [vytvořit cílovou skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard s využitím dat v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="92f79-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="92f79-173">Zjistěte, jak [používat nástroj pro tvorbu segmentů](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Campaign Standard pro definování cílové skupiny na základě dat v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="92f79-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="92f79-174">Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92f79-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="92f79-175">Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.</span><span class="sxs-lookup"><span data-stu-id="92f79-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e-mail s nabídkou obnovení z Adobe Campaign Standard.":::
