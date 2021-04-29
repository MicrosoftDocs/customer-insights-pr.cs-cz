---
title: Aktivity zákazníka
description: Definování aktivit zákazníků a jejich zobrazení na časové ose zákazníků.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866399"
---
# <a name="customer-activities"></a><span data-ttu-id="0f7d7-103">Aktivity zákazníka</span><span class="sxs-lookup"><span data-stu-id="0f7d7-103">Customer activities</span></span>

<span data-ttu-id="0f7d7-104">Zkombinujte aktivity zákazníků z [různých zdrojů dat](data-sources.md) v Dynamics 365 Customer Insights k vytvoření časové osy, která chronologicky uvádí aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="0f7d7-105">Zahrňte časovou osu do aplikací Dynamics 365 pomocí řešení [Doplněk Zákaznická karta](customer-card-add-in.md) nebo v řídicím panelu Power BI.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="0f7d7-106">Definování aktivity</span><span class="sxs-lookup"><span data-stu-id="0f7d7-106">Define an activity</span></span>

<span data-ttu-id="0f7d7-107">Vaše zdroje dat mohou zahrnovat entity s transakčními a aktivními daty z více zdrojů dat.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="0f7d7-108">Identifikujte tyto entity a vyberte aktivity, které chcete zobrazit na časové ose zákazníka.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="0f7d7-109">Vyberte entitu, která zahrnuje vaši cílovou aktivitu nebo aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="0f7d7-110">Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka a nelze přidávat entity bez pole **Datum**.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="0f7d7-111">Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="0f7d7-112">V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="0f7d7-113">Výběrem možnosti **Přidat aktivitu** spusťte řízené prostředí pro proces nastavení aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="0f7d7-114">V kroku **Data aktivity** nastavte hodnoty pro následující pole:</span><span class="sxs-lookup"><span data-stu-id="0f7d7-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="0f7d7-115">**Název aktivity**: Vyberte název své aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="0f7d7-116">**Entita**: Vyberte entitu, která obsahuje údaje o transakcích nebo aktivitách.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="0f7d7-117">**Primární klíč**: Vyberte pole, které jedinečně identifikuje záznam.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="0f7d7-118">Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nastavte data aktivity s názvem, entitou a primárním klíčem.":::

1. <span data-ttu-id="0f7d7-120">Vyberte **Další** pro přechod k dalšímu kroku.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="0f7d7-121">V kroku **Vztah** nakonfigurujte podrobnosti pro propojení dat o aktivitě s odpovídajícím zákazníkem.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="0f7d7-122">Tento krok vizualizuje spojení mezi entitami.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="0f7d7-123">**První**: Cizí pole ve vaší entitě aktivity, které se použije k navázání vztahu s jinou entitou.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="0f7d7-124">**Druhý**: Odpovídající entita zdrojového zákazníka, se kterou bude vaše entita aktivity ve vztahu.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="0f7d7-125">Můžete ji přidružit pouze ke zdrojovým entitám zákazníků, které se používají v procesu sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="0f7d7-126">**Třetí**: Pokud vztah mezi touto entitou aktivity a vybranou entitou zdrojového zákazníka již existuje, název vztahu bude v režimu jen pro čtení.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="0f7d7-127">Pokud takový vztah neexistuje, vytvoří se nový vztah se jménem, které uvedete v tomto poli.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definujte vztah entity.":::

1. <span data-ttu-id="0f7d7-129">Vyberte **Další** pro přechod k dalšímu kroku.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="0f7d7-130">V kroku **Sjednocení aktivity** vyberte událost aktivity a čas zahájení aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="0f7d7-131">**Povinná pole**</span><span class="sxs-lookup"><span data-stu-id="0f7d7-131">**Required fields**</span></span>
      1. <span data-ttu-id="0f7d7-132">**Aktivita události**: Pole, které je událostí pro tuto aktivitu</span><span class="sxs-lookup"><span data-stu-id="0f7d7-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="0f7d7-133">**Časové razítko**: Pole, které představuje čas zahájení vaší aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="0f7d7-134">**Nepovinná pole**</span><span class="sxs-lookup"><span data-stu-id="0f7d7-134">**Optional fields**</span></span>
      1. <span data-ttu-id="0f7d7-135">**Další podrobnosti**: Pole s příslušnými informacemi pro tuto aktivitu.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="0f7d7-136">**Ikona**: Ikona, která nejlépe představuje tento typ aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="0f7d7-137">**Webová adresa**: Pole obsahující adresu URL s informacemi o této aktivitě.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="0f7d7-138">Například transakční systém, který tuto aktivitu využívá.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="0f7d7-139">Tato adresa URL může být libovolné pole zdroje dat, nebo může být vytvořeno jako nové pole pomocí transformace Power Query.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="0f7d7-140">Data URL budou uložena v entitě *Sjednocená aktivita*, kterou lze následně spotřebovat pomocí [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="0f7d7-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Zadejte údaje o aktivitě zákazníka v entitě Unified Activity.":::

1. <span data-ttu-id="0f7d7-142">Volbou **Další** přejdete na další krok.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="0f7d7-143">Můžete vybrat **Dokončit a zkontrolovat** pro uložení aktivity nyní s typem aktivity nastaveným na **Jiný**.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="0f7d7-144">V kroku **Typ aktivity** vyberte typ aktivity a volitelně vyberte, zda chcete sémanticky mapovat některé typy aktivit pro použití v jiných oblastech Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="0f7d7-145">V současné době lze typy aktivity *Předplatné* & *SalesOrderLine* sémanticky mapovat po souhlasu s mapováním polí.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="0f7d7-146">Pokud typ aktivity není pro novou aktivitu relevantní, můžete si vybrat *Jiný* nebo *Vytvořit nový* pro vlastní typ aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="0f7d7-147">Volbou **Další** přejdete na další krok.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="0f7d7-148">V kroku **Kontrola** ověřte výběr.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="0f7d7-149">Vrátíte se k některému z předchozích kroků a v případě potřeby informace aktualizujete.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Zkontrolujte aktivitu v zadaných polích.":::
   
1. <span data-ttu-id="0f7d7-151">Vyberte **Uložit aktivitu** pro použití změn a vyberte **Hotovo** pro návrat na **Data** > **Aktivity**.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="0f7d7-152">Zde vidíte, které aktivity jsou nastaveny tak, aby se zobrazovaly na časové ose.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="0f7d7-153">Na stránce **Aktivity** vyberte **Spustit** ke zpracování aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="0f7d7-154">Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0f7d7-155">Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0f7d7-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0f7d7-156">Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0f7d7-157">Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="0f7d7-158">Správa existujících aktivit</span><span class="sxs-lookup"><span data-stu-id="0f7d7-158">Manage existing activities</span></span>

<span data-ttu-id="0f7d7-159">Na stránce **Data** > **Aktivity** můžete zobrazit všechny uložené aktivity a spravovat je.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="0f7d7-160">Každá aktivita je reprezentována řádkem, který také obsahuje podrobnosti o zdroji, entitě a typu aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="0f7d7-161">Následující akce jsou k dispozici, když vyberete aktivitu.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="0f7d7-162">**Upravit**: Otevře nastavení aktivity v kroku kontroly.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="0f7d7-163">Z tohoto kroku můžete změnit některou nebo celou aktuální konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="0f7d7-164">Po změně konfigurace vyberte **Uložit aktivitu** a poté vyberte **Spustit** ke zpracování změn.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="0f7d7-165">**Přejmenovat**: Otevře dialogové okno, kde zadáte jiný název vybrané aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="0f7d7-166">Výběrem možnosti **Uložit** se vaše změny uplatní.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="0f7d7-167">**Vymazat**: Otevře dialogové okno s potvrzením odstranění vybrané aktivity.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="0f7d7-168">Můžete také odstranit více než jednu aktivitu najednou tak, že vyberete aktivity a poté vyberete ikonu odstranění.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="0f7d7-169">Vyberte **Odstranit** pro potvrzení odstranění.</span><span class="sxs-lookup"><span data-stu-id="0f7d7-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
