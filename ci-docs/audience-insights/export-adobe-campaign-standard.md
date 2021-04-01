---
title: Export dat Customer Insights do Adobe Campaign Standard
description: Naučte se používat segmenty přehledů cílových skupin v Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596307"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="d1675-103">Použití segmentů Customer Insights v Adobe Campaign Standard (Preview)</span><span class="sxs-lookup"><span data-stu-id="d1675-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="d1675-104">Jako uživatel přehledů cílových skupin pro Dynamics 365 Customer Insights jste možná vytvořili segmenty, které vám pomohou zefektivnit marketingové kampaně cílením na relevantní cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="d1675-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d1675-105">Chcete-li použít segment z přehledů cílových skupin v Adobe Experience Platform a aplikacích, jako je Adobe Campaign Standard, musíte postupovat podle několika kroků uvedených v tomto článku.</span><span class="sxs-lookup"><span data-stu-id="d1675-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a><span data-ttu-id="d1675-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d1675-107">Prerequisites</span></span>

-   <span data-ttu-id="d1675-108">Licence služby Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d1675-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d1675-109">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1675-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d1675-110">Účet Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="d1675-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d1675-111">Přehled kampaně</span><span class="sxs-lookup"><span data-stu-id="d1675-111">Campaign Overview</span></span>

<span data-ttu-id="d1675-112">Abyste lépe pochopili, jak můžete použít segmenty z přehledů cílových skupin v Adobe Experience Platform, pojďme se podívat na fiktivní ukázkovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="d1675-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d1675-113">Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném.</span><span class="sxs-lookup"><span data-stu-id="d1675-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d1675-114">Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné.</span><span class="sxs-lookup"><span data-stu-id="d1675-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d1675-115">Chcete-li si tyto zákazníky udržet, chcete jim zaslat propagační nabídku e-mailem pomocí aplikace Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1675-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="d1675-116">V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="d1675-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d1675-117">Tento článek se nezabývá případem použití kampaně vícekrát.</span><span class="sxs-lookup"><span data-stu-id="d1675-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="d1675-118">Přehledy cílových skupin a Adobe Campaign Standard však lze nakonfigurovat tak, aby fungovaly i pro scénář opakující se kampaně.</span><span class="sxs-lookup"><span data-stu-id="d1675-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d1675-119">Identifikace cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="d1675-119">Identify your target audience</span></span>

<span data-ttu-id="d1675-120">V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou k dispozici v přehledech cílové skupiny a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.</span><span class="sxs-lookup"><span data-stu-id="d1675-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d1675-121">[Segment, který jste definovali v přehledech cílové skupiny](segments.md), má název **ChurnProneCustomers** a těmto zákazníkům plánujete poslat e-mailovou propagaci.</span><span class="sxs-lookup"><span data-stu-id="d1675-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

<span data-ttu-id="d1675-123">E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka.</span><span class="sxs-lookup"><span data-stu-id="d1675-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d1675-124">Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.</span><span class="sxs-lookup"><span data-stu-id="d1675-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d1675-125">Export cílové skupiny</span><span class="sxs-lookup"><span data-stu-id="d1675-125">Export your target audience</span></span>

<span data-ttu-id="d1675-126">S identifikovanou cílovou skupinou můžeme nakonfigurovat export z přehledů cílové skupiny do účtu Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="d1675-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="d1675-127">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="d1675-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d1675-128">V dlaždici **Adobe Campaign** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="d1675-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurační dlaždice pro Adobe Campaign Standard.":::

1. <span data-ttu-id="d1675-130">Zadejte **Zobrazovaný název** pro tento nový cíl exportu a poté zadejte **Název účtu**, **Klíč účtu** a **Kontejner** účtu Azure Blob Storage, do kterého chcete segment exportovat.</span><span class="sxs-lookup"><span data-stu-id="d1675-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. "::: 

   - <span data-ttu-id="d1675-132">Další informace o tom, jak najít název účtu úložiště Azure Blob a klíč účtu, viz [Správa nastavení účtu úložiště v portálu Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d1675-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="d1675-133">Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d1675-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d1675-134">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="d1675-134">Select **Next**.</span></span>

1. <span data-ttu-id="d1675-135">Zvolte segment, který chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="d1675-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="d1675-136">V tomto příkladu je to **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d1675-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. <span data-ttu-id="d1675-138">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="d1675-138">Select **Next**.</span></span>

1. <span data-ttu-id="d1675-139">Nyní namapujeme **zdrojová** pole ze segmentu přehledů cílové skupiny na **cílové** názvy polí ve schématu profilu Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1675-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapování polí pro konektor Adobe Campaign Standard.":::

   <span data-ttu-id="d1675-141">Pokud chcete přidat další atributy, vyberte **Přidat atribut**.</span><span class="sxs-lookup"><span data-stu-id="d1675-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="d1675-142">Cílový název se může lišit od názvu zdrojového pole, takže stále můžete mapovat výstup segmentu z přehledů cílové skupiny do Adobe Campaign Standard, pokud pole v obou systémech nemají stejný název.</span><span class="sxs-lookup"><span data-stu-id="d1675-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1675-143">Jako pole identity se používá e-mailová adresa, ale k mapování dat do Adobe Campaign Standard můžete použít jakýkoli jiný identifikátor z vašeho zákaznického profilu přehledů cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="d1675-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="d1675-144">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="d1675-144">Select **Save**.</span></span>

<span data-ttu-id="d1675-145">Po uložení cíle exportu jej najdete v umístění **Správce** > **Export** > **Moje cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="d1675-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Screenshot se seznamem exportů a zvýrazněným ukázkovým segmentem.":::

<span data-ttu-id="d1675-147">Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1675-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="d1675-148">Export bude spuštěn také s každou [plánovanou aktualizací](system.md).</span><span class="sxs-lookup"><span data-stu-id="d1675-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d1675-149">Zajistěte, aby počet záznamů v exportovaném segmentu byl v povoleném limitu vaší licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1675-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d1675-150">Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše.</span><span class="sxs-lookup"><span data-stu-id="d1675-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="d1675-151">Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:</span><span class="sxs-lookup"><span data-stu-id="d1675-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d1675-152">*%ContainerName%/CustomerInsights_%instanceID%/% název_cíle_exportu%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="d1675-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="d1675-153">Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="d1675-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="d1675-154">Konfigurace Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1675-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="d1675-155">Segment exportovaný z přehledů cílové skupiny obsahuje sloupce, které jste vybrali při definování cíle exportu v předchozím kroku.</span><span class="sxs-lookup"><span data-stu-id="d1675-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="d1675-156">Tato data lze použít k [vytváření profilů v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="d1675-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="d1675-157">Chcete-li použít segment v Adobe Campaign Standard, musíme rozšířit schéma profilu v Adobe Campaign Standard tak, aby zahrnovalo další dvě pole.</span><span class="sxs-lookup"><span data-stu-id="d1675-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="d1675-158">Naučte se [rozšířit zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nová pole v Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1675-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="d1675-159">V našem příkladu jsou tato pole *Název segmentu a Datum segmentu (volitelně)*.</span><span class="sxs-lookup"><span data-stu-id="d1675-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="d1675-160">Tato pole použijeme k identifikaci profilů v Adobe Campaign Standard, na které chceme tuto kampaň cílit.</span><span class="sxs-lookup"><span data-stu-id="d1675-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="d1675-161">Pokud v Adobe Campaign Standard neexistují žádné záznamy kromě těch, které se chystáte importovat, můžete tento krok přeskočit.</span><span class="sxs-lookup"><span data-stu-id="d1675-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="d1675-162">Import dat do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1675-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="d1675-163">Nyní, když je vše připraveno, musíme importovat připravená data cílové skupiny z přehledů cílové skupiny do Adobe Campaign Standard, čímž vytvoříme profily.</span><span class="sxs-lookup"><span data-stu-id="d1675-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="d1675-164">Naučte se [importovat profily v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocí pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="d1675-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="d1675-165">Pracovní postup importu na obrázku níže je konfigurován tak, aby se spouštěl každých 8 hodin, a hledá exportované segmenty přehledů cílové skupiny (soubor .csv v Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="d1675-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="d1675-166">Pracovní postup extrahuje obsah souboru CSV v určeném pořadí sloupců.</span><span class="sxs-lookup"><span data-stu-id="d1675-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="d1675-167">Tento pracovní postup byl vytvořen tak, aby prováděl základní zpracování chyb a zajistil, aby měl každý záznam e-mailovou adresu před vložením dat do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d1675-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="d1675-168">Pracovní postup také extrahuje název segmentu z názvu souboru před provedením operace upsert na data profilu ACS.</span><span class="sxs-lookup"><span data-stu-id="d1675-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot pracovního postupu importu v uživatelském rozhraní Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d1675-170">Načtení cílové skupiny v Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1675-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d1675-171">Jakmile jsou data importována do Adobe Campaign Standard, [můžete vytvořit pracovní postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [zadat dotaz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) na zákazníky na základě polí *Název segmentu* a *Datum segmentu* a vybrat profily, které byly identifikovány pro naši ukázkovou kampaň.</span><span class="sxs-lookup"><span data-stu-id="d1675-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d1675-172">Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d1675-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d1675-173">Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1675-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e-mail s nabídkou obnovení z Adobe Campaign Standard.":::