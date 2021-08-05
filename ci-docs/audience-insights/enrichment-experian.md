---
title: Obohacení pomocí obohacení třetí strany Experian
description: Obecné informace o obohacování třetí strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: abe9ee447745081e3c462d44e5901b6dac919adf
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555345"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohaťte profily zákazníků o demografické údaje z Experian (náhled)

Experian je světovým lídrem v oblasti reportingu spotřebitelských a obchodních úvěrů a marketingových služeb. Se službami rozšiřování dat Experian můžete získat hlubší porozumění svým zákazníkům obohacením svých profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem atd.

## <a name="prerequisites"></a>Požadavky

Abyste mohli konfigurovat Experian, je třeba splnit následující předpoklady:

- Musíte mít aktivní předplatné Experian. Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo. [Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Správce již nakonfiguroval připojení Experian *nebo* máte oprávnění [správce](permissions.md#administrator). Pro svůj účet Secure Transport (ST) s povoleným SSH potřebujete také ID uživatele, ID strany a Číslo modelu, které pro vás společnost Experian vytvořila.

## <a name="supported-countriesregions"></a>Podporované země/oblasti

V současné době podporujeme rozšíření profilů zákazníků pouze ve Spojených státech.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.

1. Vyberte **Obohatit moje data** v dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Experian.](media/experian-tile.png "Experian tile")
   > 

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit připojení výběrem **Přidat připojení** a výběrem Experian z rozevíracího seznamu. 

1. Vyberte **Připojit k Experian** pro potvrzení výběru připojení.

1.  Vyberte **Další** a zvolte **Sadu dat zákazníka**, kterou chcete obohatit o demograficé údaje z Experian. Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů se má použít k vyhledání odpovídajících demografických dat Experian. Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**. Pro vyšší přesnost shody lze přidat až dvě další pole. Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.

    > [!TIP]
    > Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.

1. Výběrem možnosti **Další** spusťte mapování polí.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít k vyhledání odpovídajících demografických dat z Experian. Povinná pole jsou označená.

1. Zadejte název rozšíření a název výstupní entity.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="configure-the-connection-for-experian"></a>Konfigurace rolí připojení pro Experian 

Abyste mohli konfigurovat propojení, musíte být správce. Při konfiguraci obohacení vyberte **Přidat připojení** *nbo* jděte na **Správa** > **Připojení** a vyberte **Nastavit** v dlaždici Experian.

1. Vyberte **Začínáme**.

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Zadejte platné ID uživatele, ID strany a Číslo modelu pro váš zabezpečený transportní účet Experian.

1. Zkontrolujte a poskytněte svůj souhlas s **ochranou osobních údajů a dodržováním předpisů** výběrem **souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno konfigurace připojení Experian":::

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti vašich údajů o zákaznících a na procesech obohacování nastavených pro váš účet Experian.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvořte [segmenty](segments.md) a [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům poskytli přizpůsobené prostředí.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do Experian, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Experian bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
