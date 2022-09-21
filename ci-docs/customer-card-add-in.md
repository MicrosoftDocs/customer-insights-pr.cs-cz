---
title: Doplněk karty zákazníka pro aplikace Dynamics 365 (Preview) (obsahuje video)
description: Pomocí tohoto doplňku zobrazte data profilu zákazníků z Customer Insights v aplikacích Dynamics 365.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 65fd80cc563b8b3b8c8874b66f179f8b0c7a19f0
ms.sourcegitcommit: fe33cc76d015232ff8737f77193f44f2b884bb6b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473634"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Doplněk karty zákazníka pro aplikace Dynamics 365 (Preview)

Získejte kompletní přehled o svých zákaznících přímo v aplikacích Dynamics 365. Když je v podporované aplikaci Dynamics 365 nainstalován doplněk Zákaznická karta, můžete se rozhodnout zobrazovat pole profilu zákazníka, přehledy a časovou osu aktivity. Doplněk načte data z Customer Insights bez ovlivnění dat v připojené aplikaci Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Předpoklady

- Modelem řízené aplikace Dynamics 365, jako je Sales nebo Customer Service, verze 9.0 a novější.
- Aby byla vaše data Dynamics 365 mapována na profily zákazníků Customer Insights, doporučujeme je [přijímat z aplikace Dynamics 365 pomocí konektoru Microsoft Dataverse](connect-power-query.md). Pokud pro přijímání kontaktů (nebo obchodních vztahů) Dynamics 365 používáte jinou metodu, musíte nastavit pole `contactid` (nebo `accountid`) jako [primární klíč pro tento zdroj dat v rámci procesu sjednocení dat](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Všichni uživatelé Dynamics 365 doplňku Zákaznické karty musí být [přidáni jako uživatelé](permissions.md) v Customer Insights, aby viděli data.
- [Konfigurované možnosti vyhledávání a filtrování](search-filter-index.md) v Customer Insights.
- Některá data a ovládací prvky jsou k dispozici pouze v prostředích konkrétních typů. Konfigurace doplňku vás bude informovat, pokud ovládací prvek není k dispozici kvůli vybranému typu prostředí. Tato chyba se zobrazí v ovládacím prvku při jeho vykreslování. Další informace o [případech použití prostředí](work-with-business-accounts.md).
- Každý ovládací prvek doplňku závisí na konkrétních datech v Customer Insights.
  - **Ovládací prvek měření**: Vyžaduje [nakonfigurované míry atributu zákazníka](measures.md).
  - **Ovládací prvek analytických nástrojů**: Vyžaduje data generovaná pomocí [predikcí nebo vlastních modelů](predictions-overview.md).
  - **Ovládací prvek podrobností zákazníka** zobrazuje všechna pole z profilu, která jsou k dispozici ve sjednoceném zákaznickém profilu.
  - **Ovládací prvek rozšíření** vyžaduje aktivní [rozšíření](enrichment-hub.md) použitá na profily zákazníků. Doplněk karty podporuje tato rozšíření: [Značky](enrichment-microsoft.md) poskytované společností Microsoft, [Zájmy](enrichment-microsoft.md) poskytované společností Microsoft a [Data Office o zapojení](enrichment-office.md) poskytované společností Microsoft.
  - **Ovládací prvek kontaktů** vyžaduje typ sémantické entity kontaktu.
  - **Ovládací prvek časové osy** vyžaduje [konfigurované aktivity](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalace doplňku karty zákazníka

Doplněk karty zákazníka je řešení pro aplikace pro zapojení zákazníků v Dynamics 365. Instalace řešení:

1. Přejděte do AppSource a vyhledejte **Kartu zákazníka Dynamics**.

1. Vyberte [Doplněk karty zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získat**.

K instalaci řešení se možná budete muset přihlásit pomocí svých přihlašovacích údajů pro aplikaci Dynamics 365. Instalace řešení do vašeho prostředí může nějakou dobu trvat.

## <a name="configure-the-customer-card-add-in"></a>Nakonfigurujte doplněk zákaznické karty

1. Jako správce přejděte na **Nastavení** v Dynamics 365 a vyberte **Řešení**.

1. Vyberte odkaz **Zobrazované jméno** řešení Doplněk karty zákazníka v **Dynamics 365 Customer Insights (preview)**.

   > [!div class="mx-imgBorder"]
   > ![Vyberte zobrazovaný název.](media/select-display-name.png "Vyberte zobrazované jméno.")

1. Vyberte **Přihlásit se** a zadejte přihlašovací údaje pro účet správce, pomocí kterého konfigurujete Customer Insights.

   > [!NOTE]
   > Zkontrolujte, zda blokování automaticky otevíraných oken prohlížeče neblokuje okno ověřování, když vyberete tlačítko **Přihlásit**.

1. Vyberte prostředí Customer Insights, ze kterého chcete načíst data.

1. Definujte mapování polí na záznamy v aplikaci Dynamics 365. V závislosti na vašich datech v aplikaci Customer Insights můžete zvolit mapování následujících možností:
   - Chcete-li mapovat kontakt, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity kontaktu.
   - Chcete-li mapovat obchodní vztah, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity obchodního vztahu.

   > [!div class="mx-imgBorder"]
   > ![Pole ID kontaktu.](media/contact-id-field.png "Pole ID kontaktu.")

1. Chcete-li uložit nastavení, vyberte tlačítko **Uložit konfiguraci**.

1. Dále musíte v Dynamics 365 přiřadit role zabezpečení, aby si uživatelé mohli přizpůsobit a vidět zákaznickou kartu. V aplikaci Dynamics 365 přejděte do části **Nastavení** > **Zabezpečení** > **Uživatelé**. Vyberte uživatele, kterým chcete upravit uživatelské role, a vyberte **Správa rolí**.

1. Přiřaďte roli **Úpravce karty Customer Insights** uživatelům, kteří přizpůsobí obsah zobrazený na kartě pro celou organizaci.

## <a name="add-customer-card-controls-to-forms"></a>Přidání ovládacích prvků karty zákazníka do formulářů

V závislosti na vašem scénáři se můžete rozhodnout přidat ovládací prvky buď do formuláře **Kontakt**, nebo do formuláře **Účet**. Pokud je vaše prostředí Customer Insights pro firemní účty, doporučujeme přidat ovládací prvky do formuláře Účet. V takovém případě nahraďte „kontakt“ v níže uvedených krocích výrazem „účet“.

1. Chcete-li přidat ovládací prvky zákaznické karty do kontaktního formuláře, přejděte na stránku **Nastavení** > **Přizpůsobení** v Dynamics 365.

1. Vyberte **Přizpůsobit systém**.

1. Vyhledejte entitu **Kontakt**, rozbalte ji a poté vyberte **Formuláře**.

1. Vyberte kontaktní formulář, do kterého chcete přidat ovládací prvky karty zákazníka.

    > [!div class="mx-imgBorder"]
    > ![Vyberte formulář kontaktu.](media/contact-active-forms.png "Výběr formuláře kontaktu.")

1. Chcete-li přidat ovládací prvek demografických údajů, v editoru formulářů přetáhněte libovolné pole z **Průzkumníka polí** na místo, kam chcete umístit ovládací prvek.

1. Vyberte pole ve formuláři, které jste právě přidali, a poté vyberte možnost **Změnit vlastnosti**.

1. Přejděte na kartu **Ovládací prvky** a zvolte **Přidat ovládací prvek**. Vyberte jeden z dostupných vlastních ovládacích prvků a vyberte **Přidat**.

1. V dialogovém okně **Vlastnosti pole** zrušte zaškrtnutí políčka **Zobrazit popisek ve formuláři**.

1. Vyberte možnost **Web** pro ovládací prvekl. Pro ovládací prvek Rozšíření vyberte typ rozšíření, který chcete zobrazit, konfigurací pole **enrichmentType**. Pro každý typ rozšíření přidejte samostatný ovládací prvek rozšíření.

1. Vyberte **Uložit** a **Publikovat**, chcete-li zveřejnit aktualizovaný kontaktní formulář.

1. Přejděte na publikovaný kontaktní formulář. Uvidíte nově přidaný ovládací prvek. Možná se budete muset přihlásit při prvním použití.

1. Chcete-li přizpůsobit, co se má zobrazit na vlastním ovládacím prvku, vyberte tlačítko Upravit v pravém horním rohu.

## <a name="upgrade-customer-card-add-in"></a>Upgrade doplňku karty zákazníka

Doplněk karty zákazníka se neupgraduje automaticky. Chcete-li upgradovat na nejnovější verzi, postupujte podle následujících kroků v aplikaci Dynamics 365, ve které je nainstalován doplněk.

1. V aplikaci Dynamics 365 přejděte na **Nastavení** > **Vlastní nastavení** a vyberte **Řešení**.

1. V tabulce doplňků vyhledejte **CustomerInsightsCustomerCard** a vyberte řádek.

1. Na panelu akcí vyberte **Nainstalovat upgrade řešení**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgradujte řešení v oblasti Vlastní nastavení aplikací Dynamics 365.":::

1. Po spuštění procesu upgradu se zobrazí indikátor načítání, dokud se upgrade nedokončí. Pokud není k dispozici žádná novější verze, zobrazí se při upgradu chybová zpráva.

## <a name="troubleshooting"></a>Řešení problému

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Ovládací prvky z doplňku Zákaznické karty nenacházejí data

**Problém:**

I při správně nakonfigurovaných polích ID nemohou ovládací prvky najít data pro žádného zákazníka.  

**Řešení**

1. Ujistěte se, že jste nakonfigurovali doplněk Karta podle pokynů: [Nakonfigurujte doplněk Zákaznická karta](#configure-the-customer-card-add-in)

1. Zkontrolujte konfiguraci příjmu dat. Upravte zdroj dat pro systém Dynamics 365, který obsahuje GUID ID kontaktu. Pokud je ID kontaktu GUID zobrazeno s velkými písmeny v editoru Power Query, zkuste následující kroky:
    1. Upravte zdroj dat a otevřete zdroj dat v editoru Power Query.
    1. Vyberte sloupec ID kontaktu.
    1. Vyberte **Transformovat** v panelu záhlaví a zobrazíte dostupné akce.
    1. Vyberte **malá písmena**. Ověřte, zda jsou GUID v tabulce nyní malá písmena.
    1. Uložte zdroj dat.
    1. Spusťte příjem dat, sjednocení a následné procesy k šíření změn do GUID.

Poté, co systém dokončí úplnou aktualizaci, by ovládací prvky doplňku Zákaznické karty měly zobrazovat očekávaná data.

[!INCLUDE [footer-include](includes/footer-banner.md)]
