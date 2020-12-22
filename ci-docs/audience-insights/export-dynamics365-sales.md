---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643810"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Konektor pro Dynamics 365 Sales (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.

## <a name="prerequisite"></a>Požadavek

Záznamy kontaktů [z Dynamics 365 Sales ingestované pomocí Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Nakonfigurujte konektor pro Sales

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. V **Dynamics 365 Sales** vyberte **Založit**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.

1. Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.

1. Vyberte **Další**.

1. Vyberte jeden nebo více segmentů.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).
