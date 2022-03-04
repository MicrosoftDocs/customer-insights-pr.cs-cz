---
title: Export údajů ze služby Customer Insights do Adobe Experience Platform
description: Zjistěte, jak používat segmenty přehledů cílových skupin v Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9010af3c42823ce0dd8685bf71c109aef8d3f635
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227704"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Použití segmentů Customer Insights v Adobe Experience Platform (Preview)

Jako uživatel přehledů cílové skupiny v Dynamics 365 Customer Insights jste možná vytvořili segmenty, které vám pomohou zefektivnit marketingové kampaně cílením na relevantní cílovou skupinu. Chcete-li použít segment z přehledů cílových skupin v Adobe Experience Platform a aplikacích jako je Adobe Campaign Standard, musíte postupovat podle několika kroků uvedených v tomto článku.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a>Požadavky

-   Licence služby Dynamics 365 Customer Insights
-   Licence služby Adobe Experience Platform
-   Licence Adobe Campaign Standard
-   Účet Azure Blob Storage

## <a name="campaign-overview"></a>Přehled kampaně

Abyste lépe porozuměli tomu, jak můžete používat segmenty přehledů cílových skupin v Adobe Experience Platform, podívejme se na fiktivní ukázkovou kampaň.

Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném. Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné. Abyste si udrželi tyto zákazníky, chcete jim zaslat propagační nabídku e-mailem pomocí Adobe Experience Platform.

V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň. Tento článek se nezabývá případem použití kampaně vícekrát.

## <a name="identify-your-target-audience"></a>Identifikace cílové skupiny

V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou k dispozici v přehledech cílové skupiny a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.

[Segment, který jste definovali v přehledech cílové skupiny](segments.md), má název **ChurnProneCustomers** a těmto zákazníkům plánujete poslat e-mailovou propagaci.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka. Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.

## <a name="export-your-target-audience"></a>Export cílové skupiny

S identifikovanou cílovou skupinou můžeme nakonfigurovat export z přehledů cílové skupiny do účtu Azure Blob Storage.

### <a name="configure-a-connection"></a>Konfigurace připojení

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Blob Storage** nebo vyberte **Nastavit** v dlaždici **Azure Blob Storage** ke konfiguraci propojení.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Dlaždice konfigurace pro Azure Blob Storage."::: 

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Pokud neprovedete žádnou akci, výchozí bude Aministrátoři. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Jméno účtu**, **Klíč účtu** a **Kontejner** pro účet Blob Storage, kam chcete segment exportovat.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. "::: 
   
    - Další informace o vyhledání účtu Blob Storage a klíči účtu najdete v tématu [Správa nastavení účtu úložiště na webu Azure Portal](/azure/storage/common/storage-account-manage).
    - Informace o tom, jak vytvořit kontejner, viz [Vytvoření kontejneru](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dokončete propojení výběrem možnosti **Uložit**. 

### <a name="configure-an-export"></a>Konfigurace exportu

Tento export můžete nakonfigurovat, pokud máte přístup k připojení tohoto typu. Další informace viz [Oprávnění potřebná ke konfiguraci exportu](export-destinations.md#set-up-a-new-export).

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový export, vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení z části Azure Blob Storage. Pokud nevidíte název této sekce, nemáte k dispozici žádná připojení tohoto typu.

1. Zvolte segment, který chcete exportovat. V tomto příkladu je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. Zvolte **Uložit**.

Po uložení cíle exportu jej najdete v části **Data** > **Exporty**.

Nyní můžete [exportovat segmentu na vyžádání](export-destinations.md#run-exports-on-demand). Export bude spuštěn také s každou [plánovanou aktualizací](system.md).

> [!NOTE]
> Zajistěte, aby počet záznamů v exportovaném segmentu byl v rámci povoleného limitu vaší licence Adobe Campaign Standard.

Exportovaná data jsou uložena v kontejneru úložiště Azure Blob, který jste nakonfigurovali výše. Ve vašem kontejneru se automaticky vytvoří následující cesta ke složce:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Soubor *model.json* pro exportované entity se nachází na úrovni *%ExportDestinationName%*.

Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definování datového modelu prostředí (XDM) v Adobe Experience Platform

Než lze exportovaná data z přehledů cílových skupin použít v Adobe Experience Platform, musíme definovat schéma datového modelu prostředí a [nakonfigurovat data pro profil zákazníka v reálném čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Zjistěte, [co je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a seznamte se se [základy kompozice schématu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importovat data do Adobe Experience Platform

Nyní, když je vše na svém místě, musíme importovat připravená data cílové skupiny z přehledů cílových skupin do Adobe Experience Platform.

Nejprve [vytvořte připojení zdroje Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Po definování zdrojového připojení [nakonfigurujte tok dat](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pro dávkové připojení cloudového úložiště k importu výstupu segmentu z přehledů cílových skupin do Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Vytvoření cílové skupiny v Adobe Campaign Standard

K odeslání e-mailu pro tuto kampaň použijeme Adobe Campaign Standard. Po importu dat do Adobe Experience Platform musíme [vytvořit cílovou skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard pomocí dat v Adobe Experience Platform.


Zjistěte, jak [používat nástroj pro tvorbu segmentů](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Campaign Standard k definování cílové skupiny na základě dat v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard

Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e -mail s nabídkou obnovení od Adobe Campaign Standard.":::
