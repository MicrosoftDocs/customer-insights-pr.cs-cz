---
title: Export dat ze služby Customer Insights
description: Spravujte exporty ke sdílení dat.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896135"
---
# <a name="exports-preview-overview"></a>Přehled exportů (Preview)

Stránka **Export** zobrazuje všechny nakonfigurované exporty. Exporty sdílejí konkrétní data s různými aplikacemi. Mohou zahrnovat zákaznické profily nebo entity, schémata a podrobnosti mapování. Každý export vyžaduje [připojení, které nastavil správce, ke správě ověřování a přístupu](connections.md).

> [!NOTE]
> Do března 2021 exporty vytvářely propojení k odpovídající službě automaticky. Export nyní vyžaduje [propojení, vytvořené a sdílené správcem](connections.md), než je budete moci vytvořit.

Jděte na **Data** > **Exporty** pro zobrazení stránky exportů. Všechny uživatelské role mají přístup k zobrazení nakonfigurovaných exportů. Pomocí vyhledávacího pole na panelu příkazů můžete najít exporty podle jejich názvu, názvu připojení nebo typu připojení.

## <a name="set-up-a-new-export"></a>Nastavení nového exportu

Chcete-li nastavit nebo upravit export, musíte mít k dispozici propojení. Propojení závisí na vaší [roli uživatele](permissions.md):
- Správci mají přístup ke všem propojením. Mohou také vytvářet nová propojení při nastavování exportu.
- Přispěvatelé mohou mít přístup ke konkrétním propojením. Závisí na správcích, kteří konfigurují a sdílejí propojení. Další informace viz [Umožnění přispěvatelům použít připojení pro export](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Diváci mohou prohlížet pouze existující exporty, ale nemohou je vytvářet.

1. Přejděte na **Data** > **Exporty**.

1. Pokud chcete vytvořit nový cíl exportu, vyberte **Přidat export**.

1. V podokně **Nastavit export** vyberte, které propojení chcete použít. [Propojení](connections.md) jsou spravována správci. 

1. Zadejte požadované podrobnosti a výběrem **Uložit** vytvořte export.

### <a name="edit-an-export"></a>Úprava exportu

1. Vyberte vertikální tři tečky pro cíl exportu, který chcete upravit.

1. V rozevírací nabídce vyberte možnost **Upravit**.

1. Změňte hodnoty, které chcete aktualizovat, a vyberte **Uložit**.

## <a name="view-exports-and-export-details"></a>Zobrazení exportů a podrobností exportu

Po vytvoření jsou cíle exportu uvedeny v části **Data** > **Exporty**. Všichni uživatelé mohou vidět, která data jsou sdílena, a jejich nejnovější stav.

1. Přejděte na **Data** > **Exporty**.

1. Uživatelé bez oprávnění k úpravám mohou vybrat **Zobrazit** místo **Upravit** k zobrazení podrobností o exportu.

1. Toto boční podokno zobrazuje nastavení tohoto exportu. Bez oprávnění k úpravám nemůžete hodnoty měnit. Vyberte **Zavřít** pro návrat na stránku exportu.

## <a name="run-exports-on-demand"></a>Spuštění exportů na vyžádání

Po konfiguraci exportu bude spuštěn s každým [plánovaným obnovením](system.md#schedule-tab), pokud má funkční připojení.

Chcete-li exportovat data bez čekání na plánované obnovení, přejděte na **Data** > **Exporty**. K dispozici jsou dvě možnosti:

- Chcete-li spustit všechny exporty, vyberte **Spustit vše** na panelu příkazů. 
- Chcete-li spustit jeden export, vyberte tři tečky (...) u položky seznamu a poté vyberte **Spustit**.

## <a name="remove-an-export"></a>Odebrání exportu

1. Přejděte na **Data** > **Exporty**.

1. Vyberte vertikální tři tečky pro export, který chcete odebrat.

1. V rozevírací nabídce vyberte možnost **Odebrat**.

1. Potvrďte odebrání výběrem **Odstranit** na potvrzovací obrazovce.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
