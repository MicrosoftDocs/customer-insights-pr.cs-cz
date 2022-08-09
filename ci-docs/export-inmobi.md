---
title: Export dat Customer Insights do InMobi
description: Zjistěte, jak nakonfigurovat připojení a export do InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195880"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Export dat Customer Insights do InMobi (Preview)

Exportujte seznamy segmentů nebo jiná data z vaší instance Customer Insights do [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Předpoklady

- [Účet InMobi](https://www.inmobi.com/) a přihlašovací údaje správce.
- Název a klíč [účtu Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Jestliže musíte vyhledat název a klíč, podívejte se do části [Správa nastavení účtu úložiště v Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontejner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container), do kterého exportujete data InMobi.
- InMobi vytvoří přímé připojení k vašemu Blob Storage a nakonfiguruje automatický import vašich dat do InMobi. Chcete-li zahájit proces, kontaktujte svého zástupce InMobi.

## <a name="known-limitations"></a>Známá omezení

- U Azure Blob Storage zvolte mezi [úrovní výkonu Standard a Premium](/azure/storage/blobs/storage-blob-performance-tiers). Pokud zvolíte úroveň výkonu Premium, vyberte [jako typ účtu objekty blob prémiového bloku](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Nastavení propojení s Azure Blob Storage

[Nastavení propojení s Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurace exportu

[Nakonfigurujte export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
