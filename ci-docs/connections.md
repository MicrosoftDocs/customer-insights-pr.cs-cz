---
title: Přehled propojení (preview)
description: Propojení k dalším službám z Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245503"
---
# <a name="connections-preview-overview"></a>Přehled propojení (preview)

Propojení jsou klíčem k povolení sdílení dat do a z Customer Insights. Každé propojení navazuje sdílení dat s konkrétní službou. Použití propojení ke [konfiguraci rozšíření třetích stran](enrichment-hub.md) a [konfigurace exportů](export-destinations.md). Stejné propojení lze použít vícekrát. Například jedno propojení k Dynamics 365 Marketing funguje pro více exportů a jedno propojení Leadspace lze použít pro několik rozšíření.

## <a name="export-connections"></a>Export připojení

Pouze správci mohou konfigurovat nová propojení, ale mohou [udělit přístup přispěvatelům](#allow-contributors-to-use-a-connection-for-exports) k použití stávajících propojení. Správci kontrolují, kam mohou data směřovat, přispěvatelé definují datovou část a frekvenci podle svých potřeb.

## <a name="enrichment-connections"></a>Připojení rozšiřování

Jenom správci mohou konfigurovat nová propojení, ale vytvořená propojení jsou vždy k dispozici správcům i přispěvatelům. Správci spravují přihlašovací údaje a udělují souhlas s datovými přenosy. Následně mohou správci i přispěvatelé propojení použít.

## <a name="add-a-new-connection"></a>Přidat nové propojení

### <a name="prerequisites"></a>Předpoklady

- [Oprávnění správce](permissions.md)
- Další služby společnosti Microsoft, pokud existují, jsou ve stejné organizaci

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte možnost **Přidat připojení** a zvolte typ připojení, které chcete vytvořit. Nebo jděte na kartu **Zjistit** a na dlaždici připojení vyberte **Nastavení**.

1. Dejte propojení rozpoznatelný název do pole **Zobrazovaný název**. Název a typ propojení popisují toto propojení. Doporučujeme zvolit název, který vysvětluje účel a cíl propojení.

1. Zadejte požadované údaje. Přesná pole závisí na tom, ke které službě se připojujete. Podrobnosti o konkrétním typu připojení naleznete v článku o cílové službě.

1. Pokud [použijete vlastní trezor klíčů](use-azure-key-vault.md) k uložení tajných kódů, aktivujte **Použít trezor klíčů** a vyberte tajný kód ze seznamu.

1. Zkontrolujte část Ochrana osobních údajů a dodržování předpisů a vyberte **Souhlasím**.

1. Připojení vytvořte výběrem tlačítka **Uložit**.

### <a name="data-privacy-and-compliance"></a>Ochrana osobních údajů a dodržování předpisů

Když aplikaci Dynamics 365 Customer Insights povolíte přenos dat do produktů třetích stran nebo spolčenosti Microsoft, povolíte přenos dat mimo hranici dodržování předpisů pro Dynamics 365 Customer Insights, včetně potenciálně citlivých údajů, jako jsou osobní údaje. Společnost Microsoft přenese tato data na váš pokyn, ale vy jste odpovědní za to, že třetí strana splní veškeré vaše povinnosti v oblasti ochrany osobních údajů nebo zabezpečení. Další informace viz [Prohlášení Microsoftu o zásadách ochrany osobních údajů](https://go.microsoft.com/fwlink/?linkid=396732).

Tuto funkci připojení může kdykoli odebráním ukončit správce Dynamics 365 Customer Insights.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Umožnit přispěvatelům použít propojení pro export

Při nastavování nebo úpravách propojení pro export si vyberete, kterým uživatelům je povoleno definovat toto konkrétní propojení [exporty](export-destinations.md). Ve výchozím nastavení je propojení k dispozici uživatelům s rolí správce. Změňte nastavení **Vyberte, kdo může toto propojení použít** a umožněte tak uživatelům s rolí přispěvatel používat toto propojení.

- Přispěvatelé nebudou moci propojení zobrazit ani upravit. Při vytváření exportu uvidí pouze zobrazované jméno a jeho typ.
- Sdílením propojení umožňujete přispěvatelům propojení používat. Přispěvatelé uvidí sdílená propojení, když nastaví export. Mohou spravovat každý export, který používá toto konkrétní propojení.
- Toto nastavení můžete změnit při zachování exportů, které již byly definovány přispěvateli.

## <a name="manage-existing-connections"></a>Správa existujících připojení

1. Přejděte na **Správce** > **Propojení**.

1. Výběrem karty **Rozšiřování** nebo **Exporty** zobrazíte seznam obohacených nebo exportních připojení, typ připojení, kdy bylo vytvořeno a kdo má přístup. Seznam připojení můžete seřadit podle libovolného sloupce.

1. Vyberte připojení pro zobrazení dostupných akcí.

   - **Upravte** připojení.
   - [**Odeberte**](#remove-a-connection) připojení.

### <a name="remove-a-connection"></a>Odebrání propojení

Pokud je připojení, které odstraňujete, používáno obohacením nebo exportem, musíte je nejprve odpojit nebo odebrat. Dialogové okno odebrání vás provede příslušným rozšířením nebo exportem.

> [!TIP]
> Deaktivovaná rozšiřování a odpojené exporty se stanou neaktivními. Znovu je aktivujete přidáním dalšího propojení na stránce [Rozšíření](enrichment-hub.md) nebo [Exporty](export-destinations.md).

1. Přejděte na **Správce** > **Propojení**.

1. Vyberte kartu **rozšiřování** nebo **Exporty**.

1. Vyberte připojení, které chcete odebrat.

1. V rozevírací nabídce vyberte možnost **Odebrat**. Zobrazí se dialogové okno s potvrzením.

   1. Pokud existují rozšíření nebo exporty, která toto propojení používají, vyberte tlačítko a podívejte se, co propojení používá.
      - **Exporty:** Vyberte buď **Odstranit** export nebo **Odpojit připojení**. Odpojením připojení zachováte exportní konfiguraci, ale nebude spuštěna, dokud k ní nebude přidáno další propojení.
      - **Rozšiřování:** Vyberte si buď **Odstranit** nebo **Deaktivovat** rozšiřování.
   1. Jakmile propojení již nemá žádné závislosti, vraťte se zpět na **Správce** > **Propojení** a zkuste propojení znovu odebrat.

1. Odstranění potvrďte výběrem **Odstranit**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Nastavte připojení pomocí tajných kódů spravovaných vaším vlastním trezorem klíčů

Některá připojení vyžadují tajné kódy, jako jsou klíče API nebo hesla. Některá připojení podporují tajné kódy uložené ve vašem vlastním trezoru klíčů. Další informace o podporovaných připojeních a o tom, jak je nastavit ve [vašem vlastním trezoru klíčů pro Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
