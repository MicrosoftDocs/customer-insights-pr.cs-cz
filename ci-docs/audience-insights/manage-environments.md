---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304872"
---
# <a name="manage-environments"></a>Správa prostředí

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Tento článek vysvětluje, jak vytvořit novou organizaci a jak zřídit prostředí.

## <a name="sign-up-and-create-an-organization"></a>Registrace a vytvoření organizace

1. Přejděte na webovou stránku [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Vyberte **Začínáme**.

3. Vyberte preferovaný scénář registrace a vyberte odpovídající odkaz.

4. Přijetím podmínek a volbou **Pokračovat** zahajte vytváření organizace.

5. Po vytvoření prostředí budete přesměrováni na [Customer Insights](https://home.ci.ai.dynamics.com).

6. Pomocí ukázkového prostředí prozkoumejte aplikaci nebo vytvořte nové prostředí podle kroků v další části.

7. Po zadání nastavení prostředí vyberte **Vytvořit**.

8. Po úspěšném vytvoření prostředí budete přihlášeni.

## <a name="create-an-environment-in-an-existing-organization"></a>Vytvoření prostředí v existující organizaci

Nové prostředí lze vytvořit dvěma způsoby. Můžete specifikovat zcela novou konfiguraci nebo zkopírovat některá nastavení konfigurace z existujícího prostředí.

> [!NOTE]
> Organizace mohou vytvořit *dvě* prostředí pro každou licenci Customer Insights. Pokud vaše organizace zakoupí více než jednu licenci, [kontaktujte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) a požádejte o zvýšení počtu dostupných prostředí. Další informace o kapacitě a kapacitě doplňků získáte stažením [Průvodce licencováním Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Vytvoření prostředí:

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte **Nové**.

   > [!div class="mx-imgBorder"]
   > ![Nastavení prostředí.](media/environment-settings-dialog.png)

1. V dialogovém okně **Vytvořit prostředí** vyberte **Nové prostředí**.

   Pokud chcete [kopírovat data z aktuálního prostředí](#considerations-for-copy-configuration-preview), vyberte **Kopírovat z existujícího prostředí**. Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.

1. Zadejte následující údaje:
   - **Název**: Název tohoto prostředí. Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.
   - **Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí.
   - **Oblast**: Oblast, ve které je služba nasazena a hostována.
   
1. Volitelně můžete vybrat **Upřesnit nastavení**:

   - **Uložit všechna data do**: Určuje, kam chcete ukládat výstupní data generovaná z Customer Insights. Budete mít dvě možnosti: **Úložiště Customer Insights** (Azure Data Lake spravované týmem Customer Insights) a **Azure Data Lake Storage** (váš vlastní Azure Data Lake Storage). Ve výchozím nastavení je vybráno úložiště Customer Insights.

     > [!NOTE]
     > Uložením dat do úložiště Azure Data Lake Storage souhlasíte s tím, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights. [Další informace naleznete v centru zabezpečení Microsoft.](https://www.microsoft.com/trust-center)
     >
     > V současné době jsou přijímané entity vždy ukládány do Data Lake spravovaného řešením Customer Insights. 
     > 
     > Podporujeme pouze účty Azure Data Lake Storage ze stejné oblasti Azure, kterou jste vybrali při vytváření prostředí. 
     > 
     > Podporujeme pouze účty Azure Data Lake Storage, které mají povolený hierarchický obor názvů.


   - Pro možnost Azure Data Lake Storage si můžete pro ověřování vybrat mezi možností založenou na zdroji a možností založenou na předplatném. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Název **Kontejner** nelze změnit a bude mít hodnotu `customerinsights`.
   
   - Pokud chcete použít [predikce](predictions.md), konfigurovat sdílení dat s Microsoft Dataverse, nebo povolit příjem dat z místních zdrojů dat, uveďte adresu URL prostředí Microsoft Dataverse v části **Konfigurace sdílení dat s Microsoft Dataverse a povolení dalších funkcí**. Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.

     > [!NOTE]
     > - Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.
     > - [Predikce chybějících hodnot v entitě](predictions.md) není momentálně podporováno, když povolíte sdílení dat se službou Data Lake spravovanou Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše. Datové soubory a soubory model.json budou vytvořeny a přidány do složek na základě názvu procesu.

   Pokud vytvoříte více prostředí Customer Insights a zvolíte uložení výstupních entit z těchto prostředí do svého účtu úložiště, vytvoří se pro každé prostředí samostatné složky s ci_<environmentid> v kontejneru.

### <a name="considerations-for-copy-configuration-preview"></a>Úvahy o konfiguraci kopírování (náhled)

Následující nastavení konfigurace se zkopírují:

- Konfigurace funkcí
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

Následující nastavení se *nezkopírují*:

- Profily zákazníků.
- Přihlašovací údaje ke zdroji dat. Budete muset zadat přihlašovací údaje pro každý zdroj dat a ručně aktualizovat zdroje dat.
- Zdroje dat ze složky Common Data Model a Dataverse spravované v Data Lake. Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.

Při kopírování prostředí se zobrazí potvrzovací zpráva o vytvoření nového prostředí. Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.

Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**. Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.

> [!div class="mx-imgBorder"]
> ![Kopírované zdroje dat.](media/data-sources-copied.png)

Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**. Zde najdete nastavení ze zdrojového prostředí. Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.

Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Můžete upravit některé podrobnosti existujících prostředí.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte ikonu **Upravit**.

3. V poli **Upravit prostředí** můžete změnit **zobrazovaný název** prostředí, ale nemůžete změnit **Oblast** nebo **Typ**.

4. Pokud je prostředí nakonfigurováno pro ukládání dat Azure Data Lake Storage, můžete aktualizovat **Klíč účtu**. Nemůžete však změnit **Název účtu** nebo název **Kontejneru**.

5. Volitelně můžete provést aktualizaci z připojení na základě klíče účtu do připojení založeného na prostředcích nebo předplatném. Po upgradu nelze vrátit klíč účtu. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.

6. Volitelně můžete poskytnout adresu URL prostředí Microsoft Dataverse v části **Konfigurace sdílení dat pomocí Microsoft Dataverse a povolení dalších funkcí**. Tyto funkce zahrnují sdílení dat s aplikacemi a řešeními založenými na Microsoft Dataverse, příjem dat z místních datových zdrojů nebo použití [predikcí](predictions.md). Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.

   > [!NOTE]
   > - Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.
   > - [Predikce chybějících hodnot v entitě](predictions.md) momentálně není podporována, pokud povolíte sdílení dat se spravovanou službou Data Lake Microsoft Dataverse.

   Až povolíte sdílení dat s Microsoft Dataverse, spustí se jednorázová úplná aktualizace vašich zdrojů dat a dalších procesů. Pokud procesy aktuálně běží, neuvidíte možnost povolit sdílení dat s Microsoft Dataverse. Chcete-li povolit sdílení dat, počkejte, až se tyto procesy dokončí, nebo je zrušte. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::
   
   Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše. Datové soubory a soubory model.json budou vytvořeny a přidány do příslušných podsložek v závislosti na spuštěném procesu.

## <a name="reset-an-existing-environment"></a>Obnovení existujícího prostředí

Pokud jste správce a chcete odstranit všechny konfigurace a odebrat ingegstovaná data, můžete obnovit prostředí do prázdného stavu.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace. 

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Obnovit**. 

4.  Chcete-li potvrdit odstranění, zadejte název prostředí a vyberte **Obnovit**.

## <a name="delete-an-existing-environment"></a>Odstranění existujícího prostředí

Jako správce můžete odstranit prostředí, které spravujete.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Odstranit**. 

4.  Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
