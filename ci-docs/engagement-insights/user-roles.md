---
title: Role a oprávnění
description: Přehled dostupných rolí a oprávnění pro členy pracovního prostoru.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645529"
---
# <a name="roles-and-permissions"></a>Role a oprávnění

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pracovní prostor je místo pro ukládání a správu událostí a sestav. Další informace viz [Vytvoření pracovního prostoru a přidání členů](create-workspace.md). 

Pracovní prostor může obsahovat následující role a oprávnění:

- Role *Člen* jsou uživatelé, kteří mají přístup do pracovního prostoru. Členům můžete přiřadit pracovní prostor a definovat jejich role a oprávnění. 
- Role *správce* spravují pracovní prostory a prostředí a konfigurují přehledy zapojení pro ostatní uživatele. 
- Role *přispěvatel* jsou zaměřeny na analytiky, kteří nepotřebují konfigurovat přehledy zapojení, ale chtějí vytvářet vlastní přehledy, trychtýře nebo segmenty.

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
