---
title: Rozšíření profilů zákazníků o údaje o poloze z Azure Maps (Preview)
description: Obecné informace o rozšíření první strany Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238034"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Rozšíření profilů zákazníků o údaje o poloze z Azure Maps (Preview)

Azure Maps poskytují data a služby zaměřené na umístění, aby poskytovaly zkušenosti založené na geoprostorových datech s vestavěnou informací o poloze. Služby rozšíření dat o Azure Maps zlepšují přesnost informací o poloze vašich zákazníků. Přináší možnosti, jako je normalizace adres a extrakce zeměpisné šířky a délky do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Předpoklady

- Aktivní předplatné Azure Maps. Chcete-li získat předplatné, [zaregistrujte se nebo získejte bezplatnou zkušební verzi](https://azure.microsoft.com/services/azure-maps/).

- [Připojení](connections.md) Azure Maps je [konfigurováno](#configure-the-connection-for-azure-maps) správcem.

## <a name="configure-the-connection-for-azure-maps"></a>Proveďte konfiguraci připojení pro Azure Maps

Musíte být [správce](permissions.md#admin) v Customer Insights a mít aktivní klíč API Azure Maps.

1. Při konfiguraci rozšíření vyberte **Přidat připojení** nebo přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stránka konfigurace připojení Azure Maps.":::

1. Zadejte název připojení a platný klíč API Azure Maps.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Poloha** z Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dlaždice Azure Maps":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici propojení , kontaktujte správce.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o demografické údaje od Microsoft. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro shodu: primární a/nebo sekundární adresa. Můžete určit mapování polí pro obě adresy a profily pro obě adresy rozšířit samostatně. Například pro adresu bydliště a adresu firmy. Vyberte **Další**.

1. Namapujte pole na údaje o poloze z Azure Maps. Pole **Ulice 1** a **Poštovní směrovací číslo** jsou povinná pro vybranou primární a/nebo sekundární adresu. Pro vyšší přesnost shody přidejte další pole.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapování atributů Azure Maps.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zkontrolujte **Pokročilé nastavení**, která nabízejí maximální flexibilitu pro zvládnutí případů pokročilého použití. Následující výchozí hodnoty však obvykle není nutné měnit.

   - **Typ adres**: Vrátí se nejlepší shoda adresy, i když je neúplná. Chcete -li získat pouze úplné adresy, například adresy, které obsahují číslo domu, zrušte zaškrtnutí všech políček kromě **Adresy bodů**.
   - **Jazyk**: Adresy se vrátí v jazyce podle oblasti adresy. Chcete -li použít standardizovaný jazyk adres, vyberte jazyk z rozevírací nabídky. Například výběr možnosti **čeština** vrací **Kodaň, Dánsko** místo **København, Danmark**.
   - **Maximální počet výsledků**: Počet výsledků na adresu.

1. Vyberte **Další**.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
