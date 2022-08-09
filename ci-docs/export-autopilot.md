---
title: Export segmentů do Autopilot (náhled)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195052"
---
# <a name="export-segments-to-autopilot-preview"></a>Export segmentů do Autopilot (náhled)

Exportujte segmenty sjednocených profilů zákazníků do služby Autopilot a použijte je pro e-mailový marketing ve službě Autopilot.

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

- [Účet Autopilot](https://www.autopilothq.com/) a odpovídající přihlašovací údaje správce.
- [Klíč rozhraní API služby Autopilot](https://autopilot.docs.apiary.io/#)
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 100 000 zákaznických profilů na jeden export do služby Autopilot může trvat pár hodin. Počet zákaznických profilů, které můžete exportovat do služby Autopilot, závisí na vaší smlouvě se službou Autopilot.
- Pouze segmenty.

## <a name="set-up-connection-to-autopilot"></a>Nastavení propojení s aplikací Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Autopilot**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte klíč rozhraní API Autopilot.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Autopilot. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně exportujte další pole jako **křestní jméno** a **příjmení**.

1. Vyberte segmenty, které chcete exportovat, podle popsaných omezení.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
