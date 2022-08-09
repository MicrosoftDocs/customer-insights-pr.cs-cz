---
title: Export dat do Azure Blob Storage (preview)
description: Zjistěte, jak nakonfigurovat propojení a exportovat je do Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195696"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Export dat do Azure Blob Storage (preview)

Uložte si data Customer Insights do služby Azure Blob Storage nebo je použijte k přenosu dat do jiných aplikací.

## <a name="prerequisites"></a>Předpoklady

- Název a klíč [účtu Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Jestliže musíte vyhledat název a klíč, podívejte se do části [Správa nastavení účtu úložiště v Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontejner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Známá omezení

- U Azure Blob Storage zvolte mezi [úrovní výkonu Standard a Premium](/azure/storage/blobs/storage-blob-performance-tiers). Pokud zvolíte úroveň výkonu Premium, vyberte [jako typ účtu objekty blob prémiového bloku](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Nastavení propojení s Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Blob Storage**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **jméno obchodního vztahu**, **klíč obchodního vztahu** a **kontejner** pro účet Blob Storage.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

Chcete-li nakonfigurovat tento export, musíte mít [oprávnění](export-destinations.md#set-up-a-new-export) pro tento typ připojení.

> [!IMPORTANT]
> Pokud jste pro účet Azure Blob Storage zapnuli [nastavení obnovitelného odstranění](/azure/storage/blobs/soft-delete-blob-enable), exporty se nezdaří. Chcete -li exportovat data do objektů BLOB, vypněte obnovitelné odstranění.

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení z části Azure Blob Storage. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zadejte název složky pro úložiště objektů Blob.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Exportovaná data jsou uložena v kontejneru úložiště Blob Storage, který jste nakonfigurovali. Ve vašem kontejneru se automaticky vytvoří následující cesty ke složkám:

- Pro zdrojové entity a entity generované systémem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Export entit, které obsahují velké množství dat, může vést k více souborům CSV ve stejné složce pro každý export. K rozdělení exportů dochází z důvodu výkonu, aby se minimalizovala doba potřebná k dokončení exportu.

- Soubor model.json pro exportované entity se nachází na úrovni *%ExportDestinationName%*.  
  
  Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
