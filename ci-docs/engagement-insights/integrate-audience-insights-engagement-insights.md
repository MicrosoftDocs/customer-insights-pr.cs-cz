---
title: Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení
description: Vytvořte aktivní propojení mezi přehledy cílových skupin a přehledy zapojení, abyste povolili obousměrné sdílení dat.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0fdbc93292291814b2e1a62fee2c5ff796ae14e2
ms.sourcegitcommit: 4e5b7ec50c7612765a9ec2c8673e0cc43b357abb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487099"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrace mezi přehledy cílových skupin a přehledy zapojení propojuje prostředí z obou funkcí a umožňuje sdílení dat obousměrně mezi nimi.

Pomocí jednotných profilů a segmentů z přehledy cílových skupin získáte další možnosti analýzy v přehledech zapojení. Exportujte události, které mají vysokou obchodní hodnotu, z přehledů zapojení. Pomocí těchto událostí můžete přidávat data do sjednocených profilů v přehledech cílových skupin.

## <a name="prerequisites"></a>Požadavky

- Profily přehledů cílových skupin musí být uloženy v účtu Azure Data Lake Storage, který vlastníte, nebo ve spravovaném jezeře [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). 
- Vaše prostředí přehledů cílových skupin by mělo mít přidružené prostředí Dataverse. A pokud to prostředí také používá Dataverse pro ukládání dat, nezapomeňte zaškrtnout možnost **Povolit sdílení dat** v přehledech cílových skupin. Více informací najdete v části [Vytvoření a konfigurace placeného prostředí v přehledech cílových skupin](../audience-insights/get-started-paid.md)
- Pro přehledy cílových skupin a přehledy zapojení potřebujete oprávnění správce.
- Propojená prostředí musí být ve stejné geografické oblasti.

> [!NOTE]
> - Pokud je vaše předplatné přehledů cílových skupin zkušební verzí, která využívá datové jezero interně spravované přehledy cílových skupin, kontaktujte [pirequest@microsoft.com](mailto:pirequest@microsoft.com) ohledně pomoci. 
> - Pokud vaše prostředí přehledů cílových skupin používá vaše vlastní Azure Data Lake Storage pro ukládání dat, musíte do účtu úložiště přidat instanční objekt Azure přehledů zapojení. Podrobnosti najdete v části [Připojení k účtu Azure Data Lake Storage s instančním objektem Azure pro přehledy cílových skupin](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Vytvoření propojení prostředí

Odkaz na prostředí můžete vytvořit aktualizací nastavení **Správce** > **Prostředí** v přehledech zapojení.

**Jak vytvořit aktivní propojení mezi přehledy cílových skupin a přehledy zapojení**

1. Na stránce **Správce prostředí** vyberte kartu **Propojit prostředí**.

    :::image type="content" source="media/integrate1.png" alt-text="Nastavení prostředí.":::

1. Vyberte **Nastavit prostředí** v levém horním rohu nebo ve spodní části obrazovky.

     :::image type="content" source="media/integrate2.png" alt-text="Vyberte prostředí přehledů cílových skupin.":::

1. Vyberte prostředí cílových skupin a poté vyberte **Další** pro dokončení. Nyní můžete pro propojená prostředí vybrat volitelné funkce.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Povolte atributy a segmenty sjednocených profilů přehledů cílových skupin

Po propojení můžete pro propojená prostředí vybrat volitelné funkce. Tyto funkce povolují sjednocené atributy a segmenty profilu z cílových skupin pro interaktivní analýzu zákaznických dat.

**Analyzovat webová data v přehledech zapojení**

1. Na sránce **Správce prostředí** zapněte přepínač **Sdílet data z přehledů cílových skupin s přehledy zapojení** a poté vyberte **Další**.

    :::image type="content" source="media/integrate4.png" alt-text="Vybrat funkce.":::

1. Vyberte atributy sjednocených profilů, které se stanou dimenzemi v přehledech zapojení. (Ne všechny atributy jsou užitečné dimenze. Například není pravděpodobné, že byste to potřebovali **Křestní jméno** nebo **Příjmení** jako atribut pro analýzu akcí vašeho webu.)

    :::image type="content" source="media/integrate5.png" alt-text="Kurátorovat dimenze.":::

   >[!NOTE]
   > Všechny atributy profilu cílových, které představují identifikátory (jako např **ID** a **alternativní ID**) jsou odfiltrovány z dostupných atributů a stanou se dimenzemi v přehledech zapojení.

1. Až budete s výběrem atributů hotovi, vyberte **Další**.
1. Přidejte uživatele, kteří mohou zobrazit dimenze a segmenty profilu přehledů cílových skupin v přehledech zapojení.

    :::image type="content" source="media/integrate6.png" alt-text="Správa přístupu k zákaznickým datům":::

   > [!IMPORTANT]
   > Pokud v tomto kroku uživatele výslovně nepřidáte, data budou před uživateli skryta v přehledech zapojení.
   > Aby se segmenty přehledů cílových skupin zobrazovaly v přehledech zapojení, musíte nejprve[spustit slučovací a navazující procesy](../audience-insights/merge-entities.md). Následné procesy jsou důležité, protože generují jedinečnou tabulku, která připravuje segmenty přehledů cílových skupin ke sdílení s přehledy zapojení. (Pokud je naplánována aktualizace systému, bude automaticky zahrnovat navazující procesy.)

1. Zkontrolujte svůj výběr a poté vyberte **Dokončit**.

    :::image type="content" source="media/integrate7.png" alt-text="Zkontrolujte nastavení zákaznických dat.":::

## <a name="export-refined-events-to-audience-insights"></a>Export upřesněných akcí do přehledů cílových skupin

Po vytvoření propojení mezi prostředími můžete exportovat upřesněné události z přehledů zapojení do přehledů cílových skupin a přijímat je jako nové zdroj dat. 

Další informace najdete v části [Integrace webových dat z přehledů zapojení s přehledů cílových skupin](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
