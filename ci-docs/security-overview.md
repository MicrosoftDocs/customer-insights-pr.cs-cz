---
title: Nakonfigurujte nastavení zabezpečení
description: Přečtěte si o nastavení zabezpečení v Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246054"
---
# <a name="configure-security-settings"></a>Nakonfigurujte nastavení zabezpečení

Správa klíčů API, přístup k údajům zákazníků a nastavení privátního propojení Azure.

## <a name="manage-api-keys"></a>Správa klíčů API

Zobrazte a spravujte klíče k použití [Rozhraní API Customer Insights](apis.md) s daty vašeho prostředí.

1. Jděte na **Systém** > **Zabezpečení** a vyberte kartu **API**.

1. Pokud nebyl nastaven přístup API k prostředí, vyberte **Povolit**. Nebo, chcete-li zablokovat přístup API k prostředí, vyberte **Zakázat** a potvrďte.

1. Správa primárních a sekundárních klíčů API:

   1. Chcete-li zobrazit primární nebo sekundární klíč API, vyberte symbol **Ukázat**.

   1. Chcete-li zkopírovat primární nebo sekundární klíč API, vyberte symbol **Kopírovat**.

   1. Chcete-li vytvořit nové primární nebo sekundární klíče API, vyberte možnost **Znovu generovat primární** nebo **Znovu generovat sekundární**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Bezpečný přístup k zákaznickým datům s Customer Lockbox (Preview)

Customer Insights používá schopnost Možnost zákaznické schránky Power Platform. Customer Lockbox poskytuje rozhraní pro kontrolu a schválení (nebo zamítnutí) žádostí o přístup k datům. K těmto žádostem dochází, když je potřeba datový přístup k zákaznickým údajům k vyřešení případu podpory. Chcete-li používat tuto funkci, musí mít Customer Insights existující připojení k prostředí Microsoft Dataverse ve vašem klientovi.

Další informace o Customer Lockbox naleznete v [souhrnu](/power-platform/admin/about-lockbox#summary) z Customer Lockbox Power Platform. Článek také popisuje [pracovní postup](/power-platform/admin/about-lockbox#workflow) a požadované [nastavení](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) pro aktivaci Customer Lockbox.

> [!IMPORTANT]
> Globální správci pro správce Power Platform nebo Power Platform mohou schvalovat požadavky Customer Lockbox vydaného pro Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Nastavení Azure Private Link

[Soukromé propojení Azure](/azure/private-link/private-link-overview) umožňuje Customer Insights propojit se s vaším účtem Azure Data Lake Storage přes soukromý koncový bod ve vaší virtuální síti. Pro data v účtu úložiště, která nejsou vystavena veřejnému internetu, umožňuje privátní propojení připojení k této omezené síti.

> [!IMPORTANT]
> Minimální požadavek na roli pro nastavení připojení přes privátní propojení:
>
> - Customer Insights: správce
> - Integrovaná role Azure: [Účet úložiště přispěvatel](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Oprávnění pro vlastní roli Azure: [Microsoft.Storage/storageAccounts/read a Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. V Customer Insights přejděte na **Správce** > **Zabezpečení** a vyberte kartu **Private Link**.

1. Vyberte **Přidat Private Link**.

   Podokno **Přidat soukromý odkaz** uvádí účty úložiště z klienta, k jejichž zobrazení máte oprávnění.

1. Vyberte předplatné, skupinu zdrojů a účet úložiště.

1. Zkontrolujte část [Ochrana osobních údajů a dodržování předpisů](connections.md#data-privacy-and-compliance) a vyberte **Souhlasím**.

1. Vyberte **Uložit**.

1. Přejděte na svůj účet Data Lake Storage a otevřete odkaz zobrazený na obrazovce.

1. Schvalte Private Link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
