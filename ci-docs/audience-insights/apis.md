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
ms.openlocfilehash: 4d41d7d328dfa6699b5f5e992d3a5bf3179490d8
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016584"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="4f4db-103">Práce s rozhraními API v Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f4db-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="4f4db-104">Dynamics 365 Customer Insights poskytuje rozhraní API pro vytváření vlastních aplikací založených na datech z Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f4db-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f4db-105">Podrobnosti o těchto rozhraních API jsou uvedeny v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="4f4db-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="4f4db-106">Obsahují další informace o operacích, parametrech a odpovědích.</span><span class="sxs-lookup"><span data-stu-id="4f4db-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="4f4db-107">Tento článek popisuje, jak přistupovat k rozhraním API v Customer Insights, jak vytvořit registraci aplikace Azure a jak začít s pomocí dostupných klientských knihoven.</span><span class="sxs-lookup"><span data-stu-id="4f4db-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="4f4db-108">První použití rozhraní API aplikace Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f4db-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="4f4db-109">[Přihlaste se](https://home.ci.ai.dynamics.com) do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f4db-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="4f4db-110">Pokud ještě nemáte předplatné, [zaregistrujte si zkušební verzi Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="4f4db-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="4f4db-111">Chcete-li povolit rozhraní API ve vašem prostředí Customer Insights, přejděte na **Správce** > **Oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="4f4db-112">K tomu budete potřebovat oprávnění správce.</span><span class="sxs-lookup"><span data-stu-id="4f4db-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="4f4db-113">Přejít na kartu **API** a vyberte tlačítko **Povolit**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="4f4db-114">Povolením rozhraní API vytvoříte primární a sekundární klíč předplatného pro vaši instanci, který se použije v požadavcích rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="4f4db-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="4f4db-115">Klíče můžete znovu generovat výběrem možnosti **Opětovně vygenerovat primární** nebo **Opětovně vygenerovat sekundární** v části **Správce** > **Oprávnění** > **Rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Povolení rozhraní API aplikace Customer Insights":::

1. <span data-ttu-id="4f4db-117">Volbou **Prozkoumejte naše rozhraní API** si [vyzkoušejte rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="4f4db-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="4f4db-118">Vyberte operaci rozhraní API a vyberte **Vyzkoušet**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="4f4db-119">V postranním panelu nastavte hodnotu v rozevírací nabídce **Oprávnění** na **implicitní**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="4f4db-120">Záhlaví `Authorization` získá přidaný nosný token.</span><span class="sxs-lookup"><span data-stu-id="4f4db-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="4f4db-121">Klíč předplatného se vyplní automaticky.</span><span class="sxs-lookup"><span data-stu-id="4f4db-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="4f4db-122">Volitelně můžete přidat všechny potřebné parametry dotazu.</span><span class="sxs-lookup"><span data-stu-id="4f4db-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="4f4db-123">Přejděte do dolní části postranního panelu a vyberte **Odeslat**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="4f4db-124">Odpověď HTTP se brzy objeví níže.</span><span class="sxs-lookup"><span data-stu-id="4f4db-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animovaný gif ukazující, jak vybrat test API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="4f4db-126">Vytvoření nové registrace aplikace v portálu Azure</span><span class="sxs-lookup"><span data-stu-id="4f4db-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="4f4db-127">Tyto kroky vám pomohou začít používat rozhraní API aplikace Customer Insights v aplikaci Azure pomocí delegovaných oprávnění.</span><span class="sxs-lookup"><span data-stu-id="4f4db-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="4f4db-128">Nejprve proveďte kroky v části [Začínáme](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="4f4db-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="4f4db-129">Přihlaste se do [portálu Azure](https://portal.azure.com) pomocí účtu, který má přístup k datům Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f4db-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="4f4db-130">Vlevo vyberte **Registrace aplikací**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="4f4db-131">Volbou **Nová registrace** zadejte název aplikace a vyberte typ účtu.</span><span class="sxs-lookup"><span data-stu-id="4f4db-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="4f4db-132">Volitelně přidejte adresu URL pro přesměrování.</span><span class="sxs-lookup"><span data-stu-id="4f4db-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="4f4db-133">http://localhost je dostatečná URL pro vývoj aplikace na místním počítači.</span><span class="sxs-lookup"><span data-stu-id="4f4db-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="4f4db-134">Při registraci vaší nové aplikace přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animovaný gif s nastavením oprávnění API při registraci aplikace.":::

1. <span data-ttu-id="4f4db-136">Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.</span><span class="sxs-lookup"><span data-stu-id="4f4db-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="4f4db-137">Pro **Typ oprávnění** vyberte **Delegovaná oprávnění** a vyberte oprávnění **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="4f4db-138">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-138">Select **Add permissions**.</span></span> <span data-ttu-id="4f4db-139">Pokud potřebujete přístup k rozhraní API bez přihlášení uživatele, podívejte se do části [Oprávnění aplikace mezi servery](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="4f4db-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="4f4db-140">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="4f4db-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="4f4db-141">Můžete použít ID aplikace/klienta pro registraci této aplikace v knihovně Microsoft Authentication Library (MSAL) k získání nosného tokenu, který odešlete s vaším požadavkem do rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="4f4db-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif znázorňující udělení souhlasu správce.":::

<span data-ttu-id="4f4db-143">Další informace o MSAL naleznete v části [Přehled knihovny Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="4f4db-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="4f4db-144">Další informace o registraci aplikace v Azure najdete v části [Nové prostředí registrace aplikace v portálu Azure](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="4f4db-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="4f4db-145">Informace o používání rozhraní API našich klientských knihoven najdete v části [Klientské knihovny Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="4f4db-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="4f4db-146">Oprávnění aplikace mezi servery</span><span class="sxs-lookup"><span data-stu-id="4f4db-146">Server-to-server application permissions</span></span>

<span data-ttu-id="4f4db-147">Část o [registraci aplikace](#create-a-new-app-registration-in-the-azure-portal) popisuje, jak zaregistrovat aplikaci, která vyžaduje přihlášení uživatele k ověření.</span><span class="sxs-lookup"><span data-stu-id="4f4db-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="4f4db-148">Naučte se vytvořit registraci aplikace, která nevyžaduje interakci uživatele a lze ji spustit na serveru.</span><span class="sxs-lookup"><span data-stu-id="4f4db-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="4f4db-149">V registraci aplikace v portálu Azure přejděte na **Oprávnění rozhraní API**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="4f4db-150">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="4f4db-151">Vyberte kartu **API, která moje organizace používá** a v seznamu vyberte **Dynamics 365 AI pro Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="4f4db-152">Pro **Typ oprávnění** vyberte **Oprávnění aplikací** a vyberte oprávnění **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-152">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="4f4db-153">Vyberte **Přidat oprávnění**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="4f4db-154">Přejděte zpět na **Oprávnění rozhraní API** pro registraci vaší aplikace.</span><span class="sxs-lookup"><span data-stu-id="4f4db-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="4f4db-155">Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.</span><span class="sxs-lookup"><span data-stu-id="4f4db-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif znázorňující udělení souhlasu správce.":::

1. <span data-ttu-id="4f4db-157">Na závěr musíme přidat název registrace aplikace jako uživatel v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f4db-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="4f4db-158">Otevřete Customer Insights, přejděte na **Správce** > **Oprávnění** a vyberte **Přidat uživatele**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="4f4db-159">Vyhledejte název registrace aplikace, vyberte jej z výsledků vyhledávání a vyberte **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="4f4db-160">Klientské knihovny Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f4db-160">Customer Insights client libraries</span></span>

<span data-ttu-id="4f4db-161">Tato část vám pomůže začít používat klientské knihovny dostupné pro rozhraní API v Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4f4db-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="4f4db-162">Veškerý zdrojový kód knihovny a ukázkové aplikace naleznete na [stránce Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="4f4db-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="4f4db-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="4f4db-163">C# NuGet</span></span>

<span data-ttu-id="4f4db-164">Zjistěte, jak začít používat klientské knihovny C# z NuGet.org. Pro více informací o balíčku NuGet viz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="4f4db-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="4f4db-165">V současné době je tento balíček zaměřen na rámce netstandard2.0 a netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="4f4db-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="4f4db-166">Přidání klientské knihovny C# do projektu C#</span><span class="sxs-lookup"><span data-stu-id="4f4db-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="4f4db-167">Ve Visual Studio otevřete **Správce balíčků NuGet** pro váš projekt.</span><span class="sxs-lookup"><span data-stu-id="4f4db-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="4f4db-168">Vyhledejte **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="4f4db-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="4f4db-169">Volbou **Instalovat** přidejte balíček do projektu.</span><span class="sxs-lookup"><span data-stu-id="4f4db-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="4f4db-170">Případně spusťte tento příkaz v **Konzole správce balíčků NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="4f4db-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Přidání balíčku NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="4f4db-172">Použití klientské knihovny C#</span><span class="sxs-lookup"><span data-stu-id="4f4db-172">Use the C# client library</span></span>

1. <span data-ttu-id="4f4db-173">Pomocí knihovny [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) získejte `AccessToken` s použitím vaší stávající [registrace aplikace Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="4f4db-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="4f4db-174">Po úspěšném ověření a získání tokenu vytvořte nový nebo použijte existující klient `HttpClient` s **DefaultRequestHeaders "Ověření"** nastaveným na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastaveným na [**klíč předplatného** z vašeho prostředí Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="4f4db-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="4f4db-175">Obnovte záhlaví **Oprávnění**, když to je vhodné.</span><span class="sxs-lookup"><span data-stu-id="4f4db-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="4f4db-176">Například když vypršela platnost tokenu.</span><span class="sxs-lookup"><span data-stu-id="4f4db-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="4f4db-177">Předejte klienta `HttpClient` do sestavení klienta `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="4f4db-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukázka httpclient":::

1. <span data-ttu-id="4f4db-179">Telefonujte s klientem prostřednictvím „metod rozšíření“, například `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4f4db-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="4f4db-180">Pokud je preferován přístup k základní odpovědi `Microsoft.Rest.HttpOperationResponse`, použijte například „metody zpráv HTTP“ `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="4f4db-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="4f4db-181">Odpověď bude pravděpodobně typu `object`, protože metoda může vrátit více typů (například `IList<InstanceInfo>` a `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="4f4db-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="4f4db-182">Chcete-li zkontrolovat návratový typ, můžete objekty bezpečně seslat do typů odpovědí zadaných na [stránce s podrobnostmi o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pro tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="4f4db-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="4f4db-183">Pokud potřebujete více informací o požadavku, použijte **metody zpráv HTTP** pro přístup k surovému objektu odpovědi.</span><span class="sxs-lookup"><span data-stu-id="4f4db-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="4f4db-184">Balíček NodeJS</span><span class="sxs-lookup"><span data-stu-id="4f4db-184">NodeJS package</span></span>

<span data-ttu-id="4f4db-185">Použijte klientské knihovny NodeJS dostupné prostřednictvím NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="4f4db-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="4f4db-186">Balíček Python</span><span class="sxs-lookup"><span data-stu-id="4f4db-186">Python package</span></span>

<span data-ttu-id="4f4db-187">Použijte klientské knihovny Python dostupné prostřednictvím PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="4f4db-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
