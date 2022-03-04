---
title: Správa uživatelských oprávnění
description: Informace o oprávněních a rolích uživatele.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a3d21d55d86950953611967bb66712312eb42b4b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355929"
---
# <a name="user-permissions"></a>Uživatelská oprávnění

Stránka **Oprávnění** je místo, kde nastavíte role a oprávnění pro používání přehledů cílové skupiny.

Abyste stránku mohli zobrazit, musíte mít oprávnění správce. Chcete-li přejít na stránku oprávnění v přehledech cílové skupiny, přejděte na **Správa** > **Oprávnění**.

Existují tři typy rolí:

## <a name="viewer"></a>Prohlížející

- Zkoumání přehledů a segmentů na stránkách **Domů** a **Segmenty**.
- Prohledejte a filtrujte profily zákazníků pomocí stránky **Zákazníci**. Pole musí být prohledávatelná.
- Zobrazte a prozkoumejte stránku **Rozšíření**.
- Prozkoumejte a exportujte entity pomocí stránky **Entity**.
- Zobrazení stavu systémových procesů pomocí stránky **Systém**.
- Zobrazte exporty na stránce **Exporty**.
- Instalace a použití řídicího panelu **Power BI Customer Insights**.

## <a name="contributor"></a>Přispěvatel

- Všechna oprávnění, která má k dispozici Prohlížející.
- Načtení a transformace dat pomocí stránky **Zdroje dat**.
- Vyplnění sekcí *Sjednocení dat* (**Mapa**, **Párování** a **Sloučení**), jejichž výsledkem je entita sjednoceného profilu zákazníka.
- Definice **Vztahů** a **Aktivit**.
- Vytváření segmentů pomocí stránky **Segmenty**.
- Vytvořte opatření na stránce **Opatření**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pouze pro rozšíření první strany).
- Spravujte a vytvářejte exporty na základě propojení sdílených s přispěvateli. [Další informace o tom, jak správci umožňují přispěvatelům používat propojení pro exporty](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Správce

- Všechna oprávnění, která má k dispozici Přispěvatel.
- Změna nastavení na stránce **Systém**, včetně pracovního jazyka a plánů aktualizace systémových procesů.
- Zobrazení a přidání oprávnění pomocí stránky **Oprávnění**.
- Nastavení definic vyhledávání a filtrů pro stránku Zákazníci pomocí stránky **Index hledání a filtrování** (přístupné prostřednictvím stránky **Zákazníci**).
- Spravujte propojení a povolte je pro další uživatelské role na stránce **Propojení**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pro všechna rozšíření).
- Exporty spravujte a vytvářejte na stránce **Exporty**.
- Nainstalujte a použijte **Doplněk zákaznické karty**.
- Přidání a použiti **konektoru Power Apps**.
- Povolení využití [rozhraní API aplikace Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Přiřazení oprávnění a rolí

1. V přehledech cílové skupiny přejděte na **Správa** > **Oprávnění**.

1. Volbou **Přidat uživatele** otevřete podokno **Přidat/upravit oprávnění**.

1. Pomocí pole **Vyhledávání** vyhledejte uživatele nebo skupinu Azure Active Directory, jejichž oprávnění chcete upravit. Vyberte **Roli**, kterou chcete přiřadit tomuto uživateli nebo skupině.

1. Zvolte **Uložit**. Aktuální prostředí bude automaticky sdíleno s uživatelem nebo členy skupiny, jejichž oprávnění jste změnili. Uživatelé mají přístup k aplikaci Customer Insights a vykonávají činnost dle své zadané role.

## <a name="view-current-permissions"></a>Zobrazit aktuální oprávnění

V přehledech cílové skupiny přejděte na **Správce** > **Oprávnění**, kde zjistíte, která přiřazení rolí jsou aktuálně aktivní.

- Sloupec **Typ** určuje jednoho uživatele, skupinu nebo aplikaci. Systém podporuje jednotlivé uživatele a skupiny.
- Role jsou určeny ve sloupci **Role**.
- Výběrem některého nadpisu sloupce seřadíte výsledky podle hodnoty daného sloupce.
- Pomocí **vyhledávacího** pole v horní části stránky vyhledejte konkrétní uživatele.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
