---
title: Export dat do Azure Data Lake Storage Gen2 (Preview)
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196432"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Export dat do Azure Data Lake Storage Gen2 (Preview)

Uložte si data Customer Insights v účtu Data Lake Storage Gen2, nebo ho použijte k přenosu dat do jiných aplikací.

## <a name="prerequisites"></a>Předpoklady

- [Účet úložiště pro použití s Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Jestliže musíte vyhledat název a klíč účtu úložiště, podívejte se do části [Správa nastavení účtu úložiště v Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontejner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Známá omezení

- U Azure Data Lake Storage Gen 2 si můžete vybrat mezi [úrovní výkonu Standard a Premium](/azure/storage/blobs/create-data-lake-storage-account). Pokud zvolíte úroveň výkonu Premium, vyberte [jako typ účtu objekty blob prémiového bloku](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Nastavení připojení pro Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Data Lake Gen 2**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části Azure Data Lake. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte název složky pro úložiště Azure Data Lake Storage Gen 2.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportovaná data jsou uložena v kontejneru úložiště Azure Data Lake Gen 2, který jste nakonfigurovali.

> [!TIP]
> Export entit, které obsahují velké množství dat, může vést k více souborům CSV ve stejné složce pro každý export. K rozdělení exportů dochází z důvodu výkonu, aby se minimalizovala doba potřebná k dokončení exportu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
