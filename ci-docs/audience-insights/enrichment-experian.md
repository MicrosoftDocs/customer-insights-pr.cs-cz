---
title: Rozšíření od třetí strany Experian
description: Obecné informace o rozšíření od třetí strany Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269552"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Obohaťte profily zákazníků o demografické údaje ze služby Experian (náhled)

Experian je světový lídr v oblasti spotřebitelských a obchodních úvěrových reportů a marketingových služeb. Se službami obohacení dat společnosti Experian můžete získat hlubší porozumění svým zákazníkům obohacením profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem a další.

## <a name="prerequisites"></a>Požadavky

Pro konfiguraci Experianu je třeba splnit následující předpoklady:

- Máte aktivní předplatné Experian. Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo. [Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Pro svůj účet Secure Transport (ST) s povoleným SSH, který pro vás vytvořil Experian, máte ID uživatele, ID strany a Číslo modelu.
- V přehledech cílové skupiny máte oprávnění [Správce](permissions.md#administrator).

## <a name="configuration"></a>Konfigurace

1. Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.

1. Vyberte **Obohaťte moje data** na dlaždici Experian.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice Experian](media/experian-tile.png "Dlaždice Experian")

1. Vyberte **Začít** a zadejte ID uživatele, ID strany a Číslo modelu pro váš účet Experian Secure Transport. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**. Potvrďte všechny vstupy výběrem **Použít**.

## <a name="map-your-fields"></a>Mapování polí

1.  Vyberte **Přidat data** a zvolte **sadu zákaznických dat**, kterou chcete rozšířit o demografické údaje od společnosti Experian. Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

1. Vyberte identifikátory klíčů z polí **Jméno a adresa**, **E-mail** nebo **Telefon** pro odeslání společnosti Experian k rozpoznání identity.

   > [!TIP]
   > Další klíčové atributy identifikátoru odeslané do Experian pravděpodobně přinesou vyšší míru shody.

1. Vyberte **Další** a namapujte odpovídající atributy z vaší jednotné entity zákazníka pro vybraná pole klíčového identifikátoru.

1. Vyberte **Přidat atribut**, chcete-li mapovat libovolné další atributy, které byste chtěli odeslat do Experian.

1.  Vyberte **Uložit** pro dokončení mapování pole.

    > [!div class="mx-imgBorder"]
    > ![Mapování polí Experian](media/experian-field-mapping.png "Mapování polí Experian")

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