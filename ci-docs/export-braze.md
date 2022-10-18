---
title: Export segmentů do Braze (Preview)
description: Zjistěte, jak nakonfigurovat připojení a export do Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655268"
---
# <a name="export-segments-to-braze-preview"></a>Export segmentů do Braze (Preview)

Zjistěte, jak exportovat segmenty profilů Unified Customer Profile do Braze a použít je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Braze](https://www.braze.com/) a odpovídající přihlašovací údaje správce.
- [Klíč rozhraní API služby Braze](https://www.braze.com/docs/api/basics/)
- Váš [koncový bod Braze REST](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Profily Unified Customer Profile v exportovaných segmentech obsahují pole představující e-mailovou adresu a ID zákazníka Braze.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů do Braze může trvat až 40 minut. Počet zákaznických profilů, které můžete exportovat do Braze, závisí na vaší smlouvě s Braze.
- Pouze segmenty.
- Azure Private Link není podporován pro export Braze.

## <a name="set-up-connection-to-braze"></a>Nastavení připojení k Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Braze**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadáním klíče rozhraní API pro Braze pokračujte v přihlášení.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v sekci Braze. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte svůj koncový bod REST do pole **Název hostitele** v následujícím formátu: `rest.iad-03.braze.com`.

1. Zadejte název exportu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. V poli **ID zákazníka** vyberte pole, které představuje ID Braze zákazníka. Segmenty v Braze budou vytvořeny se stejným názvem jako v Dynamics 365 Customer Insights. Můžete vybrat další volitelná pole pro párování dat.

1. Vyberte entity nebo segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
