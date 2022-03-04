---
title: Limity služeb v Dynamics 365 Customer Insights
description: Pochopte limity a omezení.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350399"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limity služeb ve funkcích aplikace Customer Insights

Tento článek popisuje vestavěné limity služby Customer Insights, které jsou navrženy tak, aby zajistily spolehlivost a stabilitu služby. Jakékoli žádosti o změny lze podat prostřednictvím [Fórum nápadů](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Přehledy pro cílovou skupinu

| Plocha  | Limity  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenty, míry a predikce | 300  | Celkový počet [segmentů](audience-insights/segments.md), [měr](audience-insights/measures.md) a [predíkcí](audience-insights/predictions.md) dohromady nesmí přesáhnout 300.  |
| Relace | 20 úrovní hloubky vztahů v cestách entit. | Při vytváření [segmentů](audience-insights/segments.md) nebo [měření](audience-insights/measures.md) pomocí rozhraní Builderu mohou mít cesty entit až 20 skokových relací mezi počáteční entitou a cílovou entitou.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
