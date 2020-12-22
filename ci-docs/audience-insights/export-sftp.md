---
title: Export dat Customer Insights do hostitelů SFTP
description: Naučte se, jak nakonfigurovat připojení k hostiteli SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643495"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="cc954-103">Konektor pro SFTP (preview)</span><span class="sxs-lookup"><span data-stu-id="cc954-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="cc954-104">Konektor SFTP umožňuje bezpečně exportovat vaše zákaznická data, která pak můžete používat v aplikacích třetích stran, do hostitele SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="cc954-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc954-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="cc954-105">Prerequisites</span></span>

- <span data-ttu-id="cc954-106">Dostupnost hostitele SFTP a odpovídající pověření.</span><span class="sxs-lookup"><span data-stu-id="cc954-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="cc954-107">Připojit se k SFTP</span><span class="sxs-lookup"><span data-stu-id="cc954-107">Connect to SFTP</span></span>

1. <span data-ttu-id="cc954-108">Přejděte na **Správce** > **Cíle exportu**.</span><span class="sxs-lookup"><span data-stu-id="cc954-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cc954-109">V **SFTP** vyberte **Založit**</span><span class="sxs-lookup"><span data-stu-id="cc954-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="cc954-110">Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.</span><span class="sxs-lookup"><span data-stu-id="cc954-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cc954-111">Zadejte **Uživatelské jméno**, **Heslo** a **Název hostitele** pro váš účet SFTP.</span><span class="sxs-lookup"><span data-stu-id="cc954-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="cc954-112">Příklad: Pokud je kořenová složka vašeho serveru SFTP /root/folder a chcete data exportovat do /root/folder/cilova_slozka_exportu_ci, měl by být hostitel sftp://<adresa_serveru>/cilova_slozka_exportu_ci".</span><span class="sxs-lookup"><span data-stu-id="cc954-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="cc954-113">Vyberte **Ověřit** pro otestování připojení.</span><span class="sxs-lookup"><span data-stu-id="cc954-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="cc954-114">Po úspěšném ověření zvolte, zda chcete exportovat data **Zazipovaná** nebo **Nezazipovaná** a vyberte **oddělovač pole** pro exportované soubory.</span><span class="sxs-lookup"><span data-stu-id="cc954-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="cc954-115">Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.</span><span class="sxs-lookup"><span data-stu-id="cc954-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cc954-116">Vyberte **Další** pro spuštění konfigurace exportu.</span><span class="sxs-lookup"><span data-stu-id="cc954-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="cc954-117">Konfigurujte připojení</span><span class="sxs-lookup"><span data-stu-id="cc954-117">Configure the connection</span></span>

1. <span data-ttu-id="cc954-118">Vyberte **atributy zákazníka**, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="cc954-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="cc954-119">Můžete exportovat jeden nebo více atributů.</span><span class="sxs-lookup"><span data-stu-id="cc954-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="cc954-120">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="cc954-120">Select **Next**.</span></span>

1. <span data-ttu-id="cc954-121">Vyberte segmenty, které chcete exportovat.</span><span class="sxs-lookup"><span data-stu-id="cc954-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="cc954-122">Zvolte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="cc954-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cc954-123">Export dat</span><span class="sxs-lookup"><span data-stu-id="cc954-123">Export the data</span></span>

<span data-ttu-id="cc954-124">Můžete [exportovat data na vyžádání](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cc954-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cc954-125">Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cc954-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cc954-126">Ochrana osobních údajů a dodržování předpisů</span><span class="sxs-lookup"><span data-stu-id="cc954-126">Data privacy and compliance</span></span>

<span data-ttu-id="cc954-127">Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje.</span><span class="sxs-lookup"><span data-stu-id="cc954-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cc954-128">Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="cc954-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cc954-129">Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cc954-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cc954-130">Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cc954-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
