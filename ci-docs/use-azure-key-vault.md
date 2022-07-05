---
title: Přineste si vlastní Azure key vault (preview)
description: Zjistěte, jak nakonfigurovat Customer Insights tak, aby ke správě tajných klíčů používala váš vlastní Azure key vault,
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080902"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Přineste si vlastní Azure key vault (preview)

Propojení vyhrazeného prostředí [Azure key vault](/azure/key-vault/general/basic-concepts) s prostředím Customer Insights pomáhá organizacím plnit požadavky na dodržování předpisů.
Vyhrazený trezor klíčů lze použít k vytvoření a použití tajných kódů na hranici dodržování předpisů organizace. Customer Insights mohou použít tajné kódy v Azure Key Vault pro [nastavení připojení](connections.md) se systémy třetích stran.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Propojení trezoru klíčů s prostředím Customer Insights

### <a name="prerequisites"></a>Předpoklady

Chcete-li konfigurovat trezor klíčů v Customer Insights, musí být splněny následující předpoklady:

- Musíte mít aktivní předplatné Azure.

- Máte roli [správce](permissions.md#admin) v Customer Insights. Více informací o [oprávněních uživatele v Customer Insights](permissions.md#assign-roles-and-permissions).

- Máte role [Přispěvatel](/azure/role-based-access-control/built-in-roles#contributor) a [Správce přístupu uživatele](/azure/role-based-access-control/built-in-roles#user-access-administrator) v trezoru klíčů nebo skupině prostředků, ke které trezor klíčů patří. Další informace najdete v části [Přidání nebo odebrání přiřazení rolí Azure pomocí Azure Portal](/azure/role-based-access-control/role-assignments-portal). Pokud v trezoru klíčů nemáte roli správce přístupu uživatele, musíte nastavit oprávnění pro řízení přístupu na základě rolí pro instanční objekt služby Azure pro Dynamics 365 Customer Insights odděleně. Postupujte podle pokynů k [použití instančního objektu Azure](connect-service-principal.md) pro trezor klíčů, který by měl být propojen.

- Trezor klíčů musí mít **zakázanou** bránu firewall Key Vault.

- Trezor klíčů je ve stejném [umístění Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) jako prostředí Customer Insights. Oblast prostředí v Customer Insights je uvedena níže v části **Správce** > **Systém** > **O programu** > **Region**.

### <a name="link-a-key-vault-to-the-environment"></a>Propojení trezoru klíčů s prostředím

1. Jděte na **Správa** > **Zabezpečení** a vyberte kartu **Trezor klíčů**.
1. V dlaždici **Trezor klíčů** vyberte **Nastavení**.
1. Zvolte **Předplatné**.
1. Vyberte trezor klíčů z rozbalovacího seznamu **Trezor klíčů**. Pokud se zobrazuje příliš mnoho trezorů klíčů, omezte výsledky hledání výběrem skupiny zdrojů.
1. Přijměte prohlášení o **ochraně osobních údajů a dodržování předpisů**.
1. Vyberte **Uložit**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Kroky k nastavení propojeného trezoru klíčů v Customer Insights.":::

Dlaždice **Trezor klíčů** nyní zobrazuje název propojeného trezoru klíčů, skupinu zdrojů a předplatné. Je připraven k použití v nastavení připojení.
Podrobnosti o tom, která oprávnění v trezoru klíčů jsou udělována v Customer Insights, najdete v části [Oprávnění udělená v trezoru klíčů](#permissions-granted-on-the-key-vault), dále v tomto článku.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Použití trezoru klíčů v nastavení připojení

Při [nastavení připojení](connections.md) do systémů třetích stran lze ke konfiguraci připojení použít tajemství z propojeného trezoru klíčů.

1. Přejděte na **Správce** > **Propojení**.
1. Vyberte **Přidat připojení**.
1. U podporovaných typů připojení je přepínač **Použít Key Vault** k dispozici, pokud jste propojili trezor klíčů.
1. Namísto ručního zadávání tajného klíče můžete zvolit tajný název, který ukazuje na tajnou hodnotu v trezoru klíčů.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Podokno připojení s připojením SFTP, které používá tajný klíč Key Vault.":::

## <a name="supported-connection-types"></a>Podporované typy připojení

Jsou podporována následující připojení [exportu](export-destinations.md):

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Oprávnění udělená v trezoru klíčů

Následující oprávnění jsou udělena Customer Insights o propojeném trezoru klíčů, pokud buď [Zásady přístupu ke službě Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) nebo [Řízení přístupu na základě rolí Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je povoleno.

### <a name="key-vault-access-policy"></a>Zásady přístupu Key Vault

| Typ        | Oprávnění          |
| ----------- | -------------------- |
| Klávesa         | [Získat klíče](/rest/api/keyvault/keys/get-keys/get-keys), [Získat klíče](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Tajný      | [Získat tajné kódy](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Získat tajné kódy](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certifikát | [Získat certifikáty](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Získat certifikát](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Předchozí hodnoty jsou minimum, které je třeba během provádění vypisovat a číst.

### <a name="azure-role-based-access-control"></a>Řízení přístupu na základě rolí Azure

Pro Customer Insights budou přidány uživatelské role Čtenář Key Vault a Tajemství Key Vault. Podrobnosti o těchto rolích najdete v tématu [Integrované role Azure pro operace s rovinou dat Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Doporučení

- Použijte samostatný nebo vyhrazený trezor klíčů, který obsahuje pouze tajemství požadovaná pro Customer Insights. Přečtěte si více o tom, proč [se doporučují samostatné trezory klíčů](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Dodržujte [osvědčené postupy pro používání Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) pro možnosti řízení přístupu, zálohování, auditu a obnovy.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Mohou Customer Insights zapisovat nebo přepisovat tajné klíče v trezoru klíčů?

Č. Pouze oprávnění ke čtení a seznamu uvedená v sekci [udělená oprávnění](#permissions-granted-on-the-key-vault) dříve v tomto článku jsou poskytovány Customer Insights. Systém nemůže v trezoru klíčů přidávat, odstraňovat ani přepisovat tajné kódy. To je také důvod, proč nemůžete zadat přihlašovací údaje, když připojení používá Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Mohu změnit připojení z používání tajných kódů Key Vault na výchozí ověřování?

Č. Poté, co jste jej nakonfigurovali pomocí tajného kódu z propojeného trezoru klíčů, nemůžete změnit zpět na výchozí připojení. Vytvořte samostatné připojení a odstraňte staré, pokud jej již nepotřebujete.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Jak mohu zrušit přístup k trezoru klíčů pro Customer Insights?

Podle toho, zda [Zásady přístupu ke službě Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) nebo [Řízení přístupu na základě rolí Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) je povoleno, musíte odebrat oprávnění pro instanční objekt `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nazvaný `Dynamics 365 AI for Customer Insights`. Všechna připojení, která používají trezor klíčů, přestanou fungovat.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Z trezoru klíčů bylo odstraněno tajemství, které se používá ve spojení. Co mám dělat?

V Customer Insights se zobrazí oznámení, když konfigurovaný tajný kód z trezoru klíčů již není přístupný. Povolte [jemné odstranění](/azure/key-vault/general/soft-delete-overview) v trezoru klíčů pro obnovení tajemství, pokud jsou omylem odstraněna.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Připojení nefunguje, ale můj tajný kód je v trezoru klíčů. Co by mohlo být příčinou?

Když v Customer Insights nelze získat přístup k trezoru klíčů, zobrazí se oznámení. Příčina by mohla být následující:

- Byla odebrána oprávnění pro instanční objekt pro Customer Insights. Je třeba je ručně obnovit.

- Brána firewall v trezoru klíčů je povolena. Aby byl trezor klíčů opět přístupný pro Customer Insights, musí být deaktivován.
