---
title: 'Konektor LiveRamp '
description: Naučte se, jak exportovat data do služby LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667176"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="d09bf-103">konektor LiveRamp&reg; (preview)</span><span class="sxs-lookup"><span data-stu-id="d09bf-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="d09bf-104">Aktivujte data v LiveRamp a propojte se s více než 500 platformami napříč digitálními, sociálními a televizními ekosystémy.</span><span class="sxs-lookup"><span data-stu-id="d09bf-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="d09bf-105">Pracujte s vašimi daty v LiveRampu na cílení, potlačení a personalizaci reklamních kampaní.</span><span class="sxs-lookup"><span data-stu-id="d09bf-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d09bf-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d09bf-106">Prerequisites</span></span>

- <span data-ttu-id="d09bf-107">K použití tohoto konektoru potřebujete předplatné LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d09bf-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d09bf-108">Chcete-li získat předplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) přímo.</span><span class="sxs-lookup"><span data-stu-id="d09bf-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d09bf-109">[Další informace o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d09bf-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="d09bf-110">Připojte se k LiveRampu</span><span class="sxs-lookup"><span data-stu-id="d09bf-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="d09bf-111">V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="d09bf-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d09bf-112">V dlaždici **LiveRamp** vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="d09bf-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d09bf-113">Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="d09bf-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d09bf-114">Zadejte **Uživatelské jméno** a **Heslo** pro váš účet LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="d09bf-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d09bf-115">Tato pověření se mohou lišit od vašich pověření LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="d09bf-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d09bf-116">Vyberte **Ověřit** a otestujte připojení k LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d09bf-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d09bf-117">Po úspěšném ověření poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="d09bf-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d09bf-118">Vyberte **Další** pro nastavení konektoru LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d09bf-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d09bf-119">Konfigurace konektoru</span><span class="sxs-lookup"><span data-stu-id="d09bf-119">Configure the connector</span></span>

1. <span data-ttu-id="d09bf-120">V poli **Vyberte svůj identifikátor klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon**, který chcete poslat do LiveRampu pro rozlišení identity.</span><span class="sxs-lookup"><span data-stu-id="d09bf-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="d09bf-121">Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.</span><span class="sxs-lookup"><span data-stu-id="d09bf-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d09bf-122">Vyberte **Přidat atribut**, chcete-li mapovat další atributy k odeslání na LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d09bf-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d09bf-123">Odesláním dalších atributů identifikátoru klíče na server LiveRamp pravděpodobně dosáhnete vyšší míry shody.</span><span class="sxs-lookup"><span data-stu-id="d09bf-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d09bf-124">Vyberte segmenty, které chcete exportovat do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="d09bf-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d09bf-125">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="d09bf-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d09bf-126">![Konektor LiveRamp s mapováním atributů](media/export-liveramp-segments.png "Konektor LiveRamp s mapováním atributů")</span><span class="sxs-lookup"><span data-stu-id="d09bf-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d09bf-127">Export dat</span><span class="sxs-lookup"><span data-stu-id="d09bf-127">Export the data</span></span>

<span data-ttu-id="d09bf-128">Export bude zahájen brzy, jakmile budou splněny všechny předpoklady pro export.</span><span class="sxs-lookup"><span data-stu-id="d09bf-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="d09bf-129">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d09bf-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="d09bf-130">Po úspěšném dokončení exportu se můžete přihlásit k LiveRamp Onboarding a aktivovat a distribuovat svá data.</span><span class="sxs-lookup"><span data-stu-id="d09bf-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d09bf-131">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="d09bf-131">Data privacy and compliance</span></span>

<span data-ttu-id="d09bf-132">Když povolíte Dynamics 365 Customer Insights přenos dat do služby Liveramp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="d09bf-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d09bf-133">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Liveramp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="d09bf-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d09bf-134">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d09bf-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d09bf-135">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d09bf-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>