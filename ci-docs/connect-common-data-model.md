---
title: Připojení ke složce Common Data Model prostřednictvím účtu Azure Data Lake
description: Práce s daty Common Data Model pomocí Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: e071bf9364b44a92d81c9ff2269ff4e8654010aa
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206991"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Připojení k datům v Azure Data Lake Storageu

Příjem dat do Dynamics 365 Customer Insights pomocí účtu Azure Data Lake Storage Gen2. Příjem dat může být úplný nebo přírůstkový.

## <a name="prerequisites"></a>Předpoklady

- Příjem dat podporuje výhradně účty Azure Data Lake Storage *Gen2*. K přijímání dat nemůžete používat účty úložiště Data Lake Gen1.

- Účet Azure Data Lake Storage musí mít [povolený hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace). Data musí být uložena v hierarchickém formátu složky, který definuje kořenovou složku a má podsložky pro každou entitu. Podsložky mohou mít úplné datové složky nebo přírůstkové datové složky.

- Chcete-li provést ověření pomocí instančního objektu Azure, ujistěte se, že je nakonfigurován ve vašem klientovi. Více informací viz [Připojení k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md).

- Úložiště Azure Data Lake Storage, ze kterého se chcete připojit a přijímat data, musí být ve stejné oblasti Azure jako prostředí Dynamics 365 Customer Insights. Připojení ke složce Common Data Model z datového jezera v jiné oblasti Azure není podporováno. Chcete-li znát oblast prostředí Azure, přejděte na **Admin** > **Systém** > **O produktu** v Customer Insights.

- Data uložená ve službách online mohou být uložena v jiném umístění, než kde jsou zpracovávána nebo uložena v Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center](https://www.microsoft.com/trust-center).

- Instanční objekt Customer Insights musí mít jednu z následujících rolí, aby mohl přistupovat k účtu úložiště. Více informací viz [Udělení oprávnění instančnímu objektu služby pro přístup k účtu úložiště](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Čtenář dat objektů blob úložiště
  - Vlastník dat objektů blob úložiště
  - Přispěvatel dat objektů blob úložiště

- Data v úložišti Data Lake by se měla řídit standardem Common Data Model pro ukládání dat a mít společný manifest datového modelu, který bude reprezentovat schéma datových souborů (*.csv nebo *.parquet). Manifest musí obsahovat podrobnosti o entitách, jako jsou sloupce entit a datové typy a umístění datového souboru a typ souboru. Další informace viz [Manifest Common Data Model](/common-data-model/sdk/manifest). Pokud manifest není přítomen, uživatelé s oprávněním správce s přístupem vlastník dat objektu Storage Blob nebo přístup k datům objektu Storage Blob přispěvatel mohou definovat schéma při zpracování dat.

## <a name="connect-to-azure-data-lake-storage"></a>Připojení k Azure Data Lake Storage

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogové okno pro zadání podrobností o připojení pro Azure Data Lake" lightbox="media/data_sources_ADLS.png":::

1. Zadejte **Název** zdroje dat a volitelně **Popis**. Název jedinečně identifikuje zdroj dat a je odkazován v následných procesech a nelze jej změnit.

1. Vyberte jednu z následujících možností pro **Připojte své úložiště pomocí**. Více informací viz [Připojení Customer Insights k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md).

   - **Zdroj Azure**: Zadejte **ID zdroje**. Volitelně, pokud chcete přijmout data z účtu úložiště prostřednictvím Azure Private Link, vyberte **Povolit private Link**. Další informace popisuje článek [Privátní propojení](security-overview.md#private-links-tab).
   - **Předplatné Azure**: Vyberte **Předplatné** a pak **Skupina zdrojů** a **Účet úložiště**. Volitelně, pokud chcete přijmout data z účtu úložiště prostřednictvím Azure Private Link, vyberte **Povolit private Link**. Další informace popisuje článek [Privátní propojení](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Potřebujete jednu z následujících rolí buď ke kontejneru na účtu úložiště a vytvoření zdroj dat:
   >
   >  - Čtenář dat objektu blob úložiště stačí ke čtení z účtu úložiště a příjmu dat do Customer Insights. 
   >  - Chcete-li soubory manifestu upravovat přímo v Customer Insights, jsou vyžadovány role přispěvatele nebo vlastníka dat objektů blob úložiště.  
  
1. Vyberte název **Kontejneru**, který obsahuje data a schéma (soubor model.json nebo manifest.json), ze kterého chcete importovat data, a vyberte **Další**.
   > [!NOTE]
   > Soubor model.json ani manifest.json přidružený k jinému zdroj dat v prostředí se v seznamu nezobrazí. Stejný soubor model.json nebo manifest.json však lze použít pro zdroje dat ve více prostředích.

1. Chcete-li vytvořit nové schéma, přejděte na [Vytvořte nový soubor schématu](#create-a-new-schema-file).

1. Chcete-li použít existující schéma, přejděte do složky obsahující soubor model.json nebo manifest.cdm.json. Soubor můžete vyhledat v adresáři.

1. Vyberte soubor json a vyberte možnost **Další**. Zobrazí se seznam dostupných entit

   :::image type="content" source="media/review-entities.png" alt-text="Dialogové okno se seznamem entit k výběru":::

1. Vyberte entity, které chcete zahrnout.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogové okno zobrazující Vyžadováno pro primární klíč":::

   > [!TIP]
   > Chcete-li upravit entitu v rozhraní pro úpravy JSON, vyberte ji a poté vyberte **Upravit soubor schématu**. Udělejte potřebné změny a vyberte **Uložit**.

1. U vybraných entit, které vyžadují přírůstkové zpracování, se pod možností **Přírůstkové obnovení** zobrazuje **Požadováno**. Pro každou z těchto entit získáte informace v části [Konfigurace přírůstkové aktualizace pro zdroje dat Azure Data Lake](incremental-refresh-data-sources.md).

1. Pro vybrané entity, kde nebyl definován primární klíč, se v části **Primární klíč** zobrazuje **Požadované**. Pro každou z těchto entit:
   1. Vyberte **Požadované**. Zobrazí se panel **Upravit entitu**.
   1. Zvolte **Primární klíč**. Primární klíč je atribut jedinečný pro entitu. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Jako primární klíče jsou podporovány atributy typu String, Integer a GUID.
   1. Volitelně změňte vzor oddílu.
   1. Výběrem **Zavřít** uložte a zavřete panel.

1. Vyberte počet **atributů** pro každou zahrnutou entitu. Zobrazí se stránka **Spravovat atributy**.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogové okno pro výběr profilování dat.":::

   1. Vytvořte nové atributy, upravte nebo odstraňte existující atributy. Můžete změnit název, formát dat nebo přidat sémantický typ.
   1. Chcete-li povolit analýzu a další funkce, vyberte **Profilování dat** pro celou entitu nebo pro konkrétní atributy. Ve výchozím nastavení není pro profilování dat povolena žádná entita.
   1. Vyberte **Hotovo**.

1. Vyberte **Uložit**. Otevře se stránka **Zdroje dat** s novým zdrojem dat se stavem **Aktualizace**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce [**Entity**](entities.md).

### <a name="create-a-new-schema-file"></a>Vytvořte nový soubor schématu.

1. Vyberte **Nový soubor schématu**.

1. Zadejte název souboru a vyberte **Uložit**.

1. Vyberte **Nová entita**. Zobrazí se panel **Nová entita**.

1. Zadejte název entity a vyberte **Umístění datových souborů**.
   - **Více souborů .csv nebo .parquet**: Přejděte do kořenové složky, vyberte typ vzoru a zadejte výraz.
   - **Jeden soubor .csv nebo .parquet**: Přejděte na soubor .csv nebo .parquet a vyberte jej.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogové okno pro vytvoření nové entity se zvýrazněným umístěním datových souborů.":::

1. Vyberte **Uložit**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogové okno pro definování nebo automatické generování atributů.":::

1. Vyberte **definovat atributy** pro ruční přidání atributů nebo vyberte **automaticky je vygenerovat**. Chcete-li definovat atributy, zadejte název, vyberte formát dat a volitelný sémantický typ. Pro automaticky generované atributy:

   1. Po automatickém vygenerování atributů vyberte **Zkontrolovat atributy**. Zobrazí se stránka **Spravovat atributy**.

   1. Ujistěte se, že formát dat je pro každý atribut správný.

   1. Chcete-li povolit analýzu a další funkce, vyberte **Profilování dat** pro celou entitu nebo pro konkrétní atributy. Ve výchozím nastavení není pro profilování dat povolena žádná entita.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogové okno pro výběr profilování dat.":::

   1. Vyberte **Hotovo**. Zobrazí se stránka **Vybrané entity**.

1. Pokračujte v přidávání entit a atributů, pokud je to možné.

1. Po přidání všech entit vyberte **Zahrnout** k zahrnutí entit do zdroje dat příjmu.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogové okno zobrazující Vyžadováno pro primární klíč":::

1. U vybraných entit, které vyžadují přírůstkové zpracování, se pod možností **Přírůstkové obnovení** zobrazuje **Požadováno**. Pro každou z těchto entit získáte informace v části [Konfigurace přírůstkové aktualizace pro zdroje dat Azure Data Lake](incremental-refresh-data-sources.md).

1. Pro vybrané entity, kde nebyl definován primární klíč, se v části **Primární klíč** zobrazuje **Požadované**. Pro každou z těchto entit:
   1. Vyberte **Požadované**. Zobrazí se panel **Upravit entitu**.
   1. Zvolte **Primární klíč**. Primární klíč je atribut jedinečný pro entitu. Aby byl atribut platným primárním klíčem, nesmí obsahovat duplicitní hodnoty, chybějící hodnoty nebo hodnoty null. Jako primární klíče jsou podporovány atributy typu String, Integer a GUID.
   1. Volitelně změňte vzor oddílu.
   1. Výběrem **Zavřít** uložte a zavřete panel.

1. Vyberte **Uložit**. Otevře se stránka **Zdroje dat** s novým zdrojem dat se stavem **Aktualizace**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Načítání dat může nějakou dobu trvat. Po úspěšné aktualizaci lze přijatá data zkontrolovat na stránce [**Entity**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Úprava zdroje dat Azure Data Lake Storage

Můžete aktualizovat volbu *Připojte se k účtu úložiště pomocí*. Více informací viz [Připojení Customer Insights k účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure](connect-service-principal.md). Pokud se chcete připojit k jinému kontejneru účtu úložiště nebo změnit název účtu, [vytvořte nové připojení zdroje dat](#connect-to-azure-data-lake-storage).

1. Přejděte na **Data** > **Zdroje dat**.

1. Vedle zdroje dat, který chcete aktualizovat, vyberte **Upravit**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogové okno pro úpravu zdroje dat Azure Data Lake.":::

1. Změňte libovolné následující informace:

   - **Description**
   - **Připojte své úložiště pomocí** a informace o připojení. Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.
      > [!NOTE]
      > K účtu úložiště nebo kontejneru musí být přiřazena jedna z následujících rolí:
        > - Čtenář dat objektů blob úložiště
        > - Vlastník dat objektů blob úložiště
        > - Přispěvatel dat objektů blob úložiště

   - **Povolit Private Link** pokud chcete přijmout data z účtu úložiště prostřednictvím Azure Private Link. Další informace popisuje článek [Privátní propojení](security-overview.md#private-links-tab).

1. Vyberte **Další**.
1. Změňte jedno z následujících:
   - Přejděte do jiného souboru model.json nebo manifest.json s jinou sadou entit z kontejneru.
   - Chcete-li ke zpracování přidat další entity, vyberte **Nová entita**.
   - Chcete-li odstranit jakékoli již vybrané entity, pokud neexistují žádné závislosti, vyberte entitu a **Odstranit**.
      > [!IMPORTANT]
      > Pokud existují závislosti na existujícím souboru model.json nebo manifest.json a sadě entit, zobrazí se chybová zpráva a nelze vybrat jiný soubor model.json nebo manifest.json. Odeberte tyto závislosti před změnou souboru model.json nebo manifest.json nebo vytvořte nový zdroj dat se souborem model.json nebo manifest.json, který chcete použít, abyste nemuseli závislosti odebrat.
   - Chcete-li změnit umístění datového souboru nebo primární klíč, vyberte **Upravit**.
   - Chcete-li změnit data přírůstkového příjmu, viz [Konfigurace přírůstkové aktualizace pro zdroje dat Azure Data Lake](incremental-refresh-data-sources.md).
   - Jen změňte název entity tak, aby odpovídal názvu entity v souboru .json.

     > [!NOTE]
     > Název entity v Customer Insights vždy po zpracování ponechejte stejný jako název entity v souboru model.json nebo manifest.json. Customer Insights ověřuje všechny názvy entit podle souboru model.json nebo manifest.json během každé aktualizace systému. Pokud se změní název entity buď v řešení Customer Insights nebo mimo něj, dojde k chybě, protože Customer Insights nemůže najít nový název entity v souboru .json. Pokud byl název ingestované entity náhodně změněn, upravte jej v Customer Insights tak, aby odpovídal názvu v souboru .json.

1. Vyberte **Atributy** pro přidání nebo změnu atributů nebo povolení profilování dat. Pak vyberte **Hotovo**.

1. Klikněte na **Uložit** pro použití změny a návrat na stránku **Zdroje dat**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
