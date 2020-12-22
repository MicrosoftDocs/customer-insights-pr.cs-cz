---
title: Vytváření a úprava měr
description: Definujte opatření související se zákazníky pro analýzu a zohlednění výkonu určitých obchodních oblastí.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405394"
---
# <a name="define-and-manage-measures"></a>Definujte a spravujte opatření

**Opatření** představují klíčové ukazatele výkonnosti, které odrážejí výkonnost a zdraví konkrétních obchodních oblastí. Přehledy cílové skupiny poskytuje intuitivní prostředí pro vytváření různých typů měr pomocí nástroje pro vytváření dotazů, které nevyžaduje ruční kódování nebo ověřování měr. Obchodní opatření můžete sledovat na **Domovské stránce**, zobrazit opatření pro konkrétní zákazníky na **Kartě zákazníka** a použít opatření k definování segmentů zákazníků na stránce **Segmenty**.

## <a name="create-a-measure"></a>Vytvořit nové opatření

Tato část vás provede vytvořením opatření od začátku. Můžete vytvářet opatřen s daty z více zdrojů dat, které jsou propojeny prostřednictvím entity Zákazník. Použijí se některé [servisní limity](service-limits.md).

1. V přehledech cílové skupiny přejděte na **Míry**.

2. Vyberte **Nové opatření**.

3. Zvolte **Typ** opatření:

   - **Atribut záazníka**: Jedno pole na zákazníka, které odráží skóre, hodnotu nebo stav pro zákazníka. Atributy zákazníka jsou vytvořeny jako atributy v nové systémové entitě nazývané **Opatření zákazníka**.

   - **Opatření zákazníka**: Přehledy o chování zákazníků s rozdělením podle vybraných dimenzí. Pro každé opatření je generována nová entita, potenciálně s více záznamy na zákazníka.

   - **Obchodní opatření**: Sleduje výkonnost a zdraví podniku. Obchodní opatření mohou mít dva různé výstupy: číselný výstup, který se zobrazí na **Domovské stránce** nebo novou entitu, kterou najdete na stránce **Entity**.

4. Zadejte **Název** a volitelný **Zobrazovaný název** a pak vyberte **Další**.

5. V sekci **Entity** z rozevíracího seznamu vyberte první entitu. V tomto okamžiku byste se měli rozhodnout, zda jsou v rámci definice míry potřeba další entity.

   > [!div class="mx-imgBorder"]
   > ![Definice opatření](media/measure-definition.png "Definice míry")

   Chcete-li přidat další entity, vyberte **Přidat entitu** a vyberte entity, které chcete pro opatření použít.

   > [!NOTE]
   > Můžete vybrat entity, které mají vztah s počáteční entitou. Další informace o definování vztahů najdete v tématu [Vztahy](relationships.md).

6. Volitelně můžete nakonfigurovat proměnné. V části **Proměnné** vyberte **Nová proměnná**.

   Proměnné jsou výpočty, které jsou prováděny v každém z vybraných záznamů. Například sčítání prodejních míst (POS) a online prodeje pro každý záznam zákazníka.

7. Zadejte **Název** proměnné.

8. V oblasti **Výraz** zvolte pole, se kterým chcete začít výpočet.

9. Zadejte výraz do oblasti **Výraz** a vyberte další pole, která mají být zahrnuta do výpočtu.

   > [!NOTE]
   > V současné době jsou podporovány pouze aritmetické výrazy. Kromě toho není podporován variabilní výpočet pro entity z různých [cest entit](relationships.md).

10. Vyberte **Hotovo**.

11. V části **Definice opatření** definujete, jak jsou vybrané entity a vypočtené proměnné agregovány v nové entitě nebo atributu měření.

12. Vyberte **Nová dimenze**. Dimenzi si můžete představit jako funkci *seskupit dle*. Datový výstup entity nebo atributu Opatření bude seskupen podle všech definovaných dimenzí.

    > [!div class="mx-imgBorder"]
    > ![Zvolit agregační cyklus](media/measures-businessreport-measure-definition2.png "Zvolit agregační cyklus")

    Vyberte nebo zadejte následující informace jako součást definice dimenze:

    - **Entita**: Pokud definujete entitu Opatření, měla by obsahovat alespoň jeden atribut. Pokud definujete atribut Opatření, bude ve výchozím nastavení obsahovat pouze jeden atribut. Tento výběr je o výběru entity, která obsahuje tento atribut.
    - **Pole**: Zvolte konkrétní atribut, který má být zahrnut buď do entity Opatření, nebo atributu.
    - **Kbelík**: Zvolte, zda chcete agregovat data na denní, měsíční nebo roční bázi. Je to povinný výběr, pouze pokud jste vybrali atribut Typ data.
    - **Jako**: Definuje název nového pole.
    - **Zobrazované jméno**: Definuje zobrazované jméno pole.

    > [!NOTE]
    > Vaše obchodní opatření bude uloženo jako entita s jedním číslem a zobrazí se na **Domovské stránce**, pokud k opatření nepřidáte další dimenze. Po přidání dalších dimenzí se opatření *nezobrazí* na **Domovské stránce**.

13. Volitelně přidejte funkce agregace. Jakákoli agregace, kterou vytvoříte, má za následek novou hodnotu v rámci entity nebo atributu Opatření. Podporované agregační funkce jsou: **Min**, **Maxi**, **Průměr**, **Medián**, **Součet**, **Počet jedinečných**, **První** (bere první záznam hodnoty dimenze) a **Poslední** (bere poslední záznam přidaný na hodnotu dimenze).

14. Výběrem možnosti **Uložit** použijete změny na opatření.

## <a name="manage-your-measures"></a>Správa opatření

Po vytvoření alespoň jedné míry se na stránce **Míry** zobrazí seznam měr.

Najdete zde informace o typu opatření, autorovi, datu a čase vytvoření, datu a datu poslední úpravy, stavu (zda je opatření aktivní, neaktivní nebo neúspěšné) a o datu a čase poslední aktualizace. Když vyberete opatření ze seznamu, zobrazí se náhled jeho výstupu.

Chcete-li obnovit všechna vaše opatření současně, vyberte **Aktualizovat vše** bez výběru konkrétního opatření.

> [!div class="mx-imgBorder"]
> ![Akce ke správě jednotlivých opatření](media/measure-actions.png "Akce ke správě jednotlivých opatření")

Případně vyberte opatření ze seznamu a proveďte jednu z následujících akcí:

- Chcete-li zobrazit podrobnosti, vyberte název opatření.
- **Upravte** konfiguraci opatření.
- **Přejmenujte** opatření.
- **Odstraňte** opatření.
- Vyberte tři tečky (...) a poté **Obnovit** pro zahájení procesu aktualizace opatření.
- Vyberte tři tečky (...) a poté **Stáhnout**, chcete-li získat .CSV soubor opatření.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="next-step"></a>Další krok

Existující opatření můžete použít k vytvoření prvního segmentu zákazníků na stránce **Segmenty**. Další informace najdete v tématu [Segmenty](segments.md).
