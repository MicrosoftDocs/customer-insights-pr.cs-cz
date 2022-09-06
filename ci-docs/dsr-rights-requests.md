---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti o práva subjektu údajů Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387103"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žádosti o práva subjektu údajů (DSR) v rámci GDPR

Obecné nařízení Evropské unie o ochraně osobních údajů (GDPR) je v platnosti od 25. května 2018. Poskytuje jednotlivcům významná práva týkající se jejich údajů. GDPR se zabývá ochranou a umožněním osobních práv jednotlivců. Více informací o závazku společnosti Microsoft k zabezpečení a dodržování předpisů si přečtěte v [Centru zabezpečení Microsoft](https://www.microsoft.com/trust-center).

Zavázali jsme se pomáhat našim zákazníkům splnit jejich požadavky GDPR. Zahrnuje právo na mazání nebo export dat, která zahrnují osobní údaje, jako jsou ID uživatelů, telefonní čísla a e-mailové adresy. Správci mohou implementovat požadavky uživatelů na odstranění nebo export osobních údajů.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Odpověď na žádosti subjektů údajů o odstranění údajů v rámci GDPR pro Customer Insights

Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR). Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.

### <a name="manage-data-subject-delete-requests"></a>Správa požadavků na vymazání subjektu údajů

Customer Insights nabízí následující prostředí produktu k odstranění osobních údajů pro konkrétního zákazníka nebo uživatele:

- **Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights. Nejprve proveďte žádosti o odstranění GDPR v původním zdroj dat.
- **Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights. Všechny žádosti o odstranění GDPR proveďte v Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Správa požadavků na odstranění zákaznických dat

Jako správce Customer Insights odeberte podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat. Ověřte, zda byly požadavky na odstranění GDPR provedeny v původním zdroji dat.

1. Přihlaste se ke službě Dynamics 365 Customer Insights.

1. Přejděte na **Data** > **Zdroje dat**.

1. Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:
   1. Vyberte zdroj dat a poté vyberte **Aktualizovat**.
   1. Zkontrolujte stav zdroje dat ve volbě **Stav**. Zaškrtnutí znamená, že aktualizace proběhla úspěšně. Výstražný trojúhelník znamená, že se něco pokazilo. Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Správa požadavků na výmaz GDPR pro zákaznická data.":::

1. Po úspěšné aktualizaci zdrojů dat spusťte také následné aktualizace. Obzvláště, pokud nemáte naplánovánu opakovanou úplnou aktualizaci Customer Insights.

   > [!IMPORTANT]
   > Statické segmenty nejsou zahrnuty do úplné aktualizace nebo následných aktualizací po požadavku na odstranění. Chcete-li zajistit, že zákaznická data budou odstraněna i ze statických segmentů, znovu vytvořte statické segmenty s aktualizovanými zdrojovými daty.

#### <a name="manage-delete-requests-for-user-data"></a>Správa žádostí o odstranění údajů uživatele

Jako správce Customer Insights odstraňte údaje o uživatelích Customer Insights.

1. Přihlaste se ke službě Dynamics 365 Customer Insights.

1. Jděte na **Správa** > **Zabezpečení** > a vyberte kartu **Uživatelé**.

1. Zaškrtněte políčko pro uživatele, které chcete odstranit.

1. Vyberte **Odstranit**.

1. Potvrďte odstranění.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR

Právo na přenositelnost údajů umožňuje subjektům údajů požádat o kopii svých osobních údajů v elektronickém formátu (definovaném jako „strukturovaný, běžně používaný, strojově čitelný a interoperabilní formát“), který lze předat jinému správci údajů.

### <a name="manage-export-and-view-requests"></a>Spravujte žádosti o export a zobrazení

Správa požadavků na export zákaznických dat

#### <a name="export-customer-data-tenant-admin"></a>Export údajů zákazníka (správce klienta)

Jako správce klienta exportujte data zákazníků.

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu zákazníka v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
2. Potvrďte potvrzení pro export dat pro požadovaného zákazníka.
3. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

#### <a name="export-user-data-tenant-admin"></a>Export údajů uživatele (správce klienta)

Jako správce klienta exportujte data uživatele.

1. Pošlete e-mail na adresu D365CI@microsoft.com a určete e-mailovou adresu uživatele v žádosti. Tým Customer Insights zašle e-mail na zaregistrovanou e-mailovou adresu klienta s žádostí o potvrzení exportu dat.
1. Potvrďte potvrzení pro export dat pro požadovaného uživatele.
1. Exportovaná data obdržíte prostřednictvím e-mailové adresy správce klienta.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Zpracování odstranění dat v Dynamics 365 Customer Insights

Data jsou odstraněna (datové oddíly a snímky dat), pokud jsou datové oddíly a snímky dat neaktivní déle než 30 dní, což znamená, že byly nahrazeny novým datovým oddílem a snímkem prostřednictvím obnovy zdrojů dat.

Ne všechna data a snímky jsou odstraněny. Nejnovější datový oddíl a snímek dat jsou aktivní, protože se používají v Customer Insights. U nejnovějších dat nezáleží, zda byly nebo nebyly zdroje dat během posledních 30 dnů aktualizovány.

[!INCLUDE [footer-include](includes/footer-banner.md)]
