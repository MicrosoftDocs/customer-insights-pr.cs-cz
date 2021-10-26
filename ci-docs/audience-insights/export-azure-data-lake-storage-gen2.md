---
title: Export dat Customer Insights do Azure Data Lake Storage Gen2
description: Naučte se konfigurovat připojení k Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605895"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Export seznamu segmentů a dalších dat do Azure Data Lake Storage Gen2 (náhled)

Uložte si data Customer Insights v účtu Data Lake Storage Gen2, nebo ho použijte k přenosu dat do jiných aplikací.

## <a name="known-limitations"></a>Známá omezení

1. Pro Azure Data Lake Storage Gen2 si můžete vybrat mezi [úrovní standardního a prémiového výkonu](/azure/storage/blobs/create-data-lake-storage-account), když vytváříte účet úložiště pro vaše datové jezero. Pokud zvolíte úroveň výkonu Premium, vyberte jako typ účtu objekty blob prémiového bloku. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Nastavení připojení pro Azure Data Lake Storage Gen2 


1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Data Lake Gen 2** pro konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro své úložiště Azure Data Lake Storage Gen2.
    - Chcete-li vědět, jak vytvořit účet úložiště pro použití se službou Azure Data Lake Storage Gen2, projděte si téma [Vytvoření účtu úložiště](/azure/storage/blobs/create-data-lake-storage-account). 
    - Další informace o názvu účtu úložiště Azure Data Lake Gen2 a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).

1. Dokončete propojení výběrem možnosti **Uložit**. 

## <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části **Azure Data Lake**. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zaškrtněte políčko vedle každé entity, kterou chcete exportovat do tohoto cíle.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand). 

Exportovaná data jsou uložena v kontejneru úložiště Azure Data Lake Gen 2, který jste nakonfigurovali. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
