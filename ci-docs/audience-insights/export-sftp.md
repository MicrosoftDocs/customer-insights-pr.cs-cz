---
title: Export dat Customer Insights do hostitelů SFTP
description: Naučte se, jak nakonfigurovat připojení k hostiteli SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643495"
---
# <a name="connector-for-sftp-preview"></a>Konektor pro SFTP (preview)

Konektor SFTP umožňuje bezpečně exportovat vaše zákaznická data, která pak můžete používat v aplikacích třetích stran, do hostitele SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Požadavky

- Dostupnost hostitele SFTP a odpovídající pověření.

## <a name="connect-to-sftp"></a>Připojit se k SFTP

1. Přejděte na **Správce** > **Cíle exportu**.

1. V **SFTP** vyberte **Založit**

1. Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.

1. Zadejte **Uživatelské jméno**, **Heslo** a **Název hostitele** pro váš účet SFTP. Příklad: Pokud je kořenová složka vašeho serveru SFTP /root/folder a chcete data exportovat do /root/folder/cilova_slozka_exportu_ci, měl by být hostitel sftp://<adresa_serveru>/cilova_slozka_exportu_ci".

1. Vyberte **Ověřit** pro otestování připojení.

1. Po úspěšném ověření zvolte, zda chcete exportovat data **Zazipovaná** nebo **Nezazipovaná** a vyberte **oddělovač pole** pro exportované soubory.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Vyberte **Další** pro spuštění konfigurace exportu.

## <a name="configure-the-connection"></a>Konfigurujte připojení

1. Vyberte **atributy zákazníka**, které chcete exportovat. Můžete exportovat jeden nebo více atributů.

1. Vyberte **Další**.

1. Vyberte segmenty, které chcete exportovat.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat prostřednictvím protokolu SFTP, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že cíl exportu splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
