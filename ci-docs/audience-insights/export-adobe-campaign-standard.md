---
title: Export dat Customer Insights do Adobe Campaign Standard
description: Naučte se používat segmenty přehledů cílových skupin v Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760273"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Použití segmentů Customer Insights v Adobe Campaign Standard (Preview)

Jako uživatel přehledů cílových skupin pro Dynamics 365 Customer Insights jste možná vytvořili segmenty, které vám pomohou zefektivnit marketingové kampaně cílením na relevantní cílové skupiny. Chcete-li použít segment z přehledů cílových skupin v Adobe Experience Platform a aplikacích, jako je Adobe Campaign Standard, musíte postupovat podle několika kroků uvedených v tomto článku.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a>Požadavky

-   Licence služby Dynamics 365 Customer Insights
-   Licence Adobe Campaign Standard
-   Účet Azure Blob Storage

## <a name="campaign-overview"></a>Přehled kampaně

Abyste lépe pochopili, jak můžete použít segmenty z přehledů cílových skupin v Adobe Experience Platform, pojďme se podívat na fiktivní ukázkovou kampaň.

Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném. Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné. Chcete-li si tyto zákazníky udržet, chcete jim zaslat propagační nabídku e-mailem pomocí aplikace Adobe Campaign Standard.

V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň. Tento článek se nezabývá případem použití kampaně vícekrát. Přehledy cílových skupin a Adobe Campaign Standard však lze nakonfigurovat tak, aby fungovaly i pro scénář opakující se kampaně.

## <a name="identify-your-target-audience"></a>Identifikace cílové skupiny

V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou k dispozici v přehledech cílové skupiny a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.

[Segment, který jste definovali v přehledech cílové skupiny](segments.md), má název **ChurnProneCustomers** a těmto zákazníkům plánujete poslat e-mailovou propagaci.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka. Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.

## <a name="export-your-target-audience"></a>Export cílové skupiny

### <a name="configure-a-connection"></a>Konfigurace připojení

S identifikovanou cílovou skupinou můžeme nakonfigurovat export z přehledů cílové skupiny do účtu Azure Blob Storage.

1. Ve statistikách cílové skupiny přejděte na **Správce** > **Připojení**.

1. Vyberte **Přidat připojení** a zvolte **Adobe Campaign** ke konfiguraci propojení nebo vyberte **Nastavit** v dlaždici **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurační dlaždice pro Adobe Campaign Standard.":::

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Zadejte **Název účtu**, **Klíč účtu** a **Kontejner** pro účet Azure Blob Storage, kam chcete segment exportovat.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. "::: 

   - Další informace o tom, jak najít název účtu úložiště Azure Blob a klíč účtu, viz [Správa nastavení účtu úložiště v portálu Azure](/azure/storage/common/storage-account-manage).

   - Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dokončete propojení výběrem možnosti **Uložit**.

### <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení v části Adobe Campaign. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zvolte segment, který chcete exportovat. V tomto příkladu je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. Vyberte **Další**.

1. Nyní namapujeme **zdrojová** pole ze segmentu přehledů cílové skupiny na **cílové** názvy polí ve schématu profilu Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapování polí pro konektor Adobe Campaign Standard.":::

   Pokud chcete přidat další atributy, vyberte **Přidat atribut**. Cílový název se může lišit od názvu zdrojového pole, takže stále můžete mapovat výstup segmentu z přehledů cílové skupiny do Adobe Campaign Standard, pokud pole v obou systémech nemají stejný název.

   > [!NOTE]
   > Jako pole identity se používá e-mailová adresa, ale k mapování dat do Adobe Campaign Standard můžete použít jakýkoli jiný identifikátor z vašeho zákaznického profilu přehledů cílové skupiny.

1. Zvolte **Uložit**.

Po uložení cíle exportu jej najdete v části **Data** > **Exporty**.

Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#run-exports-on-demand). Export bude spuštěn také s každou [plánovanou aktualizací](system.md).

> [!NOTE]
> Zajistěte, aby počet záznamů v exportovaném segmentu byl v povoleném limitu vaší licence Adobe Campaign Standard.

Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše. Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:

*%ContainerName%/CustomerInsights_%instanceID%/% název_cíle_exportu%_%segmentname%_%timestamp%.csv*

Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurace Adobe Campaign Standard

Segment exportovaný z přehledů cílové skupiny obsahuje sloupce, které jste vybrali při definování cíle exportu v předchozím kroku. Tato data lze použít k [vytváření profilů v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Chcete-li použít segment v Adobe Campaign Standard, musíme rozšířit schéma profilu v Adobe Campaign Standard tak, aby zahrnovalo další dvě pole. Naučte se [rozšířit zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) o nová pole v Adobe Campaign Standard.

V našem příkladu jsou tato pole *Název segmentu a Datum segmentu (volitelně)*.

Tato pole použijeme k identifikaci profilů v Adobe Campaign Standard, na které chceme tuto kampaň cílit.

Pokud v Adobe Campaign Standard neexistují žádné záznamy kromě těch, které se chystáte importovat, můžete tento krok přeskočit.

## <a name="import-data-into-adobe-campaign-standard"></a>Import dat do Adobe Campaign Standard

Nyní, když je vše připraveno, musíme importovat připravená data cílové skupiny z přehledů cílové skupiny do Adobe Campaign Standard, čímž vytvoříme profily. Naučte se [importovat profily v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocí pracovního postupu.

Pracovní postup importu na obrázku níže je konfigurován tak, aby se spouštěl každých 8 hodin, a hledá exportované segmenty přehledů cílové skupiny (soubor .csv v Azure Blob Storage). Pracovní postup extrahuje obsah souboru CSV v určeném pořadí sloupců. Tento pracovní postup byl vytvořen tak, aby prováděl základní zpracování chyb a zajistil, aby měl každý záznam e-mailovou adresu před vložením dat do Adobe Campaign Standard. Pracovní postup také extrahuje název segmentu z názvu souboru před provedením operace upsert na data profilu ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Screenshot pracovního postupu importu v uživatelském rozhraní Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Načtení cílové skupiny v Adobe Campaign Standard

Jakmile jsou data importována do Adobe Campaign Standard, [můžete vytvořit pracovní postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [zadat dotaz](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) na zákazníky na základě polí *Název segmentu* a *Datum segmentu* a vybrat profily, které byly identifikovány pro naši ukázkovou kampaň.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard

Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e-mail s nabídkou obnovení z Adobe Campaign Standard.":::
