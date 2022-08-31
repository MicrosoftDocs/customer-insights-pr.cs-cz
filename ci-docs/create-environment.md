---
title: Vytvořit nové prostředí
description: Kroky k vytvoření prostředí v Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304235"
---
# <a name="create-a-new-environment"></a>Vytvořit nové prostředí

Po [zakoupení licence předplatného pro Dynamics 365 Customer Insights](paid-license.md) globální správce klienta Microsoft 365 obdrží e-mail s výzvou k vytvoření prostředí. Začněte tak, že přejdete na [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start). V tomto scénáři začněte částí [Krok 1: Poskytnutí základních informací](#step-1-provide-basic-information).

Po vytvoření prvního prostředí může globální správce klienta Microsoft 365 [přidat uživatele ze své organizace jako správce](permissions.md). Tito správci pak mohou spravovat uživatele a prostředí. Pokud vaše organizace zakoupí více než jednu licenci Customer Insights, [požádejte náš tým podpory](https://go.microsoft.com/fwlink/?linkid=2079641) o zvýšení počtu dostupných prostředí. Další informace o kapacitě a přídavné kapacitě naleznete v [Průvodci licencí Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Jakmile budete mít možnost vytvářet další prostředí, přejděte do části [Spuštění procesu vytváření prostředí](#start-the-environment-creation-process).

> [!TIP]
> Pokud chcete službu vyzkoušet, získáte informace v části [Nastavení zkušebního prostředí](trial-signup.md).

## <a name="prerequisites"></a>Předpoklady

[Oprávnění správce](permissions.md) v Customer Insights

## <a name="start-the-environment-creation-process"></a>Spuštění procesu vytváření prostředí

1. Otevřete výběr prostředí a vyberte **+ Nové**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vyberte výběr prostředí.":::

1. Postupujte podle pokynů uvedených v následujících částech a poskytněte všechny požadované informace pro nové prostředí.

## <a name="step-1-provide-basic-information"></a>Krok 1: Poskytnutí základních informací

1. Zvolte, zda chcete vytvořit prostředí od začátku nebo zkopírovat data z jiného prostředí. [Kopírování dat z jiného prostředí](#copy-the-environment-configuration) vyžaduje další kroky.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialogové okno k vytvoření nového prostředí Customer Insights.":::

1. Zadejte následující údaje:

   - **Název**: Název tohoto prostředí. Toto pole je již vyplněno, pokud kopírujete z existujícího prostředí, ale můžete jej změnit.
   - **Vybrat oblast podnikání**: Primární cílová skupina pro nové prostředí: jednotliví spotřebitelé (B2C) nebo [obchodní účty (B2B)](work-with-business-accounts.md). Pokud vaše organizace obchoduje hlavně s jednotlivci, jako je maloobchodník nebo kavárna, vyberte si jednotlivé spotřebitele. Pokud jsou vaše hlavní cílová skupina jiné společnosti, jako je výrobce automobilů nebo papírenská společnost, zvolte obchodní účty.
   - **Typ**: Typ prostředí: provozní nebo sandboxové. Sandboxová prostředí neumožňují plánovanou aktualizaci dat a jsou určena pro předimplementaci a testování. Prostředí sandboxu používají stejnou primární cílovou skupinu jako provozní prostředí, které je aktuálně vybráno.
   - **Oblast**: Oblast, ve které je služba nasazena a hostována. Chcete-li použít [vlastní účet Azure Data Lake Storage](own-data-lake-storage.md) nebo [se připojit k existující organizaci Microsoft Dataverse](customer-insights-dataverse.md), Customer Insights musí být ve stejné oblasti.

1. Vyberte **Další**.

## <a name="step-2-configure-data-storage"></a>Krok 2: Konfigurace úložiště dat

1. Vyberte, kam chcete uložit data Customer Insights:

   - **Úložiště Customer Insights**: Úložiště dat je spravováno automaticky. Je to výchozí možnost a pokud neexistují specifické požadavky na ukládání dat ve vašem vlastním účtu úložiště, doporučujeme použít tuto možnost.
   - **Azure Data Lake Storage**: Vlastní účet Azure Data Lake Storage k ukládání dat, abyste měli plnou kontrolu nad tím, kde jsou data uložena. Postupujte podle kroků v části [Použití vlastního účtu Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Zvolte preferovanou možnost ukládání dat.":::

1. Vyberte **Další**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Krok 3: Připojení k Microsoft Dataverse

Pokud máte prostředí Dataverse, připojte se ke Customer Insights. Sdílejte data s Dataverse a používejte je v podnikových aplikacích založených na Dataverse, jako je Dynamics 365 Marketing nebo aplikace řízené modelem v Power Apps.

1. Postupujte podle kroků v části [Práce s daty Customer Insights v Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="sdílení dat s Microsoft Dataverse automaticky povolenémo pro nové prostředí sítě.":::

1. Vyberte **Další**.

## <a name="step-4-finalize-the-settings"></a>Krok 4: Dokončení nastavení

Zkontrolujte zadaná nastavení. Když vše vypadá kompletně, vyberte **Vytvořit** pro nastavení prostředí.

Chcete-li později změnit některá nastavení, viz [Správa prostředí](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Práce s novým prostředím

Přečtěte si následující články, které vám pomohou začít s konfigurací Customer Insights:

- [Přidání více uživatelů a přiřazení oprávnění](permissions.md).
- [Přijměte zdroje dat](data-sources.md) a proveďte u nich [proces sjednocení dat](data-unification.md) k získání [sjednocených profilů zákazníků](customer-profiles.md).
- [Obohaťte sjednocené profily zákazníků](enrichment-hub.md) nebo [spusťte prediktivní modely](predictions-overview.md).
- [Vytvořte segmenty](segments.md) pro seskupení zákazníků a [měr](measures.md), abyste mohli posoudit klíčové ukazatele výkonu.
- [Nastavte připojení](connections.md) a [exporty](export-destinations.md) ke zpracování dílčích sad dat v jiných aplikacích.

## <a name="copy-the-environment-configuration"></a>Zkopírujte konfiguraci prostředí

Pokud jste se jako správce rozhodli zkopírovat konfiguraci z existujícího prostředí, vyberte jej ze seznamu všech dostupných prostředí ve vaší organizaci.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímek obrazovky s možnostmi nastavení v nastavení prostředí.":::

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

### <a name="set-up-a-copied-environment"></a>Nastavení kopírovaného prostředí

Při kopírování konfigurace prostředí se zobrazí potvrzovací zpráva, když je vytvořeno zkopírované prostředí. Pomocí následujících kroků potvrdíte přihlašovací údaje.

1. Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat. Všechny zdroje zobrazují stav **Povinné přihlašovací údaje**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Seznam zdrojů dat, které byly zkopírovány a vyžadují ověření.":::

1. Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je. Zdroje dat ze složky Common Data Model a z Dataverse musí být vytvořeny ručně se stejným názvem jako ve zdrojovém prostředí.

1. Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**. Zde najdete nastavení ze zdrojového prostředí. Upravte je podle potřeby nebo volbou **Sjednotit** > **Sjednotit profily zákazníků a závislosti** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.

   > [!TIP]
   > Pro účty a kontakty vyberte **Sjednotit účty** > **Sjednotit profily a závislosti**.

1. Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které potřebují aktualizovat.

1. Přejděte na **Správa** > **Připojení**, kde znovu ověřte připojení ve vašem novém prostředí.

1. Jděte na **Data** > **Rozšíření** a **Data** > **Exporty** k jejich opětovné aktivaci.

[!INCLUDE [footer-include](includes/footer-banner.md)]
