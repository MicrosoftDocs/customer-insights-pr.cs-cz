---
title: Export segmentů do služby RollWorks (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do služby RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725117"
---
# <a name="export-segments-to-rollworks-preview"></a>Export segmentů do služby RollWorks (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby RollWorks a použijte je pro reklamu.

## <a name="prerequisites"></a>Předpoklady

- [Účet RollWorks](https://www.rollworks.com/) a odpovídající přihlašovací údaje správce.
- [ID inzerenta RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 250 000 zákaznických profilů na jeden export do služby RollWorks, což může trvat až 10 minut. Počet zákaznických profilů, které můžete exportovat do služby RollWorks, závisí na vaší smlouvě s RollWorks.
- Pouze segmenty.

## <a name="set-up-connection-to-rollworks"></a>Nastavení propojení s aplikací RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **RollWorks**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat.  Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí RollWorks** a poskytněte své přihlašovací údaje pro RollWorks.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části RollWorks. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vložte své **ID inzerenta RollWorks**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
