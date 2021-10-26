---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: ce2fdd435a81bb04148057554c5958e3ab59f125
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645118"
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
- Zdroje dat ze složky Common Data Model a Dataverse spravované v Data Lake. Tyto zdroje dat budete muset vytvořit ručně se stejným názvem jako ve zdrojovém prostředí.

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
