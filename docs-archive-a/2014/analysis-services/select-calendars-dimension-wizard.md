---
title: Kalender auswählen (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.serverSpecialCalendars.f1
ms.assetid: 6e28a020-2586-4b13-9333-b499fb1b33af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2048ee20dd91c942f01982d02f3265a6bad670dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618922"
---
# <a name="select-calendars-dimension-wizard"></a><span data-ttu-id="4300e-102">Kalender auswählen (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="4300e-102">Select Calendars (Dimension Wizard)</span></span>
  <span data-ttu-id="4300e-103">Auf der Seite **Kalender auswählen** können Sie für eine gegebene Zeitdimension zusätzliche Hierarchien zur Darstellung von Geschäfts-, Berichts-, Produktions- oder ISO 8601-Kalendern (International Organization for Standardization, Internationale Organisation für Normung) erstellen.</span><span class="sxs-lookup"><span data-stu-id="4300e-103">Use the **Select Calendars** page to create additional hierarchies representing fiscal, reporting, manufacturing, or International Standards Organization (ISO) 8601 calendars for the time dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-104"> Diese Seite wird nur angezeigt, wenn auf der Seite **Dimensionstyp auswählen** die Option **Serverzeitdimension** oder auf der Seite **Erstellungsmethode auswählen** die Option **Dimension ohne eine Datenquelle erstellen** und auf der Seite **Dimensionstyp auswählen** die Option **Zeitdimension** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="4300e-104">This page will appear only if you have selected **Server time dimension** on the **Select the Dimension Type** page, or if you selected **Build the dimension without using a data source** on the **Dimension Definition** page and selected **Time dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4300e-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4300e-105">Options</span></span>  
 <span data-ttu-id="4300e-106">**Geschäftskalender**</span><span class="sxs-lookup"><span data-stu-id="4300e-106">**Fiscal calendar**</span></span>  
 <span data-ttu-id="4300e-107">Wählen Sie diese Option aus, um eine Zeithierarchie basierend auf einem Geschäftskalender zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4300e-107">Select to create a time hierarchy based on a fiscal calendar.</span></span>  
  
 <span data-ttu-id="4300e-108">**Starttag und -monat**</span><span class="sxs-lookup"><span data-stu-id="4300e-108">**Start day and month**</span></span>  
 <span data-ttu-id="4300e-109">Wählen Sie Tag und Monat für den Beginn des Geschäftskalenders aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-109">Select the day and month on which the fiscal calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-110"> Diese Option ist nur bei Auswahl von **Geschäftskalender** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-110">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-111">**Benennungskonvention für Geschäftskalender**</span><span class="sxs-lookup"><span data-stu-id="4300e-111">**Fiscal calendar naming convention**</span></span>  
 <span data-ttu-id="4300e-112">Wählen Sie eine Benennungskonvention für den Geschäftskalender aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-112">Select the naming convention used by the fiscal calendar.</span></span> <span data-ttu-id="4300e-113">Wählen Sie entweder **Kalenderjahrname** oder **Kalenderjahrname +1**aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-113">Select either **Calendar year name** or **Calendar year name +1**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-114"> Diese Option ist nur bei Auswahl von **Geschäftskalender** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-114">This option is available only when **Fiscal calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-115">**Berichtskalender (oder Marketingkalender)**</span><span class="sxs-lookup"><span data-stu-id="4300e-115">**Reporting (or marketing) calendar**</span></span>  
 <span data-ttu-id="4300e-116">Wählen Sie diese Option aus, um eine Zeithierarchie basierend auf einem Berichtskalender zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4300e-116">Select to create a time hierarchy based on a reporting calendar.</span></span>  
  
 <span data-ttu-id="4300e-117">**Startwoche und -monat**</span><span class="sxs-lookup"><span data-stu-id="4300e-117">**Start week and month**</span></span>  
 <span data-ttu-id="4300e-118">Wählen Sie Woche und Monat für den Beginn des Berichtskalenders aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-118">Select the week and month on which the reporting calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-119">Diese Option ist nur bei Auswahl von **Berichtskalender (oder Marketingkalender)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-119">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-120">**Muster: Woche nach Monat**</span><span class="sxs-lookup"><span data-stu-id="4300e-120">**Week by month pattern**</span></span>  
 <span data-ttu-id="4300e-121">Wählen Sie das Muster Woche nach Monat für den Berichtskalender aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-121">Select the week by month pattern used by the reporting calendar.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-122">Diese Option ist nur bei Auswahl von **Berichtskalender (oder Marketingkalender)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-122">This option is available when **Reporting (or marketing) calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-123">In der folgenden Tabelle werden die für das Muster Woche nach Monat verfügbaren Optionen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4300e-123">The following table lists the options available for the week by month pattern.</span></span>  
  
|<span data-ttu-id="4300e-124">Wert</span><span class="sxs-lookup"><span data-stu-id="4300e-124">Value</span></span>|<span data-ttu-id="4300e-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4300e-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4300e-126">**Woche 445**</span><span class="sxs-lookup"><span data-stu-id="4300e-126">**Week 445**</span></span>|<span data-ttu-id="4300e-127">Der erste und zweite Monat im Quartal haben jeweils vier Wochen, während der dritte Monat im Quartal fünf Wochen hat.</span><span class="sxs-lookup"><span data-stu-id="4300e-127">The first month in the quarter has 4 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 5 weeks.</span></span>|  
|<span data-ttu-id="4300e-128">**Woche 454**</span><span class="sxs-lookup"><span data-stu-id="4300e-128">**Week 454**</span></span>|<span data-ttu-id="4300e-129">Der erste und dritte Monat im Quartal haben jeweils vier Wochen, während der zweite Monat im Quartal fünf Wochen hat.</span><span class="sxs-lookup"><span data-stu-id="4300e-129">The first month in the quarter has 4 weeks, the second month in the quarter has 5 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
|<span data-ttu-id="4300e-130">**Woche 544**</span><span class="sxs-lookup"><span data-stu-id="4300e-130">**Week 544**</span></span>|<span data-ttu-id="4300e-131">Der erste Monat im Quartal hat 5 Wochen, während der zweite und dritte Monat im Quartal jeweils vier Wochen haben.</span><span class="sxs-lookup"><span data-stu-id="4300e-131">The first month in the quarter has 5 weeks, the second month in the quarter has 4 weeks, and the third month in the quarter has 4 weeks.</span></span>|  
  
 <span data-ttu-id="4300e-132">**Produktionskalender**</span><span class="sxs-lookup"><span data-stu-id="4300e-132">**Manufacturing calendar**</span></span>  
 <span data-ttu-id="4300e-133">Wählen Sie diese Option aus, um eine Zeithierarchie basierend auf einem Produktionskalender zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4300e-133">Select to create a time hierarchy based on a manufacturing calendar.</span></span>  
  
 <span data-ttu-id="4300e-134">**Startwoche und -monat**</span><span class="sxs-lookup"><span data-stu-id="4300e-134">**Start week and month**</span></span>  
 <span data-ttu-id="4300e-135">Wählen Sie Woche und Monat für den Beginn des Produktionskalenders aus.</span><span class="sxs-lookup"><span data-stu-id="4300e-135">Select the week and month on which the manufacturing calendar begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-136"> Diese Option ist nur bei Auswahl von **Produktionskalender** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-136">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-137">**Quartal mit zusätzlichen Zeiträumen**</span><span class="sxs-lookup"><span data-stu-id="4300e-137">**Quarter with extra periods**</span></span>  
 <span data-ttu-id="4300e-138">Wählen Sie das Quartal mit den zusätzlichen Zeiträumen aus, oder geben Sie ein entsprechendes Quartal ein.</span><span class="sxs-lookup"><span data-stu-id="4300e-138">Select or type the quarter that will contain the extra periods.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4300e-139"> Diese Option ist nur bei Auswahl von **Produktionskalender** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4300e-139">This option is available when **Manufacturing calendar** is selected.</span></span>  
  
 <span data-ttu-id="4300e-140">**ISO 8601-Kalender**</span><span class="sxs-lookup"><span data-stu-id="4300e-140">**ISO 8601 calendar**</span></span>  
 <span data-ttu-id="4300e-141">Wählen Sie diese Option aus, um eine Hierarchie basierend auf einem ISO 8601-Kalender zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4300e-141">Select to create a hierarchy based on the ISO 8601 calendar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4300e-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4300e-142">See Also</span></span>  
 <span data-ttu-id="4300e-143">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4300e-143">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="4300e-144">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4300e-144">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4300e-145">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="4300e-145">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
