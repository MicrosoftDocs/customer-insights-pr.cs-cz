---
title: Připojení dat Common Data Model k účtu Azure Data Lake
description: Práce s daty Common Data Model pomocí Azure Data Lake Storage.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833348"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Připojení ke složce Common Data Model prostřednictvím účtu Azure Data Lake

Tento článek poskytuje informace o tom, jak ingestovat data do Dynamics 365 Customer Insights ze složky Common Data Model pomocí vašeho účtu Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Důležitá poznámka

- Data v účtu Azure Data Lake musí odpovídat standardu Common Data Model. V současné době nejsou podporovány jiné formáty.

- Ingestace dat podporuje exkluzivně účty úložiště Azure Data Lake *Gen2*. K ingestaci dat nemůžete používat účty úložiště Azure Data Lake Gen1.

- Účet úložiště Azure Data Lake Storage musí mít [povolenou funkci Hierarchický prostor názvů](/azure/storage/blobs/data-lake-storage-namespace).

- Chcete-li provést ověření pomocí instančního objektu Azure, ujistěte se, že je nakonfigurován ve vašem klientovi. Více informací viz [Připojení k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md).

- Účet úložiště Azure Data Lake, ke kterému se chcete připojit a ingestovat data, musí být ve stejné oblasti Azure jako prostředí Dynamics 365 Customer Insights. Připojení ke složce Common Data Model z datového jezera v jiné oblasti Azure není podporováno. Chcete-li znát oblast prostředí Azure, přejděte na **Admin** > **Systém** > **O produktu** v Customer Insights.

- Data uložená ve službách online mohou být uložena v jiném umístění, než kde jsou zpracovávána nebo uložena v Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Připojit se ke složce modelu Common Data Model

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Azure Data Lake Storage**, vložte **Název** zdroje dat a poté vyberte **Další**.

   - Pokud budete vyzváni, vyberte jednu z ukázkových datových sad, které se týkají vašeho odvětví, a poté vyberte **Další**.

1. Můžete si vybrat mezi použitím možnosti založené na prostředku a možnosti založené na předplatném ověřování. Více informací viz [Připojení k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md). Zadejte **Adresu serveru**, vyberte **Přihlásit se** a poté vyberte **Další**.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno pro zadání nových podrobností o připojení pro Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Potřebujete jednu z následujících rolí buď ke kontejneru na účtu úložiště a vytvoření zdroj dat:
   >
   >  - Čtenář dat objektu blob úložiště stačí ke čtení z účtu úložiště a příjmu dat do Customer Insights. 
   >  - Chcete-li soubory manifestu upravovat přímo v Customer Insights, jsou vyžadovány role přispěvatele nebo vlastníka dat objektů blob úložiště.

1. V dialogovém okně **Vybrat složku modelu Common Data Model** vyberte soubor model.json nebo manifest.json, ze kterého chcete importovat data, a vyberte **Další**.
   > [!NOTE]
   > Soubor model.json ani manifest.json přidružený k jinému zdroj dat v prostředí se v seznamu nezobrazí.

1. Ve vybraném souboru model.json nebo manifest.json uvidíte seznam dostupných entit. Projděte si jej, vyberte si z něj a zvolte **Uložit**. Všechny vybrané entity budou ingestovány z nového zdroje dat.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno zobrazující seznam entit ze souboru model.json.](media/review-entities.png)

1. Označte, pro které datové entity chcete povolit profilování dat, a poté vyberte **Uložit**. Profilování dat umožňuje analýzy a další funkce. Můžete vybrat celou entitu, čímž vyberete všechny atributy z entity, nebo můžete vybrat jen některé atributy dle vaší preference. Ve výchozím nastavení není pro profilování dat povolena žádná entita.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno zobrazující profilování dat.](media/dataprofiling-entities.png)

1. Po uložení vašich výběrů se otevře stránka **Zdroje dat**. Nyní byste měli vidět připojení ke složce Common Data Model jako zdroj dat.

> [!NOTE]
> Soubor model.json nebo manifest.json lze přidružit pouze k jednomu zdroji dat ve stejném prostředí. Stejný soubor model.json nebo manifest.json však lze použít pro zdroje dat ve více prostředích.

## <a name="edit-a-common-data-model-folder-data-source"></a>Úprava zdroje dat složky Common Data Model

Můžete aktualizovat přístupový klíč pro účet úložiště obsahující složku Common Data Model. Můžete také změnit soubor model.json nebo manifest.json. Pokud se chcete připojit k jinému kontejneru účtu úložiště nebo změnit název účtu, [vytvořte nové připojení zdroje dat](#connect-to-a-common-data-model-folder).

1. Přejděte na **Data** > **Zdroje dat**.

2. Vedle zdroj dat, který chcete aktualizovat, vyberte vertikální tři tečky (&vellip;).

3. V seznamu vyberte volbu **Upravit**.

4. Volitelně aktualizujte **Přístupový klíč** a vyberte **Další**.

   ![Dialog pro úpravu a aktualizaci přístupového klíče pro existující zdroj dat.](media/edit-access-key.png)

5. Volitelně můžete provést aktualizaci z připojení klíče účtu do připojení založeného na prostředcích nebo předplatném. Více informací viz [Připojení k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md). Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.
   > [!div class="mx-imgBorder"]

   > ![Dialogové okno pro zadání podrobností o připojení k existujícímu účtu úložiště Azure Data Lake.](media/enter-existing-storage-details.png)

6. Volitelně vyberte z kontejneru jiný soubor model.json nebo manifest.json s jinou sadou entit.

7. Volitelně můžete vybrat další entity, které chcete ingestovat. Pokud již neexistují žádné závislosti, můžete také odebrat všechny již vybrané entity.

   > [!IMPORTANT]
   > Pokud existují závislosti na existujícím souboru model.json nebo manifest.json a sadě entit, zobrazí se chybová zpráva a nelze vybrat jiný soubor model.json nebo manifest.json. Odeberte tyto závislosti před změnou souboru model.json nebo manifest.json nebo vytvořte nový zdroj dat se souborem model.json nebo manifest.json, který chcete použít, abyste nemuseli závislosti odebrat.

8. Volitelně můžete vybrat další atributy nebo entity a povolit profilování dat, nebo deaktivovat již vybrané.

[!INCLUDE [footer-include](includes/footer-banner.md)]