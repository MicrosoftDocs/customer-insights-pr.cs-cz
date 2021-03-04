---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270104"
---
# <a name="manage-environments"></a><span data-ttu-id="c7878-103">Správa prostředí</span><span class="sxs-lookup"><span data-stu-id="c7878-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c7878-104">Tento článek vysvětluje, jak vytvořit novou organizaci a jak zřídit prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="c7878-105">Registrace a vytvoření organizace</span><span class="sxs-lookup"><span data-stu-id="c7878-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="c7878-106">Přejděte na webovou stránku [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="c7878-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="c7878-107">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="c7878-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="c7878-108">Vyberte preferovaný scénář registrace a vyberte odpovídající odkaz.</span><span class="sxs-lookup"><span data-stu-id="c7878-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="c7878-109">Přijetím podmínek a volbou **Pokračovat** zahajte vytváření organizace.</span><span class="sxs-lookup"><span data-stu-id="c7878-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="c7878-110">Po vytvoření prostředí budete přesměrováni na [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="c7878-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="c7878-111">Pomocí ukázkového prostředí prozkoumejte aplikaci nebo vytvořte nové prostředí podle kroků v další části.</span><span class="sxs-lookup"><span data-stu-id="c7878-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="c7878-112">Po zadání nastavení prostředí vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="c7878-113">Po úspěšném vytvoření prostředí budete přihlášeni.</span><span class="sxs-lookup"><span data-stu-id="c7878-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="c7878-114">Vytvoření prostředí v existující organizaci</span><span class="sxs-lookup"><span data-stu-id="c7878-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="c7878-115">Nové prostředí lze vytvořit dvěma způsoby.</span><span class="sxs-lookup"><span data-stu-id="c7878-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="c7878-116">Můžete specifikovat zcela novou konfiguraci nebo zkopírovat některá nastavení konfigurace z existujícího prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="c7878-117">Vytvoření prostředí:</span><span class="sxs-lookup"><span data-stu-id="c7878-117">To create an environment:</span></span>

1. <span data-ttu-id="c7878-118">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="c7878-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="c7878-119">Vyberte **Nové**.</span><span class="sxs-lookup"><span data-stu-id="c7878-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7878-120">![Nastavení prostředí](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="c7878-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="c7878-121">V dialogovém okně **Vytvoření nového prostředí** vyberte **Nové prostředí**.</span><span class="sxs-lookup"><span data-stu-id="c7878-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="c7878-122">Pokud chcete [kopírovat data z aktuálního prostředí](#additional-considerations-for-copy-configuration-preview), vyberte **Kopírovat z existujícího prostředí**.</span><span class="sxs-lookup"><span data-stu-id="c7878-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="c7878-123">Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.</span><span class="sxs-lookup"><span data-stu-id="c7878-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="c7878-124">Zadejte následující údaje:</span><span class="sxs-lookup"><span data-stu-id="c7878-124">Provide the following details:</span></span>
   - <span data-ttu-id="c7878-125">**Název**: Název tohoto prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="c7878-126">Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.</span><span class="sxs-lookup"><span data-stu-id="c7878-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="c7878-127">**Oblast**: Oblast, ve které je služba nasazena a hostována.</span><span class="sxs-lookup"><span data-stu-id="c7878-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="c7878-128">**Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="c7878-129">Volitelně můžete vybrat **Upřesnit nastavení**:</span><span class="sxs-lookup"><span data-stu-id="c7878-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="c7878-130">**Uložit všechna data do**: Určuje, kam chcete ukládat výstupní data generovaná z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7878-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="c7878-131">Budete mít dvě možnosti: **úložiště Customer Insights** (úložiště Azure Data Lake spravované týmem Customer Insights) a **Azure Data Lake Storage Gen2** (vaše vlastní úložiště Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="c7878-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="c7878-132">Ve výchozím nastavení je vybráno úložiště Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7878-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c7878-133">Uložením dat do úložiště Azure Data Lake Storage souhlasíte s tím, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7878-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="c7878-134">Další informace naleznete v centru zabezpečení Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7878-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="c7878-135">V současné době jsou přijímané entity vždy ukládány do datového jezera spravovaného řešením Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c7878-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="c7878-136">Podporujeme pouze účty úložiště Azure Data Lake Gen2 ze stejné oblasti Azure, kterou jste vybrali při vytváření prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="c7878-137">Podporujeme pouze účty úložišť Azure Data Lake Gen2 s podporou hierarchického prostoru názvů (HNS).</span><span class="sxs-lookup"><span data-stu-id="c7878-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="c7878-138">Pro možnost Azure Data Lake Storage Gen2 si můžete vybrat mezi ověřováním založeném na prostředku nebo na předplatném.</span><span class="sxs-lookup"><span data-stu-id="c7878-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="c7878-139">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c7878-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c7878-140">Název **kontejneru** nelze změnit a je „customerinsights“.</span><span class="sxs-lookup"><span data-stu-id="c7878-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="c7878-141">Pokud chcete použít [predikce](predictions.md) nebo nakonfigurovat sdílení dat s aplikacemi a řešeními založenými na Microsoft Dataverse, zadejte adresu URL prostředí Microsoft Dataverse pod **Konfigurace sdílení dat pomocí Microsoft Dataverse a povolení dalších funkcí**.</span><span class="sxs-lookup"><span data-stu-id="c7878-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="c7878-142">Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c7878-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="c7878-143">Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="c7878-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="c7878-144">[Predikce chybějících hodnot v entitě](predictions.md) není momentálně podporováno, když povolíte sdílení dat se službou Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c7878-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="c7878-145">![Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="c7878-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="c7878-146">Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše.</span><span class="sxs-lookup"><span data-stu-id="c7878-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="c7878-147">Datové soubory a soubory model.json budou vytvořeny a přidány do příslušných podsložek na základě spuštěného procesu.</span><span class="sxs-lookup"><span data-stu-id="c7878-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="c7878-148">Pokud vytvoříte více prostředí Customer Insights a zvolíte uložení výstupních entit z těchto prostředí do svého účtu úložiště, vytvoří se pro každé prostředí samostatné složky s ci_<environmentid> v kontejneru.</span><span class="sxs-lookup"><span data-stu-id="c7878-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="c7878-149">Další úvahy o konfiguraci kopírování (Preview)</span><span class="sxs-lookup"><span data-stu-id="c7878-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="c7878-150">Následující nastavení konfigurace se zkopírují:</span><span class="sxs-lookup"><span data-stu-id="c7878-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="c7878-151">Konfigurace funkcí</span><span class="sxs-lookup"><span data-stu-id="c7878-151">Feature configurations</span></span>
- <span data-ttu-id="c7878-152">Ingestované/importované zdroje dat</span><span class="sxs-lookup"><span data-stu-id="c7878-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="c7878-153">Konfigurace sjednocení dat (mapa, shoda, sloučení)</span><span class="sxs-lookup"><span data-stu-id="c7878-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="c7878-154">Segmenty</span><span class="sxs-lookup"><span data-stu-id="c7878-154">Segments</span></span>
- <span data-ttu-id="c7878-155">Míry</span><span class="sxs-lookup"><span data-stu-id="c7878-155">Measures</span></span>
- <span data-ttu-id="c7878-156">Vztahy</span><span class="sxs-lookup"><span data-stu-id="c7878-156">Relationships</span></span>
- <span data-ttu-id="c7878-157">Aktivity</span><span class="sxs-lookup"><span data-stu-id="c7878-157">Activities</span></span>
- <span data-ttu-id="c7878-158">Index hledání a filtrování</span><span class="sxs-lookup"><span data-stu-id="c7878-158">Search & filter Index</span></span>
- <span data-ttu-id="c7878-159">Cíle exportu</span><span class="sxs-lookup"><span data-stu-id="c7878-159">Export destinations</span></span>
- <span data-ttu-id="c7878-160">Plánovaná aktualizace</span><span class="sxs-lookup"><span data-stu-id="c7878-160">Scheduled refresh</span></span>
- <span data-ttu-id="c7878-161">Rozšíření</span><span class="sxs-lookup"><span data-stu-id="c7878-161">Enrichments</span></span>
- <span data-ttu-id="c7878-162">Správa modelů</span><span class="sxs-lookup"><span data-stu-id="c7878-162">Model management</span></span>
- <span data-ttu-id="c7878-163">Přiřazení rolí</span><span class="sxs-lookup"><span data-stu-id="c7878-163">Role assignments</span></span>

<span data-ttu-id="c7878-164">Následující nastavení se *nezkopírují*:</span><span class="sxs-lookup"><span data-stu-id="c7878-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="c7878-165">Profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="c7878-165">Customer profiles.</span></span>
- <span data-ttu-id="c7878-166">Přihlašovací údaje ke zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="c7878-166">Data source credentials.</span></span> <span data-ttu-id="c7878-167">Budete muset zadat přihlašovací údaje pro každý zdroj dat a ručně aktualizovat zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="c7878-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="c7878-168">Zdroje dat ze složky Common Data Model a datového jezera spravovaného prostřednictvím Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c7878-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="c7878-169">Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="c7878-170">Při kopírování prostředí se zobrazí potvrzovací zpráva o vytvoření nového prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="c7878-171">Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="c7878-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="c7878-172">Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**.</span><span class="sxs-lookup"><span data-stu-id="c7878-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="c7878-173">Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.</span><span class="sxs-lookup"><span data-stu-id="c7878-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7878-174">![Kopírované zdroje dat](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="c7878-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="c7878-175">Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="c7878-176">Zde najdete nastavení ze zdrojového prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="c7878-177">Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="c7878-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="c7878-178">Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="c7878-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="c7878-179">Úprava stávajícího prostředí</span><span class="sxs-lookup"><span data-stu-id="c7878-179">Edit an existing environment</span></span>

<span data-ttu-id="c7878-180">Můžete upravit některé podrobnosti existujících prostředí.</span><span class="sxs-lookup"><span data-stu-id="c7878-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="c7878-181">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="c7878-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="c7878-182">Vyberte ikonu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="c7878-183">V poli **Upravit prostředí** můžete změnit **zobrazovaný název** prostředí, ale nemůžete změnit **Oblast** nebo **Typ**.</span><span class="sxs-lookup"><span data-stu-id="c7878-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="c7878-184">Pokud je prostředí nakonfigurováno pro ukládání dat v úložišti Azure Data Lake Storage Gen2, můžete aktualizovat **Klíč účtu**.</span><span class="sxs-lookup"><span data-stu-id="c7878-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="c7878-185">Nemůžete však změnit **Název účtu** nebo název **Kontejneru**.</span><span class="sxs-lookup"><span data-stu-id="c7878-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="c7878-186">Volitelně můžete provést aktualizaci z připojení na základě klíče účtu do připojení založeného na prostředcích nebo předplatném.</span><span class="sxs-lookup"><span data-stu-id="c7878-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="c7878-187">Po upgradu nelze vrátit klíč účtu.</span><span class="sxs-lookup"><span data-stu-id="c7878-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="c7878-188">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c7878-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c7878-189">Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.</span><span class="sxs-lookup"><span data-stu-id="c7878-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="c7878-190">Obnovení existujícího prostředí</span><span class="sxs-lookup"><span data-stu-id="c7878-190">Reset an existing environment</span></span>

<span data-ttu-id="c7878-191">Pokud jste správce a chcete odstranit všechny konfigurace a odebrat ingegstovaná data, můžete obnovit prostředí do prázdného stavu.</span><span class="sxs-lookup"><span data-stu-id="c7878-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="c7878-192">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="c7878-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="c7878-193">Vyberte prostředí, které chcete obnovit, a vyberte tři tečky **...**.</span><span class="sxs-lookup"><span data-stu-id="c7878-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="c7878-194">Vyberte volbu **Obnovit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="c7878-195">Chcete-li potvrdit odstranění, zadejte název prostředí a vyberte **Obnovit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="c7878-196">Odstranění existujícího prostředí (pouze pro správce)</span><span class="sxs-lookup"><span data-stu-id="c7878-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="c7878-197">Jako správce můžete odstranit prostředí, které spravujete.</span><span class="sxs-lookup"><span data-stu-id="c7878-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="c7878-198">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="c7878-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="c7878-199">Vyberte prostředí, které chcete obnovit, a vyberte tři tečky **...**.</span><span class="sxs-lookup"><span data-stu-id="c7878-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="c7878-200">Vyberte volbu **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="c7878-201">Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="c7878-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]