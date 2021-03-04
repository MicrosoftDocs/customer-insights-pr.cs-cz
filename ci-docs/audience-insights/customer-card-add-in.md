---
title: Instalace a konfigurace doplňku karty zákazníka
description: Instalace a konfigurace doplňku karty zákazníka pro Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268036"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="75067-103">Doplněk karty zákazníka (preview)</span><span class="sxs-lookup"><span data-stu-id="75067-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="75067-104">Získejte kompletní přehled o svých zákaznících přímo v aplikacích Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75067-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="75067-105">Prohlédněte si demografické údaje, statistiky a časové harmonogramy činností pomocí doplňku karty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="75067-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75067-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="75067-106">Prerequisites</span></span>

- <span data-ttu-id="75067-107">Aplikace Dynamics 365 (například Centrum prodeje nebo Centrum služeb zákazníkům) verze 9.0 a novější s povoleným sjednoceným rozhraním.</span><span class="sxs-lookup"><span data-stu-id="75067-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="75067-108">Profily zákazníků [ingestované z aplikace Dynamics 365 pomocí Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="75067-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="75067-109">Uživatelé doplňku karty zákazníka musí být [přidáni jako uživatelé](permissions.md) v přehledech cílové skupiny.</span><span class="sxs-lookup"><span data-stu-id="75067-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="75067-110">[Konfigurované možnosti vyhledávání a filtrování](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="75067-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="75067-111">Ovládací prvek demografických údajů: V jednotném profilu zákazníka jsou k dispozici demografická pole (například věk nebo pohlaví).</span><span class="sxs-lookup"><span data-stu-id="75067-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="75067-112">Kontrola rozšíření: Vyžaduje aktivní [rozšíření](enrichment-hub.md) aplikované na profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="75067-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="75067-113">Ovládací prvek analytických nástrojů: Vyžaduje data generovaná pomocí Azure Machine Learning ([predikce](predictions.md) nebo [vlastní modely](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="75067-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="75067-114">Ovládací prvek měr: Vyžaduje [konfigurované míry](measures.md).</span><span class="sxs-lookup"><span data-stu-id="75067-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="75067-115">Ovládací prvek časové osy: Vyžaduje [konfigurované aktivity](activities.md).</span><span class="sxs-lookup"><span data-stu-id="75067-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="75067-116">Instalace doplňku karty zákazníka</span><span class="sxs-lookup"><span data-stu-id="75067-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="75067-117">Doplněk karty zákazníka je řešení pro aplikace pro zapojení zákazníků v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75067-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="75067-118">Chcete-li nainstalovat řešení, přejděte na AppSource a vyhledejte **Kartu zákazníka Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="75067-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="75067-119">Vyberte [Doplněk karty zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získat**.</span><span class="sxs-lookup"><span data-stu-id="75067-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="75067-120">K instalaci řešení se možná budete muset přihlásit pomocí svých přihlašovacích údajů pro aplikaci Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75067-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="75067-121">Instalace řešení do vašeho prostředí může nějakou dobu trvat.</span><span class="sxs-lookup"><span data-stu-id="75067-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="75067-122">Nakonfigurujte doplněk zákaznické karty</span><span class="sxs-lookup"><span data-stu-id="75067-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="75067-123">Jako správce přejděte na **Nastavení** v Dynamics 365 a vyberte **Řešení**.</span><span class="sxs-lookup"><span data-stu-id="75067-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="75067-124">Vyberte odkaz **Zobrazované jméno** řešení Doplněk karty zákazníka v **Dynamics 365 Customer Insights (preview)**.</span><span class="sxs-lookup"><span data-stu-id="75067-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75067-125">![Výběr zobrazovaného názvu](media/select-display-name.png "Výběr zobrazovaného názvu")</span><span class="sxs-lookup"><span data-stu-id="75067-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="75067-126">Vyberte **Přihlásit se** a zadejte přihlašovací údaje pro účet správce, pomocí kterého konfigurujete Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75067-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="75067-127">Zkontrolujte, zda blokování automaticky otevíraných oken prohlížeče neblokuje okno ověřování, když vyberete tlačítko **Přihlásit**.</span><span class="sxs-lookup"><span data-stu-id="75067-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="75067-128">Vyberte prostředí, ze které chcete načíst data.</span><span class="sxs-lookup"><span data-stu-id="75067-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="75067-129">Definujte, které pole se má mapovat na záznamy v aplikaci Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75067-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="75067-130">Chcete-li mapovat kontakt, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity kontaktu.</span><span class="sxs-lookup"><span data-stu-id="75067-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="75067-131">Chcete-li mapovat obchodní vztah, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity obchodního vztahu.</span><span class="sxs-lookup"><span data-stu-id="75067-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75067-132">![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")</span><span class="sxs-lookup"><span data-stu-id="75067-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="75067-133">Chcete-li uložit nastavení, vyberte tlačítko **Uložit konfiguraci**.</span><span class="sxs-lookup"><span data-stu-id="75067-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="75067-134">Dále musíte v Dynamics 365 přiřadit role zabezpečení, aby si uživatelé mohli přizpůsobit a vidět zákaznickou kartu.</span><span class="sxs-lookup"><span data-stu-id="75067-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="75067-135">V aplikaci Dynamics 365 přejděte do části **Nastavení** > **Zabezpečení** > **Uživatelé**.</span><span class="sxs-lookup"><span data-stu-id="75067-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="75067-136">Vyberte uživatele, kterým chcete upravit uživatelské role, a vyberte **Správa rolí**.</span><span class="sxs-lookup"><span data-stu-id="75067-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="75067-137">Přiřaďte roli **Úpravce karty Customer Insights** uživatelům, kteří přizpůsobí obsah zobrazený na kartě pro celou organizaci.</span><span class="sxs-lookup"><span data-stu-id="75067-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="75067-138">Přidání ovládacích prvků karty zákazníka do formulářů</span><span class="sxs-lookup"><span data-stu-id="75067-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="75067-139">Chcete-li přidat ovládací prvky zákaznické karty do kontaktního formuláře, přejděte na stránku **Nastavení** > **Přizpůsobení** v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75067-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="75067-140">Vyberte **Přizpůsobit systém**.</span><span class="sxs-lookup"><span data-stu-id="75067-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="75067-141">Vyhledejte entitu **Kontakt**, rozbalte ji a poté vyberte **Formuláře**.</span><span class="sxs-lookup"><span data-stu-id="75067-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="75067-142">Vyberte kontaktní formulář, do kterého chcete přidat ovládací prvky karty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="75067-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="75067-143">![Výběr formuláře kontaktu](media/contact-active-forms.png "Výběr formuláře kontaktu")</span><span class="sxs-lookup"><span data-stu-id="75067-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="75067-144">Chcete-li přidat ovládací prvek demografických údajů, v editoru formulářů přetáhněte libovolné pole z **Průzkumníka polí** na místo, kam chcete umístit ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="75067-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="75067-145">Vyberte pole ve formuláři, které jste právě přidali, a poté vyberte možnost **Změnit vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="75067-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="75067-146">Přejděte na kartu **Ovládací prvky** a zvolte **Přidat ovládací prvek**.</span><span class="sxs-lookup"><span data-stu-id="75067-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="75067-147">Vyberte jeden z dostupných vlastních ovládacích prvků a vyberte **Přidat**.</span><span class="sxs-lookup"><span data-stu-id="75067-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="75067-148">V dialogovém okně **Vlastnosti pole** zrušte zaškrtnutí políčka **Zobrazit popisek ve formuláři**.</span><span class="sxs-lookup"><span data-stu-id="75067-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="75067-149">Vyberte možnost **Web** pro ovládací prvekl.</span><span class="sxs-lookup"><span data-stu-id="75067-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="75067-150">Pro ovládací prvek Rozšíření vyberte typ rozšíření, který chcete zobrazit, konfigurací pole **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="75067-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="75067-151">Pro každý typ rozšíření přidejte samostatný ovládací prvek rozšíření.</span><span class="sxs-lookup"><span data-stu-id="75067-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="75067-152">Vyberte **Uložit** a **Publikovat**, chcete-li zveřejnit aktualizovaný kontaktní formulář.</span><span class="sxs-lookup"><span data-stu-id="75067-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="75067-153">Přejděte na publikovaný kontaktní formulář.</span><span class="sxs-lookup"><span data-stu-id="75067-153">Go to the published contact form.</span></span> <span data-ttu-id="75067-154">Uvidíte nově přidaný ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="75067-154">You'll see the newly added control.</span></span> <span data-ttu-id="75067-155">Možná se budete muset přihlásit při prvním použití.</span><span class="sxs-lookup"><span data-stu-id="75067-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="75067-156">Chcete-li přizpůsobit, co se má zobrazit na vlastním ovládacím prvku, vyberte tlačítko Upravit v pravém horním rohu.</span><span class="sxs-lookup"><span data-stu-id="75067-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="75067-157">Upgrade doplňku karty zákazníka</span><span class="sxs-lookup"><span data-stu-id="75067-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="75067-158">Doplněk karty zákazníka se neupgraduje automaticky.</span><span class="sxs-lookup"><span data-stu-id="75067-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="75067-159">Chcete-li upgradovat na nejnovější verzi, postupujte podle tohoto postupu v aplikaci Dynamics 365, která má nainstalovaný doplněk.</span><span class="sxs-lookup"><span data-stu-id="75067-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="75067-160">V aplikaci Dynamics 365 přejděte na **Nastavení** > **Vlastní nastavení** a vyberte **Řešení**.</span><span class="sxs-lookup"><span data-stu-id="75067-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="75067-161">V tabulce doplňků vyhledejte **CustomerInsightsCustomerCard** a vyberte řádek.</span><span class="sxs-lookup"><span data-stu-id="75067-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="75067-162">Na panelu akcí vyberte **Nainstalovat upgrade řešení**.</span><span class="sxs-lookup"><span data-stu-id="75067-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade řešení v oblasti Vlastní nastavení aplikací Dynamics 365":::

1. <span data-ttu-id="75067-164">Po spuštění procesu upgradu se zobrazí indikátor načítání, dokud se upgrade nedokončí.</span><span class="sxs-lookup"><span data-stu-id="75067-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="75067-165">Pokud není k dispozici žádná novější verze, zobrazí se při upgradu chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="75067-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]