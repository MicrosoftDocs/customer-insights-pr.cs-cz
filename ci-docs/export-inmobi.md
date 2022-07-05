---
title: Export dat Customer Insights do InMobi
description: Zjistěte, jak nakonfigurovat připojení a export do InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056536"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Export seznamu segmentů a dalších dat do InMobi (preview)

Exportujte seznamy segmentů nebo jiná data z vaší instance Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Předpoklady

1. Máte [účet InMobi](https://www.inmobi.com/) a přihlašovací údaje správce.
1. Máte název účtu úložiště Azure Blob Storage a odpovídající klíč účtu. Další informace viz [Správa nastavení účtu úložiště na portálu Azure](/azure/storage/common/storage-account-manage). V účtu úložiště je kontejner, do kterého lze exportovat data inMobi. Další informace naleznete v tématu [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi vytvoří přímé připojení k vašemu Blob Storage a nakonfiguruje automatický import vašich dat do InMobi. Chcete-li zahájit proces, kontaktujte svého zástupce InMobi.

## <a name="known-limitations"></a>Známá omezení

1. U Azure Blob Storage si můžete vybrat mezi [Úrovní výkonu Standard a Premium](/azure/storage/blobs/storage-blob-performance-tiers). Pokud zvolíte úroveň výkonu Premium, vyberte [jako typ účtu objekty blob prémiového bloku](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Nastavte připojení k Azure Blob Storage a nakonfigurujte export

1. Postupujte podle pokynů k [nastavte připojení k vašemu Azure Blob Storage](export-azure-blob-storage.md).
2. Postupujte podle pokynů ke [konfiguraci exportu](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
