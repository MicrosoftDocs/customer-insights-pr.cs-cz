---
title: Integrace webových dat z přehledů o zapojení zákazníků do přehledů cílové skupiny
description: Přeneste webové informace o zákaznících z přehledů o zapojení zákazníků do přehledů cílové skupiny.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597457"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrace webových dat z přehledů o zapojení zákazníků do přehledů cílové skupiny

Zákazníci často provádějí své každodenní transakce online pomocí webových stránek. Funkce přehledů o zapojení zákazníků v Dynamics 365 Customer Insights je užitečné řešení pro integraci webových dat jako zdroje. Kromě transakčních a demografických údajů nebo údajů o chování vidíme aktivity na webu ve sjednocených profilech zákazníků. Tento profil můžeme použít k získání dalších přehledů, jako jsou segmenty, míry nebo predikce, pro aktivaci cílové skupiny.

Tento článek popisuje kroky k přenesení dat o aktivitách vašich zákazníků na webu z přehledů o zapojení zákazníků do vašeho stávajícího prostředí s přehledy cílové skupiny.

V tomto příkladu předpokládejme prostředí, které obsahuje sjednocené profily zákazníků. Profily byly sjednoceny se zdroji z průzkumů, maloobchodního prodeje a systému jízdenek. Ukazuje také související aktivity zákazníků. 

Nyní chceme vědět, zda zákazník navštíví naše webové služby a porozumí jejich aktivitám. Mezi aktivity patří například navštívené webové stránky nebo zobrazené stránky produktů z odkazu přijatého v e-mailu.

## <a name="prerequisites"></a>Požadavky

Chcete-li integrovat data z přehledů o zapojení zákazníků, je třeba splnit několik předpokladů: 

- Integrujte sadu SDK přehledů o zapojení zákazníků s vaším webem. Další informace získáte v tématu [Začínáme s webovou sadou SDK](../engagement-insights/instrument-website.md).
- Export webových událostí z přehledů o zapojení zákazníků vyžaduje přístup k účtu úložiště ADLS Gen 2, který se použije k ingestaci dat webových událostí do přehledů cílové skupiny. Další informace popisuje článek [Export událostí](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurace upřesněných událostí v přehledech o zapojení zákazníků

Poté, co správce vybavil web sadou SDK přehledů o zapojení zákazníků, *základní události* se shromažďují, když si uživatel prohlíží webovou stránku nebo někde klikne. Základní události obvykle obsahují řadu podrobností. V závislosti na vašem případu použití potřebujete pouze podmnožinu dat v základní události. Přehledy o zapojení zákazníků vám umožní vytvářet *upřesněné události* které obsahují pouze vlastnosti základní události, kterou vyberete.     

Další informace viz [Vytváření a úpravy upřesněných událostí](../engagement-insights/refined-events.md).

Důležité informace při vytváření upřesněných událostí: 

- Zadejte srozumitelný název upřesněné události. Použije se jako název aktivity v přehledech cílové skupiny.
- Vyberte alespoň následující vlastnosti k vytvoření aktivity ve přehledech cílové skupiny: 
    - Signal.Action.Name – označuje podrobnosti aktivity
    - Signal.User.Id – slouží k mapování na ID zákazníka
    - Signal.View.Uri – používá se jako webová adresa pro základ segmentů nebo měr
    - Signal.Export.Id – slouží jako primární klíč pro události <!-- system generated, do we need to list?-->
    - Signal.Timestamp – určuje datum a čas aktivity

Výběrem filtrů zobrazte jen ty události a stránky, které jsou důležité pro vaše použití. V tomto příkladu použijeme název akce „E-mailová propagace“.

## <a name="export-the-refined-web-events"></a>Export upřesněných webových událostí 

Po definování upřesněné události je třeba nakonfigurovat export dat události do úložiště Azure Data Lake Storage, které lze nastavit jako zdroj dat pro ingestaci v přehledech cílové skupiny. Export probíhá neustále, jak události proudí z vlastnosti webu.

Další informace popisuje článek [Export událostí](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingestace data událostí do přehledů cílové skupiny

Nyní, když jste definovali upřesněnou událost a nakonfigurovali její export, přejdeme k ingestaci dat do přehledů cílové skupiny. Musíte vytvořit nový zdroj dat založený na složce Common Data Model. Zadejte podrobnosti účtu úložiště, do kterého exportujete události. V souboru *default.cdm.json* vyberte upřesněnou událost, kterou chcete ingestovat a v přehledech cílové skupiny vytvořte entitu.

Další informace viz [Připojení ke složce Common Data Model pomocí účtu Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Propojení upřesněných dat událostí jako aktivity profilu zákazníka

Po dokončení ingestace entity můžete nakonfigurovat aktivitu pro profil zákazníka.

Další informace najdete v tématu [Aktivity zákazníka](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Stránka aktivit s rozbaleným podoknem Úpravy aktivity a vyplněnými poli.":::

Nakonfigurujte novou aktivitu pomocí následujícího mapování: 

- **Primární klíč:** Signal.Export.Id, jedinečné ID, které je k dispozici pro každý záznam události v přehledech o zapojení zákazníků. Tato vlastnost je generována automaticky.

- **Časové razítko:** Signal.Timestamp ve vlastnosti události.

- **Událost:** Signal.Name, název události, kterou chcete sledovat.

- **Webová adresa:** Signal.View.Uri s odkazem na URI stránky, která událost vytvořila.

- **Podrobnosti:** Signal.Action.Name představuje informace, které mají být přidruženy k události. Vybraná vlastnost v tomto případě označuje, že událost je pro e-mailovou propagaci.

- **Typ aktivity:** V tomto příkladu zvolíme typ existující aktivity WebLog. Tento výběr představuje užitečnou možnost filtru pro spuštění predikce modelů nebo vytváření segmentů založených na tomto typu aktivity.

- **Nastavení vztahu:** Toto důležité nastavení svazuje aktivitu se stávajícími profily zákazníků. **Signal.User.Id** je identifikátor nakonfigurovaný v sadě SDK, který je shromažďován a který je navázán na ID uživatele v jiných zdrojích dat, které jsou nakonfigurovány v přehledech cílové skupiny. V tomto příkladu nakonfigurujeme vztah mezi Signal.User.Id a RetailCustomers:CustomerRetailId, což je primární klíč, který byl definován v kroku mapy procesu sjednocení dat.


Po zpracování aktivit můžete zkontrolovat záznamy zákazníků a otevřít zákaznickou kartu, abyste viděli aktivity z přehledů o zapojení zákazníků na časové ose. 

> [!TIP]
> Chcete-li najít ID zákazníka, který má aktivitu v přehledu o zapojení zákazníků, přejděte na **Entity** a zobrazte náhled dat pro entitu UnifiedActivity. ActivityTypeDisplay = WebLog obsahuje aktivitu z přehledu o zapojení zákazníků nakonfigurovanou ve výše uvedeném příkladu. Zkopírujte ID zákazníka pro jeden z těchto záznamů a pro toto ID na stránce **Zákazníci**.

## <a name="next-steps"></a>Další kroky

Nyní můžete vytvořit [segmenty](segments.md), [míry](measures.md) a [predikce](predictions.md), abyste mohli vytvořit přehledné připojení ke svým zákazníkům.


[!INCLUDE[footer-include](../includes/footer-banner.md)]