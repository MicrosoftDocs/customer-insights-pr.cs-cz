---
title: Export dat Customer Insights do služby Mailchimp
description: Naučte se, jak nakonfigurovat připojení ke službě Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598193"
---
# <a name="connector-for-mailchimp-preview"></a>Konektor pro službu Mailchimp (Preview)

Exportujte segmenty sjednocených profilů zákazníků do služby Mailchimp a vytvářejte bulletiny a e-mailové kampaně.

## <a name="prerequisites"></a>Požadavky

-   Máte [účet Mailchimp](https://mailchimp.com/) a odpovídající přihlašovací údaje správce.
-   Služba Mailchimp obsahuje cílové skupiny a odpovídající ID. Další informace viz [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).
-   Máte [konfigurované segmenty](segments.md)
-   Sjednocené profily zákazníků v exportovaných segmentech obsahují pole představující e-mailovou adresu.

## <a name="connect-to-mailchimp"></a>Připojit k Mailchimpu

1. Přejděte na **Správce** > **Cíle exportu**.

1. Pod **Mailchimp** vyberte **Nastavení**.

1. Zadejte rozpoznatelný název cíle exportu do pole **Zobrazovaný název**.

1. Vyberte **Souhlasím** pro potvrzení **Ochrany osobních údajů a dodržování předpisů**.

1. Zadejte své **[ID cílové skupiny Mailchimp](https://mailchimp.com/help/find-audience-id/)** a volbou **Připojit** inicializujte připojení ke službě Mailchimp.

1. Vyberte **Ověření pomocí Mailchimp** a zadejte své přihlašovací údaje ke službě Mailchimp.

1. Vyberte **Přidat sebe jako exportujícího uživatele** a zadejte přihlašovací údaje k Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Screenshot exportu pro připojení ke službě Mailchimp":::

1. Vyberte **Další** pro konfiguraci exportu.

## <a name="configure-the-connector"></a>Konfigurace konektoru

1. V sekci **Párování dat** poli **E-mail** vyberte pole ve sjednoceném profilu zákazníka, které představuje e-mailovou adresu zákazníka. 

1. Volitelně můžete exportovat **Křestní jméno** a **Příjmení** jako další pole k vytvoření lépe přizpůsobených e-mailů. Volbou **Přidat atribut** namapujte tato pole.

1. Vyberte segmenty, které chcete exportovat. Do služby Mailchimp můžete exportovat celkem až 1 milion zákaznických profilů.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Výběr polí a segmentů pro export do služby Mailchimp":::

1. Zvolte **Uložit**.

## <a name="export-the-data"></a>Export dat

Můžete [exportovat data na vyžádání](export-destinations.md). Export bude spuštěn také s každou [plánovanou aktualizací](system.md#schedule-tab). Ve službě Mailchimp nyní najdete své segmenty v části [Cílové skupiny Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Známá omezení

- Až 1 milion profilů na jeden export do služby Mailchimp.
- Export do služby Mailchimp je omezen na segmenty.
- Export segmentů s celkem 1 milionem profilů může z důvodu omezení na straně poskytovatele trvat až tři hodiny. 
- Počet profilů, které můžete exportovat do služby Mailchimp, závisí a je omezen na vaší smlouvě se službou Mailchimp.

## <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když povolíte Dynamics 365 Customer Insights přenos dat do služby Mailchimp, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že služba Mailchimp splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).
Tuto funkci cíle exportu může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.


[!INCLUDE[footer-include](../includes/footer-banner.md)]