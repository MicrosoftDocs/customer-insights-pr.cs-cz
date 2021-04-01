---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597595"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Konektor pro Dynamics 365 Marketing (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing. Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Požadavek

- Než budete moci exportovat segment z Customer Insights do aplikace Marketing, musí se v Dynamics 365 Marketing nacházet záznamy kontaktu. Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Marketing pomocí Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Export segmentů z přehledů cílové skupiny do aplikace Marketing nevytvoří nové záznamy kontaktů v instancích aplikace Marketing. Záznamy kontaktů z aplikace Marketing musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

## <a name="configure-the-connector-for-marketing"></a>Nakonfigurujte konektor pro marketing

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. V **Dynamics 365 Marketing** vyberte **Založit**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.

1. Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.

1. Vyberte **Další**.

1. Vyberte jeden nebo více segmentů.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]