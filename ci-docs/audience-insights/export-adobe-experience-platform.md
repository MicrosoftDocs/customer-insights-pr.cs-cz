---
title: Export dat Customer Insights do Adobe Experience Platform
description: Naučte se používat segmenty přehledů cílových skupin v Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596261"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="0f8f7-103">Použití segmentů Customer Insights v Adobe Experience Platform (Preview)</span><span class="sxs-lookup"><span data-stu-id="0f8f7-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="0f8f7-104">Jako uživatel přehledů cílových skupin pro Dynamics 365 Customer Insights jste možná vytvořili segmenty, které vám pomohou zefektivnit marketingové kampaně cílením na relevantní cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="0f8f7-105">Chcete-li použít segment z přehledů cílových skupin v Adobe Experience Platform a aplikacích, jako je Adobe Campaign Standard, musíte postupovat podle několika kroků uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="0f8f7-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="0f8f7-107">Prerequisites</span></span>

-   <span data-ttu-id="0f8f7-108">Licence služby Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0f8f7-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="0f8f7-109">Licence Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="0f8f7-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="0f8f7-110">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0f8f7-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="0f8f7-111">Účet Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="0f8f7-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="0f8f7-112">Přehled kampaně</span><span class="sxs-lookup"><span data-stu-id="0f8f7-112">Campaign Overview</span></span>

<span data-ttu-id="0f8f7-113">Abyste lépe pochopili, jak můžete použít segmenty z přehledů cílových skupin v Adobe Experience Platform, pojďme se podívat na fiktivní ukázkovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="0f8f7-114">Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="0f8f7-115">Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="0f8f7-116">Chcete-li si tyto zákazníky udržet, chcete jim zaslat propagační nabídku e-mailem pomocí aplikace Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="0f8f7-117">V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="0f8f7-118">Tento článek se nezabývá případem použití kampaně vícekrát.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="0f8f7-119">Identifikace cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="0f8f7-119">Identify your target audience</span></span>

<span data-ttu-id="0f8f7-120">V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou k dispozici v přehledech cílové skupiny a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="0f8f7-121">[Segment, který jste definovali v přehledech cílové skupiny](segments.md), má název **ChurnProneCustomers** a těmto zákazníkům plánujete poslat e-mailovou propagaci.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

<span data-ttu-id="0f8f7-123">E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="0f8f7-124">Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="0f8f7-125">Export cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="0f8f7-125">Export your target audience</span></span>

<span data-ttu-id="0f8f7-126">S identifikovanou cílovou skupinou můžeme nakonfigurovat export z přehledů cílové skupiny do účtu Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="0f8f7-127">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0f8f7-128">V dlaždici **Azure Blob Storage** vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Dlaždice konfigurace pro Azure Blob Storage.":::

1. <span data-ttu-id="0f8f7-130">Zadejte **Zobrazovaný název** pro tento nový cíl exportu a poté zadejte **Název účtu**, **Klíč účtu** a **Kontejner** účtu Azure Blob Storage, do kterého chcete segment exportovat.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. "::: 

   - <span data-ttu-id="0f8f7-132">Další informace o tom, jak najít název účtu úložiště Azure Blob a klíč účtu, viz [Správa nastavení účtu úložiště v portálu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="0f8f7-133">Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="0f8f7-134">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-134">Select **Next**.</span></span>

1. <span data-ttu-id="0f8f7-135">Zvolte segment, který chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="0f8f7-136">V tomto příkladu je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="0f8f7-138">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-138">Select **Save**.</span></span>

<span data-ttu-id="0f8f7-139">Po uložení cíle exportu jej najdete v umístění **Správce** > **Export** > **Moje cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Screenshot se seznamem exportů a zvýrazněným ukázkovým segmentem.":::

<span data-ttu-id="0f8f7-141">Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="0f8f7-142">Export bude spuštěn také s každou [plánovanou aktualizací](system.md).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0f8f7-143">Zajistěte, aby počet záznamů v exportovaném segmentu byl v povoleném limitu vaší licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="0f8f7-144">Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="0f8f7-145">Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:</span><span class="sxs-lookup"><span data-stu-id="0f8f7-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="0f8f7-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="0f8f7-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="0f8f7-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="0f8f7-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="0f8f7-148">Soubor *model.json* pro exportované entity se nachází na úrovni *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="0f8f7-149">Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="0f8f7-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="0f8f7-150">Definování datového modelu prostředí (XDM) v Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="0f8f7-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="0f8f7-151">Než lze data exportovaná z přehledů cílové skupiny použít v rámci Adobe Experience Platform, musíme definovat schéma datového modelu prostředí a [konfigurovat data pro profil zákazníka v reálném čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="0f8f7-152">Zjistěte, [co je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a seznamte se se [základy kompozice schématu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="0f8f7-153">Import dat do Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="0f8f7-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="0f8f7-154">Nyní, když je vše připraveno, musíme importovat připravená data cílové skupiny z přehledů cílové skupiny do Adobe Experience Platform, čímž vytvoříme profily.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="0f8f7-155">Nejprve [vytvořte připojení zdroje Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="0f8f7-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="0f8f7-156">Po definování zdrojového připojení [nakonfigurujte tok dat](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pro dávkové připojení cloudového úložiště kvůli importu výstupu segmentu z přehledů cílové skupiny do Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="0f8f7-157">Vytvoření cílové skupiny v Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0f8f7-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="0f8f7-158">K odeslání e-mailu pro tuto kampaň použijeme Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="0f8f7-159">Po importu dat do Adobe Experience Platform musíme [vytvořit cílovou skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard s využitím dat v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="0f8f7-160">Zjistěte, jak [používat nástroj pro tvorbu segmentů](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) v Adobe Campaign Standard pro definování cílové skupiny na základě dat v Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="0f8f7-161">Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="0f8f7-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="0f8f7-162">Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.</span><span class="sxs-lookup"><span data-stu-id="0f8f7-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e-mail s nabídkou obnovení z Adobe Campaign Standard.":::