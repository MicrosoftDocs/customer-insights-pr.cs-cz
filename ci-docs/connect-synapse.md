---
title: Ingestování dat z Azure Synapse Analytics
description: Použijte databázi v Azure Synapse jako zdroj dat v Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645793"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Připojení datového zdroje dat Azure Synapse (Preview)

Azure Synapse Analytics je podniková analytická služba, která urychluje čas potřebný k získání přehledů napříč datovými sklady a velkými datovými systémy. Azure Synapse Analytics spojuje to nejlepší z technologií SQL používaných v podnikových datových skladech, technologie Spark používané pro velká data, průzkumníka dat pro analýzu protokolů a časových řad, kanály pro integraci dat a ETL/ELT a hlubokou integraci s dalšími službami Azure, jako je např Power BI, Cosmos DB a AzureML.

Další informace naleznete v tématech [Přehled Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Předpoklady

Je třeba splnit následující předpoklady, abyste mohli nakonfigurovat připojení z Dynamics 365 Customer Insights do Azure Synapse.

> [!IMPORTANT]
> Nezapomeňte nastavit všechna **přiřazení rolí**, jak je popsáno.  

## <a name="prerequisites-in-customer-insights"></a>Předpoklady v Customer Insights

* Máte roli **správce** v Customer Insights. Více informací o [oprávněních uživatele v Customer Insights](permissions.md#assign-roles-and-permissions).

V Azure: 

- Aktivní předplatné Azure.

- Pokud používáte nový účet Azure Data Lake Storage Gen2, *instanční objekt pro Customer Insights* vyžaduje oprávnění **Přispěvatel dat objektů blob úložiště**. Další informace o [připojení k Azure Data Lake Storage s instančním objektem pro Customer Insights](connect-service-principal.md). Úložiště Data Lake Gen2 **musí mít** povolen [hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).

- Ve skupině zdrojů, kde se nachází Azure Synapse workspace, musí mít *instanční objekt* a *uživatel s Customer Insights* musí mít přiřazeno alespoň oprávnění **Čtenář**. Další informace viz [Přiřazení rolí Azure pomocí webu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Uživatel* potřebuje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a propojena s pracovním prostorem Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovního prostoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vyžaduje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a připojena k pracovnímu prostoru Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- V aplikaci Azure Synapse workspace musí mít *instanční objekt pro Customer Insights* přiřazenu roli **Správce Synapse**. Další informace viz [Jak nastavit řízení přístupu pro pracovní prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Připojení k databázím datových jezer v Azure Synapse Analytics

1. Přejděte na **Data** > **Zdroje dat**.

1. Vyberte **Přidat zdroj dat**.

1. Vyberte metodu **Azure Synapse Analytics (Preview)**.

1. Uveďte **Název** pro zdroj dat a vyberte **Další** k vytvoření zdroje dat. 

1. Zvolte [dostupné připojení](connections.md) do Azure Synapse Analytics nebo vytvořte nové.

1. Vyberte **Databáze jezera** z pracovního prostoru připojeného ve vybraném připojení Azure Synapse Analytics a vyberte **Další**.

1. Vyberte entity k ingestaci z připojené databáze. 

1. Volitelně vyberte datové entity, pro které chcete profilování dat povolit. 

1. Vyberte **Uložit**, použijte svůj výběr a zahajte zpracování dat z nově vytvořeného zdroje dat propojeného s tabulkami databáze jezera v Azure Synapse Analytics.
