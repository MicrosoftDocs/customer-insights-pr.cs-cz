---
title: Export dat Customer Insights do služby Facebook Ads Manager
description: Zjistěte, jak nakonfigurovat připojení a exportovat je do služby Facebook Správce reklam.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906802"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Export seznamu segmentů do Facebook Správce reklam (preview)

Export segmentů sjednocených zákaznických profilů do Správce reklam Facebook pro vytváření kampaní Facebook a Instagram.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

- Musíte mít účet [**Facebook pro reklamy**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), který zahrnuje účet [**Facebook pro firmy**](https://business.facebook.com/).
- Musíte být správcem [**reklamního účtu Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Známá omezení

- Až 10 milionů zákaznických profilů na jeden export do služby Facebook Správce reklam.
- Export do služby Facebook Správce reklam je omezen na segmenty.
- Vytvářejte nebo aktualizujte vlastní cílovou skupinu pouze typu Facebook *seznam zákazníků*.
- Export segmentů s celkem 10 milionem profilů může trvat až 90 minut.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Nastavení propojení se správcem reklam Facebook

Než uživatelé mohou vytvořit export, musí správce nakonfigurovat propojení ke službě a umožnit přispěvatelům propojení použít.

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat propojení** a zvolte **Facebook Správce reklam** pro konfiguraci propojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude **Správci**. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Ověření pomocí Facebook reklam: 

   1. Vyberte **Pokračovat s Facebook** pro příhlášení ke svému reklamnímu účtu Facebook.

   1. Povolte oprávnění **ads_management** po ověření pomocí Facebooku.

   1. Vyberte **Reklmaní účet Facebook**, se kterým chcete pracovat.

   1. Vyberte **Existující vlastní cílová skupina** z rozevíracího seznamu nebo vytvořte **Nová vlastní cílová skupina**. Další informace viz [**Cílové skupiny ve Správci reklam Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Vlastní cílové skupiny můžete vytvářet nebo aktualizovat pouze na Facebooku typu *seznam zákazníků* s tímto exportem. V některých případech se v rozevíracím seznamu zobrazí vlastní cílová skupina různých typů. Výběr jiného typu než *seznam zákazníků* bude mít za následek selhání exportu. 

1. Zkontrolujte část **Ochrana osobních údajů a dodržování předpisů** a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**. 

1. V poli **Propojení pro export** zvolte propojení v části **Správce reklam Facebook**. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Ve **Vyberte pole identifikátoru klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon** pro odeslání do Správce reklam Facebook. 

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**.

1. Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.
   > [TIP] Nejlepší šance na shodu nastanou, pokud vyberte **E-mail** jako identifikátor klíče. Přidání dalších identifikátorů může zlepšit shodu.

1. Vyberte **Přidat atribut** k mapování více atributů pro odeslání do Správce reklam Facebook. Atributy Správce reklam Facebook mapují následující uživatelsky přehledná jména: **FN** = **křestní jméno**, **LN** = **příjmení**, **FI** = **Počáteční písmeno**, **PHONE** = **Telefon**, **GEN** = **pohlaví**, **DOB** = **Datum narození**, **ST** = **Stát**, **CT** = **Město**, **ZIP** = **PSČ**, **COUNTRY** = **Země / Region**

1. Vyberte segmenty, které chcete exportovat.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když pro Dynamics 365 Customer Insights povolíte přenos dat do služby Facebook Ads Manager, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Facebook Ads splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
