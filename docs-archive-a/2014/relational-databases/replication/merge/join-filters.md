---
title: Verknüpfungsfilter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607692"
---
# <a name="join-filters"></a><span data-ttu-id="534d1-102">Verknüpfungsfilter</span><span class="sxs-lookup"><span data-stu-id="534d1-102">Join Filters</span></span>
  <span data-ttu-id="534d1-103">Durch einen Joinfilter kann eine Tabelle auf der Grundlage der Filterkriterien einer verknüpften Tabelle in der Veröffentlichung gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="534d1-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="534d1-104">In der Regel wird eine übergeordnete Tabelle mithilfe eines parametrisierten Filters gefiltert. Anschließend werden ein oder mehrere Joinfilter auf dieselbe Weise definiert, wie Sie einen Join zwischen Tabellen definieren.</span><span class="sxs-lookup"><span data-stu-id="534d1-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="534d1-105">Die Joinfilter erweitern den parametrisierten Filter so, dass die Daten in den zugehörigen Tabellen nur dann repliziert werden, wenn sie der Joinfilterklausel entsprechen.</span><span class="sxs-lookup"><span data-stu-id="534d1-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="534d1-106">Joinfilter folgen normalerweise den Beziehungen zwischen Primär- und Fremdschlüssel, die für die Tabellen, auf die sie angewendet werden, definiert wurden. Sie sind jedoch nicht streng auf diese Primär-/Fremdschlüssel-Beziehungen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="534d1-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="534d1-107">Joinfilter können auf jeder Logik basieren, die miteinander in Beziehung stehende Daten in zwei Tabellen vergleicht.</span><span class="sxs-lookup"><span data-stu-id="534d1-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="534d1-108">Nehmen wir als Beispiel die folgenden Tabellen in der [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] -Beispieldatenbank, die durch eine Primärschlüssel/Fremdschlüssel-Beziehung miteinander verbunden sind:</span><span class="sxs-lookup"><span data-stu-id="534d1-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="534d1-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="534d1-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="534d1-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="534d1-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="534d1-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="534d1-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="534d1-112">Diese Tabellen könnten in einer Anwendung zur Unterstützung mobiler Außendienstmitarbeiter verwendet werden, müssen dabei aber gefiltert werden, damit jeder Mitarbeiter in der **HumanResources.Employee** -Tabelle nur die für die Aufträge seiner Kunden relevanten Daten erhält.</span><span class="sxs-lookup"><span data-stu-id="534d1-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="534d1-113">Dafür muss als Erstes ein parametrisierter Filter für die übergeordnete Tabelle definiert werden. In diesem Beispiel ist dies die **HumanResources.Employee** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="534d1-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="534d1-114">Diese Tabelle enthält die **LoginID**-Spalte, in der Sie die Domäne und den Anmeldenamen (Anmelde-ID) für jeden Mitarbeiter in der Form *domain\login*finden.</span><span class="sxs-lookup"><span data-stu-id="534d1-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="534d1-115">Wenn Sie diese Tabelle so filtern möchten, dass jeder Mitarbeiter nur die Daten erhält, die für ihn relevant sind, geben Sie folgende parametrisierte Filterklausel an:</span><span class="sxs-lookup"><span data-stu-id="534d1-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="534d1-116">Dieser Filter stellt sicher, dass das Abonnement des jeweiligen Mitarbeiters nur die Daten aus der **HumanResources.Employee** -Tabelle enthält, die für ihn relevant sind (in diesem Fall also nur eine einzelne Zeile).</span><span class="sxs-lookup"><span data-stu-id="534d1-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="534d1-117">Weitere Informationen zu parametrisierten Zeilenfiltern finden Sie unter [Parametrisierte Zeilenfilter](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="534d1-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="534d1-118">Als Nächstes wird dieser Filter auf jede einzelne der zugehörigen Tabellen erweitert. Die dazu verwendete Syntax ähnelt derjenigen, mit der Sie einen Join zwischen zwei Tabellen angeben können.</span><span class="sxs-lookup"><span data-stu-id="534d1-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="534d1-119">Die erste Joinfilterklausel lautet:</span><span class="sxs-lookup"><span data-stu-id="534d1-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="534d1-120">Diese Klausel stellt sicher, dass das Abonnement nur die Auftragsdaten enthält, die für den betreffenden Außendienstmitarbeiter relevant sind.</span><span class="sxs-lookup"><span data-stu-id="534d1-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="534d1-121">Die zweite Joinfilterklausel lautet:</span><span class="sxs-lookup"><span data-stu-id="534d1-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="534d1-122">Diese Klausel stellt sicher, dass das Abonnement nur die den Auftragsdaten zugehörigen Detaildaten des betreffenden Außendienstmitarbeiters enthält.</span><span class="sxs-lookup"><span data-stu-id="534d1-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="534d1-123">Dieses Beispiel zeigt eine Einzeltabelle, die an jedem Punkt verknüpft ist. Es ist aber auch möglich, an jedem Punkt mehrere Tabellen zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="534d1-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="534d1-124">Joinfilter können jeweils einzeln im Assistenten für neue Veröffentlichung und im Dialogfeld **Veröffentlichungseigenschaften** oder aber programmgesteuert hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="534d1-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="534d1-125">Außerdem können Joinfilter über den Assistenten für neue Veröffentlichung automatisch generiert werden: Geben Sie dazu einen Zeilenfilter für eine Tabelle an, und die Joinfilter werden auf alle entsprechenden Tabellen angewendet.</span><span class="sxs-lookup"><span data-stu-id="534d1-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="534d1-126">Weitere Informationen finden Sie unter [Definieren und Ändern eines Verknüpfungsfilters zwischen Mergeartikeln](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41; (Automatische Generierung eines Satzes von Verknüpfungsfiltern zwischen Mergeartikeln (SQL Server Management Studio))](../publish/automatically-generate-join-filters-between-merge-articles.md) und [Define an Article (Definieren eines Artikels)](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="534d1-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="534d1-127">Optimieren der Joinfilterleistung</span><span class="sxs-lookup"><span data-stu-id="534d1-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="534d1-128">Zur Optimierung der Leistung der Joinfilter sollten Sie die folgenden Hinweise beachten:</span><span class="sxs-lookup"><span data-stu-id="534d1-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="534d1-129">Begrenzen Sie die Anzahl der Tabellen in der Joinsfilterhierarchie.</span><span class="sxs-lookup"><span data-stu-id="534d1-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="534d1-130">Joinfilter können zwar eine unbegrenzte Anzahl von Tabellen enthalten, Filter mit einer großen Tabellenanzahl wirken sich aber möglicherweise deutlich negativ auf die Leistung bei der Mergeverarbeitung aus.</span><span class="sxs-lookup"><span data-stu-id="534d1-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="534d1-131">Wenn Sie Joinsfilter für fünf oder mehr Tabellen erstellen, sollten Sie andere Lösungen in Betracht ziehen: Kleinere Tabellen, Tabellen, die nicht geändert werden, oder Tabellen, bei denen es sich primär um Nachschlagetabellen handelt, sollten in diesem Fall nicht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="534d1-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="534d1-132">Verwenden Sie Joinsfilter nur zwischen Tabellen, für die eine Partitionierung auf Abonnements erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="534d1-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="534d1-133">Legen Sie, sofern zutreffend, für **join unique key** den Wert **True** fest.</span><span class="sxs-lookup"><span data-stu-id="534d1-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="534d1-134">Im Mergeprozess sind besondere Leistungsoptimierungsmöglichkeiten verfügbar, wenn die verknüpfte Spalte in der übergeordneten Tabelle eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="534d1-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="534d1-135">Wenn die Joinbedingung auf einer eindeutigen Spalte basiert, aktivieren Sie die Option **join unique key** für den Joinfilter.</span><span class="sxs-lookup"><span data-stu-id="534d1-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="534d1-136">Informationen zum Festlegen dieser Option finden Sie in den im vorhergehenden Abschnitt genannten Vorgehensweise-Themen.</span><span class="sxs-lookup"><span data-stu-id="534d1-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="534d1-137">Stellen Sie sicher, dass die Spalten, auf die in den Joinfiltern verwiesen wird, indiziert sind.</span><span class="sxs-lookup"><span data-stu-id="534d1-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="534d1-138">Wenn die Spalten, auf die im Filter verwiesen wird, indiziert sind, kann die Replikation die Filter effizienter verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="534d1-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="534d1-139">Erstellen Sie keine Zeilenfilter, die sich wie Joinfilter verhalten.</span><span class="sxs-lookup"><span data-stu-id="534d1-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="534d1-140">Mithilfe einer Unterabfrage in einer WHERE-Klausel ist es möglich, Zeilenfilter zu erstellen, die sich wie Joinfilter verhalten:</span><span class="sxs-lookup"><span data-stu-id="534d1-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="534d1-141">Es wird dringend empfohlen, eine solche Logik statt in einer Unterabfrage in einem Joinfilter auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="534d1-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="534d1-142">Wenn Ihre Anwendung für die Verwendung einer Unterabfrage einen Zeilenfilter benötigt, stellen Sie sicher, dass die Unterabfrage ausschließlich Daten in der Nachschlagetabelle referenziert, die sich nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="534d1-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534d1-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="534d1-143">See Also</span></span>  
 <span data-ttu-id="534d1-144">[Filtern von veröffentlichten Daten für die Mergereplikation](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="534d1-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="534d1-145">Parametrisierte Zeilenfilter</span><span class="sxs-lookup"><span data-stu-id="534d1-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
