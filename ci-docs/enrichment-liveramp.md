---
title: Rozšíření profilů zákazníků daty identity z LiveRamp (Preview)
description: Rozšiřte profily zákazníků daty LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237804"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Rozšíření profilů zákazníků daty identity z LiveRamp (Preview)

Společnost LiveRamp poskytuje deterministické offline rozlišení identity a konsolidaci zákaznických dat. Osobní identifikátory ve svých zákaznických datech můžete mapovat do grafu identity AbiliTec a přijímat ID AbiliTec. Tato ID pak můžete využít pro lepší sjednocení údajů o vašich zákaznících.

## <a name="supported-countriesregions"></a>Podporované země/oblasti

V současnosti podporujeme rozšíření zákaznických profilů o data LiveRamp pouze ve Spojených státech.

## <a name="prerequisites"></a>Předpoklady

- Aktivní předplatné LiveRamp. Chcete-li získat předplatné, kontaktujte tým svého účtu LiveRamp nebo napište na adresu [dynamics@liveramp.com](mailto:dynamics@liveramp.com).

- Aktivní předplatné AbiliTec s ID klienta a tajným kódem pro přístup k API. Další informace naleznete v tématu [Centrum vývojáře AbiliTec API](https://developers.liveramp.com/abilitec-api/).

- LiveRamp [připojení](connections.md) [konfiguruje](#configure-the-connection-for-liveramp) správce.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurace připojení pro LiveRamp

Musíte být [správce](permissions.md#admin) v Customer Insights aa mít aktivní ID a tajný kód klienta LiveRamp.

1. Při konfiguraci rozšíření vyberte příkaz **Přidat připojení** nebo přejděte na **Správa** > **Připojení** a vyberte **Nastavit** na dlaždici LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Podokno konfigurace pro nastavení připojení ke službě LiveRamp AbiliTec.":::

1. Zadejte název připojení a platné ID klienta LiveRamp a tajný kód.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Zvolte **Ověřit** pro ověření konfigurace a poté vyberte **Uložit**.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Identita** z LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Dlaždice identity na stránce s přehledem rozšíření.":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Vyberte připojení. Pokud není k dispozici propojení , kontaktujte správce.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o zákazníkovi** a zvolte profil nebo segment, které chcete obohatit o data identity z LiveRamp. Entita *Zákazník* rozšíří všechny profily vašich zákazníků zatímco segment rozšíří pouze profily zákazníků obsažené v tomto segmentu.

1. Definujte, který typ polí z vašich sjednocených profilů se má použít pro porovnávání dat identity z LiveRamp. Vyžadováno je alespoň jedno z polí **Jméno a adresa**, **Telefon** nebo **E-mail**. Pro vyšší přesnost shody přidejte další pole. Vyberte **Další**.

1. Namapujte pole na data identifikace z LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Možnosti mapování dat pro rozšíření daty LiveRamp.":::

1. Výběrem možnosti **Další** dokončete mapování polí.

1. Zadejte **Název** rozšíření a **název výstupní entity**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Spustit** k zahájení procesu obohacování nebo blízko k návratu na stránku **Rozšíření**.

## <a name="view-enrichment-results"></a>Zobrazení výsledků rozšiřování

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pokud je k dispozici možnost **Počet zákazníků obohacených o pole**, můžete procházet k podrobnostem pokrytí každého rozšířeného pole.

## <a name="next-steps"></a>Další kroky

Stavte na svých rozšířených zákaznických údajích. Použijte ID AbiliTec ke konsolidaci zákaznických profilů do osobního zobrazení.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
