---
title: Aktivity zákazníka
description: Definování aktivit zákazníků a jejich zobrazení na časové ose zákazníků.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267424"
---
# <a name="customer-activities"></a><span data-ttu-id="b6b43-103">Aktivity zákazníka</span><span class="sxs-lookup"><span data-stu-id="b6b43-103">Customer activities</span></span>

<span data-ttu-id="b6b43-104">Zkombinujte aktivity zákazníků z [různých zdrojů dat](data-sources.md) v Dynamics 365 Customer Insights a vytvořte časovou osu zákazníků se seznamem aktivit v chronologickém pořadí.</span><span class="sxs-lookup"><span data-stu-id="b6b43-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="b6b43-105">Časovou osu můžete zahrnout do aplikací pro zapojení zákazníků v Dynamics 365 prostřednictvím [doplňku karty zákazníka](customer-card-add-in.md) nebo v řídicím panelu Power BI.</span><span class="sxs-lookup"><span data-stu-id="b6b43-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="b6b43-106">Definování aktivity</span><span class="sxs-lookup"><span data-stu-id="b6b43-106">Define an activity</span></span>

<span data-ttu-id="b6b43-107">Vaše zdroje dat zahrnují entity s transakčními a aktivními daty z více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="b6b43-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="b6b43-108">Identifikujte tyto entity a vyberte aktivity, které chcete zobrazit na časové ose zákazníka.</span><span class="sxs-lookup"><span data-stu-id="b6b43-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="b6b43-109">Vyberte entitu, která zahrnuje vaši cílovou aktivitu nebo aktivity.</span><span class="sxs-lookup"><span data-stu-id="b6b43-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="b6b43-110">V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="b6b43-111">Vyberte **Přidat aktivitu**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b6b43-112">Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka a nelze přidávat entity bez pole **Datum**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="b6b43-113">Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.</span><span class="sxs-lookup"><span data-stu-id="b6b43-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="b6b43-114">V podokně **Přidat aktivitu** nastavte hodnoty pro následující pole:</span><span class="sxs-lookup"><span data-stu-id="b6b43-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="b6b43-115">**Entita**: Vyberte entitu, která obsahuje údaje o transakcích nebo aktivitách.</span><span class="sxs-lookup"><span data-stu-id="b6b43-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="b6b43-116">**Primární klíč**: Vyberte pole, které jedinečně identifikuje záznam.</span><span class="sxs-lookup"><span data-stu-id="b6b43-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="b6b43-117">Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.</span><span class="sxs-lookup"><span data-stu-id="b6b43-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="b6b43-118">**Časové razítko**: Vyberte pole, které představuje čas zahájení vaší aktivity.</span><span class="sxs-lookup"><span data-stu-id="b6b43-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="b6b43-119">**Událost**: Vyberte pole, které je událostí pro aktivitu.</span><span class="sxs-lookup"><span data-stu-id="b6b43-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="b6b43-120">**Webová adresa**: Vyberte pole představující adresu URL s dalšími informacemi o této aktivitě.</span><span class="sxs-lookup"><span data-stu-id="b6b43-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="b6b43-121">Například transakční systém, který tuto aktivitu využívá.</span><span class="sxs-lookup"><span data-stu-id="b6b43-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="b6b43-122">Tato adresa URL může být libovolné pole zdroje dat, nebo může být vytvořeno jako nové pole pomocí transformace Power Query.</span><span class="sxs-lookup"><span data-stu-id="b6b43-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="b6b43-123">Tato data URL budou uložena v entitě Sjednocená aktivita, která může být spotřebována jako navazující pomocí API.</span><span class="sxs-lookup"><span data-stu-id="b6b43-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="b6b43-124">**Podrobnosti**: Volitelně vyberte pole, které se přidá pro další podrobnosti.</span><span class="sxs-lookup"><span data-stu-id="b6b43-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="b6b43-125">**Ikona**: Volitelně vyberte ikonu představující tuto aktivitu.</span><span class="sxs-lookup"><span data-stu-id="b6b43-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="b6b43-126">**Typ aktivity**: Definujte odkaz na typ aktivity v Common Data Model, který nejlépe popisuje sémantickou definici aktivity.</span><span class="sxs-lookup"><span data-stu-id="b6b43-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="b6b43-127">V sekci **Nastavit vztah** nakonfigurujte podrobnosti tak, aby se údaje o vaší činnosti připojily k odpovídajícímu zákazníkovi.</span><span class="sxs-lookup"><span data-stu-id="b6b43-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="b6b43-128">**Pole entity aktivity**: Vyberte pole v entitě aktivity, které bude použito k navázání vztahu s jinou entitou.</span><span class="sxs-lookup"><span data-stu-id="b6b43-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="b6b43-129">**Entita zákazníka**: Vyberte odpovídající zdrojovou entitu zákazníka, se kterou bude vaše entita aktivity ve vztahu.</span><span class="sxs-lookup"><span data-stu-id="b6b43-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="b6b43-130">Můžete se vztahovat pouze k těm zdrojovým zákaznickým entitám, které se používají v procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="b6b43-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="b6b43-131">**Pole entity zákazníka**: Toto pole zobrazuje primární klíč zdrojové zákaznické entity vybraný v procesu mapování.</span><span class="sxs-lookup"><span data-stu-id="b6b43-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="b6b43-132">Toto pole primárního klíče ve zdrojové entitě zákazníka se používá k navázání vztahu s entitou aktivity.</span><span class="sxs-lookup"><span data-stu-id="b6b43-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="b6b43-133">**Název**: Pokud již existuje vztah mezi touto entitou aktivity a vybranou zdrojovou entitou zákazníka, bude název vztahu v režimu jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="b6b43-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="b6b43-134">Pokud takový vztah neexistuje, bude vytvořen nový vztah se zde uvedeným názvem.</span><span class="sxs-lookup"><span data-stu-id="b6b43-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6b43-135">![Definování vztahů entit](media/activities-entities-define.png "Definování vztahů entit")</span><span class="sxs-lookup"><span data-stu-id="b6b43-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="b6b43-136">Výběrem možnosti **Uložit** se vaše změny uplatní.</span><span class="sxs-lookup"><span data-stu-id="b6b43-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="b6b43-137">Na stránce **Aktivity** vyberte možnost **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="b6b43-138">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="b6b43-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b6b43-139">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b6b43-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b6b43-140">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="b6b43-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b6b43-141">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="b6b43-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="b6b43-142">Úprava aktivity</span><span class="sxs-lookup"><span data-stu-id="b6b43-142">Edit an activity</span></span>

1. <span data-ttu-id="b6b43-143">V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b6b43-144">Vyberte entitu aktivity, kterou chcete upravit, a vyberte **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="b6b43-145">Nebo se můžete pohybovat nad řádkem entity a vybrat ikonu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="b6b43-146">Klikněte na ikonu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="b6b43-147">V podokně **Upravit aktivitu** aktualizujte hodnoty a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="b6b43-148">Na stránce **Aktivity** vyberte možnost **Spustit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="b6b43-149">Odstranění aktivity</span><span class="sxs-lookup"><span data-stu-id="b6b43-149">Delete an activity</span></span>

1. <span data-ttu-id="b6b43-150">V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="b6b43-151">Vyberte entitu aktivity, kterou chcete odebrat, a vyberte **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="b6b43-152">Nebo se můžete pohybovat nad řádkem entity a vybrat ikonu **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="b6b43-153">Kromě toho můžete vybrat více entit aktivity, které chcete odstranit najednou.</span><span class="sxs-lookup"><span data-stu-id="b6b43-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6b43-154">![Upravit nebo odstranit vztahy mezi entitami](media/activities-entities-edit-delete.png "Upravit nebo odstranit vztahy mezi entitami")</span><span class="sxs-lookup"><span data-stu-id="b6b43-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="b6b43-155">Vybrání ikony **Odstranit**.</span><span class="sxs-lookup"><span data-stu-id="b6b43-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="b6b43-156">Odstranění potvrďte.</span><span class="sxs-lookup"><span data-stu-id="b6b43-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]