---
title: Bot pro Microsoft Teams
description: Vyhledejte sjednocené profily zákazníků v Microsoft Teams pomocí bota.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405384"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams pro Dynamics 365 Customer Insights (Preview)

Připojte se k Microsoft Teams, aby mohl bot vyhledat sjednocené profily zákazníků v kanálech Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams zobrazující zákaznický záznam](media/teams-bot.png "Bot Teams zobrazující zákaznický záznam")

## <a name="prerequisites"></a>Požadavky

Chcete-li nastavit a konfigurovat robota, musí být splněny následující předpoklady:

- Je alespoň jeden [zdroj dat přidán](data-sources.md).
- [Proces sjednocení](data-unification.md) je dopončen.
- Pole jsou přidána do [vyhledávacího a filtračního indexu](search-filter-index.md).
- Customer Insights a Teams jsou ve stejné organizaci.

## <a name="configure-the-bot"></a>Nakonfigurujte bota

1. V přehledech cílové skupiny přejděte na **Správa** > **Cíle exportu**.
1. Na dlaždici Microsoft Teams vyberte **Založit**.
1. Jste přesměrováni na oblast **Aplikace** v Teams. Můžete také otevřít Teams a vybrat **Aplikace** v levém dolním rohu nebo [je získat z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) přímo.
1. Vyhledejte **Customer Insights** a vyberte aplikaci.
1. Vyberte **Přidat**.
1. Po přihlášení k Customer Insights v Teams se zobrazí uvítací zpráva a můžete začít.

## <a name="things-you-can-do-with-the-bot"></a>Věci, které lze dělat s botem

Bot poskytuje možnosti vyhledávání pro jednotné profily zákazníků.

- Zadejte **vyhledávání** následované názvem, e-mailovou adresou nebo jiným polem ve sjednoceném profilu zákazníka, který je přidán do indexu vyhledávání a filtru.

  Z výsledného zákaznického profilu získáte kartu s až 15 poli. Více shod vrátí seznam výsledků, kde si můžete vybrat profil. Můžete přidat hledaný termín ve dvojitých uvozovkách a vyhledat přesnou shodu.

- Pokud vaše organizace používá více prostředí Customer Insights ve stejné organizaci, můžete zadat **switchinstance**, čímž zvolíte, ke kterému prostředí chcete bota připojit.

- Zadejte **pomoc** a zobrazíte seznam dostupných příkazů pro robota.  
