---
title: Export segmentů do služby DotDigital (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724978"
---
# <a name="export-segments-to-dotdigital-preview"></a>Export segmentů do služby DotDigital (preview)

Exportujte segmenty sjednocených profilů zákazníků do adresářů DotDigital a použijte je pro kampaně, e-mailový marketing a vytváření segmentů zákazníků s pomocí služby DotDigital.

## <a name="prerequisites"></a>Předpoklady

- [Účet DotDigital](https://dotdigital.com/) a [uživatel API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- ID DotDigital z [nového](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) nebo existujícího adresáře v DotDigital. ID najdete v adrese URL, když vyberete a otevřete adresář.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 1 milion zákaznických profilů na jeden export do DotDigital, což může kvůli omezením na straně poskytovatele trvat až tři hodiny. Počet zákaznických profilů, které můžete exportovat do DotDigital, závisí na vaší smlouvě s DotDigital.
- Pouze segmenty.

## <a name="set-up-connection-to-dotdigital"></a>Nastavení propojení s aplikací DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **DotDigital**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **uživatelské jméno a heslo pro DotDigital API**.

1. Zadejte svoje **ID adresáře DotDigital**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části DotDigital. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně exportujte **křestní jméno**, **příjmení**, **celé jméno**, **rod** a **PSČ**.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Ve službě DotDigital vyhledejte své segmenty v [adresářích DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
