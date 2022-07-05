---
title: Rozšiřte profily zákazníků o demografické údaje z Experian (náhled)
description: Obecné informace o rozšíření třetí strany Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053013"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Rozšiřte profily zákazníků o demografické údaje z Experian (náhled)

Experian je světovým lídrem v oblasti reportingu spotřebitelských a obchodních úvěrů a marketingových služeb. Se službami rozšiřování dat Experian můžete získat hlubší porozumění svým zákazníkům rozšířením svých profilů zákazníků o demografické údaje, jako je velikost domácnosti, příjem atd.

## <a name="supported-countriesregions"></a>Podporované země/oblasti

V současné době podporujeme rozšíření profilů zákazníků pouze ve Spojených státech.

## <a name="prerequisites"></a>Předpoklady

- Aktivní předplatné Experian. Chcete-li získat předplatné, [kontaktujte Experian](https://www.experian.com/marketing-services/contact) přímo. [Další informace o rozšiřování dat Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Experian [připojení](connections.md) [konfiguruje](#configure-the-connection-for-experian) správce.

- ID uživatele, ID strany a číslo modelu Experian pro váš účet Secure Transport (ST) s podporou SSH, který pro vás společnost Experian vytvořila.

## <a name="configure-the-connection-for-experian"></a>Konfigurace rolí připojení pro Experian

Musíte být [správce](permissions.md#admin) v Customer Insights a mít ID uživatele, ID strany a číslo modelu Experian.

1. Při konfiguraci rozšíření vyberte **Přidat připojení** nebo jděte na **Správa** > **Připojení** a vyberte **Nastavit** v dlaždici Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Podokno konfigurace připojení Experian":::

1. Zadejte název připojení a platné ID uživatele, ID strany a číslo modelu účtu zabezpečeného přenosu Experian.

1. Zkontrolujte a poskytněte svůj souhlas s [ochranou osobních údajů a dodržováním předpisů](#data-privacy-and-compliance) výběrem **souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenášet data do Experian, povolíte tím přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese takové údaje podle vašeho pokynu, ale vy jste zodpovědní za zajištění, že Experian bude splňovat veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732). Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na kartě **Demografie** z dlaždice Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Dlaždice Experian na stránce s přehledem rozšíření. ":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici správce, obraťte se na něj.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o demografické údaje z Experian. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Screenshot výběru sady zákaznických dat.":::

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro porovnávání demografických údajů z Experian. Požaduje se alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**. Pro vyšší přesnost shody přidejte další pole. Vyberte **Další**.

1. Namapujte svá pole na demografické údaje z Experian.

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
