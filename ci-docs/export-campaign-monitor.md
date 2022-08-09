---
title: Export segmentů do služby Campaign Monitor (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196294"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Export segmentů do služby Campaign Monitor (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Campaign Monitor a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Campaign Monitor](https://www.campaignmonitor.com/) a odpovídající přihlašovací údaje správce.
- [ID seznamu Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- [Vygenerovaný klíč rozhraní API](https://www.campaignmonitor.com/api/getting-started/) z **Nastavení účtu** nejprve ve službě Campaign Monitor pro získání ID seznamu rozhraní API.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na jeden export do služby Campaign Monitor, což může trvat až 20 minut. Počet zákaznických profilů, které můžete exportovat do služby Campaign Monitor, závisí na vaší smlouvě s Campaign Monitor.
- Pouze segmenty.

## <a name="set-up-connection-to-campaign-monitor"></a>Nastavení propojení s Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Campaign Monitor**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. K inicializaci propojení se službou Campaign Monitor vyberte **Propojit**.

1. Vyberte **Ověření pomocí Campaign Monitor** a poskytněte své přihlašovací údaje pro Campaign Monitor.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Campaign Monitor. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID seznamu Campaign Monitor**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. Je nutné exportovat segmenty do Campaign Monitor.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
