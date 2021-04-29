---
title: 'Konektor LiveRamp '
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760319"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="3422a-103">Export segmentů do LiveRamp&reg; (náhled)</span><span class="sxs-lookup"><span data-stu-id="3422a-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="3422a-104">Aktivujte data na LiveRamp a spojte se s více než 500 platformami v digitálních, sociálních a televizních zařízeních.</span><span class="sxs-lookup"><span data-stu-id="3422a-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="3422a-105">Pracujte s vašimi daty v LiveRampu na cílení, potlačení a personalizaci reklamních kampaní.</span><span class="sxs-lookup"><span data-stu-id="3422a-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3422a-106">Předpoklady pro připojení</span><span class="sxs-lookup"><span data-stu-id="3422a-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="3422a-107">K použití tohoto konektoru potřebujete předplatné LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="3422a-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="3422a-108">Chcete-li získat předplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) přímo.</span><span class="sxs-lookup"><span data-stu-id="3422a-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="3422a-109">[Další informace o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="3422a-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="3422a-110">Nastavení propojení s LiveRamp</span><span class="sxs-lookup"><span data-stu-id="3422a-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="3422a-111">Přejděte na **Správce** > **Propojení**.</span><span class="sxs-lookup"><span data-stu-id="3422a-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3422a-112">Vyberte **Přidat připojení** a zvolte **LiveRamp** pro konfiguraci připojení.</span><span class="sxs-lookup"><span data-stu-id="3422a-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="3422a-113">Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="3422a-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3422a-114">Název a typ propojení popisují toto propojení.</span><span class="sxs-lookup"><span data-stu-id="3422a-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3422a-115">Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.</span><span class="sxs-lookup"><span data-stu-id="3422a-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3422a-116">Zvolte, kdo může toto připojení používat.</span><span class="sxs-lookup"><span data-stu-id="3422a-116">Choose who can use this connection.</span></span> <span data-ttu-id="3422a-117">Pokud neprovedete žádnou akci, výchozí bude Aministrátoři.</span><span class="sxs-lookup"><span data-stu-id="3422a-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3422a-118">Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3422a-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3422a-119">Zadejte **Uživatelské jméno** a **Heslo** pro váš účet LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="3422a-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="3422a-120">Tato pověření se mohou lišit od vašich pověření LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="3422a-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="3422a-121">Vyberte **Ověřit** a otestujte připojení k LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="3422a-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="3422a-122">Po úspěšném ověření poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="3422a-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="3422a-123">Dokončete propojení výběrem možnosti **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="3422a-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3422a-124">Konfigurace exportu</span><span class="sxs-lookup"><span data-stu-id="3422a-124">Configure an export</span></span>

<span data-ttu-id="3422a-125">Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="3422a-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3422a-126">Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3422a-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3422a-127">Přejděte na **Data** > **Exporty**.</span><span class="sxs-lookup"><span data-stu-id="3422a-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3422a-128">Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.</span><span class="sxs-lookup"><span data-stu-id="3422a-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3422a-129">V poli **propojení pro export** vyberte propojení v části LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="3422a-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="3422a-130">Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.</span><span class="sxs-lookup"><span data-stu-id="3422a-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3422a-131">V poli **Vyberte svůj identifikátor klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon**, který chcete poslat do LiveRampu pro rozlišení identity.</span><span class="sxs-lookup"><span data-stu-id="3422a-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3422a-132">![Konektor LiveRamp s mapováním atributů](media/export-liveramp-segments.png "Konektor LiveRamp s mapováním atributů")</span><span class="sxs-lookup"><span data-stu-id="3422a-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="3422a-133">Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="3422a-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="3422a-134">Vyberte **Přidat atribut** k mapování více atributů pro odeslání na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="3422a-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="3422a-135">Odesláním dalších atributů identifikátoru klíče na server LiveRamp pravděpodobně dosáhnete vyšší míry shody.</span><span class="sxs-lookup"><span data-stu-id="3422a-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="3422a-136">Vyberte segmenty, které chcete exportovat do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="3422a-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="3422a-137">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="3422a-137">Select **Save**.</span></span>

<span data-ttu-id="3422a-138">Uložení exportu nespustí export okamžitě.</span><span class="sxs-lookup"><span data-stu-id="3422a-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3422a-139">Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3422a-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3422a-140">Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3422a-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3422a-141">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="3422a-141">Data privacy and compliance</span></span>

<span data-ttu-id="3422a-142">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Liveramp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="3422a-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3422a-143">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Liveramp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="3422a-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3422a-144">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3422a-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3422a-145">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3422a-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
