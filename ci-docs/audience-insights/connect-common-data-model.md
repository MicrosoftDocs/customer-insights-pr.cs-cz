---
title: Připojení dat Common Data Model k účtu Azure Data Lake
description: Práce s daty Common Data Model pomocí Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596537"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="23a81-103">Připojení ke složce Common Data Model prostřednictvím účtu Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="23a81-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="23a81-104">Tento článek poskytuje informace, jak ingestovat data ze složky Common Data Model pomocí vašeho účtu Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="23a81-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="23a81-105">Důležitá poznámka</span><span class="sxs-lookup"><span data-stu-id="23a81-105">Important considerations</span></span>

- <span data-ttu-id="23a81-106">Data v účtu Azure Data Lake musí odpovídat standardu Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="23a81-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="23a81-107">V současné době nejsou podporovány jiné formáty.</span><span class="sxs-lookup"><span data-stu-id="23a81-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="23a81-108">Ingestace dat podporuje exkluzivně účty úložiště Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="23a81-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="23a81-109">K ingestaci dat nemůžete používat účty úložiště Azure Data Lake Gen1.</span><span class="sxs-lookup"><span data-stu-id="23a81-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="23a81-110">Chcete-li provést ověření pomocí instančního objektu Azure, ujistěte se, že je nakonfigurován ve vašem klientovi.</span><span class="sxs-lookup"><span data-stu-id="23a81-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="23a81-111">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="23a81-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="23a81-112">Účet úložiště Azure Data Lake, ke kterému se chcete připojit a ingestovat data, musí být ve stejné oblasti Azure jako prostředí Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23a81-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="23a81-113">Připojení ke složce Common Data Model z datového jezera v jiné oblasti Azure není podporováno.</span><span class="sxs-lookup"><span data-stu-id="23a81-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="23a81-114">Chcete-li znát svoji oblast prostředí Azure, přejděte na **Správce** > **Systém** > **O produktu** v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="23a81-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="23a81-115">Data uložená ve službách online mohou být uložena v jiném umístění, než kde jsou zpracovávána nebo uložena v Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="23a81-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="23a81-116"> Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="23a81-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="23a81-117">Připojit se ke složce modelu Common Data Model</span><span class="sxs-lookup"><span data-stu-id="23a81-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="23a81-118">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="23a81-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="23a81-119">Vyberte **Přidat zdroj dat**.</span><span class="sxs-lookup"><span data-stu-id="23a81-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="23a81-120">Vyberte **Připojit se ke složce modelu Common Data Model**, zadejte **Název** pro zdroj dat a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="23a81-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="23a81-121">Pokyny pro tvoření názvů:</span><span class="sxs-lookup"><span data-stu-id="23a81-121">Name guidelines:</span></span> 
   - <span data-ttu-id="23a81-122">Začněte písmenem.</span><span class="sxs-lookup"><span data-stu-id="23a81-122">Start with a letter.</span></span>
   - <span data-ttu-id="23a81-123">Používejte pouze písmena a číslice.</span><span class="sxs-lookup"><span data-stu-id="23a81-123">Use letters and numbers only.</span></span> <span data-ttu-id="23a81-124">Nejsou povoleny speciální znaky a mezery.</span><span class="sxs-lookup"><span data-stu-id="23a81-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="23a81-125">Název musí mít 3 až 64 znaků.</span><span class="sxs-lookup"><span data-stu-id="23a81-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="23a81-126">Můžete si vybrat mezi použitím možnosti založené na prostředku a možnosti založené na předplatném ověřování.</span><span class="sxs-lookup"><span data-stu-id="23a81-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="23a81-127">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="23a81-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="23a81-128">Zadejte informace o **Kontejneru** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="23a81-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23a81-129">![Dialogové okno pro zadání nových podrobností o připojení pro Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="23a81-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="23a81-130">Abyste se mohli připojit a vytvořit zdroj dat, potřebujete jednu z následujících rolí pro kontejner nebo výše uvedený účet úložiště:</span><span class="sxs-lookup"><span data-stu-id="23a81-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="23a81-131">Čtenář dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="23a81-132">Vlastník dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="23a81-133">Přispěvatel dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="23a81-134">V dialogovém okně **Vybrat složku modelu Common Data Model** vyberte soubor model.json nebo manifest.json, ze kterého chcete importovat data, a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="23a81-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="23a81-135">Soubor model.json ani manifest.json přidružený k jinému zdroj dat v prostředí se v seznamu nezobrazí.</span><span class="sxs-lookup"><span data-stu-id="23a81-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="23a81-136">Ve vybraném souboru model.json nebo manifest.json získáte seznam dostupných entit.</span><span class="sxs-lookup"><span data-stu-id="23a81-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="23a81-137">Můžete zkontrolovat seznam dostupných entit, vybrat z něho a vybrat **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="23a81-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="23a81-138">Všechny vybrané entity budou ingestovány z nového zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="23a81-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23a81-139">![Dialogové okno zobrazující seznam entit ze souboru model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="23a81-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="23a81-140">Označte, pro které datové entity chcete povolit profilování dat a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="23a81-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="23a81-141">Profilování dat umožňuje analýzy a další funkce.</span><span class="sxs-lookup"><span data-stu-id="23a81-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="23a81-142">Můžete vybrat celou entitu, čímž vyberete všechny atributy z entity, nebo můžete vybrat jen některé atributy dle vaší preference.</span><span class="sxs-lookup"><span data-stu-id="23a81-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="23a81-143">Ve výchozím nastavení není pro profilování dat povolena žádná entita.</span><span class="sxs-lookup"><span data-stu-id="23a81-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="23a81-144">![Dialogové okno zobrazující profilování dat](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="23a81-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="23a81-145">Po uložení vašich výběrů se otevře stránka **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="23a81-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="23a81-146">Nyní byste měli vidět připojení ke složce Common Data Model jako zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="23a81-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="23a81-147">Soubor model.json nebo manifest.json lze přidružit pouze k jednomu zdroji dat ve stejném prostředí.</span><span class="sxs-lookup"><span data-stu-id="23a81-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="23a81-148">Stejný soubor model.json nebo manifest.json však lze použít pro zdroje dat ve více prostředích.</span><span class="sxs-lookup"><span data-stu-id="23a81-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="23a81-149">Úprava zdroje dat složky Common Data Model</span><span class="sxs-lookup"><span data-stu-id="23a81-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="23a81-150">Můžete aktualizovat přístupový klíč pro účet úložiště obsahující složku Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="23a81-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="23a81-151">Můžete také změnit soubor model.json nebo manifest.json.</span><span class="sxs-lookup"><span data-stu-id="23a81-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="23a81-152">Pokud se chcete připojit k jinému kontejneru účtu úložiště nebo změnit název účtu, [vytvořte nové připojení zdroje dat](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="23a81-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="23a81-153">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="23a81-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="23a81-154">Vedle zdroje dat, který chcete aktualizovat, vyberte tři tečky.</span><span class="sxs-lookup"><span data-stu-id="23a81-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="23a81-155">V seznamu vyberte volbu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="23a81-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="23a81-156">Volitelně aktualizujte **Přístupový klíč** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="23a81-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog pro úpravu a aktualizaci přístupového klíče pro existující zdroj dat](media/edit-access-key.png)

5. <span data-ttu-id="23a81-158">Volitelně můžete provést aktualizaci z připojení klíče účtu do připojení založeného na prostředcích nebo předplatném.</span><span class="sxs-lookup"><span data-stu-id="23a81-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="23a81-159">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="23a81-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="23a81-160">Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.</span><span class="sxs-lookup"><span data-stu-id="23a81-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialogové okno pro zadání podrobností o připojení k existujícímu účtu úložiště Azure Data Lake](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="23a81-162">Abyste se mohli připojit a vytvořit zdroj dat, potřebujete jednu z následujících rolí pro kontejner nebo výše uvedený účet úložiště:</span><span class="sxs-lookup"><span data-stu-id="23a81-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="23a81-163">Čtenář dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="23a81-164">Vlastník dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="23a81-165">Přispěvatel dat objektů blob úložiště</span><span class="sxs-lookup"><span data-stu-id="23a81-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="23a81-166">Volitelně vyberte z kontejneru jiný soubor model.json nebo manifest.json s jinou sadou entit.</span><span class="sxs-lookup"><span data-stu-id="23a81-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="23a81-167">Volitelně můžete vybrat další entity, které chcete ingestovat.</span><span class="sxs-lookup"><span data-stu-id="23a81-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="23a81-168">Pokud již neexistují žádné závislosti, můžete také odebrat všechny již vybrané entity.</span><span class="sxs-lookup"><span data-stu-id="23a81-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="23a81-169">Pokud existují závislosti na existujícím souboru model.json nebo manifest.json a sadě entit, zobrazí se chybová zpráva a nelze vybrat jiný soubor model.json nebo manifest.json.</span><span class="sxs-lookup"><span data-stu-id="23a81-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="23a81-170">Odeberte tyto závislosti před změnou souboru model.json nebo manifest.json nebo vytvořte nový zdroj dat se souborem model.json nebo manifest.json, který chcete použít, abyste nemuseli závislosti odebrat.</span><span class="sxs-lookup"><span data-stu-id="23a81-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="23a81-171">Volitelně můžete vybrat další atributy nebo entity a povolit profilování dat, nebo deaktivovat již vybrané.</span><span class="sxs-lookup"><span data-stu-id="23a81-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]