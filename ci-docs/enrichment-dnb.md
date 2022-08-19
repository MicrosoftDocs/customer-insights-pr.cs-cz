---
title: Obohacení firemních profilů o Dun & Bradstreet (Preview)
description: Obecné informace o rozšíření třetí strany Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237896"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Obohacení firemních profilů o Dun & Bradstreet (Preview)

Dun & Bradstreet poskytuje obchodní data, analýzy a statistiky pro podniky. Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností. Rozšíření obsahují atributy, jako je číslo DUNS, velikosti společnosti, místa, odvětví a další.

## <a name="prerequisites"></a>Předpoklady

- Aktivní licence [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Sjednocené profily zákazníků](customer-profiles.md) pro firmy.
- [Projekt](#set-up-your-dun--bradstreet-project) Dun & Bradstreet je nastaven.
- Dun & Bradstreet [připojení](connections.md) je [nakonfigurováno](#configure-a-connection-for-dun--bradstreet) správcem.

## <a name="set-up-your-dun--bradstreet-project"></a>Nastavení projektu Dun & Bradstreet

Jako licencovaný uživatel Dun & Bradstreet můžete nastavit projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Připojte se k [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Chcete-li získat přihlašovací údaje, [obnovte své heslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Stáhněte [náš soubor šablony csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), která se použije k mapování polí cílové Customer Insights na odpovídající pole Dun & Bradstreet.

1. Nahrajte soubor v kroku **Nahrajte data** prostředí tvorby projektů Dun & Bradstreet.

1. Vyberte vodorovné tečky pod příslušným **zdrojem** v nově vytvořeném projektu Dun & Bradstreet a zobrazte dostupné možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snímek obrazovky teček v projektu Dun & Bradstreet.":::

1. Vybrat **Získejte podrobnosti o S3**. Uložte tyto informace na bezpečném místě. Budete je potřebovat [pro nastavení připojení pro rozšíření](#configure-a-connection-for-dun--bradstreet) v přehledech Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snímek obrazovky výběru informací s3 v projektu Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Nakonfigurujte připojení pro Dun & Bradstreet

Musíte být [správce](permissions.md#admin) v Customer Insights a mít přihlašovací údaje z Dun & Bradstreet Connect.

1. Vyberte příkaz **Přidat připojení** při konfiguraci rozšíření nebo přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici Dun & Bradstreet.

1. Zadejte název připojení.

1. Poskytněte platné přihlašovací údaje Dun & Bradstreet a podrobnosti o projektu Dun & Bradstreet *Region, Drop folder path a Drop folder name*. [Tyto informace získáte](#set-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stránka konfigurace připojení Dun & Bradstreet":::

## <a name="supported-countries-or-regions"></a>Podporované země nebo regiony

V současné době podporujeme následující možnosti země/oblasti: Kanada (angličtina) nebo Spojené státy americké (angličtina).

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte **Rozšířit moje data** v **Data společnosti** z dlaždice Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snímek obrazovky dlaždice Dun & Bradstreet.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení a potvrďte. Pokud není k dispozici propojení , kontaktujte správce.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o data společnosti z Dun & Bradstreet. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro porovnávání dat společnosti z Dun & Bradstreet. Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**.

1. Vyberte **Další**.

1. Namapujte pole vaší společnosti na firemní data od společnosti Dun & Bradstreet. Vyžadována jsou pole **Číslo DUNS** nebo **Název společnosti** a **Země**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel mapování polí Dun & Bradstreet.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
