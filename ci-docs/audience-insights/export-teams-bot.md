---
title: Bot pro Microsoft Teams
description: Vyhledejte sjednocené profily zákazníků v Microsoft Teams pomocí bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405384"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="e6230-103">Bot Teams pro Dynamics 365 Customer Insights (Preview)</span><span class="sxs-lookup"><span data-stu-id="e6230-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="e6230-104">Připojte se k Microsoft Teams, aby mohl bot vyhledat sjednocené profily zákazníků v kanálech Teams.</span><span class="sxs-lookup"><span data-stu-id="e6230-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e6230-105">![Bot Teams zobrazující zákaznický záznam](media/teams-bot.png "Bot Teams zobrazující zákaznický záznam")</span><span class="sxs-lookup"><span data-stu-id="e6230-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6230-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e6230-106">Prerequisites</span></span>

<span data-ttu-id="e6230-107">Chcete-li nastavit a konfigurovat robota, musí být splněny následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="e6230-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e6230-108">Je alespoň jeden [zdroj dat přidán](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e6230-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="e6230-109">[Proces sjednocení](data-unification.md) je dopončen.</span><span class="sxs-lookup"><span data-stu-id="e6230-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="e6230-110">Pole jsou přidána do [vyhledávacího a filtračního indexu](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="e6230-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="e6230-111">Customer Insights a Teams jsou ve stejné organizaci.</span><span class="sxs-lookup"><span data-stu-id="e6230-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="e6230-112">Nakonfigurujte bota</span><span class="sxs-lookup"><span data-stu-id="e6230-112">Configure the bot</span></span>

1. <span data-ttu-id="e6230-113">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="e6230-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="e6230-114">Na dlaždici Microsoft Teams vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="e6230-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="e6230-115">Jste přesměrováni na oblast **Aplikace** v Teams.</span><span class="sxs-lookup"><span data-stu-id="e6230-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="e6230-116">Můžete také otevřít Teams a vybrat **Aplikace** v levém dolním rohu nebo [je získat z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) přímo.</span><span class="sxs-lookup"><span data-stu-id="e6230-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="e6230-117">Vyhledejte **Customer Insights** a vyberte aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e6230-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="e6230-118">Vyberte **Přidat**.</span><span class="sxs-lookup"><span data-stu-id="e6230-118">Select **Add**.</span></span>
1. <span data-ttu-id="e6230-119">Po přihlášení k Customer Insights v Teams se zobrazí uvítací zpráva a můžete začít.</span><span class="sxs-lookup"><span data-stu-id="e6230-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="e6230-120">Věci, které lze dělat s botem</span><span class="sxs-lookup"><span data-stu-id="e6230-120">Things you can do with the bot</span></span>

<span data-ttu-id="e6230-121">Bot poskytuje možnosti vyhledávání pro jednotné profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="e6230-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="e6230-122">Zadejte **vyhledávání** následované názvem, e-mailovou adresou nebo jiným polem ve sjednoceném profilu zákazníka, který je přidán do indexu vyhledávání a filtru.</span><span class="sxs-lookup"><span data-stu-id="e6230-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="e6230-123">Z výsledného zákaznického profilu získáte kartu s až 15 poli.</span><span class="sxs-lookup"><span data-stu-id="e6230-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="e6230-124">Více shod vrátí seznam výsledků, kde si můžete vybrat profil.</span><span class="sxs-lookup"><span data-stu-id="e6230-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="e6230-125">Můžete přidat hledaný termín ve dvojitých uvozovkách a vyhledat přesnou shodu.</span><span class="sxs-lookup"><span data-stu-id="e6230-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="e6230-126">Pokud vaše organizace používá více prostředí Customer Insights ve stejné organizaci, můžete zadat **switchinstance**, čímž zvolíte, ke kterému prostředí chcete bota připojit.</span><span class="sxs-lookup"><span data-stu-id="e6230-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="e6230-127">Zadejte **pomoc** a zobrazíte seznam dostupných příkazů pro robota.</span><span class="sxs-lookup"><span data-stu-id="e6230-127">Enter **help** to see a list of available commands for the bot.</span></span>  
