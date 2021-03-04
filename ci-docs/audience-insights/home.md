---
title: Domovská stránka v přehledech cílové skupiny
description: Začněte s průzkumem aplikace na domovské stránce.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477033"
---
# <a name="create-a-new-environment"></a>Vytvořit nové prostředí

## <a name="create-a-trial-environment"></a>Vytvoření zkušebního prostředí

Zkušební verzi si můžete zaregistrovat na [stránce pro registraci zkušební verze](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Zkušební verze vyprší po 30 dnech.

1. Vyberte možnost **Zaregistrovat bezplatnou zkušební verzi** a vyberte **Zaregistrovat se**.

1. Uveďte svou pracovní nebo školní e-mailovou adresu, řekněte nám o sobě více a vyberte **Další**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogové okno pro registraci zkušební verzi instance":::

1. Zadejte **Název** nového prostředí. 

1. Vyberte typ zkušební verze.

1. Zvolte **Oblast** pro vaše prostředí.

1. Volitelně pro správce organizace Dynamics 365: Vyberte **Upřesnit nastavení** a zadejte adresu URL vaší organizace, abyste mohli používat funkce predikce, například predikovat ztracené zákazníky.

1. Vyberte **Vytvořit**. 

Po vytvoření prostředí uvidíte **ukázkové** prostředí, které vám umožní prozkoumat aplikaci pomocí fiktivních dat. Ukázková data můžete změnit tak, aby odpovídala vašemu odvětví. Vyberte ikonu **Nastavení** v záhlaví a vyberte **Nastavení ukázky**. Dále můžete změnit vizuální motiv. 

[Přejděte do prostředí](#switch-environments), které jste vytvořili během procesu registrace, abyste mohli pracovat se svými vlastními daty.

## <a name="create-a-new-production-or-sandbox-environment"></a>Vytvoření nového provozního nebo sandboxového prostředí

Ve vašem prostředí vyberte **nástroj pro výběr prostředí** v záhlaví aplikace a vyberte **Nový**.

Postupujte podle pokynů jako byste [tvořili zkušební prostředí](#create-a-trial-environment). Ve výchozím nastavení jsou data uložena ve spravovaném datovém jezeře Customer Insights. Při výběru možnosti **Upřesnit nastavení** získáte další možnosti k uchování dat ve vašem vlastním datovém jezeru Azure Data Lake. Zadejte název a klíč účtu k navázání připojení k vašemu datovému jezeru Azure Data Lake. 

> [!IMPORTANT]
> Uložením dat do úložiště Azure Data Lake Storage souhlasíte, že tato data budou přenesena a uložena v příslušném zeměpisném umístění pro daný účet Azure Storage, které se může lišit od umístění dat uložených ve službě Dynamics 365 Customer Insights. [Další informace naleznete v centru zabezpečení Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Prozkoumání domovské stránky

Máte [přístup k přehledům cílové skupiny z Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na následující adrese URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Domovská stránka** zobrazí přehled segmentů, měr a dat rozšíření (pokud jsou nakonfigurována) po dokončení fází [mapování](map-entities.md), [párování](match-entities.md) a [sloučení](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Přehledy na domovské stránce](media/home-page-insights.png "Přehledy na domovské stránce")

V sekci **Poslední segmenty** uvidíte skupiny zákazníků na základě demografických, behaviorálních nebo transakčních atributů, které jste definovali. [Vytváření segmentů](segments.md) vám pomůže seskupit vaši zákaznickou základnu a lépe zacílit vaše obchodní aktivity.

**Nedávné ukazatele** zobrazí dlaždice s [klíčovými ukazateli výkonu (KPI)](measures.md), které jste definovali. Například průměrná pravděpodobnost odchodu zákazníků nebo průměrné online útraty na zákazníka.

Část **Nedávná obohacení** uvádí výsledky běhů obohacování, které byly nedávno dokončeny. [Rozšíření](enrichment-hub.md) přidává informace o vaší zákaznické základně. Například porozuměním zájmům a značkám, ke kterým mají vztah.

## <a name="switch-environments"></a>Přepnutí prostředí

Vyberte ovládaí prvek **Prostředí** v pravém horním rohu stránky pro změnu prostředí.

> [!div class="mx-imgBorder"] 
> ![Přepnout prostředí](media/home-page-environment-switcher.png "Přepnout prostředí")

Správci mohou vytvářet a spravovat [více prostředí](manage-environments.md). Udržování více než jednoho prostředí může být užitečné, pokud například vaše organizace působí na mezinárodní úrovni a potřebujete oddělit data a přehledy různými způsoby.

## <a name="next-step"></a>Další krok

Chcete-li na domovské stránce zobrazit své vlastní přehledy, musíte nejprve [přidat zdroje dat](data-sources.md) a [sjednotit](data-unification.md) vaše data pro vytvoření profilů zákazníků.


[!INCLUDE[footer-include](../includes/footer-banner.md)]