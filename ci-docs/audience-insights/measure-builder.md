---
title: Vytvořte nové míry pomocí tvůrce míry
description: Vytvářejte míry od nuly a analyzujte klíčové metriky svého podnikání.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359895"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Pomocí nástroje pro tvorbu míry vytvořte míry od začátku

Tento článek vysvětluje, jak vytvořit novou [míru](measures.md) od nuly. Tvůrce míry vám umožňuje definovat výpočty pomocí matematických operátorů, agregačních funkcí a filtrů. Můžete vytvořit míru s atributy z entit, které se vztahují k sjednocené entitě *Zákazník*. 

Vytváření měr v prostředí B2C a B2B funguje stejným způsobem. Nicméně, pokud vaše B2B prostředí [používá účty s hierarchií](relationships.md#set-up-account-hierarchies), můžete se rozhodnout agregovat míru napříč souvisejícími podúčty.

Míru můžete také rychle vytvořit výběrem ze sady běžně používaných a předdefinovaných měr. Více informací naleznete v části [Použití šablony pro vytvoření míry](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

Můžete vytvářet míry na úrovni jednotlivých zákazníků (atribut zákazníka, míra zákaznika) nebo na úrovni podniku/organizace (obchodní míra). Atribut zákazníka a míra zákazníka jsou dva typy, které vám umožňují sledovat výkon podle zákazníka. Například celková útrata každého zákazníka. Obchodní míry vám umožňují sledovat výkon jednotlivých podniků. Například celkový příjem společnosti.

- Atribut zákazníka: Vygeneruje výstup jako nový atribut, který se uloží jako nový sloupec v pojmenované entitě generované systémem *Míra zákazníka*. Při aktualizaci atributu zákazníka se všechny ostatní atributy zákazníka v entitě *Míra zákazníka* aktualizují současně. Kromě toho jsou atributy zákazníka zobrazeny na kartě profilu zákazníka. Po spuštění nebo uložení atributu zákazníka jej nelze změnit na míru zákazníka.

- Míra zákazníka: Generuje výstup jako vlastní entitu a po spuštění nebo uložení ji nelze změnit na atribut zákazníka. Míry zákazníka se nezobrazují na kartě profilu zákazníka.

- Obchodní míra: Generuje výstup jako svou vlastní entitu a zobrazuje se na domovské stránce vašeho prostředí Customer Insights.

1. Přejděte na **Míry**.

1. Vyberte **Nový** a zvolte **Vytvořit vlastní**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prázdná konfigurační obrazovka pro míru B2C.":::

1. Vyberte **Upravit jméno** a zadejte **Název** míry. 

1. V oblasti konfigurace vyberte funkci agregace z rozevírací nabídky **Vybrat funkci**. Agregační funkce zahrnují: 
   - **Sum**
   - **Průměr**
   - **Počet**
   - **Počet jedinečných**
   - **Max**
   - **Min.**
   - **První**: přebírá první hodnotu datového záznamu
   - **Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu
   - **ArgMax**: vyhledá datový záznam poskytující maximální hodnotu z cílové funkce
   - **ArgMin**: vyhledá datový záznam poskytující minimální hodnotu z cílové funkce

1. Volbou **Přidat atribut** vyberte data, která potřebujete k vytvoření této míry.
   
   1. Vyberte kartu **Atributy**. 
   1. Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit. 
   1. Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry. Nelze vybrat více atributů najednou.
   1. Atribut dat ze stávající míry můžete také vybrat výběrem karty **Míry** nebo můžete vyhledat název entity nebo míry. 
   1. Volbou **Přidat** přidáte vybraný atribut do míry.

1. Chcete-li vytvořit složitější míry, můžete přidat další atributy nebo použít matematické operátory ve své funkci míry.

1. Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti. Při použití filtrů se k výpočtu míry použijí pouze záznamy, které odpovídají filtrům.
  
   1. V části **Přidat atribut** podokna **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.
   1. Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.
   1. Volbou **Použít** přidáte filtry do míry.

1. Vyberte **Dimenze** a zvolte více polí, která se přidají jako sloupce do entity výstupu míry.
 
   1. Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr. Například město nebo pohlaví. Ve výchozím nastavení je vybrána dimenze *CustomerID* k vytvoření *měr na úrovni zákazníka*. Pokud chcete vytvořit *míry na úrovni podniku*, můžete odebrat výchozí míru.
   1. Volbou **Hotovo** přidáte dimenze do míry.

1. Pokud jsou ve vašich datech hodnoty, které je třeba nahradit celým číslem, vyberte **Pravidla**. Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla. Například nahraďte text *nula* číslem *0*.

1. Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, musíte zvolit jednu z identifikovaných [cest vztahů mezi entitami](relationships.md). Výsledné míry se mohou lišit v závislosti na vybrané cestě. 
   
   1. Vyberte **Vztahová cesta** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry. Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.
   1. Volbou **Hotovo** použijete svůj výběr. 

1. Chcete-li přidat další výpočty pro míru, vyberte **Nový výpočet**. Pro nové výpočty můžete použít pouze entity na stejné cestě entity. Další výpočtu se v entitě výstupu míry zobrazí jako nové sloupce.

1. Vyberte **...** na výpočtu, abyste **duplikovali**, **přejmenovali** nebo **odstranili** výpočet z míry.

1. V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí. Náhled dynamicky reaguje na změny v konfiguraci.

1. Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru. Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později.

1. Jděte na **Míry** pro zobrazení nově vytvořené míry v seznamu.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)


Můžete vytvářet míry na úrovni jednotlivých obchodích vztahů (míra zákaznika) nebo na úrovni všech obchodních vztahů (obchodní míra). 

- Míra zákazíka: Generuje výstup jako svou vlastní entitu. Míry zákazníka se nezobrazují na kartě profilu zákazníka.

- Obchodní míra: Generuje výstup jako svou vlastní entitu a zobrazuje se na domovské stránce vašeho prostředí Customer Insights.

1. Přejděte na **Míry**.

1. Vyberte **Nové**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prázdná konfigurační obrazovka pro míru B2B.":::

1. Vyberte **Upravit jméno** a zadejte **Název** míry. 

1. V oblasti konfigurace vyberte funkci agregace z rozevírací nabídky **Vybrat funkci**. Agregační funkce zahrnují: 
   - **Sum**
   - **Průměr**
   - **Počet**
   - **Počet jedinečných**
   - **Max**
   - **Min.**
   - **První**: přebírá první hodnotu datového záznamu
   - **Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu

1. Volbou **Přidat atribut** vyberte data, která potřebujete k vytvoření této míry.
   
   1. Vyberte kartu **Atributy**. 
   1. Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit. 
   1. Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry. Nelze vybrat více atributů najednou.
   1. Atribut dat ze stávající míry můžete také vybrat výběrem karty **Míry** nebo můžete vyhledat název entity nebo míry. 
   1. Volbou **Přidat** přidáte vybraný atribut do míry.

1. Chcete-li vytvořit složitější míry, můžete přidat další atributy nebo použít matematické operátory ve své funkci míry.

1. Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti. Při použití filtrů se k výpočtu míry použijí pouze záznamy, které odpovídají filtrům.
  
   1. V části **Přidat atribut** podokna **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.
   1. Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.
   1. Volbou **Použít** přidáte filtry do míry.

1. Vyberte **Dimenze** a zvolte více polí, která se přidají jako sloupce do entity výstupu míry.
 
   1. Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr. Například město nebo pohlaví. Ve výchozím nastavení je vybrána dimenze *CustomerID* k vytvoření *měr na úrovni zákazníka*. Pokud chcete vytvořit *míry na úrovni podniku*, můžete odebrat výchozí míru.
   1. Volbou **Hotovo** přidáte dimenze do míry.

1. Pokud jsou ve vašich datech hodnoty, které je třeba nahradit celým číslem, vyberte **Pravidla**. Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla. Například nahraďte text *nula* číslem *0*.

1. Můžete použít přepínač **Sloučit podúčty** pokud [používáte účty s hierarchiemi](relationships.md#set-up-account-hierarchies).
   - Pokud je nastavena na **Vypnuto**, míra se vypočítá pro každý účet. Každý účet má svůj vlastní výsledek.
   - Pokud je nastavena na **Na**, vyberte **Upravit** ke zvolení hierarchie účtu podle přijatých hierarchií. Míra přinese pouze jeden výsledek, protože je agregována s podúčty.

1. Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, musíte zvolit jednu z identifikovaných [cest vztahů mezi entitami](relationships.md). Výsledné míry se mohou lišit v závislosti na vybrané cestě. 
   
   1. Vyberte **Vztahová cesta** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry. Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.
   1. Volbou **Hotovo** použijete svůj výběr. 

1. Vyberte **...** na výpočtu, abyste **duplikovali**, **přejmenovali** nebo **odstranili** výpočet z míry.

1. V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí. Náhled dynamicky reaguje na změny v konfiguraci.

1. Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru. Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později.

1. Jděte na **Míry** pro zobrazení nově vytvořené míry v seznamu.

---