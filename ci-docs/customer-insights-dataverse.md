---
title: Práce s daty Customer Insights v Microsoft Dataverse
description: Přečtěte si, jak propojit Customer Insights a Microsoft Dataverse a porozumějte výstupním entitám, které jsou exportovány do Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303821"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práce s daty Customer Insights v Microsoft Dataverse

Aplikace Customer Insights nabízí možnost zpřístupnění výstupních entit v [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Tato integrace umožňuje snadné sdílení dat a vlastní vývoj prostřednictvím přístupu s žádným nebo minimálním množstvím kódu. [Výstupní entity](#output-entities) jsou k dispozici jako tabulky v prostředí Dataverse. Data můžete použít pro jakoukoli jinou aplikaci založenou na tabulkách Dataverse. Tyto tabulky umožňují scénáře, jako jsou automatizované pracovní postupy prostřednictvím Power Automate nebo vytváření aplikací pomocí Power Apps.

Připojení k prostředí Dataverse vám také umožňuje [ingestovat data z místních zdrojů dat pomocí datových toků a bran platformy Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Předpoklady

- Prostředí Customer Insights a Dataverse musí být hostována ve stejné oblasti.
- V prostředí Dataverse musí být nastavena role globálního správce. Ověřte, zda je toto prostředí [Dataverse přidruženo](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) k určitým skupinám zabezpečení a ujistěte se, že jste do těchto skupin zabezpečení přidáni.
- K prostředí Dataverse, které chcete připojit, již není přiřazeno žádné jiné prostředí Customer Insights. Naučte se, jak [odebrat existující připojení k prostředí Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Prostředí Microsoft Dataverse připojené k jedinému účtu úložiště, pokud toto prostředí nakonfigurujete k [použití s vaším úložištěm Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Nárok kapacity úložiště Dataverse

Předplatné Customer Insights vás opravňuje k dodatečné kapacitě pro stávající [kapacitu úložiště Dataverse](/power-platform/admin/capacity-storage) vaší organizace. Přidaná kapacita závisí na počtu profilů, které vaše předplatné používá.

**Příklad:**

Předpokládejme, že získáte 15 GB úložiště databáze a 20 GB úložiště souborů na 100 000 zákaznických profilů. Pokud vaše předplatné zahrnuje 300 000 zákaznických profilů, vaše celková kapacita úložiště je 45 GB (3 x 15 GB) úložiště databáze a 60 GB (3 x 20 GB) úložiště souborů. Podobně pokud máte předplatné B2B s 30 000 účty, vaše celková kapacita úložiště je 45 GB (3 x 15 GB) úložiště databáze a 60 GB (3 x 20 GB) úložiště souborů.

Kapacita protokolů není pro vaši organizaci přírůstková a pevná.

Další podrobné informace o nárocích na kapacitu najdete v [příručce licencování Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Připojení prostředí Dataverse ke Customer Insights

Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse, když [vytváříte prostředí Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="sdílení dat s Microsoft Dataverse automaticky povoleno pro nová prostředí.":::

1. Zadejte adresu URL svého prostředí Dataversenebo ponechte prázdné, aby pro vás bylo vytvořeno.

   > [!NOTE]
   > Po navázání spojení mezi Customer Insights a Dataverse neměňte název organizace pro prostředí Dataverse. Název organizace je použit v adrese URL pro Dataverse a změněný název přeruší spojení s Customer Insights.

   [Správci Power Platform mohou kontrolovat, kdo může vytvářet nová prostředí Dataverse](/power-platform/admin/control-environment-creation). Pokud zkoušíte vytvořit nové prostředí Customer Insights a nelze to provést, správce mohl zakázat vytváření prostředí Dataverse pro všechny kromě správců.

1. Pokud používáte vlastní účet Data Lake Storage:
   1. Vyberte **Povolit sdílení dat** s Dataverse.
   1. Zadejte **Identifikátor oprávnění**. Chcete-li získat identifikátor oprávnění, [povolte sdílení dat s Dataverse z vlastního úložiště Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povolení sdílení dat s Dataverse z vlastního úložiště Azure Data Lake Storage (Preview)

Ve [vlastním účtu Azure Data Lake Storage](own-data-lake-storage.md) ověřte, zda uživatel vytvářející prostředí Customer Insights má minimálně oprávnění **Čtenář dat objektu blob úložiště** v kontejneru `customerinsights` v účtu úložiště.

### <a name="limitations"></a>Omezení

- Mapování pouze jedna ku jedné mezi organizací Dataverse a účtem Azure Data Lake Storage. Jakmile je organizace Dataverse připojena k účtu úložiště, nemůže se připojit k jinému účtu úložiště. Toto omezení brání, aby řešení Dataverse naplnilo více účtů úložiště.
- Sdílení dat nebude fungovat, pokud je pro přístup k vašemu účtu Azure Data Lake Storage potřeba nastavení Azure Private Link, protože je za firewallem. Dataverse aktuálně nepodporuje připojení k privátním koncovým bodům prostřednictvím Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Vytvoření skupin zabezpečení ve vlastním účtu Azure Data Lake Storage

1. V předplatném Azure vytvořte dvě skupiny zabezpečení – jednu skupinu zabezpečení **Čtenář** a jednu skupinu zabezpečení **Přispěvatel** a nastavte službu Microsoft Dataverse jako vlastníka obou skupin zabezpečení.

1. Prostřednictvím těchto skupin zabezpečení můžete spravovat seznam řízení přístupu (ACL) v kontejneru `customerinsights` v účtu úložiště.
   1. Do skupiny zabezpečení **Čtenář** s oprávněním **jen pro čtení** přidejte službu Microsoft Dataverse a všechny obchodní aplikace Dataverse, jako je Dynamics 365 Marketing.
   1. Do skupiny zabezpečení **Přispěvatel** přidejte *pouze* aplikace Customers Insights, které budou mít oprávnění **čtení a zápis**, aby mohly zapisovat profily a přehledy.

### <a name="set-up-powershell"></a>Nastavení PowerShell

Vytvořením prostředí PowerShell můžete spouštět skripty PowerShell.

1. Nainstalujte nejnovější verzi [Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači vyberte klávesu Windows na klávesnicivy, hledejte **Windows PowerShell** a vyberte **Spustit jako správce**.
   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.

1. Importujte tři moduly.
   1. V okně PowerShell zadejte `Install-Module -Name Az.Accounts` a řiďte se pokyny.
   1. Tento postup opakujte pro `Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Spouštění skriptů PowerShell a získeání identifikátoru oprávnění

1. Stáhněte si dva skripty PowerShell, které potřebujete ke spuštění, z [úložiště GitHub](https://github.com/trin-msft/byol) našeho technika.
   - `CreateSecurityGroups.ps1`: Vyžaduje oprávnění správce klienta.
   - `ByolSetup.ps1`: Vyžaduje oprávnění vlastníka dat objektu Storage Blob na úrovni účtu úložiště/kontejneru. Tento skript vytvoří oprávnění za vás. Přiřazení vaší role lze po úspěšném spuštění skriptu ručně odebrat.

1. Spusťte skript `CreateSecurityGroups.ps1` v prostředí Windows PowerShell zadáním ID předplatného Azure obsahujícího vaše úložiště Azure Data Lake Storage. Otevřete skript PowerShell v editoru a prohlédněte si další informace a implementovanou logiku.

   Tento skript vytvoří dvě skupiny zabezpečení ve vašem předplatném Azure: jednu pro skupinu Čtenář a druhou pro skupinu Přispěvatel. Služba Microsoft Dataverse je vlastníkem obou těchto skupin zabezpečení.

1. Uložte obě hodnoty ID skupiny zabezpečení vygenerované tímto skriptem, protože je použijeme ve skriptu `ByolSetup.ps1`.

   > [!NOTE]
   > Vytvoření skupiny zabezpečení lze u vašeho klienta zakázat. V takovém případě by bylo potřeba ruční nastavení a váš správce Azure AD by musel [povolit vytvoření skupiny zabezpečení](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Spusťte skript `ByolSetup.ps1` v prostředí Windows PowerShell zadáním ID předplatného Azure obsahujícího vaše úložiště Azure Data Lake Storage, název účtu úložiště, název skupiny zdrojů a hodnoty ID skupin zabezpečení Čtenář a Přispěvatel. Otevřete skript PowerShell v editoru a prohlédněte si další informace a implementovanou logiku.

   Tento skript přidá požadované řízení přístupu založené na roli (RBAC) pro službu Microsoft Dataverse a všechny podnikové aplikace Dataverse. Aktualizuje také seznam řízení přístupu (ACL) v kontejneru `customerinsights` pro skupiny zabezpečení vytvořené pomocí skriptu `CreateSecurityGroups.ps1`. Skupina Přispěvatel bude mít uděleno oprávnění *rwx* a skupina Čtenář bude mít uděleno pouze oprávnění *r-x*.

1. Zkopírujte výstupní řetězec, který vypadá takto: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Zadejte zkopírovaný výstupní řetězec do pole **Identifikátor oprávnění** v kroku konfigurace prostředí Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurace umožňující sdílení dat z vlastního úložiště Azure Data Lake Storage s Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odebrání existujícího připojení k prostředí Dataverse

Pokud se při připojení k prostředí Dataverse zobrazí chybová zpráva **Tato organizace CDS je již připojena k jiné instanci Customer Insights**, znamená to, že prostředí Dataverse se již v prostředí Customer Insights používá. Stávající připojení můžete odebrat jako globální správce prostředí Dataverse. Projevení změn může trvat několik hodin.

1. Přejděte na [Power Apps](https://make.powerapps.com).
1. Ve výběru prostředí vyberte požadované prostředí.
1. Přejděte na **Řešení**.
1. Odinstalujte nebo odstraňte pojmenované řešení **Doplněk karty zákazníka Dynamics 365 Customer Insights (Preview)**.

NEBO

1. Otevřete prostředí Dataverse.
1. Přejděte na **Upřesnit nastavení** > **Řešení**.
1. Odinstalujte řešení **CustomerInsightsCustomerCard**.

Pokud se odebrání připojení nezdaří kvůli závislostem, musíte odstranit i závislosti. Další informace popisuje článek [Odstranění závislostí](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Výstupní entity

Některé výstupní entity ze Customer Insights jsou dostupné jako tabulky v Dataverse. V následujících částech je popsáno očekávané schéma těchto tabulek.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Obohacení](#enrichment)
- [Predikce](#prediction)
- [Členství v segmentu](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Tato tabulka obsahuje sjednocený profil zákazníka z Customer Insights. Schéma pro sjednocený zákaznický profil závisí na entitách a atributech použitých v procesu sjednocení dat. Schéma profilu zákazníka obvykle obsahuje podmnožinu atributů z [definice Common Data Model sloupce CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabulka AlternateKey obsahuje klíče entit, které se účastnily procesu sjednocení.

|Column  |Typ  |Popis  |
|---------|---------|---------|
|DataSourceName    |String         | Název zdroje dat. Příklad: `datasource5`        |
|EntityName        | String        | Název entity v Customer Insights. Příklad: `contact1`        |
|AlternateValue    |String         |Alternativní ID, které je namapováno na ID zákazníka. Příklad: `cntid_1078`         |
|KeyRing           | Víceřádkový text        | Hodnota JSON  </br> Ukázka: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | ID sjednoceného profilu zákazníka.         |
|AlternateKeyId     | GUID         |  Deterministický GUID AlternateKey založený na msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Ukázka: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tato tabulka obsahuje aktivity uživatelů, které jsou k dispozici v Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Řetězcové      | ID profilu zákazníka                                                                      |
| ActivityId        | Řetězcové      | Interní ID aktivity zákazníka (primární klíč)                                       |
| SourceEntityName  | String      | Název zdrojové entity                                                                |
| SourceActivityId  | String      | Primární klíč ze zdrojové entity                                                       |
| ActivityType      | String      | Typ sémantické aktivity nebo název vlastní aktivity                                        |
| ActivityTimeStamp | DATETIME    | Časové razítko aktivity                                                                      |
| Titulek             | Řetězcové      | Nadpis nebo název aktivity                                                               |
| Description       | String      | Popis aktivity                                                                     |
| Adresa URL               | String      | Odkaz na externí adresu URL specifickou pro aktivitu                                         |
| SemanticData      | Řetězec JSON | Zahrnuje seznam párů hodnot klíče pro pole sémantického mapování specifická pro typ aktivity |
| RangeIndex        | String      | Časové razítko Unix používané pro třídění časové osy aktivity a dotazů na rozsah platnosti |
| mydynci_unifiedactivityid   | GUID | Interní ID aktivity zákazníka (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tato tabulka obsahuje výstupní data měr založených na atributech zákazníka.

| Column             | Typ             | Popis                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | ID profilu zákazníka        |
| Míry           | Řetězec JSON      | Zahrnuje seznam párů hodnot klíče pro název a hodnoty měr pro daného zákazníka | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profilu zákazníka |


### <a name="enrichment"></a>Obohacení

Tato tabulka obsahuje výstup z procesu obohacování.

| Column               | Typ             |  Popis                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | ID profilu zákazníka                                 |
| EnrichmentProvider   | String           | Název poskytovatele pro obohacení                                  |
| EnrichmentType       | String           | Typ obohacení                                      |
| Hodnoty               | Řetězec JSON      | Seznam atributů vytvořených procesem obohacování |
| msdynci_enrichmentid | GUID             | Deterministický GUID generovaný z msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Predikce

Tato tabulka obsahuje výstup z prognóz modelu.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Řetězcové      | ID profilu zákazníka                                  |
| ModelProvider        | Řetězcové      | Název poskytovatele modelu                                      |
| Model                | String      | Název modelu                                                |
| Hodnoty               | Řetězec JSON | Seznam atributů vytvořených modelem |
| msdynci_predictionid | GUID        | Deterministický GUID generovaný z msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Členství v segmentu

Tato tabulka obsahuje informace o členství v segmentech profilů zákazníků.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID profilu zákazníka        |
| SegmentProvider      | String       | Aplikace, která publikuje segmenty.      |
| SegmentMembershipType | Řetězcové       | Typ zákazníka pro záznam členství tohoto segmentu. Podporuje více typů, jako je zákazník, kontakt nebo obchodní vztah. Výchozí: Zákazník  |
| Segmenty       | Řetězec JSON  | Seznam jedinečných segmentů, jichž je profil zákazníka členem      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členství v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Identifikátor GUID      | Deterministický GUID generovaný z `msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
