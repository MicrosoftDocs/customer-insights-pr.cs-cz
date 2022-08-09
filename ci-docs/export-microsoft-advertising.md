---
title: Export segmentů do služby Microsoft Advertising (preview)
description: Naučte se konfigurovat připojení a export do služby Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196524"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Export segmentů do služby Microsoft Advertising (preview)

Exportujte segmenty Customer Insights do služby Microsoft Advertising a vytvořte cílové skupiny shody zákazníků. Tyto cílové skupiny používejte pro své reklamní kampaně.

## <a name="prerequisites"></a>Předpoklady

- [Účet Microsoft Advertising](https://ads.microsoft.com/) a odpovídající přihlašovací údaje správce.
- ID zákazníka a ID účtu Microsoft Advertising. Vyhledejte ID zákazníka (`cid`) a ID účtu (`aid`) v parametrech adresy URL, když jste přihlášeni do služby Microsoft Advertising.
- Přijali jste podmínky použití řešení Customer Match.
- [Nakonfigurované segmenty](segments.md) v Customer Insights.
- Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="known-limitations"></a>Známá omezení

- Až 500 000 zákaznických profilů na jeden export do Microsoft Advertising, který může trvat až 10 minut.
- Pouze segmenty.

## <a name="set-up-connection-to-microsoft-advertising"></a>Nastavení propojení se službou Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Microsoft Advertising**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Výchozí jsou správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **ID zákazníka Microsoft Advertising**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Volbou **Připojit** inicializujte připojení ke službě Braze.

1. Vyberte **Ověření pomocí Microsoft Advertising** a zadejte své přihlašovací údaje pro Microsoft Advertising.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části Microsoft Advertising. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte segmenty, které chcete exportovat. Cílové skupiny shody zákazníků ve službě Microsoft Advertising se automaticky vytvářejí s názvem segmentů vybraných pro export. Výsledkem každého segmentu bude samostatná cílová skupina shody zákazníků.

1. Vložte své **ID zákazníka a ID účtu Microsoft Advertising**.

1. V části **Párování dat** v poli **E-mail** vyberte pole s e-mailovou adresou zákazníka.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
