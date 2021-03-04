---
title: Vztahy mezi entitami a cesty k entitám
description: Vytvářejte a spravujte vztahy mezi entitami z více zdrojů dat.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269863"
---
# <a name="relationships-between-entities"></a>Vztahy mezi entitami

Vztahy vám pomůžou propojit entity a generovat graf dat, když entity sdílejí společný identifikátor (cizí klíč), na který lze odkazovat z jedné entity do druhé. Připojené entity umožňují definovat segmenty a míry na základě více zdrojů dat.

Existují dva typy vztahů. Neupravitelné systémové vztahy, které jsou vytvořeny automaticky, a vlastní vztahy vytvořené a nakonfigurované uživateli.

Během procesů párování a sloučení jsou systémové vztahy vytvořeny na pozadí na základě inteligentního párování. Tyto vztahy pomáhají propojit záznamy profilu zákazníka se záznamy jiných odpovídajících entit. Následující diagram znázorňuje vytvoření tří systémových vztahů, když je entita zákazníka spárována s dalšími entitami k vytvoření konečné entity profilu zákazníka.

> [!div class="mx-imgBorder"]
> ![Vytváření vztahu](media/relationships-entities-merge.png "Vytváření vztahu")

- **Vztah *CustomerToContact*** byl vytvořen mezi entitou Zákazník a entitou Kontakt. Entita zákazníka získá klíčové pole **Contact_contactId**, které se vztahuje ke klíčovému poli entity Kontakt **contactId**.
- **Vztah *CustomerToAccount*** byl vytvořen mezi entitou Zákazník a entitou Obchodní vztah. Entita zákazníka získá klíčové pole **Account_accountId**, které se vztahuje ke klíčovému poli entity Obchodní vztah **accountId**.
- **Vztah *CustomerToWebAccount*** byl vytvořen mezi entitou Zákazník a entitou WebAccount. Entita zákazníka získá klíčové pole **WebAccount_webaccountId**, které se vztahuje ke klíčovému poli entity WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Vytvoření vztahu

Definujte vlastní vztahy na stránce **Vztahy**. Každý vztah se skládá z entity Zdroj (entity, která drží cizí klíč) a entity Cíl (entity, na kterou cizí klíč zdrojové entity odkazuje).

1. V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.

2. Vyberte **Nový vztah**.

3. V podokně **Přidat vztah** zadejte následující informace:

   > [!div class="mx-imgBorder"]
   > ![Zadat podrobnosti vztahu](media/relationships-add.png "Zadat podrobnosti vztahu")

   - **Název vztahu**: Název, který odráží účel vztahu (například **AccountWebLogs**).
   - **Popis**: Popis vztahu.
   - **Zdrojová entita**: Vyberte entitu, která se používá jako zdroj ve vztahu (například WebLog).
   - **Kardinalita**: Vyberte kardinalitu záznamů zdrojové entity. Například "mnoho" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.
   - **Pole zdrojového klíče**: Představuje pole cizího klíče ve zdrojové entitě. WebLog má například cizí klíčové pole **accountId**.
   - **Cílová entita**: Vyberte entitu, která se používá jako cíl ve vztahu (například WebAccount).
   - **Cílová kardinalita**: Vyberte kardinalitu záznamů cílové entity. Například "jedna" znamená, že více záznamů Weblog souvisí s jedním webovým účtem.
   - **Cílové klíčové pole**: Toto pole představuje klíčové pole cílové entity. WebAccount má například klíčové pole **accountId**.

> [!NOTE]
> Podporovány jsou pouze vztahy N:1 a 1:1. Vztahy N:N lze vytvořit pomocí dvou vztahů N:1 a entity propojení (entita, která se používá k připojení zdrojové entity a cílové entity).

## <a name="delete-a-relationship"></a>Odstranit vztah

1. V přehledech cílové skupiny přejděte na **Data** > **Vztahy**.

2. Zaškrtněte políčka u všech vztahů, které chcete odstranit.

3. Vyberte **Odstranit** v horní části tabulky **Vztahy**.

4. Odstranění potvrďte.

## <a name="next-step"></a>Další krok

Systém a vlastní vztahy se používají k vytvoření segmentů založených na více zdrojích dat, které již nejsou prosíceny. Další informace najdete v tématu [Segmenty](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]