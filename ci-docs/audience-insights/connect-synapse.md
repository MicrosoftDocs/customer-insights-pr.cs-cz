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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356016"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Připojení datového zdroje dat Azure Synapse (Preview)

Azure Synapse Analytics je podniková analytická služba, která urychluje čas potřebný k získání přehledů napříč datovými sklady a velkými datovými systémy. Azure Synapse Analytics spojuje to nejlepší z technologií SQL používaných v podnikových datových skladech, technologie Spark používané pro velká data, průzkumníka dat pro analýzu protokolů a časových řad, kanály pro integraci dat a ETL/ELT a hlubokou integraci s dalšími službami Azure, jako je např Power BI, Cosmos DB a AzureML.

Další informace naleznete v tématech [Přehled Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Předpoklady

Pro konfiguraci připojení z Customer Insights je nutné splnit následující předpoklady Azure Synapse.

> [!IMPORTANT]
> Nezapomeňte nastavit všechna **přiřazení rolí**, jak je popsáno.  

## <a name="prerequisites-in-customer-insights"></a>Předpoklady v Customer Insights

* Máte roli **správce** v Customer Insights. Více informací o [oprávněních uživatele v přehledech cílové skupiny](permissions.md#assign-roles-and-permissions).

V Azure: 

- Aktivní předplatné Azure.

- Pokud používáte nový účet Azure Data Lake Storage Gen2, *objekt zabezpečení služby* pro přehledy cílové skupiny vyžaduje oprávnění **Přispěvatel dat v objektu blob úložiště**. Další informace o [připojení k Azure Data Lake Storage s instančním objektem pro přehledy cílových skupin](connect-service-principal.md). Úložiště Data Lake Gen2 **musí mít** povolen [hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).

- Ve skupině prostředků je umístěn pracovní prostor Azure Synapse ,*instanční objekt služby* a *uživatel pro přehledy cílové skupiny* musí mít přiděleno alespoň jedno oprávnění **Čtenář**. Další informace viz [Přiřazení rolí Azure pomocí webu Azure Portal](/azure/role-based-access-control/role-assignments-portal).

- *Uživatel* potřebuje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a propojena s pracovním prostorem Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita pracovního prostoru Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vyžaduje oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a připojena k pracovnímu prostoru Azure Synapse. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- V pracovním prostoru Azure Synapse musí mít *instanční objekt pro přehledy cílové skupiny* přiřazenou roli **Správce Synapse**. Další informace viz [Jak nastavit řízení přístupu pro pracovní prostor Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

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
