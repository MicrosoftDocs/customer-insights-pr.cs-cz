---
title: Nastavení zabezpečení v Dynamics 365 Customer Insights
description: Přečtěte si o nastavení zabezpečení v Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653700"
---
# <a name="security-overview-page"></a>Stránka Přehled zabezpečení

Stránka **Zabezpečení** uvádí možnosti konfigurace uživatelských oprávnění a funkcí, které pomáhají více zabezpečit Dynamics 365 Customer Insights. Na tuto stránku mají přístup pouze správci. 

Přejděte na **Správce** > **Zabezpečení** pro konfiguraci nastavení.

Stránka **Zabezpečení** obsahuje následující karty:
- [Uživatelé](#users-tab)
- [Rozhraní API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Karta Uživatelé

Přístup k Customer Insights je omezen na uživatele ve vaší organizaci, které do aplikace přidal správce. Karta **Uživatelé** umožňuje spravovat přístup uživatelů a jejich oprávnění. Další informace naleznete viz [Oprávnění uživatele](permissions.md).

## <a name="apis-tab"></a>Karta API

Zobrazte a spravujte klíče k použití [Rozhraní API Customer Insights](apis.md) s daty vašeho prostředí.

Můžete vytvořit nový primární a sekundární klíč výběrem **Regenerujte primární** nebo **Regenerujte sekundární**. 

Chcete-li zablokovat přístup API k prostředí, vyberte **Zakázat**. Pokud jsou rozhraní API zakázána, můžete vybrat **Povolit** a znovu udělit přístup.

## <a name="key-vault-tab"></a>Karta Trezor klíčů

Karta **Trezor klíčů** umožňuje propojit a spravovat svůj vlastní [trezor klíčů Azure](/azure/key-vault/general/basic-concepts) k prostředí.
Vyhrazený trezor klíčů lze použít k vytvoření a použití tajných kódů na hranici dodržování předpisů organizace. Customer Insights mohou použít tajné kódy v Azure Key Vault pro [nastavení připojení](connections.md) se systémy třetích stran.

Další informace viz téma [Použití vlastního trezoru klíčů Azure](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
