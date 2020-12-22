---
title: Instalace a konfigurace doplňku karty zákazníka
description: Instalace a konfigurace doplňku karty zákazníka pro Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644035"
---
# <a name="customer-card-add-in-preview"></a>Doplněk karty zákazníka (preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Získejte kompletní přehled o svých zákaznících přímo v aplikacích Dynamics 365. Prohlédněte si demografické údaje, statistiky a časové harmonogramy činností pomocí doplňku karty zákazníka.

## <a name="prerequisites"></a>Požadavky

- Aplikace Dynamics 365 (například Centrum prodeje nebo Centrum služeb zákazníkům) verze 9.0 a novější s povoleným sjednoceným rozhraním.
- Profily zákazníků [ingestované z aplikace Dynamics 365 pomocí Common Data Service](connect-power-query.md).
- Uživatelé doplňku karty zákazníka musí být [přidáni jako uživatelé](permissions.md) v přehledech cílové skupiny.
- [Konfigurované možnosti vyhledávání a filtrování](search-filter-index.md).
- Ovládací prvek demografických údajů: V jednotném profilu zákazníka jsou k dispozici demografická pole, například věk nebo pohlaví.
- Kontrola rozšíření: Vyžaduje aktivní [rozšíření](enrichment-hub.md) aplikované na profily zákazníků.
- Ovládací prvek analytických nástrojů: Vyžaduje data generovaná pomocí Azure Machine Learning ([predikce](predictions.md) nebo [vlastní modely](custom-models.md))
- Ovládací prvek měr: Vyžaduje [konfigurované míry](measures.md).
- Ovládací prvek časové osy: Vyžaduje [konfigurované aktivity](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalace doplňku karty zákazníka

Doplněk karty zákazníka je řešení pro aplikace pro zapojení zákazníků v Dynamics 365. Chcete-li nainstalovat řešení, přejděte na AppSource a vyhledejte **Kartu zákazníka Dynamics**. Vyberte [Doplněk karty zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získat**.

K instalaci řešení se možná budete muset přihlásit pomocí svých přihlašovacích údajů pro aplikaci Dynamics 365.

Instalace řešení do vašeho prostředí může nějakou dobu trvat.

## <a name="configure-the-customer-card-add-in"></a>Nakonfigurujte doplněk zákaznické karty

1. Jako správce přejděte na **Nastavení** v Dynamics 365 a vyberte **Řešení**.

1. Vyberte odkaz **Zobrazované jméno** řešení Doplněk karty zákazníka v **Dynamics 365 Customer Insights (preview)**.

   > [!div class="mx-imgBorder"]
   > ![Výběr zobrazovaného názvu](media/select-display-name.png "Výběr zobrazovaného názvu")

1. Vyberte **Přihlásit se** a zadejte přihlašovací údaje pro účet správce, pomocí kterého konfigurujete Customer Insights.

   > [!NOTE]
   > Zkontrolujte, zda blokování automaticky otevíraných oken prohlížeče neblokuje okno ověřování, když vyberete tlačítko **Přihlásit**.

1. Vyberte prostředí, ze které chcete načíst data.

1. Definujte, které pole se má mapovat na záznamy v aplikaci Dynamics 365.
   - Chcete-li mapovat kontakt, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity kontaktu.
   - Chcete-li mapovat obchodní vztah, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity obchodního vztahu.

   > [!div class="mx-imgBorder"]
   > ![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")

1. Chcete-li uložit nastavení, vyberte tlačítko **Uložit konfiguraci**.

1. Dále musíte v Dynamics 365 přiřadit role zabezpečení, aby si uživatelé mohli přizpůsobit a vidět zákaznickou kartu. V aplikaci Dynamics 365 přejděte do části **Nastavení** > **Zabezpečení** > **Uživatelé**. Vyberte uživatele, kterým chcete upravit uživatelské role, a vyberte **Správa rolí**.

1. Přiřaďte roli **Úpravce karty Customer Insights** uživatelům, kteří přizpůsobí obsah zobrazený na kartě pro celou organizaci.

## <a name="add-customer-card-controls-to-forms"></a>Přidání ovládacích prvků karty zákazníka do formulářů
  
1. Chcete-li přidat ovládací prvky zákaznické karty do kontaktního formuláře, přejděte na stránku **Nastavení** > **Přizpůsobení** v Dynamics 365.

1. Vyberte **Přizpůsobit systém**.

1. Vyhledejte entitu **Kontakt**, rozbalte ji a poté vyberte **Formuláře**.

1. Vyberte kontaktní formulář, do kterého chcete přidat ovládací prvky karty zákazníka.

    > [!div class="mx-imgBorder"]
    > ![Výběr formuláře kontaktu](media/contact-active-forms.png "Výběr formuláře kontaktu")

1. Chcete-li přidat ovládací prvek demografických údajů, v editoru formulářů přetáhněte libovolné pole z **Průzkumníka polí** na místo, kam chcete umístit ovládací prvek.

1. Vyberte pole ve formuláři, které jste právě přidali, a poté vyberte možnost **Změnit vlastnosti**.

1. Přejděte na kartu **Ovládací prvky** a zvolte **Přidat ovládací prvek**. Vyberte jeden z dostupných vlastních ovládacích prvků a vyberte **Přidat**.

1. V dialogovém okně **Vlastnosti pole** zrušte zaškrtnutí políčka **Zobrazit popisek ve formuláři**.

1. Vyberte možnost **Web** pro ovládací prvekl. Pro ovládací prvek Rozšíření vyberte typ rozšíření, který chcete zobrazit, konfigurací pole **enrichmentType**. Pro každý druh rozšíření musíte přidat samostatnou kontrolu rozšíření.

1. Vyberte **Uložit** a **Publikovat**, chcete-li zveřejnit aktualizovaný kontaktní formulář.

1. Přejděte na publikovaný kontaktní formulář. Uvidíte nově přidaný ovládací prvek. Možná se budete muset přihlásit při prvním použití.

1. Chcete-li přizpůsobit, co se má zobrazit na vlastním ovládacím prvku, vyberte tlačítko Upravit v pravém horním rohu.
