---
title: Správa pracovních prostorů a prostředí
description: Jak vytvářet, přejmenovávat a mazat pracovní prostory a prostředí.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645438"
---
# <a name="manage-environments-and-workspaces"></a>Správa prostředí a pracovních prostorů

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Přehled

Tento téma popisuje, jak spravovat pracovní prostory a prostředí, jakmile již byly vytvořeny. 

- *Pracovní prostor* je prostor pro ukládání a správu událostí a sestav. Zde můžete zobrazit aktivitu uživatelů v reálném čase. Když vytváříte pracovní prostor, vyberete typ dat, která se mají do pracovního prostoru odeslat. Aktuálně jsou podporována webová data a mobilní aplikace. Další informace viz [Vytvoření pracovního prostoru a přidání členů](create-workspace.md).

- *Prostředí* je prostor, kde spravujete své pracovní prostory a připojení. Další informace naleznete v tématu [Vytvoření nového prostředí](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Správa existujícího pracovního prostoru

V prostředí můžete udržovat více pracovních prostorů současně. Vaše [role](user-roles.md) určuje, jak v nich můžete pracovat. 

 - Chcete-li spravovat pracovní prostor, musíte být správcem prostředí nebo správcem pracovního prostoru.
 - Jako správce pracovního prostoru můžete stávající pracovní prostory přejmenovat nebo je odstranit. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centrum správy pracovního prostoru":::

### <a name="edit-a-workspace-name"></a>Úprava názvu pracovního prostoru

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Nastavení**.

1. Do políčka **Název pracovního prostoru** zadejte nový název.

1. Výběrem možnosti **Uložit** se vaše změny uplatní.

### <a name="delete-a-workspace"></a>Odstranění pracovního prostoru

Odstraněním pracovního prostoru trvale odeberete veškerý jeho obsah, data, nastavení a oprávnění. Tuto akci nelze vrátit zpět.

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Nastavení**.

1. Vyberte **Odstranit pracovní prostor**. 

1. V dialogu **Odstranit pracovní prostor** zadejte **POTVRDIT ODSTRANěNí** velkými písmeny. 

1. Chcete-li trvale odstranit pracovní prostor, vyberte **Odstranit**.

### <a name="manage-workspace-members"></a>Správa členů pracovního prostoru

1. Přejděte na **Správce** > **Pracovní prostor** a vyberte **Členové**.

1. Vyberte **Přidat členy** k udělení přístupu a [přiřazení rolí](user-roles.md). V současné době je k dispozici pouze **Správce pracovního prostoru**.

1. Vyberte **Přidat členy** a přidejte je do svého pracovního prostoru.

## <a name="manage-an-existing-environment"></a>Správa existujícího prostředí

Jako správce prostředí můžete do prostředí přistupovat z levého navigačního podokna. Můžete konfigurovat nastavení prostředí, další správce prostředí a pracovní prostory. Vyberte záložky pro přesun mezi různými oblastmi v centru pro správu.

:::image type="content" source="media/environment-edit.png" alt-text="Centrum pro správu prostředí.":::

### <a name="rename-an-environment"></a>Přejmenování prostředí

1. Přejděte na **Správce** > **Prostředí** a vyberte **Nastavení**.

1. Aktualizujte **Název prostředí** a vyberte **Uložit** k použití změn.

### <a name="manage-environment-members"></a>Správa členů prostředí

1. Přejděte na **Správce** > **Prostředí** a vyberte **Členové**.

1. Vyberte **Přidat členy** k aktualizaci členů a [přiřazení rolí](user-roles.md). V současné době je k dispozici pouze **Správce prostředí**.

1. Vyberte **Přidat členy** a přidejte je do svého prostředí.

### <a name="delete-an-environment"></a>Odstranění prostředí

Správci prostředí mohou prostředí odstranit. Před odstraněním prostředí musíte odebrat všechny pracovní prostory pod ním.

1. Přejděte na **Správce** > **Prostředí** a vyberte **Nastavení**.

1. Vyberte **Odstranit prostředí**. 

1. V dialogu **Odstranit pracovní prostor** zadejte **POTVRDIT ODSTRANěNí** velkými písmeny. 

1. Pokud chcete prostředí trvale odstranit, vyberte **Odstranit**.

## <a name="manage-connections"></a>Spravovat připojení

Navázání připojení k přehledům cílové skupiny vám umožní zobrazit sestavy ve statistikách zapojení na základě jednotných profilů zákazníků. 

Více informací najdete v části [Vytvoření propojení mezi přehledy cílových skupin a přehledy zapojení](integrate-audience-insights-engagement-insights.md)

## <a name="manage-personal-data"></a>Správa osobních údajů

V zájmu ochrany osobních údajů zákazníka můžete odstranit nebo exportovat identifikovatelná data koncového uživatele.

Další informace viz [Odstranění a export dat události obsahující osobní údaje](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
