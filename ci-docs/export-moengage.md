---
title: Export segmentů do MoEngage
description: Zjistěte, jak nakonfigurovat připojení a export do MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199088"
---
# <a name="export-segments-to-moengage-preview"></a>Export segmentů do MoEngage (Preview)

Exportujte segmenty sjednocených profilů zákazníků do služby MoEngage a použijte je pro e-mailový marketing ve službě MoEngage.

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

- [Účet MoEngage](https://www.moengage.com/) a odpovídající přihlašovací údaje správce.
- Klíč rozhraní API služby MoEngage z Nastavení > rozhraní API v MoEngage.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.

## <a name="known-limitations"></a>Známá omezení

- Až 100 000 zákaznických profilů na jeden export do MoEngage může trvat až 15 minut. Počet zákaznických profilů, které můžete exportovat do MoEngage, závisí na vaší smlouvě s MoEngage.
- Pouze segmenty.

## <a name="set-up-connection-to-moengage"></a>Nastavení propojení s MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a volbou **MoEngage** začněte konfigurovat připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vložte svoje [ID rozhraní API dat a klíč rozhraní API služby MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. K inicializaci propojení se službou MoEngage vyberte **Propojit**.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části MoEngage. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Opakujte stejné kroky pro další volitelná pole.

1. Vyberte segmenty, které chcete exportovat. Vytvoříme jeden nebo více segmentů se stejným názvem jako vybrané segmenty v MoEngage v sekci **Segmenty** > **Vlastní segmenty**.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
