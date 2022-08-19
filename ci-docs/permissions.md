---
title: Přiřadit uživatelská oprávnění
description: Informace o oprávněních a rolích uživatele.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245411"
---
# <a name="assign-user-permissions"></a>Přiřadit uživatelská oprávnění

Přístup k Customer Insights je omezen na uživatele ve vaší organizaci, kteří jsou do aplikace přidáni správcem. Správce může uživatele přidávat, upravovat nebo odebírat. Uživatelem může být jeden uživatel, skupina nebo aplikace. Uživatel může mít tři typy rolí:

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
- Dokončete **Sjednocení dat**, jehož výsledkem je entita sjednoceného profilu zákazníka.
- Definice **Vztahů** a **Aktivit**.
- Vytváření segmentů pomocí stránky **Segmenty**.
- Vytvořte opatření na stránce **Opatření**.
- Správa konfigurace a rozšíření zákaznických profilů ze stránky **Rozšíření** (pouze pro rozšíření první strany).
- Spravujte a vytvářejte exporty na základě [propojení sdílených s přispěvateli](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Správa

- Všechna oprávnění, která má k dispozici Přispěvatel.
- Změna nastavení na stránce **Systém**, včetně pracovního jazyka a plánů aktualizace systémových procesů a exportování diagnostických protokolů.
- Změňte nastavení na stránce **Zabezpečení**, včetně uživatelů, klíčů API, soukromých odkazů a trezoru klíčů.
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

## <a name="add-users"></a>Přidat uživatele

1. Jděte na **Správa** > **Zabezpečení** a vyberte kartu **Uživatelé**.

1. Volbou **Přidat uživatele** otevřete podokno **Přidat/upravit oprávnění**.

1. Pomocí pole **Vyhledávání** vyhledejte uživatele nebo skupinu Azure Active Directory, jejichž oprávnění chcete přidat. Vyberte **Roli**, kterou chcete přiřadit tomuto uživateli nebo skupině.

1. Vyberte **Uložit**. Aktuální prostředí bude automaticky sdíleno s uživatelem nebo členy skupiny. Uživatelé mají přístup k aplikaci Customer Insights a vykonávají činnost dle své zadané role.

## <a name="view-current-permissions"></a>Zobrazit aktuální oprávnění

Jděte na **Správa** > **Zabezpečení** a vyberte **Uživatelé**, aby se zobrazil seznam aktivních uživatelů a jejich přiřazení rolí. Seznam uživatelů můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít konkrétního uživatele.

## <a name="manage-current-users"></a>Správa aktuálních uživatelů

Jděte na **Správa** > **Zabezpečení** a vyberte kartu **Uživatelé**. Seznam uživatelů můžete seřadit podle libovolného sloupce nebo pomocí vyhledávacího pole najít uživatele, kterého chcete spravovat.

Vyberte uživatele pro zobrazení dostupných akcí.

- **Upravit** k úpravě role uživatele v Customer Insights. Potvrďte změnu výběrem možnosti **Uložit**.
- **Odstranit** k odebrání uživateli přístupu do Customer Insights. Vyberte **Odstranit** pro potvrzení odstranění.

[!INCLUDE [footer-include](includes/footer-banner.md)]
