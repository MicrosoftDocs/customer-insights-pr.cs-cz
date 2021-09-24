---
title: Aktivace předpřipravených sestav profilu
description: Jak vytvořit sestavy profilu připravené k okamžitému použití seskupené podle pohlaví, věku a kraje nebo oblasti původu.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486112"
---
# <a name="out-of-box-profile-reports"></a>Předpřipravené sestavy profilu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sestava je soubor vizualizací dat, které vám pomohou měřit a porozumět chování uživatelů. Připojením k přehledům o cílové skupině Customer Insights vám může přehled zapojení ukázat sestavu s informacemi o sjednocených profilech zákazníků. Tato sestava obsahuje počet profilů, které máte, seskupené podle pohlaví, věku a geografického umístění.

## <a name="prerequisites"></a>Požadavky

Prostředí přehledů o cílové skupině musí ukládat data v účtu Azure Data Lake Storage spravovaném zákazníkem.

Pokud používáte zkušební verzi funkce přehledů o cílové skupině nebo prostředí v datovém jezeru spravovaném Customer Insights, [kontaktujte nás](https://go.microsoft.com/fwlink/?linkid=2145734) pro pomoc.  


## <a name="enable-the-customer-profile-report"></a>Aktivace sestavy profilu zákazníka

Správce prostředí musí [propojit přehledy zapojení a přehledy cílových skupin](integrate-audience-insights-engagement-insights.md).

Po zadání podrobností o připojení může správce udělit přístup dalším lidem v organizaci, aby si mohli zprávu prohlédnout. Správce prostředí nastavující připojení má automaticky přístup k sestavě profilu zákazníka. 

Po dokončení připojení bude funkce **Profily** k dispozici v levém navigačním podokně. 

- Chcete-li zobrazit sestavu, přejděte na **Prozkoumat** > **Profily**.

Sestava **Profily** obsahuje vizualizace o pohlaví, věku a geografickém umístění připojených profilů zákazníků.

:::image type="content" source="media/customer-profiles.png" alt-text="Sestava profilu zákazníka.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]