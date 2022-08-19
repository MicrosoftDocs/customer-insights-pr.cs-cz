---
title: Rozšíření profilů zákazníků s HERE Technologies (Preview)
description: Obecné informace o rozšíření od třetí strany HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237850"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Rozšíření profilů zákazníků s HERE Technologies (Preview)

HERE Technologies je společnost postavená na lokalizační platformě, která poskytuje data a služby týkající se umístění. Služby obohacování dat společnosti HERE Technologies zlepšují přesnost informací o poloze vašich zákazníků. Poskytuje normalizaci adres, extrakci zeměpisné šířky a délky a další.

## <a name="prerequisites"></a>Předpoklady

- Aktivní předplatné HERE Technologies. Chcete-li získat předplatné, [zaregistrujte se zde](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) nebo [kontaktujte společnost HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) přímo. [Zjistěte více o HERE Technologies Location Enrichment.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Připojení](connections.md) HERE [konfiguruje](#configure-the-connection-for-here-technologies) správce.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurace propojení pro HERE Technologies

Musíte být [správce](permissions.md#admin) v Customer Insights a mít aktivní klíč API HERE Technologies.

1. Při konfiguraci rozšíření vyberte **Přidat připojení** nebo přejděte na **Správce** > **Připojení** a v dlaždici HERE Technologies vyberte **Nastavit**.

1. Zadejte název připojení a platný klíč API HERE Technologies.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Stránka konfigurace připojení pro HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Poloha** od HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Dlaždice HERE Technologies.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici propojení , kontaktujte správce.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o demografické údaje od HERE Technologies. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro shodu: primární a/nebo sekundární adresa. Můžete určit mapování polí pro obě adresy a profily pro obě adresy rozšířit samostatně. Například pro adresu bydliště a adresu firmy. Vyberte **Další**.

1. Namapujte svá pole na demografické údaje z HERE Technologies.. Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu. Pro vyšší přesnost shody přidejte další pole.

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
