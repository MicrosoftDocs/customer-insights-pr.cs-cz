---
title: Obohacení profilů zákazníků pomocí údaje o poloze z Azure Maps
description: Obecné informace o obohacování první strany Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466754"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Obohacení zákaznických profilů o Azure Maps (Preview)

Azure Maps poskytuje data a služby zaměřené na polohu, který poskytují prostředí založená na geoprostorových datech s integrovanou inteligencí polohy. Služby obohacování dat o Azure Maps zlepšují přesnost informací o poloze vašich zákazníků. Přináší možnosti, jako je normalizace adres a extrakce zeměpisné šířky a délky do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Požadavky

Chcete -li konfigurovat obohacení dat o Azure Maps, musí být splněny následující předpoklady:

- Musíte mít aktivní předplatné Azure Maps. Chcete -li získat předplatné, můžete se [zaregistrovat nebo získat bezplatnou zkušební verzi](https://azure.microsoft.com/services/azure-maps/).

- Máte k dispozici [připojení](connections.md) k Azure Maps *nebo* máte oprávnění [správce](permissions.md#administrator) a aktivní klíč API rozhraní Azure Maps.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**. 

1. Na dlaždici **Poloha** vyberte **Obohatit moje data**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Dlaždice Azure Maps":::

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici připojení k Azure Maps, obraťte se na správce. Pokud jste správce, můžete [nakonfigurovat připojení pro Azure Maps](#configure-the-connection-for-azure-maps). 

1. Vyberte **Další** pro potvrzení výběru.

1. Vyberte **datovou sadu zákazníka**, kterou chcete obohatit o údaje o poloze z Azure Maps. Můžete vybrat entitu **Zákazník**, abyste obohatili všechny své sjednocené zákaznické profily, nebo vyberte entitu segmentu, abyste obohatili pouze profily zákazníků obsažené v tomto segmentu.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Snímek obrazovky při výběru datové sady zákazníka.":::

1. Vyberte, zda chcete pole mapovat na primární nebo sekundární adresu. Můžete zadat mapování polí pro obě adresy a obohatit profily pro obě adresy samostatně, například pro adresu bydliště a obchodní adresu. Vyberte **Další**.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít k vyhledání odpovídajících dat o poloze z Azure Maps. Pole **Ulice 1** a **PSČ** pro vybranou primární nebo sekundární adresu jsou povinná pole. Pro vyšší přesnost shody můžete přidat další pole.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Stránka konfigurace obohacení o Azure Maps.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Vyhodnoťte, zda chcete upravit **Pokročilé nastavení**. Ta jsou poskytována tak, aby dávala maximální flexibilitu při zpracování pokročilých případů použití, ale výchozí hodnoty budou ve většině případů adekvátní:
   - **Typ adres**: Výchozí chování je takové, že obohacení vrátí nejlepší shodu adresy, i když je neúplná. Chcete -li získat pouze úplné adresy, například adresy, které obsahují číslo domu, zrušte zaškrtnutí všech políček kromě **Adresy bodů**. 
   - **Jazyk**: Ve výchozím nastavení jsou adresy vráceny v jazyce pro oblast, do které byla adresa určena. Chcete -li použít standardizovaný jazyk adres, vyberte jazyk z rozevírací nabídky. Například výběr **Angličtina** zobrazí **Copenhagen, Denmark** namísto **København, Danmark**.

1. Zadejte jméno rozšíření.

1. Zkontrolujte své volby a pak vyberte možnost **Uložit obohacení**.

## <a name="configure-the-connection-for-azure-maps"></a>Proveďte konfiguraci připojení pro Azure Maps

Chcete -li konfigurovat připojení, musíte být správcem v přehledech cílových skupin. Při konfiguraci obohacení vyberte **Přidat připojení** nebo přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici Azure Maps.

1. V poli **Zobrazovaný název** zadejte název připojení.

1. Poskytněte platný klíč rozhraní API pro Azure Maps.

1. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Stránka konfigurace připojení Azure Maps.":::

## <a name="enrichment-results"></a>Výsledky rozšíření

Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů. Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab). Doba zpracování bude záviset na velikosti vašich zákaznických dat a dobách odezvy API rozhraní.

Po dokončení procesu obohacení si můžete prohlédnout nově obohacená data profilů zákazníků pod možností **Moje obohacení**. Dále najdete čas poslední aktualizace a počet obohacených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do Azure Maps, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Azure Maps bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace najdete v [prohlášení o ochraně osobních údajů společnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
