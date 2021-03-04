---
title: Aktivity zákazníka
description: Definování aktivit zákazníků a jejich zobrazení na časové ose zákazníků.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267424"
---
# <a name="customer-activities"></a>Aktivity zákazníka

Zkombinujte aktivity zákazníků z [různých zdrojů dat](data-sources.md) v Dynamics 365 Customer Insights a vytvořte časovou osu zákazníků se seznamem aktivit v chronologickém pořadí. Časovou osu můžete zahrnout do aplikací pro zapojení zákazníků v Dynamics 365 prostřednictvím [doplňku karty zákazníka](customer-card-add-in.md) nebo v řídicím panelu Power BI.

## <a name="define-an-activity"></a>Definování aktivity

Vaše zdroje dat zahrnují entity s transakčními a aktivními daty z více zdrojů dat. Identifikujte tyto entity a vyberte aktivity, které chcete zobrazit na časové ose zákazníka. Vyberte entitu, která zahrnuje vaši cílovou aktivitu nebo aktivity.

1. V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.

1. Vyberte **Přidat aktivitu**.

   > [!NOTE]
   > Entita musí mít alespoň jeden atribut typu **Datum**, aby byla součástí na časové osy zákazníka a nelze přidávat entity bez pole **Datum**. Ovládací prvek **Přidat aktivitu** není povolen, pokud není taková entita nalezena.

1. V podokně **Přidat aktivitu** nastavte hodnoty pro následující pole:

   - **Entita**: Vyberte entitu, která obsahuje údaje o transakcích nebo aktivitách.
   - **Primární klíč**: Vyberte pole, které jedinečně identifikuje záznam. Nemělo by obsahovat žádné duplicitní hodnoty, prázdné hodnoty nebo chybějící hodnoty.
   - **Časové razítko**: Vyberte pole, které představuje čas zahájení vaší aktivity.
   - **Událost**: Vyberte pole, které je událostí pro aktivitu.
   - **Webová adresa**: Vyberte pole představující adresu URL s dalšími informacemi o této aktivitě. Například transakční systém, který tuto aktivitu využívá. Tato adresa URL může být libovolné pole zdroje dat, nebo může být vytvořeno jako nové pole pomocí transformace Power Query. Tato data URL budou uložena v entitě Sjednocená aktivita, která může být spotřebována jako navazující pomocí API.
   - **Podrobnosti**: Volitelně vyberte pole, které se přidá pro další podrobnosti.
   - **Ikona**: Volitelně vyberte ikonu představující tuto aktivitu.
   - **Typ aktivity**: Definujte odkaz na typ aktivity v Common Data Model, který nejlépe popisuje sémantickou definici aktivity.

1. V sekci **Nastavit vztah** nakonfigurujte podrobnosti tak, aby se údaje o vaší činnosti připojily k odpovídajícímu zákazníkovi.

    - **Pole entity aktivity**: Vyberte pole v entitě aktivity, které bude použito k navázání vztahu s jinou entitou.
    - **Entita zákazníka**: Vyberte odpovídající zdrojovou entitu zákazníka, se kterou bude vaše entita aktivity ve vztahu. Můžete se vztahovat pouze k těm zdrojovým zákaznickým entitám, které se používají v procesu sjednocení dat.
    - **Pole entity zákazníka**: Toto pole zobrazuje primární klíč zdrojové zákaznické entity vybraný v procesu mapování. Toto pole primárního klíče ve zdrojové entitě zákazníka se používá k navázání vztahu s entitou aktivity.
    - **Název**: Pokud již existuje vztah mezi touto entitou aktivity a vybranou zdrojovou entitou zákazníka, bude název vztahu v režimu jen pro čtení. Pokud takový vztah neexistuje, bude vytvořen nový vztah se zde uvedeným názvem.
   
   > [!div class="mx-imgBorder"]
   > ![Definování vztahů entit](media/activities-entities-define.png "Definování vztahů entit")

1. Výběrem možnosti **Uložit** se vaše změny uplatní.

1. Na stránce **Aktivity** vyberte možnost **Spustit**.

> [!TIP]
> Existuje [šest typů stavů](system.md#status-types) pro úkoly/procesy. Navíc většina procesů [závisí na dalších navazujících procesech](system.md#refresh-policies). Můžete vybrat stav procesu a zobrazit podrobnosti o průběhu celé úlohy. Po výběru **Zobrazit podrobnosti** pro jeden z úkolů úlohy najdete další informace: čas zpracování, datum posledního zpracování a všechny chyby a varování spojené s úkolem.

## <a name="edit-an-activity"></a>Úprava aktivity

1. V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.

2. Vyberte entitu aktivity, kterou chcete upravit, a vyberte **Upravit**. Nebo se můžete pohybovat nad řádkem entity a vybrat ikonu **Upravit**.

3. Klikněte na ikonu **Upravit**.

4. V podokně **Upravit aktivitu** aktualizujte hodnoty a vyberte **Uložit**.

5. Na stránce **Aktivity** vyberte možnost **Spustit**.

## <a name="delete-an-activity"></a>Odstranění aktivity

1. V přehledech cílové skupiny přejděte na **Data** > **Aktivity**.

2. Vyberte entitu aktivity, kterou chcete odebrat, a vyberte **Odstranit**. Nebo se můžete pohybovat nad řádkem entity a vybrat ikonu **Odstranit**. Kromě toho můžete vybrat více entit aktivity, které chcete odstranit najednou.
   > [!div class="mx-imgBorder"]
   > ![Upravit nebo odstranit vztahy mezi entitami](media/activities-entities-edit-delete.png "Upravit nebo odstranit vztahy mezi entitami")

3. Vybrání ikony **Odstranit**.

4. Odstranění potvrďte.


[!INCLUDE[footer-include](../includes/footer-banner.md)]