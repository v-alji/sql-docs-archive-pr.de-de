---
title: Zeiträume definieren (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.timefrequency.f1
ms.assetid: 6bda6b7e-d306-4e68-9acb-84de8f44d1b4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88b69eaa265b7a98f7d32063b602897d02016fa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621729"
---
# <a name="define-time-periods-dimension-wizard"></a><span data-ttu-id="b7c47-102">Zeiträume definieren (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="b7c47-102">Define Time Periods (Dimension Wizard)</span></span>
  <span data-ttu-id="b7c47-103">Auf der Seite **Zeiträume definieren** können Sie Informationen zum Kalenderjahr sowie Zeithäufigkeiten für die Zeitdimension oder die Serverzeitdimension definieren.</span><span class="sxs-lookup"><span data-stu-id="b7c47-103">Use the **Define Time Periods** page to define the calendar year information and time frequencies to include in the time dimension or server time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7c47-104"> Diese Seite wird nur angezeigt, wenn Sie auf der Seite **Dimensionstyp auswählen** die Option **Serverzeitdimension** ausgewählt haben, oder wenn Sie auf der Seite **Erstellungsmethode auswählen** die Option **Dimension ohne eine Datenquelle erstellen** und auf der Seite **Dimensionstyp auswählen** die Option **Zeitdimension** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b7c47-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Select Build Method** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7c47-105">Auf dieser Seite können Sie das Kalenderjahr für eine Zeitdimension definieren.</span><span class="sxs-lookup"><span data-stu-id="b7c47-105">This page is for defining the calendar year of a time dimension.</span></span> <span data-ttu-id="b7c47-106">Auf der Seite **Kalender auswählen** können Sie für die Zeitdimension ein Geschäfts-, Produktions-, Berichts- oder ISO 8601-Jahr definieren.</span><span class="sxs-lookup"><span data-stu-id="b7c47-106">To define a fiscal, manufacturing, reporting, or International Standards Organization (ISO) 8601 year for the time dimension, use the **Select Calendars** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b7c47-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b7c47-107">Options</span></span>  
 <span data-ttu-id="b7c47-108">**Erster Kalendertag**</span><span class="sxs-lookup"><span data-stu-id="b7c47-108">**First calendar day**</span></span>  
 <span data-ttu-id="b7c47-109">Geben Sie den ersten Tag des aktuellen Jahres ein, oder wählen Sie den Tag aus.</span><span class="sxs-lookup"><span data-stu-id="b7c47-109">Type or select the day that begins the current year.</span></span>  
  
 <span data-ttu-id="b7c47-110">**Letzter Kalendertag**</span><span class="sxs-lookup"><span data-stu-id="b7c47-110">**Last calendar day**</span></span>  
 <span data-ttu-id="b7c47-111">Geben Sie den letzten Tag des aktuellen Jahres ein, oder wählen Sie den Tag aus.</span><span class="sxs-lookup"><span data-stu-id="b7c47-111">Type or select the day that ends the current year.</span></span>  
  
 <span data-ttu-id="b7c47-112">**Erster Tag der Woche**</span><span class="sxs-lookup"><span data-stu-id="b7c47-112">**First day of the week**</span></span>  
 <span data-ttu-id="b7c47-113">Wählen Sie den ersten Tag der Woche aus.</span><span class="sxs-lookup"><span data-stu-id="b7c47-113">Select the day that begins a week.</span></span>  
  
 <span data-ttu-id="b7c47-114">**Zeiträume**</span><span class="sxs-lookup"><span data-stu-id="b7c47-114">**Time periods**</span></span>  
 <span data-ttu-id="b7c47-115">Wählen Sie die Zeiträume für das Kalenderjahr der Zeitdimension aus.</span><span class="sxs-lookup"><span data-stu-id="b7c47-115">Select the time periods for the calendar year of the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7c47-116">Der Zeitraum `Date` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7c47-116">The `Date` time period is required.</span></span>  
  
 <span data-ttu-id="b7c47-117">**Sprache für die Namen der Zeitelemente**</span><span class="sxs-lookup"><span data-stu-id="b7c47-117">**Language for time member names**</span></span>  
 <span data-ttu-id="b7c47-118">Wählen Sie die Sprache für die Elemente der Zeitdimension aus.</span><span class="sxs-lookup"><span data-stu-id="b7c47-118">Select the language for the members in the time dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c47-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7c47-119">See Also</span></span>  
 <span data-ttu-id="b7c47-120">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b7c47-120">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="b7c47-121">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b7c47-121">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="b7c47-122">[Dimensionen in mehrdimensionalen Modellen](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b7c47-122">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="b7c47-123">Kalender &#40;Dimensions-Assistenten auswählen&#41;</span><span class="sxs-lookup"><span data-stu-id="b7c47-123">Select Calendars &#40;Dimension Wizard&#41;</span></span>](select-calendars-dimension-wizard.md)  
  
  
