---
title: Vytvoření a konfigurace placené licence Customer Insights
description: Proveďte kroky k získání licencovaného předplatného pro Dynamics 365 Customer Insights a nakonfigurujte jej.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034444"
---
# <a name="get-started-with-a-paid-subscription"></a>Začínáme s placeným předplatným

Tento článek vysvětluje, jak vytvořit nové prostředí poté, co vaše organizace zakoupila předplatné Dynamics 365 Customer Insights. Pokud si přejete zakoupit Customer Insights, možnosti, jak nás kontaktovat jsou uvedeny na [webu Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Pokud chcete službu a funkce vyzkoušet, získáte informace v části [Nastavení zkušebního prostředí](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Vytvoření prostředí v existující organizaci

Po zakoupení předplacené licence pro Customer Insights obdrží globální správce klienta Microsoft 365 e-mail s pozvánkou k vytvoření prostředí. Začněte tak, že přejdete na [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start). 

Customer Insights není licencován na uživatele, takže se nezobrazí v oblasti licencí. Pokud hledáte licenci v centru pro správu Microsoft 365, přejděte na **Vaše produkty**. 

> [!NOTE]
> Organizace mohou vytvořit *dvě* prostředí pro každou licenci Customer Insights. Pokud vaše organizace zakoupí více než jednu licenci, [kontaktujte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) a požádejte o zvýšení počtu dostupných prostředí. Chcete-li získat další informace o kapacitě a doplňkové kapacitě, stáhněte si [Průvodce licencí Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Vytvoření prostředí:

1. V dialogovém okně **Vytvořit prostředí** vyberte **Nové prostředí**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogové okno k vytvoření nového prostředí Customer Insights.":::

   Doporučujeme začít s nastavením prostředí od nuly. Pokud jste však správcem nebo členem zkušebního prostředí, můžete [zkopírovat data z jiného prostředí](manage-environments.md#copy-the-environment-configuration) výběrem možnosti **Kopírovat z existujícího prostředí**. Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.

1. Zadejte následující údaje:
   - **Název**: Název tohoto prostředí. Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.
   - **Oblast**: Oblast, ve které je služba nasazena a hostována.
   - **Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí. Sandboxová prostředí neumožňují plánovanou aktualizaci dat a jsou určena pro předimplementaci a testování.
   
1. Volitelně můžete vybrat **Upřesnit nastavení**:

   - **Uložit všechna data do**: Určuje, kam chcete ukládat výstupní data generovaná z Customer Insights. Budete mít dvě možnosti: **Úložiště Customer Insights** (Azure Data Lake spravované týmem Customer Insights) a **Azure Data Lake Storage** (váš vlastní Azure Data Lake Storage). Ve výchozím nastavení je vybráno úložiště Customer Insights.

     > [!NOTE]
     > Uložením dat do úložiště Azure Data Lake Storage souhlasíte s tím, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights. [Další informace naleznete v centru zabezpečení Microsoft.](https://www.microsoft.com/trust-center)
     >
     > V současné době jsou přijímané entity z datových toků Power BI uloženy v datovém jezeře spravovaném Microsoft Dataverse. 
     > 
     > Podporujeme pouze účty Azure Data Lake Storage ze stejné oblasti Azure, kterou jste vybrali při vytváření prostředí. 
     > 
     > Podporujeme pouze účty Azure Data Lake Storage, které mají povolený hierarchický obor názvů.


   - Pro možnost Azure Data Lake Storage si můžete pro ověřování vybrat mezi možností založenou na zdroji a možností založenou na předplatném. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Název **Kontejner** nelze změnit a bude mít hodnotu `customerinsights`.
   
   - Pokud chcete použít [předem integrované modely](predictions-overview.md#out-of-box-models), nakonfigurujte sdílení dat s Microsoft Dataverse nebo povolte příjem dat z místních zdrojů dat, poskytněte adresu URL prostředí Microsoft Dataverse v části **Nakonfigurovat sdílení dat s Microsoft Dataverse a povolit další možnosti**. Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.

     > [!NOTE]
     > - Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.
     > - [Predikce chybějících hodnot v entitě](predictions.md) momentálně není podporována, pokud povolíte sdílení dat se spravovanou službou Data Lake Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::

   Po dokončení systémových procesů, jako je například příjem dat, systém vytvoří odpovídající složky na zadaném účtu úložiště. Datové soubory a soubory model.json se vytvářejí a přidávají do složek na základě názvu procesu.

   Pokud vytvoříte více prostředí Customer Insights a zvolíte uložení výstupních entit z těchto prostředí do svého účtu úložiště, vytvoří se pro každé prostředí samostatné složky s ci_<environmentid> v kontejneru.

1. Vyberte **Vytvořit** pro nastavení prostředí. 

## <a name="configure-an-environment"></a>Konfigurace prostředí

Přečtěte si následující články, které vám pomohou začít s konfigurací Customer Insights. 

- [Přidání více uživatelů a přiřazení oprávnění](permissions.md).
- [Přijměte zdroje dat](data-sources.md) a proveďte u nich [proces sjednocení dat](data-unification.md) k získání [sjednocených profilů zákazníků](customer-profiles.md).
- [Obohaťte sjednocené profily zákazníků](enrichment-hub.md) nebo [spusťte prediktivní modely](predictions-overview.md).
- Vytvořte [segmenty](segments.md) k seskupení zákazníků a [měřítka](measures.md) ke kontrole KPI.
- Nastavte [připojení](connections.md) a [exporty](export-destinations.md) ke zpracování dílčích sad dat v jiných aplikacích.
