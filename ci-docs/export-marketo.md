---
title: Export segmentů do Marketo (náhled)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724932"
---
# <a name="export-segments-to-marketo-preview"></a>Export segmentů do Marketo (náhled)

Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.

## <a name="prerequisites"></a>Předpoklady

- [Účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.
- [ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/).
- [Marketo obsahuje stávající seznamy](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) a odpovídající ID.
- [Konfigurované segmenty](segments.md).
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 1 milion zákaznických profilů na jeden export do Marketo může trvat až 3 hodiny. Počet zákaznických profilů, které můžete exportovat do Marketo, závisí na vaší smlouvě s Marketo.
- Pouze segmenty.

## <a name="set-up-connection-to-marketo"></a>Nastavení propojení s aplikací Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Marketo**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST**. Koncový bod názvu hostitele REST je pouze název hostitele, bez https://. Příklad: xyz-abc-123.mktorest.com.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Propojení pro export** vyberte propojení v části Marketo. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID seznamu Marketo**. ID seznamu je čistě číselná hodnota. Například pokud je vaše ID seznamu Marketo ST12345A7, odstraňte znak před a za číslicemi a zadejte *12345*.

1. V sekci **Párování dat** vyberte alespoň jedno pole, které představuje e-mailovou adresu zákazníka nebo ID Marketo zákazníka.

1. Volitelně exportujte **křestní jméno**, **příjmení**, **město**, **stát** a **zemi/oblast** pro vytvoření více přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Ve službě Marketo vyhledejte své segmenty v části [Seznamy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
