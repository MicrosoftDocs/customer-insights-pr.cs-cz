---
title: Export dat Customer Insights do služby Facebook Ads Manager
description: Naučte se, jak nakonfigurovat připojení Správce reklam Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643675"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="49ed7-103">Konektor pro Správce reklam Facebook (náhled)</span><span class="sxs-lookup"><span data-stu-id="49ed7-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="49ed7-104">Export segmentů sjednocených zákaznických profilů do Správce reklam Facebook pro vytváření kampaní Facebook a Instagram.</span><span class="sxs-lookup"><span data-stu-id="49ed7-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49ed7-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="49ed7-105">Prerequisites</span></span>

- <span data-ttu-id="49ed7-106">Musíte mít [**reklamní účet Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), který obsahuje [**podnikatelský účet Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="49ed7-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="49ed7-107">Musíte být správcem [**reklamního účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="49ed7-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="49ed7-108">Připojte se ke Správci reklam Facebook</span><span class="sxs-lookup"><span data-stu-id="49ed7-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="49ed7-109">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="49ed7-110">Ve **Správci reklam Facebook** vyberte **Založit**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="49ed7-111">Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="49ed7-112">Vyberte **Pokračovat s Facebook** pro příhlášení ke svému reklamnímu účtu Facebook.</span><span class="sxs-lookup"><span data-stu-id="49ed7-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="49ed7-113">Povolte oprávnění **ads_management** po ověření pomocí Facebooku.</span><span class="sxs-lookup"><span data-stu-id="49ed7-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="49ed7-114">Vyberte **Reklmaní účet Facebook**, se kterým chcete pracovat.</span><span class="sxs-lookup"><span data-stu-id="49ed7-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="49ed7-115">Vyberte **Existující vlastní cílová skupina** z rozevíracího seznamu nebo vytvořte **Nová vlastní cílová skupina**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="49ed7-116">Další informace viz [**Cílové skupiny ve Správci reklam Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="49ed7-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="49ed7-117">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="49ed7-118">Vyberte **Další** pro konfiguraci exportu.</span><span class="sxs-lookup"><span data-stu-id="49ed7-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="49ed7-119">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="49ed7-119">Configure the connector</span></span>

1. <span data-ttu-id="49ed7-120">Ve **Vyberte pole identifikátoru klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon** pro odeslání do Správce reklam Facebook.</span><span class="sxs-lookup"><span data-stu-id="49ed7-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="49ed7-121">Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="49ed7-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="49ed7-122">[TIP] Nejlepší šance na shodu nastanou, pokud vyberte **E-mail** jako identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="49ed7-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="49ed7-123">Přidání dalších identifikátorů může zlepšit shodu.</span><span class="sxs-lookup"><span data-stu-id="49ed7-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="49ed7-124">Vyberte **Přidat atribut**, chcete-li mapovat další atributy, které chcete odeslat do Správce reklam Facebook.</span><span class="sxs-lookup"><span data-stu-id="49ed7-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="49ed7-125">Atributy Správce reklam Facebook mapují následující uživatelsky přívětivá jména: **FN** = **křestní jméno**, **LN** = **příjmení**, **FI** = **Počáteční písmeno**, **PHONE** = **Telefon**, **GEN** = **pohlaví**, **DOB** = **Datum narození**, **ST** = **Stát**, **CT** = **Město**, **ZIP** = **PSČ**, **COUNTRY** = **Země / Region**</span><span class="sxs-lookup"><span data-stu-id="49ed7-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="49ed7-126">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="49ed7-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="49ed7-127">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="49ed7-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="49ed7-128">Export dat</span><span class="sxs-lookup"><span data-stu-id="49ed7-128">Export the data</span></span>

<span data-ttu-id="49ed7-129">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="49ed7-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="49ed7-130">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49ed7-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49ed7-131">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="49ed7-131">Data privacy and compliance</span></span>

<span data-ttu-id="49ed7-132">Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby Facebook Ads Manager, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="49ed7-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49ed7-133">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Facebook Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="49ed7-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="49ed7-134">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="49ed7-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="49ed7-135">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="49ed7-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
