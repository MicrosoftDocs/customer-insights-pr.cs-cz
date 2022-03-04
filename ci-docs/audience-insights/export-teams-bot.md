---
title: Bot pro Microsoft Teams
description: Vyhledejte sjednocené profily zákazníků v Microsoft Teams pomocí bota.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232094"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams pro Dynamics 365 Customer Insights (Preview)

Připojte se k Microsoft Teams, aby mohl bot vyhledat sjednocené profily zákazníků v kanálech Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams zobrazující zákaznický záznam.](media/teams-bot.png "Bot Teams zobrazující zákaznický záznam")

## <a name="prerequisites"></a>Požadavky

Chcete-li nastavit a konfigurovat robota, musí být splněny následující předpoklady:

- Je alespoň jeden [zdroj dat přidán](data-sources.md).
- [Proces sjednocení](data-unification.md) je dopončen.
- Pole jsou přidána do [vyhledávacího a filtračního indexu](search-filter-index.md).
- Customer Insights a Teams jsou ve stejné organizaci.
- Vaše prostředí má primární cílovou skupinu nastavenou na jednotlivé zákazníky. Obchodní účty nejsou podporované.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]