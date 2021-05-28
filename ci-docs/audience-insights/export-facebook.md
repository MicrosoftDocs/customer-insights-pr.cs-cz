---
title: Export dat Customer Insights do služby Facebook Ads Manager
description: Zjistěte, jak nakonfigurovat připojení a exportovat je do služby Facebook Správce reklam.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976034"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="c5a96-103">Export seznamu segmentů do Facebook Správce reklam (preview)</span><span class="sxs-lookup"><span data-stu-id="c5a96-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="c5a96-104">Export segmentů sjednocených zákaznických profilů do Správce reklam Facebook pro vytváření kampaní Facebook a Instagram.</span><span class="sxs-lookup"><span data-stu-id="c5a96-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="c5a96-105">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="c5a96-105">Prerequisites for connection</span></span>

- <span data-ttu-id="c5a96-106">Musíte mít účet [**Facebook pro reklamy**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), který zahrnuje účet [**Facebook pro firmy**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="c5a96-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="c5a96-107">Musíte být správcem [**reklamního účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="c5a96-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c5a96-108">Známá omezení</span><span class="sxs-lookup"><span data-stu-id="c5a96-108">Known limitations</span></span>

- <span data-ttu-id="c5a96-109">Až 10 milionů zákaznických profilů na jeden export do služby Facebook Správce reklam.</span><span class="sxs-lookup"><span data-stu-id="c5a96-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="c5a96-110">Export do služby Facebook Správce reklam je omezen na segmenty.</span><span class="sxs-lookup"><span data-stu-id="c5a96-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="c5a96-111">Vytvářejte nebo aktualizujte vlastní cílovou skupinu pouze typu Facebook *seznam zákazníků*.</span><span class="sxs-lookup"><span data-stu-id="c5a96-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="c5a96-112">Export segmentů s celkem 10 milionem profilů může trvat až 90 minut.</span><span class="sxs-lookup"><span data-stu-id="c5a96-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="c5a96-113">Nastavení propojení se správcem reklam Facebook</span><span class="sxs-lookup"><span data-stu-id="c5a96-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="c5a96-114">Než uživatelé mohou vytvořit export, musí správce nakonfigurovat propojení ke službě a umožnit přispěvatelům propojení použít.</span><span class="sxs-lookup"><span data-stu-id="c5a96-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="c5a96-115">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c5a96-116">Vyberte **Přidat propojení** a zvolte **Facebook Správce reklam** pro konfiguraci propojení.</span><span class="sxs-lookup"><span data-stu-id="c5a96-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="c5a96-117">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c5a96-118">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="c5a96-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c5a96-119">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="c5a96-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c5a96-120">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="c5a96-120">Choose who can use this connection.</span></span> <span data-ttu-id="c5a96-121">Pokud neprovedete žádnou akci, výchozí bude **Správci**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="c5a96-122">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c5a96-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c5a96-123">Ověření pomocí Facebook reklam:</span><span class="sxs-lookup"><span data-stu-id="c5a96-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="c5a96-124">Vyberte **Pokračovat s Facebook** pro příhlášení ke svému reklamnímu účtu Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5a96-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="c5a96-125">Povolte oprávnění **ads_management** po ověření pomocí Facebooku.</span><span class="sxs-lookup"><span data-stu-id="c5a96-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="c5a96-126">Vyberte **Reklmaní účet Facebook**, se kterým chcete pracovat.</span><span class="sxs-lookup"><span data-stu-id="c5a96-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="c5a96-127">Vyberte **Existující vlastní cílová skupina** z rozevíracího seznamu nebo vytvořte **Nová vlastní cílová skupina**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="c5a96-128">Další informace viz [**Cílové skupiny ve Správci reklam Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="c5a96-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="c5a96-129">Vlastní cílové skupiny můžete vytvářet nebo aktualizovat pouze na Facebooku typu *seznam zákazníků* s tímto exportem.</span><span class="sxs-lookup"><span data-stu-id="c5a96-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="c5a96-130">V některých případech se v rozevíracím seznamu zobrazí vlastní cílová skupina různých typů.</span><span class="sxs-lookup"><span data-stu-id="c5a96-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="c5a96-131">Výběr jiného typu než *seznam zákazníků* bude mít za následek selhání exportu.</span><span class="sxs-lookup"><span data-stu-id="c5a96-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="c5a96-132">Zkontrolujte část **Ochrana osobních údajů a dodržování předpisů** a vyberte **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="c5a96-133">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c5a96-134">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="c5a96-134">Configure an export</span></span>

<span data-ttu-id="c5a96-135">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="c5a96-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c5a96-136">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c5a96-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c5a96-137">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c5a96-138">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="c5a96-139">V poli **Propojení pro export** zvolte propojení v části **Správce reklam Facebook**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="c5a96-140">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="c5a96-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c5a96-141">Ve **Vyberte pole identifikátoru klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon** pro odeslání do Správce reklam Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5a96-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="c5a96-142">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c5a96-143">Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="c5a96-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="c5a96-144">[TIP] Nejlepší šance na shodu nastanou, pokud vyberte **E-mail** jako identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="c5a96-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="c5a96-145">Přidání dalších identifikátorů může zlepšit shodu.</span><span class="sxs-lookup"><span data-stu-id="c5a96-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="c5a96-146">Vyberte **Přidat atribut** k mapování více atributů pro odeslání do Správce reklam Facebook.</span><span class="sxs-lookup"><span data-stu-id="c5a96-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="c5a96-147">Atributy Správce reklam Facebook mapují následující uživatelsky přehledná jména: **FN** = **křestní jméno**, **LN** = **příjmení**, **FI** = **Počáteční písmeno**, **PHONE** = **Telefon**, **GEN** = **pohlaví**, **DOB** = **Datum narození**, **ST** = **Stát**, **CT** = **Město**, **ZIP** = **PSČ**, **COUNTRY** = **Země / Region**</span><span class="sxs-lookup"><span data-stu-id="c5a96-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="c5a96-148">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="c5a96-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c5a96-149">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="c5a96-149">Select **Save**.</span></span>

<span data-ttu-id="c5a96-150">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="c5a96-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c5a96-151">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c5a96-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c5a96-152">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c5a96-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c5a96-153">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="c5a96-153">Data privacy and compliance</span></span>

<span data-ttu-id="c5a96-154">Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby Facebook Ads Manager, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="c5a96-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c5a96-155">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Facebook Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="c5a96-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c5a96-156">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c5a96-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c5a96-157">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c5a96-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
