---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Naučte se, jak nakonfigurovat připojení k Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598101"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Konektor pro Dynamics 365 Sales (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.

## <a name="prerequisite"></a>Požadavek

1. Než budete moci exportovat segment z Customer Insights do aplikace Sales, musí se v Dynamics 365 Sales nacházet záznamy kontaktu. Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Sales pomocí Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Export segmentů z přehledů cílové skupiny do aplikace Sales nevytvoří nové záznamy kontaktů v instancích aplikace Sales. Záznamy kontaktů z aplikace Sales musí být zpracovány v přehledech cílové skupiny a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]