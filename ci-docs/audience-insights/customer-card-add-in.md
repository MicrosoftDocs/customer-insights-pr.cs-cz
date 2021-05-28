---
title: Doplněk zákaznické karty pro aplikace Dynamics 365
description: Zobrazte data z přehledu cílové skupiny v aplikacích Dynamics 365 s tímto doplňkem.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059580"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="82dd2-103">Doplněk karty zákazníka (preview)</span><span class="sxs-lookup"><span data-stu-id="82dd2-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="82dd2-104">Získejte kompletní přehled o svých zákaznících přímo v aplikacích Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="82dd2-105">S doplňkem Zákaznická karta nainstalovaným v podporované aplikaci Dynamics 365 můžete zvolit zobrazení demografických údajů, přehledů a časových os aktivit.</span><span class="sxs-lookup"><span data-stu-id="82dd2-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="82dd2-106">Doplněk načte data z Customer Insights bez ovlivnění dat v připojené aplikaci Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="82dd2-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="82dd2-107">Prerequisites</span></span>

- <span data-ttu-id="82dd2-108">Doplněk funguje pouze s modelem řízenými aplikacemi Dynamics 365, jako je Sales nebo Customer Service, verze 9.0 a novější.</span><span class="sxs-lookup"><span data-stu-id="82dd2-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="82dd2-109">Aby se vaše data Dynamics 365 mapovala na profily zákazníků přehledů cílové skupiny, musí být [přijata z aplikace Dynamics 365 pomocí konektoru Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="82dd2-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="82dd2-110">Všichni uživatelé doplňku zákaznické karty Dynamics 365 musí být [přidáni jako uživatelé](permissions.md) v přehledech cílové skupiny, aby mohli zobrazovat data.</span><span class="sxs-lookup"><span data-stu-id="82dd2-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="82dd2-111">[Konfigurované možnosti vyhledávání a filtrování](search-filter-index.md) v přehledech cílové skupiny jsou vyžadovány, aby vyhledávání dat fungovalo.</span><span class="sxs-lookup"><span data-stu-id="82dd2-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="82dd2-112">Každý ovládací prvek doplňku závisí na konkrétních datech v přehledech cílové skupiny:</span><span class="sxs-lookup"><span data-stu-id="82dd2-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="82dd2-113">Ovládací prvek měr: Vyžaduje [konfigurované míry](measures.md).</span><span class="sxs-lookup"><span data-stu-id="82dd2-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="82dd2-114">Ovládání inteligence: Vyžaduje data generovaná pomocí [predikcí](predictions.md) nebo [vlastních modelů](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="82dd2-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="82dd2-115">Ovládací prvek demografických údajů: V jednotném profilu zákazníka jsou k dispozici demografická pole (například věk nebo pohlaví).</span><span class="sxs-lookup"><span data-stu-id="82dd2-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="82dd2-116">Kontrola rozšíření: Vyžaduje aktivní [rozšíření](enrichment-hub.md) aplikované na profily zákazníků.</span><span class="sxs-lookup"><span data-stu-id="82dd2-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="82dd2-117">Ovládací prvek časové osy: Vyžaduje [konfigurované aktivity](activities.md).</span><span class="sxs-lookup"><span data-stu-id="82dd2-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="82dd2-118">Instalace doplňku karty zákazníka</span><span class="sxs-lookup"><span data-stu-id="82dd2-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="82dd2-119">Doplněk karty zákazníka je řešení pro aplikace pro zapojení zákazníků v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="82dd2-120">Chcete-li nainstalovat řešení, přejděte na AppSource a vyhledejte **Kartu zákazníka Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="82dd2-121">Vyberte [Doplněk karty zákazníka v AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) a vyberte **Získat**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="82dd2-122">K instalaci řešení se možná budete muset přihlásit pomocí svých přihlašovacích údajů pro aplikaci Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="82dd2-123">Instalace řešení do vašeho prostředí může nějakou dobu trvat.</span><span class="sxs-lookup"><span data-stu-id="82dd2-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="82dd2-124">Nakonfigurujte doplněk zákaznické karty</span><span class="sxs-lookup"><span data-stu-id="82dd2-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="82dd2-125">Jako správce přejděte na **Nastavení** v Dynamics 365 a vyberte **Řešení**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="82dd2-126">Vyberte odkaz **Zobrazované jméno** řešení Doplněk karty zákazníka v **Dynamics 365 Customer Insights (preview)**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82dd2-127">![Výběr zobrazovaného názvu](media/select-display-name.png "Výběr zobrazovaného názvu")</span><span class="sxs-lookup"><span data-stu-id="82dd2-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="82dd2-128">Vyberte **Přihlásit se** a zadejte přihlašovací údaje pro účet správce, pomocí kterého konfigurujete Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="82dd2-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="82dd2-129">Zkontrolujte, zda blokování automaticky otevíraných oken prohlížeče neblokuje okno ověřování, když vyberete tlačítko **Přihlásit**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="82dd2-130">Vyberte prostředí Customer Insights, ze kterého chcete načíst data.</span><span class="sxs-lookup"><span data-stu-id="82dd2-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="82dd2-131">Definujte mapování polí na záznamy v aplikaci Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="82dd2-132">V závislosti na vašich datech v aplikaci Customer Insights můžete zvolit mapování následujících možností:</span><span class="sxs-lookup"><span data-stu-id="82dd2-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="82dd2-133">Chcete-li mapovat kontakt, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity kontaktu.</span><span class="sxs-lookup"><span data-stu-id="82dd2-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="82dd2-134">Chcete-li mapovat obchodní vztah, vyberte pole v entitě Zákazník, které odpovídá ID vaší entity obchodního vztahu.</span><span class="sxs-lookup"><span data-stu-id="82dd2-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82dd2-135">![Pole ID kontaktu](media/contact-id-field.png "Pole ID kontaktu")</span><span class="sxs-lookup"><span data-stu-id="82dd2-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="82dd2-136">Chcete-li uložit nastavení, vyberte tlačítko **Uložit konfiguraci**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="82dd2-137">Dále musíte v Dynamics 365 přiřadit role zabezpečení, aby si uživatelé mohli přizpůsobit a vidět zákaznickou kartu.</span><span class="sxs-lookup"><span data-stu-id="82dd2-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="82dd2-138">V aplikaci Dynamics 365 přejděte do části **Nastavení** > **Zabezpečení** > **Uživatelé**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="82dd2-139">Vyberte uživatele, kterým chcete upravit uživatelské role, a vyberte **Správa rolí**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="82dd2-140">Přiřaďte roli **Úpravce karty Customer Insights** uživatelům, kteří přizpůsobí obsah zobrazený na kartě pro celou organizaci.</span><span class="sxs-lookup"><span data-stu-id="82dd2-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="82dd2-141">Přidání ovládacích prvků karty zákazníka do formulářů</span><span class="sxs-lookup"><span data-stu-id="82dd2-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="82dd2-142">Chcete-li přidat ovládací prvky zákaznické karty do kontaktního formuláře, přejděte na stránku **Nastavení** > **Přizpůsobení** v Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="82dd2-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="82dd2-143">Vyberte **Přizpůsobit systém**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="82dd2-144">Vyhledejte entitu **Kontakt**, rozbalte ji a poté vyberte **Formuláře**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="82dd2-145">Vyberte kontaktní formulář, do kterého chcete přidat ovládací prvky karty zákazníka.</span><span class="sxs-lookup"><span data-stu-id="82dd2-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="82dd2-146">![Výběr formuláře kontaktu](media/contact-active-forms.png "Výběr formuláře kontaktu")</span><span class="sxs-lookup"><span data-stu-id="82dd2-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="82dd2-147">Chcete-li přidat ovládací prvek demografických údajů, v editoru formulářů přetáhněte libovolné pole z **Průzkumníka polí** na místo, kam chcete umístit ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="82dd2-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="82dd2-148">Vyberte pole ve formuláři, které jste právě přidali, a poté vyberte možnost **Změnit vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="82dd2-149">Přejděte na kartu **Ovládací prvky** a zvolte **Přidat ovládací prvek**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="82dd2-150">Vyberte jeden z dostupných vlastních ovládacích prvků a vyberte **Přidat**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="82dd2-151">V dialogovém okně **Vlastnosti pole** zrušte zaškrtnutí políčka **Zobrazit popisek ve formuláři**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="82dd2-152">Vyberte možnost **Web** pro ovládací prvekl.</span><span class="sxs-lookup"><span data-stu-id="82dd2-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="82dd2-153">Pro ovládací prvek Rozšíření vyberte typ rozšíření, který chcete zobrazit, konfigurací pole **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="82dd2-154">Pro každý typ rozšíření přidejte samostatný ovládací prvek rozšíření.</span><span class="sxs-lookup"><span data-stu-id="82dd2-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="82dd2-155">Vyberte **Uložit** a **Publikovat**, chcete-li zveřejnit aktualizovaný kontaktní formulář.</span><span class="sxs-lookup"><span data-stu-id="82dd2-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="82dd2-156">Přejděte na publikovaný kontaktní formulář.</span><span class="sxs-lookup"><span data-stu-id="82dd2-156">Go to the published contact form.</span></span> <span data-ttu-id="82dd2-157">Uvidíte nově přidaný ovládací prvek.</span><span class="sxs-lookup"><span data-stu-id="82dd2-157">You'll see the newly added control.</span></span> <span data-ttu-id="82dd2-158">Možná se budete muset přihlásit při prvním použití.</span><span class="sxs-lookup"><span data-stu-id="82dd2-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="82dd2-159">Chcete-li přizpůsobit, co se má zobrazit na vlastním ovládacím prvku, vyberte tlačítko Upravit v pravém horním rohu.</span><span class="sxs-lookup"><span data-stu-id="82dd2-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="82dd2-160">Upgrade doplňku karty zákazníka</span><span class="sxs-lookup"><span data-stu-id="82dd2-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="82dd2-161">Doplněk karty zákazníka se neupgraduje automaticky.</span><span class="sxs-lookup"><span data-stu-id="82dd2-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="82dd2-162">Chcete-li upgradovat na nejnovější verzi, postupujte podle tohoto postupu v aplikaci Dynamics 365, která má nainstalovaný doplněk.</span><span class="sxs-lookup"><span data-stu-id="82dd2-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="82dd2-163">V aplikaci Dynamics 365 přejděte na **Nastavení** > **Vlastní nastavení** a vyberte **Řešení**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="82dd2-164">V tabulce doplňků vyhledejte **CustomerInsightsCustomerCard** a vyberte řádek.</span><span class="sxs-lookup"><span data-stu-id="82dd2-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="82dd2-165">Na panelu akcí vyberte **Nainstalovat upgrade řešení**.</span><span class="sxs-lookup"><span data-stu-id="82dd2-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Upgrade řešení v oblasti Vlastní nastavení aplikací Dynamics 365":::

1. <span data-ttu-id="82dd2-167">Po spuštění procesu upgradu se zobrazí indikátor načítání, dokud se upgrade nedokončí.</span><span class="sxs-lookup"><span data-stu-id="82dd2-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="82dd2-168">Pokud není k dispozici žádná novější verze, zobrazí se při upgradu chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="82dd2-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
