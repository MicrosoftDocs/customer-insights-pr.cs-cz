---
title: Vytvoření měr pomocí tvůrce měr
description: Vytvářejte míry od nuly a analyzujte klíčové metriky svého podnikání.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170841"
---
# <a name="create-measures-with-measure-builder"></a>Vytvoření měr pomocí tvůrce měr

Tvůrce měr umožňuje definovat výpočty pomocí matematických operátorů, agregačních funkcí a filtrů. Míry definujete pomocí atributů z entit, které se vztahují k sjednocené entitě *Zákazník*.

Vytváření měr v prostředí B2C a B2B funguje stejným způsobem. Nicméně, pokud vaše B2B prostředí [používá účty s hierarchií](relationships.md#set-up-account-hierarchies), zvolte, zda agregovat míru napříč souvisejícími podúčty.

# <a name="individual-consumers-b-to-c"></a>[Jednotliví spotřebitelé (B2C)](#tab/b2c)

Vytvořte míry na úrovni jednotlivých zákazníků (atribut zákazníka, míra zákaznika) nebo na úrovni podniku/organizace (obchodní míra). Atribut zákazníka a míra zákazníka vám umožňují sledovat výkon podle zákazníka. Například celková útrata každého zákazníka. Obchodní míry sledují výkon jednotlivých podniků. Například celkový příjem společnosti.

- Atribut zákazníka: Vygeneruje výstup jako nový atribut, který se uloží jako nový sloupec v pojmenované entitě generované systémem *Míra zákazníka*. Při aktualizaci atributu zákazníka se všechny ostatní atributy zákazníka v entitě *Míra zákazníka* aktualizují současně. Kromě toho jsou atributy zákazníka zobrazeny na kartě profilu zákazníka. Po spuštění nebo uložení atributu zákazníka jej nelze změnit na míru zákazníka.

- Míra zákazníka: Generuje výstup jako vlastní entitu a po spuštění nebo uložení ji nelze změnit na atribut zákazníka. Míry zákazníka se nezobrazují na kartě profilu zákazníka.

- Obchodní míra: Generuje výstup jako svou vlastní entitu a zobrazuje se na domovské stránce vašeho prostředí Customer Insights.

1. Přejděte na **Míry**.

1. Vyberte **Nový** > **Vytvořit svůj vlastní**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Prázdná konfigurační obrazovka pro míru B2C." lightbox="media/measure-b2c.png":::

1. Vedle míry bez názvu vyberte možnost **Upravit podrobnosti**. Zadejte název míry. Volitelně přidejte [značky](work-with-tags-columns.md#manage-tags) do nové míry.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogové okno Úprava podrobností":::

1. Vyberte **Hotovo**.

1. Chcete-li sledovat výkon na podnikové úrovni, přepněte **Typ míry** na **Podniková úroveň**. Ve výchozím nastavení je vybrána **Zákaznická úroveň**. **Zákaznická úroveň** automaticky přidá atribut *CustomerId* do dimenzí, zatímco **Podniková úroveň** jej automaticky odstraní.

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

1. Volbou **Přidat atribut** vyberte data pro vytvoření této míry.

   1. Vyberte kartu **Atributy**.
   1. Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit.
   1. Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry. Nelze vybrat více atributů najednou.
   1. Volitelně zvolte atribut dat ze stávající míry výběrem karty **Míry** nebo vyhledejte název entity nebo míry.
   1. Vyberte **Přidat**.

1. Chcete-li vytvořit složitější míry, přidejte další atributy nebo použít matematické operátory ve své funkci míry.

1. Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti. Při použití filtrů se k výpočtu míry použijí pouze záznamy, které odpovídají filtrům.
  
   1. V části **Přidat atribut** podokna **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.
   1. Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.
   1. Vyberte **Použít**.

1. Vyberte **Dimenze** a zvolte více polí, která se přidají jako sloupce do entity výstupu míry.

   1. Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr. Například město nebo pohlaví.
      > [!TIP]
      > Pokud jste jako **Typ měření** vybrali **Zákaznická úroveň**, atribut *CustomerId* je již přidán. Pokud atribut odeberete, **Typ měření** se přepne na **Podniková úroveň**.
   1. Vyberte **Hotovo**.

1. Pokud jsou ve vašich datech hodnoty, které je třeba nahradit celým číslem, vyberte **Pravidla**. Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla. Například nahraďte text *nula* číslem *0*.

1. Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, zvolte jednu z identifikovaných [cest vztahů mezi entitami](relationships.md). Výsledné míry se mohou lišit v závislosti na vybrané cestě.

   1. Vyberte **Vztahová cesta** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry. Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.
   1. Vyberte **Hotovo**.

1. Chcete-li přidat další výpočty pro míru, vyberte **Nový výpočet**. Pro nové výpočty použijte pouze entity ve stejné cestě entity. Další výpočtu se v entitě výstupu míry zobrazí jako nové sloupce. Volitelně volbou **Upravit název** vytvořte název pro výpočet.

1. Vyberte vertikální tři tečky (&vellip;) při výpočtu pro **Duplikování** nebo **Odebrání** výpočtu z míry.

1. V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí. Náhled dynamicky reaguje na změny v konfiguraci.

1. Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru. Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později. Zobrazí se stránka **Míry**.

# <a name="business-accounts-b-to-b"></a>[Obchodní účty (B2B)](#tab/b2b)

Vytvořte míry na úrovni jednotlivých obchodních vztahů (míra zákazníka) nebo na úrovni všech obchodních vztahů (obchodní míra).

- Míra zákazíka: Generuje výstup jako svou vlastní entitu. Míry zákazníka se nezobrazují na kartě profilu zákazníka.

- Obchodní míra: Generuje výstup jako svou vlastní entitu a zobrazuje se na domovské stránce vašeho prostředí Customer Insights.

1. Přejděte na **Míry**.

1. Vyberte **Nové**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Prázdná konfigurační obrazovka pro míru B2B.":::

1. Vedle míry bez názvu vyberte možnost **Upravit podrobnosti**. Zadejte název míry. Volitelně přidejte [značky](work-with-tags-columns.md#manage-tags) do nové míry. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogové okno Úprava podrobností":::

1. Vyberte **Hotovo**.

1. V oblasti konfigurace vyberte funkci agregace z rozevírací nabídky **Vybrat funkci**. Agregační funkce zahrnují:
   - **Sum**
   - **Průměr**
   - **Počet**
   - **Počet jedinečných**
   - **Max**
   - **Min.**
   - **První**: přebírá první hodnotu datového záznamu
   - **Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu

1. Volbou **Přidat atribut** vyberte data pro vytvoření této míry.

   1. Vyberte kartu **Atributy**.
   1. Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit.
   1. Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry. Nelze vybrat více atributů najednou.
   1. Volitelně zvolte atribut dat ze stávající míry výběrem karty **Míry** nebo vyhledejte název entity nebo míry.
   1. Volbou **Přidat** přidáte vybraný atribut do míry.

1. Chcete-li vytvořit složitější míry, přidejte další atributy nebo použít matematické operátory ve své funkci míry.

1. Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti. Při použití filtrů se k výpočtu míry použijí pouze záznamy, které odpovídají filtrům.
  
   1. V části **Přidat atribut** podokna **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.
   1. Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.
   1. Volbou **Použít** přidáte filtry do míry.

1. Vyberte **Dimenze** a zvolte více polí, která se přidají jako sloupce do entity výstupu míry.

   1. Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr. Například město nebo pohlaví.
      > [!TIP]
      > Atribut *CustomerId* je již přidán, což označuje, že se jedná o typu míry na úrovni zákazníka. Pokud atribut odeberete, typ míry se změní na podnikovou úroveň.
   1. Volbou **Hotovo** přidáte dimenze do míry.

1. Pokud jsou ve vašich datech hodnoty, které je třeba nahradit celým číslem, vyberte **Pravidla**. Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla. Například nahraďte text *nula* číslem *0*.

1. Pokud [použijete obchodní vztahy s hierarchiemi](relationships.md#set-up-account-hierarchies), zkontrolujte **Shrnutí dílčích obchodních vztahů**.
   - Pokud je nastavena na **Vypnuto**, míra se vypočítá pro každý účet. Každý obchodní vztah má svůj vlastní výsledek.
   - Pokud je nastavena na **Na**, vyberte **Upravit** ke zvolení hierarchie účtu podle přijatých hierarchií. Míra přinese pouze jeden výsledek, protože je agregována s dílčími obchodními vztahy.

1. Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, zvolte jednu z identifikovaných [cest vztahů mezi entitami](relationships.md). Výsledné míry se mohou lišit v závislosti na vybrané cestě.

   1. Vyberte **Vztahová cesta** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry. Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.
   1. Volbou **Hotovo** použijete svůj výběr.

1. Vyberte vertikální tři tečky (&vellip;) při výpočtu pro **Duplikování** nebo **Odebrání** výpočtu z míry.

1. V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí. Náhled dynamicky reaguje na změny v konfiguraci.

1. Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru. Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později. Zobrazí se stránka **Míry**.

---

## <a name="next-step"></a>Další krok

Pomocí existujících měr vytvoříte [segment zákazníka](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
