---
title: Export segmentů do LiveRamp (náhled)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196708"
---
# <a name="export-segments-to-liverampreg-preview"></a>Export segmentů do LiveRamp&reg; (náhled)

Aktivujte data na LiveRamp a spojte se s více než 500 platformami v digitálních, sociálních a televizních zařízeních. Pracujte s vašimi daty v LiveRampu na cílení, potlačení a personalizaci reklamních kampaní.

## <a name="prerequisites"></a>Předpoklady

- K použití tohoto konektoru potřebujete předplatné LiveRamp. Chcete-li získat předplatné, [kontaktujte LiveRamp](https://liveramp.com/contact/) přímo. [Další informace o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Známá omezení

- Export LiveRamp používá export SFTP. Cíle SFTP za branami firewall v současnosti nejsou podporovány.
- Pokud pro ověřování používáte klíč SSH, musíte [vytvořit svůj soukromý klíč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako formát PEM nebo SSH.COM. Pokud používáte Putty, převeďte svůj soukromý klíč jeho exportem jako Open SSH. Podporovány jsou následující formáty privátního klíče:
  - RSA ve formátu OpenSSL PEM a ssh.com
  - DSA ve formátu OpenSSL PEM a ssh.com
  - ECDSA 256/384/521 ve formátu OpenSSL PEM
  - ED25519 a RSA ve formátu klíče OpenSSH
- Běh exportu závisí na výkonu vašeho systému. Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.
- Export entit s až 100 miliony zákaznických profilů může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti.
- Skutečný počet profilů (nebo dat), které můžete exportovat do služby LiveRamp, závisí na vašem předplatné s LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Nastavení propojení s LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **LiveRamp**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte, zda se chcete provádět ověřování prostřednictvím SSH nebo uživatelského jména a hesla pro vaše připojení a zadejte potřebné podrobnosti.

1. Vyberte **Ověřit** a otestujte připojení k LiveRamp.

1. Po úspěšném ověření zkontrolujte [oznámení o ochraně osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části LiveRamp. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. V poli **Připojit data** vyberte **E-mail**, **Jméno a adresa** nebo **Telefon**, který chcete poslat do služby LiveRamp pro rozpoznání identity.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Konektor LiveRamp s mapováním atributů.":::

1. Mapujte odpovídající atributy ze své entity *Zákazník* pro vybraný identifikátor klíče.

1. Vyberte **Přidat atribut** k mapování více atributů pro odeslání na LiveRamp.

   > [!TIP]
   > Odesláním dalších atributů identifikátoru klíče na server LiveRamp pravděpodobně dosáhnete vyšší míry shody.

1. Vyberte segmenty, které chcete exportovat.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
