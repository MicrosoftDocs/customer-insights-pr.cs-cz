---
title: Export dat Customer Insights do služby Azure Blob Storage
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976126"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Export seznamu segmentů a dalších dat do služby Azure Blob Storage (náhled)

Uložte si data Customer Insights do služby Azure Blob Storage nebo je použijte k přenosu dat do jiných aplikací.

## <a name="set-up-the-connection-to-blob-storage"></a>Nastavení propojení s Blob Storage

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Blob Storage** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **jméno obchodního vztahu**, **klíč obchodního vztahu** a **kontejner** pro účet Blob Storage.
    - Další informace o vyhledání účtu Blob Storage a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).
    - Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat cíl**.

1. V poli **propojení pro export** vyberte propojení z části Azure Blob Storage. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab).     
Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

Exportovaná data jsou uložena v kontejneru úložiště Blob Storage, který jste nakonfigurovali. Ve vašem kontejneru se automaticky vytvoří následující cesty ke složkám:

- Pro zdrojové entity a entity generované systémem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json pro exportované entity bude mít úroveň %ExportDestinationName%
  - Příklad: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
