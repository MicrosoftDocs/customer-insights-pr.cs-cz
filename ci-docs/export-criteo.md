---
title: Export segmentů do Criteo (Preview)
description: Zjistěte, jak nakonfigurovat připojení a export do Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760018"
---
# <a name="export-segments-to-criteo-preview"></a>Export segmentů do Criteo (Preview)

Exportujte segmenty jednotných zákaznických profilů pro generování kampaní, e-mailový marketing a využívání specifických skupin zákazníků pomocí služby Criteo.

## <a name="prerequisites"></a>Předpoklady

- [Účet Criteo Dynamics Retargeting](https://www.criteo.com/login/) a odpovídající přihlašovací údaje správce.
- [Konfigurované segmenty](segments.md).
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na jeden export do služby Criteo, což může trvat až 30 minut. Počet zákaznických profilů, které můžete exportovat do služby Criteo, závisí na vaší smlouvě s Criteo.
- Pouze segmenty.

## <a name="set-up-connection-to-criteo"></a>Nastavení připojení ke Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Criteo**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověřit pomocí Criteo** a zadejte své uživatelské jméno správce a přihlašovací údaje pro Criteo.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v sekci Criteo. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
