---
title: Rozšíření firemních profilů od třetí strany Leadspace
description: Obecné informace o rozšíření od třetí strany Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269414"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Rozšíření profilů společnosti o Leadspace (náhled)

Leadspace je společnost zabývající se datovou vědou, která poskytuje B2B zákaznickou datovou platformu. Umožňuje zákazníkům s jednotnými profily zákazníků rozšiřovat data společností. Rozšíření zahrnuje dodatečné atributy, včetně velikosti společnosti, místa, odvětví a dalších.

## <a name="prerequisites"></a>Požadavky

Abyste mohli Leadspace konfigurovat, je třeba splnit následující předpoklady:

- Máte aktivní licenci Leadspace a „časově neomezený klíč“ (označovaný jako **Token Leadspace**). Kontaktujte přímo [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pro podrobnosti o jejich produktu.
- Máte oprávnění pro [správu](permissions.md#administrator).
- Máte [sjednocené profily zákazníků](customer-profiles.md) pro společnosti.

## <a name="configuration"></a>Konfigurace

1. V přehledech cílové skupiny přejděte na **Data** > **Rozšíření**.

1. Vybrat **Rozšířit moje data** na dlaždici Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot dlaždice Leadspace.":::

1. Vyberte **Začít** a poté zadejte aktivní **Token Leadspace** (časově neomezený klíč). Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**. Potvrďte oba vstupy výběrem **Připojit k Leadspace**.

1. Vyberte **Mapovat data** a zvolte datovou sadu, kterou chcete rozšířit o firemní data od společnosti Leadspace. Můžete vybrat entitu *Zákazník* k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Výběr mezi profilem zákazníka a rozšířením segmentu.":::

1. Klikněte na **Další** a definujte, která pole z vašich sjednocených profilů by měla být použita k vyhledání odpovídajících firemních dat z Leadspace. Pole **Název společnosti** je povinné. Pro vyšší přesnost shody až do dvou dalších polí můžete přidat **Web společnosti** a **Umístění společnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno mapování pole Leadspace.":::
   
1. Vyberte **Použít** k dokončení mapování polí.

1. Vyberte **Spustit** pro rozšíření profilů společnosti. Rychlost provedení rozšíření závisí na počtu sjednocených profilů zákazníků.

## <a name="enrichment-results"></a>Výsledky rozšíření

Po aktualizaci rozšíření si můžete prohlédnout nově rozšířená firemní data v části [Moje rozšíření](enrichment-hub.md). Najdete čas poslední aktualizace a počet rozšířených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

Další informace naleznete na webu [Rozhraní API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Další kroky

Stavte na svých obohacených zákaznických údajích. Vytvářejte [segmenty](segments.md), [míry](measures.md) a dokonce [exportujte data](export-destinations.md), abyste svým zákazníkům dopřáli osobní zážitek.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Leadspace, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Leadspace splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]