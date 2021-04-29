---
title: Rozšíření od třetí strany Experian
description: Obecné informace o rozšíření od třetí strany Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896365"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohaťte profily zákazníků o demografické údaje ze služby Experian (náhled)

Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb. Se službami obohacení dat společnosti Experian můžete získat hlubší porozumění svým zákazníkům obohacením profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.

## <a name="prerequisites"></a>Požadavky

Pro konfiguraci Experianu je třeba splnit následující předpoklady:

- Máte aktivní předplatné Experian. Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo. [Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Správce již nakonfiguroval připojení Experian *nebo* máte oprávnění [správce](permissions.md#administrator). Pro svůj účet Secure Transport (ST) s povoleným SSH, který pro vás společnost Experian vytvořila, potřebujete také ID uživatele, ID strany a číslo modelu.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.

1. Vyberte **Obohaťte moje data** na dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Experian](media/experian-tile.png "Dlaždice Experian")
   > 

1. V rozevíracím seznamu vyberte [propojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit připojení výběrem možnosti **Přidat připojení** a volbou Experian z rozevíracího seznamu. 

1. Výběr připojení potvrďte výběrem **Připojit k Experian**.

1.  Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o demografické údaje ze služby Experian. Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů by se měla použít k vyhledání odpovídajících demografických údajů od Leadspace. Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**. Pro vyšší přesnost shody lze přidat až dvě další pole. Tento výběr ovlivní mapovací pole, ke kterým máte přístup v dalším kroku.

    > [!TIP]
    > Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.

1. Výběrem možnosti **Další** spusťte mapování polí.

1. Definujte, který typ polí z vašich sjednocených profilů by se měla použít k vyhledání odpovídajících demografických údajů od Leadspace. Povinná pole jsou označená.

1. Zadejte název rozšíření a název výstupní entity.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="configure-the-connection-for-experian"></a>Konfigurace propojení pro Experian 

Abyste mohli konfigurovat propojení, musíte být správce. Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Experian vyberte **Nastavit**.

1. Vyberte **Začínáme**.

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Zadejte platné ID uživatele, ID strany a Číslo modelu pro účet zabezpečené přepravy Experian.

1. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno konfigurace připojení pro Experian":::

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti vašich údajů o zákaznících a na procesech obohacování nastavených pro váš účet společností Experian.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Experian, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Experian splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
