---
title: Export segmentů do služby AdRoll (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724670"
---
# <a name="export-segments-to-adroll-preview"></a>Export segmentů do služby AdRoll (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby AdRoll a použijte je pro reklamu.

## <a name="prerequisites"></a>Předpoklady

- [Účet AdRoll](https://www.adroll.com/) a odpovídající přihlašovací údaje správce.
- [ID služby AdRoll Advertiser](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 250 000 zákaznických profilů na jeden export do služby AdRoll, což může trvat až 10 minut. Počet zákaznických profilů, které můžete exportovat do služby AdRoll, závisí na vaší smlouvě s AdRoll a je jí omezen.
- Pouze segmenty. Segment musí obsahovat alespoň 100 zákaznických profilů.

## <a name="set-up-connection-to-adroll"></a>Nastavení propojení s AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **AdRoll**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí AdRoll** a zadejte své přihlašovací údaje správce k AdRoll.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části AdRoll. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vložte své **ID inzerenta AdRoll**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
