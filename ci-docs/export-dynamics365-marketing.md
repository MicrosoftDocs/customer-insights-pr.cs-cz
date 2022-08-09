---
title: Export segmentů do Dynamics 365 Marketing (Preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196616"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Export segmentů do Dynamics 365 Marketing (Preview)

Použití [segmentů](segments.md) pro generování kampaní a kontaktování konkrétní skupiny zákazníků pomocí [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Pokud používáte nové funkce Dynamics 365 Marketing pro orchestraci cesty zákazníka v reálném čase v organizaci Dataverse, nemusíte vytvářet standardní export do Dynamics 365 Marketing. Kontakty a segmenty ze Customer Insights jsou dostupné přímo v Dynamics 365 Marketing po propojení Marketing a Customer Insights. Před odstraněním existujících exportů si prostudujte dokumentaci o tom, [jak propojit Customer Insights a orchestraci cesty zákazníka Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Požadavek

Než budete moci exportovat segment z Customer Insights do aplikace Marketing, musí se v Dynamics 365 Marketing nacházet záznamy kontaktu. Přečtěte si, jak ingestovat kontakty v [Dynamics 365 Marketing pomocí Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Export segmentů z Customer Insights do Marketing nevytvoří nové záznamy kontaktů v instancích Marketing. Záznamy kontaktů z Marketingu musí být zpracovány v Customer Insights a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

## <a name="set-up-connection-to-marketing"></a>Nastavení propojení s aplikací Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Dynamics 365 Marketing**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte marketingovou adresu URL vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Marketing.

1. Namapujte pole ID kontaktu v entitě Zákazník na ID kontaktu Dynamics 365.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Propojení pro export** vyberte propojení v části Dynamics 365 Marketing. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte pole ID kontaktu v entitě Zákazník, které odpovídá ID kontaktu Dynamics 365.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
