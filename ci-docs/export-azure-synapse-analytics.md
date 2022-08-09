---
title: Export dat do Azure Synapse Analytics (Preview)
description: Zjistěte, jak nakonfigurovat připojení do Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196386"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Export dat do Azure Synapse Analytics (Preview)

Azure Synapse je analytická služba, která zrychluje čas na nahlédnutí napříč datovými sklady a systémy velkých objemů dat. Data služby Customer Insights můžete přijímat a používat v [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Předpoklady

> [!NOTE]
> Nezapomeňte nastavit všechna **přiřazení rolí**, jak je popsáno.

- V Customer Insights musí mít váš uživatelský účet Azure Active Directory (AD) roli [Správce](permissions.md#assign-roles-and-permissions).

V Azure:

- Aktivní předplatné Azure.

- Pokud používáte nový účet Azure Data Lake Storage Gen2, [instanční objekt pro Customer Insights](connect-service-principal.md) má oprávnění **Přispěvatel dat objektů blob úložiště**. Úložiště Data Lake Gen2 **musí mít** povolen [hierarchický obor názvů](/azure/storage/blobs/data-lake-storage-namespace).

- Ve skupině zdrojů, kde se nachází aplikace Azure Synapse workspace, musí mít *instanční objekt* a *uživatel Azure AD s oprávněním správce v Customer Insights* přiřazeni alespoň [oprávnění](/azure/role-based-access-control/role-assignments-portal) **Čtenář**.

- Uživatel *Azure AD s oprávněním správce v Customer Insights* má oprávnění **Přispěvatel dat objektů blob úložiště** v účtu Azure Data Lake Storage Gen2, kde jsou data umístěna a propojena s aplikací Azure Synapse workspace. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Spravovaná identita aplikace Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* má oprávnění **Přispěvatel dat úložiště objektů blob** u účtu Azure Data Lake Storage Gen2, kde jsou umístěna data a připojena k aplikaci Azure Synapse workspace. Přečtěte si více o [používání portálu Azure pro přiřazení role Azure pro přístup k datům objektů blob a fronty](/azure/storage/common/storage-auth-aad-rbac-portal) a [oprávněních pro přispěvatele dat objektů blob úložiště](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- V aplikaci Azure Synapse workspace musí mít *instanční objekt pro Customer Insights* [přiřazenu roli](/azure/synapse-analytics/security/how-to-set-up-access-control) **Správce Synapse**.

## <a name="set-up-connection-to-azure-synapse"></a>Nastavení propojení k Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a vyberte **Azure Synapse Analytics**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vyberte nebo vyhledejte předplatné, ve kterém chcete použít data Customer Insights. Jakmile je vybráno předplatné, můžete také vybrat **Pracovní prostor**, **Účet úložiště** a **Kontejner**.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

## <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)] Pro konfiguraci exportu se sdíleným připojením potřebujete v Customer Insights minimálně oprávnění **Přispěvatel**.

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **Propojení pro export** vyberte propojení v části Azure Synapse Analytics. Pokud není k dispozici propojení , kontaktujte správce.

1. Poskytují rozpoznatelné **zobrazované jméno** pro váš export a **název databáze**. Export vytvoří novou [databázi jezera Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) v pracovním prostoru definovaném v připojení.

1. Vyberte entity, do kterých chcete exportovat do Azure Synapse Analytics.
   > [!NOTE]
   > Zdroje dat založené na [složce Common Data Model](connect-common-data-model.md) nejsou podporovány.

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Chcete-li dotazovat data, která byla exportována do Synapse Analytics, potřebujete přístup **Čtenář dat objektu blob úložiště** k cílovému úložišti v pracovním prostoru exportů.

## <a name="update-an-export"></a>Aktualizace exportu

1. Přejděte na **Data** > **Exporty**.

1. V žádosti, kterou chcete aktualizovat, vyberte **Upravit**.

   - **Přidejte** nebo **Odeberte** entity z výběru. Pokud jsou entity z výběru odebrány, nebudou odstraněny z databáze Synapse Analytics. Budoucí aktualizace dat však neaktualizuje odebrané entity v této databázi.

   - **Změna názvu databáze** vytvoří novou databázi Synapse Analytics. Databáze s názvem, který byl nakonfigurován dříve, neobdrží žádné aktualizace v budoucích aktualizacích.

[!INCLUDE [footer-include](includes/footer-banner.md)]
