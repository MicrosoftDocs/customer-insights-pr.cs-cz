---
title: Export segmentů do služby Constant Contact (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4d2ec29c194dc481ee40048b8ecbed813291b4d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196478"
---
# <a name="export-segments-to-constant-contact-preview"></a>Export segmentů do služby Constant Contact (preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Constant Contact a použijte je pro marketingové aktivity.

## <a name="prerequisites"></a>Předpoklady

- [Účet Constant Contact](https://www.constantcontact.com/account-home) a odpovídající přihlašovací údaje správce.
- [ID seznamu Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). Otevřete seznam v Constant Contact a vyhledejte ID seznamu v adrese URL.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na jeden export do služby Constant Contact, což může trvat až jednu hodinu. Počet zákaznických profilů, které můžete exportovat do služby Constant Contact, závisí na vaší smlouvě se Constant Contact.
- Pouze segmenty.

## <a name="set-up-connection-to-constant-contact"></a>Nastavení propojení s Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Constant Contact**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověřit pomocí konstantního kontaktu** a zadejte své přihlašovací údaje správce pro konstantní kontakt.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části Constant Contact. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID seznamu služby Constant Contact**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně exportujte **Křestní jméno** a **Příjmení** jako další pole k vytvoření lépe přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
