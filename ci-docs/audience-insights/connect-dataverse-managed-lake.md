---
title: Připojení k tabulkám v Microsoft Dataverse
description: Importovat data ze spravovaného datového jezera Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692566"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Připojte se k datům ve spravovaném datovém jezeru Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článek poskytuje informace o tom, jak se mohou uživatelé Dataverse rychle připojit ke svým analytickým entitám ve spravovaném jezeře Dataverse. Musíte být administrátorem v organizaci Dataverse, abyste se mohli podívat na seznam entit dostupných ve spravovaném jezeře.

## <a name="important-considerations"></a>Důležitá poznámka

Data uložená v online službách, například Azure Data Lake Storage, mohou být uloženy na jiném místě, než kde jsou zpracovávána nebo ukládána data Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Připojení k datovému jezeru spravovaném pomocí Dataverse

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte **Přidat zdroj dat**.

3. Vyberte **Připojit ke spravovanému jezeru Microsoft Dataverse** a pak vyberte **Další**.

4. Zadejte **Název** zdroje dat vyberte **Další**. Pokyny pro tvoření názvů: 
   - Začněte písmenem.
   - Používejte pouze písmena a číslice. Nejsou povoleny speciální znaky a mezery.
   - Název musí mít 3 až 64 znaků.

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