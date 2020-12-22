---
title: Připojení k entitám ve spravovaném jezeře Common Data Service
description: Importovat data ze spravovaného datového jezera Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643390"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="356a3-103">Připojte se k datům ve spravovaném datovém jezeru Common Data Service</span><span class="sxs-lookup"><span data-stu-id="356a3-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="356a3-104">Tento článek poskytuje informace o tom, jak se stávající zákazníci Dynamics 365 mohou rychle připojit ke svým analytickým entitám ve spravovaném jezeru Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="356a3-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="356a3-105">Musíte být administrátorem v organizaci Common Data Service, abyste se mohli podívat na seznam entit dostupných ve spravovaném jezeře.</span><span class="sxs-lookup"><span data-stu-id="356a3-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="356a3-106">Důležitá poznámka</span><span class="sxs-lookup"><span data-stu-id="356a3-106">Important considerations</span></span>

<span data-ttu-id="356a3-107">Data uložená v online službách, například Azure Data Lake Storage, mohou být uloženy na jiném místě, než kde jsou zpracovávána nebo ukládána data Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="356a3-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="356a3-108"> Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="356a3-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="356a3-109">Připojení k datovému jezeru spravovaném pomocí Common Data Service</span><span class="sxs-lookup"><span data-stu-id="356a3-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="356a3-110">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="356a3-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="356a3-111">Vyberte **Přidat zdroj dat**.</span><span class="sxs-lookup"><span data-stu-id="356a3-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="356a3-112">Vyberte **Připojit se k Common Data Service** a vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="356a3-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="356a3-113">Zadejte **Název** zdroje dat vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="356a3-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="356a3-114">Vyplňte pole **Adresa serveru** pro svou organizaci Common Data Service a vyberte **Přihlásit se**.</span><span class="sxs-lookup"><span data-stu-id="356a3-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="356a3-115">![Dialogové okno pro zadání adresy serveru Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="356a3-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="356a3-116">Vyberte entity, které chcete ingestovat z dostupného seznamu.</span><span class="sxs-lookup"><span data-stu-id="356a3-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="356a3-117">Pokud jsou některé entity již vybrány, mohou být použity jinými aplikacemi Dynamics 365 (jako například Dynamics 365 Sales Insights nebo Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="356a3-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="356a3-118">Tento výběr nelze změnit.</span><span class="sxs-lookup"><span data-stu-id="356a3-118">You can't change the selection.</span></span> <span data-ttu-id="356a3-119">Tyto entity budou k dispozici, jakmile se vytvoří zdroj dat.</span><span class="sxs-lookup"><span data-stu-id="356a3-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="356a3-120">![Dialogové okno zobrazující seznam entit v organizaci Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="356a3-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="356a3-121">Uložte výběr a začněte synchronizovat vybrané entity se spravovaným jezerem Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="356a3-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="356a3-122">Nově přidané připojení najdete na stránce **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="356a3-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="356a3-123">Bude zařazeno do fronty pro aktualizaci a zobrazí počet entit jako 0, dokud nebudou všechny entity synchronizovány.</span><span class="sxs-lookup"><span data-stu-id="356a3-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="356a3-124">Pouze jeden zdroj dat prostředí může současně používat totéž spravované jezero Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="356a3-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="356a3-125">Úprava zdroje dat datového jezera spravovaného pomocí Common Data Service</span><span class="sxs-lookup"><span data-stu-id="356a3-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="356a3-126">Výběr entit můžete upravit až po vytvoření zdroje dat.</span><span class="sxs-lookup"><span data-stu-id="356a3-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="356a3-127">Například pokud byly přidány další entity do Common Data Service a chcete je také importovat.</span><span class="sxs-lookup"><span data-stu-id="356a3-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="356a3-128">Pokud se chcete připojit k jiné instanci Common Data Service, [vytvořte nový zdroj dat](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="356a3-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="356a3-129">V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.</span><span class="sxs-lookup"><span data-stu-id="356a3-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="356a3-130">Vedle zdroje dat, který chcete aktualizovat, vyberte tři tečky.</span><span class="sxs-lookup"><span data-stu-id="356a3-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="356a3-131">V seznamu vyberte volbu **Upravit**.</span><span class="sxs-lookup"><span data-stu-id="356a3-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="356a3-132">Vyberte další entity z dostupného seznamu entit a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="356a3-132">Select additional entities from the available list of entities and select **Save**.</span></span>
