---
title: Experimenty v Machine Learning Studio (classic)
description: Použití modelů Machine Learning Studio (classic) v Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555161"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Použití modelů založených na Azure Machine Learning Studio (classic)

Sjednocená data v Dynamics 365 Customer Insights jsou zdrojem pro vytváření modelů strojového učení, které mohou generovat další obchodní poznatky. Customer Insights se integruje s řešeními Machine Learning Studio (classic), abyste mohli používat své vlastní modely. Chcete-li vědět, jak modely vyvinuté v Azure Machine Learning jsou integrovány s Customer Insights, viz [Experimenty v Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Požadavky

- Přístup k Customer Insights
- Aktivní předplatné Azure Enterprise
- [Sjednocené profily zákazníka](data-unification.md)
- Nastavený [export entity do úložiště Azure Blob](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Nastavení řešení Machine Learning Studio Classic

V prvním kroku musíme vytvořit pracovní prostor a otevřít Machine Learning Studio (classic).

1. Předěte na [https://www.portal.azure.com](https://www.portal.azure.com/) a přihlaste se.

1. Vyberte **Vytvořit prostředek**.

1. Vyhledejte **Pracovní prostor Machine Learning Studio** a vyberte **Vytvořit**.

1. Zadejte požadované údaje pro [vytvoření pracovního prostoru](/azure/machine-learning/studio/create-workspace). Zvolte **Cenová úroveň plánu webové služby** na základě množství dat, které plánujete importovat. Pro nejlepší výkon vyberte **Umístění**, které je pro vás geograficky nejbližší.

1. Po vytvoření prostředku se zobrazí řídicí panel pracovního prostoru Machine Learning Studio. Vyberte **Spustit Machine Learning Studio**.

   ![Uživatelské rozhraní Azure Machine Learning Studio.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Práce s Azure Machine Learning Studio

Nyní můžete vytvořit nový experiment nebo importovat existující šablonu experimentu z ukázkové galerie. Existují ukázkové experimenty pro tři standardní scénáře:

- [Predikce úbytku](#churn-analysis)

- [Hodnota životnosti zákazníka](#customer-lifetime-value-prediction)

- [Doporučení produktu nebo další nejlepší akce](#productrecommendation-or-next-best-action)

1. Pokud vytvoříte nový experiment nebo použijete šablonu experimentu z galerie, musíte nakonfigurovat vlastnosti **Importovat data**. V průvodci nebo přímo zadejte podrobnosti pro přístup k úložišti Azure Blob Storage, které obsahuje vaše data.  

   ![Experiment Azure Machine Learning Studio.](media/azure-machine-learning-studio-experiment.png)

1. Nyní můžete sestavit vlastní procesní kanál pro čištění a předzpracování dat, extrahování funkcí a trénování vhodného modelu.

1. Otestujte a optimalizujte výkon modelu.

1. Pokud jste spokojeni s kvalitou modelu, vyberte **Nastavit webovou službu** > **Prediktivní webová služba**. Tato možnost importuje trénovaný model a kanál pro vytváření funkcí z výukového experimentu do prediktivní služby. Prediktivní služba může vzít další sadu vstupních dat se schématem použitým ve výukovém experimentu k vytváření predikcí.

   ![Nastavení prediktivní webové služby.](media/predictive-webservice-control.png)

1. Jakmile je experiment prediktivní webové služby úspěšný, můžete jej nasadit pro automatické plánování. Chcete-li, aby webová služba fungovala s Customer Insights, zvolte **Nasadit webovou službu** > **Nasadit webovou službu [nová] Preview**. [Další informace o nasazení webové služby](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Nasazení prediktivní webové služby.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Ukázkové modely z galerie

Pro modely v tomto článku použijeme fiktivní scénář Contoso Hotel. Contoso Hotel shromažďuje následující údaje:

- Data CRM sestávající z aktivity hotelového pobytu. Datová sada obsahuje informace o datech pobytu každého registrovaného zákazníka. Obsahuje také informace o rezervaci, typech pokojů, podrobnosti o výdajích atd. Data pokrývají čtyři roky, od ledna 2014 do ledna 2018.
- Profily zákazníků hotelových hostů. Tyto profily obsahují informace o každém zákazníkovi, včetně jeho jména, data narození, poštovní adresy, pohlaví a telefonního čísla.
- Využití služeb nabízených hotelem, jako jsou lázně, prádelna, WiFi nebo kurýr. Tyto informace se zaznamenávají pro každého registrovaného zákazníka. Obvykle je využívání služeb spojeno s pobytem. V některých případech mohou služby využívat zákazníci, aniž by zůstali v hotelu.

## <a name="churn-analysis"></a>Analýza úbytku

Analýza úbytku se vztahuje na různé oblasti podnikání. V tomto příkladu se podíváme na úbytek služeb, konkrétně v souvislosti s hotelovými službami, jak je popsáno výše. Poskytuje funkční příklad kompletního kanálu modelu, který může být použit jako výchozí bod pro jakýkoli jiný typ modelu úbytku.

### <a name="definition-of-churn"></a>Definice úbytku

Definice úbytku se může lišit podle scénáře. V tomto příkladu by měl být host, který v minulém roce nenavštívil hotel, označen jako odchozí.  

Šablonu experimentu lze importovat z galerie. Nejprve se ujistěte, že importujete data pro **Aktivita hotelového pobytu** (Hotel Stay Activity), **Zákaznická data** (Customer Data) a **Data využití služby** (Service Usage Data) z úložiště Azure Blob.

   ![Import dat pro model úbytku.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Vytváření funkcí

Na základě definice úbytku nejprve identifikujeme nezpracované funkce, které ovlivní popisek. Poté tyto nezpracované funkce zpracujeme na číselné funkce, které lze použít s modely strojového učení. K integraci dat dochází v Customer Insights, abychom se k těmto tabulkám mohli připojit pomocí *ID zákazníka*.

   ![Spojení importovaných dat.](media/join-imported-data.png)

Vytváření funkcí pro sestavení modelu analýzy odlivu zákazníků může být trochu složitější. Data jsou funkcí času, kdy se denně zaznamenává nová hotelová aktivita. Během vytváření funkcí chceme generovat statické funkce z dynamických dat. V tomto případě generujeme několik funkcí z hotelové aktivity s posuvným oknem po dobu jednoho roku. Rovněž rozšiřujeme kategorické funkce, jako je typ pokoje nebo typ rezervace, na samostatné funkce pomocí kódování nul a jedniček.  

Končený seznam funkcí:

| **Počet**  | **Původní sloupec**          | **Odvozené funkce**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Room Type (typ pokoje)                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Typ rezervace                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Travel Category (kategorie cestování)              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dollars Spent (utracené dolary)                | TotalDollarSpent                                                                                                                          |
| 5           | Check-in and Checkout dates (datum přihlášení a odhlášení)  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Service Usage (využití služby)                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Výběr modelu

Nyní musíme zvolit optimální algoritmus, který se má použít. V tomto případě je většina funkcí založena na kategorických prvcích. Typicky dobře fungují modely založené na rozhodovacích stromech. Pokud existují pouze numerické funkce, mohla by být lepší volba neuronové sítě. V takových situacích je také dobrým kandidátem metoda podpůrných vektorů (SVM); k získání nejlepšího výkonu však potřebuje trochu vyladění. Zvolíme si **Zesílený rozhodovací strom se dvěma třídami** jako první zvolený model následovaný **SVM se dvěma třídami** jako druhý model. Azure Machine Learning Studio vám umožňuje provádět A/B testování, takže je výhodné začít se dvěma modely, nikoli s jedním.

Následující obrázek ukazuje cvičení modelu a kanál vyhodnocení v Azure Machine Learning Studio:

![Model úbytku v Azure Machine Learning Studio.](media/azure-machine-learning-model.png)

Také používáme techniku zvanou **Důležitost funkce permutace**, což je důležitý aspekt optimalizace modelu. Integrované modely mají malý až žádný přehled o dopadu na jakékoli konkrétní funkce konečné predikce. Kalkulačka důležitosti funkce používá vlastní algoritmus pro výpočet vlivu jednotlivých prvků na výsledek konkrétního modelu. Důležitost funkce je normalizována mezi +1 a -1. Negativní vliv znamená, že odpovídající funkce má kontraintuitivní vliv na výsledek a měla by být z modelu odstraněna. Pozitivní vliv naznačuje, že funkce výrazně přispívá k predikci. Tyto hodnoty nejsou korelačními koeficienty, protože se jedná o odlišné metriky. Další informace viz [Důležitost funkce permutace](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Celý [experiment úbytku je k dispozici v Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Predikce hodnoty životnosti zákazníka

Výpočet hodnoty životnosti zákazníka (CLTV) je jednou z klíčových metrik, které může firma použít k hodnocení a segmentaci svých zákazníků. Pro hotelnictví je důležité znát své zákazníky. Například důležité je porozumění faktorům, které vytváří dobré zákazníky. Pomáhá vedení hotelu posoudit, na které funkce se musí zaměřit a zlepšit je, aby byli spokojeni jejich draze platící zákazníci. Tato rozhodnutí mohou mít přímý dopad na prodej a výdělky.  

### <a name="definition-of-cltv"></a>Definice CLTV

V tomto příkladu definujeme CLTV zákazníka jako celkovou částku v dolarech, kterou má zákazník v následujících 365 dnech utratit. K predikci této hodnoty využijeme data všech zákazníků za poslední tři roky.

### <a name="featurization"></a>Vytváření funkcí

V tomto případě bude vytváření funkcí velmi podobné scénáři úbytku. Popisky a předpovídané hodnoty se však liší od výše uvedených.

### <a name="model-selection"></a>Výběr modelu

Predikce CLTV je regresní problém, protože predikovaná hodnota je kladná oceňovaná spojitá proměnná. Na základě vlastností objektu vybereme **Posílená regrese rozhodovacího stromu** jako jeden algoritmus a **Regrese neuronové sítě** jako další algoritmus pro trénování modelu.

## <a name="product-recommendation-or-next-best-action"></a>Doporučení produktu nebo další nejlepší akce

Doporučení produktu v hotelovém scénáři se interpretuje jako doporučení služeb, které hotel nabízí zákazníkům. Cílem je vybrat vhodné služby pro zákazníky tak, aby jejich využití bylo maximalizováno. Je to podobné jako doporučení filmů pro uživatele služeb streamování videa.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Defnice doporučení produktu nebo další nejlepší akce

Tento cíl definujeme jako maximalizaci dolarové částky za využití služeb tím, že hotelovým zákazníkům nabízíme ty nejlepší služby podle jejich zájmu.

### <a name="featurization"></a>Vytváření funkcí

Stejně jako u modelu úbytku se připojíme k ID zákazníka služby (ServiceCustomerID) hotelu pomocí ID zákazníka (CustomerID), abychom mohli vytvářet doporučení konzistentně podle ID zákazníka.

![Vytváření funkcí pro model doporučení.](media/azure-machine-learning-model-featurization.png)

Data jsou získána ze tří různých entit a funkce jsou z nich odvozeny. Vytváření funkcí pro problém doporučení se liší ve srovnání se scénáři úbytku nebo CLTV. Model doporučení vyžaduje vstupní data ve formě tří sad funkcí.

### <a name="model-selection"></a>Výběr modelu

Predikujeme produkty nebo služby pomocí algoritmu **Trénování nástroje pro doporučení shody** pro trénování modelu doporučení.

![Algoritmus doporučení produktů.](media/azure-machine-learning-model-recommendation-algorithm.png)

Tři vstupní porty pro model **Trénování nástroje pro doporučení shody** vezmou data o využití služeb cvičení, popis zákazníka (volitelné) a popis služby. Existují tři různé způsoby bodování modelu. Jedním z nich je hodnocení modelu, kde se skóre Normalizovaný srážkový kumulativní přírůstek (NDCG) vypočítá pro zařazení hodnocených položek. V tomto experimentu máme skóre NDCG 0,97. Další dvě možnosti jsou bodování modelu v celém katalogu doporučitelných služeb nebo bodování pouze u položek, které uživatelé dosud nepoužili.

Pokud se podíváme dále na distribuci doporučení v celém katalogu služeb, všimneme si, že nejlepší služby pro doporučení jsou telefon, WiFi a kurýr. To je v souladu s tím, co jsme zjistili z distribucí údajů o spotřebě služby:

![Výstup modelu doporučení.](media/azure-machine-learning-model-output.png)

Celý [experiment s doporučením produktu je přístupný v Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrace vlastních modelů

Chcete-li tyto predikce použít v Customer Insights, musíte **exportovat** predikce spolu s ID zákazníků. [Exportujte je do stejného umístění úložiště Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs), do kterého exportujete zdrojová data. Prediktivní webová služba může být naplánována tak, aby pracovala pravidelně a aktualizovala bodování.

Data generovaná vlastním modelem lze použít k dalšímu rozšíření vašich zákaznických dat. Další informace viz [Vlastní modely strojového učení](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]