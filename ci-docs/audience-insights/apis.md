---
title: Práce s API
description: Použití rozhraní API a přehled o souvisejících omezeních.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267516"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="2ba19-103">Práce s rozhraními API v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2ba19-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="2ba19-104">Dynamics 365 Customer Insights poskytuje rozhraní API pro vytváření vlastních aplikací založených na datech z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ba19-105">Podrobnosti o těchto rozhraních API jsou uvedeny v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="2ba19-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="2ba19-106">Obsahují další informace o operacích, parametrech a odpovědích.</span><span class="sxs-lookup"><span data-stu-id="2ba19-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="2ba19-107">Tento článek popisuje, jak přistupovat k rozhraním API v Customer Insights, jak vytvořit registraci aplikace Azure a jak začít s pomocí dostupných klientských knihoven.</span><span class="sxs-lookup"><span data-stu-id="2ba19-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="2ba19-108">První použití rozhraní API aplikace Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2ba19-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="2ba19-109">[Přihlaste se](https://home.ci.ai.dynamics.com) do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="2ba19-110">Pokud ještě nemáte předplatné, [zaregistrujte si zkušební verzi Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="2ba19-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="2ba19-111">Chcete-li povolit rozhraní API ve vašem prostředí Customer Insights, přejděte na **Správce** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="2ba19-112">K tomu budete potřebovat oprávnění správce.</span><span class="sxs-lookup"><span data-stu-id="2ba19-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="2ba19-113">Přejít na kartu **API** a vyberte tlačítko **Povolit**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="2ba19-114">Povolením rozhraní API vytvoříte primární a sekundární klíč předplatného pro vaši instanci, který se použije v požadavcích rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="2ba19-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="2ba19-115">Klíče můžete znovu generovat výběrem možnosti **Opětovně vygenerovat primární** nebo **Opětovně vygenerovat sekundární** v části **Správce** > **Oprávnění** > **Rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Povolení rozhraní API aplikace Customer Insights":::

1. <span data-ttu-id="2ba19-117">Volbou **Prozkoumejte naše rozhraní API** si vyzkoušejte rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="2ba19-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="2ba19-118">Vyberte operaci rozhraní API a vyberte **Vyzkoušet**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="2ba19-119">V postranním panelu nastavte hodnotu v rozevírací nabídce **Oprávnění** na **implicitní**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="2ba19-120">Záhlaví `Authorization` získá přidaný nosný token.</span><span class="sxs-lookup"><span data-stu-id="2ba19-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="2ba19-121">Klíč předplatného se vyplní automaticky.</span><span class="sxs-lookup"><span data-stu-id="2ba19-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="2ba19-122">Volitelně můžete přidat všechny potřebné parametry dotazu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="2ba19-123">Přejděte do dolní části postranního panelu a vyberte **Odeslat**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="2ba19-124">Odpověď HTTP se brzy objeví níže.</span><span class="sxs-lookup"><span data-stu-id="2ba19-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="2ba19-125">Vytvoření nové registrace aplikace v portálu Azure</span><span class="sxs-lookup"><span data-stu-id="2ba19-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="2ba19-126">Tyto kroky vám pomohou začít používat rozhraní API aplikace Customer Insights v aplikaci Azure pomocí delegovaných oprávnění.</span><span class="sxs-lookup"><span data-stu-id="2ba19-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="2ba19-127">Nejprve proveďte kroky v části [Začínáme](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="2ba19-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="2ba19-128">Přihlaste se do [portálu Azure](https://portal.azure.com) pomocí účtu, který má přístup k datům Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="2ba19-129">Vlevo vyberte **Registrace aplikací**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="2ba19-130">Volbou **Nová registrace** zadejte název aplikace a vyberte typ účtu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="2ba19-131">Volitelně přidejte adresu URL pro přesměrování.</span><span class="sxs-lookup"><span data-stu-id="2ba19-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="2ba19-132">http://localhost je dostatečná URL pro vývoj aplikace na místním počítači.</span><span class="sxs-lookup"><span data-stu-id="2ba19-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="2ba19-133">Při registraci vaší nové aplikace přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="2ba19-134">Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="2ba19-135">Pro **Typ oprávnění** vyberte **Delegovaná oprávnění** a vyberte oprávnění **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="2ba19-136">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-136">Select **Add permissions**.</span></span> <span data-ttu-id="2ba19-137">Pokud potřebujete přístup k rozhraní API bez přihlášení uživatele, podívejte se do části [Oprávnění aplikace mezi servery](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="2ba19-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="2ba19-138">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="2ba19-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="2ba19-139">Můžete použít ID aplikace/klienta pro registraci této aplikace v knihovně Microsoft Authentication Library (MSAL) k získání nosného tokenu, který odešlete s vaším požadavkem do rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="2ba19-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="2ba19-140">Další informace o MSAL naleznete v části [Přehled knihovny Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="2ba19-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="2ba19-141">Další informace o registraci aplikace v Azure najdete v části [Nové prostředí registrace aplikace v portálu Azure](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="2ba19-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="2ba19-142">Informace o používání rozhraní API našich klientských knihoven najdete v části [Klientské knihovny Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="2ba19-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="2ba19-143">Oprávnění aplikace mezi servery</span><span class="sxs-lookup"><span data-stu-id="2ba19-143">Server-to-server application permissions</span></span>

<span data-ttu-id="2ba19-144">Část o [registraci aplikace](#create-a-new-app-registration-in-the-azure-portal) popisuje, jak zaregistrovat aplikaci, která vyžaduje přihlášení uživatele k ověření.</span><span class="sxs-lookup"><span data-stu-id="2ba19-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="2ba19-145">Naučte se vytvořit registraci aplikace, která nevyžaduje interakci uživatele a lze ji spustit na serveru.</span><span class="sxs-lookup"><span data-stu-id="2ba19-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="2ba19-146">V registraci aplikace v portálu Azure přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="2ba19-147">Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="2ba19-148">Pro **Typ oprávnění** vyberte **Oprávnění aplikací** a vyberte oprávnění **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="2ba19-149">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="2ba19-150">Chcete-li udělit souhlas správce s tímto oprávněním aplikace, musíte přidat instanční objekt.</span><span class="sxs-lookup"><span data-stu-id="2ba19-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="2ba19-151">Nainstalujte modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="2ba19-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="2ba19-152">Připojte se k účtu AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="2ba19-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="2ba19-153">ID vašeho klienta najdete v části **Přehled** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="2ba19-154">Spuštěním následujícího příkazu přidejte instanční objekt Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametr AppId se týká aplikace API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ukázkový instanční objekt":::

1. <span data-ttu-id="2ba19-156">Přejděte zpět na **Oprávnění rozhraní API** pro registraci vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="2ba19-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="2ba19-157">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="2ba19-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="2ba19-158">Na závěr musíme přidat název registrace aplikace jako uživatel v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="2ba19-159">Otevřete Customer Insights, přejděte na **Správce** > **Oprávnění** a vyberte **Přidat uživatele**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="2ba19-160">Vyhledejte název registrace aplikace, vyberte jej z výsledků vyhledávání a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="2ba19-161">Klientské knihovny Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2ba19-161">Customer Insights client libraries</span></span>

<span data-ttu-id="2ba19-162">Tato část vám pomůže začít používat klientské knihovny dostupné pro rozhraní API v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ba19-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="2ba19-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="2ba19-163">C# NuGet</span></span>

<span data-ttu-id="2ba19-164">Zjistěte, jak začít používat klientské knihovny C# z NuGet.org. Pro více informací o balíčku NuGet viz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="2ba19-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="2ba19-165">V současné době je tento balíček zaměřen na rámce netstandard2.0 a netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="2ba19-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="2ba19-166">Přidání klientské knihovny C# do projektu C#</span><span class="sxs-lookup"><span data-stu-id="2ba19-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="2ba19-167">Ve Visual Studio otevřete **Správce balíčků NuGet** pro váš projekt.</span><span class="sxs-lookup"><span data-stu-id="2ba19-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="2ba19-168">Vyhledejte **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="2ba19-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="2ba19-169">Volbou **Instalovat** přidejte balíček do projektu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="2ba19-170">Případně spusťte tento příkaz v **Konzole správce balíčků NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="2ba19-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Přidání balíčku NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="2ba19-172">Použití klientské knihovny C#</span><span class="sxs-lookup"><span data-stu-id="2ba19-172">Use the C# client library</span></span>

1. <span data-ttu-id="2ba19-173">Pomocí knihovny [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) získejte `AccessToken` s použitím vaší stávající [registrace aplikace Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2ba19-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="2ba19-174">Po úspěšném ověření a získání tokenu vytvořte nový nebo použijte existující klient `HttpClient` s **DefaultRequestHeaders "Ověření"** nastaveným na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastaveným na [**klíč předplatného** z vašeho prostředí Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="2ba19-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="2ba19-175">Obnovte záhlaví **Oprávnění**, když to je vhodné.</span><span class="sxs-lookup"><span data-stu-id="2ba19-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="2ba19-176">Například když vypršela platnost tokenu.</span><span class="sxs-lookup"><span data-stu-id="2ba19-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="2ba19-177">Předejte klienta `HttpClient` do sestavení klienta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="2ba19-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukázka httpclient":::

1. <span data-ttu-id="2ba19-179">Telefonujte s klientem prostřednictvím „metod rozšíření“, například `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2ba19-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="2ba19-180">Pokud je preferován přístup k základní odpovědi `Microsoft.Rest.HttpOperationResponse`, použijte například „metody zpráv HTTP“ `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="2ba19-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="2ba19-181">Odpověď bude pravděpodobně typu `object`, protože metoda může vrátit více typů (například `IList<InstanceInfo>` a `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="2ba19-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="2ba19-182">Chcete-li zkontrolovat návratový typ, můžete objekty bezpečně seslat do typů odpovědí zadaných na [stránce s podrobnostmi o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="2ba19-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="2ba19-183">Pokud potřebujete více informací o požadavku, použijte **metody zpráv HTTP** pro přístup k surovému objektu odpovědi.</span><span class="sxs-lookup"><span data-stu-id="2ba19-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]