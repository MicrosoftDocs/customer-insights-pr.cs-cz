---
title: Návod - Správa prostředí
description: Naučte se, jak spravovat stávající prostředí Customer Insights jako správce."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833484"
---
# <a name="how-to-manage-environments"></a>Návod: Správa prostředí

Správci [vytváří](create-environment.md) a spravují prostředí. Mohou změnit některá nastavení ve stávajících prostředích. Firma, typ, region, možnost úložiště a nastavení Dataverse jsou po vytvoření prostředí neměnné. Pokud chcete tato nastavení změnit, resetujte prostředí nebo vytvořte nové prostředí.

## <a name="edit-an-existing-environment"></a>Úprava stávajícího prostředí

Můžete upravit některé podrobnosti existujících prostředí.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte ikonu **Upravit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikona pro úpravu nastavení prostředí.":::

1. V poli **Upravit prostředí** můžete aktualizovat nastavení prostředí.

Chcete-li začít s novým prostředím, informace získáte v tématu [Vytvoření nového prostředí](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Změna vlastníka prostředí

Několik uživatelů může mít oprávnění správce, vlastníkem prostředí je ale pouze jeden uživatel. Ve výchozím nastavení je to správce, kdo na samém začátku vytváří prostředí. Jako správce prostředí můžete přiřadit vlastnictví jinému uživateli s oprávněním správce.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte ikonu **Upravit**.

1. V poli **Upravit prostředí** přejděte na krok **Základní informace**.

1. V poli **Změnit vlastníka prostředí** vyberte nového vlastníka prostředí.  

1. Vyberte **Zkontrolovat a dokončit** a pak příkazem **Aktualizovat** aplikujte změny.

## <a name="claim-ownership-of-an-environment"></a>Deklarace vlastnictví prostředí

Pokud je uživatelský účet vlastníka odstraněn nebo pozastaven, prostředí nebude mít vlastníka. Každý uživatel s rolí správce si může nárokovat vlastnictví a stát se novým vlastníkem. Mohou nadále vlastnit prostředí nebo [změnit vlastnictví na jiného správce](#change-the-owner-of-an-environment).

Chcete-li nárokovat vlastnictví, vyberte tlačítko **Převzít vlastnictví**, které se zobrazí v horní části každé stránky v Customer Insights, když původní vlastník opustil organizaci.

## <a name="reset-an-existing-environment-preview"></a>Resetování stávajícího prostředí (Preview)

Jako vlastník prostředí můžete resetovat prostředí do prázdného stavu, pokud chcete odstranit všechny konfigurace a odebrat ingestovaná data.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte prostředí, které chcete resetovat, a vyberte vertikální tři tečky (&vellip;).

1. Vyberte volbu **Obnovit**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrola resetování prostředí.":::

1. Vyberte, zda chcete resetovat celé prostředí, vše kromě zdrojů dat nebo vše, co je nakonfigurováno nad jednotným profilem zákazníka.

1. Pro potvrzení zadejte název prostředí a vyberte **Resetovat**.

## <a name="delete-an-existing-environment"></a>Odstranění existujícího prostředí

Jako vlastník prostředí můžete odstranit prostředí, které spravujete.

1. Vyberte nástroj pro výběr **prostředí** v záhlaví aplikace.

1. Vyberte prostředí, které chcete resetovat, a vyberte vertikální tři tečky (&vellip;). 

1. Vyberte volbu **Odstranit**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrola odstranění prostředí":::

1. Chcete-li odstranění potvrdit, zadejte název prostředí a vyberte **Odstranit**.

> [!IMPORTANT]
> Odstraněním prostředí se neodstraní připojení k prostředí Dataverse. Pokud plánujete připojit stejné prostředí Dataverse do nového prostředí Customer Insights, musíte toto připojení odebrat. Podívejte se na část, jak [odstranit existující připojení k prostředí Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
