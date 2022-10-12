---
title: Připojte se k datům ve spravovaném datovém jezeru Microsoft Dataverse
description: Importovat data ze spravovaného datového jezera Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609786"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Připojte se k datům ve spravovaném datovém jezeru Microsoft Dataverse

Uživatelé Microsoft Dataverse se mohou rychle připojit k analytickým entitám v jezeře spravovaném Microsoft Dataverse. Pouze jeden zdroj dat prostředí může současně používat totéž spravované jezero Dataverse.

> [!NOTE]
> Musíte být správcem organizace Dataverse, abyste mohli pokračovat a zobrazit seznam entit dostupných ve spravovaném jezeře.

## <a name="prerequisites"></a>Předpoklady

- Data uložená v online službách, například Azure Data Lake Storage, mohou být uloženy na jiném místě, než kde jsou zpracovávána nebo ukládána data Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center](https://www.microsoft.com/trust-center).

- Viditelné jsou pouze entity Dataverse se zapnutým [sledováním změn](/power-platform/admin/enable-change-tracking-control-data-synchronization). Tyto entity lze exportovat do datového jezera spravovaného pomocí Dataverse a použít v Customer Insights. Předpřipravené tabulky Dataverse mají ve výchozím nastavení povoleno sledování změn. U vlastních tabulek musíte sledování změn zapnout. Chcete-li zkontrolovat, zda je u tabulky Dataverse povoleno sledování změn, přejděte na [Power Apps](https://make.powerapps.com) > **Data** > **Tabulky**. Vyhledejte tabulku, která vás zajímá, a vyberte ji. Jděte na **Nastavení** > **Upřesnit možnosti** a zkontrolujte nastavení **Sledovat změny**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Připojení k datovému jezeru spravovaném pomocí Dataverse

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte možnost **Microsoft Dataverse**.

1. Zadejte **Název** zdroje dat a volitelně **Popis**.

1. Poskytněte **Adresu serveru** pro organizaci Dataverse a vyberte **Přihlásit se**.

1. Z dostupného seznamu vyberte tabulky, které chcete ingestovat jako entity do Customer Insights.

   > [!NOTE]
   > Pokud jsou některé tabulky již vybrány, mohou je používat jiné aplikace Dynamics 365 (například Dynamics 365 Sales Insights nebo Customer Service Insights). Tento výběr nelze změnit. Tyto tabulky budou k dispozici jako entity po vytvoření zdroje dat.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogové okno zobrazující seznam entit v prostředí Dataverse.":::

1. Uložením výběru spustíte synchronizaci vybraných tabulek Dataverse. Nově přidané připojení najdete na stránce **Zdroje dat**. Bude ve frontě k aktualizaci a zobrazí počet entit jako 0, dokud nebudou synchronizovány všechny vybrané tabulky.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce [**Entity**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Úprava zdroje dat datového jezera spravovaného pomocí Dataverse

Výběr entit můžete upravit až po vytvoření zdroje dat. Například pokud byly přidány další entity do Dataverse a chcete je také importovat.
Chcete -li se připojit k jinému datovému jezeru Dataverse, [vytvořte nový zdroj dat](#connect-to-a-dataverse-managed-lake).

1. Přejděte na **Data** > **Zdroje dat**.

1. Vedle zdroje dat, který chcete aktualizovat, vyberte **Upravit**.

1. Vyberte další entity z dostupného seznamu entit.

1. Klikněte na **Uložit** pro použití změny a návrat na stránku **Zdroje dat**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Běžné důvody chyb příjmu nebo poškozených dat

Následující kontroly běží na přijatých datech, aby odhalily poškozené záznamy:

- Hodnota pole se neshoduje s datovým typem jeho sloupce.
- Pole obsahují znaky, které způsobují, že sloupce neodpovídají očekávanému schématu. Například: nesprávně formátované uvozovky, neuzavřené uvozovky nebo znaky nového řádku.
- Pokud existují sloupce datetime/date/datetimeoffset, je třeba jejich formát zadat v modelu, pokud se neřídí standardním formátem ISO.

### <a name="schema-or-data-type-mismatch"></a>Neshoda schématu nebo datového typu

Pokud data neodpovídají schématu, jsou záznamy klasifikovány jako poškozené. Opravte zdrojová data nebo schéma a znovu je zpracujte.

### <a name="datetime-fields-in-the-wrong-format"></a>Pole data a času v nesprávném formátu

Pole data a času v entitě nejsou ve formátu ISO nebo en-US. Výchozí formát data a času v Customer Insights je formát en-US. Všechna pole data a času v entitě musí být ve stejném formátu. Customer Insights podporuje další formáty za předpokladu, že anotace nebo vlastnosti jsou vytvořeny na úrovni zdroje nebo entity v modelu nebo manifest.json. Příklad: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  V souboru manifest.json lze formát data a času zadat na úrovni entity nebo na úrovni atributu. Na úrovni entity použijte „exhibitsTraits“ v entitě v *.manifest.cdm.json k definování formátu data a času. Na úrovni atributu použijte „appliedTraits“ v atributu v entityname.cdm.json.

**Manifest.json na úrovni entity**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json na úrovni atributu**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
