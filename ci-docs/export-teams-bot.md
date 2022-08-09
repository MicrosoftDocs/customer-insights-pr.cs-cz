---
title: Bot Teams pro Dynamics 365 Customer Insights (Preview)
description: Vyhledejte sjednocené profily zákazníků v Microsoft Teams pomocí bota.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195834"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams pro Dynamics 365 Customer Insights (Preview)

Připojte se k Microsoft Teams, aby mohl bot vyhledat sjednocené profily zákazníků v kanálech Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams zobrazující zákaznický záznam":::

## <a name="prerequisites"></a>Předpoklady

- Je přidán alespoň jeden [zdroj dat](data-sources.md).
- [Proces sjednocení](data-unification.md) je dopončen.
- Pole jsou přidána do [indexu vyhledávání a filtrování](search-filter-index.md).
- Customer Insights a Teams jsou ve stejné organizaci.
- Vaše prostředí má primární cílovou skupinu nastavenou na jednotlivé zákazníky. Obchodní účty nejsou podporované.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Nakonfigurujte bota

1. Přejděte na **Správce** > **Propojení**.
1. Na dlaždici Microsoft Teams vyberte **Založit**.
1. Jste přesměrováni na oblast **Aplikace** v Teams. Můžete také otevřít Teams a vybrat **Aplikace** v levém dolním rohu nebo [je získat z AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) přímo.
1. Vyhledejte **Customer Insights** a vyberte aplikaci.
1. Vyberte **Přidat**.
1. Přihlaste se do Customer Insights v Teams. Zobrazí se uvítací zpráva.

## <a name="things-you-can-do-with-the-bot"></a>Věci, které lze dělat s botem

Bot poskytuje možnosti vyhledávání pro jednotné profily zákazníků.

- Zadejte **vyhledávání** následované názvem, e-mailovou adresou nebo jiným polem ve sjednoceném profilu zákazníka, který je přidán do indexu vyhledávání a filtru.

  Z výsledného zákaznického profilu získáte kartu s až 15 poli. Více shod vrátí seznam výsledků, kde si můžete vybrat profil. Chcete-li vyhledat přesnou shodu, přidejte hledaný termín ve dvojitých uvozovkách.

- Pokud vaše organizace používá více prostředí Customer Insights ve stejné organizaci, můžete zadat **switchinstance**, čímž zvolíte, ke kterému prostředí chcete bota připojit.

- Zadejte **pomoc** a zobrazíte seznam dostupných příkazů pro robota.  

[!INCLUDE [footer-include](includes/footer-banner.md)]