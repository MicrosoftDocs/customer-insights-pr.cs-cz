---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755536"
---
Po zpracování dat zahajte proces sjednocování dat a vytvořte jednotný profil zákazníka. Další informace naleznete v tématu [Sjednocení dat](../data-unification.md).

### <a name="select-source-fields"></a>Výběr zdrojových polí

1. Po ingestaci dat namapujte kontakty z eCommerce a věrnostní data na běžné datové typy. Přejděte na **Data** > **Sjednotit**.

1. Vyberte entity, které představují profil zákazníka – **eCommerceContacts** a **loyCustomers**.

   ![Sjednocení zdrojů dat eCommerce a věrnostních bodů.](../media/unify-ecommerce-loyalty.png)

1. Vyberte **ContactId** jako primární klíč pro **eCommerceContatcs** a **LoyaltyID** jako primární klíč pro **loyCustomers**.

1. Vyberte **Další**. Přeskočte duplicitní záznamy a vyberte **další**.

### <a name="match-conditions"></a>Podmínky shody

1. Zvolte **eCommerceContacts: eCommerce** jako primární entitu a zahrňte všechny záznamy.

1. Vyberte **loyCustomers: LoyaltyScheme** a zahrňte všechny záznamy.

1. Přidání pravidla:
   - Vyberte **Celé jméno** pro eCommerceContacts a loyCustomers.
   - Vyberte **Typ (telefon, jméno, adresa, ...)** pro **Normalizovat**.
   - Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.
   - Jako jméno zadejte **FullName, Email**.

1. Přidejte druhou podmínku pro e-mailovou adresu:
   - Vyberte **Email** pro eCommerceContacts a loyCustomers.
   - Ponechejte pole Noramlizovat prázdné.
   - Nastavte **Úroveň přesnosti**: **Základní** a **Hodnota**: **Vysoká**.

   ![Sjednocení pravidla párování pro jméno a e-mail.](../media/unify-match-rule.png)

1. Vyberte **Hotovo**.

1. Vyberte **Další**.

### <a name="unify-fields"></a>Sjednocení polí

1. Přejmenujte **ContactId** pro entitu **loyCustomers** na **ContactIdLOYALTY** k odlišení od ostatních zpracovaných ID.

1. Vyberte **Další** ke kontrole a poté vyberte **Vytvořit profily zákazníků**.
