---
title: Návod - Vytvoření nového prostředí
description: Kroky k vytvoření prostředí s Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011603"
---
# <a name="how-to-create-a-new-environment"></a>Návod: Vytvoření nového prostředí

Po [zakoupení licence předplatného pro Dynamics 365 Customer Insights](paid-license.md) globální správce klienta Microsoft 365 obdrží e-mail s výzvou k vytvoření prostředí. Začněte tak, že přejdete na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tomto scénáři můžete přejít přímo na [Krok 1: Poskytnutí základních informací](#step-1-provide-basic-information).

Po vytvoření prvního prostředí může globální správce klienta Microsoft 365 [přidat uživatele ze své organizace jako správce](permissions.md). V budoucnu mohou tito správci spravovat uživatele a prostředí. Pokud vaše organizace zakoupí více než jednu licenci Customer Insights, [požádejte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) o zvýšení počtu dostupných prostředí. Další informace o kapacitě a přídavné kapacitě naleznete v [Průvodci licencí Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Pokud chcete službu vyzkoušet, získáte informace v části [Nastavení zkušebního prostředí](trial-signup.md).

## <a name="prerequisites"></a>Předpoklady

Potřebujete [oprávnění správce](permissions.md) v Customer Insights k vytváření nebo správě prostředí.

## <a name="start-the-environment-creation-process"></a>Spuštění procesu vytváření prostředí

1. Otevřete výběr prostředí a vyberte **+ Nové**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte výběr prostředí.":::

1. Postupujte podle pokynů uvedených v následujících částech a poskytněte všechny požadované informace pro nové prostředí. Pokud jste prostředí nakonfigurovali dříve, můžete také [zkopírovat konfiguraci](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Krok 1: Poskytnutí základních informací

V kroku **Základní informace** zvolte, zda chcete vytvořit prostředí od začátku nebo [zkopírovat data z jiného prostředí](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogové okno k vytvoření nového prostředí Customer Insights.":::

Zadejte následující údaje:

- **Název**: Název tohoto prostředí. Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.
- **Vyberte svou firmu**: Vyberte primární cílovou skupinu pro nové prostředí. Můžete pracovat s jednotlivými spotřebiteli (B2C) nebo [obchodními účty](work-with-business-accounts.md) (B2B). Pokud vaše organizace obchoduje hlavně s jednotlivci, jako je maloobchodník nebo kavárna, vyberte si jednotlivé spotřebitele. V případě, že vaše hlavní cílová skupina jsou jiné společnosti, jako je výrobce automobilů nebo papírenská společnost, zvolte obchodní účty.
- **Typ**: Vyberte, zda chcete vytvořit provozní nebo sandboxové prostředí. Sandboxová prostředí neumožňují plánovanou aktualizaci dat a jsou určena pro předimplementaci a testování. Prostředí sandboxu používají stejnou primární cílovou skupinu jako provozní prostředí, které je aktuálně vybráno.
- **Oblast**: Oblast, ve které je služba nasazena a hostována. Chcete-li použít [vlastní účet Azure Data Lake Storage](own-data-lake-storage.md) nebo [se připojit k existující organizaci Microsoft Dataverse](customer-insights-dataverse.md), Customer Insights musí být ve stejné oblasti.

## <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurace úložiště dat

V kroku **Úložiště dat** z přehledů cílové skupiny vyberte, kam chcete data Customer Insights uložit.

Můžete si zvolit ze dvou možností:

- **Úložiště Customer Insights**: Úložiště dat spravuje tým Customer Insights. Je to výchozí možnost a pokud neexistují specifické požadavky na ukládání dat ve vašem vlastním účtu úložiště, doporučujeme použít tuto možnost.
- **Azure Data Lake Storage**: Zadejte vlastní účet Azure Data Lake Storage k ukládání dat, abyste měli plnou kontrolu nad tím, kde jsou data uložena. Více informací v části [Použití vlastního účtu Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Zvolte preferovanou možnost ukládání dat.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Připojení k Microsoft Dataverse

Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse. Sdílejte data s Dataverse a používejte je v podnikových aplikacích založených na Dataverse, jako je Dynamics 365 Marketing nebo aplikace řízené modelem v Power Apps.


Pokud nemáte vlastní prostředí Dataverse, nechte toto pole prázdné a my vám ho vytvoříme.

Více informací viz [Práce s daty Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="sdílení dat s Microsoft Dataverse automaticky povolenémo pro nové prostředí sítě.":::

### <a name="step-4-finalize-the-settings"></a>Krok 4: Dokončení nastavení

V kroku **Kontrola** projděte všechna zadaná nastavení. Když vše vypadá kompletně, vyberte **Vytvořit** pro nastavení prostředí.

Některá nastavení můžete změnit později. Další informace naleznete v tématu [Správa prostředí](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Práce s novým prostředím

Přečtěte si následující články, které vám pomohou začít s konfigurací Customer Insights:

- [Přidání více uživatelů a přiřazení oprávnění](permissions.md).
- [Přijměte zdroje dat](data-sources.md) a proveďte u nich [proces sjednocení dat](data-unification.md) k získání [sjednocených profilů zákazníků](customer-profiles.md).
- [Obohaťte sjednocené profily zákazníků](enrichment-hub.md) nebo [spusťte prediktivní modely](predictions-overview.md).
- [Vytvořte segmenty](segments.md) pro seskupení zákazníků a [měr](measures.md), abyste mohli posoudit klíčové ukazatele výkonu.
- [Nastavte připojení](connections.md) a [exporty](export-destinations.md) ke zpracování dílčích sad dat v jiných aplikacích.

## <a name="copy-the-environment-configuration"></a>Zkopírujte konfiguraci prostředí

Jako správce můžete při vytváření nového prostředí zkopírovat konfiguraci z existujícího prostředí.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímek obrazovky s možnostmi nastavení v nastavení prostředí.":::

Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.

Následující nastavení konfigurace se zkopírují:

- Zdroje dat importované přes Power Query
- Konfigurace sjednocení dat
- Segments
- Opatření
- Relace
- Aktivity
- Index hledání a filtrování
- Exporty
- Plán aktualizace
- Rozšíření
- Prediktivní modely
- Přiřazení rolí

## <a name="set-up-a-copied-environment"></a>Nastavení kopírovaného prostředí

Když zkopírujete konfiguraci prostředí, musíte k potvrzení přihlašovacích údajů provést několik dalších kroků:

- Profily zákazníků. Nejprve ověřte a přijměte zdroje dat a spusťte sjednocení dat, abyste znovu vytvořili profily zákazníků.
- Přihlašovací údaje ke zdroji dat. Musíte zadat přihlašovací údaje pro každý zdroj dat, abyste mohli ručně ověřit a obnovit zdroje dat.
- Zdroje dat ze složky Common Data Model a Dataverse. Tyto zdroje dat musíte vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.
- Tajné kódy připojení, které se používají pro exporty a rozšíření. Musíte znovu ověřit připojení a poté znovu aktivovat rozšíření a exporty.

Po vytvoření zkopírovaného prostředí se zobrazí potvrzovací zpráva. Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.

Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**. Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam zdrojů dat, které byly zkopírovány a vyžadují ověření.":::

Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**. Zde najdete nastavení ze zdrojového prostředí. Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.

Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.

Než znovu aktivujete exporty a rozšíření, přejděte na **Správa** > **Připojení**, kde znovu ověřte připojení ve vašem novém prostředí.

[!INCLUDE [footer-include](includes/footer-banner.md)]
