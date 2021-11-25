---
title: Žádosti o práva subjektu údajů (DSR) v rámci GDPR | Microsoft Docs
description: Odpověď na žádosti subjektů údajů pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732672"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Žádosti o práva subjektu údajů (DSR) v rámci GDPR

Obecné nařízení Evropské unie o ochraně osobních údajů (GDPR) je v platnosti od 25. května 2018. Poskytuje jednotlivcům významná práva týkající se jejich údajů. GDPR se zabývá ochranou a umožněním osobních práv jednotlivců. Více informací o závazku společnosti Microsoft k zabezpečení a dodržování předpisů si můžete přečíst v [Centru zabezpečení Microsoft](https://www.microsoft.com/trust-center).

Zavázali jsme se pomáhat našim zákazníkům splnit jejich požadavky GDPR. Zahrnuje právo na mazání a export dat, která zahrnují osobní údaje, jako jsou ID uživatelů, telefonní čísla a e-mailové adresy. Správci mohou implementovat požadavky uživatelů na odstranění nebo export osobních údajů.

## <a name="audience-insights"></a>Přehledy pro cílovou skupinu

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Odpověď na žádosti subjektů údajů o odstranění údajů v rámci GDPR pro funkci přehledů cílové skupiny Dynamics 365 Customer Insights

Právo na odstranění osobních údajů ze zákaznických údajů organizace je klíčovou ochranou podle obecného nařízení o ochraně osobních údajů (GDPR). Odstranění osobních údajů zahrnuje odstranění všech osobních údajů a protokolů generovaných systémem, s výjimkou informací z protokolu auditu.

#### <a name="manage-data-subject-delete-requests"></a>Správa požadavků na vymazání subjektu údajů

Přehledy cílové skupiny nabízí následující integrované prostředí k odstranění osobních údajů konkrétního zákazníka nebo uživatele:

- **Správa požadavků na výmaz zákaznických dat**: Údaje o zákaznících v nástroji Customer Insights jsou přijímány z původních zdrojů dat mimo Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v původním zdroj dat.
- **Správa žádostí o odstranění údajů uživatele Customer Insights**: Data uživatelů jsou vytvářena v Customer Insights. Všechny žádosti o odstranění GDPR musí být provedeny v Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Správa požadavků na odstranění zákaznických dat

Správce Customer Insights může podle těchto kroků odebrat zákaznická data, která byla odstraněna ze zdroje dat:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**
3. Pro každý zdroj dat v seznamu, který obsahuje odstraněná zákaznická data:
   1. Vyberte (...) a poté volbu **Aktualizovat**.
   2. Zkontrolujte stav zdroje dat ve volbě **Stav**. Zaškrtnutí znamená, že aktualizace proběhla úspěšně. Výstražný trojúhelník znamená, že se něco pokazilo. Pokud se zobrazí výstražný trojúhelník, kontaktujte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Správa požadavků na výmaz GDPR pro zákaznická data.](audience-insights/media/gdpr-data-sources.png "Správa požadavků na výmaz GDPR pro zákaznická data")

##### <a name="manage-delete-requests-for-user-data"></a>Správa žádostí o odstranění údajů uživatele

Správce Customer Insights může odstranit údaje o uživatelích Customer Insights podle těchto kroků:

1. Přihlaste se ke službě Dynamics 365 Customer Insights.
2. V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.
3. Zaškrtněte políčko pro uživatele, kterého chcete smazat.
4. Vyberte **Odstranit**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Odpověď na žádosti subjektu údajů o export údajů v rámci GDPR

V rámci našeho závazku s vámi spolupracovat na vaší cestě k obecnému nařízení o ochraně údajů (GDPR) jsme vyvinuli dokumentaci, která vám pomůže s přípravou. Tato dokumentace popisuje kroky, které můžete dnes podniknout k podpoře dodržování předpisů GDPR, když používáte přehledy cílové skupiny.

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

## <a name="consent-management-preview"></a>Správa souhlasu (Preview)

Funkce správy souhlasu neshromažďuje uživatelská data přímo. Importuje a zpracovává pouze data souhlasu poskytnuté uživateli v jiných aplikacích.

Chcete-li odebrat data souhlasu konkrétních uživatelů, odstraňte je ze zdrojů dat ingestovaných funkcí správy souhlasu. Po aktualizaci zdroje dat budou odebraná data odstraněna také v Centru souhlasu. Aplikace, které používají entitu souhlasu, odstraní také data, která byla odstraněna ze zdroje po [aktualizaci](audience-insights/system.md#refresh-processes). Zdroje dat doporučujeme aktualizovat krátce po reakci na žádost subjektu údajů o odebrání dat uživatele ze všech ostatních procesů a aplikací.


## <a name="engagement-insights-preview"></a>Přehledy zapojení (Preview)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Odstranění a export dat události obsahující identifikovatelné údaje koncového uživatele

Následující části popisují, jak odstranit a exportovat data událostí, která mohou obsahovat osobní údaje.

Odstranění nebo export dat:

1. Označte vlastnosti události, které obsahují data s osobními údaji.
2. Odstraňte nebo exportujte data spojená s konkrétními hodnotami (například: zadané ID uživatele).

#### <a name="tag-and-update-event-properties"></a>Označení a aktualizace vlastnosti události

Osobní údaje jsou označeny na úrovni vlastností události. Nejprve označte vlastnosti, které se uvažují k odstranění nebo exportu.

Chcete-li označit vlastnost události jako obsahující osobní údaje, postupujte takto:

1. Otevřete pracovní prostor obsahující událost.

1. Přejděte na **Data** > **Události** pro zobrazení seznamu událostí ve vybraném pracovním prostoru.
  
1. Vyberte událost, kterou chcete označit.

1. Vyberte **Upravit vlastnosti** a otevřete podokno se seznamem všech vlastností vybrané události.
     
1. Vyberte **...** a poté vyberte **Upravit**, aby se zobrazilo dialogové okno **Aktualizovat vlastnost**.

   ![Upravte událost.](engagement-insights/media/edit-event.png "Upravit událost")

1. V okně **Aktualizovat vlastnost** vyberte **...** v pravém horním rohu a poté vyberte pole **Obsahuje EUII**. Vyberte **Aktualizovat** k uložení změn.

   ![Uloží vaše změny.](engagement-insights/media/update-property.png "Uloží vaše změny.")

   > [!NOTE]
   > Pokaždé, když se schéma události změní nebo vytvoříte novou událost, doporučujeme vyhodnotit vlastnosti přidružené události a v případě potřeby je označit nebo odznačit jako obsahující osobní údaje.

#### <a name="delete-or-export-tagged-event-data"></a>Odstranění nebo export označených data událostí

Pokud byly všechny vlastnosti události označeny odpovídajícím způsobem, jak je popsáno v předchozím kroku, může správce prostředí vydat požadavek na odstranění oproti označeným datům události.

Správa požadavků na vymazání nebo export EUII

1. Přejděte na **Správce** > **Prostředí** > **Nastavení**.

1. V části **Sprvovat identifikovatelné údaje koncového uživatele (EUII)** vyberte **Spravovat EUII**.

##### <a name="deletion"></a>Odstranění

K odstranění můžete do části **Odstranit identifikovatelné údaje o koncovém uživateli (EUII)** zadat seznam uživatelských ID oddělených čárkami. Tyto ID budou poté porovnány se všemi označenými vlastnostmi událostí všech projektů v aktuálním prostředí pomocí přesné shody řetězců. 

Pokud hodnota vlastnosti odpovídá jednomu z poskytnutých ID, přidružená událost bude trvale odstraněna. Z důvodu nevratnosti této akce musíte po výběru **Odstranit** vymazání potvrdit.

##### <a name="export"></a>Export

Proces exportu je identický s procesem mazání, pokud jde o definování hodnot vlastností události v části **Export identifikovatelných údajů koncového uživatele (EUII)**. Dále budete muset poskytnout **URL úložiště Azure Blob** k určení cíle exportu. Adresa URL objektu Azure Blob musí obsahovat a [sdílený přístupový podpis (SAS)](/azure/storage/common/storage-sas-overview).

Po výběru možnosti **Export** všechny události aktuálního týmu, které obsahují odpovídající označené vlastnosti, budou exportovány ve formátu CSV do cíle exportu.

### <a name="good-practices"></a>Osvědčené postupy

* Snažte se vyhnout odesílání událostí, které obsahují osobní údaje.
* Pokud potřebujete odesílat události obsahující data EUII, omezte počet událostí a vlastností událostí, které obsahují data EUII. V ideálním případě se omezte na jednu takovou událost.
* Zajistěte, aby k odeslaným osobním údajům mělo přístup co nejméně lidí.
* U událostí obsahujících osobní údaje nezapomeňte nastavit jednu vlastnost tak, aby vyzařovala jedinečný identifikátor, který lze snadno propojit s konkrétním uživatelem (například ID uživatele). Díky tomu je snazší oddělit data a exportovat nebo odstranit správná data.
* Pro každou událost označte pouze jednu službu jako obsahující osobní údaje. V ideálním případě takovou, která obsahuje pouze jedinečný identifikátor.
* Neoznačujte vlastnosti obsahující podrobné hodnoty (například celé tělo požadavku). Funkce přehledy zapojení používá při rozhodování, které události k odstranění nebo exportu, přesnou shodu řetězců.

[!INCLUDE[footer-include](includes/footer-banner.md)]