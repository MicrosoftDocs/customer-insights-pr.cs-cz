---
title: Tvorba a správa prostředí
description: 'Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.'
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
---

# <a name="manage-environments"></a>Správa prostředí

## <a name="switch-environments"></a>Přepnutí prostředí

Vyberte ovládaí prvek **Prostředí** v pravém horním rohu stránky pro změnu prostředí.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímek obrazovky ovládacího prvku pro přepínání prostředí.":::

Správci mohou [vytvářet](create-environment.md) a spravovat prostředí.

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Můžete upravit některé podrobnosti existujících prostředí.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte ikonu **Upravit**.

3. V poli **Upravit prostředí** můžete aktualizovat nastavení prostředí.

Další informace o nastavení prostředí naleznete v tématu [Vytvoření nového prostředí](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Připojení k Microsoft Dataverseu
   
Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse. 

Poskytněte své vlastní prodtředí Microsoft Dataverse pro sdílení dat (profilů a přehledů) s podnikovými aplikacemi založenými na Dataverse, jako je Dynamics 365 Marketing nebo modelem řízené aplikace v Power Apps.

Pokud chcete použít [připravené modely predikce](predictions-overview.md#out-of-box-models), nakonfigurujte sdílení dat pomocí Dataverse. Nebo můžete povolit příjem dat z místních zdrojů dat a poskytnout adresu URL prostředí Microsoft Dataverse, které spravuje vaše organizace.

Povolení sdílení dat s Microsoft Dataverse zaškrtnutím políčka pro sdílení dat aktivujete kompletní jednorázovou aktualizaci vašich zdrojů dat a všech ostatních procesů.

> [!IMPORTANT]
> 1. Customer Insights a Dataverse musí být ve stejné oblasti, aby bylo možné sdílet data.
> 1. Musíte mít roli globálního správce v prostředí Dataverse. Ověřte, zda je toto prostředí [Dataverse přidruženo](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) k určitým skupinám zabezpečení a ujistěte se, že jste do těchto skupin zabezpečení přidáni.
> 1. K tomuto prostředí Dataverse již není přidruženo žádné existující prostředí Customer Insights. Naučte se, jak [odebrat existující připojení k prostředí Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Povolení sdílení dat s Dataverse z vlastního Azure Data Lake Storage (Preview)

Pokud je vaše prostředí nakonfigurováno pro použití vlastního Azure Data Lake Storage k uchovávání dat Customer Insights, povolení sdílení dat s Microsoft Dataverse vyžaduje zvláštní konfiguraci.

1. V předplatném Azure vytvořte dvě skupiny zabezpečení – jednu skupinu zabezpečení **Čtenář** a jednu skupinu zabezpečení **Přispěvatel** a nastavte službu Microsoft Dataverse jako vlastníka obou skupin zabezpečení.
2. Prostřednictvím těchto skupin zabezpečení můžete spravovat seznam řízení přístupu (ACL) v kontejneru CustomerInsights v účtu úložiště. Do skupiny zabezpečení **Čtenář** s oprávněním **jen pro čtení** přidejte službu Microsoft Dataverse a všechny obchodní aplikace Dataverse, jako je Dynamics 365 Marketing. Do skupiny zabezpečení **Přispěvatel** přidejte *pouze* aplikace Customers Insights, které budou mít oprávnění **čtení a zápis**, aby mohly zapisovat profily a přehledy.
   
#### <a name="prerequisites"></a>Předpoklady

Chcete-li provést skripty prostředí PowerShell, musíte mít importovány následující tři moduly. 

1. Nainstalujte nejnovější verzi [Azure Active Directory PowerShell pro Graph](/powershell/azure/active-directory/install-adv2).
   1. Na počítači vyberte klávesu Windows na klávesnicivy, hledejte **Windows PowerShell** a vyberte **Spustit jako správce**.
   1. V okně PowerShell, které se otevře, zadejte `Install-Module AzureAD`.
2. Importujte tři moduly.
    1. V okně PowerShell zadejte `Install-Module -Name Az.Accounts` a řiďte se pokyny. 
    1. Tento postup opakujte pro `Install-Module -Name Az.Resources` a `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Kroky konfigurace

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
        - Po úspěšném spuštění skriptu zkopírujte výstupní řetězec. Výstupní řetězec vypadá takto: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Zadejte výstupní řetězec zkopírovaný shora do pole **Identifikátor oprávnění** v kroku konfigurace prostředí Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Možnosti konfigurace umožňující sdílení dat z vlastního úložiště Azure Data Lake Storage s Microsoft Dataverse .":::

Customer Insights nepodporuje následující scénáře sdílení dat:
- Pokud povolíte sdílení dat pomocí Dataverse, nebudete moci [vytvořit předpokládané nebo chybějící hodnoty v entitě](predictions.md).
- Pokud povolíte sdílení dat s Dataverse, v prostředí Customer Insights nebudete moci zobrazit žádné volitelné vložené sestavy PowerBI.

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

## <a name="copy-the-environment-configuration"></a>Zkopírujte konfiguraci prostředí

Jako správce můžete při vytváření nového prostředí zkopírovat konfiguraci z existujícího prostředí. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímek obrazovky s možnostmi nastavení v nastavení prostředí.":::

Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.

Následující nastavení konfigurace se zkopírují:

- Ingestované/importované zdroje dat
- Konfigurace sjednocení dat (mapa, shoda, sloučení)
- Segmenty
- Míry
- Vztahy
- Aktivity
- Index hledání a filtrování
- Cíle exportu
- Plánovaná aktualizace
- Rozšíření
- Správa modelů
- Přiřazení rolí

## <a name="set-up-a-copied-environment"></a>Nastavení kopírovaného prostředí

Při kopírování konfigurace prostředí se *nezkopírují* následující data:

- Profily zákazníků.
- Přihlašovací údaje ke zdroji dat. Budete muset zadat přihlašovací údaje pro každý zdroj dat a ručně aktualizovat zdroje dat.
- Zdroje dat ze složky Common Data Model a datového jezera spravovaného Dataverse. Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.
- Tajné kódy připojení, které se používají pro exporty a rozšíření. Musíte znovu ověřit připojení a poté znovu aktivovat rozšíření a exporty. 

Při kopírování prostředí se zobrazí potvrzovací zpráva o vytvoření nového prostředí. Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.

Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**. Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam zdrojů dat, které byly zkopírovány a vyžadují ověření.":::

Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**. Zde najdete nastavení ze zdrojového prostředí. Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.

Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.

Než znovu aktivujete exporty a rozšíření, přejděte na **Správa** > **Připojení**, kde znovu ověřte připojení ve vašem novém prostředí.

## <a name="change-the-owner-of-an-environment"></a>Změna vlastníka prostředí

I když v Customer Insights může mít několik uživatelů oprávnění správce, vlastníkem prostředí je pouze jeden uživatel. Ve výchozím nastavení je to správce, kdo na samém začátku vytváří prostředí. Jako správce prostředí můžete přiřadit vlastnictví jinému uživateli s oprávněním správce.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte ikonu **Upravit**.

1. V poli **Upravit prostředí** přejděte na krok **Základní informace**.

1. V poli **Změnit vlastníka prostředí** vyberte nového vlastníka prostředí.  

1. Vyberte **Zkontrolovat a dokončit** a pak příkazem **Aktualizovat** aplikujte změny. 

## <a name="claim-ownership-of-an-environment"></a>Deklarace vlastnictví prostředí

Pokud vlastník prostředí opustí organizaci nebo je smazán jeho uživatelský účet, prostředí nebude mít vlastníka. Uživatel s oprávněním správce si může nárokovat vlastnictví a stát se novým vlastníkem. Mohou nadále vlastnit prostředí nebo [změnit vlastnictví na jiného správce](#change-the-owner-of-an-environment). 

Chcete-li nárokovat vlastnictví, vyberte tlačítko **Převzít vlastnictví**, které se zobrazí v horní části každé stránky v Customer Insights, když původní vlastník opustil organizaci.

## <a name="reset-an-existing-environment"></a>Obnovení existujícího prostředí

Jako vlastník prostředí můžete resetovat prostředí do prázdného stavu, pokud chcete odstranit všechny konfigurace a odebrat ingestovaná data.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace. 

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Obnovit**. 

4.  Chcete-li potvrdit odstranění, zadejte název prostředí a vyberte **Obnovit**.

## <a name="delete-an-existing-environment"></a>Odstranění existujícího prostředí

Jako vlastník prostředí můžete odstranit prostředí, které spravujete.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Odstranit**. 

4.  Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.

> [!NOTE]
> Odstraněním prostředí se neodstraní přidružení k prostředí Dataverse. Naučte se, jak [odebrat existující připojení k prostředí Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
