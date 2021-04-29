---
title: Rozšíření pomocí vlastního importu SFTP
description: Obecné informace o rozšíření pomocí vlastního importu SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896273"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="932c6-103">Rozšíření profilů zákazníků o vlastní data (Preview)</span><span class="sxs-lookup"><span data-stu-id="932c6-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="932c6-104">Vlastní import protokolu SFTP (Secure File Transfer Protocol) umožňuje importovat data, která nemusí projít procesem sjednocení dat.</span><span class="sxs-lookup"><span data-stu-id="932c6-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="932c6-105">Je to flexibilní, bezpečný a snadný způsob, jak přenést svá data.</span><span class="sxs-lookup"><span data-stu-id="932c6-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="932c6-106">Vlastní import SFTP lze použít v kombinaci s [exportem SFTP](export-sftp.md), který vám umožní exportovat data profilu zákazníka, která jsou potřebná pro rozšíření.</span><span class="sxs-lookup"><span data-stu-id="932c6-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="932c6-107">Data lze poté zpracovat, rozšířit a vlastní import SFTP lze použít k přenesení rozšířených dat zpět do přehledů cílové skupiny v Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="932c6-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="932c6-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="932c6-108">Prerequisites</span></span>

<span data-ttu-id="932c6-109">Chcete-li nakonfigurovat vlastní import SFTP, musíte splnit následující předpoklady:</span><span class="sxs-lookup"><span data-stu-id="932c6-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="932c6-110">Máte název souboru a umístění (cestu) souboru, který se má importovat do hostitele SFTP.</span><span class="sxs-lookup"><span data-stu-id="932c6-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="932c6-111">Tady je soubor *model.json*, který určuje [schéma Common Data Model](/common-data-model/) pro data k importu.</span><span class="sxs-lookup"><span data-stu-id="932c6-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="932c6-112">Tento soubor musí být ve stejném adresáři jako soubor, který chcete importovat.</span><span class="sxs-lookup"><span data-stu-id="932c6-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="932c6-113">Správce již nakonfiguroval připojení SFTP *nebo* máte oprávnění [správce](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="932c6-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="932c6-114">Budete potřebovat přihlašovací údaje uživatele, adresu URL a číslo portu pro umístění SFTP, ze kterého chcete importovat data.</span><span class="sxs-lookup"><span data-stu-id="932c6-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="932c6-115">Konfigurace importu</span><span class="sxs-lookup"><span data-stu-id="932c6-115">Configure the import</span></span>

1. <span data-ttu-id="932c6-116">Přejděte na **Data** > **Obohacení** a vyberte kartu **Objevit**.</span><span class="sxs-lookup"><span data-stu-id="932c6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="932c6-117">V **dlaždici Vlastní import SFTP** vyberte **Rozšířit moje údaje** a pak vyberte **Začínáme**.</span><span class="sxs-lookup"><span data-stu-id="932c6-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Dlaždice vlastního importu SFTP":::

1. <span data-ttu-id="932c6-119">V rozevíracím seznamu vyberte [propojení](connections.md).</span><span class="sxs-lookup"><span data-stu-id="932c6-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="932c6-120">Pokud není k dispozici propojení , kontaktujte správce.</span><span class="sxs-lookup"><span data-stu-id="932c6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="932c6-121">Pokud jste správce, můžete vytvořit připojení výběrem možnosti **Přidat připojení** a volbou **Vlastní import SFTP** z rozevíracího seznamu.</span><span class="sxs-lookup"><span data-stu-id="932c6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="932c6-122">Vybrané připojení potvrďte výběrem **Propojit s Custom Import**.</span><span class="sxs-lookup"><span data-stu-id="932c6-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="932c6-123">Vyberte **Další** a zadejte **název souboru** a **cestu** datového souboru, který chcete importovat.</span><span class="sxs-lookup"><span data-stu-id="932c6-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Screenshot při zadávání datového umístění.":::

1. <span data-ttu-id="932c6-125">Vyberte **Další** a zadejte název rozšíření a název výstupní entity.</span><span class="sxs-lookup"><span data-stu-id="932c6-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="932c6-126">Po kontrole vašich voleb vyberte **Uložit rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="932c6-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="932c6-127">Konfigurace připojení pro vlastní import SFTP</span><span class="sxs-lookup"><span data-stu-id="932c6-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="932c6-128">Abyste mohli konfigurovat propojení, musíte být správce.</span><span class="sxs-lookup"><span data-stu-id="932c6-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="932c6-129">Při konfiguraci rozšíření vyberte **Přidat připojení** *nebo* přejděte na **Správce** > **Připojení** a v dlaždici Vlastní import vyberte **Nastavit**.</span><span class="sxs-lookup"><span data-stu-id="932c6-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="932c6-130">Do pole **Zobrazované jméno** zadejte jméno.</span><span class="sxs-lookup"><span data-stu-id="932c6-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="932c6-131">Zadejte platné uživatelské jméno, heslo a adresu URL hostitele pro server STFP, na kterém se nacházejí importovaná data.</span><span class="sxs-lookup"><span data-stu-id="932c6-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="932c6-132">Projděte si a poskytněte svůj souhlas s **Ochranou osobních údajů a dodržování předpisů** výběrem zaškrtávacího políčka **Souhlasím**.</span><span class="sxs-lookup"><span data-stu-id="932c6-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="932c6-133">Vyberte **Ověřit** k ověření konfigurace.</span><span class="sxs-lookup"><span data-stu-id="932c6-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="932c6-134">Po dokončení ověřování lze připojení uložit kliknutím na **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="932c6-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="932c6-135">![Stránka konfigurace připojení pro Experian](media/enrichment-SFTP-connection.png "Stránka konfigurace připojení pro Experian")</span><span class="sxs-lookup"><span data-stu-id="932c6-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="932c6-136">Definování mapování polí</span><span class="sxs-lookup"><span data-stu-id="932c6-136">Defining field mappings</span></span> 

<span data-ttu-id="932c6-137">Adresář obsahující soubor, který se má importovat na server SFTP, musí také obsahovat soubor *model.json*.</span><span class="sxs-lookup"><span data-stu-id="932c6-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="932c6-138">Tento soubor definuje schéma, které se má použít pro import dat.</span><span class="sxs-lookup"><span data-stu-id="932c6-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="932c6-139">Schéma musí používat [Common Data Model](/common-data-model/) pro zadání mapování polí.</span><span class="sxs-lookup"><span data-stu-id="932c6-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="932c6-140">Jednoduchý příklad souboru model.json vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="932c6-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="932c6-141">Výsledky rozšíření</span><span class="sxs-lookup"><span data-stu-id="932c6-141">Enrichment results</span></span>

<span data-ttu-id="932c6-142">Chcete-li zahájit proces obohacení, vyberte **Spustit** z panelu příkazů.</span><span class="sxs-lookup"><span data-stu-id="932c6-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="932c6-143">Můžete také nechat systém automaticky spustit obohacení jako součást [plánované aktualizace](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="932c6-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="932c6-144">Doba zpracování bude záviset na velikosti dat, která mají být importována, a na připojení k serveru SFTP.</span><span class="sxs-lookup"><span data-stu-id="932c6-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="932c6-145">Po dokončení procesu rozšíření můžete zkontrolovat nově importovaná data v sekci **Moje rozšíření**.</span><span class="sxs-lookup"><span data-stu-id="932c6-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="932c6-146">Dále najdete čas poslední aktualizace a počet obohacených profilů.</span><span class="sxs-lookup"><span data-stu-id="932c6-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="932c6-147">Výběrem volby **Zobrazit rozšířená data** získáte přístup k podrobnému zobrazení každého rozšířeného profilu.</span><span class="sxs-lookup"><span data-stu-id="932c6-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="932c6-148">Další kroky</span><span class="sxs-lookup"><span data-stu-id="932c6-148">Next steps</span></span>

<span data-ttu-id="932c6-149">Stavte na svých obohacených zákaznických údajích.</span><span class="sxs-lookup"><span data-stu-id="932c6-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="932c6-150">Vytvořte [segmenty](segments.md), [míry](measures.md) a [exportujte data](export-destinations.md) pro zajištění prostředí na míru zákazníkům.</span><span class="sxs-lookup"><span data-stu-id="932c6-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
