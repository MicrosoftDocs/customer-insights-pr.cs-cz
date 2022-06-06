---
title: Práce s daty Customer Insights v Microsoft Dataverse
description: Přečtěte si, jak propojit Customer Insights a Microsoft Dataverse a porozumějte výstupním entitám, které jsou exportovány do Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833668"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Práce s daty Customer Insights v Microsoft Dataverse

Customer Insights poskytuje možnost zpřístupnit výstupní entity jako [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Tato integrace umožňuje snadné sdílení dat a vlastní vývoj prostřednictvím přístupu s žádným nebo minimálním množstvím kódu. [Výstupní entity](#output-entities) jsou k dispozici jako tabulky v prostředí Dataverse. Data můžete použít pro jakoukoli jinou aplikaci založenou na tabulkách Dataverse. Tyto tabulky umožňují scénáře, jako jsou automatizované pracovní postupy prostřednictvím Power Automate nebo vytváření aplikací pomocí Power Apps.

Připojení k prostředí Dataverse vám také umožňuje [ingestovat data z místních zdrojů dat pomocí datových toků a bran platformy Power Platform](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Předpoklady

- Prostředí Customer Insights a Dataverse musí být hostována ve stejné oblasti.
- Musíte mít roli globálního správce v prostředí Dataverse. Ověřte, zda je toto prostředí [Dataverse přidruženo](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) k určitým skupinám zabezpečení a ujistěte se, že jste do těchto skupin zabezpečení přidáni.
- K prostředí Dataverse, které chcete připojit, již není přiřazeno žádné jiné prostředí Customer Insights. Naučte se, jak [odebrat existující připojení k prostředí Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Prostředí Microsoft Dataverse se může připojit pouze k jednomu účtu úložiště. Platí pouze v případě, že nakonfigurujete prostředí k [použití Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Připojení prostředí Dataverse ke Customer Insights

Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse, když [vytváříte prostředí Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="sdílení dat s Microsoft Dataverse automaticky povolenémo pro nové prostředí sítě.":::

Správci mohou nakonfigurovat Customer Insights pro připojení existujícího prostředí Dataverse. Poskytnutím adresy URL k prostředí Dataverse připojuje se k jejich novému prostředí Customer Insights.

Pokud nechcete použít existující prostředí Dataverse, systém vytvoří nové prostředí pro data Customer Insights ve vašem klientovi. [Správci Power Platform mohou kontrolovat, kdo může vytvářet prostředí](/power-platform/admin/control-environment-creation). Pokud nastavujete nové prostředí Customer Insights a správce zakázal vytváření prostředí Dataverse pro všechny kromě správců, nemusí se vám podařit vytvořit nové prostředí.

**Povolte sdílení dat** s Dataverse zaškrtnutím políčka sdílení dat.

Pokud používáte svůj vlastní účet Data Lake Storage, potřebujete také **Identifikátor oprávnění**. Další informace o tom, jak získat identifikátor oprávnění, naleznete v následující části.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povolení sdílení dat s Dataverse z vlastního Azure Data Lake Storage (Preview)

Povolení sdílení dat s Microsoft Dataverse, když vaše prostředí [používá svůj vlastní účet Azure Data Lake Storage](own-data-lake-storage.md), potřebuje dodatečnou konfiguraci. Uživatel nastavující prostředí Customer Insights musí mít minimálně oprávnění **Čtenář dat objektu blob úložiště** na kontejneru *CustomerInsights* v účtu Azure Data Lake Storage.

1. V předplatném Azure vytvořte dvě skupiny zabezpečení – jednu skupinu zabezpečení **Čtenář** a jednu skupinu zabezpečení **Přispěvatel** a nastavte službu Microsoft Dataverse jako vlastníka obou skupin zabezpečení.
2. Prostřednictvím těchto skupin zabezpečení můžete spravovat seznam řízení přístupu (ACL) v kontejneru CustomerInsights v účtu úložiště. Do skupiny zabezpečení **Čtenář** s oprávněním **jen pro čtení** přidejte službu Microsoft Dataverse a všechny obchodní aplikace Dataverse, jako je Dynamics 365 Marketing. Do skupiny zabezpečení **Přispěvatel** přidejte *pouze* aplikace Customers Insights, které budou mít oprávnění **čtení a zápis**, aby mohly zapisovat profily a přehledy.

### <a name="limitations"></a>Omezení

Při používání Dataverse s vlastním účetem Azure Data Lake Storage jsou dvě omezení:

- Existuje mapování jedna ku jedné mezi organizací Dataverse a účtem Azure Data Lake Storage. Jakmile je organizace Dataverse připojena k účtu úložiště, nemůže se připojit k jinému účtu úložiště. Toto omezení brání tomu, aby Dataverse naplnil více účtů úložiště.
- Sdílení dat nebude fungovat, pokud je pro přístup k vašemu účtu úložiště Azure Data Lake potřeba nastavení Azure Private Link, protože je za firewallem. Dataverse aktuálně nepodporuje připojení k privátním koncovým bodům prostřednictvím Private Link.

### <a name="set-up-powershell"></a>Nastavení PowerShell

Chcete-li spustit skripty PowerShellu, musíte nejprve odpovídajícím způsobem nastavit PowerShell.

1. Nainstalujte nejnovější verzi [Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači vyberte klávesu Windows na klávesnicivy, hledejte **Windows PowerShell** a vyberte **Spustit jako správce**.
   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.
2. Importujte tři moduly.
    1. V okně PowerShell zadejte `Install-Module -Name Az.Accounts` a řiďte se pokyny.
    1. Tento postup opakujte pro `Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Kroky konfigurace

1. Stáhněte si dva skripty PowerShell, které potřebujete ke spuštění, z [úložiště GitHub](https://github.com/trin-msft/byol) našeho technika.
    1. `CreateSecurityGroups.ps1`
       - Pro spuštění tohoto skriptu PowerShell potřebujete oprávnění *správce klienta*.
       - Tento skript PowerShell vytvoří dvě skupiny zabezpečení ve vašem předplatném Azure. Jeden pro skupinu Čtenář a druhý pro skupinu Přispěvatel a službu Microsoft Dataverse nastaví jako vlastníka pro obě tyto skupiny zabezpečení.
       - Spusťte tento skript PowerShell v prostředí Windows PowerShell zadáním ID předplatného Azure obsahujícího vaše úložiště Azure Data Lake Storage. Otevřete skript PowerShell v editoru a prohlédněte si další informace a implementovanou logiku.
       - Uložte obě hodnoty ID skupiny zabezpečení vygenerované tímto skriptem, protože je použijeme ve skriptu `ByolSetup.ps1`.

        > [!NOTE]
        > Vytvoření skupiny zabezpečení lze u vašeho klienta zakázat. V takovém případě by bylo potřeba ruční nastavení a váš správce Azure AD by musel [povolit vytvoření skupiny zabezpečení](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Pro spuštění tohoto skriptu potřebujete oprávnění *Vlastník dat v objektech blob služby Storage* na úrovni účtu úložiště / kontejneru nebo vám jej tento skript vytvoří. Přiřazení vaší role lze po úspěšném spuštění skriptu ručně odebrat.
        - Tento skript PowerShell přidá požadované řízení přístupu založené na roli (RBAC) pro službu Microsoft Dataverse a všechny podnikové aplikace Dataverse. Aktualizuje také seznam řízení přístupu (ACL) v kontejneru CustomerInsights pro skupiny zabezpečení vytvořené pomocí skriptu `CreateSecurityGroups.ps1`. Skupina Přispěvatel bude mít oprávnění *rwx* a skupina Čtenář bude mít pouze oprávnění *rx*.
        - Spusťte tento skript PowerShell v prostředí Windows PowerShell zadáním ID předplatného Azure obsahujícího vaše úložiště Azure Data Lake Storage, název účtu úložiště, název skupiny zdrojů a hodnoty ID skupin zabezpečení Čtenář a Přispěvatel. Otevřete skript PowerShell v editoru a prohlédněte si další informace a implementovanou logiku.
        - Po úspěšném spuštění skriptu zkopírujte výstupní řetězec. Výstupní řetězec vypadá takto: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Zadejte výstupní řetězec zkopírovaný shora do pole **Identifikátor oprávnění** v kroku konfigurace prostředí Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurace umožňující sdílení dat z vlastního úložiště Azure Data Lake Storage s Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Odebrání existujícího připojení k prostředí Dataverse

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

| Column            | Typ        | Popis                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID profilu zákazníka                                                                      |
| ActivityId        | String      | Interní ID aktivity zákazníka (primární klíč)                                       |
| SourceEntityName  | String      | Název zdrojové entity                                                                |
| SourceActivityId  | String      | Primární klíč ze zdrojové entity                                                       |
| ActivityType      | String      | Typ sémantické aktivity nebo název vlastní aktivity                                        |
| ActivityTimeStamp | DATETIME    | Časové razítko aktivity                                                                      |
| Název             | String      | Nadpis nebo název aktivity                                                               |
| Popis       | String      | Popis aktivity                                                                     |
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

| Column               | Typ        | Popis                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID profilu zákazníka                                  |
| ModelProvider        | String      | Název poskytovatele modelu                                      |
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
| SegmentMembershipType | String       | Typ zákazníka, který toto členství v segmentu zaznamenává. Podporuje více typů, jako je zákazník, kontakt nebo obchodní vztah. Výchozí: Zákazník  |
| Segmenty       | Řetězec JSON  | Seznam jedinečných segmentů, jichž je profil zákazníka členem      |
| msdynci_identifier  | String   | Jedinečný identifikátor záznamu členství v segmentu. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Identifikátor GUID      | Deterministický GUID generovaný z `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
