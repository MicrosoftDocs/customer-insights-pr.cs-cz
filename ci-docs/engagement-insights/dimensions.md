---
title: Zobrazení a vytvoření dimenzí
description: Vytváření, úprava a odstraňování dimenzí.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623624"
---
# <a name="view-and-create-dimensions"></a>Zobrazení a vytvoření dimenzí

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimenze je atribut událostí, který může popisovat, filtrovat nebo seskupovat data. Pokud na svém webu provozujete marketingovou propagaci, můžete pomocí dimenzí třídit návštěvníky na nové a vracející se uživatele.  

Přehledy zapojení zahrnují předem připravené vestavěné dimenze (OOB) pro vlastnosti události. Příklady:

- Název prohlížeče
- Název stránky
- Model zařízení
- Operační systém
- Země/oblast

## <a name="view-dimensions"></a>Zobrazení dimenzí

Dimenze jsou založeny na stávajících vlastnostech události. Když použijete sledovací kód pro přehledy zapojení, automaticky se vytvoří systémové dimenze.

1. V levém navigačním podokně přejděte na **Data**. 
1. Výběrem položky **Dimenze** zobrazíte seznam všech dimenzí v pracovním prostoru. 
   > [!NOTE]
   > Dimenze generované systémem jsou jen ke čtení. Nemůžete je upravit. Vytvářet a upravovat můžete pouze vlastní dimenze.

## <a name="create-a-dimension"></a>Vytvořit dimenzi

Kromě dimenzí generovaných systémem mohou správci prostředí a pracovního prostoru vytvářet vlastní dimenze. Vlastní dimenze jsou založeny na výchozích vlastnostech základních událostí nebo mohou použít [uživatelské vlastnosti události](advanced-SDK-implementation.md).

1. Přejděte na položku **Data** > **Dimenze**.
1. Vyberte **Nová dimenze**.

   :::image type="content" source="media/add-dimension.png" alt-text="Přidání dimenze k události.":::

1. V podokně **Vytvořit dimenzi** vyberte vlastnost, na které bude dimenze založena. Seznam vlastností zobrazí všechny vlastnosti v pracovním prostoru, které nejsou přiřazeny k dimenzi.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Vytvořte novou dimenzi.":::
      
3. Zapište název do pole **Zobrazovaný název**. Volitelně můžete přidat **popis**.
4. Výběrem příkazu **Vytvořit** dimenzi uložte. Může trvat až jednu minutu, než budete moci použít dimenzi ve [vlastní sestavě](custom-reports.md) nebo [segmentu](segments.md). 

## <a name="edit-a-dimension"></a>Úprava dimenze

Název a popis dimenze můžete změnit. Můžete upravovat pouze dimenze vytvořené uživateli, ale nemůžete upravovat systémové dimenze.


1. Přejděte na položku **Data** > **Dimenze**.
1. Vyberte dimenzi, kterou chcete odstranit.
1. V podokně **Upravit dimenzi** aktualizujte dimenzi.
1. Výběrem možnosti **Použít** se vaše změny uloží.

## <a name="delete-a-dimension"></a>Odstranění dimenze

Můžete odstranit pouze dimenze vytvořené uživatelem, ale nemůžete odstranit systémové dimenze.

Odstranění dimenze je trvalé. Sestavy a segmenty, které používají odstraněnou dimenzi, již nebudou fungovat. 

1. Přejděte na položku **Data** > **Dimenze**.
1. Vyberte dimenzi, kterou chcete odstranit.
1. V podokně **Upravit dimenzi** vyberte příkaz **Odstranit dimenzi**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Odstranění dimenze události.":::

1. Odstranění potvrďte zápisem **CONFIRM DELETE** (všechna písmena velká). 
1. Vyberte **Odstranit**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
