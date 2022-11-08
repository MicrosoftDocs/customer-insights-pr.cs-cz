---
title: Export segmentů do Facebook Ads Manager (preview) (obsahuje video)
description: Zjistěte, jak nakonfigurovat připojení a exportovat je do služby Facebook Správce reklam.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724578"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Export segmentů do Facebook Ads Manager (preview)

Export segmentů sjednocených zákaznických profilů do Správce reklam Facebook pro vytváření kampaní Facebook a Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Předpoklady

- Potřebujete [reklamní účet Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), který zahrnuje [obchodní účet Facebook](https://business.facebook.com/).
- Oprávnění správce v [reklamním účtu Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Vlastní Podmínky cílové skupiny musí přijmout uživatel, který nastavuje připojení v Customer Insights.

## <a name="known-limitations"></a>Známá omezení

- Až 10 milion zákaznických profilů na export do správce reklam na Facebooku může trvat až 90 minut.
- Pouze segmenty.
- Integrace reklam Facebook nepodporuje uživatele s více než 25 reklamními účty.
- Typ *Seznam zákazníků* Facebook pouze ve [vlastních cílových skupinách](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > V některých případech se v rozevíracím seznamu mohou zobrazit vlastní cílové skupiny různých typů. Pokud vyberete jiný typ než *seznam zákazníků*, export selže.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavení propojení se správcem reklam Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Správce reklam na Facebooku**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. [Umožněte přispěvatelům použít propojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ověření pomocí Facebook reklam:

   1. Vyberte **Pokračovat s Facebook** pro přihlášení k účtu Facebook Ads.

   1. Povolte oprávnění **ads_management** po ověření pomocí Facebooku.

   1. Vyberte **Reklmaní účet Facebook**, se kterým chcete pracovat.

   1. V rozevíracím seznamu vyberte **Existující vlastní cílová skupina** nebo vytvořte **novou vlastní cílovou skupinu**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části Správce reklam na Facebooku. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V poli **Připojení dat** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon** pro odeslání do správce reklam na Facebooku.

1. Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.
   > [!TIP]
   > Nejlepší šance na shodu nastanou, pokud vyberte **E-mail** jako identifikátor klíče. Přidání dalších identifikátorů může zlepšit shodu.

1. Vyberte **Přidat atribut** k mapování více atributů pro odeslání do Správce reklam Facebook. Atributy Správce reklam Facebook mapují následující uživatelsky přehledná jména: **FN** = **křestní jméno**, **LN** = **příjmení**, **FI** = **Počáteční písmeno**, **PHONE** = **Telefon**, **GEN** = **pohlaví**, **DOB** = **Datum narození**, **ST** = **Stát**, **CT** = **Město**, **ZIP** = **PSČ**, **COUNTRY** = **Země / Region**

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
