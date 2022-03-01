---
title: Export dat Customer Insights do Azure Data Lake Storage Gen2
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477171"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Konektor pro Azure Data Lake Storage Gen2 (Preview)

Uchovávejte svá data Customer Insights ve službě Azure Data Lake Storage Gen2 nebo ji použijte k jejich přenosu do jiných aplikací.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfigurace konektoru pro Azure Data Lake Storage Gen2

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. Pod **Azure Data Lake Storage Gen2** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.

1. Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.
    - Chcete-li vědět, jak vytvořit účet úložiště pro použití se službou Azure Data Lake Storage Gen2, projděte si téma [Vytvoření účtu úložiště](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Další informace, jak vyhledat název účtu úložiště Azure Data Lake Gen2 a klíč účtu, najdete v článku [Správa nastavení účtu úložiště v Azure Portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Vyberte **Další**.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md#export-data-on-demand). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).
