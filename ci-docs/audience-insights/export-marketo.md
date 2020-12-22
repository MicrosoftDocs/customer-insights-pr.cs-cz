---
title: Export dat Customer Insights do služby Marketo
description: Naučte se, jak nakonfigurovat připojení ke službě Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570395"
---
# <a name="connector-for-marketo-preview"></a>Konektor pro službu Marketo (Preview)

Exportem segmentů sjednocených profilů zákazníků můžete generovat kampaně, poskytovat e-mailový marketing a využívat konkrétní skupiny zákazníků pomocí služby Marketo.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Marketo](https://login.marketo.com/) a odpovídající přihlašovací údaje správce.
-   Služba Marketo obsahuje stávající seznamy a odpovídající ID. Další informace naleznete v [seznamech Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Máte [konfigurované segmenty](segments.md).
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="connect-to-marketo"></a>Připojení ke službě Marketo

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **Marketo** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Zadejte své **[ID klienta Marketo, tajný klíč klienta a název hostitele koncového bodu REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Zadejte své **[ID seznamu Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Volbou **Souhlasím** potvrdíte **Ochranu osobních údajů a dodržování předpisů** a volbou **Připojit** inicializujete připojení ke službě Marketo.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Screenshot exportu pro připojení ke službě Marketo":::

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **Křestní jméno**, **Příjmení**, **Město**, **Stát** a **Oblast/zemi** jako další pole k vytvoření lépe přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. Do služby Marketo můžete exportovat celkem až 1 milion zákaznických profilů.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Výběr polí a segmentů pro export do služby Marketo":::

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab). Ve službě Marketo nyní najdete své segmenty v části [Seznamy Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby Marketo.
- Export do služby Marketo je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může trvat až 3 hodiny. 
- Počet profilů, které můžete exportovat do služby Marketo, závisí a je omezen na vaší smlouvě se službou Marketo.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Marketo, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že společnost Marketo splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.
