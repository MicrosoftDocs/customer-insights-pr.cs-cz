---
title: Rozšíření od třetí strany HERE Technologies
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668670"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Rozšíření profilů zákazníků od HERE Technologies (Preview)

HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění. Se službami rozšíření dat HERE Technologies můžete dosáhnout přesnějšího porozumění polohy svých zákazníků normalizací adres, získáním zeměpisné šířky a délky atd.

## <a name="prerequisites"></a>Požadavky

Chcete-li nakonfigurovat rozšíření společnosti HERE Technologies, musíte splnit následující předpoklady:

- Musíte mít aktivní předplatné HERE Technologies. Chcete-li získat předplatné, můžete se [registrovat zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo. [Zjistěte více o HERE Technologies Location Enrichment.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Máte klíč rozhraní API pro HERE Technologies.

- Máte oprávnění pro [správu](permissions.md#administrator).

## <a name="configuration"></a>Konfigurace

1. Přejděte na **Data** > **Rozšíření**.

1. Vyberte **Rozšířit moje data** na dlaždici HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Dlaždice HERE Technologies](media/HERE-tile.png "Dlaždice HERE Technologies")

1. Zadejte aktivní **klíč rozhraní API pro HERE Technologies**. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**. 

1. Potvrďte oba vstupy výběrem **Připojit k HERE**.

1. Vyberte **Přidat data** a zvolte, zda chcete mapovat pole na primární nebo sekundární adresu. Můžete zadat mapování polí pro obě adresy (například adresu domácnosti a adresu firmy) a profily pro obě adresy rozšířit samostatně. Vyberte **Další**.

1. Definujte, která pole z vašich sjednocených profilů se mají použít k vyhledání odpovídajících dat umístění od HERE Technologies. Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu. Pro vyšší přesnost shody lze přidat více polí.

   > [!div class="mx-imgBorder"]
   > ![Stránka konfigurace rozšíření od HERE Technologies](media/enrichment-HERE-configuration.png "Stránka konfigurace rozšíření od HERE Technologies")

1. Vyberte **Použít** k dokončení mapování polí.

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy rozhraní API od HERE Technologies.

Po dokončení procesu obohacení můžete zkontrolovat nově obohacené údaje o zákaznických profilech v **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti HERE Technologies, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost HERE Technologies splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
