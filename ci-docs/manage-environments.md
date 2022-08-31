---
title: Správa prostředí
description: Naučte se, jak spravovat stávající prostředí Customer Insights jako správce."
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304272"
---
# <a name="manage-environments"></a>Správa prostředí

Správci [vytváří](create-environment.md) a spravují prostředí. Mohou změnit některá nastavení ve stávajících prostředích. Firma, typ, region, možnost úložiště a nastavení Dataverse jsou po vytvoření prostředí neměnné. Pokud chcete tato nastavení změnit, [resetujte prostředí](#reset-an-existing-environment-preview) nebo [vytvořte nové prostředí](create-environment.md).

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Upravte podrobnosti existujícího prostředí, jako je název nebo nastavení výchozího prostředí.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte ikonu **Upravit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona pro úpravu nastavení prostředí.":::

1. V podokně **Úprava prostředí** můžete aktualizovat nastavení prostředí.

1. Vyberte **Zkontrolovat a dokončit** a pak příkazem **Aktualizovat** aplikujte změny.

## <a name="change-the-owner-of-an-environment"></a>Změna vlastníka prostředí

Několik uživatelů může mít oprávnění správce, vlastníkem prostředí je ale pouze jeden uživatel. Ve výchozím nastavení je to správce, kdo na samém začátku vytváří prostředí. Jako správce prostředí můžete přiřadit vlastnictví jinému uživateli s oprávněním správce.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte ikonu **Upravit**.

1. V podokně **Úprava prostředí** přejděte na krok **Základní informace**.

1. V poli **Změnit vlastníka prostředí** vyberte nového vlastníka prostředí.  

1. Vyberte **Zkontrolovat a dokončit** a pak příkazem **Aktualizovat** aplikujte změny.

## <a name="claim-ownership-of-an-environment"></a>Deklarace vlastnictví prostředí

Pokud je uživatelský účet vlastníka odstraněn nebo pozastaven, prostředí nebude mít vlastníka. Jakýkoli uživatel s rolí správce si může nárokovat vlastnictví a stát se novým vlastníkem. Vlastnící správce může nadále vlastnit prostředí nebo [změnit vlastnictví na jiného správce](#change-the-owner-of-an-environment).

Chcete-li nárokovat vlastnictví, vyberte tlačítko **Převzít vlastnictví**, které se zobrazí v horní části každé stránky v Customer Insights, když původní vlastník opustil organizaci.

## <a name="reset-an-existing-environment-preview"></a>Obnovení stávajícího prostředí (Preview)

Jako vlastník prostředí obnovte prostředí do prázdného stavu, pokud chcete odstranit všechny konfigurace a odebrat ingestovaná data.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte prostředí, které chcete resetovat, a vyberte vertikální tři tečky (&vellip;).

1. Vyberte položku **Obnovit (Preview)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola resetování prostředí.":::

1. Vyberte, zda chcete resetovat celé prostředí, vše kromě zdrojů dat nebo vše, co je nakonfigurováno nad jednotným profilem zákazníka.

1. Pro potvrzení zadejte název prostředí a vyberte **Resetovat**.

## <a name="delete-an-existing-environment"></a>Odstranění existujícího prostředí

Jako vlastník prostředí jej můžete odstranit.

> [!IMPORTANT]
> Odstraněním prostředí se neodstraní připojení k prostředí Dataverse. Pokud v budoucnu plánujete připojit stejné prostředí Dataverse k novému prostředí Customer Insights, [musíte toto připojení odebrat z prostředí Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte prostředí, které chcete odstranit, a vyberte vertikální tři tečky (&vellip;). 

1. Vyberte **Odstranit**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola odstranění prostředí":::

1. Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
