---
title: Vytvořit a spravovat segmenty
description: Vytvořte segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064929"
---
# <a name="create-and-manage-segments"></a>Vytvořit a spravovat segmenty

Definujte složité filtry kolem sjednocené entity zákazníka a souvisejících entit. Každý segment po zpracování vytvoří sadu záznamů o zákaznících, které můžete exportovat a se kterými můžete provádět akce. Segmenty jsou spravovány na stránce **Segmenty**. 

Následující příklad ukazuje funkci segmentace. Definovali jsme segment pro zákazníky, kteří si za posledních 90 dní objednali zboží alespoň za $500 *a* kteří se účastnili volání služby zákazníkům, které bylo eskalováno.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Screenshot uživatelského rozhraní nástroje pro vytváření segmentů se dvěma skupinami, které určují segment zákazníka.":::

## <a name="create-a-new-segment"></a>Vytvořit nový segment

Existuje několik způsobů, jak vytvořit nový segment. Tato část popisuje, jak vytvořit *prázdný segment*. Můžete také vytvořit *rychlý segment* na základě existujících entit nebo využijte strojové učení modely k získání *navrhovaných segmentů*. Další informace: [Přehled segmentů](segments.md)

Při vytváření segmentu můžete uložit koncept. Bude uložen jako neaktivní segment a nelze jej aktivovat, dokud není dokončen s platnou konfigurací.

1. Přejde na stránku **Segmenty**.

1. Vybrat **Nový** > **Prázdný segmeny**.

1. V podokně **Nový segment** vyberte typ segmentu:

   - **Dynamické segmenty** [obnovení](segments.md#refresh-segments) podle opakujícího se plánu.
   - **Statické segmenty** se spustí jednou, když jej vytvoříte.

1. Poskytněte **název výstupní entity** pro daný segment. Volitelně zadejte zobrazované jméno a popis, který pomáhá identifikovat segment.

1. Vyberte **Další**, chcete-li se dostat na stránku **Tvůrce segmentu**, kde definujete skupinu. Skupina je sada zákazníků.

1. Zvolte entitu, která obsahuje atribut, který chcete zahrnout do segmentace.

1. Vyberte atribut, podle kterého chcete segmentovat. Tento atribut může mít jeden ze čtyř typů hodnot: číselný, řetězec, datum nebo logický.

1. Zvolte operátor a hodnotu vybraného atributu.

   > [!div class="mx-imgBorder"]
   > ![Vlastní filtr skupin](media/customer-group-numbers.png "Filtr skupin zákazníků")

   |Počet |Definice  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operátor         |
   |4    |Hodnota         |

   1. Chcete-li do skupiny přidat další podmínky, můžete použít dva logické operátory:

      - Operátor **AND**: Obě podmínky musí být splněny v rámci procesu segmentace. Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.

      - Operátor **OR**: Buď je třeba splnit jednu z podmínek v rámci procesu segmentace. Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.

      > [!div class="mx-imgBorder"]
      > ![Operátor OR, u kterého je třeba splnit obě podmínky](media/segmentation-either-condition.png "Operátor OR, u kterého je třeba splnit obě podmínky")

      V současné době je možné vnořit operátor **OR** do operátoru **AND**, ale ne naopak.

   1. Každá skupina odpovídá skupině zákazníků. Skupiny můžete kombinovat tak, aby zahrnovaly zákazníky požadované pro váš obchodní případ.    
   Vyberte **Přidat skupinu**.

      > [!div class="mx-imgBorder"]
      > ![Skupina zákazníků přidat skupinu](media/customer-group-add-group.png "Skupina zákazníků přidat skupinu")

   1. Vyberte jednoho z nastavených operátorů: **Union**, **Intersect** nebo **Except**.

   > [!div class="mx-imgBorder"]
   > ![Skupina zákazníků přidat sjednocení](media/customer-group-union.png "Skupina zákazníků přidat sjednocení")

   - **Sjednocení** sjednotí dvě skupiny.

   - **Průnik** překrývá dvě skupiny. Pouze data, která *jsou společná* pro obě skupiny, zůstanou zachována ve sjednocené skupině.

   - **Výjimka** kombinuje dvě skupiny. Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, zůstanou zachována.

1. Pokud je entita propojena se sjednocenou entitou zákazníka prostřednictvím [Vztahů](relationships.md), musíte definovat cestu vztahu k vytvoření platného segmentu. Přidávejte entity z cesty vztahu, dokud nevyberete entitu **Zákazník: CustomerInsights** z rozevíracího seznamu. Poté vyberte **Všechny záznamy** pro každý krok.

   > [!div class="mx-imgBorder"]
   > ![Cesta vztahů při vytváření segmentů](media/segments-multiple-relationships.png "Cesta vztahů při vytváření segmentů")

1. Ve výchozím nastavení segmenty generují výstupní entitu, která obsahuje všechny atributy profilů zákazníků, které odpovídají definovaným filtrům. Pokud je segment založen na jiných entitách než *Zákazník*, můžete do výstupní entity přidat další atributy z těchto entit. Volbou **Atributy projektu** zvolte atributy, které budou připojeny k výstupní entitě.  
  
   Příklad: Segment je založen na entitě, která obsahuje údaje o aktivitě zákazníka, která je provázána s entitou *Zákazník*. Segment vyhledá všechny zákazníky, kteří volali na technickou podporu za posledních 60 dní. Můžete se rozhodnout připojit délku hovoru a počet hovorů ke všem odpovídajícím záznamům zákazníků ve výstupní entitě. Tyto informace mohou být užitečné k zaslání e-mailu s užitečnými odkazy na články online nápovědy a často kladené dotazy zákazníkům, kteří často volali.

   > [!NOTE]
   > - Projektované atributy fungují pouze pro entity, které mají vztah jedna k mnoha s entitou zákazníka. Například jeden zákazník může mít více předplatných.
   > - Můžete projektovat pouze atributy z entity, která se používá v každé skupině segmentového dotazu, který vytváříte.
   > - Při použití operátorů sady jsou zohledněny projektované atributy.

1. Výběrem možnosti **Uložit** uložte segment. Pokud budou všechny požadavky ověřeny, bude váš segment uložen a zpracován. V opačném případě bude uložen jako koncept.

1. Volbou **Zpět na segmenty** přejdete zpět na stránku **Segmenty**.



## <a name="quick-segments"></a>Rychlé segmenty

Rychlé segmenty umožňují rychle vytvářet jednoduché segmenty jediným operátorem a získat tak rychlejší přehledy.

1. Na stránce **Segmenty** vyberte **Nový** > **Vytvořit z**.

   - Vyberte možnost **Profiley**, chcete-li vytvořit segment založený na entitě *sjednocený zákazník*.
   - Vyberte možnost **Míry**, pokud chcete vytvořit segment kolem měr, které jste dříve vytvořili.
   - Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.

2. V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**.

3. Systém vám poskytne další přehledy, které vám pomohou vytvořit lepší segmenty vašich zákazníků.
   - Pro kategorická pole zobrazíme 10 nejlepších zákazníků. Vyberte **Hodnotu** a zvolte **Hodnotit**.

   - U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka. Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.

4. Systém vám poskytne **Odhadovanou velikost segmentu**. Můžete zvolit, zda chcete vygenerovat segment, který jste definovali, nebo jej nejprve znovu navštívit, abyste získali jinou velikost segmentu.

    > [!div class="mx-imgBorder"]
    > ![Název a odhad pro rychlý segment](media/quick-segment-name.png "Název a odhad pro rychlý segment")

5. Zadejte **Název** svého sgmentu. Volitelně zadejte **Zobrazovaný název**.

6. Výběrem možnosti **Uložit** vytvořte segment.

7. Po dokončení zpracování segmentu jej můžete zobrazit jako jakýkoli jiný segment, který jste vytvořili.

## <a name="next-steps"></a>Další kroky

[Exportujtesegment](export-destinations.md) a prozkoumejte [Kartu zákazníka](customer-card-add-in.md) a [Konektory](export-power-bi.md), abyste získali přehled o úrovni zákazníka.

[!INCLUDE[footer-include](../includes/footer-banner.md)]