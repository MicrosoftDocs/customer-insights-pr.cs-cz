---
title: Vytvoření prostředí v Customer Insights
description: Kroky k vytvoření prostředí s licencovaným předplatným pro Dynamics 365 Customer Insights.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d29992c88bd54fcfcf5e6429a89a34b6f73148c8
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088094"
---
# <a name="create-an-environment-in-audience-insights"></a>Vytvoření prostředí v přehledech cílové skupiny

Tento článek vysvětluje, jak vytvořit nové prostředí poté, co vaše organizace zakoupila předplatné Dynamics 365 Customer Insights. 

Organizace mohou vytvořit *dvě* prostředí pro každou licenci Customer Insights. Pokud vaše organizace zakoupí více než jednu licenci, [požádejte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) o zvýšení počtu dostupných prostředí. Chcete-li získat další informace o kapacitě a doplňkové kapacitě, stáhněte si [Průvodce licencí Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Pokud chcete službu vyzkoušet, získáte informace v části [Nastavení zkušebního prostředí](../trial-signup.md).

## <a name="create-a-new-environment"></a>Vytvořit nové prostředí

Po zakoupení licence předplatného pro Customer Insights globální správce klienta Microsoft 365 obdrží e-mail s výzvou k vytvoření prostředí. Začněte tak, že přejdete na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). 

Řízené prostředí vám pomůže krok za krokem shromáždit všechny požadované informace pro nové prostředí. Potřebujete [oprávnění správce](permissions.md) v přehledech cílové skupiny k vytváření nebo správě prostředí.

1. V přehledech cílové skupiny otevřete nástroj pro výběr prostředí a vyberte **+ Nové**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Vyberte výběr prostředí.":::

1. Postupujte podle pokynů uvedených v následujících částech.

### <a name="step-1-provide-environment-information"></a>Krok 1: Poskytněte informace o prostředí

V kroku **Základní informace** zvolte, zda chcete vytvořit prostředí od začátku nebo [zkopírovat data z jiného prostředí](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogové okno k vytvoření nového prostředí Customer Insights.":::

Zadejte následující údaje:
   - **Název**: Název tohoto prostředí. Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.
   - **Vyberte svou firmu**: Vyberte primární cílovou skupinu pro nové prostředí. Můžete pracovat s jednotlivými spotřebiteli (B2C) nebo [obchodními účty](work-with-business-accounts.md) (B2B).
   - **Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí. Sandboxová prostředí neumožňují plánovanou aktualizaci dat a jsou určena pro předimplementaci a testování. Prostředí sandboxu používají stejnou primární cílovou skupinu jako provozní prostředí, které je aktuálně vybráno.
   - **Oblast**: Oblast, ve které je služba nasazena a hostována.

### <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurace úložiště dat

V kroku **Úložiště dat** z přehledů cílové skupiny vyberte, kam chcete data uložit.

Budete mít dvě možnosti: **Úložiště Customer Insights** (datové jezero Azure spravované týmem Customer Insights) a **Azure Data Lake Storage** (vaše vlastní úložiště Azure Data Lake Storage). Ve výchozím nastavení je vybráno úložiště Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Vyberte Azure Data Lake Storage pro uložení přehledů dat cílové skupiny.":::

Uložením dat do Azure Data Lake Storage souhlasíte s tím, že data budou přenesena a uložena v příslušném geografickém umístění pro daný účet úložiště Azure. Toto umístění se může lišit od místa, kde jsou uložena data Dynamics 365 Customer Insights. Další informace naleznete v [centru zabezpečení Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights aktuálně podporuje následující:
> - Požité entity z toků dat Power BI, které jsou uloženy v souboru Microsoft Dataverse - spravované Data Lake.  
> - Účty Azure Data Lake Storage ze stejné oblasti Azure, kterou jste vybrali při vytváření prostředí.
> - Účty Azure Data Lake Storage, které jsou Gen2 a které mají povolený *hierarchický obor názvů*. Účty úložiště Azure Data Lake Gen1 nejsou podporovány.

Pro možnost Azure Data Lake Storage si můžete pro ověřování vybrat mezi možností založenou na zdroji a možností založenou na předplatném. Více informací viz [Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure](connect-service-principal.md). Název **kontejneru** bude `customerinsights` a nelze jej změnit.

Po dokončení systémových procesů, jako je například příjem dat, systém vytvoří odpovídající složky v účtu úložiště, který jste zadali. Datové soubory a soubory *model.json* se vytvářejí a přidávají do složek na základě názvu procesu.

Pokud vytvoříte více prostředí Customer Insights a rozhodnete se uložit výstupní entity z těchto prostředí do svého účtu úložiště, vytvoří Customer Insights pro každé prostředí samostatné složky s `ci_environmentID` v kontejneru.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Připojení k Microsoft Dataverse
   
Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse.

Pokud chcete použít [připravené modely predikce](predictions-overview.md#out-of-box-models), nakonfigurujte sdílení dat pomocí Dataverse. Nebo můžete povolit příjem dat z místních zdrojů dat a poskytnout adresu URL prostředí Microsoft Dataverse, které spravuje vaše organizace. Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights s datovým jezerem spravovaným Dataverse.

> [!IMPORTANT]
> Customer Insights a Dataverse musí být ve stejné oblasti, aby bylo možné sdílet data.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nepodporuje následující scénáře sdílení dat:
> - Pokud uložíte všechna data do vlastního úložiště Azure Data Lake Storage, nebudete moci povolit sdílení dat pomocí datového jezera spravovaného Dataverse.
> - Pokud povolíte sdílení dat pomocí Dataverse, nebudete moci [vytvořit předpokládané nebo chybějící hodnoty v entitě](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Krok 4: Dokončení nastavení

V kroku **Kontrola** projděte všechna zadaná nastavení. Když vše vypadá kompletně, vyberte **Vytvořit** pro nastavení prostředí. 

Většinu nastavení můžete také změnit později. Další informace naleznete v tématu [Správa prostředí](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Práce s novým prostředím

Přečtěte si následující články, které vám pomohou začít s konfigurací Customer Insights: 

- [Přidání více uživatelů a přiřazení oprávnění](permissions.md).
- [Přijměte zdroje dat](data-sources.md) a proveďte u nich [proces sjednocení dat](data-unification.md) k získání [sjednocených profilů zákazníků](customer-profiles.md).
- [Obohaťte sjednocené profily zákazníků](enrichment-hub.md) nebo [spusťte prediktivní modely](predictions-overview.md).
- [Vytvořte segmenty](segments.md) pro seskupení zákazníků a [měr](measures.md), abyste mohli posoudit klíčové ukazatele výkonu.
- [Nastavte připojení](connections.md) a [exporty](export-destinations.md) ke zpracování dílčích sad dat v jiných aplikacích.
