---
title: Připojení k tabulkám v Microsoft Dataverse
description: Importovat data ze spravovaného datového jezera Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
  - ci-dataverse
  - customerInsights
---

# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Připojte se k datům ve spravovaném datovém jezeru Microsoft Dataverse

Tento článek poskytuje informace, jak se uživatelé Dataverse mohou rychle připojit k analytickým entitám ve spravovaném jezeru Microsoft Dataverse. 

> [!NOTE]
> Musíte být správcem organizace Dataverse, abyste mohli pokračovat a zobrazit seznam entit dostupných ve spravovaném jezeře.

## <a name="important-considerations"></a>Důležitá poznámka

1. Data uložená v online službách, například Azure Data Lake Storage, mohou být uloženy na jiném místě, než kde jsou zpracovávána nebo ukládána data Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center](https://www.microsoft.com/trust-center).
2. Viditelné jsou pouze entity Dataverse se zapnutým [sledováním změn](/power-platform/admin/enable-change-tracking-control-data-synchronization). Tyto entity lze exportovat do datového jezera spravovaného pomocí Dataverse a použít v Customer Insights. Předpřipravené tabulky Dataverse mají ve výchozím nastavení povoleno sledování změn. U vlastních tabulek musíte sledování změn zapnout. Chcete-li zkontrolovat, zda je u tabulky Dataverse povoleno sledování změn, přejděte na [Power Apps](https://make.powerapps.com) > **Data** > **Tabulky**. Vyhledejte tabulku, která vás zajímá, a vyberte ji. Jděte na **Nastavení** > **Upřesnit možnosti** a zkontrolujte nastavení **Sledovat změny**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Připojení k datovému jezeru spravovaném pomocí Dataverse

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte **Přidat zdroj dat**.

3. Vyberte **Microsoft Dataverse** a pak **Další**.

4. Zadejte **Název** zdroje dat vyberte **Další**. 

5. Poskytněte **Adresu serveru** pro organizaci Dataverse a vyberte **Přihlásit se**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Obrazovka v kroku příjmu dat, kde uživatel může zadat adresu URL prostředí Dataverse.":::

6. Z dostupného seznamu vyberte tabulky, které chcete zpracovat jako entity pro přehledy cílové skupiny.    

   > [!NOTE]
   > Pokud jsou některé tabulky již vybrány, mohou je používat jiné aplikace Dynamics 365 (například Dynamics 365 Sales Insights nebo Customer Service Insights). Tento výběr nelze změnit. Tyto tabulky budou k dispozici jako entity po vytvoření zdroje dat.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogové okno zobrazující seznam entit v prostředí Dataverse.":::

7. Uložením výběru spustíte synchronizaci vybraných tabulek Dataverse. Nově přidané připojení najdete na stránce **Zdroje dat**. Bude ve frontě k aktualizaci a zobrazí počet entit jako 0, dokud nebudou synchronizovány všechny vybrané tabulky.

Pouze jeden zdroj dat prostředí může současně používat totéž spravované jezero Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Úprava zdroje dat datového jezera spravovaného pomocí Dataverse

Výběr entit můžete upravit až po vytvoření zdroje dat. Například pokud byly přidány další entity do Dataverse a chcete je také importovat.    
Chcete -li se připojit k jinému datovému jezeru Dataverse, [vytvořte nový zdroj dat](#connect-to-a-dataverse-managed-lake).

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vedle zdroje dat, který chcete aktualizovat, vyberte tři tečky.

3. V seznamu vyberte volbu **Upravit**.

4. Vyberte další entity z dostupného seznamu entit a vyberte **Uložit**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
