---
title: Správa uživatelských oprávnění
description: Informace o oprávněních a rolích uživatele.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689212"
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
- Export segmentů ze stránky **Segmenty**.
- Instalace a použití řídicího panelu **Power BI Customer Insights**.

## <a name="contributor"></a>Přispěvatel

- Všechna oprávnění, která má k dispozici Prohlížející.
- Načtení a transformace dat pomocí stránky **Zdroje dat**.
- Vyplnění sekcí *Sjednocení dat* (**Mapa**, **Párování** a **Sloučení**), jejichž výsledkem je entita sjednoceného profilu zákazníka.
- Definice **Vztahů** a **Aktivit**.
- Vytváření segmentů pomocí stránky **Segmenty**.
- Vytvořte opatření na stránce **Opatření**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pouze pro rozšíření první strany).

## <a name="administrator"></a>Správce

- Všechna oprávnění, která má k dispozici Přispěvatel.
- Změna nastavení na stránce **Systém**, včetně pracovního jazyka a plánů aktualizace systémových procesů.
- Zobrazení a přidání oprávnění pomocí stránky **Oprávnění**.
- Nastavení definic vyhledávání a filtrů pro stránku Zákazníci pomocí stránky **Index hledání a filtrování** (přístupné prostřednictvím stránky **Zákazníci**).
- Definujte cíle segmentu Dynamics 365 Sales pomocí stránky **Cíle exportu**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pro všechna rozšíření).
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
