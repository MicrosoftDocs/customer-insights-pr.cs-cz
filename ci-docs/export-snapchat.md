---
title: Export segmentů do služby Snapchat (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do služby Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195374"
---
# <a name="export-segments-to-snapchat-preview"></a>Export segmentů do služby Snapchat (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Snapchat a použijte je pro reklamu.

## <a name="prerequisites"></a>Předpoklady

- [Účet Snapchat Business](https://business.snapchat.com/), [účet Snapchat Ads](https://ads.snapchat.com/) a odpovídající přihlašovací údaje správce. Musíte být alespoň členem obchodního vztahu organizace a správcem dat konkrétního účtu reklamy.
- Alespoň jedna cílová skupina typu SAM (Snap Audience Match) ve správci Snapchat Audience.
- [ID Snapchat Segment/Audience](https://businesshelp.snapchat.com/s/article/custom-audiences). ID cílové skupiny lze nalézt v adrese URL po výběru cílové skupiny ve správci cílové skupiny Snapchat.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů, což může trvat až 15 minut.
- Pouze segmenty.

## <a name="set-up-connection-to-snapchat"></a>Nastavení propojení se Snapchatem

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Snapchat**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí Snapchatu** a poskytněte své přihlašovací údaje pro Snapchat.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Snapchat. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID služby Snapchat Segment/Audience**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
