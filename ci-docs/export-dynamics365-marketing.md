---
title: Export dat Customer Insights do Dynamics 365 Marketing
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645711"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Použití segmentů v Dynamics 365 Marketing (Preview)



Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí Dynamics 365 Marketing. Další informace získáte v tématu [Použití segmentů z Dynamics 365 Customer Insights s Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Pokud používáte nové funkce Dynamics 365 Marketing pro orchestraci cesty zákazníka v reálném čase v organizaci Dataverse, nemusíte vytvářet standardní export do Dynamics 365 Marketing. Kontakty a segmenty ze Customer Insights jsou dostupné přímo v Dynamics 365 Marketing po propojení Marketing a Customer Insights. Před odstraněním existujících exportů si prostudujte dokumentaci o tom, [jak propojit Customer Insights a orchestraci cesty zákazníka Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Předpoklad pro propojení

- Než budete moci exportovat segment z Customer Insights do aplikace Marketing, musí se v Dynamics 365 Marketing nacházet záznamy kontaktu. Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Marketing pomocí Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Export segmentů z Customer Insights do Marketing nevytvoří nové záznamy kontaktů v instancích Marketing. Záznamy kontaktů z Marketingu musí být zpracovány v Customer Insights a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

## <a name="set-up-connection-to-marketing"></a>Nastavení propojení s aplikací Marketing

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Dynamics 365 Marketing** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.

1. Namapujte pole ID kontaktu v entitě Zákazník na ID kontaktu Dynamics 365.

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **Propojení pro export** vyberte propojení v části Dynamics 365 Marketing. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Vyberte jeden nebo více segmentů.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
