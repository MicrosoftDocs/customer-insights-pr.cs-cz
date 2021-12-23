---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 309b2a900e50727ffa655fc6b5fe728ea55ba5bf
ms.sourcegitcommit: 626d485dae1e001e63e4d4bf78f6770766822ba0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/06/2021
ms.locfileid: "7892376"
---
# <a name="manage-environments"></a>Správa prostředí

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Přepnutí prostředí

Vyberte ovládaí prvek **Prostředí** v pravém horním rohu stránky pro změnu prostředí.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímek obrazovky ovládacího prvku pro přepínání prostředí.":::

Správci mohou [vytvářet](create-environment.md) a spravovat prostředí.

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Můžete upravit některé podrobnosti existujících prostředí.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte ikonu **Upravit**.

3. V poli **Upravit prostředí** můžete aktualizovat nastavení prostředí.

Další informace o nastavení prostředí naleznete v tématu [Vytvoření nového prostředí](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Připojení k Microsoft Dataverseu
   
Krok **Microsoft Dataverse** vám umožní propojit Customer Insights s vaším prostředím Dataverse.

Pokud chcete použít [připravené modely predikce](predictions-overview.md#out-of-box-models), nakonfigurujte sdílení dat pomocí Dataverse. Nebo můžete povolit příjem dat z místních zdrojů dat a poskytnout adresu URL prostředí Microsoft Dataverse, které spravuje vaše organizace. Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights s datovým jezerem spravovaným Dataverse.

> [!IMPORTANT]
> Customer Insights a Dataverse musí být ve stejné oblasti, aby bylo možné sdílet data.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights nepodporuje následující scénáře sdílení dat:
> - Pokud uložíte všechna data do vlastního úložiště Azure Data Lake Storage, nebudete moci povolit sdílení dat pomocí datového jezera spravovaného Dataverse.
> - Pokud povolíte sdílení dat pomocí Dataverse, nebudete moci [vytvořit předpokládané nebo chybějící hodnoty v entitě](predictions.md).

## <a name="copy-the-environment-configuration"></a>Zkopírujte konfiguraci prostředí

Když vytváříte nové prostředí, můžete se rozhodnout zkopírovat konfiguraci z existujícího prostředí. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Snímek obrazovky s možnostmi nastavení v nastavení prostředí.":::

Uvidíte seznam všech dostupných prostředí z vaší organizace, ze kterých můžete kopírovat data.

Následující nastavení konfigurace se zkopírují:

- Ingestované/importované zdroje dat
- Konfigurace sjednocení dat (mapa, shoda, sloučení)
- Segmenty
- Míry
- Vztahy
- Aktivity
- Index hledání a filtrování
- Cíle exportu
- Plánovaná aktualizace
- Rozšíření
- Správa modelů
- Přiřazení rolí

Následující data *nejsou* zkopírována:

- Profily zákazníků.
- Přihlašovací údaje ke zdroji dat. Budete muset zadat přihlašovací údaje pro každý zdroj dat a ručně aktualizovat zdroje dat.

- Zdroje dat ze složky Common Data Model a datového jezera spravovaného Dataverse. Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.

Při kopírování prostředí se zobrazí potvrzovací zpráva o vytvoření nového prostředí. Volbou **Přejít na zdroje dat** zobrazíte seznam zdrojů dat.

Všechny zdroje dat zobrazí stav **Povinné přihlašovací údaje**. Upravte zdroje dat a zadejte přihlašovací údaje a aktualizujte je.

:::image type="content" source="media/data-sources-copied.png" alt-text="Seznam zdrojů dat, které byly zkopírovány a vyžadují ověření.":::

Po aktualizaci zdrojů dat přejděte na **Data** > **Sjednotit**. Zde najdete nastavení ze zdrojového prostředí. Upravte je podle potřeby nebo volbou **Spustit** zahajte proces sjednocení dat a vytvořte jednotnou entitu zákazníka.

Po dokončení sjednocení dat přejděte na **Míry** a **Segmenty**, které také potřebují aktualizovat.

## <a name="reset-an-existing-environment"></a>Obnovení existujícího prostředí

Pokud jste správce a chcete odstranit všechny konfigurace a odebrat ingegstovaná data, můžete obnovit prostředí do prázdného stavu.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace. 

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Obnovit**. 

4.  Chcete-li potvrdit odstranění, zadejte název prostředí a vyberte **Obnovit**.

## <a name="delete-an-existing-environment"></a>Odstranění existujícího prostředí

Jako správce můžete odstranit prostředí, které spravujete.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte prostředí, které chcete obnovit, a vyberte tři tečky (**...**). 

3. Vyberte volbu **Odstranit**. 

4.  Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
