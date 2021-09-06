---
title: Tvorba a správa prostředí
description: Zjistěte, jak se zaregistrovat do služby a jak spravovat prostředí.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034169"
---
# <a name="manage-environments"></a>Správa prostředí

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Přepnutí prostředí

Vyberte ovládaí prvek **Prostředí** v pravém horním rohu stránky pro změnu prostředí.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Snímek obrazovky ovládacího prvku pro přepínání prostředí.":::

Správci mohou [vytvářet](get-started-paid.md) a spravovat prostředí.

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Můžete upravit některé podrobnosti existujících prostředí.

1.  Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

2.  Vyberte ikonu **Upravit**.

3. V poli **Upravit prostředí** můžete změnit **zobrazovaný název** prostředí, ale nemůžete změnit **Oblast** nebo **Typ**.

4. Pokud je prostředí nakonfigurováno pro ukládání dat Azure Data Lake Storage, můžete aktualizovat **Klíč účtu**. Nemůžete však změnit **Název účtu** nebo název **Kontejneru**.

5. Volitelně můžete provést aktualizaci z připojení na základě klíče účtu do připojení založeného na prostředcích nebo předplatném. Po upgradu nelze vrátit klíč účtu. Další informace viz [Připojení přehledů cílové skupiny k účtu Azure Data Lake Storage Gen 2 pomocí instančního objektu Azure](connect-service-principal.md). Nemůžete změnit informace o **kontejneru** při aktualizaci připojení.

6. Volitelně můžete poskytnout adresu URL prostředí Microsoft Dataverse v části **Konfigurace sdílení dat pomocí Microsoft Dataverse a povolení dalších funkcí**. Tyto funkce zahrnují sdílení dat s aplikacemi a řešeními založenými na Microsoft Dataverse, příjem dat z místních datových zdrojů nebo použití [predikcí](predictions.md). Vyberte **Povolit sdílení dat**, abyste sdíleli výstupní data Customer Insights se službou Data Lake spravovanou Microsoft Dataverse.

   > [!NOTE]
   > - Sdílení dat se službou Data Lake spravovanou Microsoft Dataverse aktuálně není podporováno, když uložíte všechna data do svého vlastního úložiště Azure Data Lake Storage.
   > - [Predikce chybějících hodnot v entitě](predictions.md) a vestavěné sestavy PowerBI v přehledech cílové skupiny (pokud jsou povoleny ve vašem prostředí) v současné době nejsou podporovány, když povolíte sdílení dat se spravovaným datovým jezerem Microsoft Dataverse.

   Až povolíte sdílení dat s Microsoft Dataverse, spustí se jednorázová úplná aktualizace vašich zdrojů dat a dalších procesů. Pokud procesy aktuálně běží, neuvidíte možnost povolit sdílení dat s Microsoft Dataverse. Chcete-li povolit sdílení dat, počkejte, až se tyto procesy dokončí, nebo je zrušte. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Možnosti konfigurace umožňující sdílení dat s Microsoft Dataverse.":::
   
   Když spustíte procesy, jako je ingestace dat nebo vytvoření segmentu, vytvoří se odpovídající složky v účtu úložiště, který jste zadali výše. Datové soubory a soubory model.json budou vytvořeny a přidány do příslušných podsložek v závislosti na spuštěném procesu.

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
