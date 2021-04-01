---
title: Připojení k entitám ve spravovaném jezeře Common Data Service
description: Importovat data ze spravovaného datového jezera Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596951"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Připojte se k datům ve spravovaném datovém jezeru Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článek poskytuje informace o tom, jak se stávající zákazníci Dynamics 365 mohou rychle připojit ke svým analytickým entitám ve spravovaném jezeru Common Data Service. Musíte být administrátorem v organizaci Common Data Service, abyste se mohli podívat na seznam entit dostupných ve spravovaném jezeře.

## <a name="important-considerations"></a>Důležitá poznámka

Data uložená v online službách, například Azure Data Lake Storage, mohou být uloženy na jiném místě, než kde jsou zpracovávána nebo ukládána data Dynamics 365 Customer Insights. Importem nebo připojením k datům uloženým v online službách souhlasíte s tím, že data lze přenášet a ukládat pomocí Dynamics 365 Customer Insights. [Další informace naleznete v Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Připojení k datovému jezeru spravovaném pomocí Common Data Service

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vyberte **Přidat zdroj dat**.

3. Vyberte **Připojit se k Common Data Service** a vyberte **Další**.

4. Zadejte **Název** zdroje dat vyberte **Další**. Pokyny pro tvoření názvů: 
   - Začněte písmenem.
   - Používejte pouze písmena a číslice. Nejsou povoleny speciální znaky a mezery.
   - Název musí mít 3 až 64 znaků.

5. Vyplňte pole **Adresa serveru** pro svou organizaci Common Data Service a vyberte **Přihlásit se**.

   > [!div class="mx-imgBorder"]
   > ![Dialogové okno pro zadání adresy serveru Common Data Service](media/enter-CDS-org-details.png)

6. Vyberte entity, které chcete ingestovat z dostupného seznamu.    

   > [!NOTE]
   > Pokud jsou některé entity již vybrány, mohou být použity jinými aplikacemi Dynamics 365 (jako například Dynamics 365 Sales Insights nebo Customer Service Insights). Tento výběr nelze změnit. Tyto entity budou k dispozici, jakmile se vytvoří zdroj dat.

   > [!div class="mx-imgBorder"]
   > ![Dialogové okno zobrazující seznam entit v organizaci Common Data Service](media/select-analytical-entities.png)

7. Uložte výběr a začněte synchronizovat vybrané entity se spravovaným jezerem Common Data Service. Nově přidané připojení najdete na stránce **Zdroje dat**. Bude zařazeno do fronty pro aktualizaci a zobrazí počet entit jako 0, dokud nebudou všechny entity synchronizovány.

Pouze jeden zdroj dat prostředí může současně používat totéž spravované jezero Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Úprava zdroje dat datového jezera spravovaného pomocí Common Data Service

Výběr entit můžete upravit až po vytvoření zdroje dat. Například pokud byly přidány další entity do Common Data Service a chcete je také importovat.    
Pokud se chcete připojit k jiné instanci Common Data Service, [vytvořte nový zdroj dat](#connect-to-a-common-data-service-managed-lake).

1. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2. Vedle zdroje dat, který chcete aktualizovat, vyberte tři tečky.

3. V seznamu vyberte volbu **Upravit**.

4. Vyberte další entity z dostupného seznamu entit a vyberte **Uložit**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]