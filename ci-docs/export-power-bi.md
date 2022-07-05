---
title: Konektor Power BI (preview)
description: Zjistěte, jak používat konektor Dynamics 365 Customer Insights v Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051261"
---
# <a name="power-bi-connector-preview"></a>Konektor Power BI (preview)

Vytvářejte vizualizace pro svá data pomocí Microsoft Power BI Desktop. Vytvářejte další informace a vytvářejte přehledy s vašimi sjednocenými údaji o zákaznících.

## <a name="prerequisites"></a>Požadavky

- Máte sjednocené profily zákazníků.
- Nejnovější verze [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je instalován v počítači. [Další informace o aplikaci Power BI Desktop](/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Konfigurace konektorupro Power BI

1. V Power BI Desktop vyberte **Soubor** > **Získat data**.

1. Vyberte **Zobrazit více** vyhledejte **Dynamics 365 Customer Insights**

1. Vyberte **Připojit**.

1. **Přihláste se** se stejným účtem organizace, který používáte pro Customer Insights a vyberte **Připojit**.
   > [!NOTE]
   > Účet, který uvedete v tomto kroku, se používá k načtení dat ze služby Customer Insights a nemusí být totožný s tím, kterým jste přihlášeni k Power BI. Chcete-li obnovit účet, který se používá k načítání dat, otevřete Power BI a jděte na **Soubor** > **Možnosti** > **Nastavení** > **Nastavení zdroje dat**. V seznamu zdrojů dat vyberte **Přihlášení k Dynamics 365 Customer Insights** a vyberte **Vymazat oprávnění**.  

1. V dialogovém okně **Navigátor**. se zobrazí seznam všech prostředí, do kterých máte přístup. Rozbalte prostředí a otevřete libovolnou složku (entity, míry, segmenty, rozšíření). Například otevřete složky **Entity**, abyste viděli všechny entity, které můžete importovat.

   ![Navigátor konektoru Power BI.](media/power-bi-navigator.png "Navigátor konektoru Power BI")

1. Zaškrtněte políčka vedle entit, které chcete zahrnout, a **Načíst**. Můžete vybrat více entit z více prostředí.

1. Během načítání entit se zobrazí dialogové okno načítání. Jakmile se načtou všechny vaše vybrané entity, můžete použít funkce Power BI pro vizualizaci dat.

## <a name="large-data-sets"></a>Velké datové sady

Konektor Customer Insights pro Power BI je navržen pro práci s datovými sadami, které obsahují až 1 milion profilů zákazníků. Import větších souborů dat může fungovat, ale trvá to dlouho. Proces by navíc mohl běžet do časového limitu z důvodu omezení Power BI. Další informace viz [Power BI: Doporučení pro velké soubory dat](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Práce s podmnožinou dat

Zvažte práci s podmnožinou vašich dat. Můžete například vytvořit [segmenty](segments.md) místo exportování všech záznamů zákazníka do Power BI.

## <a name="troubleshooting"></a>Řešení problému

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Prostředí Customer Insights se nezobrazuje v Power BI

Prostředí, která mají více než jeden [vztah](relationships.md) definovaný mezi dvěma identickými entitami v Customer Insights nebudou dostupné v konektoru Power BI.

Duplikované vztahy můžete identifikovat a odstranit.

1. Přejděte na **Data** > **Vztahy** na prostředí, které vám chybí v Power BI.
2. Identifikujte duplicitní vztahy:
   - Zkontrolujte, zda je mezi stejnými dvěma entitami definován více než jeden vztah.
   - Zkontrolujte, zda existuje vztah vytvořený mezi dvěma entitami, které jsou obě zahrnuty do procesu sjednocení. Mezi všemi entitami zahrnutými do procesu sjednocení je definován implicitní vztah.
3. Odstraňte veškeré identifikované duplicitní vztahy.

Po odstranění duplicitních vztahů zkuste znovu nakonfigurovat konektor Power BI. Prostředí by mělo být ihned k dispozici.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Chyby v polích data při načítání entit do Power BI Desktop

Při načítání entit, které obsahují pole s formátem data, jako je MM/DD/RRRR, můžete narazit na chyby v důsledku neshodných formátů národního prostředí. Tento nesoulad nastane, když váš soubor Power BI Desktop je nastaven na jiné národní prostředí než angličtina (Spojené státy americké), protože pole data v Customer Insights jsou uložena ve formátu USA.

Soubor Power BI Desktop má jediné nastavení národního prostředí, které se použije při načítání dat. Aby byla tato pole dat interpretována správně, nastavte národní prostředí souboru .BPI na angličtinu (Spojené státy). [Zjistěte, jak změnit národní prostředí souboru plochy Power BI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
