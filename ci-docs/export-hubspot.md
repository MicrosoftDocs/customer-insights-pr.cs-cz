---
title: Export dat Customer Insights do služby HubSpot
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588900"
---
# <a name="export-segments-to-hubspot-preview"></a>Export segmentů do HubSpot (Preview)

Zjistěte, jak exportovat sjednocené zákaznické profily do HubSpot a použít pro e-mailový marketing.

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

- [Účet HubSpot](https://www.hubspot.com/) a odpovídající přihlašovací údaje správce.
- [Klíč rozhraní API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) z HubSpot.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Známá omezení

- Až 100 000 zákaznických profilů na export do HubSpot, jehož dokončení může trvat až 15 minut. Počet zákaznických profilů, které můžete exportovat do HubSpot, závisí na vaší smlouvě s HubSpot a je jí omezen.
- Pouze segmenty.

## <a name="set-up-connection-to-hubspot"></a>Nastavení propojení s aplikací HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **HubSpot** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Po zadání výzvy zadejte přihlašovací údaje HubSpot.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. K inicializaci propojení se službou HubSpot vyberte **Propojit**.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **Propojení pro export** vyberte propojení v části HubSpot. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Opakujte stejné kroky pro další volitelná pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
