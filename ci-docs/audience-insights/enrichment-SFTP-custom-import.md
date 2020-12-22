---
title: Rozšíření pomocí vlastního importu SFTP
description: Obecné informace o rozšíření pomocí vlastního importu SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568420"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="ba80b-103">Rozšíření profilů zákazníků o vlastní data (Preview)</span><span class="sxs-lookup"><span data-stu-id="ba80b-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="ba80b-104">Vlastní import prostřednictvím protokolu SFTP (Secure File Transfer Protocol) umožňuje importovat data, která nemusí projít procesem sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="ba80b-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="ba80b-105">Je to flexibilní, bezpečný a snadný způsob, jak přenést svá data.</span><span class="sxs-lookup"><span data-stu-id="ba80b-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="ba80b-106">Vlastní import SFTP lze použít v kombinaci s [exportem SFTP](export-sftp.md), který vám umožní exportovat data profilu zákazníka, která jsou potřebná pro rozšíření.</span><span class="sxs-lookup"><span data-stu-id="ba80b-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="ba80b-107">Data lze poté zpracovat, rozšířit a vlastní import SFTP lze použít k přenesení rozšířených dat zpět do přehledů cílové skupiny v Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba80b-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ba80b-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba80b-108">Prerequisites</span></span>

<span data-ttu-id="ba80b-109">Chcete-li nakonfigurovat vlastní import SFTP, musíte splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="ba80b-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ba80b-110">Máte přihlašovací údaje uživatele (uživatelské jméno a heslo) pro umístění SFTP, odkud budou importována data.</span><span class="sxs-lookup"><span data-stu-id="ba80b-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="ba80b-111">Máte adresu URL a číslo portu (obvykle 22) pro hostitele STFP.</span><span class="sxs-lookup"><span data-stu-id="ba80b-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="ba80b-112">Máte název souboru a umístění souboru, který se má importovat na hostitele SFTP.</span><span class="sxs-lookup"><span data-stu-id="ba80b-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="ba80b-113">Existuje soubor *model.json*, který určuje schéma pro data, která mají být importována.</span><span class="sxs-lookup"><span data-stu-id="ba80b-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="ba80b-114">Tento soubor musí být ve stejném adresáři jako soubor, který chcete importovat.</span><span class="sxs-lookup"><span data-stu-id="ba80b-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="ba80b-115">Máte oprávnění pro [správu](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="ba80b-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="ba80b-116">Konfigurace</span><span class="sxs-lookup"><span data-stu-id="ba80b-116">Configuration</span></span>

1. <span data-ttu-id="ba80b-117">Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="ba80b-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="ba80b-118">V **dlaždici vlastního importu SFTP** vyberte **Rozšířit moje data**.</span><span class="sxs-lookup"><span data-stu-id="ba80b-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba80b-119">![Dlaždice vlastního importu SFTP](media/SFTP_Custom_Import_tile.png "Dlaždice vlastního importu SFTP")</span><span class="sxs-lookup"><span data-stu-id="ba80b-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="ba80b-120">Vyberte **Začít** a zadejte přihlašovací údaje a adresu serveru SFTP.</span><span class="sxs-lookup"><span data-stu-id="ba80b-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="ba80b-121">Například sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="ba80b-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="ba80b-122">Zadejte název souboru, který obsahuje data, a cestu k souboru na serveru SFTP, pokud není v kořenové složce.</span><span class="sxs-lookup"><span data-stu-id="ba80b-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="ba80b-123">Potvrďte všechny vstupy volbou **Připojit k vlastnímu importu**.</span><span class="sxs-lookup"><span data-stu-id="ba80b-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba80b-124">![Informační rámeček s konfigurací vlastního importu SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Informační rámeček s konfigurací vlastního importu SFTP")</span><span class="sxs-lookup"><span data-stu-id="ba80b-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="ba80b-125">Definování mapování polí</span><span class="sxs-lookup"><span data-stu-id="ba80b-125">Defining field mappings</span></span> 

<span data-ttu-id="ba80b-126">Adresář obsahující soubor, který se má importovat na server SFTP, musí také obsahovat soubor *model.json*.</span><span class="sxs-lookup"><span data-stu-id="ba80b-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="ba80b-127">Tento soubor definuje schéma, které se má použít pro import dat.</span><span class="sxs-lookup"><span data-stu-id="ba80b-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="ba80b-128">Schéma musí používat [Common Data Model](https://docs.microsoft.com/common-data-model/) pro zadání mapování polí.</span><span class="sxs-lookup"><span data-stu-id="ba80b-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="ba80b-129">Jednoduchý příklad souboru model.json vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="ba80b-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="ba80b-130">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="ba80b-130">Enrichment results</span></span>

<span data-ttu-id="ba80b-131">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="ba80b-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ba80b-132">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba80b-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba80b-133">Doba zpracování bude záviset na velikosti dat, která mají být importována, a na připojení k serveru SFTP.</span><span class="sxs-lookup"><span data-stu-id="ba80b-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="ba80b-134">Po dokončení procesu rozšíření můžete zkontrolovat nově importovaná data v sekci **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="ba80b-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="ba80b-135">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="ba80b-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ba80b-136">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="ba80b-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba80b-137">Další kroky</span><span class="sxs-lookup"><span data-stu-id="ba80b-137">Next steps</span></span>

<span data-ttu-id="ba80b-138">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="ba80b-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ba80b-139">Vytvořte [segmenty](segments.md), [míry](measures.md) a [exportujte data](export-destinations.md) pro zajištění prostředí na míru zákazníkům.</span><span class="sxs-lookup"><span data-stu-id="ba80b-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


