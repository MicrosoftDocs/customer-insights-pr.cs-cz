---
title: Obohacení firemních profilů o Dun & Bradstreet
description: Obecné informace o rozšíření třetí strany Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653699"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Obohacení firemních profilů o Dun & Bradstreet (preview)

Dun & Bradstreet poskytuje obchodní data, analýzy a statistiky pro podniky. Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností. Rozšíření obsahují atributy, jako je číslo DUNS, velikosti společnosti, místa, odvětví a další.

## <a name="prerequisites"></a>Předpoklady

Abyste mohli konfigurovat rozšíření Dun & Bradstreet, je třeba splnit následující předpoklady:

- Máte aktivní licenci [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Máte [sjednocené profily zákazníků](customer-profiles.md) pro společnosti.
- Dun & Bradstreet [připojení](connections.md) je nakonfigurováno správcem. Můžete si ho vytvořit, pokud máte oprávnění [správce](permissions.md#admin) a přihlašovací údaje z Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Nastavení vašeho projektu Dun & Bradstreet

Jako licencovaný uživatel Dun & Bradstreet můžete nastavit projekt v [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Připojte se k [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Chcete-li získat přihlašovací údaje, [obnovte své heslo](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Stáhněte [náš soubor šablony csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), která se použije k mapování polí cílové skupiny statistik na odpovídající pole Dun & Bradstreet. 

1. Nahrajte soubor v kroku **Nahrajte data** prostředí tvorby projektů Dun & Bradstreet. 

1. Vyberte vodorovné tečky pod příslušným **zdrojem** v nově vytvořeném projektu Dun & Bradstreet a zobrazte dostupné možnosti.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Snímek obrazovky teček v projektu Dun & Bradstreet.":::

1. Vybrat **Získejte podrobnosti o S3**. Uložte tyto informace na bezpečném místě. Budete je potřebovat [pro nastavení připojení pro rozšíření](#configure-a-connection-for-dun--bradstreet) v přehledech cílových skupin. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Snímek obrazovky výběru informací s3 v projektu Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**.

1. Vyberte **Rozšířit moje data** na dlaždici Dun & Bradstreet a vyberte **Začít**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Snímek obrazovky dlaždice Dun & Bradstreet.":::

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit připojení. Vyberte **Přidat připojení** a vyberte **Dun & Bradstreet**. 

1. Vyberte **Připojte se k Dun & Bradstreet** pro potvrzení připojení.

1. Vyberte **Další** a zvolte **Sadu zákaznických dat**, kterou chcete rozšířit o data společnosti od společnosti Dun & Bradstreet. Můžete vybrat entitu **Zákazník** a rozšířit všechny profily vašich zákazníků, nebo vyberte entitu segmentu a rozšiřte pouze sjednocené profily zákazníků obsažené v tomto segmentu.

1. Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů se používají k hledání odpovídajících dat společnosti od Dun & Bradstreet. Vyžadována jsou pole **Číslo DUNS** nebo **Název společnosti** a **Země**. Pole země podporuje [dvou nebo třípísmenné kódy zemí](https://www.iso.org/iso-3166-country-codes.html), název země v angličtině, název země v rodném jazyce a telefonní předvolbu. Některé běžné varianty zemí zahrnují:

   * USA: Spojené státy americké, Spojené státy, USA, Amerika.
   * CA: Kanada.
   * GB: Spojené království, UK, Velká Británie, GB, Spojené království Velké Británie a Severního Irska, Spojené království Velké Británie.
   * AU: Austrálie, Australské společenství.
   * FR: Francie, Francouzská republika
   * DE: Německo, Německý, Deutschland, Allemagne, Spolková republika Německo, Německá republika.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel mapování polí Dun & Bradstreet.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte název rozšíření a po přezkoumání vašich voleb vyberte **Uložit rozšíření**.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Nakonfigurujte připojení pro Dun & Bradstreet 

Abyste mohli konfigurovat propojení, musíte být správce. Vyberte příkaz **Přidat připojení** při konfiguraci rozšíření *nebo* přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici Dun & Bradstreet.

1. Vyberte **Začínáme**. 

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Poskytněte platné přihlašovací údaje Dun & Bradstreet a podrobnosti o projektu Dun & Bradstreet *Region, Drop folder path a Drop folder name*. [Tyto informace získáte](#setting-up-your-dun--bradstreet-project) z projektu Dun & Bradstreet.

1. Zkontrolujte a poskytněte svůj souhlas s **ochranou osobních údajů a dodržováním předpisů** výběrem **souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Stránka konfigurace připojení Dun & Bradstreet":::

## <a name="enrichment-results"></a>Výsledky rozšíření

Po aktualizaci rozšíření si můžete prohlédnout nově rozšířená firemní data v části [Moje rozšíření](enrichment-hub.md). Najdete čas poslední aktualizace a počet rozšířených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat do Dun & Bradstreet, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že Dun & Bradstreet splňuje veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](includes/footer-banner.md)]
