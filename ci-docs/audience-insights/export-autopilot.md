---
title: Export dat Customer Insights do služby Autopilot
description: Naučte se, jak nakonfigurovat připojení ke službě Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596122"
---
# <a name="connector-for-autopilot-preview"></a>Konektor pro službu Autopilot (Preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Autopilot a použijte je pro e-mailový marketing ve službě Autopilot. 

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Autopilot](https://www.autopilothq.com/) a odpovídající přihlašovací údaje správce.
-   V přehledech cílové skupiny máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="connect-to-autopilot"></a>Připojení ke službě Autopilot

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **Autopilot** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurační podokno pro připojení služby Autopilot.":::

1. Zadejte svůj **klíč rozhraní API služby Autopilot** [Klíč rozhraní API služby Autopilot](https://autopilot.docs.apiary.io/#).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Volbou **Připojit** inicializujte připojení ke službě Autopilot.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. Stejné kroky opakujte pro další volitelná pole, například **Křestní jméno**, **Příjmení**.

1. Vyberte segmenty, které chcete exportovat. Velice **doporučujeme neexportovat více než 100 000 profilů zákazníků** do služby Autopilot. 

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).

## <a name="known-limitations"></a>Známá omezení

- Do služby Autopilot můžete exportovat celkem až 100 000 profilů zákazníků.
- Export do služby Autopilot je omezen na segmenty.
- Export až 100 000 profilů do služby Autopilot může trvat až několik hodin. 
- Počet profilů, které můžete exportovat do služby Autopilot, závisí a je omezen na vaší smlouvě se službou Autopilot.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Autopilot, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Autopilot splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]