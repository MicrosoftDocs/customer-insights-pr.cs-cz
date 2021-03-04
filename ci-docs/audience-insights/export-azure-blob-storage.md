---
title: Export dat Customer Insights do úložiště Azure Blob
description: Naučte se, jak nakonfigurovat připojení k úložišti Azure Blob.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269184"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor pro úložiště Azure Blob (náhled)

Uchovávejte svá data Customer Insights v úložišti Azure Blob nebo jej použijte k přenosu dat do jiných aplikací.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurace konektoru pro úložiště Azure Blob

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.

1. V **Azure Blob Storage** vyberte **Založit**.

1. Vložte **Název účtu**, **Klíč účtu** a **Kontejner** pro váš účet úložiště Azure Blob.
    - Další informace o tom, jak najít název účtu úložiště Azure Blob a klíč účtu, viz [Správa nastavení účtu úložiště v portálu Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Zadejte rozpoznatelný název cíle do pole **Zobrazovaný název**.

1. Vyberte **Další**.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Zvolte **Uložit**.

Exportovaná data jsou uložena v konfiguračním úložném kontejneru Azure Blob. Ve vašem kontejneru se automaticky vytvoří následující cesty ke složkám:

- Pro zdrojové entity a entity generované systémem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pro exportované entity bude umístěn na úrovni %ExportDestinationName%
  - Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md#export-data-on-demand). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]