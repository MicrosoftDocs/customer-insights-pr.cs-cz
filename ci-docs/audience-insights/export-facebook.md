---
title: Export dat Customer Insights do služby Facebook Ads Manager
description: Naučte se, jak nakonfigurovat připojení Správce reklam Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269966"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Konektor pro Správce reklam Facebook (náhled)

Export segmentů sjednocených zákaznických profilů do Správce reklam Facebook pro vytváření kampaní Facebook a Instagram.

## <a name="prerequisites"></a>Požadavky

- Musíte mít [**reklamní účet Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), který obsahuje [**podnikatelský účet Facebook**](https://business.facebook.com/).
- Musíte být správcem [**reklamního účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Připojte se ke Správci reklam Facebook

1. Přejděte na **Správce** > **Cíle exportu**.

1. Ve **Správci reklam Facebook** vyberte **Založit**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Vyberte **Pokračovat s Facebook** pro příhlášení ke svému reklamnímu účtu Facebook.

1. Povolte oprávnění **ads_management** po ověření pomocí Facebooku.

1. Vyberte **Reklmaní účet Facebook**, se kterým chcete pracovat.

1. Vyberte **Existující vlastní cílová skupina** z rozevíracího seznamu nebo vytvořte **Nová vlastní cílová skupina**. Další informace viz [**Cílové skupiny ve Správci reklam Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. Ve **Vyberte pole identifikátoru klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon** pro odeslání do Správce reklam Facebook.

1. Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.
   > [TIP] Nejlepší šance na shodu nastanou, pokud vyberte **E-mail** jako identifikátor klíče. Přidání dalších identifikátorů může zlepšit shodu.

1. Vyberte **Přidat atribut**, chcete-li mapovat další atributy, které chcete odeslat do Správce reklam Facebook. Atributy Správce reklam Facebook mapují následující uživatelsky přívětivá jména: **FN** = **křestní jméno**, **LN** = **příjmení**, **FI** = **Počáteční písmeno**, **PHONE** = **Telefon**, **GEN** = **pohlaví**, **DOB** = **Datum narození**, **ST** = **Stát**, **CT** = **Město**, **ZIP** = **PSČ**, **COUNTRY** = **Země / Region**

1. Vyberte segmenty, které chcete exportovat.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).

## <a name="known-limitations"></a>Známá omezení

- Až 10 milionů zákaznických profilů na jeden export do služby Facebook Správce reklam 
- Export do služby Facebook Správce reklam je omezen na segmenty
- Export segmentů s celkem 10 milionem profilů může trvat až 90 minut

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby Facebook Ads Manager, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Facebook Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]