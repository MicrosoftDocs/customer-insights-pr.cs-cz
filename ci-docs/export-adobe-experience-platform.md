---
title: Export segmentů do Adobe Experience Platform (preview)
description: Přečtěte si, jak používat segmenty Customer Insights v Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195282"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Export segmentů do Adobe Experience Platform (preview)

Exportujte segmenty, které cílí na relevantní publikum, do Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram zpracování kroků popsaných v tomto článku.":::

## <a name="prerequisites"></a>Předpoklady

- Licence Adobe Experience Platform.
- Licence Adobe Campaign Standard.
- Název a klíč [účtu Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account). Jestliže musíte vyhledat název a klíč, podívejte se do části [Správa nastavení účtu úložiště v Azure Portal](/azure/storage/common/storage-account-manage).
- [Kontejner Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Přehled kampaně

Chcete-li lépe porozumět tomu, jak můžete použít segmenty z Customer Insights v Adobe Experience Platform, podívejme se na fiktivní ukázkovou kampaň.

Předpokládejme, že vaše společnost nabízí svým zákazníkům v USA měsíční službu založenou na předplatném. Chcete identifikovat zákazníky, jejichž předplatná mají být obnovena v příštích osmi dnech, ale kteří dosud neobnovili své předplatné. Abyste si udrželi tyto zákazníky, chcete jim zaslat propagační nabídku e-mailem pomocí Adobe Experience Platform.

V tomto příkladu chceme jednou spustit propagační e-mailovou kampaň. Tento článek se nezabývá případem použití kampaně vícekrát.

## <a name="identify-your-target-audience"></a>Identifikace cílové skupiny

V našem scénáři předpokládáme, že e-mailové adresy zákazníků jsou dostupné v Customer Insights a jejich propagační preference byly analyzovány za účelem identifikace členů segmentu.

[Segment, který jste definovali v Customer Insights](segments.md) je nazýván **ChurnProneCustomers** a plánujete poslat těmto zákazníkům e-mailovou propagaci.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Screenshot stránky se segmenty s vytvořeným segmentem ChurnProneCustomers.":::

E-mail s nabídkou, který chcete odeslat, bude obsahovat křestní jméno, příjmení a datum ukončení předplatného zákazníka. Informuje zákazníky o slevě, kterou získají, pokud si předplatné obnoví před jeho koncem.

## <a name="export-your-target-audience"></a>Export cílové skupiny

Nakonfigurujeme export z Customer Insights do účtu Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Nastavení propojení s Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte **Přidat připojení** a zvolte **Azure Blob Storage**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zvolte, kdo může toto připojení používat. Ve výchozím nastavení jsou to pouze správci. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Zadejte **Jméno účtu**, **Klíč účtu** a **Kontejner** pro účet Blob Storage, kam chcete segment exportovat.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurace účtu úložiště. ":::

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Dokončete propojení výběrem možnosti **Uložit**.

### <a name="configure-an-export"></a>Konfigurace exportu

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Přejděte na **Data** > **Exporty**.

1. Vyberte **Přidat export**.

1. V poli **propojení pro export** vyberte propojení z části Azure Blob Storage. Pokud není k dispozici propojení , kontaktujte správce.

1. Zadejte název exportu.

1. Zvolte segment, který chcete exportovat. V tomto příkladu je to **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Screenshot uživatelského rozhraní pro výběr segmentu s vybraným segmentem ChurnProneCustomers.":::

1. Vyberte **Uložit**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Zajistěte, aby počet záznamů v exportovaném segmentu byl v rámci povoleného limitu vaší licence Adobe Campaign Standard.

Exportovaná data jsou uložena v konfiguračním úložném kontejneru Azure Blob Storage. Ve vašem kontejneru se automaticky vytvoří následující cesty ke složkám:

- Pro zdrojové entity a entity generované systémem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Soubor *model.json* pro exportované entity se nachází na úrovni *%ExportDestinationName%*.

  Příklad: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definování datového modelu prostředí (XDM) v Adobe Experience Platform

Než lze exportovaná data z Customer Insights použít v rámci Adobe Experience Platform, definujte schéma datového modelu zkušeností a [konfigurovat data pro profil zákazníka v reálném čase](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Zjistěte, [co je XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) a seznamte se se [základy kompozice schématu](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importovat data do Adobe Experience Platform

Importujte připravená cílová skupina data z Customer Insights do Adobe Experience Platform.

1. [Vytvořte připojení zdroje Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Nakonfigurujte tok dat](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pro dávkové připojení cloudového úložiště pro import segmentového výstupu z Customer Insights do Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Vytvoření cílové skupiny v Adobe Campaign Standard

K odeslání e-mailu pro tuto kampaň použijeme Adobe Campaign Standard.

1. [Vytvořte cílovou skupinu](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) v Adobe Campaign Standard využívající data v Adobe Experience Platform.

1. [Pomocí nástroje pro tvorbu segmentů](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) v Adobe Campaign Standard definujte cílovou skupinu na základě dat v Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Vytvoření a odeslání e-mailu pomocí Adobe Campaign Standard

Vytvořte obsah e-mailu a poté [otestujte a odešlete](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) svůj e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Ukázkový e -mail s nabídkou obnovení od Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
