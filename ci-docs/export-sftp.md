---
title: Export dat do hostitelů SFTP (Preview) (obsahuje video)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do umístění SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207221"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Export dat do hostitelů SFTP (Preview)

Využijte svá zákaznická data v aplikacích třetích stran a exportujte je do umístění Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Předpoklady

- Dostupnost hostitele SFTP a odpovídajících pověření.

## <a name="known-limitations"></a>Známá omezení

- Cíle SFTP za branami firewall v současnosti nejsou podporovány.
- Běh exportu závisí na výkonu vašeho systému. Jako minimální konfiguraci vašeho serveru doporučujeme dvě jádra CPU a 1 GB paměti.
- Až 100 milionů zákaznických profilů, což může trvat 90 minut při použití doporučené minimální konfigurace dvou jader CPU a 1 GB paměti.
- Pokud pro ověřování používáte klíč SSH, musíte [vytvořit svůj soukromý klíč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako formát PEM nebo SSH.COM. Pokud používáte Putty, převeďte svůj soukromý klíč jeho exportem jako Open SSH. Podporovány jsou následující formáty privátního klíče:
  - RSA ve formátu OpenSSL PEM a ssh.com
  - DSA ve formátu OpenSSL PEM a ssh.com
  - ECDSA 256/384/521 ve formátu OpenSSL PEM
  - ED25519 a RSA ve formátu klíče OpenSSH

## <a name="set-up-connection-to-sftp"></a>Nastavení propojení k SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **SFTP**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte, zda se chcete provádět ověřování prostřednictvím SSH nebo uživatelského jména a hesla pro vaše připojení a zadejte potřebné podrobnosti. Pokud pro ověřování používáte klíč SSH, musíte [vytvořit svůj soukromý klíč](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) jako formát PEM nebo SSH.COM. Pokud používáte Putty, převeďte svůj soukromý klíč jeho exportem jako Open SSH. Podporovány jsou následující formáty privátního klíče:
   - RSA ve formátu OpenSSL PEM a ssh.com
   - DSA ve formátu OpenSSL PEM a ssh.com
   - ECDSA 256/384/521 ve formátu OpenSSL PEM
   - ED25519 a RSA ve formátu klíče OpenSSH

1. Vyberte **Ověřit** pro otestování připojení.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části SFTP. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Vyberte, zda chcete exportovat data **komprimovaná jako gzip** nebo **rozbalená** a vyberte **oddělovač polí** pro exportované soubory.

1. Vyberte entity, například segmenty, které chcete exportovat.

   > [!NOTE]
   > Každá vybraná entita bude při exportu rozdělena maximálně na pět výstupních souborů.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Export entit, které obsahují velké množství dat, může vést k více souborům CSV ve stejné složce pro každý export. K rozdělení exportů dochází z důvodu výkonu, aby se minimalizovala doba potřebná k dokončení exportu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
