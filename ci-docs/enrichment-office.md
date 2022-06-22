---
title: Rozšíření profilů zákazníků o data z Microsoft Office 365
description: Pomocí vlastnických dat z Microsoft Office můžete rozšířit vaše zákaznické profily o data o zapojení.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954125"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Rozšíření profilů zákazníků o data o zapojení (Preview)

Pomocí dat z Microsoft Office 365 můžete rozšířit profily vašich zákaznických účtů o přehledy o zapojení prostřednictvím aplikací Office 365. Data o zapojení se skládají z aktivit e-mailů a schůzek, které jsou agregovány na úrovni účtu. Například počet e-mailů z obchodního účtu nebo počet schůzek s obchodním vztahem. Nejsou k dispozici žádné údaje o jednotlivých uživatelích.

## <a name="supported-countries-or-regions"></a>Podporované země nebo regiony

V současné době podporujeme následující regiony: Velká Británie, Evropa, Severní Amerika.

## <a name="prerequisites"></a>Předpoklady

- Aktivní cloudová licence Office 365.
- [Sjednocené profily zákazníků](customer-profiles.md) na základě [obchodních vztahů](work-with-business-accounts.md)
- [Připojená organizace Microsoft Dataverse](create-environment.md#step-3-connect-to-microsoft-dataverse) v prostředí Customer Insights.
- Oprávnění [správce](permissions.md#admin).
- Souhlas od svého správce klienta Office 365 k použití dat Office 365, aby bylo možné v aplikacích Dynamics 365 poskytnout **Přehledy pro organizaci**.

## <a name="configure-the-enrichment"></a>Konfigurace rozšíření

1. Přejděte na **Data** > **Rozšíření** a vyberte kartu **Objevit**.

1. Vyberte příkaz **Rozšířit moje data** na dlaždici **Zapojení obchodního vztahu**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Dlaždice Zapojení účtu":::

1. Zkontrolujte přehled a poté vyberte **Další**.

1. Zadejte e-mailové adresy z vaší organizace, pro které budou data Office agregována. Pro relevantní komunikaci jsou zpracovávány pouze údaje z uvedených e-mailových adres. Osvědčeným postupem je používat e-mailové skupiny, například *Prodejní tým USA*, které můžete spravovat v Office 365. Počet e-mailových adres ve skupinách je rozpoznán a zobrazen. Celkový počet e-mailových adres musí být alespoň 2 a nesmí překročit 2 500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailové adresy pro zapojení účtů.":::

1. Zkontrolujte a poskytněte svůj souhlas pro [souhlas správce klienta Office 365](#office-365-tenant-administrator-consent) výběrem **Souhlasím**.

1. Vyberte **Další**.

1. Vyberte **Sada údajů o kontaktu** a zvolte profil nebo segment, které chcete rozšířit. Vyberte **Další**.

1. Namapujte pole kontaktní e-mailové adresy a vyberte **Další**.

1. Zadejte **Název** rozšíření a **Výstupní entitu**.

1. Po kontrole vašich voleb vyberte **Uložit rozšíření**.

1. Vyberte **Zavřít** pro návrat na stránku **Rozšíření**.

### <a name="office-365-tenant-administrator-consent"></a>Souhlas správce klienta Office 365

Pro aktivaci rozšíření je nutný souhlas správce klienta Office 365. Při uložení rozšíření je správcům klienta Office 365 odeslán e-mail, který je žádá, aby zkontrolovali a souhlasili s povolením aplikací Dynamics 365 používat data Office 365, aby bylo možné poskytovat **Přehledy pro organizaci**. Správce klienta Office 365 může souhlasit také přímo ve své konzole správce Office 365 výběrem možnosti **Přehledy pro organizaci**.

## <a name="running-the-enrichment-for-the-first-time"></a>První spuštění rozšíření

Když je rozšíření poprvé spuštěno, jakmile dá správce klienta Office 365 souhlas, začne stahování dat z Office 365. Tento proces nějakou dobu trvá. První spuštění rozšíření bude naplánován se zpožděním šesti hodin. Počet dní, které data pokrývají, můžete vidět na stránce s přehledem o zapojení účtu po dokončení rozšíření. Při velkém objemu dat spusťte rozšíření po několika dnech znovu. Tím zajistíte úplnost dat pro celý časový interval, což je jeden rok.

V závislosti na velikosti dat Office může dokončení běhu rozšíření trvat několik hodin.

Když spustíte rozšíření, Microsoft zpracuje data v rámci působnosti dodržování předpisů Office 365 k vytvoření agregovaných přehledů, které jsou poté přidány do vašeho prostředí Customer Insights. Uživatelé Customer Insights nebudou mít k dispozici žádná data na individuální úrovni (například obsah e-mailu nebo pozvánky v kalendáři).

Vyberte **Spustit** pro zahájení procesu rozšíření.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Výsledky rozšíření

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] To je entita *Office*. Entita *Office_UserEntity*, která obsahuje ID služby Active Directory pro e-mailové adresy, které byly vybrány během konfigurace rozšíření.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Náhled výsledků po spuštění procesu rozšíření.":::

Všechna data jsou agregována až na úroveň účtu. Systém pro každý účet vypočítává skóre zapojení, které se pohybuje od 0 do 100. Skóre zapojení poskytuje složenou míru zapojení účtu napříč e-maily a schůzkami ve vztahu k vašim ostatním účtům. Následující seznam obsahuje agregovaná data poskytnutá rozšířením zapojení účtu:

| Data                                                                              | Název sloupce                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skóre zapojení                                                                  |  EngagementScore                         |
| Počet e-mailů na účet                                                       |  NoOfEmails_ToAccount                    |
| Počet e-mailů z účtu                                                     |  NoOfEmails_FromAccount                  |
| Počet schůzek iniciovaných účtem                                           |  NoOfMeetings_FromAccount                |
| Počet schůzek iniciovaných vaší organizací                                 |  NoOfMeetings_ToAccount                  |
| Počet lidí z vaší organizace na schůzkách s účtem                  |  NoOfContactsInvolved_Meetings           |
| Počet lidí z vaší organizace v e-mailových konverzacích s účtem       |  NoOfContactsInvolved_Emails             |
| Počet lidí z účtu na schůzkách s vaší organizací                  |  NoOfAccountContactsInvolved_Meetings    |
| Počet lidí z účtu v e-mailových konverzacích s vaší organizací       |  NoOfAccountContactsInvolved_Emails      |
| Počáteční datum zapojení (první e-mail nebo schůzka v datech)                        |  EngagementStartDate                     |
| Počet dnů od posledního e-mailu                                                             |  DaysSinceLastEmail                      |
| Počet dnů od poslední schůzky                                                           |  DaysSinceLastMeeting                    |
| Průměrná délka schůzek                                                      |  AverageDuration_Of_Meetings             |
| Průměrná doba trvání e-mailových odpovědí z účtu                                    |  AverageDuration_Of_AccountEmailReplies  |
| Počáteční datum agregace                                                            |  AggregationStartDate                    |
| Úroveň agregace (rok, měsíc nebo týden)                                          |  AggregationLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Zobrazení rozšíření dat na kartě zákazníka

Zapojení účtu lze také zobrazit na kartách jednotlivých zákazníků. Jděte na **Zákazníci** a vyberte profil zákazníka. Na kartě zákazníka najdete skóre zapojení účtu, celkový počet e-mailů a celkový počet schůzek agregovaných za poslední rok. Najdete zde také grafy, které ukazují historii e-mailů a schůzek.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Karta zákazníka s rozšířenými daty.":::

## <a name="next-steps"></a>Další kroky

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Například segment, který obsahuje všechny zákazníky, kteří mají hodnotu vyšší než 60 pro *dní od posledního e-mailu* a *dní od poslední schůzky*. Tento segment obsahuje zastaralé účty, které se můžete pokusit znovu aktivovat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
