---
title: Doplnění částečných dat pomocí predikcí
description: Pomocí predikcí můžete vyplnit neúplná zákaznická data.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 9634523f61e27a0ed183186a788ab0cef3c0491b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353995"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Doplňte svá dílčí data o predikce (zastaralé)

> [!IMPORTANT]
> Tato funkce bude **zastaralá** od **5. listopadu 2021**. Stávající implementace budou fungovat, dokud nebude funkce odstraněna, ale pomocí níže uvedených pokynů nebudete moci vytvářet nové integrace.

Předpovědi vám umožňují snadno vytvářet předpovídané hodnoty, které mohou zlepšit vaše porozumění zákazníkovi. Na stránce **Analytické nástroje** > **Predikce** můžete volbou **Moje predikce** zobrazit predikce, které jste nakonfigurovali v jiných částech přehledů cílové skupiny, a umožnit vám je dále přizpůsobovat.

> [!NOTE]
> Tuto funkci nemůžete použít, pokud vaše prostředí používá úložiště Azure Data Lake Gen 2.
>
> Funkce predikcí používá automatizované prostředky k vyhodnocování údajů a vytváření predikcí na základě těchto údajů, a proto má schopnost být použita jako metoda profilování, protože tento pojem je definován obecným nařízením o ochraně údajů („GDPR“). Použití této funkce zákazníkem ke zpracování dat může podléhat GDPR nebo jiným zákonům nebo předpisům. Zodpovídáte za to, že použití Dynamics 365 Customer Insights, včetně predikcí, je v souladu se všemi příslušnými zákony a předpisy, včetně zákonů týkajících se soukromí, osobních údajů, biometrických údajů, ochrany údajů a důvěrnosti komunikace.

## <a name="prerequisites"></a>Požadavky

Než bude vaše organizace moci používat funkci předpovědí, musí být splněny následující předpoklady:

1. Vaše organizace má instanci [nastavení v Microsoft Dataverse](/ai-builder/build-model#prerequisites) a je ve stejné organizaci jako Customer Insights.

2. Vaše prostředí přehledu cílové skupiny je připojeno k vaší instanci Dataverse.

Další informace naleznete v tématu [Vytvoření nového prostředí](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Vytvoření predikce v entitě Zákazník

1. V přehledech cílové skupiny přejděte na **Data** > **Entity**.

2. Vyberte entitu **Zákazník**.

3. V entitě **Zákazník: CustomerInsights** vyberte entitu na kartě **Pole**.

4. Vyhledejte název atributu, pro který chcete predikovat hodnoty, a vyberte ikonu **Přehled** ve sloupci **Souhrn**.
   > [!div class="mx-imgBorder"]
   > ![Ikona přehledu.](media/intelligence-overviewicon.png "Přehledová ikona")

5. Pokud pro váš atribut existuje vysoká míra chybějících hodnot, vyberte **Předpovědět chybějící hodnoty** a pokračujte tak ve své predikci.
   > [!div class="mx-imgBorder"]
   > ![Přehledový stav se zobrazeným tlačítkem predikce chybějících hodnot.](media/intelligence-overviewpredictmissingvalues.png "Přehledový stav se zobrazeným tlačítkem predikce chybějících hodnot")

6. Poskytněte **Zobrazované jméno** a **Název výstupní entity** pro výsledky predikce.

7. Předvyplněný seznam možností ukáže, kde můžete namapovat hodnoty na předpovídanou kategorii. V takovém případě budou vaše jediné možnosti kategorie 0 nebo 1, protože mapují na pravdivou / nepravdivou nebo binární povahu predikce. Ve sloupci Kategorie namapujte hodnoty polí, které chcete mít klasifikovány jako „0“ v konečné predikci, na „0“ ve sloupci Kategorie, a položky, které chcete v konečné predikci klasifikovat jako „1“, na „1“.
   > [!div class="mx-imgBorder"]
   > ![Příklad zobrazení mapovaných hodnot polí do kategorií.](media/intelligence-categorymapping.png "Příklad zobrazení mapovaných hodnot polí do kategorií")

8. Vyberte **Hotovo** a předpověď bude zpracována. Zpracování bude nějakou dobu trvat, v závislosti na velikosti a složitosti dat. Výsledky buduo k dispozici v nové entitě na základě **Název výstupní entity** předpovědi, kterou jste vytvořili.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Vytvořte předpověď při vytváření segmentu

Při vytváření segmentu je také možné předpovídat chybějící hodnoty pro konkrétní atribut volby. Konkrétně, když rychle vytvoříte segment na základě své sjednocené entity zákazníka nebo entity Customer_Measure.

V rámci tohoto toku si vyberete konkrétní atribut, který bude základem vašeho segmentu, jako je spokojenost zákazníka nebo částka nákupu. Po vytvoření segmentu systém navrhne metodu předpovídání chybějících hodnot pro tento atribut.

1. V přehledech cílové skupiny přejděte na **Segmenty** a vyberte dlaždici **Profily**.

2. Vyberte **Pole**, chcete-li vytvořit segment a vyberte **Operátor**, poté vyberte **Recenze**.

3. Poskytněte **Název** a **Zobrazované jméno** pro segment.

4. Zvolte **Uložit**.

5. Pokud segment, který jste vytvořili, obsahuje neúplná data ve zdrojovém poli, můžete předpovědět chybějící hodnoty.
   > [!div class="mx-imgBorder"]
   > ![Tlačítko predikce.](media/segments-predictoption.png "Tlačítko predikce")

6. Poskytněte **Zobrazované jméno** a **Název výstupní entity** pro výsledky predikce.

7. Vyberte **Hotovo**. Vaše předpověď bude brzy vygenerována a bude k dispozici v nové entitě s názvem, který jste zadali pro **Název výstupní entity**.

## <a name="view-a-prediction"></a>Zobrazit předpověď

1. V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.

2. Vyberte předpověď, kterou chcete zkontrolovat.

3. Vyberte elipsu ve sloupci **Akce** a zvolte **Zobrazit**.

4. Uvidíte několik datových bodů v zobrazení vaší predikce.
   > [!div class="mx-imgBorder"]
   > ![Stránka predikce.](media/intelligence-predictionsviewpage.png "Stránka predikce")

   - **Předvídané hodnoty** zobrazuje mapování, které jste vytvořili během fáze mapování Pole na Kategorie. Zobrazí se hodnoty ve vašem datovém souboru, které byly mapovány do konkrétní kategorie.
   -**Špičkové vlivy** jsou faktory v rámci vašeho datového souboru, které s největší pravděpodobností ovlivnily důvěru predikce, že vaše hodnota pole bude mapována na konkrétní kategorii.
   - **Výkon** označuje, jak se předpovědi dělají. Další informace získáte kliknutím na odkaz.
   - **Náhled** ukazuje ukázky souboru výstupních dat z vaší predikce a pravděpodobnosti nebo naší důvěryhodnosti předpovídané hodnoty, kde 0 je nejistý a 1 je jistý.

## <a name="update-a-prediction"></a>Aktualizovat predikci

1. V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.

2. Vyberte předpověď, kterou chcete aktualizovat, a vyberte ikonu **Aktualizovat**.

3. Predikce bude naplánována pro zpracování. Můžete vidět čas, kdy byla naposledy aktualizována ve sloupci **Aktualizováno** na stránce **Předpovědi**.

## <a name="edit-a-prediction"></a>Upravit předpověď

Poté, co vytvoříte predikce, můžete upravit model v AI Builderu pro zvýšení efektivity vašeho modelu.  

1. V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.

2. Vyberte předpověď, kterou chcete upravit.

3. Vyberte elipsu ve sloupci **Akce** a zvolte **Zobrazit**.

4. Vyberte **Přizpůsobit v AI Builderu**.

5. Aktualizujte svůj model v AI Builderu. [Další informace o správě modelů v nástroji AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Příští spuštění vaší predikce použije aktualizovaný model, který jste vytvořili.

> [!NOTE]
> Nové modely vytvořené v AI Builderu se nezobrazí ve přehledech cílových skupin, pokud model nebyl vytvořen z výše uvedených prostředí.

## <a name="remove-a-prediction"></a>Odeberte předpověď

1. V přehledech cílové skupiny přejděte na **Analytické nástroje** > **Predikce** > **Moje predikce**.

2. Vyberte předpověď, kterou chcete odstranit.

3. Vyberte elipsu ve sloupci **Akce** a zvolte **Odstranit**.

4. Potvrďte odstranění.

## <a name="troubleshooting"></a>Řešení problémů

Pokud nemůžete dokončit připojení procesu Dataverse kvůli chybě, můžete zkusit proces dokončit ručně. V procesu připojení se mohou vyskytnout dva známé problémy:

- Řešení Doplněk karty zákazníka není nainstalováno.
    1. Vyplňte pokyny k [instalaci a konfiguraci řešení](customer-card-add-in.md).

- Oprávnění k aplikaci nejsou udělena.
    1. Přejděte na [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Vyberte **Prostředí**.
    1. Vyberte tlačítko se třemi vedle prostředí, do kterého chcete přidat oprávnění, a vyberte **Nastavení**.
    1. Rozbalte **Uživatelé + oprávnění** a vyberte **Uživatelé**.
    1. Vyberte **+ Nový** a vyberte **Uživatel**.
    1. Vyberte možnost **Uživatel aplikace**, pokud ještě není vybrána, a zadejte následující informace:
        - **Uživatelské jméno:** cihelp@microsoft.com
        - **ID aplikace:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Jméno:** Customer
        - **Příjmení:** Insights
        - **Primární e-mail:** cihelp@microsoft.com
    1. Zvolte **Uložit a zavřít**.
    1. Vyberte uživatele, kterého jste právě vytvořili.
    1. Na horním panelu nabídek zvolte **Spravovat role**.
    1. Vyberte **Správce systému**, poté vyberte **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
