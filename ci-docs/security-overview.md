---
title: Nastavení zabezpečení v Customer Insights
description: Přečtěte si o nastavení zabezpečení v Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947407"
---
# <a name="security-settings-in-customer-insights"></a>Nastavení zabezpečení v Customer Insights

Stránka **Zabezpečení** uvádí možnosti konfigurace uživatelských oprávnění a funkcí, které pomáhají více zabezpečit Dynamics 365 Customer Insights. Na tuto stránku mají přístup pouze správci.

Přejděte na **Správce** > **Zabezpečení** pro konfiguraci nastavení.

Stránka **Zabezpečení** obsahuje následující karty:

- [Uživatelé](#users-tab)
- [Rozhraní API](#apis-tab)
- [Privátní odkazy](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Bezpečný přístup k zákaznickým datům s Customer Lockbox (Preview)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Karta Uživatelé

Přístup k Customer Insights je omezen na uživatele ve vaší organizaci, které do aplikace přidal správce. Karta **Uživatelé** umožňuje spravovat přístup uživatelů a jejich oprávnění. Další informace naleznete viz [Oprávnění uživatele](permissions.md).

## <a name="apis-tab"></a>Karta API

Zobrazte a spravujte klíče k použití [Rozhraní API Customer Insights](apis.md) s daty vašeho prostředí.

Můžete vytvořit nový primární a sekundární klíč výběrem **Regenerujte primární** nebo **Regenerujte sekundární**. 

Chcete-li zablokovat přístup API k prostředí, vyberte **Zakázat**. Pokud jsou rozhraní API zakázána, můžete vybrat **Povolit** a znovu udělit přístup.

## <a name="private-links-tab"></a>Karta Privátní propojení

[Soukromé propojení Azure](/azure/private-link/private-link-overview) umožňuje Customer Insights propojit se s vaším účtem Azure Data Lake Storage přes soukromý koncový bod ve vaší virtuální síti. Pro data v účtu úložiště, která nejsou vystavena veřejnému internetu, umožňuje privátní propojení připojení k této omezené síti.

> [!IMPORTANT]
> Minimální požadavek na roli pro nastavení připojení přes privátní propojení:
>
> - Customer Insights: správce
> - Integrovaná role Azure: [Účet úložiště přispěvatel](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Oprávnění pro vlastní roli Azure: [Microsoft.Storage/storageAccounts/read a Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Nastavení privátního propojení v Customer Insights je dvoufázový proces. Nejprve zahájíte vytvoření soukromého odkazu z **Správa** > **Zabezpečení** > **Privátní propojení** v Customer Insights. Podokno **Přidat soukromý odkaz** uvádí účty úložiště z klienta, k jejichž zobrazení máte oprávnění. Vyberte účet úložiště a poskytněte souhlas s vytvořením soukromého odkazu.

Dále musíte schválit privátní propojení na straně účtu Data Lake Storage. Chcete-li nové privátní propojení schválit, otevřete propojení uvedené na obrazovce.

## <a name="key-vault-tab"></a>Karta Trezor klíčů

Karta **Trezor klíčů** umožňuje propojit a spravovat svůj vlastní [trezor klíčů Azure](/azure/key-vault/general/basic-concepts) k prostředí.
Vyhrazený trezor klíčů lze použít k vytvoření a použití tajných kódů na hranici dodržování předpisů organizace. Customer Insights mohou použít tajné kódy v Azure Key Vault pro [nastavení připojení](connections.md) se systémy třetích stran.

Další informace viz téma [Použití vlastního trezoru klíčů Azure](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpečný přístup k zákaznickým datům s Customer Lockbox (Preview)

Customer Insights používá schopnost Možnost zákaznické schránky Power Platform. Customer Lockbox poskytuje rozhraní pro kontrolu a schválení (nebo zamítnutí) žádostí o přístup k datům. K těmto žádostem dochází, když je potřeba datový přístup k zákaznickým údajům k vyřešení případu podpory. Chcete-li používat tuto funkci, musí mít Customer Insights existující připojení k prostředí Microsoft Dataverse ve vašem klientovi.

Další informace o Customer Lockbox naleznete v [souhrnu](/power-platform/admin/about-lockbox#summary) z Customer Lockbox Power Platform. Článek také popisuje [pracovní postup](/power-platform/admin/about-lockbox#workflow) a požadované [nastavení](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) pro aktivaci Customer Lockbox.

> [!IMPORTANT]
> Globální správci pro správce Power Platform nebo Power Platform mohou schvalovat požadavky Customer Lockbox vydaného pro Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
