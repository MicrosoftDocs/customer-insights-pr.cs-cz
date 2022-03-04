---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti subjektů údajů pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350261"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žádosti o práva subjektu údajů (DSR) v rámci GDPR

Obecné nařízení Evropské unie o ochraně osobních údajů (GDPR) je v platnosti od 25. května 2018. Poskytuje jednotlivcům významná práva týkající se jejich údajů. GDPR se zabývá ochranou a umožněním osobních práv jednotlivců. Více informací o závazku společnosti Microsoft k zabezpečení a dodržování předpisů si můžete přečíst v [Centru zabezpečení Microsoft](https://www.microsoft.com/trust-center).

Zavázali jsme se pomáhat našim zákazníkům splnit jejich požadavky GDPR. Zahrnuje právo na mazání a export dat, která zahrnují osobní údaje, jako jsou ID uživatelů, telefonní čísla a e-mailové adresy. Správci mohou implementovat požadavky uživatelů na odstranění nebo export osobních údajů.

## <a name="audience-insights"></a>Přehledy pro cílovou skupinu

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpověď na žádosti subjektů údajů o odstranění údajů v rámci GDPR pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights

Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR). Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požadavků na vymazání subjektu údajů

Přehledy cílové skupiny nabízí následující integrované prostředí k odstranění osobních údajů konkrétního zákazníka nebo uživatele:

- **Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v původním zdroj dat.
- **Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Správa požadavků na odstranění zákaznických dat

Správce Customer Insights může podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**
3. Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:
   1. Vyberte (...) a poté volbu **Aktualizovat**.
   2. Zkontrolujte stav zdroje dat ve volbě **Stav**. Zaškrtnutí znamená, že aktualizace proběhla úspěšně. Výstražný trojúhelník znamená, že se něco pokazilo. Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Správa požadavků na výmaz GDPR pro zákaznická data.](audience-insights/media/gdpr-data-sources.png "Správa požadavků na výmaz GDPR pro zákaznická data")

##### <a name="manage-delete-requests-for-user-data"></a>Správa žádostí o odstranění údajů uživatele

Správce Customer Insights může odstranit údaje o uživatelích Customer Insights podle těchto kroků:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.
3. Zaškrtněte políčko pro uživatele, kterého chcete smazat.
4. Vyberte **Odstranit**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR

V rámci našeho závazku s vámi spolupracovat na vaší cestě k obecnému nařízení o ochraně údajů (GDPR) jsme vyvinuli dokumentaci, která vám pomůže s přípravou. Tato dokumentace popisuje kroky, které můžete dnes podniknout k podpoře dodržování předpisů GDPR, když používáte přehledy cílové skupiny.

#### <a name="manage-export-and-view-requests"></a>Spravujte žádosti o export a zobrazení

Právo na přenositelnost údajů umožňuje subjektům údajů požádat o kopii svých osobních údajů v elektronickém formátu (definovaném jako „strukturovaný, běžně používaný, strojově čitelný a interoperabilní formát“), který lze předat jinému správci údajů.

##### <a name="export-customer-data-tenant-admin"></a>Export údajů zákazníka (správce klienta)

Správce klienta může exportovat údaje pomocí následujícího postupu:

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu zákazníka v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného zákazníka.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

##### <a name="export-user-data-tenant-admin"></a>Export údajů uživatele (správce klienta)

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu uživatele v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného uživatele.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

## <a name="consent-management-preview"></a>Správa souhlasu (Preview)

Funkce správy souhlasu neshromažďuje uživatelská data přímo. Importuje a zpracovává pouze data souhlasu poskytnuté uživateli v jiných aplikacích.

Chcete-li odebrat data souhlasu konkrétních uživatelů, odstraňte je ze zdrojů dat ingestovaných funkcí správy souhlasu. Po aktualizaci zdroje dat budou odebraná data odstraněna také v Centru souhlasu. Aplikace, které používají entitu souhlasu, odstraní také data, která byla odstraněna ze zdroje po [aktualizaci](audience-insights/system.md#refresh-processes). Zdroje dat doporučujeme aktualizovat krátce po reakci na žádost subjektu údajů o odebrání dat uživatele ze všech ostatních procesů a aplikací.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]