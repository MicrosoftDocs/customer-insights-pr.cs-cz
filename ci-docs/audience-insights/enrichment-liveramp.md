---
title: Rozšíření dat identity LiveRamp
description: Rozšiřte profily zákazníků daty LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373012"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Rozšíření profilů zákazníků daty identity z LiveRamp (Preview) 

Společnost LiveRamp poskytuje deterministické offline rozlišení identity a konsolidaci zákaznických dat. Osobní identifikátory ve svých zákaznických datech můžete mapovat do grafu identity AbiliTec a přijímat ID AbiliTec. Tato ID pak můžete využít pro lepší sjednocení údajů o vašich zákaznících. 

## <a name="prerequisites"></a>Předpoklady 

Abyste mohli konfigurovat rozšíření, je třeba splnit následující předpoklady: 

- Máte aktivní předplatné LiveRamp. Chcete-li získat předplatné, kontaktujte tým svého účtu LiveRamp nebo napište na adresu [dynamics@liveramp.com](mailto:dynamics@liveramp.com).   

- Aktivní předplatné AbiliTec s ID klienta a tajným kódem pro přístup k API. Další informace naleznete v tématu [Centrum vývojáře AbiliTec API](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Podporované země/oblasti 

V současnosti podporujeme rozšíření zákaznických profilů o data LiveRamp pouze ve Spojených státech. 

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření 

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**. 

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Identita**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dlaždice identity na stránce s přehledem rozšíření.":::

1. V rozevíracím seznamu vyberte [připojení](connections.md). Pokud není k dispozici propojení , kontaktujte správce. Pokud jste správce, můžete vytvořit připojení výběrem možnosti **Přidat připojení**. V rozevíracím seznamu vyberte **LiveRamp**. 

1. Vyberte **Další** a zvolte **Sadu zákaznických dat**, kterou chcete rozšířit o data identity od společnosti LiveRamp. Můžete vybrat entitu *Zákazník* a rozšířit všechny profily vašich zákazníků, nebo vyberte entitu *segmentu* a rozšiřte pouze profily zákazníků obsažené v tomto segmentu. 

1. Vyberte **Další** a definujte, který typ polí z vašich sjednocených profilů by se měl použít k hledání odpovídajících identifikačních dat LiveRamp. Vyžadováno je alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**. 

   > [!TIP]
   > Čím více identifikátorů a polí klíče mapujete, tím větší je pravděpodobnost vyšší míry shody 

1. Mapujte pole z vaší sjednocené entity *Zákazník*, která bude použita pro hledání shody s grafem AbiliTec ID společnosti LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti mapování dat pro rozšíření daty LiveRamp.":::

1. Výběrem možnosti **Další** dokončete mapování polí. 

1. Zadejte **Název** rozšíření a **Výstupní entitu**. 

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigurace připojení pro LiveRamp 

Abyste mohli [konfigurovat připojení](connections.md), musíte být správcem. Při konfiguraci rozšíření vyberte příkaz **Přidat připojení** nebo přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Podokno konfigurace pro nastavení připojení ke službě LiveRamp AbiliTec.":::

1. V poli **Zobrazovaný název** zadejte název připojení. 

1. Zadejte platné ID klienta LiveRamp a tajný kód. 

1. Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**. 

1. Vyberte **Ověřit** k ověření konfigurace. 

1. Připojení dokončíte výběrem možnosti **Uložit**. 

## <a name="enrichment-results"></a>Výsledky rozšíření 

Chcete-li zahájit proces rozšíření, vyberte Spustit v panelu příkazů. Můžete také nechat systém automaticky spustit rozšíření jako součást  [plánované aktualizace](system.md#schedule-tab). Doba zpracování závisí na velikosti vašich zákaznických dat. 

Po dokončení procesu rozšíření si můžete prohlédnout nově rozšířená data zákaznických profilů v části  **Moje rozšíření**. Dále najdete čas poslední aktualizace a počet rozšířených profilů. 

Výběrem volby  **Zobrazit rozšířená** data získáte přístup k podrobnému zobrazení každého rozšířeného profilu. 

## <a name="next-steps"></a>Další kroky

Stavte na svých rozšířených zákaznických údajích. Použijte ID AbiliTec ke konsolidaci zákaznických profilů do osobního zobrazení. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů 

Když povolíte aplikaci Dynamics 365 Customer Insights přenos dat do služby LiveRamp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft taková data přenese na váš pokyn, ale vy jste odpovědní za zajištění toho, že LiveRamp splňuje veškeré vaše případné povinnosti týkající se ochrany soukromí nebo zabezpečení. Další informace najdete v [prohlášení o ochraně osobních údajů společnosti Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Tuto funkci rozšíření může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
