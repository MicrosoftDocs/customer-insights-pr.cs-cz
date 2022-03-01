---
title: Konektor pro Power BI
description: Zjistěte, jak používat konektor Dynamics 365 Customer Insights v Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405356"
---
# <a name="connector-for-power-bi-preview"></a>Konektor pro Power BI (preview)

Vytvářejte vizualizace svých dat pomocí Power BI Desktop. Vytvářejte další informace a vytvářejte přehledy s vašimi sjednocenými údaji o zákaznících.

## <a name="prerequisites"></a>Požadavky

- Máte sjednocené profily zákazníků.
- Nejnovější verze [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) je v počítači nainstalována. [Další informace o aplikaci Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop)

## <a name="configure-the-connector-for-power-bi"></a>Konfigurace konektorupro Power BI

1. V Power BI Desktop vyberte **Soubor** > **Získat data**.

1. Vyberte **Zobrazit více** vyhledejte **Dynamics 365 Customer Insights**

1. Vyberte výsledek a vyberte **Připojit**.

1. **Přihláste se** se stejným účtem organizace, který používáte pro Customer Insights a vyberte **Připojit**.
   > [!NOTE]
   > Účet, který uvedete v tomto kroku, se používá k načtení dat ze služby Customer Insights a nemusí být totožný s tím, kterým jste přihlášeni k Power BI. Chcete-li obnovit účet, který se používá k načítání dat, otevřete Power BI a jděte na **Soubor** > **Možnosti** > **Nastavení** > **Nastavení zdroje dat**. V seznamu zdrojů dat vyberte **Přihlášení k Dynamics 365 Customer Insights** a vyberte **Vymazat oprávnění**.  

1. V dialogovém okně **Navigátor**. se zobrazí seznam všech prostředí, do kterých máte přístup. Rozbalte prostředí a otevřete libovolnou složku (entity, míry, segmenty, rozšíření). Například otevřete složky **Entity**, abyste viděli všechny entity, které můžete importovat.

   ![Navigátor konektoru Power BI](media/power-bi-navigator.png "Navigátor konektoru Power BI")

1. Zaškrtněte políčka vedle entit, které chcete zahrnout, a **Načíst**. Můžete vybrat více entit z více prostředí.

1. Během načítání entit se zobrazí dialogové okno načítání. Jakmile se načtou všechny vaše vybrané entity, můžete použít funkce Power BI pro vizualizaci dat.

## <a name="large-data-sets"></a>Velké datové sady

Konektor Customer Insights pro Power BI je navržen pro práci s datovými sadami, které obsahují až 1 milion profilů zákazníků. Import větších souborů dat může fungovat, ale trvá to dlouho. Proces by navíc mohl běžet do časového limitu z důvodu omezení Power BI. Další informace viz [Power BI: Doporučení pro velké soubory dat](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Práce s podmnožinou dat

Zvažte práci s podmnožinou vašich dat. Můžete například vytvořit [segmenty](segments.md) místo exportování všech záznamů zákazníka do Power BI.
