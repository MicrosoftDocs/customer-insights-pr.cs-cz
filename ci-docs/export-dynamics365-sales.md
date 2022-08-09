---
title: Export segmentů do Dynamics 365 Sales (Preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195973"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Export segmentů do Dynamics 365 Sales (Preview)

Aplikace Dynamics 365 Sales umožňuje na základě zákaznických dat vytvářet marketingové seznamy, sledovat pracovní postupy a rozesílat propagační akce.

## <a name="prerequisites"></a>Předpoklady

Než budete moci exportovat segment z Customer Insights do aplikace Sales, musí se v Dynamics 365 Sales nacházet záznamy kontaktu. Přečtěte si více o ingestování kontaktů z [Dynamics 365 Sales s využitím Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Export segmentů z Customer Insights do Sales nevytvoří nové záznamy kontaktů v instancích Sales. Záznamy kontaktů ze Sales musí být zpracovány v Customer Insights a použity jako zdroj dat. Než je možné segmenty exportovat, rovněž je třeba záznamy kontaktů zahrnout do sjednocené entity zákazníka, aby bylo možné mapovat ID zákazníků na ID kontaktů.

## <a name="known-limitations"></a>Známá omezení

Exporty do Dynamics 365 Sales jsou omezeny na 100 000 na jeden segment, což může trvat až 3 hodiny.

## <a name="set-up-connection-to-sales"></a>Nastavení propojení se Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Dynamics 365 Sales**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte adresu URL Sales vaší organizace do pole **Adresa serveru**.

1. V sekci **Účet správce serveru** vyberte **Přihlásit se** a vyberte účet Dynamics 365 Sales.

1. Namapujte pole ID zákazníka na ID kontaktu Dynamics 365.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Dynamics 365 Sales. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte pole ID kontaktu v entitě Zákazník, které odpovídá ID kontaktu Dynamics 365.

1. Vyberte segmenty, které chcete exportovat.

1. Zvolte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
