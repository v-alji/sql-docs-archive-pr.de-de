---
title: Filtereinstellungen (Objekt-Explorer und Hilfsprogramm-Explorer) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607503"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="bfc07-102">Filtereinstellungen (Objekt-Explorer und Hilfsprogramm-Explorer)</span><span class="sxs-lookup"><span data-stu-id="bfc07-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="bfc07-103">Mithilfe dieses Dialogfelds können Sie einen Filter angeben.</span><span class="sxs-lookup"><span data-stu-id="bfc07-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="bfc07-104">Mit einem Filter können Sie Objekt-Explorer und Hilfsprogramm-Explorer so konfigurieren, dass nur Elemente angezeigt werden, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="bfc07-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="bfc07-105">So können Sie mit einem Filter beispielsweise nur Aufträge mit Namen anzeigen lassen, die das Wort "Wartung" enthalten.</span><span class="sxs-lookup"><span data-stu-id="bfc07-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="bfc07-106">Die Kopfzeile für das Dialogfeld **Filtereinstellungen** enthält den Namen des Servers und kann den Namen der Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="bfc07-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="bfc07-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="bfc07-107">UI element list</span></span>  
 <span data-ttu-id="bfc07-108">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="bfc07-108">**Property**</span></span>  
 <span data-ttu-id="bfc07-109">Zeigt die Eigenschaft an, nach der gefiltert werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfc07-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="bfc07-110">**Operator**</span><span class="sxs-lookup"><span data-stu-id="bfc07-110">**Operator**</span></span>  
 <span data-ttu-id="bfc07-111">Wählen Sie die Art aus, in der der Filter den Wert auf die Eigenschaft anwendet.</span><span class="sxs-lookup"><span data-stu-id="bfc07-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="bfc07-112">Folgende Optionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bfc07-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="bfc07-113">**Ist gleich**</span><span class="sxs-lookup"><span data-stu-id="bfc07-113">**Equals**</span></span>  
  
     <span data-ttu-id="bfc07-114">Der Filter zeigt Elemente an, bei denen die Eigenschaft und der Wert genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="bfc07-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="bfc07-115">**Contains**</span><span class="sxs-lookup"><span data-stu-id="bfc07-115">**Contains**</span></span>  
  
     <span data-ttu-id="bfc07-116">Der Filter zeigt die Elemente an, bei denen die Eigenschaft den Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="bfc07-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="bfc07-117">Die Eigenschaft kann noch weiteren Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="bfc07-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="bfc07-118">**Enthält nicht**</span><span class="sxs-lookup"><span data-stu-id="bfc07-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="bfc07-119">Der Filter zeigt die Elemente an, bei denen die Eigenschaft den Wert nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="bfc07-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="bfc07-120">**Kleiner als**</span><span class="sxs-lookup"><span data-stu-id="bfc07-120">**Less than**</span></span>  
  
     <span data-ttu-id="bfc07-121">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum vor dem eingegebenen Wert liegt.</span><span class="sxs-lookup"><span data-stu-id="bfc07-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="bfc07-122">**Kleiner oder gleich**</span><span class="sxs-lookup"><span data-stu-id="bfc07-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="bfc07-123">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum vor dem eingegebenen Wert liegt bzw. genau dem Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="bfc07-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="bfc07-124">**Größer als**</span><span class="sxs-lookup"><span data-stu-id="bfc07-124">**Greater than**</span></span>  
  
     <span data-ttu-id="bfc07-125">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum nach dem eingegebenen Wert liegt.</span><span class="sxs-lookup"><span data-stu-id="bfc07-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="bfc07-126">**Größer oder gleich**</span><span class="sxs-lookup"><span data-stu-id="bfc07-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="bfc07-127">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum nach dem eingegebenen Wert liegt bzw. genau dem Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="bfc07-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="bfc07-128">**Zwischen**</span><span class="sxs-lookup"><span data-stu-id="bfc07-128">**Between**</span></span>  
  
     <span data-ttu-id="bfc07-129">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum zwischen den eingegebenen Datumsangaben liegt.</span><span class="sxs-lookup"><span data-stu-id="bfc07-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="bfc07-130">Wählen Sie **Zwischen** aus, und drücken Sie TAB, um eine weitere Zeile für die Eingabe des zweiten Datums hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bfc07-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="bfc07-131">**Nicht zwischen**</span><span class="sxs-lookup"><span data-stu-id="bfc07-131">**Not between**</span></span>  
  
     <span data-ttu-id="bfc07-132">Verfügbar für Datumsangaben. Dieser Filter zeigt Elemente an, deren Datum vor oder nach den beiden eingegebenen Datumsangaben liegt.</span><span class="sxs-lookup"><span data-stu-id="bfc07-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="bfc07-133">Wählen Sie **Nicht zwischen** aus, und fügen Sie der **Operator** -Spalte mit TAB eine neue Zeile für die Eingabe des zweiten Datums hinzu.</span><span class="sxs-lookup"><span data-stu-id="bfc07-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="bfc07-134">**Wert**</span><span class="sxs-lookup"><span data-stu-id="bfc07-134">**Value**</span></span>  
 <span data-ttu-id="bfc07-135">Geben Sie den Wert ein, mit dem die Eigenschaft verglichen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfc07-135">Type the value to compare to the property.</span></span> <span data-ttu-id="bfc07-136">Bei Datumsangaben klicken Sie auf den nach unten zeigenden Pfeil, um einen Kalender für die Auswahl des Datums anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bfc07-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="bfc07-137">**Filter löschen**</span><span class="sxs-lookup"><span data-stu-id="bfc07-137">**Clear Filter**</span></span>  
 <span data-ttu-id="bfc07-138">Entfernt alle aktuellen Filtereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bfc07-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc07-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfc07-139">See Also</span></span>  
 <span data-ttu-id="bfc07-140">[SQL Server Management Studio verwenden](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="bfc07-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="bfc07-141">Funktionen und Tasks im SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="bfc07-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
