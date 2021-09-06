---
title: Vztahy mezi entitami a cesty k entitám
description: Vytvářejte a spravujte vztahy mezi entitami z více zdrojů dat.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 1853fcd8db2918a0b4a19fa0934e2f0ddbcf6d093c85fdf2068a13f954035dec
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035223"
---
# <a name="relationships-between-entities"></a>Vztahy mezi entitami

Vztahy propojují entity a definují graf dat, když entity sdílejí společný identifikátor (cizí klíč). Na tento cizí klíč lze odkazovat z jedné entity do druhé. Propojené entity umožňují definovat segmenty a míry na základě více zdrojů dat.

Existují tři typy vztahů: 
- Neupravitelné systémové vztahy, vytvořené systémem jako součást procesu sjednocení dat
- Neupravitelné zděděné vztahy, které se vytvářejí automaticky během přijímání zdrojů dat 
- Upravitelné vlastní vztahy, vytvořené a konfigurované uživateli

## <a name="non-editable-system-relationships"></a>Neupravitelné systémové vztahy

Během sjednocení dat se automaticky vytvářejí systémové vztahy na základě inteligentního párování. Tyto vztahy pomáhají propojit záznamy profilu zákazníka s odpovídajícími záznamy. Následující diagram ilustruje vytvoření tří systémových vztahů. Entita zákazníka je spárována s jinými entitami za účelem vytvoření sjednocené entity *Zákazník*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram s cestami vztahů pro entitu zákazníka se třemi vztahy 1:N.":::

- **Vztah *CustomerToContact*** byl vytvořen mezi entitou *Zákazník* a entitou *Kontakt*. Entita *Zákazník* získá klíčové pole **Contact_contactID**, které se vztahuje ke klíčovému poli **contactID** entity *Kontakt*.
- **Vztah *CustomerToAccount*** byl vytvořen mezi entitou *Zákazník* a entitou *Obchodní vztah*. Entita *Zákazník* získá klíčové pole **Account_accountID**, které se vztahuje ke klíčovému poli **accountID** entity *Obchodní vztah*.
- **Vztah *CustomerToWebAccount*** byl vytvořen mezi entitou *Zákazník* a entitou *WebAccount*. Entita *Zákazník* získá klíčové pole **WebAccount_webaccountID**, které se vztahuje ke klíčovému poli **webaccountID** entity *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Neupravitelné zděděné vztahy

Během procesu přijímání dat systém hledá ve zdrojích dat existující vztahy. Pokud neexistuje žádný vztah, systém ho automaticky vytvoří. Tyto vztahy se také používají v následných procesech.

## <a name="create-a-custom-relationship"></a>Vytvoření vlastního vztahu

Vztah se skládá ze *zdrojové entity* obsahující cizí klíč a *cílové entity* na kterou cizí klíč zdrojové entity ukazuje. 

1. V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.

2. Vyberte **Nový vztah**.

3. V podokně **Nový vztah** zadejte následující informace:

   :::image type="content" source="media/relationship-add.png" alt-text="Boční podokno Nový vztah s prázdnými vstupními poli.":::

   - **Název vztahu**: Název, který vyjadřuje účel vztahu. Příklad: CustomerToSupportCase (vztah mezi zákazníkem a případem podpory).
   - **Popis**: Popis vztahu.
   - **Zdrojová entita**: Entita, která se ve vztahu používá jako zdroj. Příklad: SupportCase (případ podpory).
   - **Cílová entita**: Entita, která se ve vztahu používá jako cíl. Příklad: Customer (zákazník).
   - **Kardinalita zdroje**: Určete kardinalitu zdrojové entity. Kardinalita popisuje počet možných prvků v sadě. Vždy je ve vztahu ke kardinalitě cíle. Můžete si vybrat hodnotu **Jeden** nebo **Mnoho**. Podporovány jsou pouze vztahy N:1 a 1:1.  
     - Vztah mnoha k jednomu jinému: Více zdrojových záznamů se může vztahovat k jednomu cílovému záznamu. Příklad: Několik případů podpory od jednoho zákazníka.
     - Vztah jednoho k jednomu jinému: Jeden záznam zdroje se vztahuje k jednomu cílovému záznamu. Příklad: Jedno věrnostní ID pro jednoho zákazníka.

     > [!NOTE]
     > Vztahy „mnoho k mnoha jiným“ lze vytvořit pomocí dvou vztahů „mnoho k jednomu“ a propojovací entity, která spojuje zdrojovou entitu a cílovou entitu.

   - **Cílová kardinalita**: Vyberte kardinalitu záznamů cílové entity. 
   - **Pole zdrojového klíče**: Pole cizího klíče ve zdrojové entitě. Příklad: SupportCase může použít CaseID jako pole cizího klíče.
   - **Pole cílového klíče**: Klíčové pole cílové entity. Příklad: Customer může použít klíčové pole **CustomerID**.

4. Výběrem položky **Uložit** vytvoříte vlastní vztah.

## <a name="view-relationships"></a>Zobrazení vztahů

Stránka Vztahy uvádí seznam všech vztahů, které byly vytvořeny. Každý řádek představuje vztah, který zahrnuje také podrobnosti o zdrojové entitě, cílové entitě a kardinalitě. 

:::image type="content" source="media/relationships-list.png" alt-text="Seznam vztahů a možnosti na panelu akcí na stránce Vztahy.":::

Tato stránka nabízí sadu možností pro stávající a nové vztahy: 
- **Nový vztah**: [Vytvoření vlastního vztahu](#create-a-custom-relationship).
- **Vizualizér** :[Prozkoumejte vizualizér vztahů](#explore-the-relationship-visualizer) a zobrazte si síťový diagram stávajících vztahů a jejich kardinalitu.
- **Filtrovat podle**: Vyberte typ vztahů, které se mají zobrazit v seznamu.
- **Vyhledat vztahy**: U vlastností vztahů použijte textové vyhledávání.

### <a name="explore-the-relationship-visualizer"></a>Prohlídka vizualizéru vztahů

Vizualizér vztahů zobrazuje si síťový diagram stávajících vztahů mezi propojenými entitami a jejich kardinalitu. Vizualizuje také cestu vztahu.

Chcete-li si zobrazení přizpůsobit, můžete změnit polohu polí jejich přetažením na plátně.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Snímek síťového diagramu vizualizátoru vztahů s propojením mezi souvisejícími entitami.":::

Dostupné možnosti: 
- **Exportovat jako obrázek**: Uloží aktuální zobrazení jako obrazový soubor.
- **Změnit na vodorovné/svislé rozložení**: Změňte zarovnání entit a vztahů.
- **Upravit**: Aktualizujte vlastnosti vlastních vztahů v podokně úprav a uložte změny.

### <a name="relationship-path"></a>Cesta vztahu

Cesta vztahu popisuje entity, které jsou propojeny se vztahy mezi zdrojovou entitou a cílovou entitou. Používá se při vytváření segmentu nebo míry, která zahrnuje jiné entity než entitu jednotného profilu, a existuje několik možností, jak dosáhnout entity sjednoceného profilu.

Cesta vztahu informuje systém, přes které vztahy má přistupovat k entitě jednotného profilu. Různé cesty vztahů mohou přinést různé výsledky.

Například entita *eCommerce_eCommercePurchases* má ke sjednocenému profilu entity *Zákazník* následující vztahy:

- eCommerce_eCommercePurchases > Zákazník
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Zákazník
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Zákazník 

Cesta vztahu určuje, které entity můžete použít při vytváření pravidel pro míry nebo segmenty. Výběr možnosti s nejdelší cestou vztahu pravděpodobně přinese méně výsledků, protože odpovídající záznamy musí být součástí všech entit. V tomto případě musí zákazník mít zakoupené zboží prostřednictvím elektronického obchodování (eCommerce_eCommercePurchases), v pokladním místě (POS_posPurchases) a účastnit se našeho věrnostního programu (loyaltyScheme_loyCustomers). Při výběru první možnosti byste pravděpodobně získali více výsledků, protože zákazníci musí existovat pouze v jedné další entitě.

## <a name="manage-existing-relationships"></a>Správa existujících vztahů 

Na stránce Vztahy je každý vztah reprezentován řádkem. 

Vyberte vztah a zvolte jednu z následujících možností: 
 
- **Upravit**: Aktualizujte vlastnosti vlastních vztahů v podokně úprav a uložte změny.
- **Odstranit**: Odstranění vlastních vztahů.
- **Zobrazit** : Zobrazení systémem vytvořených a zděděných vztahů. 

## <a name="next-step"></a>Další krok

Systém a vlastní vztahy se používají k [vytváření segmentů](segments.md) a [měr](measures.md) na základě více zdrojů dat, které již nejsou seskupeny v silech.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
