---
title: Export segmentů do služby Mailchimp (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725024"
---
# <a name="export-segments-to-mailchimp-preview"></a>Export segmentů do služby Mailchimp (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Mailchimp a vytvářejte bulletiny a e-mailové kampaně.

## <a name="prerequisites"></a>Předpoklady

- [Účet Mailchimp](https://mailchimp.com/) a odpovídající přihlašovací údaje správce.
- [Existující cílové skupiny ve službě Mailchimp](https://mailchimp.com/help/create-audience/) a odpovídající [ID cílových skupin](https://mailchimp.com/help/find-audience-id/).
- [Konfigurované segmenty](segments.md).
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 1 milion zákaznických profilů na jeden export do Mailchimp může trvat až tři hodiny. Počet zákaznických profilů, které můžete exportovat do Mailchimp, závisí na vaší smlouvě s Mailchimp.
- Pouze segmenty.

## <a name="set-up-connection-to-mailchimp"></a>Nastavení propojení s aplikací Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Mailchimp**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí Mailchimp** a zadejte své přihlašovací údaje ke službě Mailchimp.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Mailchimp. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID cílové skupiny Mailchimp**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně exportujte **křestní jméno** a **příjmení** pro vytvoření více přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
