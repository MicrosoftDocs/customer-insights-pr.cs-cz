---
title: Konektor pro Power BI
description: Zjistěte, jak používat konektor Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596031"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="b8ace-103">Konektor pro Power BI (preview)</span><span class="sxs-lookup"><span data-stu-id="b8ace-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="b8ace-104">Vytvářejte vizualizace svých dat pomocí Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="b8ace-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="b8ace-105">Vytvářejte další informace a vytvářejte přehledy s vašimi sjednocenými údaji o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="b8ace-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8ace-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="b8ace-106">Prerequisites</span></span>

- <span data-ttu-id="b8ace-107">Máte sjednocené profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="b8ace-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="b8ace-108">Nejnovější verze [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalován v počítači.</span><span class="sxs-lookup"><span data-stu-id="b8ace-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="b8ace-109">[Další informace o aplikaci Power BI Desktop](/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="b8ace-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="b8ace-110">Konfigurace konektorupro Power BI</span><span class="sxs-lookup"><span data-stu-id="b8ace-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="b8ace-111">V Power BI Desktop vyberte **Soubor** > **Získat data**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="b8ace-112">Vyberte **Zobrazit více** vyhledejte **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="b8ace-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="b8ace-113">Vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-113">Select **Connect**.</span></span>

1. <span data-ttu-id="b8ace-114">**Přihláste se** se stejným účtem organizace, který používáte pro Customer Insights a vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b8ace-115">Účet, který uvedete v tomto kroku, se používá k načtení dat ze služby Customer Insights a nemusí být totožný s tím, kterým jste přihlášeni k Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="b8ace-116">Chcete-li obnovit účet, který se používá k načítání dat, otevřete Power BI a jděte na **Soubor** > **Možnosti** > **Nastavení** > **Nastavení zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="b8ace-117">V seznamu zdrojů dat vyberte **Přihlášení k Dynamics 365 Customer Insights** a vyberte **Vymazat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="b8ace-118">V dialogovém okně **Navigátor**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="b8ace-119">se zobrazí seznam všech prostředí, do kterých máte přístup.</span><span class="sxs-lookup"><span data-stu-id="b8ace-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="b8ace-120">Rozbalte prostředí a otevřete libovolnou složku (entity, míry, segmenty, rozšíření).</span><span class="sxs-lookup"><span data-stu-id="b8ace-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="b8ace-121">Například otevřete složky **Entity**, abyste viděli všechny entity, které můžete importovat.</span><span class="sxs-lookup"><span data-stu-id="b8ace-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="b8ace-122">![Navigátor konektoru Power BI](media/power-bi-navigator.png "Navigátor konektoru Power BI")</span><span class="sxs-lookup"><span data-stu-id="b8ace-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="b8ace-123">Zaškrtněte políčka vedle entit, které chcete zahrnout, a **Načíst**.</span><span class="sxs-lookup"><span data-stu-id="b8ace-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="b8ace-124">Můžete vybrat více entit z více prostředí.</span><span class="sxs-lookup"><span data-stu-id="b8ace-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="b8ace-125">Během načítání entit se zobrazí dialogové okno načítání.</span><span class="sxs-lookup"><span data-stu-id="b8ace-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="b8ace-126">Jakmile se načtou všechny vaše vybrané entity, můžete použít funkce Power BI pro vizualizaci dat.</span><span class="sxs-lookup"><span data-stu-id="b8ace-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="b8ace-127">Velké datové sady</span><span class="sxs-lookup"><span data-stu-id="b8ace-127">Large data sets</span></span>

<span data-ttu-id="b8ace-128">Konektor Customer Insights pro Power BI je navržen pro práci s datovými sadami, které obsahují až 1 milion profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="b8ace-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="b8ace-129">Import větších souborů dat může fungovat, ale trvá to dlouho.</span><span class="sxs-lookup"><span data-stu-id="b8ace-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="b8ace-130">Proces by navíc mohl běžet do časového limitu z důvodu omezení Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="b8ace-131">Další informace viz [Power BI: Doporučení pro velké soubory dat](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="b8ace-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="b8ace-132">Práce s podmnožinou dat</span><span class="sxs-lookup"><span data-stu-id="b8ace-132">Work with a subset of data</span></span>

<span data-ttu-id="b8ace-133">Zvažte práci s podmnožinou vašich dat.</span><span class="sxs-lookup"><span data-stu-id="b8ace-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="b8ace-134">Můžete například vytvořit [segmenty](segments.md) místo exportování všech záznamů zákazníka do Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b8ace-135">Řešení problému</span><span class="sxs-lookup"><span data-stu-id="b8ace-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="b8ace-136">Prostředí Customer Insights se nezobrazuje v Power BI</span><span class="sxs-lookup"><span data-stu-id="b8ace-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="b8ace-137">Prostředí, která mají více než jeden [vztah](relationships.md) definovaný mezi dvěma identickými entitami v přehledech cílové skupiny nebudou dostupné v konektoru Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="b8ace-138">Duplikované vztahy můžete identifikovat a odstranit.</span><span class="sxs-lookup"><span data-stu-id="b8ace-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="b8ace-139">V přehledech cílové skupiny přejděte na **Data** > **Vztahy** pro prostředí, ve kterém chybí Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="b8ace-140">Identifikujte duplicitní vztahy:</span><span class="sxs-lookup"><span data-stu-id="b8ace-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="b8ace-141">Zkontrolujte, zda je mezi stejnými dvěma entitami definován více než jeden vztah.</span><span class="sxs-lookup"><span data-stu-id="b8ace-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="b8ace-142">Zkontrolujte, zda existuje vztah vytvořený mezi dvěma entitami, které jsou obě zahrnuty do procesu sjednocení.</span><span class="sxs-lookup"><span data-stu-id="b8ace-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="b8ace-143">Mezi všemi entitami zahrnutými do procesu sjednocení je definován implicitní vztah.</span><span class="sxs-lookup"><span data-stu-id="b8ace-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="b8ace-144">Odstraňte veškeré identifikované duplicitní vztahy.</span><span class="sxs-lookup"><span data-stu-id="b8ace-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="b8ace-145">Po odstranění duplicitních vztahů zkuste znovu nakonfigurovat konektor Power BI.</span><span class="sxs-lookup"><span data-stu-id="b8ace-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="b8ace-146">Prostředí by mělo být ihned k dispozici.</span><span class="sxs-lookup"><span data-stu-id="b8ace-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]