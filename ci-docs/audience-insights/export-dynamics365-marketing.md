---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643765"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Konektor pro Dynamics 365 Marketing (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing. Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Požadavek

Záznamy kontaktů [z Dynamics 365 Marketing ingestované pomocí Common Data Service](connect-power-query.md).

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
