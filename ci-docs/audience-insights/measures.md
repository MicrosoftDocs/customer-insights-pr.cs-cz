---
title: Vytváření a správa měr
description: Definujte míry, které budou analyzovat a reflektovat výkon vašeho podnikání.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304781"
---
# <a name="define-and-manage-measures"></a>Definujte a spravujte opatření

Míry vám pomohou lépe porozumět chování zákazníků a výkonnosti podniku. Zaměřují se na relevantní hodnoty ze [sjednocených profilů](data-unification.md). Například firma chce vidět *celkové výdaje na zákazníka*, aby rozuměla historii nebo míře nákupu jednotlivého zákazníka nebo změřila *celkový prodej společnosti*, aby porozuměla agregovaným výnosům v celém podniku.  

Míry jsou vytvářeny pomocí nástroje pro tvorbu měr, což je platforma pro dotazování dat s různými operátory a možnostmi jednoduchého mapování. Umožňuje filtrovat data, seskupovat výsledky, detekovat [cesty vztahů mezi entitami](relationships.md) a zobrazovat náhledy výstupu.

Pomocí nástroje pro tvorbu měr můžete plánovat obchodní aktivity dotazováním zákaznických dat a extrahováním přehledů. Například vytvoření míry *celkové výdaje na zákazníka* a *celková návratnost na zákazníka* pomáhá identifikovat skupinu zákazníků s vysokými výdaji, ale s vysokou návratností. [Vytvořením segmentu](segments.md) můžete řídit nejvhodnější akce, které se mají následně provést. 

## <a name="build-your-own-measure-from-scratch"></a>Vytvoření vlastní míry od začátku

Tato sekce vás provede vytvořením nové míry od nuly. Můžete vytvořit míru s datovými atributy z datových entit, které mají nastavený vztah pro připojení k entitě zákazníka. 

1. V přehledech cílové skupiny přejděte na **Míry**.

1. Vyberte **Nový** a zvolte **Vytvořit vlastní**.

1. Vyberte **Upravit jméno** a zadejte **Název** míry. 
   > [!NOTE]
   > Pokud má vaše nová konfigurace míry pouze dvě pole, například CustomerID a jeden výpočet, výstup bude přidán jako nový sloupec do entity generované systémem s názvem Customer_Measure. Hodnotu míry uvidíte ve sjednoceném profilu zákazníka. Další míry vygenerují vlastní entity.

1. V oblasti konfigurace vyberte funkci agregace z rozevírací nabídky **Vybrat funkci**. Agregační funkce zahrnují: 
   - **Sum**
   - **Průměr**
   - **Počet**
   - **Počet jedinečných**
   - **Max**
   - **Min.**
   - **První**: přebírá první hodnotu datového záznamu
   - **Poslední**: převezme poslední hodnotu, která byla přidána do datového záznamu

   :::image type="content" source="media/measure-operators.png" alt-text="Operátory pro výpočty měr.":::

1. Volbou **Přidat atribut** vyberte data, která potřebujete k vytvoření této míry.
   
   1. Vyberte kartu **Atributy**. 
   1. Datová entita: Vyberte entitu, která obsahuje atribut, který chcete měřit. 
   1. Atribut dat: Vyberte atribut, který chcete použít ve funkci agregace pro výpočet míry. Nelze vybrat více atributů najednou.
   1. Atribut dat ze stávající míry můžete také vybrat výběrem karty **Míry**. Nebo můžete vyhledat název entity nebo míry. 
   1. Volbou **Přidat** přidáte vybraný atribut do míry.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vyberte atribut, který se má použít ve výpočtech.":::

1. Chcete-li vytvořit složitější míry, můžete přidat další atributy nebo použít matematické operátory ve své funkci míry.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Vytvořte komplexní míru s matematickými operátory.":::

1. Chcete-li přidat filtry, vyberte možnost **Filtr** v konfigurační oblasti. 
  
   1. V části **Přidat atribut** podokna **Filtry** vyberte atribut, který chcete použít k vytvoření filtrů.
   1. Nastavte operátory filtru tak, aby definovaly filtr pro každý vybraný atribut.
   1. Volbou **Použít** přidáte filtry do míry.

1. Chcete-li přidat dimenze, vyberte možnost **Dimenze** v konfigurační oblasti. Dimenze se v entitě výstupu míry zobrazí jako sloupce.
 
   1. Volbou **Upravit dimenze** přidáte atributy dat, podle kterých chcete seskupit hodnoty měr. Například město nebo pohlaví. Ve výchozím nastavení je vybrána dimenze *CustomerID* k vytvoření *měr na úrovni zákazníka*. Pokud chcete vytvořit *míry na úrovni podniku*, můžete odebrat výchozí míru.
   1. Volbou **Hotovo** přidáte dimenze do míry.

1. Pokud jsou ve vašich datech hodnoty, které potřebujete nahradit celým číslem, nahraďte například hodnotu *null* hodnotou *0*, vyberte **Pravidla**. Nakonfigurujte pravidlo a ujistěte se, že jako náhradu zvolíte pouze celá čísla.

1. Pokud mezi datovou entitou, kterou jste mapovali, a entitou *Zákazník* existuje více cest, musíte zvolit jednu z identifikovaných [cest vztahů mezi entitami](relationships.md). Výsledné míry se mohou lišit v závislosti na vybrané cestě. 
   
   1. Vyberte **Předvolby dat** a vyberte cestu entity, která by měla být použita k identifikaci vaší míry. Pokud existuje pouze jedna cesta k entitě *Zákazník*, tento ovládací prvek se nezobrazí.
   1. Volbou **Hotovo** použijete svůj výběr. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Umožňuje vybrat cestu entitu pro tuto míru.":::

1. Chcete-li přidat další výpočty pro míru, vyberte **Nový výpočet**. Pro nové výpočty můžete použít pouze entity na stejné cestě entity. Další výpočtu se v entitě výstupu míry zobrazí jako nové sloupce.

1. Vyberte **...** na výpočtu, abyste **duplikovali**, **přejmenovali** nebo **odstranili** výpočet z míry.

1. V oblasti **Náhled** uvidíte schéma dat pro entitu výstupu míry, včetně filtrů a dimenzí. Náhled dynamicky reaguje na změny v konfiguraci.

1. Volbou **Spustit** vypočtete výsledky pro konfigurovanou míru. Vyberte **Uložit a zavřít**, chcete-li zachovat aktuální konfiguraci a spustit míru později.

1. Jděte na **Míry** pro zobrazení nově vytvořené míry v seznamu.

## <a name="use-a-template-to-build-a-measure"></a>Vytvoření míry pomocí šablony

K jejich vytváření můžete použít předdefinované šablony běžně používaných měr. Podrobné popisy šablon a průvodce vám pomohou s efektivním vytvořením míry. Šablony vycházejí z mapovaných dat entity *Sjednocená aktivita*. Ujistěte se tedy, že jste nakonfigurovali [aktivity zákazníků](activities.md) před vytvořením míry ze šablony.

Dostupné šablony měr: 
- Průměrná hodnota transakce
- Celková hodnota transakce
- Průměrné denní výnosy
- Průměrné roční výnosy
- Počet transakcí
- Získané věrnostní body
- Uplatněné věrnostní body
- Zůstatek věrnostních bodů
- Životnost aktivního zákazníka
- Doba trvání věrnostního členství
- Čas od posledního nákupu

Následující postup popisuje kroky k vytvoření nové míry pomocí šablony.

1. V přehledech cílové skupiny přejděte na **Míry**.

1. Vyberte **Nová** a vyberte **Zvolit šablonu**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Screenshot rozevírací nabídky při vytváření nové míry se zvýrazněním šablony.":::

1. Najděte šablonu, která vyhovuje vašim potřebám, a vyberte **Zvolit šablonu**.

1. Zkontrolujte požadovaná data a vyberte **Začít**, pokud máte všechna data na místě.

1. V podokně **Upravit jméno** nastavte název míry a výstupní entitu. 

1. Vyberte **Hotovo**.

1. V části **Nastavit časové období** definujte časový rámec dat, která se mají použít. Vyberte, zda má nová míra pokrývat celou datovou sadu, výběrem **Kdykoli**, nebo zda se má zaměřovat na **Specifické časové období**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Screenshot zobrazující část časového období při konfiguraci míry ze šablony.":::

1. V další části vyberte **Přidat data** pro výběr aktivit a namapování příslušných dat z entity *Sjednocená aktivita*.

    1. Krok 1 ze 2: V části **Typ aktivity** vyberte typ entity, kterou chcete použít. Pro **Aktivity** vyberte entity, které chcete mapovat.
    1. Krok 2 ze 2: Vyberte atribut z entity *Sjednocená aktivita* pro komponentu požadovanou vzorcem. Například pro průměrnou hodnotu transakce je to atribut představující hodnotu transakce. Pro **Časové razítko aktivity** vyberte atribut z entity Unified Activity, která představuje datum a čas aktivity.
   
1. Jakmile je mapování dat úspěšné, můžete vidět stav jako **Kompletní** a název mapovaných aktivit a atributů.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Screenshot z dokončené konfigurace šablony míry.":::

1. Nyní můžete vybrat **Spustit** k výpočtu výsledků míry. Chcete-li to upřesnit později, vyberte **Uložit koncept**.

## <a name="manage-your-measures"></a>Správa opatření

Seznam měr naleznete na stránce **Míry**.

Najdete informace o typu, tvůrci, datu vytvoření, statusu a stavu míry. Když vyberete míru ze seznamu, můžete zobrazit náhled výstupu a stáhnout soubor CSV.

Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.

> [!div class="mx-imgBorder"]
> ![Akce ke správě jednotlivých opatření.](media/measure-actions.png "Akce ke správě jednotlivých opatření.")

Vyberte míru ze seznamu a použijte některou z následujících voleb:

- Chcete-li zobrazit podrobnosti, vyberte název míry.
- **Upravte** konfiguraci míry.
- **Aktualizujte** míru na základě nejnovějších údajů.
- **Přejmenujte** míru.
- **Odstraňte** míry.
- **Aktivujte** nebo **deaktivujte**. Neaktivní míry se během [plánované aktualizace](system.md#schedule-tab) neaktualizují.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="next-step"></a>Další krok

K vytváření můžete použít stávající míry [zákaznický segment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
