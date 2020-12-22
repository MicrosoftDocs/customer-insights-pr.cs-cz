---
title: Domovská stránka v přehledech cílové skupiny
description: Začněte s průzkumem aplikace na domovské stránce.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405381"
---
# <a name="create-a-new-environment"></a>Vytvořit nové prostředí

## <a name="create-a-trial-environment"></a>Vytvoření zkušebního prostředí

Zkušební verzi si můžete zaregistrovat na [stránce pro registraci zkušební verze](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Zkušební verze vyprší po 30 dnech.

1. Vyberte možnost **Zaregistrovat bezplatnou zkušební verzi** a vyberte **Zaregistrovat se**.

1. Uveďte svou pracovní nebo školní e-mailovou adresu, řekněte nám o sobě více a vyberte **Další**.

1. Zadejte **Název** nového prostředí. 

1. Vyberte typ zkušební verze.

1. Zvolte **Oblast** pro vaše prostředí.

1. Volitelně pro správce organizace Dynamics 365: Vyberte **Upřesnit nastavení** a zadejte adresu URL vaší organizace, abyste mohli používat funkce predikce, například predikovat ztracené zákazníky.

1. Vyberte **Vytvořit**. 

Po vytvoření prostředí uvidíte **ukázkové** prostředí, které vám umožní prozkoumat aplikaci pomocí fiktivních dat. Ukázková data můžete změnit tak, aby odpovídala vašemu odvětví. Vyberte ikonu **Nastavení** v záhlaví a vyberte **Nastavení ukázky**. Dále můžete změnit vizuální motiv. 

[Přejděte do prostředí](#change-between-environments), které jste vytvořili během procesu registrace, abyste mohli pracovat se svými vlastními daty.

## <a name="create-a-new-production-or-sandbox-environment"></a>Vytvoření nového provozního nebo sandboxového prostředí

Ve vašem prostředí vyberte ikonu **Nastavení** v záhlaví a vyberte **Nové prostředí**.

Postupujte podle pokynů jako byste [tvořili zkušební prostředí](#create-a-trial-environment). Při výběru možnosti **Upřesnit nastavení** získáte další možnosti k uchování dat ve vašem vlastním datovém jezeru Azure Data Lake. Zadejte název a klíč účtu k navázání připojení k vašemu datovému jezeru Azure Data Lake. Ve výchozím nastavení jsou data uložena ve spravovaném datovém jezeře Customer Insights.

> [!IMPORTANT]
> Uložením dat do úložiště Azure Data Lake Storage souhlasíte, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights. [Další informace naleznete v centru zabezpečení Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Prozkoumání domovské stránky

Můžete [přistupovat k prostředí Customer Insights](https://home.ci.ai.dynamics.com/) na následující adrese URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Domovská stránka** zobrazuje přehled vaší zákaznické základny a klíčové metriky ke sledování stavu vaší firmy.

> [!div class="mx-imgBorder"] 
> ![Přehledy na domovské stránce](media/home-page-insights.png "Přehledy na domovské stránce")

V sekci **Poslední segmenty** uvidíte skupiny zákazníků na základě demografických, behaviorálních nebo transakčních atributů, které jste definovali. [Vytváření segmentů](segments.md) vám pomůže lépe zacílit na vaše obchodní aktivity.

**Nedávná měření** ukazují dlaždice s [měřeními](measures.md). Měření jsou klíčové ukazatele výkonu (KPI), které jste definovali. Například průměrná pravděpodobnost ztráty zákazníků nebo průměrné online výdaje na zákazníka.

Část **Nedávná obohacení** uvádí výsledky běhů obohacování, které byly nedávno dokončeny. Obohacení přidává informace o vaší zákaznické základně. Například porozuměním zájmům a značkám, ke kterým mají vztah. Tyto informace lze získat díky možnostem [rozšíření](enrichment-microsoft-graph.md) po dokončení fází [mapování](map-entities.md), [spárování](match-entities.md) a [sloučení](merge-entities.md).

## <a name="change-between-environments"></a>Změna mezi prostředími

Po nastavení a konfiguraci [zdrojů dat](data-sources.md) budete moci přejít z ukázkového prostředí do prostředí v ostrém provozu. Použití produkčního prostředí vám umožní pracovat s vašimi vlastními zákaznickými daty. Vyberte ovládaí prvek **Prostředí** v pravém horním rohu stránky pro změnu prostředí.

> [!div class="mx-imgBorder"] 
> ![Přepnout prostředí](media/home-page-environment-switcher.png "Přepnout prostředí")

Správci mohou vytvářet a spravovat [více prostředí](manage-environments.md). Udržování více než jednoho prostředí může být užitečné, pokud například vaše organizace působí na mezinárodní úrovni a potřebujete oddělit data a přehledy různými způsoby.

## <a name="next-step"></a>Další krok

Chcete-li na domovské stránce zobrazit své vlastní přehledy, musíte nejprve [přidat zdroje dat](data-sources.md) a [sjednotit](data-unification.md) vaše data pro vytvoření profilů zákazníků.
