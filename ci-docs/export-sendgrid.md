---
title: Export segmentů do SendGrid (náhled)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196984"
---
# <a name="export-segments-to-sendgrid-preview"></a>Export segmentů do SendGrid (náhled)

Exportujte segmenty sjednocených profilů zákazníků do seznamů kontaktů SendGrid a použijte je pro kampaně a e-mailový marketing ve službě SendGrid.

## <a name="prerequisites"></a>Předpoklady

- [Účet SendGrid](https://sendgrid.com/) a odpovídající přihlašovací údaje správce.
- [Existující seznam kontaktů ve službě SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) a odpovídající ID.
- [Klíč rozhraní API služby SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 100 000 zákaznických profilů celkem do SendGrid může trvat pár hodin. Počet zákaznických profilů, které můžete exportovat do služby SendGrid, závisí na vaší smlouvě se službou SendGrid.
- Pouze segmenty.

## <a name="set-up-connection-to-sendgrid"></a>Nastavení propojení se SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **SendGrid**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte svůj **klíč rozhraní API služby SendGrid**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Propojení pro export** vyberte propojení v části SendGrid. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte své **ID seznamu SendGrid**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně vyberte pole jako **Křestní jméno**, **Příjmení**, **Země/oblast**, **Stát**, **Město** a **PSČ**.

1. Vyberte segmenty, které chcete exportovat, podle popsaných omezení.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
