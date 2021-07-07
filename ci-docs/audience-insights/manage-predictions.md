---
title: Sdílené úkoly pro scénáře predikcí
description: Naučte se spravovat a vylepšovat předpovědi a odstraňovat problémy s nimi.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315870"
---
# <a name="manage-predictions"></a><span data-ttu-id="10b24-103">Správa predikcí</span><span class="sxs-lookup"><span data-stu-id="10b24-103">Manage predictions</span></span>

<span data-ttu-id="10b24-104">Tento článek probírá některé úkoly, které sdílí většina scénářů predikcí.</span><span class="sxs-lookup"><span data-stu-id="10b24-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="10b24-105">Řešení potíží se selháním predikce</span><span class="sxs-lookup"><span data-stu-id="10b24-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="10b24-106">Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="10b24-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="10b24-107">Vyberte svislé tři tečky vedle predikce, u které chcete zobrazit protokoly chyb.</span><span class="sxs-lookup"><span data-stu-id="10b24-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="10b24-108">Vyberte **Protokoly**.</span><span class="sxs-lookup"><span data-stu-id="10b24-108">Select **Logs**.</span></span>

1. <span data-ttu-id="10b24-109">Zkontrolujte všechny chyby.</span><span class="sxs-lookup"><span data-stu-id="10b24-109">Review all the errors.</span></span> <span data-ttu-id="10b24-110">Existuje několik typů chyb, které mohou nastat a které popisují, jaký stav chybu způsobil.</span><span class="sxs-lookup"><span data-stu-id="10b24-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="10b24-111">Například chyba, že není k dispozici dostatek dat, aby bylo možné provést přesnou predikci, se obvykle vyřeší načtením dalších dat do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="10b24-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="10b24-112">Sestava použitelnosti vstupních dat</span><span class="sxs-lookup"><span data-stu-id="10b24-112">Input data usability report</span></span>

<span data-ttu-id="10b24-113">Sestava použitelnosti vstupních dat poskytuje konsolidovaný pohled na chyby a varování, které mohou generovat vaše předdefinované predikce.</span><span class="sxs-lookup"><span data-stu-id="10b24-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="10b24-114">Poskytuje také doporučení, jak zlepšit výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="10b24-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="10b24-115">Sestava je k dispozici poté, co model dokončí tréninkový proces.</span><span class="sxs-lookup"><span data-stu-id="10b24-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="10b24-116">Je vytvořena pro každý model samostatně, bez ohledu na to, zda byl úspěšně dokončen nebo ne.</span><span class="sxs-lookup"><span data-stu-id="10b24-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="10b24-117">Zobrazení sestavy použitelnosti vstupních dat</span><span class="sxs-lookup"><span data-stu-id="10b24-117">View the input data usability report</span></span>

<span data-ttu-id="10b24-118">Poté, co předpřipravený model dokončí svůj tréninkový krok, zobrazte sestavu:</span><span class="sxs-lookup"><span data-stu-id="10b24-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="10b24-119">Vyberte tři tečky vedle názvu modelu a zvolte možnost **Sestava použitelnosti vstupních dat**.</span><span class="sxs-lookup"><span data-stu-id="10b24-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="10b24-120">Vyberte stav modelu a vyberte položku **Zobrazit sestavu použitelnosti vstupních dat** v bočním podokně.</span><span class="sxs-lookup"><span data-stu-id="10b24-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="10b24-121">Vyberte jeden z modelů v seznamu a na panelu příkazů vyberte **Sestava použitelnosti vstupních dat**.</span><span class="sxs-lookup"><span data-stu-id="10b24-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="10b24-122">Otevřete stránku výsledků modelu a na panelu příkazů vyberte **Sestava použitelnosti vstupních dat**.</span><span class="sxs-lookup"><span data-stu-id="10b24-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="10b24-123">Informace v sestavě použitelnosti vstupních dat</span><span class="sxs-lookup"><span data-stu-id="10b24-123">Information in the input data usability report</span></span>

<span data-ttu-id="10b24-124">Následující sloupce v sestavě obsahují užitečné informace ke zlepšení dat pro model.</span><span class="sxs-lookup"><span data-stu-id="10b24-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Příklad sestavy použitelnosti vstupních dat zobrazující tabulku s chybami, varováními a doporučeními.":::

- <span data-ttu-id="10b24-126">Název: Popisný název chyby, varování nebo doporučení.</span><span class="sxs-lookup"><span data-stu-id="10b24-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="10b24-127">Krok: Fáze, školení nebo skóre modelu, které se informace týká.</span><span class="sxs-lookup"><span data-stu-id="10b24-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="10b24-128">Stav: Závažnost informací (chyba, varování, doporučení).</span><span class="sxs-lookup"><span data-stu-id="10b24-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="10b24-129">Název sloupce: Sloupec v entitě, který je třeba upravit, aby se zlepšil výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="10b24-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="10b24-130">Název entity: Název entity, kterou je třeba upravit, aby se zlepšil výkon modelu.</span><span class="sxs-lookup"><span data-stu-id="10b24-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="10b24-131">Podrobnosti: Podrobnosti o chybě, varování nebo doporučení.</span><span class="sxs-lookup"><span data-stu-id="10b24-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="10b24-132">Aktualizace předpovědi</span><span class="sxs-lookup"><span data-stu-id="10b24-132">Refresh a prediction</span></span>

<span data-ttu-id="10b24-133">Předpovědi se automaticky aktualizují podle stejného [plánu aktualizace dat](system.md#schedule-tab), jaký je konfigurován v nastavení.</span><span class="sxs-lookup"><span data-stu-id="10b24-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="10b24-134">Můžete je také aktualizovat ručně.</span><span class="sxs-lookup"><span data-stu-id="10b24-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="10b24-135">Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="10b24-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="10b24-136">Vyberte svislé tři tečky vedle predikce, kterou chcete aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="10b24-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="10b24-137">Vyberte **Aktualizovat**.</span><span class="sxs-lookup"><span data-stu-id="10b24-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="10b24-138">Odstranění predikce</span><span class="sxs-lookup"><span data-stu-id="10b24-138">Delete a prediction</span></span>

<span data-ttu-id="10b24-139">Odstraněním predikce odstraníte také jeho výstupní entitu.</span><span class="sxs-lookup"><span data-stu-id="10b24-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="10b24-140">Přejděte na **Analytické nástroje** > **Predikce** a vyberte kartu **Moje predikce**.</span><span class="sxs-lookup"><span data-stu-id="10b24-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="10b24-141">Vyberte svislé tři tečky vedle predikce, kterou chcete odstranit.</span><span class="sxs-lookup"><span data-stu-id="10b24-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="10b24-142">Vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="10b24-142">Select **Delete**.</span></span>
