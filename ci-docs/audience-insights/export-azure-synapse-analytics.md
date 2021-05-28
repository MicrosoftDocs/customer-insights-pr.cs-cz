---
title: Export údajů ze služby Customer Insights do Azure Synapse Analytics
description: Zjistěte, jak nakonfigurovat připojení a exportovat je do Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977369"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Export dat do Azure Synapse Analytics (Preview)

Azure Synapse je analytická služba, která zrychluje čas na nahlédnutí napříč datovými sklady a systémy velkých objemů dat. Data služby Customer Insights můžete přijímat a používat v [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Požadavky

Pro konfiguraci připojení z Customer Insights je nutné splnit následující předpoklady Azure Synapse.

> [!NOTE]
> Nezapomeňte nastavit všechna **přiřazení rolí**, jak je popsáno.  

## <a name="prerequisites-in-customer-insights"></a>Předpoklady v Customer Insights

* V přehledech cílové skupiny máte roli **Administrátor**. Přečtěte si více o [nastavení uživatelských oprávnění ve statistikách cílové skupiny](permissions.md#assign-roles-and-permissions)

V Azure: 

- Aktivní předplatné Azure.

- Pokud používáte nový účet Azure Data Lake Storage Gen2, *objekt zabezpečení služby* pro přehledy cílové skupiny vyžaduje oprávnění **Přispěvatel dat v objektu blob úložiště**. Více informací získáte v tématu [Připojení účtu Azure Data Lake Storage Gen2 pomocí instančního objektu Azure pro přehledy cílové skupiny](connect-service-principal.md). Úložiště Data Lake Gen2 **musí mít** povolen [hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).

- Ve skupině prostředků je umístěn pracovní prostor Azure Synapse ,*instanční objekt služby* a *uživatel pro přehledy cílové skupiny* musí mít přiděleno alespoň jedno oprávnění **Čtenář**. Další informace viz [Přiřazení rolí Azure pomocí webu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Uživatel* potřebuje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a propojena s pracovním prostorem Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovního prostoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vyžaduje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a připojena k pracovnímu prostoru Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- V pracovním prostoru Azure Synapse musí mít *instanční objekt pro přehledy cílové skupiny* přiřazenou roli **Správce Synapse**. Další informace viz [Jak nastavit řízení přístupu pro pracovní prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Nastavení propojení a exportu do Azure Synapse

### <a name="configure-a-connection"></a>Konfigurace připojení

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Synapse Analytics** nebo vyberte **Nastavit** v dlaždici **Azure Synapse Analytics** ke konfiguraci připojení.

1. Dejte propojení rozpoznatelný název do pole Zobrazovaný název. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte nebo vyhledejte předplatné, ve kterém chcete použít data Customer Insights. Jakmile je vybráno předplatné, můžete také vybrat **Pracovní prostor**, **Účet úložiště** a **Kontejner**.

1. Propojení uložte výběrem tlačítka **Uložit**.

### <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **Připojení pro export** vyberte připojení v části **Azure Synapse Analytics**. Pokud nevidíte název této sekce, nemáte k dispozici žádná [připojení tohoto typu](connections.md).

1. Poskytují rozpoznatelné **zobrazované jméno** pro váš export a **název databáze**.

1. Vyberte entity, do kterých chcete exportovat Azure Synapse Analytics.

1. Zvolte **Uložit**.

Uložení exportu nespustí export okamžitě.

Export probíhá s každou [plánovanou aktualizací](system.md#schedule-tab). Můžete také [exportovat data na vyžádání](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Aktualizace exportu

1. Přejděte na **Data** > **Exporty**.

1. V žádosti, kterou chcete aktualizovat, vyberte **Upravit**.

   - **Přidejte** nebo **Odeberte** entity z výběru. Pokud jsou entity z výběru odebrány, nebudou odstraněny z databáze Synapse Analytics. Budoucí aktualizace dat však neaktualizuje odebrané entity v této databázi.

   - **Změna názvu databáze** vytvoří novou databázi Synapse Analytics. Databáze s názvem, který byl nakonfigurován dříve, neobdrží žádné aktualizace v budoucích aktualizacích.
