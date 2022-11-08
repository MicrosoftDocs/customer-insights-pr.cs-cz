---
title: Export segmentů do Sendinblue (náhled)
description: Naučte se, jak nakonfigurovat propojení a exportovat ho do Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724886"
---
# <a name="export-segments-to-sendinblue-preview"></a>Export segmentů do Sendinblue (náhled)

Segmenty sjednocených profilů zákazníků exportujte pro účely generování kampaní, poskytování e-mailového marketingu a využívání konkrétních skupin zákazníků se Sendinblue.

## <a name="prerequisites"></a>Předpoklady

- [Účet Sendinblue](https://www.sendinblue.com/) a odpovídající pověření správce.
- [Klíč rozhraní API služby SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- V Sendinblue existují seznamy a odpovídající ID.
- [Konfigurované segmenty](segments.md).
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Privátní propojení v kombinaci s použitím vlastního úložiště (BYOS) není podporováno.
- Až 1 milion zákaznických profilů na export do služby Sendinblue, což může trvat až 90 minut. Počet zákaznických profilů, které můžete exportovat do služby Sendinblue, závisí na vaší smlouvě se službou Sendinblue.
- Pouze segmenty.

## <a name="set-up-connection-to-sendinblue"></a>Nastavení připojení se Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Sendinblue**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **klíč API služby SendinBlue**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** zvolte připojení z části Sendinblue. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte **ID seznamu Sendinblue**.

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka.

1. Volitelně exportujte **křestní jméno**, **příjmení** a **telefon** k vytvoření přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
