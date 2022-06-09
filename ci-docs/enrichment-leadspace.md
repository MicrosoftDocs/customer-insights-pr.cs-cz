---
title: Rozšíření firemních profilů od třetí strany Leadspace
description: Obecné informace o rozšíření od třetí strany Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645835"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Rozšíření profilů společnosti o Leadspace (náhled)

Leadspace je společnost zabývající se vědou o datech, která poskytuje platformu zákaznických dat B2B. Umožňuje prostředí s jednotnými profily zákazníků založenými na účtech rozšiřovat jejich data. Rozšiřte *Profily zákazníků* o atributy, jako je velikost společnosti, umístění nebo odvětví. Rozšiřte *Kontaktní profily* o atributy, jako je titul, osobnost nebo ověření e -mailem.

## <a name="prerequisites"></a>Předpoklady

Abyste mohli Leadspace konfigurovat, je třeba splnit následující předpoklady:

- Máte aktivní licenci Leadspace.
- Máte [sjednocené profily zákazníků](customer-profiles.md) na základě účtů.
- propojení Leadspace již bylo nakonfigurováno správcem nebo máte oprávnění [správce](permissions.md#admin) a "trvalý klíč" (označovaný jako **Token Leadspace**). Informace o produktu si zjistěte přímo u společnosti [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření**.

1. Vyberte **Rozšířit moje data** v dlaždici Leadspace a vyberte **Začít**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot dlaždice Leadspace.":::

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit propojení výběrem možnosti **Přidat propojení** a **Leadspace**. 

1. propojení potvrďte výběrem **Připojit k Leadspace**.

1. Vyberte **Další** a zvolte **datovou sadu zákazníka**, kterou chcete rozšířit o firemní data ze služby Leadspace. Můžete vybrat entitu **Zákazník** k rozšíření všech profilů vašich zákazníků nebo vyberte entitu segmentu k rozšíření pouze profilů zákazníků obsažených v tomto segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Vyberte **Další** a definujte, která pole z vašich sjednocených profilů se použijí k vyhledání odpovídajících firemních dat z Leadspace. Pole **Název společnosti** je povinné. Pro vyšší přesnost shody až do dvou dalších polí můžete přidat **Web společnosti** a **Umístění společnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno mapování pole Leadspace.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Pokud máte *profily kontaktu*, které byste chtěli rozšířit, zaškrtněte políčko. Customer Insights automaticky namapují požadovaná pole.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Kontakt Leadspace zaznamenává rozšíření.":::
 
1. Zadejte název rozšíření a po přezkoumání vašich voleb vyberte **Uložit rozšíření**.


## <a name="configure-the-connection-for-leadspace"></a>Konfigurace propojení pro Leadspace 

Abyste mohli konfigurovat propojení, musíte být správce. Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Leadspace vyberte **Nastavit**.

1. Vyberte **Začínáme**. 

1. Do pole **Zobrazované jméno** zadejte jméno.

1. Zadejte platný token Leadspace.

1. Zkontrolujte a poskytněte svůj souhlas s **ochranou osobních údajů a dodržováním předpisů** výběrem **souhlasím**.

1. Vyberte **Ověřit** k ověření konfigurace.

1. Po dokončení ověření vyberte **Uložit**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stránka konfigurace propojení pro Leadspace":::

## <a name="enrichment-results"></a>Výsledky rozšíření

Po aktualizaci rozšíření si můžete prohlédnout nově rozšířená firemní data v části [Moje rozšíření](enrichment-hub.md). Najdete čas poslední aktualizace a počet rozšířených profilů.

Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.

Další informace naleznete na webu [Rozhraní API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Další kroky


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Leadspace, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Leadspace splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE [footer-include](includes/footer-banner.md)]