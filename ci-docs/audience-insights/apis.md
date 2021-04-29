---
title: Práce s API
description: Použití rozhraní API a přehled o souvisejících omezeních.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873654"
---
# <a name="work-with-customer-insights-apis"></a>Práce s rozhraními API v Customer Insights

Dynamics 365 Customer Insights poskytuje rozhraní API pro vytváření vlastních aplikací založených na datech z Customer Insights.

> [!IMPORTANT]
> Podrobnosti o těchto rozhraních API jsou uvedeny v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Obsahují další informace o operacích, parametrech a odpovědích.

Tento článek popisuje, jak přistupovat k rozhraním API v Customer Insights, jak vytvořit registraci aplikace Azure a jak začít s pomocí dostupných klientských knihoven.

## <a name="get-started-trying-the-customer-insights-apis"></a>První použití rozhraní API aplikace Customer Insights

1. [Přihlaste se](https://home.ci.ai.dynamics.com) do Customer Insights. Pokud ještě nemáte předplatné, [zaregistrujte si zkušební verzi Customer Insights](https://aka.ms/tryci).

1. Chcete-li povolit rozhraní API ve vašem prostředí Customer Insights, přejděte na **Správce** > **Oprávnění**. K tomu budete potřebovat oprávnění správce.

1. Přejít na kartu **API** a vyberte tlačítko **Povolit**.    
   Povolením rozhraní API vytvoříte primární a sekundární klíč předplatného pro vaši instanci, který se použije v požadavcích rozhraní API. Klíče můžete znovu generovat výběrem možnosti **Opětovně vygenerovat primární** nebo **Opětovně vygenerovat sekundární** v části **Správce** > **Oprávnění** > **Rozhraní API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Povolení rozhraní API aplikace Customer Insights":::

1. Volbou **Prozkoumejte naše rozhraní API** si [vyzkoušejte rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Vyberte operaci rozhraní API a vyberte **Vyzkoušet**.

1. V postranním panelu nastavte hodnotu v rozevírací nabídce **Oprávnění** na **implicitní**. Záhlaví `Authorization` získá přidaný nosný token. Klíč předplatného se vyplní automaticky.
  
1. Volitelně můžete přidat všechny potřebné parametry dotazu.

1. Přejděte do dolní části postranního panelu a vyberte **Odeslat**.

Odpověď HTTP se brzy objeví níže.


   :::image type="content" source="media/try-apis.gif" alt-text="Animovaný gif ukazující, jak vybrat test API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Vytvoření nové registrace aplikace v portálu Azure

Tyto kroky vám pomohou začít používat rozhraní API aplikace Customer Insights v aplikaci Azure pomocí delegovaných oprávnění. Nejprve proveďte kroky v části [Začínáme](#get-started-trying-the-customer-insights-apis).

1. Přihlaste se do [portálu Azure](https://portal.azure.com) pomocí účtu, který má přístup k datům Customer Insights.

1. Vlevo vyberte **Registrace aplikací**.

1. Volbou **Nová registrace** zadejte název aplikace a vyberte typ účtu.
   Volitelně přidejte adresu URL pro přesměrování. http://localhost je dostatečná URL pro vývoj aplikace na místním počítači.

1. Při registraci vaší nové aplikace přejděte na **Oprávnění rozhraní API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animovaný gif s nastavením oprávnění API při registraci aplikace.":::

1. Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.

1. Pro **Typ oprávnění** vyberte **Delegovaná oprávnění** a vyberte oprávnění **user_impersonation**.

1. Vyberte **Přidat oprávnění**. Pokud potřebujete přístup k rozhraní API bez přihlášení uživatele, podívejte se do části [Oprávnění aplikace mezi servery](#server-to-server-application-permissions).

1. Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.

Můžete použít ID aplikace/klienta pro registraci této aplikace v knihovně Microsoft Authentication Library (MSAL) k získání nosného tokenu, který odešlete s vaším požadavkem do rozhraní API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif znázorňující udělení souhlasu správce.":::

Další informace o MSAL naleznete v části [Přehled knihovny Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).

Další informace o registraci aplikace v Azure najdete v části [Nové prostředí registrace aplikace v portálu Azure](/azure/active-directory/develop/app-registration-portal-training-guide).

Informace o používání rozhraní API našich klientských knihoven najdete v části [Klientské knihovny Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Oprávnění aplikace mezi servery

Část o [registraci aplikace](#create-a-new-app-registration-in-the-azure-portal) popisuje, jak zaregistrovat aplikaci, která vyžaduje přihlášení uživatele k ověření. Naučte se vytvořit registraci aplikace, která nevyžaduje interakci uživatele a lze ji spustit na serveru.

1. V registraci aplikace v portálu Azure přejděte na **Oprávnění rozhraní API**.

1. Vyberte **Přidat oprávnění** a vyberte **Customer Insights** v postranním panelu.

1. Pro **Typ oprávnění** vyberte **Oprávnění aplikací** a vyberte oprávnění **CustomerInsights.Api.All**.

1. Vyberte **Přidat oprávnění**.

1. Chcete-li udělit souhlas správce s tímto oprávněním aplikace, musíte přidat instanční objekt.

   1. Nainstalujte modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Připojte se k účtu AD: `Connect-AzureAD -TenantId <your tenant id>`. ID vašeho klienta najdete v části **Přehled** > **Azure Active Directory**.
   1. Spuštěním následujícího příkazu přidejte instanční objekt Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parametr AppId se týká aplikace API Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Ukázkový instanční objekt":::

1. Přejděte zpět na **Oprávnění rozhraní API** pro registraci vaší aplikace.

1. Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animovaný gif znázorňující udělení souhlasu správce.":::

1. Na závěr musíme přidat název registrace aplikace jako uživatel v Customer Insights.    
   Otevřete Customer Insights, přejděte na **Správce** > **Oprávnění** a vyberte **Přidat uživatele**.

1. Vyhledejte název registrace aplikace, vyberte jej z výsledků vyhledávání a vyberte **Uložit**.

## <a name="customer-insights-client-libraries"></a>Klientské knihovny Customer Insights

Tato část vám pomůže začít používat klientské knihovny dostupné pro rozhraní API v Customer Insights. Veškerý zdrojový kód knihovny a ukázkové aplikace naleznete na [stránce Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Zjistěte, jak začít používat klientské knihovny C# z NuGet.org. Pro více informací o balíčku NuGet viz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). V současné době je tento balíček zaměřen na rámce netstandard2.0 a netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Přidání klientské knihovny C# do projektu C#

1. Ve Visual Studio otevřete **Správce balíčků NuGet** pro váš projekt.

1. Vyhledejte **Microsoft.Dynamics.CustomerInsights.Api**.

1. Volbou **Instalovat** přidejte balíček do projektu.
   Případně spusťte tento příkaz v **Konzole správce balíčků NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Přidání balíčku NuGet do projektu Visual Studio":::

#### <a name="use-the-c-client-library"></a>Použití klientské knihovny C#

1. Pomocí knihovny [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) získejte `AccessToken` s použitím vaší stávající [registrace aplikace Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po úspěšném ověření a získání tokenu vytvořte nový nebo použijte existující klient `HttpClient` s **DefaultRequestHeaders "Ověření"** nastaveným na **Nosný <access token>** a **Ocp-Apim-Subscription-Key** nastaveným na [**klíč předplatného** z vašeho prostředí Customer Insights](#get-started-trying-the-customer-insights-apis).    
   Obnovte záhlaví **Oprávnění**, když to je vhodné. Například když vypršela platnost tokenu.

1. Předejte klienta `HttpClient` do sestavení klienta `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Ukázka httpclient":::

1. Telefonujte s klientem prostřednictvím „metod rozšíření“, například `GetAllInstancesAsync`. Pokud je preferován přístup k základní odpovědi `Microsoft.Rest.HttpOperationResponse`, použijte například „metody zpráv HTTP“ `GetAllInstancesWithHttpMessagesAsync`.

1. Odpověď bude pravděpodobně typu `object`, protože metoda může vrátit více typů (například `IList<InstanceInfo>` a `ApiErrorResult`). Chcete-li zkontrolovat návratový typ, můžete objekty bezpečně seslat do typů odpovědí zadaných na [stránce s podrobnostmi o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pro tuto operaci.    
   Pokud potřebujete více informací o požadavku, použijte **metody zpráv HTTP** pro přístup k surovému objektu odpovědi.

### <a name="nodejs-package"></a>Balíček NodeJS

Použijte klientské knihovny NodeJS dostupné prostřednictvím NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Balíček Python

Použijte klientské knihovny Python dostupné prostřednictvím PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
