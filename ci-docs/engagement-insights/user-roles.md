---
title: Role a oprávnění
description: Přehled dostupných rolí a oprávnění pro členy pracovního prostoru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036685"
---
# <a name="roles-and-permissions"></a>Role a oprávnění

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovní prostor je prostor pro ukládání a správu událostí a sestav. Člen je uživatel, který má přístup do pracovního prostoru. Členům můžete přiřadit pracovní prostor a definovat jejich role a oprávnění. Role správce spravují pracovní prostory a prostředí a konfigurují přehledy zapojení pro ostatní uživatele. Role přispěvatele jsou zaměřeny na analytiky, kteří nepotřebují konfigurovat přehledy zapojení, ale chtějí vytvářet vlastní přehledy, trychtýře nebo segmenty.

## <a name="permissions"></a>Oprávnění
  
Následující tabulka identifikuje oprávnění pro každou roli. 

| Oprávnění | Správce prostředí | Správce pracovního prostoru | Přispěvatel prostředí | Přispěvatel pracovního prostoru | 
|--|--|--|--|--|
| Vytváření prostředí (tvůrce se automaticky stává správcem prostředí) | X* | X* | X* | X* |  
| Konfigurace prostředí (členové prostředí, odstranění prostředí) | X |  |  |  |  
| Vytvoření pracovních prostorů | X |  |  |  |  
| Konfigurace pracovních prostorů (členové pracovního prostoru, odstranění pracovního prostoru) | X | X |  |  |  
| Konfigurace událostí a upřesněných událostí | X | X | |  |  
| Zobrazení událostí pracovního prostoru a upřesněných událostí | X | X | |  |  
| Zobrazení prostředků pracovního prostoru (sestavy, segmenty a metriky)| X | X | X | X |  
| Vytvoření vlastních sestav a trychtýřů | X | X | X | X |  
| Vytvoření základních metrik a dimenzí| X | X |  |  |  
| Vytvoření segmentů| X | X | X | X |  

* Lze vytvořit zkušební prostředí pouze v náhledu. 

## <a name="add-members"></a>Přidat členy

Můžete přidávat a odebírat členy z pracovních prostorů a prostředí. Další informace viz [Prostředí a pracovní prostory](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
