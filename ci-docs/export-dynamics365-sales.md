---
title: Export dat Customer Insights do Dynamics 365 Sales
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645787"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Použití segmentů v Dynamics 365 Sales (Preview)



Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.

## <a name="known-limitations"></a>Známá omezení

- Exporty do Dynamics 365 Sales jsou omezeny na 100 000 členů na segment.
- Dokončení exportů segmentů do Dynamics 365 Sales může trvat až 3 hodiny. 

## <a name="prerequisite-for-connection"></a>Předpoklad pro připojení

1. Než budete moci exportovat segment z Customer Insights do aplikace Sales, musí se v Dynamics 365 Sales nacházet záznamy kontaktu. Přečtěte si více o ingestování kontaktů z [Dynamics 365 Sales s využitím Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Export segmentů z Customer Insights do Sales nevytvoří nové záznamy kontaktů v instancích Sales. Záznamy kontaktů ze Sales musí být zpracovány v Customer Insights a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

## <a name="set-up-the-connection-to-sales"></a>Nastavení propojení se Sales

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Dynamics 365 Sales** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.

1. Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části Dynamics 365 Sales. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte jeden nebo více segmentů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
