---
title: 'Konektor LiveRamp '
description: Naučte se, jak exportovat data do služby LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597549"
---
# <a name="liverampreg-connector-preview"></a>konektor LiveRamp&reg; (preview)

Aktivujte data v LiveRamp a propojte se s více než 500 platformami napříč digitálními, sociálními a televizními ekosystémy. Pracujte s vašimi daty v LiveRampu na cílení, potlačení a personalizaci reklamních kampaní.

## <a name="prerequisites"></a>Požadavky

- K použití tohoto konektoru potřebujete předplatné LiveRamp.
- Chcete-li získat předplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) přímo. [Další informace o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Připojte se k LiveRampu

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. V dlaždici **LiveRamp** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.

1. Zadejte **Uživatelské jméno** a **Heslo** pro váš účet LiveRamp Secure FTP (SFTP).
Tato pověření se mohou lišit od vašich pověření LiveRamp Onboarding.

1. Vyberte **Ověřit** a otestujte připojení k LiveRamp.

1. Po úspěšném ověření poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Vyberte **Další** pro nastavení konektoru LiveRamp.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V poli **Vyberte svůj identifikátor klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon**, který chcete poslat do LiveRampu pro rozlišení identity.

1. Mapujte odpovídající atributy z unifikované entity zákazníka na vybraný identifikátor klíče.

1. Vyberte **Přidat atribut**, chcete-li mapovat další atributy k odeslání na LiveRamp.

   > [!TIP]
   > Odesláním dalších atributů identifikátoru klíče na server LiveRamp pravděpodobně dosáhnete vyšší míry shody.

1. Vyberte segmenty, které chcete exportovat do LiveRamp.

1. Zvolte **Uložit**.

> [!div class="mx-imgBorder"]
> ![Konektor LiveRamp s mapováním atributů](media/export-liveramp-segments.png "Konektor LiveRamp s mapováním atributů")

## <a name="export-the-data"></a>Export dat

Export bude zahájen brzy, jakmile budou splněny všechny předpoklady pro export. Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).
Po úspěšném dokončení exportu se můžete přihlásit k LiveRamp Onboarding a aktivovat a distribuovat svá data.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Liveramp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Liveramp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

[!INCLUDE[footer-include](../includes/footer-banner.md)]