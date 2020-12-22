---
title: Vyhledání podobných zákazníků pomocí AI
description: Najděte podobné segmenty zákazníků pomocí uměl= inteligence.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405383"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="9e403-103">Podobní zákazníci (náhled)</span><span class="sxs-lookup"><span data-stu-id="9e403-103">Similar Customers (preview)</span></span>

<span data-ttu-id="9e403-104">Tato funkce vám umožní najít podobné zákazníky ve vaší zákaznické základně pomocí umělé inteligence.</span><span class="sxs-lookup"><span data-stu-id="9e403-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="9e403-105">Abyste mohli tuto funkci používat, musíte mít vytvořen alespoň jeden segment.</span><span class="sxs-lookup"><span data-stu-id="9e403-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="9e403-106">Rozšíření kritérií existujícího segmentu pomůže najít zákazníky podobné tomuto segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="9e403-107">*Najděte podobné zákazníky* používá automatizované prostředky k vyhodnocování údajů a vytváření předpovědí na základě těchto údajů, a proto má schopnost být použita jako metoda profilování, protože tento pojem je definován obecným nařízením o ochraně údajů („GDPR“).</span><span class="sxs-lookup"><span data-stu-id="9e403-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="9e403-108">Použití této funkce zákazníkem ke zpracování dat může podléhat GDPR nebo jiným zákonům nebo předpisům.</span><span class="sxs-lookup"><span data-stu-id="9e403-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9e403-109">Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně predikcí, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.</span><span class="sxs-lookup"><span data-stu-id="9e403-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="9e403-110">Najít podobné zákazníky</span><span class="sxs-lookup"><span data-stu-id="9e403-110">Finding similar customers</span></span>

1. <span data-ttu-id="9e403-111">V přehledech cílové skupiny přejděte na **Segmenty** a vyberte segment, na kterém chcete založit svůj nový segment.</span><span class="sxs-lookup"><span data-stu-id="9e403-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="9e403-112">To je váš *zdrojový segment*.</span><span class="sxs-lookup"><span data-stu-id="9e403-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="9e403-113">Na panelu akcí vyberte **Najděte podobné zákazníky**.</span><span class="sxs-lookup"><span data-stu-id="9e403-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="9e403-114">Zkontrolujte navrhované jméno nového segmentu a v případě potřeby jej změňte.</span><span class="sxs-lookup"><span data-stu-id="9e403-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="9e403-115">Zkontrolujte pole, která definují váš nový segment.</span><span class="sxs-lookup"><span data-stu-id="9e403-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="9e403-116">Tato pole definují základ, na kterém se systém pokusí najít podobné zákazníky ve vašem zdrojovém segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="9e403-117">Systém ve výchozím nastavení vybere doporučená pole.</span><span class="sxs-lookup"><span data-stu-id="9e403-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="9e403-118">Pole, která mohou výrazně snížit výkon modelu, jsou automaticky vyloučena:</span><span class="sxs-lookup"><span data-stu-id="9e403-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="9e403-119">Pole s následujícími typy dat: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="9e403-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="9e403-120">Pole s mohutností (počet prvků v poli) menší než 2 nebo více než 30</span><span class="sxs-lookup"><span data-stu-id="9e403-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="9e403-121">Zvolte, zda chcete zahrnout **Všichni zákazníci** nebo pouze zákazníci v **Specifickém existujícím segmentu** ve vašem novém segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="9e403-122">Vyloučte zákazníky ve svém zdrojovém segmentu výběrem zaškrtávacího políčka **Vyloučit všechny ve zdrojovém segmentu**.</span><span class="sxs-lookup"><span data-stu-id="9e403-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="9e403-123">Ve výchozím nastavení systém navrhuje zahrnout do výstupu pouze 20% z velikosti cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="9e403-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="9e403-124">Upravte tuto mezní hodnotu podle potřeby.</span><span class="sxs-lookup"><span data-stu-id="9e403-124">Edit this threshold as needed.</span></span> <span data-ttu-id="9e403-125">Zvýšení mezní hodnoty sníží přesnost.</span><span class="sxs-lookup"><span data-stu-id="9e403-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="9e403-126">Vyberte **Spustit** ve spodní části stránky a spusťte úlohu binární klasifikace (metoda strojového učení), která analyzuje datový soubor.</span><span class="sxs-lookup"><span data-stu-id="9e403-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="9e403-127">Zobrazit podobný segment</span><span class="sxs-lookup"><span data-stu-id="9e403-127">View the similar segment</span></span>

<span data-ttu-id="9e403-128">Po zpracování podobného segmentu najdete nový segment uvedený v seznamu na stránce **Segmenty**.</span><span class="sxs-lookup"><span data-stu-id="9e403-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e403-129">![Podobný segment zákazníků](media/expanded-segment.png "Podobný segment zákazníků")</span><span class="sxs-lookup"><span data-stu-id="9e403-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="9e403-130">Vyberte **Pohled** na panelu akcí a otevřete detail segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="9e403-131">Toto zobrazení obsahuje informace o distribuci výsledků napříč [skórem podobnosti](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="9e403-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="9e403-132">Hodnoty skóre podobnosti najdete také v **Náhledu členů segmentu**.</span><span class="sxs-lookup"><span data-stu-id="9e403-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="9e403-133">Použijte výstup podobného segmentu</span><span class="sxs-lookup"><span data-stu-id="9e403-133">Use the output of a similar segment</span></span>

<span data-ttu-id="9e403-134">Můžete [pracovat s výstupem podobného segmentu](segments.md) stejně jako u jiných segmentů.</span><span class="sxs-lookup"><span data-stu-id="9e403-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="9e403-135">Například exportujte segment nebo vytvořte měřítko.</span><span class="sxs-lookup"><span data-stu-id="9e403-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="9e403-136">Aktualizujte a upravte podobný segment</span><span class="sxs-lookup"><span data-stu-id="9e403-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="9e403-137">Chcete-li obnovit podobný segment, vyberte jej na stránce **Segmenty** a vyberte **Obnovit** na panelu akcí.</span><span class="sxs-lookup"><span data-stu-id="9e403-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="9e403-138">Úpravy podobného segmentu znovu zpracují vaše data.</span><span class="sxs-lookup"><span data-stu-id="9e403-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="9e403-139">Dříve vytvořený segment se aktualizuje aktualizovanými daty.</span><span class="sxs-lookup"><span data-stu-id="9e403-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="9e403-140">Chcete-li upravit podobný segment, vyberte jej na stránce **Segmenty** a vyberte **Upravit** na panelu akcí.</span><span class="sxs-lookup"><span data-stu-id="9e403-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="9e403-141">Použijte své změny a vyberte **Spustit** pro zahájení zpracování.</span><span class="sxs-lookup"><span data-stu-id="9e403-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="9e403-142">Odstranit podobný segment</span><span class="sxs-lookup"><span data-stu-id="9e403-142">Delete a similar segment</span></span>

<span data-ttu-id="9e403-143">Vyberte segment an stránce **Segmenty** a vyberte **Odstranit** na panelu akcí.</span><span class="sxs-lookup"><span data-stu-id="9e403-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="9e403-144">Pak podvrďte odstranění.</span><span class="sxs-lookup"><span data-stu-id="9e403-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="9e403-145">O skóre podobnosti</span><span class="sxs-lookup"><span data-stu-id="9e403-145">About similarity scores</span></span>

<span data-ttu-id="9e403-146">Model strojového učení binární klasifikace přiřazuje skóre zákazníkům v podobném segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="9e403-147">Skóre je založeno na podobnosti se zákazníky ve zdrojovém segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="9e403-148">Skóre podobnosti pod 0,55 jsou zákazníci klasifikovaní systémem jako *ne podobní* zákazníkům ve zdrojovém segmentu</span><span class="sxs-lookup"><span data-stu-id="9e403-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="9e403-149">Skóre podobnosti mezi 0,55 - 0,7 se klasifikuje jako *trochu podobné*</span><span class="sxs-lookup"><span data-stu-id="9e403-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="9e403-150">Skóre podobnosti mezi 0,7 - 0,85 se klasifikuje jako *podobné*</span><span class="sxs-lookup"><span data-stu-id="9e403-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="9e403-151">Skóre podobnosti mezi 0,85 - 1 jsou zákazníci klasifikovaní jako *velmi podobní*</span><span class="sxs-lookup"><span data-stu-id="9e403-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="9e403-152">Zákazníci s skóre podobnosti pod 0,4 nejsou do výstupu modelu zahrnuti.</span><span class="sxs-lookup"><span data-stu-id="9e403-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="9e403-153">Systém je nepovažuje za dostatečně podobné zdrojovému segmentu.</span><span class="sxs-lookup"><span data-stu-id="9e403-153">The system doesn't consider them similar enough to the source segment.</span></span>
