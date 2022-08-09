---
title: Export segmentů do Omnisend (preview)
description: Naučte se konfigurovat připojení a export do služby Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196156"
---
# <a name="export-segments-to-omnisend-preview"></a>Export segmentů do Omnisend (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Omnisend a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Omnisend](https://www.omnisend.com/) a odpovídající přihlašovací údaje správce.
- [Klíč rozhraní API služby Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na jeden export do služby Omnisend, což může trvat až čtyři hodiny. Počet zákaznických profilů, které můžete exportovat do Omnisend, závisí na vaší smlouvě s Omnisend.
- Pouze segmenty.

## <a name="set-up-connection-to-omnisend"></a>Nastavení připojení ke službě Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Omnisend**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte svůj klíč rozhraní API Omnisend.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části Omnisend. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně můžete exportovat **křestní jméno**, **příjmení**, **adresu**, **zemi/oblast**, **stát**, **město** a **PSČ**, abyste vytvořili více přizpůsobené e-maily. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
