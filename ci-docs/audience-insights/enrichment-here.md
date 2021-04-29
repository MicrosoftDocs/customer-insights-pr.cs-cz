---
title: Rozšíření od třetí strany HERE Technologies
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896043"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Rozšíření profilů zákazníků od HERE Technologies (Preview)

HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění. Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.

## <a name="prerequisites"></a>Požadavky

Chcete-li nakonfigurovat rozšíření společnosti HERE Technologies, musíte splnit následující předpoklady:

- Musíte mít aktivní předplatné HERE Technologies. Chcete-li získat předplatné, můžete se [registrovat zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo. [Zjistěte více o HERE Technologies Location Enrichment.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Zde je k dispozici [propojení](connections.md) HERE *nebo* máte oprávnění [správce](permissions.md#administrator) a klíč API HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**. 

1. Vyberte **Rozšířit moje data** v dlaždici HERE Technologies a vyberte **Začít**.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice HERE Technologies](media/HERE-tile.png "Dlaždice HERE Technologies")

1. V rozevíracím seznamu vyberte [propojení](connections.md). Pokud není k dispozici propojení, kontaktujte správce. Pokud jste správce, můžete vytvořit propojení výběrem možnosti **Přidat propojení**. V rozevírací nabídce zvolte **HERE Technologies**. 

1. Výběr připojení potvrďte výběrem **Připojit k HERE Technologies**.

1.  Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o údaje o poloze od společnosti HERE Technologies. Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Zvolte, zda chcete mapovat pole na primární nebo sekundární adresu. Můžete určit mapování polí pro obě adresy a profily pro obě adresy obohatit samostatně. Například pokud existuje adresa domů a do zaměstnání. Vyberte **Další**.

1. Definujte, která pole z vašich sjednocených profilů se mají použít k vyhledání odpovídajících dat umístění od HERE Technologies. Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu. Pro vyšší přesnost shody lze přidat více polí.

   > [!div class="mx-imgBorder"]
   > ![Stránka konfigurace rozšíření od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurace rozšíření od HERE Technologies")

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte jméno rozšíření. 

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurace propojení pro HERE technologies 

Abyste mohli konfigurovat propojení, musíte být správce. Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici HERE Technologies vyberte **Nastavit**.

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Zadejte platný klíč API společnosti HERE Technologies.

1. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.

> [!div class="mx-imgBorder"]
   > ![Stránka konfigurace připojení pro HERE Technologies](media/enrichment-HERE-connection.png "Stránka konfigurace připojení pro HERE Technologies")

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy rozhraní API od HERE Technologies.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti HERE Technologies, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost HERE Technologies splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
