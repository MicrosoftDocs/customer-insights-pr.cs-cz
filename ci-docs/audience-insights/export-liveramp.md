---
title: 'Konektor LiveRamp '
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226344"
---
# <a name="export-segments-to-liverampreg-preview"></a>Export segmentů do LiveRamp&reg; (náhled)

Aktivujte data na LiveRamp a spojte se s více než 500 platformami v digitálních, sociálních a televizních zařízeních. Pracujte s vašimi daty v LiveRampu na cílení, potlačení a personalizaci reklamních kampaní.

## <a name="prerequisites-for-a-connection"></a>Předpoklady pro připojení

- K použití tohoto konektoru potřebujete předplatné LiveRamp.
- Chcete-li získat předplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) přímo. [Další informace o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Nastavení propojení s LiveRamp

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **LiveRamp** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Uživatelské jméno** a **Heslo** pro váš účet LiveRamp Secure FTP (SFTP).
Tato pověření se mohou lišit od vašich pověření LiveRamp Onboarding.

1. Vyberte **Ověřit** a otestujte připojení k LiveRamp.

1. Po úspěšném ověření poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení v části LiveRamp. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. V poli **Vyberte svůj identifikátor klíče** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon**, který chcete poslat do LiveRampu pro rozlišení identity.
   > [!div class="mx-imgBorder"]
   > ![Konektor LiveRamp s mapováním atributů.](media/export-liveramp-segments.png "Konektor LiveRamp s mapováním atributů")

1. Mapujte odpovídající atributy ze své entity *Zákazník* pro vybraný identifikátor klíče.

1. Vyberte **Přidat atribut** k mapování více atributů pro odeslání na LiveRamp.

   > [!TIP]
   > Odesláním dalších atributů identifikátoru klíče na server LiveRamp pravděpodobně dosáhnete vyšší míry shody.

1. Vyberte segmenty, které chcete exportovat do LiveRamp.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Liveramp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Liveramp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
