---
title: Vytvoření a konfigurace zkušební verze Customer Insights
description: Proveďte kroky k získání zkušebního předplatného pro Dynamics 365 Customer Insights a nakonfigurujte jej.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f038dedd369ac9e623146b66528efa87c47a8c23769037d8709fa9b804a0b723
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035407"
---
# <a name="set-up-a-trial-environment"></a>Nastavení zkušebního prostředí 

Zkušební verze Dynamics 365 Customer Insights umožňuje zkontrolovat klíčové funkce a zjistit více o různých funkcích. Zkušební předplatné se po vypršení platnosti odstraní. Zkušební prostředí vytvářejí jednotliví uživatelé, kteří se stanou správcem zkušebního prostředí. Mohou pozvat k vyzkoušení zkušební verze více uživatelů a konfigurovat různé funkce.

## <a name="create-a-trial-environment"></a>Vytvoření zkušebního prostředí

Zkušební verzi si můžete zaregistrovat na [stránce pro registraci zkušební verze](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Vyberte možnost **Zaregistrovat bezplatnou zkušební verzi** a vyberte **Zaregistrovat se**.

1. Zadejte svou pracovní nebo školní e-mailovou adresu, řekněte nám více o sobě a vyberte **Začít**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogové okno pro registraci zkušební verzi instance":::

1. Zkontrolujte podmínky a pokračujte výběrem možnosti **Souhlasím**.

1. Zadejte **Název** nového prostředí. 

1. Nastavte **typ** prostředí jako **Zkušební**.

1. V poli **Vybrat ukázku odvětví** můžete volitelně vybrat datovou sadu specifickou pro dané odvětví. Můžete také [přepnout na ukázku odvětví](#use-industry-specific-demo-data-sets-in-audience-insights) později a začít s výchozí datovou sadou.

1. Zvolte **Oblast** pro vaše prostředí.

1. Volitelně, pokud jste správcem organizace Dynamics 365: Vyberte **Pokročilé nastavení** a zadejte adresu URL své organizace, abyste mohli používat funkce predikce, jako je například predikce zákazníků, kteří odejdou. 

1. Vyberte **Vytvořit**. 

Dokončení nastavení prostředí zabere pár okamžiků. Po dokončení budete přesměrováni do ukázkového prostředí nebo ukázky odvětví, které jste zvolili v kroku výše. Nyní můžete aplikaci prozkoumat pomocí ukázkových dat pouze pro čtení. Chcete -li přidat vlastní data do prostředí, přečtěte si téma [Vytvoření ukázkových dat pro konkrétní scénáře ve svém vlastním prostředí](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Screenshot nově vytvořeného zkušebního prostředí.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Použití souborů ukázkových datových sad specifických pro dané odvětví v přehledech cílové skupiny

Propojení skutečných zdrojů dat je jedním z klíčových kroků při využívání výkonu Customer Insights. Chcete-li vyzkoušet funkce, aniž byste zasahovali do svých vlastních dat, můžete volitelně použít ukázková data pro konkrétní odvětví. K dispozici je několik sad ukázkových dat pro následující odvětví: 

-   Automobilový průmysl
-   Bankovnictví
-   Spotřební zboží
-   Státní správa
-   Zdravotní péče
-   Pohostinství
-   Pojištění
-   Výroba
-   Profesionální služby
-   Maloobchod

### <a name="see-industry-specific-demo-data-in-trials"></a>Viz zkušební data pro konkrétní odvětví

Pro verzi Customer Insights jen pro čtení, přizpůsobenou konkrétnímu odvětví nebo scénáři, začněte v ukázkovém prostředí. 
 
1.  V přehledech cílové skupiny vyberte **ukázkové** prostředí v nástroji pro výběr prostředí.

2.  Na stránce **Domů** vyberte možnost z rozevírací nabídky Vybrat ukázku odvětví.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Vyberte si odvětví pro zkušební prostředí.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Vytvářejte ukázková data pro konkrétní scénáře ve svém vlastním prostředí

Jako správce vytvoříte nové prostředí výběrem prostředí v záhlaví aplikace. V novém prostředí můžete konfigurovat své vlastní zdroje dat a nastavit aplikaci podle svých požadavků. 

1.  V přehledech cílové skupiny přejděte na **Data** > **Zdroje dat**.

2.  Chcete -li importovat vlastní zdroje dat, přejděte na [průvodce příjmem dat](data-sources.md).     
   Pokud dáváte přednost práci s ukázkovými daty, která vám umožní vyzkoušet příjem dat, můžete ve svém prostředí zpracovat ukázková data z odvětví. Vyberte možnost **Import z Datahub** a postupujte podle níže uvedených kroků.

3.  Vyberte kartu odvětví, která vyhovuje vašemu scénáři. 

4.  Zkontrolujte a případně aktualizujte navrhovaný název zdroje dat. 

5.  Vyberte **Další** pro příjem ukázkových dat. 

Nyní můžete zpracovaná data použít k přizpůsobení Customer Insights vašemu scénáři. Chcete -li zobrazit prostředí specifické pro přijatá ukázková data, zvolte při výběru prostředí možnost **<Industry> ukázka**.

## <a name="limitations-in-trials"></a>Omezení ve zkušebních verzích

- Zkušební verze jsou ve výchozím nastavení aktivní po dobu 30 dnů. Můžete je však prodloužit po 23. dni, když se přihlásíte do zkušební verze.
- Během zkušební doby nemůžete používat vlastní účet Azure Data Lake Storage k ukládání výstupních dat. Data však můžete přijímat z účtu Data Lake Storage.
- Do úložiště můžete uložit až 3 GB dat prostředí Dataverse, které se automaticky zřídí, když spustíte zkušební verzi Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Zkopírování dat ze zkušební verze do placeného předplatného

Při upgradu na placenou verzi Customer Insights obecně doporučujeme začít s novými daty. 

Pokud si zakoupíte Customer Insights, můžete volitelně zkopírovat data ze zkušebního prostředí. Chcete -li migrovat nastavení ze zkušebního prostředí do placeného, musíte být správcem zkušební verze Customer Insights a globálním správcem vašeho klienta Microsoft 365 nebo správcem Dynamics 365 ve vaší organizaci. 

Po prvním přihlášení k placené instanci Customer Insights budete požádáni o vytvoření nového prostředí. V tomto procesu se můžete rozhodnout zkopírovat konfiguraci z existujícího prostředí a migrovat většinu nastavení. Pokud máte výše uvedená oprávnění, zkušební prostředí se zobrazí v tomto seznamu. Další informace viz [Kopírování konfigurace prostředí](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Další kroky

Přečtěte si následující články, které vám pomohou začít s konfigurací Customer Insights. 

- [Přidání více uživatelů a přiřazení oprávnění](permissions.md).
- [Přijměte zdroje dat](data-sources.md) a proveďte u nich [proces sjednocení dat](data-unification.md) k získání [sjednocených profilů zákazníků](customer-profiles.md).
- [Obohaťte sjednocené profily zákazníků](enrichment-hub.md) nebo [spusťte prediktivní modely](predictions-overview.md).
- Vytvořte [segmenty](segments.md) k seskupení zákazníků a [měřítka](measures.md) ke kontrole KPI.
- Nastavte [připojení](connections.md) a [exporty](export-destinations.md) ke zpracování dílčích sad dat v jiných aplikacích.