---
title: Práce s API
description: Použití rozhraní API a přehled o souvisejících omezeních.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304734"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="f5778-103">Práce s rozhraními API v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f5778-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="f5778-104">Dynamics 365 Customer Insights poskytuje rozhraní API pro vytváření vlastních aplikací na základě vašich dat ve službě Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5778-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5778-105">Podrobnosti o těchto rozhraních API jsou uvedeny v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="f5778-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="f5778-106">Obsahují další informace o operacích, parametrech a odpovědích.</span><span class="sxs-lookup"><span data-stu-id="f5778-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="f5778-107">Tento článek popisuje, jak přistupovat k API Customer Insights, vytvořit registraci aplikace Azure a začít s dostupnými knihovnami klientů.</span><span class="sxs-lookup"><span data-stu-id="f5778-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="f5778-108">První použití rozhraní API aplikace Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f5778-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="f5778-109">[Přihlaste se](https://home.ci.ai.dynamics.com) do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5778-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="f5778-110">Pokud ještě nemáte předplatné, [zaregistrujte si zkušební verzi Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="f5778-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="f5778-111">Chcete-li povolit rozhraní API ve vašem prostředí Customer Insights, přejděte na **Správce** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="f5778-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="f5778-112">K tomu budete potřebovat oprávnění správce.</span><span class="sxs-lookup"><span data-stu-id="f5778-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="f5778-113">Přejít na kartu **API** a vyberte tlačítko **Povolit**.</span><span class="sxs-lookup"><span data-stu-id="f5778-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="f5778-114">Povolením rozhraní API vytvoříte primární a sekundární klíč předplatného pro vaši instanci, který se použije v požadavcích rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="f5778-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="f5778-115">Klíče můžete znovu generovat výběrem možnosti **Opětovně vygenerovat primární** nebo **Opětovně vygenerovat sekundární** v části **Správce** > **Oprávnění** > **Rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="f5778-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Povolení rozhraní API aplikace Customer Insights":::

1. <span data-ttu-id="f5778-117">Volbou **Prozkoumejte naše rozhraní API** si [vyzkoušejte rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="f5778-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="f5778-118">Vyberte operaci rozhraní API a vyberte **Vyzkoušet**.</span><span class="sxs-lookup"><span data-stu-id="f5778-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="f5778-119">V bočním podokně nastavte hodnotu v rozevírací nabídce **Autorizace** na **implicitní**.</span><span class="sxs-lookup"><span data-stu-id="f5778-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="f5778-120">Záhlaví `Authorization` se přidá s nosným tokenem.</span><span class="sxs-lookup"><span data-stu-id="f5778-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="f5778-121">Klíč předplatného se vyplní automaticky.</span><span class="sxs-lookup"><span data-stu-id="f5778-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="f5778-122">Volitelně můžete přidat všechny potřebné parametry dotazu.</span><span class="sxs-lookup"><span data-stu-id="f5778-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="f5778-123">Přejděte do dolní části postranního panelu a vyberte **Odeslat**.</span><span class="sxs-lookup"><span data-stu-id="f5778-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="f5778-124">Odpověď HTTP se brzy objeví níže.</span><span class="sxs-lookup"><span data-stu-id="f5778-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Jak testovat API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="f5778-126">Vytvoření nové registrace aplikace v portálu Azure</span><span class="sxs-lookup"><span data-stu-id="f5778-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="f5778-127">Tyto kroky vám pomohou začít používat rozhraní API Customer Insights v aplikaci Azure pomocí delegovaných oprávnění.</span><span class="sxs-lookup"><span data-stu-id="f5778-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="f5778-128">Nezapomeňte nejprve dokončit část [Začínáme](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f5778-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="f5778-129">Přihlaste se do [portálu Azure](https://portal.azure.com) pomocí účtu, který má přístup k datům Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5778-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="f5778-130">Vlevo vyberte **Registrace aplikací**.</span><span class="sxs-lookup"><span data-stu-id="f5778-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="f5778-131">Volbou **Nová registrace** zadejte název aplikace a vyberte typ účtu.</span><span class="sxs-lookup"><span data-stu-id="f5778-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="f5778-132">Volitelně přidejte adresu URL pro přesměrování.</span><span class="sxs-lookup"><span data-stu-id="f5778-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="f5778-133">http://localhost je dostatečná URL pro vývoj aplikace na místním počítači.</span><span class="sxs-lookup"><span data-stu-id="f5778-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="f5778-134">Při registraci vaší nové aplikace přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="f5778-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Jak nastavit oprávnění API v registraci aplikace.":::

1. <span data-ttu-id="f5778-136">Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.</span><span class="sxs-lookup"><span data-stu-id="f5778-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="f5778-137">Pro **Typ oprávnění** vyberte **Delegovaná oprávnění** a pak vyberte oprávnění **zosobnění uživatele**.</span><span class="sxs-lookup"><span data-stu-id="f5778-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="f5778-138">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="f5778-138">Select **Add permissions**.</span></span> <span data-ttu-id="f5778-139">Pokud potřebujete přístup k rozhraní API bez přihlášení uživatele, podívejte se do části [Oprávnění aplikace mezi servery](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="f5778-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="f5778-140">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="f5778-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="f5778-141">Můžete použít ID aplikace/klienta pro registraci této aplikace v knihovně Microsoft Authentication Library (MSAL) k získání nosného tokenu, který odešlete s vaším požadavkem do rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="f5778-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Jak udělit souhlas správce.":::

<span data-ttu-id="f5778-143">Další informace o MSAL naleznete v části [Přehled knihovny Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="f5778-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="f5778-144">Další informace o registraci aplikace v Azure najdete v části [Registrace aplikace](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="f5778-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="f5778-145">Informace o používání rozhraní API v našich klientských knihovnách najdete v části [Klientské knihovny Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="f5778-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="f5778-146">Oprávnění aplikace mezi servery</span><span class="sxs-lookup"><span data-stu-id="f5778-146">Server-to-server application permissions</span></span>

<span data-ttu-id="f5778-147">Část o [registraci aplikace](#create-a-new-app-registration-in-the-azure-portal) popisuje, jak zaregistrovat aplikaci, která vyžaduje přihlášení uživatele k ověření.</span><span class="sxs-lookup"><span data-stu-id="f5778-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="f5778-148">Naučte se vytvořit registraci aplikace, která nevyžaduje interakci uživatele a lze ji spustit na serveru.</span><span class="sxs-lookup"><span data-stu-id="f5778-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="f5778-149">V registraci aplikace v portálu Azure přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="f5778-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="f5778-150">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="f5778-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="f5778-151">Vyberte kartu **API, která moje organizace používá** a v seznamu vyberte **Dynamics 365 AI pro Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="f5778-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="f5778-152">Pro **Typ oprávnění** vyberte **Oprávnění aplikace** a pak vyberte oprávnění **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="f5778-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="f5778-153">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="f5778-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="f5778-154">Přejděte zpět na **Oprávnění rozhraní API** pro registraci vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="f5778-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="f5778-155">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="f5778-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Jak udělit souhlas správce.":::

1. <span data-ttu-id="f5778-157">Na závěr musíme přidat název registrace aplikace jako uživatel v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5778-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="f5778-158">Otevřete Customer Insights, přejděte na **Správce** > **Oprávnění** a vyberte **Přidat uživatele**.</span><span class="sxs-lookup"><span data-stu-id="f5778-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="f5778-159">Vyhledejte název registrace aplikace, vyberte jej z výsledků vyhledávání a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="f5778-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="f5778-160">Klientské knihovny Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f5778-160">Customer Insights client libraries</span></span>

<span data-ttu-id="f5778-161">Tato část vám pomůže začít používat klientské knihovny dostupné pro rozhraní API v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5778-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="f5778-162">Veškerý zdrojový kód knihovny a ukázkové aplikace naleznete na [stránce Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="f5778-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="f5778-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="f5778-163">C# NuGet</span></span>

<span data-ttu-id="f5778-164">Zjistěte, jak začít používat klientské knihovny C# z NuGet.org. Pro více informací o balíčku NuGet viz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="f5778-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="f5778-165">V současné době je tento balíček zaměřen na rámce netstandard2.0 a netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="f5778-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="f5778-166">Přidání klientské knihovny C# do projektu C#</span><span class="sxs-lookup"><span data-stu-id="f5778-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="f5778-167">Ve Visual Studio otevřete **Správce balíčků NuGet** pro váš projekt.</span><span class="sxs-lookup"><span data-stu-id="f5778-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="f5778-168">Vyhledejte **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="f5778-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="f5778-169">Volbou **Instalovat** přidejte balíček do projektu.</span><span class="sxs-lookup"><span data-stu-id="f5778-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="f5778-170">Případně spusťte tento příkaz v **Konzole správce balíčků NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="f5778-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Přidání balíčku NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="f5778-172">Použití klientské knihovny C#</span><span class="sxs-lookup"><span data-stu-id="f5778-172">Use the C# client library</span></span>

1. <span data-ttu-id="f5778-173">Pomocí knihovny [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) získejte `AccessToken` s použitím vaší stávající [registrace aplikace Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="f5778-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="f5778-174">Po úspěšném ověření a získání tokenu vytvořte nový nebo použijte existující klient `HttpClient` s **DefaultRequestHeaders "Ověření"** nastaveným na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastaveným na [**klíč předplatného** z vašeho prostředí Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="f5778-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="f5778-175">Obnovte záhlaví **Oprávnění**, když to je vhodné.</span><span class="sxs-lookup"><span data-stu-id="f5778-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="f5778-176">Například když vypršela platnost tokenu.</span><span class="sxs-lookup"><span data-stu-id="f5778-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="f5778-177">Předejte klienta `HttpClient` do sestavení klienta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="f5778-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukázka httpclient":::

1. <span data-ttu-id="f5778-179">Telefonujte s klientem prostřednictvím „metod rozšíření“ - například `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f5778-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="f5778-180">Pokud je preferován přístup k základní odpovědi `Microsoft.Rest.HttpOperationResponse` - použijte například „metody zpráv HTTP“ `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="f5778-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="f5778-181">Odpověď bude pravděpodobně typu `object`, protože metoda může vrátit více typů (například `IList<InstanceInfo>` a `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="f5778-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="f5778-182">Chcete-li zkontrolovat návratový typ, můžete objekty bezpečně seslat do typů odpovědí zadaných na [stránce s podrobnostmi o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="f5778-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="f5778-183">Pokud potřebujete více informací o požadavku, použijte **metody zpráv HTTP** pro přístup k surovému objektu odpovědi.</span><span class="sxs-lookup"><span data-stu-id="f5778-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="f5778-184">Balíček NodeJS</span><span class="sxs-lookup"><span data-stu-id="f5778-184">NodeJS package</span></span>

<span data-ttu-id="f5778-185">Použijte klientské knihovny NodeJS dostupné prostřednictvím NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="f5778-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="f5778-186">Balíček Python</span><span class="sxs-lookup"><span data-stu-id="f5778-186">Python package</span></span>

<span data-ttu-id="f5778-187">Použijte klientské knihovny Python dostupné prostřednictvím PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="f5778-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
