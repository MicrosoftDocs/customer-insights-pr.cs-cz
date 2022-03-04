---
title: Export dat Customer Insights do služby Marketo
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ec286bb6a90fb4d18e89caf9166aa659b29d668e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231971"
---
# <a name="export-segments-to-marketo-preview"></a>Export segmentů do Marketo (náhled)

Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.

## <a name="prerequisites-for-connection"></a>Předpoklady pro připojení

-   Máte [účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.
-   Služba Marketo obsahuje stávající seznamy a odpovídající ID. Další informace naleznete v [seznamech Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion zákaznických profilů na export do Marketo.
- Export do služby Marketo je omezen na segmenty.
- Export segmentů s celkem 1 miliony zákaznických profilů může trvat až 3 hodiny. 
- Počet zákaznických profilů, které můžete exportovat do Marketo, závisí na vaší smlouvě s Marketo a je jí omezen.

## <a name="set-up-connection-to-marketo"></a>Nastavení propojení s aplikací Marketo

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Marketo** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte své **[ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**. Koncový bod názvu hostitele REST je pouze název hostitele, bez `https://`. Příklad: `xyz-abc-123.mktorest.com`. 

1. Volbou **Souhlasím** potvrdíte **Ochranu osobních údajů a dodržování předpisů** a volbou **Připojit** inicializujete připojení ke službě Marketo.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Propojení pro export** vyberte propojení v části Marketo. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zadejte **[ID seznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID seznamu je čistě číselná hodnota. Například pokud je vaše ID seznamu Marketo ST12345A7, odstraňte znak před a za číslicemi a zadejte `12345`. 

1. V části **Párování dat** v poli **E-mail** vyberte pole představující e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **křestní jméno**, **příjmení**, **město**, **stát** a **zemi/region** pro vytvoření více přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. Do služby Marketo můžete exportovat celkem až 1 milion zákaznických profilů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). Ve službě Marketo nyní najdete své segmenty v části [Seznamy Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Marketo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Marketo splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
