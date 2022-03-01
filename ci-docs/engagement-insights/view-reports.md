---
title: Zobrazení datových sestav
description: Pomocí dostupných sestav můžete zobrazit aktivitu na svém webu v reálném čase.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036640"
---
# <a name="view-reports"></a>Zobrazit sestavy

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sestava je kolekce vizualizací dat využívajících data shromážděná prostřednictvím SDK, která vám pomohou měřit a pochopit chování uživatelů. Přehledy zapojení Dynamics 365 Customer Insights zahrnují out-of-the-box (OOB) sestavy pro webové a mobilní projekty.  

## <a name="web-reports"></a>Webové sestavy

K webovým sestavám můžete přejít z části **Zjistit** v levém navigačním podokně.

:::image type="content" source="media/report-menu.png" alt-text="Navigace zobrazující seznam dostupných sestav.":::

### <a name="real-time-usage-report"></a>Sestava využití v reálném čase

Sestava **Využití v reálném čase** poskytuje přehled aktuální aktivity na vašem webu, který se automaticky každou minutu obnovuje. Pomocí využití v reálném čase můžete sledovat dopad marketingových kampaní, tiskových akcí a dalších scénářů na provoz vašeho webu.

### <a name="key-metrics-reports"></a>Sestavy o klíčových metrikách

- **Zobrazení stránky** uvádí zobrazení stránek pro jednotlivé stránky spolu s počtem celkových zobrazení stránek ve vybraném časovém rámci.

- **Návštěvy** zobrazují informace o počtu návštěv a délce návštěvy.

- **Návštěvníci** informují o nových a vracejících se unikátních návštěvnících vašeho webu.

### <a name="content-reports"></a>Sestavy obsahu

- **Odkazy** zobrazují informace o počtu a typu kliknutí.

- **Ukončit stránky** uvádí seznam odkazů, na které návštěvníci klikli, aby opustili váš web.

### <a name="traffic-sources-reports"></a>Sestavy Zdroje přenosů

- **Odkazující** uvádí seznam domén a adres URL, které odkazovaly návštěvníky na váš web.

- **Kódy sledování** uvádí podrobnosti o kódech sledování v odkazech, které přivedly návštěvníky na váš web.

### <a name="visitor-profiles-reports"></a>Sestavy o profilech návštěvníků

- **Zařízení** uvádí seznam fyzických zařízení, která byla použita k přístupu na váš web.

- **Operační systém a prohlížeče** poskytuje informace o operačních systémech a prohlížečích, které byly spuštěny při přístupu na váš web.

- **Místa** zobrazit informace o návštěvnících podle země, regionu a města.

- **Jazyky** uvádějí seznam zobrazení stránky podle preferovaných jazyků návštěvníka.

## <a name="mobile-reports"></a>Mobilní sestavy

Mobilní sestavy jsou seskupeny do kategorií použití v reálném čase, aplikací a uživatelů. K mobilním sestavám můžete přejít z části **Zjistit** v levém navigačním podokně.   

:::image type="content" source="media/mobile-reports.png" alt-text="Uživatelské rozhraní přehledů zapojení, které zobrazuje sestavu využití v reálném čase, která vykresluje data v grafech a seznamech.":::   

### <a name="real-time-usage"></a>Využití v reálném čase

**Využití v reálném čase** poskytuje přehled o aktuální aktivitě ve vaší mobilní aplikaci, která se každou minutu automaticky obnovuje. Pomocí využití v reálném čase můžete sledovat počet uživatelů a relací aktuálně aktivních ve vaší aplikaci a zobrazení na horní obrazovce.

### <a name="app-reports"></a>Sestavy aplikace

- **Zobrazení obrazovky** uvádí zobrazení obrazovky pro jednotlivé obrazovky v aplikaci a celkový počet zobrazení obrazovky ve vybraném časovém rámci. Zobrazení obrazovky můžete prohlížet podle názvu obrazovky nebo titulu obrazovky.

- **Relace** zobrazují informace o počtu relací a délce relace.

- **Frekvence návratů** seskupuje počty relací podle počtu dní od poslední relace.

- **Uživatelé** zobrazuje nové a vracející se uživatele ve vaší mobilní aplikaci.

- **Události** zobrazují seznam všech událostí shromážděných z vaší aplikace plus celkový počet pro každou událost.

### <a name="user-reports"></a>Uživatelské sestavy

- **Verze aplikace** uvádí seznam verzí mobilní aplikace používaných vaší uživatelskou základnou.

- **Zařízení a verze OS** poskytují přehledy o tom, na kterých zařízeních a operačních systémech běží vaše mobilní aplikace.

- **Místa** zobrazují informace o uživatelích aplikace podle země, regionu a města.

## <a name="filter-by-time-or-value"></a>Filtrovat podle času nebo hodnoty

Můžete vybrat časový rámec nebo hodnotu ve webovém nebo mobilním přehledu a zaměřit se na hodnotu nebo časové období. 

- Chcete-li vybrat časový rámec, vyberte **Více [...]** z rozevíracího seznamu sestavy. Výběr časového rozsahu je pro sestavu využití v reálném čase deaktivován; časový rozsah pro sestavu o využití v reálném čase je „nyní“.

- Ve většině sestav vyberte hodnotu v grafu nebo seznamu a filtrujte sestavu pro vybranou hodnotu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]