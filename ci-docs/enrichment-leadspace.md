---
title: Rozšíření firemních profilů od třetí strany Leadspace
description: Obecné informace o rozšíření od třetí strany Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954171"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Rozšíření profilů společnosti o Leadspace (náhled)

Leadspace je společnost zabývající se vědou o datech, která poskytuje platformu zákaznických dat B2B. Umožňuje prostředí s jednotnými profily zákazníků založenými na účtech rozšiřovat jejich data. Rozšiřte *Profily zákazníků* o atributy, jako je velikost společnosti, umístění nebo odvětví. Rozšiřte *Kontaktní profily* o atributy, jako je titul, osobnost nebo ověření e -mailem.

## <a name="prerequisites"></a>Předpoklady

- Aktivní licence Leadspace.
- [Sjednocené profily zákazníků](customer-profiles.md) na základě obchodních vztahů.
- Leadspace [připojení](connections.md) [konfiguruje](#configure-the-connection-for-leadspace) správce. Informace o produktu si zjistěte přímo u společnosti [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>Konfigurace propojení pro Leadspace

Musíte být [správce](permissions.md#admin) v Customer Insights a mít „věčný klíč“ (označovaný jako **Token Leadspace**).

1. Při konfiguraci rozšíření vyberte **Přidat připojení** nebo přejděte na **Správce** > **Připojení** a v dlaždici Leadspace vyberte **Nastavit**.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Stránka konfigurace propojení pro Leadspace":::

1. Zadejte název připojení a platný token Leadspace.

1. Zkontrolujte a poskytněte svůj souhlas s [ochranou osobních údajů a dodržováním předpisů](#data-privacy-and-compliance) výběrem **souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat společnosti Leadspace, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Leadspace splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte **Rozšířit moje data** v **Data společnosti** z dlaždice Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Screenshot dlaždice Leadspace.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici správce, obraťte se na něj.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o data společnosti z Leadspace. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro shodu: primární a/nebo sekundární adresa. Můžete určit mapování polí pro obě adresy a profily pro obě adresy rozšířit samostatně. Například pro adresu bydliště a adresu firmy. Vyberte **Další**.

1. Namapujte pole vaší společnosti na firemní data z Leadspace. Pole **Název společnosti** je povinné. Pro vyšší přesnost shody až do dvou dalších polí můžete přidat **Web společnosti** a **Umístění společnosti**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Podokno mapování pole Leadspace.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Pokud máte *profily kontaktu*, které byste chtěli rozšířit, zaškrtněte políčko. Customer Insights automaticky namapují požadovaná pole.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Kontakt Leadspace zaznamenává rozšíření.":::

1. Vyberte **Další**.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="enrichment-results"></a>Výsledky rozšíření

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Další informace naleznete na webu [Rozhraní API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
