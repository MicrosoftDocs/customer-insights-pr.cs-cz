---
title: Konektor pro Power BI
description: Zjistěte, jak používat konektor Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405356"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="ec53c-103">Konektor pro Power BI (preview)</span><span class="sxs-lookup"><span data-stu-id="ec53c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="ec53c-104">Vytvářejte vizualizace svých dat pomocí Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ec53c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="ec53c-105">Vytvářejte další informace a vytvářejte přehledy s vašimi sjednocenými údaji o zákaznících.</span><span class="sxs-lookup"><span data-stu-id="ec53c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec53c-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ec53c-106">Prerequisites</span></span>

- <span data-ttu-id="ec53c-107">Máte sjednocené profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="ec53c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="ec53c-108">Nejnovější verze [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je v počítači nainstalována.</span><span class="sxs-lookup"><span data-stu-id="ec53c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="ec53c-109">[Další informace o aplikaci Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)</span><span class="sxs-lookup"><span data-stu-id="ec53c-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="ec53c-110">Konfigurace konektorupro Power BI</span><span class="sxs-lookup"><span data-stu-id="ec53c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="ec53c-111">V Power BI Desktop vyberte **Soubor** > **Získat data**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="ec53c-112">Vyberte **Zobrazit více** vyhledejte **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="ec53c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="ec53c-113">Vyberte výsledek a vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="ec53c-114">**Přihláste se** se stejným účtem organizace, který používáte pro Customer Insights a vyberte **Připojit**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ec53c-115">Účet, který uvedete v tomto kroku, se používá k načtení dat ze služby Customer Insights a nemusí být totožný s tím, kterým jste přihlášeni k Power BI.</span><span class="sxs-lookup"><span data-stu-id="ec53c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="ec53c-116">Chcete-li obnovit účet, který se používá k načítání dat, otevřete Power BI a jděte na **Soubor** > **Možnosti** > **Nastavení** > **Nastavení zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="ec53c-117">V seznamu zdrojů dat vyberte **Přihlášení k Dynamics 365 Customer Insights** a vyberte **Vymazat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="ec53c-118">V dialogovém okně **Navigátor**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="ec53c-119">se zobrazí seznam všech prostředí, do kterých máte přístup.</span><span class="sxs-lookup"><span data-stu-id="ec53c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="ec53c-120">Rozbalte prostředí a otevřete libovolnou složku (entity, míry, segmenty, rozšíření).</span><span class="sxs-lookup"><span data-stu-id="ec53c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="ec53c-121">Například otevřete složky **Entity**, abyste viděli všechny entity, které můžete importovat.</span><span class="sxs-lookup"><span data-stu-id="ec53c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="ec53c-122">![Navigátor konektoru Power BI](media/power-bi-navigator.png "Navigátor konektoru Power BI")</span><span class="sxs-lookup"><span data-stu-id="ec53c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="ec53c-123">Zaškrtněte políčka vedle entit, které chcete zahrnout, a **Načíst**.</span><span class="sxs-lookup"><span data-stu-id="ec53c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="ec53c-124">Můžete vybrat více entit z více prostředí.</span><span class="sxs-lookup"><span data-stu-id="ec53c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="ec53c-125">Během načítání entit se zobrazí dialogové okno načítání.</span><span class="sxs-lookup"><span data-stu-id="ec53c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="ec53c-126">Jakmile se načtou všechny vaše vybrané entity, můžete použít funkce Power BI pro vizualizaci dat.</span><span class="sxs-lookup"><span data-stu-id="ec53c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="ec53c-127">Velké datové sady</span><span class="sxs-lookup"><span data-stu-id="ec53c-127">Large data sets</span></span>

<span data-ttu-id="ec53c-128">Konektor Customer Insights pro Power BI je navržen pro práci s datovými sadami, které obsahují až 1 milion profilů zákazníků.</span><span class="sxs-lookup"><span data-stu-id="ec53c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="ec53c-129">Import větších souborů dat může fungovat, ale trvá to dlouho.</span><span class="sxs-lookup"><span data-stu-id="ec53c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="ec53c-130">Proces by navíc mohl běžet do časového limitu z důvodu omezení Power BI.</span><span class="sxs-lookup"><span data-stu-id="ec53c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="ec53c-131">Další informace viz [Power BI: Doporučení pro velké soubory dat](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="ec53c-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="ec53c-132">Práce s podmnožinou dat</span><span class="sxs-lookup"><span data-stu-id="ec53c-132">Work with a subset of data</span></span>

<span data-ttu-id="ec53c-133">Zvažte práci s podmnožinou vašich dat.</span><span class="sxs-lookup"><span data-stu-id="ec53c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="ec53c-134">Můžete například vytvořit [segmenty](segments.md) místo exportování všech záznamů zákazníka do Power BI.</span><span class="sxs-lookup"><span data-stu-id="ec53c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
