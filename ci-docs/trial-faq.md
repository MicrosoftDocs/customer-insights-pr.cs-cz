---
title: Nejčastější otázky ke zkušební verzi Dynamics 365 Customer Insights
description: Řešení častých otázek týkajících se nastavení a správy zkušební verze Customer Insights. Přečtěte si, jak vyřešit problémy s platformou a aplikacemi.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051491"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Nejčastější otázky ke zkušební verzi Dynamics 365 Customer Insights

## <a name="sign-up"></a>Registrace

### <a name="what-are-the-system-requirements-for-the-trial"></a>Jaké jsou systémové požadavky pro zkušební verzi?

Tato aplikace je cloudová služba, která kromě aktualizovaného webového prohlížeče nevyžaduje žádný další speciální software, i když platí určitá omezení. Chcete -li dosáhnout nejlepšího zkušebního provozu, vyhněte se přístupu na zkušební web v anonymním režimu a vyberte si zkušební místo, které je vám nejblíže. [Další informace o požadavcích na webovou aplikaci.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Jak se zaregistruji ke zkušební verzi bez klienta Microsoft 365?

Můžete zadat nepracovní e-mailovou adresu a my vám vytvoříme účet a klienta.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Můžu se zaregistrovat k více aplikacím Dynamics 365, jako je Sales, Marketing a Customer Service?

Ano, můžete. Chcete-li zobrazit všechny dostupné zkušební verze, [navštivte stránku zkušebního centra](https://dynamics.microsoft.com/dynamics-365-free-trial). Ke přihlášení k různým zkušebním pokusům můžete použít stejný e-mailový účet. Na stejném zkušebním webu však není možné mít více aplikací. Každá zkušební verze bude na jiné organizaci a adrese URL. Zkušební data se nebudou sdílet mezi aplikacemi.

## <a name="trial-app"></a>Zkušební aplikace

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Po registraci jsem neobdržel e-mail s podrobnostmi o zkušebním období, co mám dělat?

Když se zaregistrujete ke zkušební verzi, obdržíte e-mail s podrobnostmi o zkušební verzi. Pokud e-mail ve složce Doručená pošta nevidíte, zkontrolujte složku se spamem. Případně pro přístup k aplikaci použijte následující kroky:

1. Přejděte na zkušební web a vyberte **Vyzkoušet zdarma**.
1. Zadejte ID e-mailu, který jste použili, abyste se přihlásili ke zkušební verzi. Budete přesměrováni do zkušební aplikace.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Jak přidám do zkušební verze další uživatele?

Pokud chcete přidat uživatele, přejděte pomocí účtu správce zkušební verze do [Centra pro správu Microsoft 365](https://admin.microsoft.com). Podle pokynů [centra pro správu](/microsoft-365/admin/add-users/add-users) přidejte uživatele až do limitu zkušební licence. Pokud již uživatel, kterého přidáváte, má účet Microsoft 365, přiřaďte mu roli zabezpečení v organizaci zkušební verze. Další informace naleznete v tématu [Přiřazení role zabezpečení uživateli](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Kolik uživatelů mohu přidat do zkušebního prostředí?

Do zkušebního prostředí můžete přidat neomezený počet uživatelů.

### <a name="how-do-i-reset-the-trial-environment"></a>Jak mohu resetovat zkušební prostředí?

Zkušební prostředí není možné resetovat. Můžete však počkat na ukončení zkušebního období a poté se znovu zaregistrovat k nové zkušební verzi.

## <a name="trial-expiration-and-extension"></a>Vypršení platnosti a prodloužení zkušební verze

### <a name="how-do-i-extend-the-trial"></a>Jak mohu prodloužit zkušební verzi?

Zkušební verzi můžete v aplikaci prodloužit přímo. Zkušební verzi můžete prodloužit jednou.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Mohu zkušební verzi převést na placenou licenci?

Při upgradu na placenou verzi Customer Insights obecně doporučujeme začít s novými daty. 

Pokud volitelně používáte pouze Customer Insights, můžete si data zkopírovat ze zkušebního prostředí, pokud si zakoupíte Customer Insights. Musíte být správcem zkušební verze Customer Insights a globálním správcem svého klienta Microsoft 365 nebo správcem Dynamics 365 ve vaší organizaci k migraci nastavení ze zkušebního prostředí do placeného prostředí.

Po prvním přihlášení k placené instanci Customer Insights budete požádáni o vytvoření nového prostředí. V tomto procesu se můžete rozhodnout zkopírovat konfiguraci z existujícího prostředí a migrovat většinu nastavení. Pokud máte výše uvedená oprávnění, zkušební prostředí se zobrazí v tomto seznamu. Další informace viz [Kopírování konfigurace prostředí](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Jaké jsou limity a kvóty zkušební verze?

- Během zkušební verze Customer Insights nemůžete použít vlastní účet úložiště Azure Data Lake Storage k ukládání výstupních dat. Data však můžete přijímat z účtu Data Lake Storage.
- Můžete uložit až 3 GB dat prostředí Dataverse, které se automaticky zřídí, když spustíte zkušební verzi Customer Insights.

## <a name="customer-insights-specific-questions"></a>Customer Insights – konkrétní otázky

### <a name="how-do-i-start-using-the-trial"></a>Jak mohu začít zkušební verzi používat?

Po přihlášení ke zkušební verzi se dostanete na hlavní obrazovku aplikace. Hlavní obrazovka obsahuje odkazy na uživatelské příručky a výukové programy. Další informace najdete na odkazech v části [Další zdroje](trial-signup.md#additional-resources) na stránce registrace zkušební verze.

### <a name="what-features-are-available-in-the-trial"></a>Jaké funkce jsou dostupné ve zkušební verzi?

Většina funkcí funkcí Customer Insights je k dispozici ve zkušební verzi.

Následující funkce **nejsou k dispozici**:

- Nemůžete vytvářet nová prostředí, která používají váš vlastní účet Azure Data Lake Storage.
- Prostředí zkušební verze není možné odstranit.

### <a name="how-long-does-the-trial-last"></a>Jak dlouho zkušební verze platí?

Zkušební verze Customer Insights trvá 30 dní. Zkušební verzi můžete prodloužit jednou po 23 dnech, když se přihlásíte do zkušebního prostředí.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Jak odeberu ukázková data ze zkušební verze?

Nemůžete odebrat ukázková data ze zkušební verze.
