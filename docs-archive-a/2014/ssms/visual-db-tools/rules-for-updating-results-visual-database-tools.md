---
title: Regeln zum Aktualisieren von Ergebnissen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- updating query results
- Query Designer [SQL Server], Results pane
- Results pane
ms.assetid: de131ef0-ccbd-446f-9400-b93c7b8fa537
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc6befc6571f29be95b176f8de6d7dcfaed9108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719339"
---
# <a name="rules-for-updating-results-visual-database-tools"></a><span data-ttu-id="86775-102">Regeln zum Aktualisieren von Ergebnissen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="86775-102">Rules for Updating Results (Visual Database Tools)</span></span>
  <span data-ttu-id="86775-103">In vielen Fällen können Sie das im [Ergebnisbereich](visual-database-tools.md)angezeigte Resultset aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="86775-103">In many cases, you can update the result set displayed in the [Results Pane](visual-database-tools.md).</span></span> <span data-ttu-id="86775-104">Manchmal ist dies allerdings nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="86775-104">However, in some cases you cannot.</span></span>  
  
 <span data-ttu-id="86775-105">Damit Ergebnisse aktualisiert werden können, muss der [Abfrage- und Sicht-Designer](query-and-view-designer-tools-visual-database-tools.md) über genügend Informationen verfügen, um die Zeile in der Tabelle eindeutig identifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="86775-105">In general, in order to update results, the [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) must have sufficient information to uniquely identify the row in the table.</span></span> <span data-ttu-id="86775-106">Ein Beispiel ist der Fall, dass die Abfrage einen Primärschlüssel in die Ausgabeliste einfügt.</span><span class="sxs-lookup"><span data-stu-id="86775-106">An example is if the query includes a primary key in the output list.</span></span> <span data-ttu-id="86775-107">Außerdem müssen Sie über eine ausreichende Berechtigung zum Update der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="86775-107">In addition, you must have sufficient permission to update the database.</span></span>  
  
 <span data-ttu-id="86775-108">Wenn die Abfrage auf einer Sicht basiert, kann sie aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="86775-108">If your query is based on a view, you might be able to update it.</span></span> <span data-ttu-id="86775-109">Dieselben Richtlinien werden angewendet, allerdings nicht nur auf die Sicht selbst, sondern auf die zugrunde liegenden Tabellen in der Sicht.</span><span class="sxs-lookup"><span data-stu-id="86775-109">The same guidelines apply, except that they apply to the underlying tables in the view, not just to the view itself.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86775-110">Der Abfrage- und Sicht-Designer kann nicht im Voraus ermitteln, ob Sie ein auf einer Sicht basierendes Resultset aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="86775-110">The Query and View Designer cannot determine in advance whether you can update a result set based on a view.</span></span> <span data-ttu-id="86775-111">Daher werden alle Sichten angezeigt, obwohl Sie diese möglicherweise nicht aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="86775-111">Therefore, it displays all views, even though you might not be able to update them.</span></span>  
  
 <span data-ttu-id="86775-112">Die folgende Tabelle gibt eine Übersicht über die einzelnen Fälle, in denen Sie Abfrageergebnisse im Ergebnisbereich aktualisieren bzw. nicht aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="86775-112">The following table summarizes specific instances in which you might and might not be able to update query results in the Results pane.</span></span> <span data-ttu-id="86775-113">Häufig wird durch die verwendete Datenbank bestimmt, ob die Ergebnisse einer Abfrage aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="86775-113">In many cases, the database you are using dictates whether you can update query results.</span></span>  
  
|<span data-ttu-id="86775-114">Abfrage</span><span class="sxs-lookup"><span data-stu-id="86775-114">Query</span></span>|<span data-ttu-id="86775-115">Können die Ergebnisse aktualisiert werden?</span><span class="sxs-lookup"><span data-stu-id="86775-115">Can results be updated?</span></span>|  
|-----------|-----------------------------|  
|<span data-ttu-id="86775-116">Abfrage auf Grundlage einer Tabelle mit Primärschlüssel in der Ausgabeliste</span><span class="sxs-lookup"><span data-stu-id="86775-116">Query based on one table with primary key in the output list</span></span>|<span data-ttu-id="86775-117">Ja (außer wie im Folgenden aufgeführt).</span><span class="sxs-lookup"><span data-stu-id="86775-117">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="86775-118">Abfrage auf Grundlage einer Tabelle ohne eindeutigen Index und Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="86775-118">Query based on a table with no unique index and without a primary key</span></span>|<span data-ttu-id="86775-119">Hängt von der Abfrage und der Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="86775-119">Depends on query and database.</span></span> <span data-ttu-id="86775-120">Einige Datenbanken lassen Updates zu, wenn genügend Informationen zur eindeutigen Identifizierung von Datensätzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="86775-120">Some databases allow updates if sufficient information is available to uniquely identify records.</span></span>|  
|<span data-ttu-id="86775-121">Abfrage auf Grundlage mehrerer Tabellen, die nicht verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="86775-121">Query based on multiple tables which are not joined</span></span>|<span data-ttu-id="86775-122">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-122">No.</span></span>|  
|<span data-ttu-id="86775-123">Abfrage auf Grundlage von als schreibgeschützt markierten Daten der Datenbank</span><span class="sxs-lookup"><span data-stu-id="86775-123">Query based on data marked as read-only in the database</span></span>|<span data-ttu-id="86775-124">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-124">No.</span></span>|  
|<span data-ttu-id="86775-125">Abfrage auf Grundlage einer Sicht, die eine Tabelle ohne Einschränkungen umfasst</span><span class="sxs-lookup"><span data-stu-id="86775-125">Query based on a view that involves one table with no constraints</span></span>|<span data-ttu-id="86775-126">Ja (außer wie im Folgenden aufgeführt).</span><span class="sxs-lookup"><span data-stu-id="86775-126">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="86775-127">Abfrage auf Grundlage von Tabellen, die über eine 1:1-Beziehung verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="86775-127">Query based on tables joined with a one-to-one relationship</span></span>|<span data-ttu-id="86775-128">Ja (außer wie im Folgenden aufgeführt).</span><span class="sxs-lookup"><span data-stu-id="86775-128">Yes (except as listed below).</span></span>|  
|<span data-ttu-id="86775-129">Abfrage auf Grundlage von Tabellen, die über eine 1:n-Beziehung verknüpft sind</span><span class="sxs-lookup"><span data-stu-id="86775-129">Query based on tables joined with a one-to-many relationship</span></span>|<span data-ttu-id="86775-130">Meistens.</span><span class="sxs-lookup"><span data-stu-id="86775-130">Usually.</span></span>|  
|<span data-ttu-id="86775-131">Abfrage auf Grundlage von drei oder mehr Tabellen, bei denen eine m:n-Beziehung vorliegt</span><span class="sxs-lookup"><span data-stu-id="86775-131">Query based on three or more tables in which there is a many-to-many relationship</span></span>|<span data-ttu-id="86775-132">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-132">No.</span></span>|  
|<span data-ttu-id="86775-133">Abfrage auf Grundlage einer Tabelle, für die keine Updateberechtigung vorliegt</span><span class="sxs-lookup"><span data-stu-id="86775-133">Query based on a table for which update permission is not granted</span></span>|<span data-ttu-id="86775-134">Kann gelöscht, aber nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="86775-134">Can delete but not update.</span></span>|  
|<span data-ttu-id="86775-135">Abfrage auf Grundlage einer Tabelle, für die keine Löschberechtigung vorliegt</span><span class="sxs-lookup"><span data-stu-id="86775-135">Query based on a table for which delete permission is not granted</span></span>|<span data-ttu-id="86775-136">Kann aktualisiert, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="86775-136">Can update but not delete.</span></span>|  
|<span data-ttu-id="86775-137">Aggregatabfrage</span><span class="sxs-lookup"><span data-stu-id="86775-137">Aggregate query</span></span>|<span data-ttu-id="86775-138">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-138">No.</span></span>|  
|<span data-ttu-id="86775-139">Abfrage auf Grundlage einer Unterabfrage, die Summen oder Aggregatfunktionen enthält</span><span class="sxs-lookup"><span data-stu-id="86775-139">Query based on a subquery that contains totals or aggregate functions</span></span>|<span data-ttu-id="86775-140">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-140">No.</span></span>|  
|<span data-ttu-id="86775-141">Abfrage, die das Schlüsselwort DISTINCT zum Ausschließen von doppelten Zeilen enthält</span><span class="sxs-lookup"><span data-stu-id="86775-141">Query that includes the DISTINCT keyword to exclude duplicate rows</span></span>|<span data-ttu-id="86775-142">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-142">No.</span></span>|  
|<span data-ttu-id="86775-143">Abfrage, deren FROM-Klausel eine benutzerdefinierte Funktion enthält, die eine Tabelle zurückgibt, wobei diese Funktion mehrere SELECT-Anweisungen enthält</span><span class="sxs-lookup"><span data-stu-id="86775-143">Query whose FROM clause includes a user-defined function that returns a table and the user-defined function contains multiple select statements</span></span>|<span data-ttu-id="86775-144">Nein.</span><span class="sxs-lookup"><span data-stu-id="86775-144">No.</span></span>|  
|<span data-ttu-id="86775-145">Abfrage, deren FROM-Klausel eine benutzerdefinierte Inlinefunktion enthält</span><span class="sxs-lookup"><span data-stu-id="86775-145">Query whose FROM clause includes an inline user-defined function</span></span>|<span data-ttu-id="86775-146">Ja.</span><span class="sxs-lookup"><span data-stu-id="86775-146">Yes.</span></span>|  
  
 <span data-ttu-id="86775-147">Außerdem können Sie möglicherweise bestimmte Spalten in den Abfrageergebnissen nicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="86775-147">In addition, you might not be able to update specific columns in the query results.</span></span> <span data-ttu-id="86775-148">Im Folgenden sind bestimmte Spaltentypen aufgeführt, die Sie im Ergebnisbereich nicht aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="86775-148">The following list summarizes specific types of columns that you cannot update in the Results pane.</span></span>  
  
-   <span data-ttu-id="86775-149">Spalten, die auf Ausdrücken basieren</span><span class="sxs-lookup"><span data-stu-id="86775-149">Columns based on expressions</span></span>  
  
-   <span data-ttu-id="86775-150">Spalten, die auf benutzerdefinierten Skalarfunktionen basieren</span><span class="sxs-lookup"><span data-stu-id="86775-150">Columns based on scalar user-defined functions</span></span>  
  
-   <span data-ttu-id="86775-151">Zeilen oder Spalten, die von einem anderen Benutzer gelöscht wurden</span><span class="sxs-lookup"><span data-stu-id="86775-151">Rows or columns deleted by another user</span></span>  
  
-   <span data-ttu-id="86775-152">Zeilen oder Spalten, die von einem anderen Benutzer gesperrt wurden (gesperrte Zeilen können i. d. R. unmittelbar nach Aufhebung der Sperre aktualisiert werden)</span><span class="sxs-lookup"><span data-stu-id="86775-152">Rows or columns locked by another user (locked rows can usually be updated as soon as they are unlocked)</span></span>  
  
-   <span data-ttu-id="86775-153">Timestamp- oder BLOB-Spalten</span><span class="sxs-lookup"><span data-stu-id="86775-153">Timestamp or BLOB columns</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86775-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86775-154">See Also</span></span>  
 [<span data-ttu-id="86775-155">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="86775-155">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
