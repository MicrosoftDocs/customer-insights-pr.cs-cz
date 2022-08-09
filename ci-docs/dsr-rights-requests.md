---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti o práva subjektu údajů Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146687"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žádosti o práva subjektu údajů (DSR) v rámci GDPR

Obecné nařízení Evropské unie o ochraně osobních údajů (GDPR) je v platnosti od 25. května 2018. Poskytuje jednotlivcům významná práva týkající se jejich údajů. GDPR se zabývá ochranou a umožněním osobních práv jednotlivců. Více informací o závazku společnosti Microsoft k zabezpečení a dodržování předpisů si můžete přečíst v [Centru zabezpečení Microsoft](https://www.microsoft.com/trust-center).

Zavázali jsme se pomáhat našim zákazníkům splnit jejich požadavky GDPR. Zahrnuje právo na mazání a export dat, která zahrnují osobní údaje, jako jsou ID uživatelů, telefonní čísla a e-mailové adresy. Správci mohou implementovat požadavky uživatelů na odstranění nebo export osobních údajů.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Odpověď na žádosti o odstranění subjektu údajů GDPR Dynamics 365 Customer Insights

Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR). Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požadavků na vymazání subjektu údajů

Customer Insights nabízí následující prostředí produktu k odstranění osobních údajů pro konkrétního zákazníka nebo uživatele:

- **Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights. Nejprve proveďte žádosti o odstranění GDPR v původním zdroj dat.
- **Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Správa požadavků na odstranění zákaznických dat

Správce Customer Insights může podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat. Ujistěte se, že požadavek na odstranění byl proveden ve vašem zdroji dat, než budete pokračovat podle níže uvedených kroků. 

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
1. Přejděte na **Data** > **Zdroje dat**
1. Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:
   1. Vyberte vertikální tři tečky (&vellip;) a poté vyberte **Obnovit**.
   1. Zkontrolujte stav zdroje dat ve volbě **Stav**. Zaškrtnutí znamená, že aktualizace proběhla úspěšně. Výstražný trojúhelník znamená, že se něco pokazilo. Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.
1. Po úspěšné aktualizaci zdrojů dat spusťte také následné aktualizace. Obzvláště, pokud nemáte naplánovánu opakovanou úplnou aktualizaci Customer Insights. 

> [!IMPORTANT]
> Statické segmenty nejsou zahrnuty do úplné aktualizace nebo následných aktualizací po požadavku na odstranění. Chcete-li zajistit, že zákaznická data budou odstraněna i ze statických segmentů, znovu vytvořte statické segmenty s aktualizovanými zdrojovými daty.

> [!div class="mx-imgBorder"]
> ![Správa požadavků na výmaz GDPR pro zákaznická data.](media/gdpr-data-sources.png "Správa požadavků na výmaz GDPR pro zákaznická data")

##### <a name="manage-delete-requests-for-user-data"></a>Správa žádostí o odstranění údajů uživatele

Správce Customer Insights může odstranit údaje o uživatelích Customer Insights podle těchto kroků:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. Přejděte na **Správce** > **Zabezpečení** > **Oprávnění**.
3. Zaškrtněte políčko pro uživatele, kterého chcete smazat.
4. Vyberte **Odstranit**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR

V rámci našeho závazku s vámi spolupracovat na vaší cestě k obecnému nařízení o ochraně údajů (GDPR) jsme vyvinuli dokumentaci, která vám pomůže s reagovat na žádosti z datových subjektů.

#### <a name="manage-export-and-view-requests"></a>Spravujte žádosti o export a zobrazení

Právo na přenositelnost údajů umožňuje subjektům údajů požádat o kopii svých osobních údajů v elektronickém formátu (definovaném jako „strukturovaný, běžně používaný, strojově čitelný a interoperabilní formát“), který lze předat jinému správci údajů.

##### <a name="export-customer-data-tenant-admin"></a>Export údajů zákazníka (správce klienta)

Správce klienta může exportovat údaje pomocí následujícího postupu:

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu zákazníka v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného zákazníka.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

##### <a name="export-user-data-tenant-admin"></a>Export údajů uživatele (správce klienta)

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu uživatele v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného uživatele.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Zpracování odstranění dat v Dynamics 365 Customer Insights

1. Data budou odstraněna (datové oddíly a snímky dat), pokud jsou datové oddíly a snímky dat neaktivní déle než 30 dní, což znamená, že byly nahrazeny novým datovým oddílem a snímkem prostřednictvím aktualizace zdrojů dat.
2. Ne všechna data a snímky jsou odstraněny. Nejnovější datový oddíl a datový snímek jsou podle definice aktivní, protože se používají v Customer Insights. U nejnovějších dat nezáleží, zda byly nebo nebyly zdroje dat během posledních 30 dnů aktualizovány.

[!INCLUDE [footer-include](includes/footer-banner.md)]
