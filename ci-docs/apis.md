---
title: Práce s rozhraními API v Customer Insights
description: Použití rozhraní API a přehled o souvisejících omezeních.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387332"
---
# <a name="work-with-customer-insights-apis"></a>Práce s rozhraními API v Customer Insights

Dynamics 365 Customer Insights poskytuje rozhraní API pro vytváření vlastních aplikací na základě vašich dat ve službě Customer Insights.

> [!IMPORTANT]
> Podrobnosti o těchto rozhraních API jsou uvedeny v části [Referenční informace o rozhraních API v Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Obsahují další informace o operacích, parametrech a odpovědích.

Vyzkoušejte rozhraní Customer Insights API, vytvořte registraci Azure App a začněte s klientskými knihovnami.

## <a name="get-started-trying-the-customer-insights-apis"></a>První použití rozhraní API aplikace Customer Insights

Povolte rozhraní API Customer Insights a vyzkoušejte je. Správce Customer Insights musí povolit přístup API k Customer Insights. Jakmile je přístup povolen, může každý uživatel používat API s klíčem předplatného.

1. [Přihlaste se](https://home.ci.ai.dynamics.com) do Customer Insights. Pokud ještě nemáte předplatné, [zaregistrujte si zkušební verzi Customer Insights](https://aka.ms/tryci).

1. Jděte na **Správa** > **Zabezpečení** > a vyberte kartu **Rozhraní API**.

1. Pokud nebyl nastaven přístup API k prostředí, vyberte **Povolit**.

   Povolením rozhraní API vytvoříte primární a sekundární klíč předplatného pro vaši instanci, který se použije v požadavcích rozhraní API. Pokud chcete znovu generovat klíče, vyberte **Opětovně vygenerovat primární** nebo **Opětovně vygenerovat sekundární** na kartě **Rozhraní API**.

1. Vyberte [**Prozkoumat naše rozhraní API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) k vyzkoušení rozhraní API.

1. Vyhledejte a vyberte operaci API a vyberte **Zkusit**.

   :::image type="content" source="media/try-api.png" alt-text="Jak testovat API.":::

1. V bočním podokně nastavte hodnotu v rozevírací nabídce **Autorizace** na **implicitní**. Záhlaví `Authorization` se přidá s nosným tokenem. Klíč předplatného se vyplní automaticky.
  
1. Volitelně můžete přidat všechny potřebné parametry dotazu.

1. Přejděte do dolní části postranního panelu a vyberte **Odeslat**.

   Odpověď HTTP se zobrazí v dolní části podokna.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Vytvoření nové registrace aplikace v portálu Azure

Vytvořte novou [registraci aplikace](/graph/auth-register-app-v2), pokud chcete používat rozhraní API Customer Insights v aplikaci Azure pomocí delegovaných oprávnění.

1. Nejprve dokončete část [Začínáme](#get-started-trying-the-customer-insights-apis).

1. Přihlaste se do [portálu Azure](https://portal.azure.com) pomocí účtu, který má přístup k datům Customer Insights.

1. Vyhledete a vyberte **Registrace aplikace**.

1. Volbou **Nová registrace** zadejte název aplikace a vyberte typ účtu.

   Volitelně přidejte adresu URL pro přesměrování. http://localhost je dostatečná URL pro vývoj aplikace na místním počítači.

1. Vyberte **Zaregistrovat**.

1. Při registraci vaší nové aplikace přejděte na **Oprávnění rozhraní API**.

1. Vyberte **Přidat oprávnění** a vyberte **Dynamics 365 AI for Customer Insights** v bočním podokně.

1. Pro **Typ oprávnění** vyberte **Delegovaná oprávnění** a pak vyberte oprávnění **zosobnění uživatele**.

1. Vyberte **Přidat oprávnění**.

1. Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.

1. Pokud potřebujete přístup k rozhraní API bez přihlášení uživatele, podívejte se do části [Oprávnění aplikace mezi servery](#server-to-server-application-permissions).

Můžete použít ID aplikace/klienta pro registraci této aplikace v knihovně [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) k získání nosného tokenu, který odešlete s vaším požadavkem do rozhraní API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Informace o používání rozhraní API v našich klientských knihovnách najdete v části [Klientské knihovny Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Oprávnění aplikace mezi servery

Vytvořte registraci aplikace, která nevyžaduje zásah uživatele a lze ji spustit na serveru.

1. V registraci aplikace v portálu Azure přejděte na **Oprávnění rozhraní API**.

1. Vyberte **Přidat oprávnění**.

1. Vyberte kartu **API, která moje organizace používá** a v seznamu vyberte **Dynamics 365 AI pro Customer Insights**.

1. Pro **Typ oprávnění** vyberte **Oprávnění aplikace** a pak vyberte oprávnění **CustomerInsights.Api.All**.

1. Vyberte **Přidat oprávnění**.

1. Přejděte zpět na **Oprávnění rozhraní API** pro registraci vaší aplikace.

1. Vyberte **Udělit souhlas správce pro...** k dokončení registrace aplikace.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Přidejte název registrace aplikace jako uživatel v Customer Insights.

   1. Otevřete Customer Insights, přejděte na **Správce** > **Zabezpečení** a vyberte **Přidat uživatele**.

   1. Vyhledejte název registrace aplikace, vyberte jej z výsledků vyhledávání a vyberte **Uložit**.

## <a name="sample-queries"></a>Vzorové dotazy

Krátký seznam vzorových dotazů OData pro práci s rozhraními API najdete v části [Příklady dotazů OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Klientské knihovny Customer Insights

Začněte používat klientské knihovny dostupné pro rozhraní API v Customer Insights. Veškerý zdrojový kód knihovny a ukázkové aplikace naleznete na [stránce Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Použijte klientské knihovny jazyka C# z NuGet.org. V současné době se balíček zaměřuje na rámce netstandard2.0 a netcoreapp2.0. Více informací o balíčku NuGet viz [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Přidání klientské knihovny C# do projektu C#

1. Ve Visual Studio otevřete **Správce balíčků NuGet** pro váš projekt.

1. Vyhledejte **Microsoft.Dynamics.CustomerInsights.Api**.

1. Volbou **Instalovat** přidejte balíček do projektu.

   Případně spusťte tento příkaz v **Konzole správce balíčků NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Použití klientské knihovny C#

1. Pomocí knihovny [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) získejte `AccessToken` s použitím vaší stávající [registrace aplikace Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Po úspěšném ověření a získání tokenu vytvořte nový nebo použijte existující `HttpClient` s vlastností **DefaultRequestHeaders "Autorizace"** nastavenou na **Bearer "přístupový token"** a **Ocp-Apim-Subscription-Key** nastavenou na [**klíč předplatného** z vašeho prostředí Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Obnovte záhlaví **Oprávnění**, když to je vhodné. Například když vypršela platnost tokenu.

1. Předejte klienta `HttpClient` do sestavení klienta `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Telefonujte s klientem prostřednictvím „metod rozšíření“, například `GetAllInstancesAsync`. Pokud je preferován přístup k základní odpovědi `Microsoft.Rest.HttpOperationResponse` - použijte například „metody zpráv HTTP“ `GetAllInstancesWithHttpMessagesAsync`.

1. Odpověď je pravděpodobně typu `object`, protože metoda může vrátit více typů (například `IList<InstanceInfo>` a `ApiErrorResult`). Chcete-li zkontrolovat návratový typ, použijte objekty v typech odpovědí specifikovaných na [stránce s podrobnostmi o rozhraní API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) pro tuto operaci.

   Pokud potřebujete více informací o požadavku, použijte **metody zpráv HTTP** pro přístup k surovému objektu odpovědi.

### <a name="nodejs-package"></a>Balíček NodeJS

Použijte klientské knihovny NodeJS dostupné prostřednictvím NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Balíček Python

Použijte klientské knihovny Python dostupné prostřednictvím PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
