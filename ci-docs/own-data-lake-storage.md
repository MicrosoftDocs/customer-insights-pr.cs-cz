---
title: Použití vlastního účtu Azure Data Lake Storage Gen2
author: mukeshpo
description: Přečtěte si o požadavcích na použití vlastního účtu Azure Data Lake Storage pro ukládání dat Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011925"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Použití vlastního účtu Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights vám dává možnost uložit všechna svá data v [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Uložením dat do Data Lake Storage souhlasíte s tím, že data budou přenesena a uložena v příslušném geografickém umístění pro daný účet úložiště Azure. Další informace naleznete v tématu [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Správci v Customer Insights mohou [vytvářet prostředí](create-environment.md) a [určit možnost ukládání dat](create-environment.md#step-2-configure-data-storage) v procesu.

## <a name="prerequisites-to-use-your-storage-account"></a>Požadavky pro použití vašeho účtu úložiště

- Účty Azure Data Lake Storage musí být ve stejné oblasti Azure, kterou jste vybrali při vytváření prostředí Customer Insights. Oblast prostředí Customer Insights můžete zkontrolovat v části **Správce** > **Systém** > **O aplikaci**.
- Data Lake Storage musí být ve verzi Gen2 a mít [povolený hierarchický obor názvů](/azure/storage/blobs/create-data-lake-storage-account). Účty úložiště Gen1 nejsou podporovány.
- Kontejner s názvem `customerinsights` musí existovat na účtu úložiště. Musíte jej vytvořit dříve, než použijete své vlastní úložiště Data Lake Storage v Customer Insights. Správce, který nastavuje prostředí Customer Insights, potřebuje roli Přispěvatel dat objektů blob úložiště nebo roli vlastníka dat Storage objektů blob úložiště nebo kontejner `customerinsights`. Další informace o přidělování oprávnění v účtu úložiště naleznete v části [Vytvoření účtu úložiště](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Propojení Customer Insights se svým účtem úložiště

Když vytváříte nové prostředí, ujistěte se, že existuje účet Data Lake Storage a že jsou splněny všechny předpoklady.

1. V kroku **Datové úložiště** při vytváření prostředí nastavte **Uložit výstupní data** na **Azure Data Lake Storage Gen2**.
1. Vyberte si, jak **Připojit úložiště**. Pro ověřování si můžete vybrat mezi možností založenou na zdrojích a možností založenou na předplatném. Více informací viz [Připojení k účtu Azure Data Lake Storage pomocí instančního objektu Azure](connect-service-principal.md).
   - Pro **Předplatné Azure** vyberte **Předplatné**, **Skupina zdrojů** a **Účet úložiště**, která obsahuje kontejner `customerinsights`.
   - Pro **Klíč účtu** zadejte **Název účtu** a **Klíč účtu** pro účet Data Lake Storage. Použití této metody ověřování znamená, že jste informováni, pokud vaše organizace otočí klíče. Musíte [aktualizovat konfiguraci prostředí](manage-environments.md#edit-an-existing-environment) o nový klíč, když je otočen.
1. Vyberte, zda chcete pro připojení k účtu úložiště použít Azure Private Link a [vytvořit připojení k Private Link](security-overview.md#private-links-tab) s dvoufázovým procesem.

Po dokončení systémových procesů, jako je například příjem dat, systém vytvoří odpovídající složky v účtu úložiště. Datové soubory a soubory *model.json* se vytvářejí a přidávají do složek na základě názvu procesu.

Pokud vytvoříte více prostředí Customer Insights a rozhodnete se uložit výstupní entity z těchto prostředí do svého účtu úložiště, vytvoří Customer Insights pro každé prostředí samostatné složky s `ci_environmentID` v kontejneru.
