---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti subjektů údajů pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405382"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žádosti o práva subjektu údajů (DSR) v rámci GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpověď na žádosti subjektů údajů o odstranění údajů v rámci GDPR pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights

Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR). Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.

### <a name="manage-data-subject-delete-requests"></a>Správa požadavků na vymazání subjektu údajů

Přehledy cílové skupiny nabízí následující integrované prostředí k odstranění osobních údajů konkrétního zákazníka nebo uživatele:

- **Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v původním zdroj dat.
- **Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Správa mazacích požadavků na zákaznická data

Správce Customer Insights může podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**
3. Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:
   1. Vyberte (...) a poté volbu **Aktualizovat**.
   2. Zkontrolujte stav zdroje dat ve volbě **Stav**. Zaškrtnutí znamená, že aktualizace proběhla úspěšně. Výstražný trojúhelník znamená, že se něco pokazilo. Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Správa požadavků na výmaz GDPR pro zákaznická data](media/gdpr-data-sources.png "Správa požadavků na výmaz GDPR pro zákaznická data")

#### <a name="manage-delete-requests-for-user-data"></a>Správa žádostí o odstranění údajů uživatele

Správce Customer Insights může odstranit údaje o uživatelích Customer Insights podle těchto kroků:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.
3. Zaškrtněte políčko pro uživatele, kterého chcete smazat.
4. Vyberte **Odstranit**.

> [!div class="mx-imgBorder"]
> ![Zpracování žádostí o odstranění údajů uživatele v rámci GDPR](media/gdpr-permissions.png "Zpracování žádostí o odstranění údajů uživatele v rámci GDPR")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR

V rámci našeho závazku s vámi spolupracovat na vaší cestě k obecnému nařízení o ochraně údajů (GDPR) jsme vyvinuli dokumentaci, která vám pomůže s přípravou. Tato dokumentace popisuje kroky, které můžete dnes podniknout k podpoře dodržování předpisů GDPR, když používáte přehledy cílové skupiny.

### <a name="manage-export-and-view-requests"></a>Spravujte žádosti o export a zobrazení

Právo na přenositelnost údajů umožňuje subjektům údajů požádat o kopii svých osobních údajů v elektronickém formátu (definovaném jako „strukturovaný, běžně používaný, strojově čitelný a interoperabilní formát“), který lze předat jinému správci údajů.

#### <a name="export-customer-data-tenant-admin"></a>Export údajů zákazníka (správce klienta)

Správce klienta může exportovat údaje pomocí následujícího postupu:

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu zákazníka v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného zákazníka.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

#### <a name="export-user-data-tenant-admin"></a>Export údajů uživatele (správce klienta)

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu uživatele v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného uživatele.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.
