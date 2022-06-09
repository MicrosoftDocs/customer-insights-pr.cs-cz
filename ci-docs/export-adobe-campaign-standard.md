---
title: Export dat Customer Insights do Adobe Campaign Standard
description: Přečtěte si, jak používat segmenty Customer Insights v Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645829"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Použití segmentů Customer Insights v Adobe Campaign Standard (Preview)

Jako uživatel Dynamics 365 Customer Insights jste možná vytvořili segmenty, abyste zefektivnili své marketingové kampaně cílením na relevantní publikum. Chcete-li použít segment z Customer Insights v Adobe Experience Platform a aplikacích jako Adobe Campaign Standard, musíte provést několik kroků popsaných v tomto článku.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a>Požadavky

-   Licence služby Dynamics 365 Customer Insights
-   Licence Adobe Campaign Standard
-   Účet Azure Blob Storage

## <a name="campaign-overview"></a>Přehled kampaně

Chcete-li lépe porozumět tomu, jak můžete použít segmenty z Customer Insights v Adobe Experience Platform, podívejme se na fiktivní ukázkovou kampaň.

Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném. Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné. Abyste si udrželi tyto zákazníky, chcete jim zaslat propagační nabídku e-mailem pomocí Adobe Campaign Standard.

V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň. Tento článek se nezabývá případem použití kampaně vícekrát. Nicméně, Customer Insights and Adobe Campaign Standard lze nakonfigurovat tak, aby fungovala i pro scénář opakujících se kampaní.

## <a name="identify-your-target-audience"></a>Identifikace cílové skupiny

V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou dostupné v a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.

[Segment, který jste definovali v Customer Insights](segments.md) je nazýván **ChurnProneCustomers** a plánujete poslat těmto zákazníkům e-mailovou propagaci.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka. Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.

## <a name="export-your-target-audience"></a>Export cílové skupiny

### <a name="configure-a-connection"></a>Konfigurace připojení

Když je naše cílová skupina identifikována, můžeme nakonfigurovat export do účtu Azure Blob Storage.

1. V Customer Insights přejděte na **Správce** > **Připojení**.

1. Vyberte **Přidat připojení** a zvolte **Adobe Campaign** ke konfiguraci připojení nebo vyberte **Nastavit** na dlaždici **Adobe Campaign**.

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

1. V poli **Připojení pro export** zvolte připojení z části Adobe Campaign. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zvolte segment, který chcete exportovat. V tomto příkladu je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. Vyberte **Další**.

1. Nyní namapujeme **Zdrojová** pole ze segmentu Customer Insights na názvy **Cílových** polí ve schématu profilu Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapování pole pro konektor Adobe Campaign Standard connector.":::

   Pokud chcete přidat další atributy, vyberte **Přidat atribut**. Název cíle se může lišit od názvu zdrojového pole, takže stále můžete mapovat výstup segmentu ze Customer Insights na Adobe Campaign Standard, pokud pole nemají v obou systémech stejný název.

   > [!NOTE]
   > E-mailová adresa se používá jako pole identity, ale k mapování dat můžete použít jakýkoli jiný identifikátor z profilu zákazníka do Adobe Campaign Standard.

1. Vyberte **Uložit**.

Po uložení cíle exportu jej najdete v části **Data** > **Exporty**.

Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#run-exports-on-demand). Export bude spuštěn také s každou [plánovanou aktualizací](system.md).

> [!NOTE]
> Zajistěte, aby počet záznamů v exportovaném segmentu byl v rámci povoleného limitu vaší licence Adobe Campaign Standard.

Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše. Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:

*%ContainerName%/CustomerInsights_%instanceID%/% název_cíle_exportu%_%segmentname%_%timestamp%.csv*

Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurace Adobe Campaign Standard

Exportované segmenty obsahují sloupce, které jste vybrali při definování cíle exportu v předchozím kroku. Tato data lze použít k [vytváření profilů v Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Chcete-li použít segment v Adobe Campaign Standard, musíme rozšířit schéma profilu v Adobe Campaign Standard, aby obsahovalo dvě další pole. Zjistěte, jak [rozšířit zdroj profilu](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) v Adobe Campaign Standard o nová pole.

V našem příkladu jsou tato pole *Název segmentu a Datum segmentu (volitelně)*.

Tato pole použijeme k identifikaci profilů v Adobe Campaign Standard, na které chceme pro tuto kampaň cílit.

Pokud nejsou žádné další záznamy Adobe Campaign Standard, kromě toho, co se chystáte importovat, můžete tento krok přeskočit.

## <a name="import-data-into-adobe-campaign-standard"></a>Import data do Adobe Campaign Standard

Nyní, když je vše na svém místě, musíme importovat připravená cílová skupina data z Customer Insights do Adobe Campaign Standard pro vytváření profilů. Zjistěte, [jak importovat profily do Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) pomocí pracovního postupu.

Pracovní postup importu na obrázku níže byl nakonfigurován tak, aby se spouštěl každých osm hodin a vyhledával exportované segmenty Customer Insights (soubor .csv v Azure Blob Storage). Pracovní postup extrahuje obsah souboru CSV v určeném pořadí sloupců. Tento pracovní postup byl vytvořen tak, aby prováděl základní zpracování chyb a zajistil, aby měl každý záznam e-mailovou adresu před hydratací dat Adobe Campaign Standard. Pracovní postup také extrahuje název segmentu z názvu souboru před upsertingem do dat profilu Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Snímek obrazovky pracovního postupu importu v uživatelském rozhraní Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Načtení cílové skupiny v Adobe Campaign Standard

Jakmile jsou data importována do Adobe Campaign Standard, [můžete vytvořit pracovní postup](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) a [dotazovat se](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) na zákazníky na základě *názvu segmentu* a *data segmentu* a vybrat profily, které byly identifikovány pro naši ukázkovou kampaň.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard

Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e -mail s nabídkou obnovení od Adobe Campaign Standard.":::