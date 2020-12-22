---
title: Připojení dat Common Data Model k účtu Azure Data Lake
description: Práce s daty Common Data Model pomocí Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643450"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Připojení ke složce Common Data Model prostřednictvím účtu Azure Data Lake

Tento článek poskytuje informace, jak ingestovat data ze složky Common Data Model pomocí vašeho účtu Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Důležitá poznámka

- Data v účtu Azure Data Lake musí odpovídat standardu Common Data Model. V současné době nejsou podporovány jiné formáty.

- Ingestace dat podporuje exkluzivně účty úložiště Azure Data Lake *Gen2*. K ingestaci dat nemůžete používat účty úložiště Azure Data Lake Gen1.

- Chcete-li provést ověření pomocí instančního objektu Azure, ujistěte se, že je nakonfigurován ve vašem klientovi. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md).

- Účet úložiště Azure Data Lake, ke kterému se chcete připojit a ingestovat data, musí být ve stejné oblasti Azure jako prostředí Dynamics 365 Customer Insights. Připojení ke složce Common Data Model z datového jezera v jiné oblasti Azure není podporováno. Chcete-li znát svoji oblast prostředí Azure, přejděte na **Správce** > **Systém** > **O produktu** v přehledech cílové skupiny.

- Data uložená ve službách online mohou být uložena v jiném umístění, než kde jsou zpracovávána nebo uložena v Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Připojit se ke složce modelu Common Data Model

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Připojit se ke složce modelu Common Data Model**, zadejte **Název** pro zdroj dat a vyberte **Další**.

1. Můžete si vybrat mezi použitím možnosti založené na prostředku a možnosti založené na předplatném ověřování. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Zadejte informace o **Kontejneru** a vyberte **Další**.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno pro zadání podrobností o připojení pro Azure Data Lake](media/enter-new-storage-details.png)

1. V dialogovém okně **Vybrat složku modelu Common Data Model** vyberte soubor model.json, ze kterého chcete importovat data, a vyberte **Další**.
   > [!NOTE]
   > Žádný soubor model.json přidružený k jinému zdroj dat v prostředí se v seznamu nezobrazí.

1. Ve vybraném souboru model.json získáte seznam dostupných entit. Můžete zkontrolovat seznam dostupných entit, vybrat z něho a vybrat **Uložit**. Všechny vybrané entity budou ingestovány z nového zdroje dat.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno zobrazující seznam entit ze souboru model.json](media/review-entities.png)

8. Označte, pro které datové entity chcete povolit profilování dat a vyberte **Uložit**. Profilování dat umožňuje analýzy a další funkce. Můžete vybrat celou entitu, čímž vyberete všechny atributy z entity, nebo můžete vybrat jen některé atributy dle vaší preference. Ve výchozím nastavení není pro profilování dat povolena žádná entita.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno zobrazující profilování dat](media/dataprofiling-entities.png)

9. Po uložení vašich výběrů se otevře stránka **Zdroje dat**. Nyní byste měli vidět připojení ke složce Common Data Model jako zdroj dat.

> [!NOTE]
> Soubor model.json lze přidružit pouze k jednomu zdroji dat ve stejném prostředí. Stejný soubor model.json však lze použít pro zdroje dat ve více prostředích.

## <a name="edit-a-common-data-model-folder-data-source"></a>Úprava zdroje dat složky Common Data Model

Můžete aktualizovat přístupový klíč pro účet úložiště obsahující složku Common Data Model. Můžete také změnit soubor model.json. Pokud se chcete připojit k jinému kontejneru účtu úložiště nebo změnit název účtu, [vytvořte nové připojení zdroje dat](#connect-to-a-common-data-model-folder).

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vedle zdroje dat, který chcete aktualizovat, vyberte tři tečky.

3. V seznamu vyberte volbu **Upravit**.

4. Volitelně aktualizujte **Přístupový klíč** a vyberte **Další**.

   ![Dialog pro úpravu a aktualizaci přístupového klíče pro existující zdroj dat](media/edit-access-key.png)

5. Volitelně můžete provést aktualizaci z připojení klíče účtu do připojení založeného na prostředcích nebo předplatném. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.
   > [!div class="mx-imgBorder"]
   > ![Dialogové okno pro zadání podrobností o připojení pro Azure Data Lake](media/enter-existing-storage-details.png)

6. Volitelně vyberte jiný soubor model.json s jinou sadou entit z kontejneru.

7. Volitelně můžete vybrat další entity, které chcete ingestovat. Pokud již neexistují žádné závislosti, můžete také odebrat všechny již vybrané entity.

   > [!IMPORTANT]
   > Pokud existují závislosti na existujícím souboru model.json a sadě entit, zobrazí se chybová zpráva a nemůžete vybrat jiný soubor model.json. Před změnou souboru model.json odeberte tyto závislosti nebo vytvořte nový zdroj dat se souborem model.json, který chcete použít, abyste se vyhnuli odstranění závislostí.

8. Volitelně můžete vybrat další atributy nebo entity a povolit profilování dat, nebo deaktivovat již vybrané.   
