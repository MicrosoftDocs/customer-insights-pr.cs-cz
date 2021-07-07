---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304872"
---
# <a name="manage-environments"></a><span data-ttu-id="5b513-103">Správa prostředí</span><span class="sxs-lookup"><span data-stu-id="5b513-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5b513-104">Tento článek vysvětluje, jak vytvořit novou organizaci a jak zřídit prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="5b513-105">Registrace a vytvoření organizace</span><span class="sxs-lookup"><span data-stu-id="5b513-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="5b513-106">Přejděte na webovou stránku [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="5b513-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="5b513-107">Vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="5b513-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="5b513-108">Vyberte preferovaný scénář registrace a vyberte odpovídající odkaz.</span><span class="sxs-lookup"><span data-stu-id="5b513-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="5b513-109">Přijetím podmínek a volbou **Pokračovat** zahajte vytváření organizace.</span><span class="sxs-lookup"><span data-stu-id="5b513-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="5b513-110">Po vytvoření prostředí budete přesměrováni na [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="5b513-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="5b513-111">Pomocí ukázkového prostředí prozkoumejte aplikaci nebo vytvořte nové prostředí podle kroků v další části.</span><span class="sxs-lookup"><span data-stu-id="5b513-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="5b513-112">Po zadání nastavení prostředí vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="5b513-113">Po úspěšném vytvoření prostředí budete přihlášeni.</span><span class="sxs-lookup"><span data-stu-id="5b513-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="5b513-114">Vytvoření prostředí v existující organizaci</span><span class="sxs-lookup"><span data-stu-id="5b513-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="5b513-115">Nové prostředí lze vytvořit dvěma způsoby.</span><span class="sxs-lookup"><span data-stu-id="5b513-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="5b513-116">Můžete specifikovat zcela novou konfiguraci nebo zkopírovat některá nastavení konfigurace z existujícího prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="5b513-117">Organizace mohou vytvořit *dvě* prostředí pro každou licenci Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b513-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="5b513-118">Pokud vaše organizace zakoupí více než jednu licenci, [kontaktujte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) a požádejte o zvýšení počtu dostupných prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="5b513-119">Další informace o kapacitě a kapacitě doplňků získáte stažením [Průvodce licencováním Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="5b513-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="5b513-120">Vytvoření prostředí:</span><span class="sxs-lookup"><span data-stu-id="5b513-120">To create an environment:</span></span>

1. <span data-ttu-id="5b513-121">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="5b513-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="5b513-122">Vyberte **Nové**.</span><span class="sxs-lookup"><span data-stu-id="5b513-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b513-123">![Nastavení prostředí.](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="5b513-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="5b513-124">V dialogovém okně **Vytvořit prostředí** vyberte **Nové prostředí**.</span><span class="sxs-lookup"><span data-stu-id="5b513-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="5b513-125">Pokud chcete [kopírovat data z aktuálního prostředí](#considerations-for-copy-configuration-preview), vyberte **Kopírovat z existujícího prostředí**.</span><span class="sxs-lookup"><span data-stu-id="5b513-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="5b513-126">Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.</span><span class="sxs-lookup"><span data-stu-id="5b513-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="5b513-127">Zadejte následující údaje:</span><span class="sxs-lookup"><span data-stu-id="5b513-127">Provide the following details:</span></span>
   - <span data-ttu-id="5b513-128">**Název**: Název tohoto prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="5b513-129">Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.</span><span class="sxs-lookup"><span data-stu-id="5b513-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="5b513-130">**Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="5b513-131">**Oblast**: Oblast, ve které je služba nasazena a hostována.</span><span class="sxs-lookup"><span data-stu-id="5b513-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="5b513-132">Volitelně můžete vybrat **Upřesnit nastavení**:</span><span class="sxs-lookup"><span data-stu-id="5b513-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="5b513-133">**Uložit všechna data do**: Určuje, kam chcete ukládat výstupní data generovaná z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b513-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="5b513-134">Budete mít dvě možnosti: **Úložiště Customer Insights** (Azure Data Lake spravované týmem Customer Insights) a **Azure Data Lake Storage** (váš vlastní Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="5b513-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="5b513-135">Ve výchozím nastavení je vybráno úložiště Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b513-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="5b513-136">Uložením dat do úložiště Azure Data Lake Storage souhlasíte s tím, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b513-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="5b513-137">Další informace naleznete v centru zabezpečení Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5b513-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="5b513-138">V současné době jsou přijímané entity vždy ukládány do Data Lake spravovaného řešením Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b513-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="5b513-139">Podporujeme pouze účty Azure Data Lake Storage ze stejné oblasti Azure, kterou jste vybrali při vytváření prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="5b513-140">Podporujeme pouze účty Azure Data Lake Storage, které mají povolený hierarchický obor názvů.</span><span class="sxs-lookup"><span data-stu-id="5b513-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="5b513-141">Pro možnost Azure Data Lake Storage si můžete pro ověřování vybrat mezi možností založenou na zdroji a možností založenou na předplatném.</span><span class="sxs-lookup"><span data-stu-id="5b513-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="5b513-142">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5b513-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5b513-143">Název **Kontejner** nelze změnit a bude mít hodnotu `customerinsights`.</span><span class="sxs-lookup"><span data-stu-id="5b513-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="5b513-144">Pokud chcete použít [predikce](predictions.md), konfigurovat sdílení dat s Microsoft Dataverse, nebo povolit příjem dat z místních zdrojů dat, uveďte adresu URL prostředí Microsoft Dataverse v části **Konfigurace sdílení dat s Microsoft Dataverse a povolení dalších funkcí**.</span><span class="sxs-lookup"><span data-stu-id="5b513-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="5b513-145">Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b513-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="5b513-146">Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5b513-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="5b513-147">[Predikce chybějících hodnot v entitě](predictions.md) není momentálně podporováno, když povolíte sdílení dat se službou Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b513-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5b513-148">![Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="5b513-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="5b513-149">Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše.</span><span class="sxs-lookup"><span data-stu-id="5b513-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="5b513-150">Datové soubory a soubory model.json budou vytvořeny a přidány do složek na základě názvu procesu.</span><span class="sxs-lookup"><span data-stu-id="5b513-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="5b513-151">Pokud vytvoříte více prostředí Customer Insights a zvolíte uložení výstupních entit z těchto prostředí do svého účtu úložiště, vytvoří se pro každé prostředí samostatné složky s ci_<environmentid> v kontejneru.</span><span class="sxs-lookup"><span data-stu-id="5b513-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="5b513-152">Úvahy o konfiguraci kopírování (náhled)</span><span class="sxs-lookup"><span data-stu-id="5b513-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="5b513-153">Následující nastavení konfigurace se zkopírují:</span><span class="sxs-lookup"><span data-stu-id="5b513-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="5b513-154">Konfigurace funkcí</span><span class="sxs-lookup"><span data-stu-id="5b513-154">Feature configurations</span></span>
- <span data-ttu-id="5b513-155">Ingestované/importované zdroje dat</span><span class="sxs-lookup"><span data-stu-id="5b513-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="5b513-156">Konfigurace sjednocení dat (mapa, shoda, sloučení)</span><span class="sxs-lookup"><span data-stu-id="5b513-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="5b513-157">Segmenty</span><span class="sxs-lookup"><span data-stu-id="5b513-157">Segments</span></span>
- <span data-ttu-id="5b513-158">Míry</span><span class="sxs-lookup"><span data-stu-id="5b513-158">Measures</span></span>
- <span data-ttu-id="5b513-159">Vztahy</span><span class="sxs-lookup"><span data-stu-id="5b513-159">Relationships</span></span>
- <span data-ttu-id="5b513-160">Aktivity</span><span class="sxs-lookup"><span data-stu-id="5b513-160">Activities</span></span>
- <span data-ttu-id="5b513-161">Index hledání a filtrování</span><span class="sxs-lookup"><span data-stu-id="5b513-161">Search & filter Index</span></span>
- <span data-ttu-id="5b513-162">Cíle exportu</span><span class="sxs-lookup"><span data-stu-id="5b513-162">Export destinations</span></span>
- <span data-ttu-id="5b513-163">Plánovaná aktualizace</span><span class="sxs-lookup"><span data-stu-id="5b513-163">Scheduled refresh</span></span>
- <span data-ttu-id="5b513-164">Rozšíření</span><span class="sxs-lookup"><span data-stu-id="5b513-164">Enrichments</span></span>
- <span data-ttu-id="5b513-165">Správa modelů</span><span class="sxs-lookup"><span data-stu-id="5b513-165">Model management</span></span>
- <span data-ttu-id="5b513-166">Přiřazení rolí</span><span class="sxs-lookup"><span data-stu-id="5b513-166">Role assignments</span></span>

<span data-ttu-id="5b513-167">Následující nastavení se *nezkopírují*:</span><span class="sxs-lookup"><span data-stu-id="5b513-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="5b513-168">Profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="5b513-168">Customer profiles.</span></span>
- <span data-ttu-id="5b513-169">Přihlašovací údaje ke zdroji dat.</span><span class="sxs-lookup"><span data-stu-id="5b513-169">Data source credentials.</span></span> <span data-ttu-id="5b513-170">Budete muset zadat přihlašovací údaje pro každý zdroj dat a ručně aktualizovat zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="5b513-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="5b513-171">Zdroje dat ze složky Common Data Model a Dataverse spravované v Data Lake.</span><span class="sxs-lookup"><span data-stu-id="5b513-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="5b513-172">Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="5b513-173">Při kopírování prostředí se zobrazí potvrzovací zpráva o vytvoření nového prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="5b513-174">Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="5b513-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="5b513-175">Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**.</span><span class="sxs-lookup"><span data-stu-id="5b513-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="5b513-176">Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.</span><span class="sxs-lookup"><span data-stu-id="5b513-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5b513-177">![Kopírované zdroje dat.](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="5b513-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="5b513-178">Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="5b513-179">Zde najdete nastavení ze zdrojového prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="5b513-180">Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.</span><span class="sxs-lookup"><span data-stu-id="5b513-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="5b513-181">Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="5b513-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="5b513-182">Úprava stávajícího prostředí</span><span class="sxs-lookup"><span data-stu-id="5b513-182">Edit an existing environment</span></span>

<span data-ttu-id="5b513-183">Můžete upravit některé podrobnosti existujících prostředí.</span><span class="sxs-lookup"><span data-stu-id="5b513-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="5b513-184">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="5b513-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="5b513-185">Vyberte ikonu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="5b513-186">V poli **Upravit prostředí** můžete změnit **zobrazovaný název** prostředí, ale nemůžete změnit **Oblast** nebo **Typ**.</span><span class="sxs-lookup"><span data-stu-id="5b513-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="5b513-187">Pokud je prostředí nakonfigurováno pro ukládání dat Azure Data Lake Storage, můžete aktualizovat **Klíč účtu**.</span><span class="sxs-lookup"><span data-stu-id="5b513-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="5b513-188">Nemůžete však změnit **Název účtu** nebo název **Kontejneru**.</span><span class="sxs-lookup"><span data-stu-id="5b513-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="5b513-189">Volitelně můžete provést aktualizaci z připojení na základě klíče účtu do připojení založeného na prostředcích nebo předplatném.</span><span class="sxs-lookup"><span data-stu-id="5b513-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="5b513-190">Po upgradu nelze vrátit klíč účtu.</span><span class="sxs-lookup"><span data-stu-id="5b513-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="5b513-191">Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5b513-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="5b513-192">Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.</span><span class="sxs-lookup"><span data-stu-id="5b513-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="5b513-193">Volitelně můžete poskytnout adresu URL prostředí Microsoft Dataverse v části **Konfigurace sdílení dat pomocí Microsoft Dataverse a povolení dalších funkcí**.</span><span class="sxs-lookup"><span data-stu-id="5b513-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="5b513-194">Tyto funkce zahrnují sdílení dat s aplikacemi a řešeními založenými na Microsoft Dataverse, příjem dat z místních datových zdrojů nebo použití [predikcí](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="5b513-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="5b513-195">Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b513-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="5b513-196">Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="5b513-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="5b513-197">[Predikce chybějících hodnot v entitě](predictions.md) momentálně není podporována, pokud povolíte sdílení dat se spravovanou službou Data Lake Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b513-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="5b513-198">Až povolíte sdílení dat s Microsoft Dataverse, spustí se jednorázová úplná aktualizace vašich zdrojů dat a dalších procesů.</span><span class="sxs-lookup"><span data-stu-id="5b513-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="5b513-199">Pokud procesy aktuálně běží, neuvidíte možnost povolit sdílení dat s Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="5b513-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="5b513-200">Chcete-li povolit sdílení dat, počkejte, až se tyto procesy dokončí, nebo je zrušte.</span><span class="sxs-lookup"><span data-stu-id="5b513-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::
   
   <span data-ttu-id="5b513-202">Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše.</span><span class="sxs-lookup"><span data-stu-id="5b513-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="5b513-203">Datové soubory a soubory model.json budou vytvořeny a přidány do příslušných podsložek v závislosti na spuštěném procesu.</span><span class="sxs-lookup"><span data-stu-id="5b513-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="5b513-204">Obnovení existujícího prostředí</span><span class="sxs-lookup"><span data-stu-id="5b513-204">Reset an existing environment</span></span>

<span data-ttu-id="5b513-205">Pokud jste správce a chcete odstranit všechny konfigurace a odebrat ingegstovaná data, můžete obnovit prostředí do prázdného stavu.</span><span class="sxs-lookup"><span data-stu-id="5b513-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="5b513-206">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="5b513-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="5b513-207">Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**).</span><span class="sxs-lookup"><span data-stu-id="5b513-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="5b513-208">Vyberte volbu **Obnovit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="5b513-209">Chcete-li potvrdit odstranění, zadejte název prostředí a vyberte **Obnovit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="5b513-210">Odstranění existujícího prostředí</span><span class="sxs-lookup"><span data-stu-id="5b513-210">Delete an existing environment</span></span>

<span data-ttu-id="5b513-211">Jako správce můžete odstranit prostředí, které spravujete.</span><span class="sxs-lookup"><span data-stu-id="5b513-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="5b513-212">Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.</span><span class="sxs-lookup"><span data-stu-id="5b513-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="5b513-213">Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**).</span><span class="sxs-lookup"><span data-stu-id="5b513-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="5b513-214">Vyberte volbu **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="5b513-215">Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="5b513-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
