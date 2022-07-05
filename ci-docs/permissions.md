---
title: Správa uživatelských oprávnění
description: Informace o oprávněních a rolích uživatele.
ms.date: 02/09/2022
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
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054847"
---
# <a name="manage-user-permissions"></a>Správa uživatelských oprávnění

Stránka **Oprávnění** je místem, kde nastavíte role a oprávnění pro používání Customer Insights.

Abyste stránku mohli zobrazit, musíte mít oprávnění správce. Chcete-li se dostat na stránku oprávnění, přejděte na **Správce** > **Zabeupečení** > **Uživatelé**.

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
- Dokončení ***Sjednocení dat**, jehož výsledkem je entita sjednoceného profilu zákazníka.
- Definice **Vztahů** a **Aktivit**.
- Vytváření segmentů pomocí stránky **Segmenty**.
- Vytvořte opatření na stránce **Opatření**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pouze pro rozšíření první strany).
- Spravujte a vytvářejte exporty na základě propojení sdílených s přispěvateli. [Další informace o tom, jak správci umožňují přispěvatelům používat propojení pro exporty](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Správa

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
- [Přiřazení vlastnictví prostředí](manage-environments.md#change-the-owner-of-an-environment) jinému správci.

## <a name="admin-owner"></a>Správce (vlastník)

- Všechna oprávnění dostupná správci.
- [Obnovit a odstranit](manage-environments.md#reset-an-existing-environment-preview) prostředí.

## <a name="assign-roles-and-permissions"></a>Přiřazení oprávnění a rolí

1. Přejděte na **Správce** > **Zabezpečení** > **Uživatelé**.

1. Volbou **Přidat uživatele** otevřete podokno **Přidat/upravit oprávnění**.

1. Pomocí pole **Vyhledávání** vyhledejte uživatele nebo skupinu Azure Active Directory, jejichž oprávnění chcete upravit. Vyberte **Roli**, kterou chcete přiřadit tomuto uživateli nebo skupině.

1. Zvolte **Uložit**. Aktuální prostředí bude automaticky sdíleno s uživatelem nebo členy skupiny, jejichž oprávnění jste změnili. Uživatelé mají přístup k aplikaci Customer Insights a vykonávají činnost dle své zadané role.

## <a name="view-current-permissions"></a>Zobrazit aktuální oprávnění

Přejděte na **Správce** > **Zabezpečení** > **Uživatelé**, abyste viděli, jaké přiřazení rolí jsou aktuálně aktivní.

- Sloupec **Typ** určuje jednoho uživatele, skupinu nebo aplikaci. Systém podporuje jednotlivé uživatele a skupiny.
- Role jsou určeny ve sloupci **Role**.
- Výběrem některého nadpisu sloupce seřadíte výsledky podle hodnoty daného sloupce.
- Pomocí **vyhledávacího** pole v horní části stránky vyhledejte konkrétní uživatele.


[!INCLUDE [footer-include](includes/footer-banner.md)]
