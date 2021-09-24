---
title: Vytvoření segmentů pomocí tvůrce segmentů
description: Vytvořte segmenty zákazníků a seskupte je podle různých atributů.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494486"
---
# <a name="create-segments"></a>Vytvoření segmentů

Definujte složité filtry kolem sjednocené entity zákazníka a souvisejících entit. Každý segment po zpracování vytvoří sadu záznamů o zákaznících, které můžete exportovat a se kterými můžete provádět akce. Segmenty jsou spravovány na stránce **Segmenty**. Můžete [vytvářet nové segmenty](#create-a-new-segment) pomocí [tvůrce segmentů](#segment-builder) nebo [vytvářet rychlé segmenty](#quick-segments) z jiných oblastí aplikace.

## <a name="segment-builder"></a>Tvůrce segmentů

Následující obrázek ukazuje různé aspekty tvůrce segmentů. Ukazuje segment, jehož výsledkem je skupina zákazníků. Zákazníci si objednali zboží v konkrétním časový rámec a nasbírali řadu bodů za odměnu nebo utratili určitou částku peněz. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Prvky nástroje pro tvorbu segmentů." lightbox="media/segment-builder-overview.png":::

1 - Uspořádejte svůj segment pomocí pravidel a dílčích pravidel. Každé pravidlo nebo dílčí pravidlo se skládá z podmínek. Zkombinujte podmínky s logickými operátory

2 - Vyberte [cestu vztahu](relationships.md) mezi entitami, které platí pro pravidlo. Cesta vztahu určuje, které atributy lze použít v podmínce.

3 - Spravujte pravidla a dílčí pravidla. Změňte pozici pravidla nebo jej odstraňte.

4 - Přidejte podmínky a vytvořte správnou úroveň vnoření pomocí dílčích pravidel.

5 - Aplikujte nastavené operace na připojená pravidla.

6 - Pomocí podokna atributů přidejte dostupné atributy entit nebo vytvořte podmínky na základě atributů. Podokno zobrazuje seznam entit a atributů na základě zvolené cesty vztahu, které jsou k dispozici pro vybrané pravidlo.

7 - Přidejte podmínky na základě atributů ke stávajícím pravidlům a dílčím pravidlům nebo je přidejte do nového pravidla.

8 - Zrušit a znovu provést změny při vytváření segmentu.

Výše uvedený příklad ilustruje schopnost segmentace. Definovali jsme segment pro zákazníky, kteří nakoupili zboží online alespoň za 500 USD *a* mají zájem o vývoj softwaru.

## <a name="create-a-new-segment"></a>Vytvořit nový segment

Existuje několik způsobů, jak vytvořit nový segment. Tato část popisuje, jak vytvořit vlastní segment od začátku. Můžete také vytvořit *rychlý segment* na základě existujících entit nebo využijte strojové učení modely k získání *navrhovaných segmentů*. Další informace: [Přehled segmentů](segments.md)

Při vytváření segmentu můžete uložit koncept. Bude uložen jako neaktivní segment a nelze jej aktivovat, dokud není dokončen s platnou konfigurací.

1. Přejde na stránku **Segmenty**.

1. Vyberte **Nový** > **Vytvořit svůj vlastní**.

1. Na stránce tvůrce segmentů definujte první pravidlo. Pravidlo se skládá z jedné nebo více podmínek a definuje sadu zákazníků.

1. V části **Pravidlo 1** vyberte atribut entity, podle které chcete filtrovat zákazníky. Vybrat atributy lze dvěma způsoby: 
   - Zkontrolujte seznam dostupných entit a atributů v podokně **Přidat do pravidla** a vyberte ikonu **+** vedle atributu, který chcete přidat. Vyberte, zda chcete přidat atribut do existujícího pravidla, nebo jej použít k vytvoření nového pravidla.
   - Chcete -li zobrazit návrhy shod, zadejte název atributu do sekce pravidel.

1. Vyberte operátory k určení odpovídajících hodnot podmínky. Atribut může mít jako hodnotu jeden ze čtyř datových typů: číselný, řetězec, datum nebo logickou hodnotu. V závislosti na datovém typu atributu jsou k určení podmínky k dispozici různé operátory. 

1. Vyberte **Přidat podmínku** pro přidání dalších podmínek do pravidla. Chcete -li vytvořit pravidlo pod aktuálním pravidlem, vyberte **Přidat dílčí pravidlo**.

1. Pokud pravidlo používá jiné entity než *Zákazník*, musíte nastavit cestu vztahu. Cesta vztahu je povinná a informuje systém, přes které vztahy chcete přistupovat k jednotné entitě zákazníka. Vyberte **Nastavit cestu vztahu** a namapujte vybranou entitu na jednotnou entitu zákazníka. Pokud existuje pouze jedna možná cesta vztahu, systém ji automaticky vybere. Různé cesty vztahů mohou přinést různé výsledky. Každé pravidlo může mít svou vlastní cestu vztahu.

   :::image type="content" source="media/relationship-path.png" alt-text="Cesta potenciálního vztahu při vytváření pravidla na základě entity mapované na jednotnou entitu zákazníka.":::

   Například entita *eCommerce_eCommercePurchases* na snímku obrazovky má čtyři možnosti mapování na entitu *Zákazník*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Zákazník
   - eCommerce_eCommercePurchases > Zákazník
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Zákazník
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Zákazník Při výběru poslední možnosti můžeme do podmínek pravidla zahrnout atributy ze všech uvedených entit. Pravděpodobně získáme méně výsledků, protože odpovídající záznamy o zákaznících musí být součástí všech entit. V tomto případě zákazníci zakoupili zboží prostřednictvím elektronického obchodování (*eCommerce_eCommercePurchases*), v pokladním místě (*POS_posPurchases*) a účastnili se našeho věrnostního programu (*loyaltyScheme_loyCustomers*). Při výběru druhé možnosti můžeme vybrat pouze atributy z entit *eCommerce_eCommercePurchases* a *Zákazník*. Výsledkem bude pravděpodobně více výsledných profilů zákazníků.

1. Pokud máte v pravidle více podmínek, můžete si vybrat, který logický operátor je spojuje.

   - Operátor **AND**: Pro zařazení záznamu do segmentu musí být splněny všechny podmínky. Tato možnost je nejužitečnější při definování podmínek mezi různými entitami.

   - Operátor **OR**: Pro zařazení záznamu do segmentu musí být jedna z podmínek. Tato možnost je nejužitečnější při definování více podmínek pro stejnou entitu.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Pravidlo s dvěma podmínkami AND":::

   Při použití operátoru OR musí být všechny podmínky založeny na entitách zahrnutých v cestě vztahu.

   1. Můžete vytvořit více pravidel a vytvořit různé sady záznamů o zákaznících. Skupiny můžete kombinovat tak, aby zahrnovaly zákazníky požadované pro váš obchodní případ. Chcete-li vytvořit nové pravidlo, vyberte **Přidat pravidlo**. Konkrétně, pokud nemůžete zahrnout entitu do pravidla kvůli zadané cestě vztahu, musíte vytvořit nové pravidlo pro výběr atributů z něj.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Přidejte nové pravidlo do segmentu a vyberte nastavený operátor.":::

   1. Vyberte jednoho z nastavených operátorů: **Union**, **Intersect** nebo **Except**.

   - **Sjednocení** sjednotí dvě skupiny.

   - **Průnik** překrývá dvě skupiny. Pouze data, která *jsou společná* pro obě skupiny, zůstanou zachována ve sjednocené skupině.

   - **Výjimka** kombinuje dvě skupiny. Pouze data ve skupině A, která *nejsou společná* s daty ve skupině B, zůstanou zachována.

1. Ve výchozím nastavení segmenty generují výstupní entitu obsahující všechny atributy zákaznické profily, které odpovídají definovaným filtrům. Pokud je segment založen na jiných entitách než *Zákazník*, můžete do výstupní entity přidat další atributy z těchto entit. Volbou **Atributy projektu** zvolte atributy, které budou připojeny k výstupní entitě.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Příklad projektovaných atributů vybraných v postranním podokně, které mají být přidány do výstupní entity.":::
  
   Příklad: Segment je založen na entitě, která obsahuje data o nákupu, související s entitou *Zákazník*. Segment hledá všechny zákazníky ze Španělska, kteří zakoupili zboží v aktuálním roce. Můžete se rozhodnout připojit atributy, jako cena zboží nebo datum nákupu, ke všem odpovídajícím záznamům zákazníků ve výstupní entitě. Tyto informace mohou být užitečné pro analýzu sezónních korelací s celkovou útratou.

   > [!NOTE]
   > - Projektované atributy fungují pouze pro entity, které mají vztah jedna k mnoha s entitou zákazníka. Například jeden zákazník může mít více předplatných.
   > - Atributy můžete projektovat pouze z entity, která se používá v každém pravidle segmentového dotazu, který vytváříte.
   > - Při použití operátorů sady jsou zohledněny projektované atributy.

1. Před uložením a spuštěním segmentu vyberte **Upravit podrobnosti** vedle názvu segmentu. Zadejte název pro svůj segment a aktualizujte navrhovaný **Název výstupní entity** pro segment. K segmentu můžete také přidat popis.

1. Vyberte **Spustit** a uložte a zpracujte svůj segment, pokud jsou ověřeny všechny požadavky. V opačném případě bude uložen jako neaktivní koncept segmentu.

1. Volbou **Zpět na segmenty** přejdete zpět na stránku **Segmenty**.

> [!TIP]
> - Při nastavování operátorů pro podmínky nebude tvůrce segmentů navrhovat platné hodnoty z entit. Můžete přejít na **Data** > **Entity** a stáhněte si data entit, abyste zjistili, které hodnoty jsou k dispozici.
> - Podmínky založené na datech vám umožňují přepínat mezi pevnými daty a pohyblivým rozsahem dat.
> - Pokud máte pro svůj segment více pravidel, najdete kolem pravidla, které upravujete, modrý pruh.
> - Pravidla a podmínky můžete přesunout na jiná místa v definici segmentu. Vyberte [...] vedle pravidla nebo podmínky a zvolte, jak a kam je chcete přesunout.
> - Ovládací prvky **Vrátit zpět** a **Opakovat** na panelu příkazů vám umožní vrátit zpět změny.

## <a name="quick-segments"></a>Rychlé segmenty

Rychlé segmenty umožňují rychle vytvářet jednoduché segmenty jediným operátorem a získat tak rychlejší přehledy.

1. Na stránce **Segmenty** vyberte **Nový** > **Vytvořit z**.

   - Vyberte možnost **Profiley**, chcete-li vytvořit segment založený na entitě *sjednocený zákazník*.
   - Vyberte možnost **Míry**, pokud chcete vytvořit segment kolem měr, které jste dříve vytvořili.
   - Vyberte možnost **Analytické nástroje**, chcete-li sestavit segment kolem jedné z výstupních entit, které jste vygenerovali pomocí funkcí **Predikce** nebo **Vlastní modely**.

2. V dialogovém okně **Nový rychlý segment** vyberte atribut z rozbalovací nabídky **Pole**.

3. Systém poskytne více přehledů, které vám pomohou vytvořit lepší segmenty vašich zákazníků.
   - Pro kategorická pole zobrazíme 10 nejlepších zákazníků. Vyberte **Hodnotu** a zvolte **Hodnotit**.

   - U číselného atributu systém zobrazí, jaká hodnota atributu spadá pod percentil každého zákazníka. Zvolte **Operátor** a **Hodnotu** a pak vyberte **Zkontrolovat**.

4. Systém vám poskytne **Odhadovanou velikost segmentu**. Můžete zvolit, zda chcete vygenerovat segment, který jste definovali, nebo jej nejprve znovu navštívit, abyste získali jinou velikost segmentu.

    > [!div class="mx-imgBorder"]
    > ![Název a odhad pro rychlý segment.](media/quick-segment-name.png "Název a odhad pro rychlý segment")

5. Zadejte **Název** svého sgmentu. Volitelně zadejte **Zobrazovaný název**.

6. Výběrem možnosti **Uložit** vytvořte segment.

7. Po dokončení zpracování segmentu jej můžete zobrazit jako jakýkoli jiný segment, který jste vytvořili.

## <a name="next-steps"></a>Další kroky

[Exportujte segment](export-destinations.md) a prozkoumejte [integraci karty zákazníka](customer-card-add-in.md) pro použití segmentů v jiných aplikacích.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
