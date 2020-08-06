---
title: Hierarchische Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [SQL Server], tables to support
- hierarchyid [Database Engine], concepts
- hierarchical tables [Database Engine]
- SqlHierarchyId
- hierarchyid [Database Engine]
- hierarchical queries [SQL Server], using hierarchyid data type
ms.assetid: 19aefa9a-fbc2-4b22-92cf-67b8bb01671c
author: rothja
ms.author: jroth
ms.openlocfilehash: 351a5a4aa6bc1655b8da5fced3e51385dd498bdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616999"
---
# <a name="hierarchical-data-sql-server"></a><span data-ttu-id="526df-102">Hierarchische Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="526df-102">Hierarchical Data (SQL Server)</span></span>
  <span data-ttu-id="526df-103">Der integrierte `hierarchyid` Datentyp vereinfacht das Speichern und Abfragen hierarchischer Daten.</span><span class="sxs-lookup"><span data-stu-id="526df-103">The built-in `hierarchyid` data type makes it easier to store and query hierarchical data.</span></span> <span data-ttu-id="526df-104">`hierarchyid`ist für das darstellen von Strukturen optimiert, bei denen es sich um den gängigsten Typ hierarchischer Daten handelt.</span><span class="sxs-lookup"><span data-stu-id="526df-104">`hierarchyid` is optimized for representing trees, which are the most common type of hierarchical data.</span></span>  
  
 <span data-ttu-id="526df-105">Hierarchische Daten sind definiert als Satz von Datenelementen, die durch hierarchische Beziehungen miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="526df-105">Hierarchical data is defined as a set of data items that are related to each other by hierarchical relationships.</span></span> <span data-ttu-id="526df-106">Hierarchische Beziehungen sind vorhanden, wenn ein Datenelement einem anderen Element übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="526df-106">Hierarchical relationships exist where one item of data is the parent of another item.</span></span> <span data-ttu-id="526df-107">Beispiele für die hierarchischen Daten, die im Allgemeinen in Datenbanken gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="526df-107">Examples of the hierarchical data that is commonly stored in databases include the following:</span></span>  
  
-   <span data-ttu-id="526df-108">Eine Organisationsstruktur</span><span class="sxs-lookup"><span data-stu-id="526df-108">An organizational structure</span></span>  
  
-   <span data-ttu-id="526df-109">Ein Dateisystem</span><span class="sxs-lookup"><span data-stu-id="526df-109">A file system</span></span>  
  
-   <span data-ttu-id="526df-110">Eine Gruppe von Aufgaben in einem Projekt.</span><span class="sxs-lookup"><span data-stu-id="526df-110">A set of tasks in a project</span></span>  
  
-   <span data-ttu-id="526df-111">Eine Taxonomie sprachlicher Termini</span><span class="sxs-lookup"><span data-stu-id="526df-111">A taxonomy of language terms</span></span>  
  
-   <span data-ttu-id="526df-112">Ein Diagramm der Links zwischen Webseiten</span><span class="sxs-lookup"><span data-stu-id="526df-112">A graph of links between Web pages</span></span>  
  
 <span data-ttu-id="526df-113">Mit dem Datentyp [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) können Sie Tabellen mit einer hierarchischen Struktur erstellen oder die hierarchische Struktur der Daten an einem anderen Speicherort beschreiben.</span><span class="sxs-lookup"><span data-stu-id="526df-113">Use [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) as a data type to create tables with a hierarchical structure, or to describe the hierarchical structure of data that is stored in another location.</span></span> <span data-ttu-id="526df-114">Verwenden Sie die [hierarchyid-Funktionen](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] , um hierarchische Daten abzufragen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="526df-114">Use the [hierarchyid functions](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) in [!INCLUDE[tsql](../includes/tsql-md.md)] to query and manage hierarchical data.</span></span>  
  
##  <a name="key-properties-of-hierarchyid"></a><a name="keyprops"></a> <span data-ttu-id="526df-115">Haupteigenschaften von hierarchyid</span><span class="sxs-lookup"><span data-stu-id="526df-115">Key Properties of hierarchyid</span></span>  
 <span data-ttu-id="526df-116">Ein Wert des `hierarchyid`-Datentyps stellt eine Position in einer Strukturhierarchie dar.</span><span class="sxs-lookup"><span data-stu-id="526df-116">A value of the `hierarchyid` data type represents a position in a tree hierarchy.</span></span> <span data-ttu-id="526df-117">Werte des Typs `hierarchyid` verfügen über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="526df-117">Values for `hierarchyid` have the following properties:</span></span>  
  
-   <span data-ttu-id="526df-118">Äußerst komprimiert</span><span class="sxs-lookup"><span data-stu-id="526df-118">Extremely compact</span></span>  
  
     <span data-ttu-id="526df-119">Die durchschnittliche Zahl der Bits, die erforderlich sind, um einen Knoten in einer Struktur mit *n* Knoten darzustellen, hängt von der durchschnittlichen Anzahl der Verzweigungen (der durchschnittlichen Anzahl untergeordneter Knoten) eines Knotens ab.</span><span class="sxs-lookup"><span data-stu-id="526df-119">The average number of bits that are required to represent a node in a tree with *n* nodes depends on the average fanout (the average number of children of a node).</span></span> <span data-ttu-id="526df-120">Bei wenigen Verzweigungen (0-7) entspricht diese Zahl etwa 6\*logA*n* Bit, wobei A die durchschnittliche Anzahl von Verzweigungen angibt.</span><span class="sxs-lookup"><span data-stu-id="526df-120">For small fanouts, (0-7) the size is about 6\*logA*n* bits, where A is the average fanout.</span></span> <span data-ttu-id="526df-121">Ein Knoten in einer 100.000 Leute umfassenden Organisationshierarchie mit durchschnittlich 6 Verzweigungen benötigt etwa 38 Bit.</span><span class="sxs-lookup"><span data-stu-id="526df-121">A node in an organizational hierarchy of 100,000 people with an average fanout of 6 levels takes about 38 bits.</span></span> <span data-ttu-id="526df-122">Dieser Wert wird bei der Speicherung auf 40 Bit oder 5 Byte aufgerundet.</span><span class="sxs-lookup"><span data-stu-id="526df-122">This is rounded up to 40 bits, or 5 bytes, for storage.</span></span>  
  
-   <span data-ttu-id="526df-123">Vergleiche erfolgen in Tiefensuchreihenfolge</span><span class="sxs-lookup"><span data-stu-id="526df-123">Comparison is in depth-first order</span></span>  
  
     <span data-ttu-id="526df-124">Bei zwei `hierarchyid` Werten von **a** und **b**bedeutet **a<b** , dass in einem tiefen ersten Durchlauf der Struktur a vor b kommt.</span><span class="sxs-lookup"><span data-stu-id="526df-124">Given two `hierarchyid` values **a** and **b**, **a<b** means a comes before b in a depth-first traversal of the tree.</span></span> <span data-ttu-id="526df-125">Indizes für `hierarchyid`-Datentypen verwenden die Tiefensuchreihenfolge, und einander benachbarte Knoten werden bei der Tiefensuchreihenfolge nahe beieinander gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-125">Indexes on `hierarchyid` data types are in depth-first order, and nodes close to each other in a depth-first traversal are stored near each other.</span></span> <span data-ttu-id="526df-126">Einem Datensatz untergeordnete Datensätze werden zum Beispiel angrenzend an diesen Datensatz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-126">For example, the children of a record are stored adjacent to that record.</span></span>  
  
-   <span data-ttu-id="526df-127">Unterstützung willkürlicher Einfüge- und Löschvorgänge</span><span class="sxs-lookup"><span data-stu-id="526df-127">Support for arbitrary insertions and deletions</span></span>  
  
     <span data-ttu-id="526df-128">Mithilfe der [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) -Methode ist es immer möglich, rechts oder links von einem gegebenen Knoten einen gleichgeordneten Knoten zu generieren oder ihn auch zwischen zwei gleichgeordneten Knoten einzufügen.</span><span class="sxs-lookup"><span data-stu-id="526df-128">By using the [GetDescendant](/sql/t-sql/data-types/getdescendant-database-engine) method, it is always possible to generate a sibling to the right of any given node, to the left of any given node, or between any two siblings.</span></span> <span data-ttu-id="526df-129">Die Vergleichseigenschaft bleibt auch dann gewahrt, wenn eine beliebige Anzahl von Knoten in die Hierarchie eingefügt oder aus ihr gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="526df-129">The comparison property is maintained when an arbitrary number of nodes is inserted or deleted from the hierarchy.</span></span> <span data-ttu-id="526df-130">Die meisten Einfüge- und Löschoperationen behalten die Kompaktheitseigenschaft bei.</span><span class="sxs-lookup"><span data-stu-id="526df-130">Most insertions and deletions preserve the compactness property.</span></span> <span data-ttu-id="526df-131">Einfügungen zwischen zwei Knoten erzeugen jedoch hierarchyid-Werte in einer etwas weniger komprimierten Darstellung.</span><span class="sxs-lookup"><span data-stu-id="526df-131">However, insertions between two nodes will produce hierarchyid values with a slightly less compact representation.</span></span>  
  
  
##  <a name="limitations-of-hierarchyid"></a><a name="limits"></a> <span data-ttu-id="526df-132">Einschränkungen von hierarchyid</span><span class="sxs-lookup"><span data-stu-id="526df-132">Limitations of hierarchyid</span></span>  
 <span data-ttu-id="526df-133">Für den- `hierarchyid` Datentyp gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="526df-133">The `hierarchyid` data type has the following limitations:</span></span>  
  
-   <span data-ttu-id="526df-134">Eine Spalte des Typs `hierarchyid` stellt nicht automatisch eine Baumstruktur dar.</span><span class="sxs-lookup"><span data-stu-id="526df-134">A column of type `hierarchyid` does not automatically represent a tree.</span></span> <span data-ttu-id="526df-135">Es ist Aufgabe der Anwendung, `hierarchyid`-Werte so zu erstellen und zuzuweisen, dass die gewünschte Beziehung zwischen Zeilen anhand der Werte zu erkennen ist.</span><span class="sxs-lookup"><span data-stu-id="526df-135">It is up to the application to generate and assign `hierarchyid` values in such a way that the desired relationship between rows is reflected in the values.</span></span> <span data-ttu-id="526df-136">Einige Anwendungen können eine Spalte vom Typ `hierarchyid` aufweisen, der den Speicherort in einer Hierarchie angibt, die in einer anderen Tabelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="526df-136">Some applications might have a column of type `hierarchyid` that indicates the location in a hierarchy defined in another table.</span></span>  
  
-   <span data-ttu-id="526df-137">Es ist Aufgabe der Anwendung, die Parallelität zu verwalten, indem sie geeignete `hierarchyid`-Werte generiert und zuweist.</span><span class="sxs-lookup"><span data-stu-id="526df-137">It is up to the application to manage concurrency in generating and assigning `hierarchyid` values.</span></span> <span data-ttu-id="526df-138">Es gibt keine Garantie dafür, dass die `hierarchyid`-Werte einer Spalte eindeutig sind, sofern die Anwendung keine Einschränkung für einen eindeutigen Schlüssel verwendet oder selbst dafür sorgt, dass eindeutige Werte erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="526df-138">There is no guarantee that `hierarchyid` values in a column are unique unless the application uses a unique key constraint or enforces uniqueness itself through its own logic.</span></span>  
  
-   <span data-ttu-id="526df-139">Hierarchische, durch `hierarchyid`-Werte dargestellte Beziehungen werden nicht wie Fremdschlüsselbeziehungen durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="526df-139">Hierarchical relationships represented by `hierarchyid` values are not enforced like a foreign key relationship.</span></span> <span data-ttu-id="526df-140">Es ist möglich und manchmal auch angemessen, eine hierarchische Beziehung herzustellen, in der das Element B dem Element A untergeordnet ist, um dann A zu löschen, wodurch B mit einer Beziehung zu einem nicht mehr vorhandenen Datensatz verbleibt.</span><span class="sxs-lookup"><span data-stu-id="526df-140">It is possible and sometimes appropriate to have a hierarchical relationship where A has a child B, and then A is deleted leaving B with a relationship to a nonexistent record.</span></span> <span data-ttu-id="526df-141">Wenn dieses Verhalten unannehmbar ist, muss die Anwendung vor dem Löschen von Elementen prüfen, ob untergeordnete Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="526df-141">If this behavior is unacceptable, the application must query for descendants before deleting parents.</span></span>  
  
  
##  <a name="when-to-use-alternatives-to-hierarchyid"></a><a name="alternatives"></a> <span data-ttu-id="526df-142">Wann Alternativen zu hierarchyid zu verwenden sind</span><span class="sxs-lookup"><span data-stu-id="526df-142">When to Use Alternatives to hierarchyid</span></span>  
 <span data-ttu-id="526df-143">Zur Darstellung hierarchischer Daten gibt es zwei Alternativen zu `hierarchyid`. Diese sind:</span><span class="sxs-lookup"><span data-stu-id="526df-143">Two alternatives to `hierarchyid` for representing hierarchical data are:</span></span>  
  
-   <span data-ttu-id="526df-144">Über- und untergeordnet</span><span class="sxs-lookup"><span data-stu-id="526df-144">Parent/Child</span></span>  
  
-   <span data-ttu-id="526df-145">XML</span><span class="sxs-lookup"><span data-stu-id="526df-145">XML</span></span>  
  
 <span data-ttu-id="526df-146">`hierarchyid` ist diesen Alternativen im Allgemeinen überlegen.</span><span class="sxs-lookup"><span data-stu-id="526df-146">`hierarchyid` is generally superior to these alternatives.</span></span> <span data-ttu-id="526df-147">Jedoch gibt es bestimmte, unten aufgelistete Situationen, in denen diese Alternativen wahrscheinlich überlegen sind.</span><span class="sxs-lookup"><span data-stu-id="526df-147">However, there are specific situations detailed below where the alternatives are likely superior.</span></span>  
  
### <a name="parentchild"></a><span data-ttu-id="526df-148">Über- und untergeordnet</span><span class="sxs-lookup"><span data-stu-id="526df-148">Parent/Child</span></span>  
 <span data-ttu-id="526df-149">Beim Ansatz mit über- und untergeordneten Elementen enthält jede Zeile einen Verweis auf das übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="526df-149">When using the Parent/Child approach, each row contains a reference to the parent.</span></span> <span data-ttu-id="526df-150">Im folgenden Beispiel wird eine typische Tabelle definiert, welche die über- und untergeordneten Zeilen einer Über-/Unterordnungsbeziehung enthält.</span><span class="sxs-lookup"><span data-stu-id="526df-150">The following table defines a typical table used to contain the parent and the child rows in a Parent/Child relationship:</span></span>  
  
```  
USE AdventureWorks2012 ;  
GO  
  
CREATE TABLE ParentChildOrg  
   (  
    BusinessEntityID int PRIMARY KEY,  
    ManagerId int REFERENCES ParentChildOrg(BusinessEntityID),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
```  
  
 <span data-ttu-id="526df-151">Vergleich von über- und untergeordneten Elementen mit `hierarchyid` bei allgemeinen Vorgängen</span><span class="sxs-lookup"><span data-stu-id="526df-151">Comparing Parent/Child and `hierarchyid` for Common Operations</span></span>  
  
-   <span data-ttu-id="526df-152">Teilstrukturabfragen sind mit `hierarchyid` bedeutend schneller.</span><span class="sxs-lookup"><span data-stu-id="526df-152">Subtree queries are significantly faster with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="526df-153">Abfragen für direkt untergeordnete Elemente sind bei `hierarchyid` etwas langsamer.</span><span class="sxs-lookup"><span data-stu-id="526df-153">Direct descendant queries are slightly slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="526df-154">Das Verschieben innerer Knoten erfolgt bei `hierarchyid` langsamer.</span><span class="sxs-lookup"><span data-stu-id="526df-154">Moving non-leaf nodes is slower with `hierarchyid`.</span></span>  
  
-   <span data-ttu-id="526df-155">Das Einfügen innerer Knoten und das Einfügen oder Verschieben von Blattknoten weisen bei `hierarchyid` die gleiche Komplexität auf.</span><span class="sxs-lookup"><span data-stu-id="526df-155">Inserting non-leaf nodes and inserting or moving leaf nodes has the same complexity with `hierarchyid`.</span></span>  
  
 <span data-ttu-id="526df-156">Über- und untergeordnete Elemente könnten überlegen sein, wenn die folgenden Bedingungen vorliegen:</span><span class="sxs-lookup"><span data-stu-id="526df-156">Parent/Child might be superior when the following conditions exist:</span></span>  
  
-   <span data-ttu-id="526df-157">Die Größe des Schlüssels ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="526df-157">The size of the key is critical.</span></span> <span data-ttu-id="526df-158">Bei gleicher Anzahl von Knoten ist ein `hierarchyid`-Wert gleich groß oder größer als ein ganzzahliger Wert (`smallint`, `int`, `bigint`).</span><span class="sxs-lookup"><span data-stu-id="526df-158">For the same number of nodes, a `hierarchyid` value is equal to or larger than an integer-family (`smallint`, `int`, `bigint`) value.</span></span> <span data-ttu-id="526df-159">Das ist allerdings nur in seltenen Fällen ein Grund, über- und untergeordnete Elemente zu verwenden, denn `hierarchyid` ist bezüglich E/A- und CPU-Auslastung weitaus effizienter als die allgemeinen Tabellenausdrücke, die bei Verwendung einer Über-/Unterordnungsstruktur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="526df-159">This is only a reason to use Parent/Child in rare cases, because `hierarchyid` has significantly better locality of I/O and CPU complexity than the common table expressions required when you are using a Parent/Child structure.</span></span>  
  
-   <span data-ttu-id="526df-160">Abfragen erstrecken sich selten über Abschnitte der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="526df-160">Queries rarely query across sections of the hierarchy.</span></span> <span data-ttu-id="526df-161">Eine Abfrage bezieht sich mit anderen Worten in der Regel auf einen bestimmten Punkt in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="526df-161">In other words, queries usually address only a single point in the hierarchy.</span></span> <span data-ttu-id="526df-162">In diesen Fällen ist die benachbarte Speicherung der Elemente nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="526df-162">In these cases co-location is not important.</span></span> <span data-ttu-id="526df-163">Eine Struktur über- und untergeordneter Elemente ist beispielsweise dann überlegen, wenn die Organisationstabelle nur für die Verarbeitung von Gehaltsdaten einzelner Angestellter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="526df-163">For example, Parent/Child is superior when the organization table is only used to process payroll for individual employees.</span></span>  
  
-   <span data-ttu-id="526df-164">Innere Knotenteilstrukturen verschieben sich häufig, und dabei ist die Leistung sehr wichtig.</span><span class="sxs-lookup"><span data-stu-id="526df-164">Non-leaf subtrees move frequently and performance is very important.</span></span> <span data-ttu-id="526df-165">Wird in einer Über-/Unterordnungsstruktur die Position einer Zeile in der Hierarchie geändert, ist davon nur eine einzelne Zeile betroffen.</span><span class="sxs-lookup"><span data-stu-id="526df-165">In a parent/child representation changing the location of a row in a hierarchy affects a single row.</span></span> <span data-ttu-id="526df-166">Das Ändern der Position einer Zeile in einer `hierarchyid` Verwendung wirkt sich auf *n* Zeilen aus, wobei *n* die Anzahl der Knoten in der Teilstruktur ist, die verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="526df-166">Changing the location of a row in a `hierarchyid` usage affects *n* rows, where *n* is number of nodes in the sub-tree being moved.</span></span>  
  
     <span data-ttu-id="526df-167">Wenn sich innere Knotenteilstrukturen häufig verschieben und die Leistung wichtig ist, jedoch die meisten Verschiebeoperationen auf einer wohldefinierten Ebene der Hierarchie stattfinden, sollten Sie erwägen, die höheren und niedrigeren Ebenen in zwei Hierarchien aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="526df-167">If the non-leaf subtrees move frequently and performance is important, but most of the moves are at a well-defined level of the hierarchy, consider splitting the higher and lower levels into two hierarchies.</span></span> <span data-ttu-id="526df-168">Dadurch beschränken sich alle Verschiebungen auf Blattebenen der höheren Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="526df-168">This makes all moves into leaf-levels of the higher hierarchy.</span></span> <span data-ttu-id="526df-169">Betrachten Sie beispielsweise eine Hierarchie der von einem Dienst gehosteten Websites.</span><span class="sxs-lookup"><span data-stu-id="526df-169">For instance, consider a hierarchy of Web sites hosted by a service.</span></span> <span data-ttu-id="526df-170">Websites enthalten viele auf hierarchische Weise angeordnete Seiten.</span><span class="sxs-lookup"><span data-stu-id="526df-170">Sites contain many pages arranged in a hierarchical manner.</span></span> <span data-ttu-id="526df-171">Gehostete Sites können an einen anderen Ort innerhalb der Site-Hierarchie verschoben werden, jedoch werden die untergeordneten Seiten nur selten neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="526df-171">Hosted sites might be moved to other locations in the site hierarchy, but the subordinate pages are rarely re-arranged.</span></span> <span data-ttu-id="526df-172">Dies könnte wie folgt dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="526df-172">This could be represented via:</span></span>  
  
    ```  
    CREATE TABLE HostedSites   
       (  
        SiteId hierarchyid, PageId hierarchyid  
       ) ;  
    GO  
    ```  
  
  
### <a name="xml"></a><span data-ttu-id="526df-173">XML</span><span class="sxs-lookup"><span data-stu-id="526df-173">XML</span></span>  
 <span data-ttu-id="526df-174">Ein XML-Dokument ist eine Baumstruktur, daher kann eine einzige Instanz eines XML-Datentyps eine vollständige Hierarchie repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="526df-174">An XML document is a tree, and therefore a single XML data type instance can represent a complete hierarchy.</span></span> <span data-ttu-id="526df-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] `hierarchyid` werden Werte intern verwendet, um die Position in der Hierarchie darzustellen, wenn ein XML-Index erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="526df-175">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] when an XML index is created, `hierarchyid` values are used internally to represent the position in the hierarchy.</span></span>  
  
 <span data-ttu-id="526df-176">Die Verwendung des XML-Datentyps kann überlegen sein, wenn alle folgenden Punkte zutreffen:</span><span class="sxs-lookup"><span data-stu-id="526df-176">Using XML data type can be superior when all the following are true:</span></span>  
  
-   <span data-ttu-id="526df-177">Es wird immer die vollständige Hierarchie gespeichert und abgerufen.</span><span class="sxs-lookup"><span data-stu-id="526df-177">The complete hierarchy is always stored and retrieved.</span></span>  
  
-   <span data-ttu-id="526df-178">Die Daten werden von der Anwendung im XML-Format verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="526df-178">The data is consumed in XML format by the application.</span></span>  
  
-   <span data-ttu-id="526df-179">Prädikatssuchen werden äußerst selten verwendet und die Leistung ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="526df-179">Predicate searches are extremely limited and not performance critical.</span></span>  
  
 <span data-ttu-id="526df-180">Wenn eine Anwendung zum Beispiel mehrere Organisationen verfolgt, immer die gesamte Organisationshierarchie speichert und abruft sowie keine einzelne Organisation abfragt, dann könnte eine Tabelle der folgenden Form sinnvoll sein:</span><span class="sxs-lookup"><span data-stu-id="526df-180">For example, if an application tracks multiple organizations, always stores and retrieves the complete organizational hierarchy, and does not query into a single organization, a table of the following form might make sense:</span></span>  
  
```  
CREATE TABLE XMLOrg   
    (  
    Orgid int,  
    Orgdata xml  
    ) ;  
GO  
```  
  
  
##  <a name="indexing-strategies-for-hierarchical-data"></a><a name="indexing"></a> <span data-ttu-id="526df-181">Indizieren von Strategien für hierarchische Daten</span><span class="sxs-lookup"><span data-stu-id="526df-181">Indexing Strategies for Hierarchical Data</span></span>  
 <span data-ttu-id="526df-182">Für die Indizierung hierarchischer Daten gibt es zwei Strategien:</span><span class="sxs-lookup"><span data-stu-id="526df-182">There are two strategies for indexing hierarchical data:</span></span>  
  
-   <span data-ttu-id="526df-183">**Tiefensuche**</span><span class="sxs-lookup"><span data-stu-id="526df-183">**Depth-first**</span></span>  
  
     <span data-ttu-id="526df-184">Bei einem Tiefensuchindex werden Zeilen in einer Teilstruktur nahe beieinander gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-184">A depth-first index stores the rows in a subtree near each other.</span></span> <span data-ttu-id="526df-185">Zum Beispiel werden alle Mitarbeiter, die einem bestimmten Manager berichten, in der Nähe des Datensatzes dieses Managers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-185">For example, all employees that report through a manager are stored near their managers' record.</span></span>  
  
     <span data-ttu-id="526df-186">In einem Tiefensuchindex sind alle Knoten in der Teilstruktur eines Knotens zusammen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="526df-186">In a depth-first index, all nodes in the subtree of a node are co-located.</span></span> <span data-ttu-id="526df-187">Daher sind Tiefensuchindizes besonders effizient bei der Abfrage von Teilstrukturen, etwa bei Abfragen des Typs "Ermittle alle Dateien in diesem Ordner und seinen Unterordnern".</span><span class="sxs-lookup"><span data-stu-id="526df-187">Depth-first indexes are therefore efficient for answering queries about subtrees, such as "Find all files in this folder and its subfolders".</span></span>  
  
-   <span data-ttu-id="526df-188">**Breitensuche**</span><span class="sxs-lookup"><span data-stu-id="526df-188">**Breadth-first**</span></span>  
  
     <span data-ttu-id="526df-189">Bei einem Breitensuchindex werden die Zeilen jeder Ebene der Hierarchie zusammen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-189">A breadth-first stores the rows each level of the hierarchy together.</span></span> <span data-ttu-id="526df-190">Zum Beispiel werden die Datensätze aller Mitarbeiter, die direkt einem bestimmten Manager berichten, nahe beieinander gespeichert.</span><span class="sxs-lookup"><span data-stu-id="526df-190">For example, the records of employees who directly report to the same manager are stored near each other.</span></span>  
  
     <span data-ttu-id="526df-191">In einem Breitensuchindex sind alle einem Knoten untergeordneten Knoten zusammen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="526df-191">In a breadth-first index all direct children of a node are co-located.</span></span> <span data-ttu-id="526df-192">Daher sind Breitensuchindizes besonders effizient bei der Abfrage von unmittelbar untergeordneten Elementen, etwa bei Abfragen des Typs "Ermittle alle Angestellten, die direkt diesem Manager berichten".</span><span class="sxs-lookup"><span data-stu-id="526df-192">Breadth-first indexes are therefore efficient for answering queries about immediate children, such as "Find all employees who report directly to this manager".</span></span>  
  
 <span data-ttu-id="526df-193">Ob Sie einen Tiefen- oder Breitensuchindex verwenden und welchen Sie (wenn überhaupt) als Gruppierungsschlüssel definieren, hängt von der relativen Wichtigkeit der oben genanten Abfragetypen ab sowie von der relativen Wichtigkeit von SELECT- gegenüber DML-Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="526df-193">Whether to have depth-first, breadth-first, or both, and which to make the clustering key (if any), depends on the relative importance of the above types of queries, and the relative importance of SELECT vs. DML operations.</span></span> <span data-ttu-id="526df-194">Ein ausführliches Beispiel zu Indizierungsstrategien finden Sie unter [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="526df-194">For a detailed example of indexing strategies, see [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
### <a name="creating-indexes"></a><span data-ttu-id="526df-195">Erstellen von Indizes</span><span class="sxs-lookup"><span data-stu-id="526df-195">Creating Indexes</span></span>  
 <span data-ttu-id="526df-196">Die Methode „GetLevel()“ kann verwendet werden, um eine Breitensuchreihenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="526df-196">The GetLevel() method can be used to create a breadth first ordering.</span></span> <span data-ttu-id="526df-197">Im folgenden Beispiel werden sowohl Breitensuch- als auch Tiefensuchindizes erstellt:</span><span class="sxs-lookup"><span data-stu-id="526df-197">In the following example, both breadth-first and depth-first indexes are created:</span></span>  
  
```wmimof  
USE AdventureWorks2012 ;   
GO  
  
CREATE TABLE Organization  
   (  
    BusinessEntityID hierarchyid,  
    OrgLevel as BusinessEntityID.GetLevel(),   
    EmployeeName nvarchar(50) NOT NULL  
   ) ;  
GO  
  
CREATE CLUSTERED INDEX Org_Breadth_First   
ON Organization(OrgLevel,BusinessEntityID) ;  
GO  
  
CREATE UNIQUE INDEX Org_Depth_First   
ON Organization(BusinessEntityID) ;  
GO  
```  
  
  
## <a name="examples"></a><span data-ttu-id="526df-198">Beispiele</span><span class="sxs-lookup"><span data-stu-id="526df-198">Examples</span></span>  
  
### <a name="simple-example"></a><span data-ttu-id="526df-199">Einfaches Beispiel</span><span class="sxs-lookup"><span data-stu-id="526df-199">Simple Example</span></span>  
 <span data-ttu-id="526df-200">Das folgende Beispiel wurde absichtlich einfach gehalten, um Ihnen die ersten Schritte zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="526df-200">The following example is intentionally simplistic to help you get started.</span></span> <span data-ttu-id="526df-201">Erstellen Sie zunächst eine Tabelle, in der einige geografischen Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="526df-201">First create a table to hold some geography data.</span></span>  
  
```  
CREATE TABLE SimpleDemo  
(Level hierarchyid NOT NULL,  
Location nvarchar(30) NOT NULL,  
LocationType nvarchar(9) NULL);  
```  
  
 <span data-ttu-id="526df-202">Fügen Sie nun Daten für einige Kontinente, Länder, Bundesstaaten und Städte ein.</span><span class="sxs-lookup"><span data-stu-id="526df-202">Now insert data for some continents, countries, states, and cities.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES   
('/1/', 'Europe', 'Continent'),  
('/2/', 'South America', 'Continent'),  
('/1/1/', 'France', 'Country'),  
('/1/1/1/', 'Paris', 'City'),  
('/1/2/1/', 'Madrid', 'City'),  
('/1/2/', 'Spain', 'Country'),  
('/3/', 'Antarctica', 'Continent'),  
('/2/1/', 'Brazil', 'Country'),  
('/2/1/1/', 'Brasilia', 'City'),  
('/2/1/2/', 'Bahia', 'State'),  
('/2/1/2/1/', 'Salvador', 'City'),  
('/3/1/', 'McMurdo Station', 'City');  
```  
  
 <span data-ttu-id="526df-203">Wählen Sie die Daten aus, und fügen Sie eine Spalte hinzu, durch die die Daten für die Ebene (Level) in einen leicht verständlichen Textwert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="526df-203">Select the data, adding a column that converts the Level data into a text value that is easy to understand.</span></span> <span data-ttu-id="526df-204">Mit dieser Abfrage wird das Ergebnis auch nach dem `hierarchyid`-Datentyp sortiert.</span><span class="sxs-lookup"><span data-stu-id="526df-204">This query also orders the result by the `hierarchyid` data type.</span></span>  
  
```  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], *   
FROM SimpleDemo ORDER BY Level;  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
Converted Level  Level     Location         LocationType  
/1/              0x58      Europe           Continent  
/1/1/            0x5AC0    France           Country  
/1/1/1/          0x5AD6    Paris            City  
/1/2/            0x5B40    Spain            Country  
/1/2/1/          0x5B56    Madrid           City  
/2/              0x68      South America    Continent  
/2/1/            0x6AC0    Brazil           Country  
/2/1/1/          0x6AD6    Brasilia         City  
/2/1/2/          0x6ADA    Bahia            State  
/2/1/2/1/        0x6ADAB0  Salvador         City  
/3/              0x78      Antarctica       Continent  
/3/1/            0x7AC0    McMurdo Station  City  
```  
  
 <span data-ttu-id="526df-205">Beachten Sie, dass die Hierarchie über eine gültige Struktur verfügt, obwohl sie intern nicht konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="526df-205">Notice that the hierarchy is has a valid structure, even though it is not internally consistent.</span></span> <span data-ttu-id="526df-206">Bahia ist der einzige Bundesstaat.</span><span class="sxs-lookup"><span data-stu-id="526df-206">Bahia is the only state.</span></span> <span data-ttu-id="526df-207">Er wird in der Hierarchie als gleichgeordnetes Element der Stadt Brasilia angezeigt.</span><span class="sxs-lookup"><span data-stu-id="526df-207">It appears in the hierarchy as a peer of the city Brasilia.</span></span> <span data-ttu-id="526df-208">Entsprechend wird auch für McMurdo Station kein übergeordnetes Land angegeben.</span><span class="sxs-lookup"><span data-stu-id="526df-208">Similarly, McMurdo Station does not have a parent country.</span></span> <span data-ttu-id="526df-209">Die Benutzer müssen entscheiden, ob dieser Hierarchietyp für ihre Zwecke geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="526df-209">Users must decide if this type of hierarchy is appropriate for their use.</span></span>  
  
 <span data-ttu-id="526df-210">Fügen Sie eine weitere Zeile hinzu, und wählen Sie die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="526df-210">Add another row and select the results.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/1/3/1/', 'Kyoto', 'City'), ('/1/3/1/', 'London', 'City');  
SELECT CAST(Level AS nvarchar(100)) AS [Converted Level], * FROM SimpleDemo ORDER BY Level;  
```  
  
 <span data-ttu-id="526df-211">Dadurch werden weitere potenzielle Probleme deutlich.</span><span class="sxs-lookup"><span data-stu-id="526df-211">This demonstrates more possible problems.</span></span> <span data-ttu-id="526df-212">Kyoto kann als Ebene `/1/3/1/` eingefügt werden, obwohl keine übergeordnete Ebene `/1/3/`vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="526df-212">Kyoto can be inserted as level `/1/3/1/` even though there is no parent level `/1/3/`.</span></span> <span data-ttu-id="526df-213">Darüber hinaus verfügen sowohl London als auch Kyoto für `hierarchyid` über denselben Wert.</span><span class="sxs-lookup"><span data-stu-id="526df-213">And both London and Kyoto have the same value for the `hierarchyid`.</span></span> <span data-ttu-id="526df-214">Auch in diesem Fall müssen die Benutzer entscheiden, ob dieser Hierarchietyp für sie geeignet ist und Werte blockieren, die nicht brauchbar sind.</span><span class="sxs-lookup"><span data-stu-id="526df-214">Again, users must decide if this type of hierarchy is appropriate for their use, and block values that are invalid for their usage.</span></span>  
  
 <span data-ttu-id="526df-215">Auch in dieser Tabelle wurde die oberste Hierarchieebene `'/'`nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="526df-215">Also, this table did not use the top of the hierarchy `'/'`.</span></span> <span data-ttu-id="526df-216">Sie wurde weggelassen, weil die Kontinente kein gemeinsames übergeordnetes Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="526df-216">It was omitted because there is no common parent of all the continents.</span></span> <span data-ttu-id="526df-217">Sie können den gesamten Planeten hinzufügen, falls Sie ein gemeinsames übergeordnetes Element benötigen.</span><span class="sxs-lookup"><span data-stu-id="526df-217">You can add one by adding the whole planet.</span></span>  
  
```  
INSERT SimpleDemo  
VALUES ('/', 'Earth', 'Planet');  
```  
  
##  <a name="related-tasks"></a><a name="tasks"></a> <span data-ttu-id="526df-218">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="526df-218">Related Tasks</span></span>  
  
###  <a name="migrating-from-parentchild-to-hierarchyid"></a><a name="migrating"></a> <span data-ttu-id="526df-219">Migrieren von über- und untergeordneten Elementen zu hierarchyid</span><span class="sxs-lookup"><span data-stu-id="526df-219">Migrating from Parent/Child to hierarchyid</span></span>  
 <span data-ttu-id="526df-220">Die meisten Strukturen werden mit über- und untergeordneten Elementen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="526df-220">Most trees are represented using Parent/Child.</span></span> <span data-ttu-id="526df-221">Die einfachste Möglichkeit, von einer über-und untergeordneten Struktur zu einer Tabelle mit zu migrieren, `hierarchyid` besteht darin, eine temporäre Spalte oder eine temporäre Tabelle zu verwenden, um die Anzahl der Knoten auf jeder Ebene der Hierarchie nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="526df-221">The easiest way to migrate from a Parent/Child structure to a table using `hierarchyid` is to use a temporary column or a temporary table to keep track of the number of nodes at each level of the hierarchy.</span></span> <span data-ttu-id="526df-222">Ein Beispiel für die Migration einer über- und untergeordneten Tabelle finden Sie in Lektion 1 von [Tutorial: Verwenden des hierarchyid-Datentyps](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="526df-222">For an example of migrating a Parent/Child table, see lesson 1 of [Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md).</span></span>  
  
  
###  <a name="managing-a-tree-using-hierarchyid"></a><a name="BKMK_ManagingTrees"></a> <span data-ttu-id="526df-223">Verwalten einer Struktur mit hierarchyid</span><span class="sxs-lookup"><span data-stu-id="526df-223">Managing a Tree Using hierarchyid</span></span>  
 <span data-ttu-id="526df-224">Eine `hierarchyid`-Spalte muss zwar nicht notwendigerweise eine Struktur darstellen, jedoch kann eine Anwendung dies auf einfache Weise sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="526df-224">Although a `hierarchyid` column does not necessarily represent a tree, an application can easily ensure that it does.</span></span>  
  
-   <span data-ttu-id="526df-225">Führen Sie eine der folgenden Maßnahmen durch, wenn Sie neue Werte erstellen:</span><span class="sxs-lookup"><span data-stu-id="526df-225">When generating new values, do one of the following:</span></span>  
  
    -   <span data-ttu-id="526df-226">Halten Sie die Nummer des letzten untergeordneten Elements in der übergeordneten Zeile fest.</span><span class="sxs-lookup"><span data-stu-id="526df-226">Keep track of the last child number in the parent row.</span></span>  
  
    -   <span data-ttu-id="526df-227">Berechnen Sie das letzte untergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="526df-227">Compute the last child.</span></span> <span data-ttu-id="526df-228">Für die effiziente Ausführung dieser Berechnung ist ein Breitensuchindex erforderlich.</span><span class="sxs-lookup"><span data-stu-id="526df-228">Doing this efficiently requires a breadth-first index.</span></span>  
  
-   <span data-ttu-id="526df-229">Setzen Sie Eindeutigkeit durch, indem Sie für die Spalte, vielleicht als Teil eines Gruppierungsschlüssels, einen eindeutigen Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="526df-229">Enforce uniqueness by creating a unique index on the column, perhaps as part of a clustering key.</span></span> <span data-ttu-id="526df-230">Um sicherzustellen, dass eindeutige Werte eingefügt werden, führen Sie eine der folgenden Maßnahmen durch:</span><span class="sxs-lookup"><span data-stu-id="526df-230">To ensure that unique values are inserted, do one of the following:</span></span>  
  
    -   <span data-ttu-id="526df-231">Spüren Sie Verletzungen des eindeutigen Indexes auf und wiederholen Sie den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="526df-231">Detect unique key violation failures and retry.</span></span>  
  
    -   <span data-ttu-id="526df-232">Bestimmen Sie die Eindeutigkeit eines jeden neuen untergeordneten Knotens, und fügen Sie ihn als Teil einer serialisierbaren Transaktion ein.</span><span class="sxs-lookup"><span data-stu-id="526df-232">Determine the uniqueness of each new child node, and insert it as part of a serializable transaction.</span></span>  
  
  
#### <a name="example-using-error-detection"></a><span data-ttu-id="526df-233">Beispiel für Fehlererkennung</span><span class="sxs-lookup"><span data-stu-id="526df-233">Example Using Error Detection</span></span>  
 <span data-ttu-id="526df-234">Der Code im folgenden Beispiel berechnet den **EmployeeId** -Wert des neuen untergeordneten Elements, und spürt anschließend eine Schlüsselverletzung auf, worauf er zur Markierung **INS_EMP** zurückkehrt, um den **EmployeeId** -Wert für die neue Zeile neu zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="526df-234">In the following example, the sample code computes the new child **EmployeeId** value, and then detects any key violation and returns to **INS_EMP** marker to recompute the **EmployeeId** value for the new row:</span></span>  
  
```  
USE AdventureWorks ;  
GO  
  
CREATE TABLE Org_T1  
   (  
    EmployeeId hierarchyid PRIMARY KEY,  
    OrgLevel AS EmployeeId.GetLevel(),  
    EmployeeName nvarchar(50)   
   ) ;  
GO  
  
CREATE INDEX Org_BreadthFirst ON Org_T1(OrgLevel, EmployeeId)  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50) )   
AS  
BEGIN  
    DECLARE @last_child hierarchyid  
INS_EMP:   
    SELECT @last_child = MAX(EmployeeId) FROM Org_T1   
    WHERE EmployeeId.GetAncestor(1) = @mgrid  
INSERT Org_T1 (EmployeeId, EmployeeName)  
SELECT @mgrid.GetDescendant(@last_child, NULL), @EmpName   
-- On error, return to INS_EMP to recompute @last_child  
IF @@error <> 0 GOTO INS_EMP   
END ;  
GO  
```  
  
  
#### <a name="example-using-a-serializable-transaction"></a><span data-ttu-id="526df-235">Beispiel für eine serialisierbare Transaktion</span><span class="sxs-lookup"><span data-stu-id="526df-235">Example Using a Serializable Transaction</span></span>  
 <span data-ttu-id="526df-236">Für den **Org_BreadthFirst** -Index stellt sicher, dass **@last_child** mittels einer Bereichssuche ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="526df-236">The **Org_BreadthFirst** index ensures that determining **@last_child** uses a range seek.</span></span> <span data-ttu-id="526df-237">Zusätzlich zu anderen Fehler Fällen, die eine Anwendung überprüfen möchte, kann eine doppelte Schlüssel Verletzung nach dem Einfügen auf einen Versuch hindeuten, mehrere Mitarbeiter mit der gleichen ID hinzuzufügen, und **@last_child** muss daher neu berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="526df-237">In addition to other error cases an application might want to check, a duplicate key violation after the insert indicates an attempt to add multiple employees with the same id, and therefore **@last_child** must be recomputed.</span></span> <span data-ttu-id="526df-238">Im folgenden Code werden eine serialisierbare Transaktion und ein Breitensuchindex verwendet, um den neuen Knotenwert zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="526df-238">The following code uses a serializable transaction and a breadth-first index to compute the new node value:</span></span>  
  
```  
CREATE TABLE Org_T2  
    (  
    EmployeeId hierarchyid PRIMARY KEY,  
    LastChild hierarchyid,   
    EmployeeName nvarchar(50)   
    ) ;  
GO  
  
CREATE PROCEDURE AddEmp(@mgrid hierarchyid, @EmpName nvarchar(50))   
AS  
BEGIN  
DECLARE @last_child hierarchyid  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION   
  
UPDATE Org_T2   
SET @last_child = LastChild = EmployeeId.GetDescendant(LastChild,NULL)  
WHERE EmployeeId = @mgrid  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(@last_child, @EmpName)  
COMMIT  
END ;  
```  
  
 <span data-ttu-id="526df-239">Im folgenden Code wird die Tabelle mit drei Zeilen aufgefüllt. Anschließend werden die Ergebnisse zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="526df-239">The following code populates the table with three rows and returns the results:</span></span>  
  
```  
INSERT Org_T2 (EmployeeId, EmployeeName)   
    VALUES(hierarchyid::GetRoot(), 'David') ;  
GO  
AddEmp 0x , 'Sariya'  
GO  
AddEmp 0x58 , 'Mary'  
GO  
SELECT * FROM Org_T2  
```  
  
 [!INCLUDE[ssResult](../includes/ssresult-md.md)]  
  
```  
EmployeeId LastChild EmployeeName  
---------- --------- ------------  
0x        0x58       David  
0x58      0x5AC0     Sariya  
0x5AC0    NULL       Mary  
```  
  
  
###  <a name="enforcing-a-tree"></a><a name="BKMK_EnforcingTrees"></a> <span data-ttu-id="526df-240">Durchsetzen einer Struktur</span><span class="sxs-lookup"><span data-stu-id="526df-240">Enforcing a tree</span></span>  
 <span data-ttu-id="526df-241">In den Beispielen oben wird veranschaulicht, wie eine Anwendung sicherstellen kann, dass eine Struktur gewahrt bleibt.</span><span class="sxs-lookup"><span data-stu-id="526df-241">The above examples illustrate how an application can ensure that a tree is maintained.</span></span> <span data-ttu-id="526df-242">Um eine Struktur mithilfe von Einschränkungen durchzusetzen, kann eine berechnete Spalte mit einer Fremdschlüsseleinschränkung für die Primärschlüssel-ID erstellt werden, die das übergeordnete Element jedes Knotens berechnet.</span><span class="sxs-lookup"><span data-stu-id="526df-242">To enforce a tree by using constraints, a computed column that defines the parent of each node can be created with a foreign key constraint back to the primary key id.</span></span>  
  
```  
CREATE TABLE Org_T3  
(  
   EmployeeId hierarchyid PRIMARY KEY,  
   ParentId AS EmployeeId.GetAncestor(1) PERSISTED    
      REFERENCES Org_T3(EmployeeId),  
   LastChild hierarchyid,   
   EmployeeName nvarchar(50)  
)  
GO  
```  
  
 <span data-ttu-id="526df-243">Diese Methode der Durchsetzung einer Beziehung ist dann vorzuziehen, wenn Code, dem bezüglich der Bewahrung der hierarchischen Struktur nicht vertraut werden kann, über direkten DML-Zugriff auf die Tabelle verfügt.</span><span class="sxs-lookup"><span data-stu-id="526df-243">This method of enforcing a relationship is preferred when code that is not trusted to maintain the hierarchical tree has direct DML access to the table.</span></span> <span data-ttu-id="526df-244">Diese Methode könnte jedoch die Leistung reduzieren, da die Einschränkung bei jedem DML-Vorgang geprüft werden muss.</span><span class="sxs-lookup"><span data-stu-id="526df-244">However this method might reduce performance because the constraint must be checked on every DML operation.</span></span>  
  
  
###  <a name="finding-ancestors-by-using-the-clr"></a><a name="findclr"></a> <span data-ttu-id="526df-245">Suchen von Vorgängern mit CLR</span><span class="sxs-lookup"><span data-stu-id="526df-245">Finding Ancestors by Using the CLR</span></span>  
 <span data-ttu-id="526df-246">Ein allgemeiner Vorgang, der zwei Knoten einer Hierarchie betrifft, ist die Ermittlung des kleinsten gemeinsamen Vorgängers.</span><span class="sxs-lookup"><span data-stu-id="526df-246">A common operation involving two nodes in a hierarchy is to find the lowest common ancestor.</span></span> <span data-ttu-id="526df-247">Dies kann in [!INCLUDE[tsql](../includes/tsql-md.md)] oder CLR geschrieben werden, da der- `hierarchyid` Typ in beiden verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="526df-247">This can be written in either [!INCLUDE[tsql](../includes/tsql-md.md)] or CLR, because the `hierarchyid` type is available in both.</span></span> <span data-ttu-id="526df-248">CLR wird empfohlen, da die Leistung höher ist.</span><span class="sxs-lookup"><span data-stu-id="526df-248">CLR is recommended because performance will be faster.</span></span>  
  
 <span data-ttu-id="526df-249">Verwenden Sie den folgenden CLR-Code, um die Vorgänger aufzulisten und den kleinsten gemeinsamen Vorgänger zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="526df-249">Use the following CLR code to list ancestors and to find the lowest common ancestor:</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Text;  
using Microsoft.SqlServer.Server;  
using Microsoft.SqlServer.Types;  
  
public partial class HierarchyId_Operations  
{  
    [SqlFunction(FillRowMethodName = "FillRow_ListAncestors")]  
    public static IEnumerable ListAncestors(SqlHierarchyId h)  
    {  
        while (!h.IsNull)  
        {  
            yield return (h);  
            h = h.GetAncestor(1);  
        }  
    }  
    public static void FillRow_ListAncestors(Object obj, out SqlHierarchyId ancestor)  
    {  
        ancestor = (SqlHierarchyId)obj;  
    }  
  
    public static HierarchyId CommonAncestor(SqlHierarchyId h1, HierarchyId h2)  
    {  
        while (!h1.IsDescendant(h2))  
            h1 = h1.GetAncestor(1);  
  
        return h1;  
    }  
}  
```  
  
 <span data-ttu-id="526df-250">Um die Methoden **ListAncestor** und **CommonAncestor** in den folgenden [!INCLUDE[tsql](../includes/tsql-md.md)] -Beispielen verwenden zu können, müssen Sie die DLL und die **HierarchyId_Operations** -Assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] erstellen, indem Sie Code ähnlich dem folgenden ausführen:</span><span class="sxs-lookup"><span data-stu-id="526df-250">To use the **ListAncestor** and **CommonAncestor** methods in the following [!INCLUDE[tsql](../includes/tsql-md.md)] examples, build the DLL and create the **HierarchyId_Operations** assembly in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] by executing code similar to the following:</span></span>  
  
```  
CREATE ASSEMBLY HierarchyId_Operations   
FROM '<path to DLL>\ListAncestors.dll'  
GO  
```  
  
  
###  <a name="listing-ancestors"></a><a name="ancestors"></a> <span data-ttu-id="526df-251">Auflisten von Vorgängern</span><span class="sxs-lookup"><span data-stu-id="526df-251">Listing Ancestors</span></span>  
 <span data-ttu-id="526df-252">Die Erstellung einer Liste von Vorgängern, um beispielsweise die Position innerhalb einer Organisation anzuzeigen, ist ein häufig vorkommender Vorgang.</span><span class="sxs-lookup"><span data-stu-id="526df-252">Creating a list of ancestors of a node is a common operation, for instance to show position in an organization.</span></span> <span data-ttu-id="526df-253">Eine Möglichkeit dazu bietet die Verwendung einer Tabellenwertfunktion mithilfe der oben definierten **HierarchyId_Operations** -Klasse:</span><span class="sxs-lookup"><span data-stu-id="526df-253">One way of doing this is by using a table-valued-function using the **HierarchyId_Operations** class defined above:</span></span>  
  
 <span data-ttu-id="526df-254">Verwenden von [!INCLUDE[tsql](../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="526df-254">Using [!INCLUDE[tsql](../includes/tsql-md.md)]:</span></span>  
  
```  
CREATE FUNCTION ListAncestors (@node hierarchyid)  
RETURNS TABLE (node hierarchyid)  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.ListAncestors  
GO  
```  
  
 <span data-ttu-id="526df-255">Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="526df-255">Example of usage:</span></span>  
  
```  
DECLARE @h hierarchyid  
SELECT @h = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- /1/1/5/2/  
  
SELECT LoginID, OrgNode.ToString() AS LogicalNode  
FROM HumanResources.EmployeeDemo AS ED  
JOIN ListAncestors(@h) AS A   
   ON ED.OrgNode = A.Node  
GO  
```  
  
  
###  <a name="finding-the-lowest-common-ancestor"></a><a name="lowestcommon"></a> <span data-ttu-id="526df-256">Ermitteln des kleinsten gemeinsamen Vorgängers</span><span class="sxs-lookup"><span data-stu-id="526df-256">Finding the Lowest Common Ancestor</span></span>  
 <span data-ttu-id="526df-257">Erstellen Sie mithilfe der oben definierten **HierarchyId_Operations** -Klasse die folgende [!INCLUDE[tsql](../includes/tsql-md.md)] -Funktion, die den kleinsten gemeinsamen Vorgänger zweier Knoten in einer Hierarchie ermittelt:</span><span class="sxs-lookup"><span data-stu-id="526df-257">Using the **HierarchyId_Operations** class defined above, create the following [!INCLUDE[tsql](../includes/tsql-md.md)] function to find the lowest common ancestor involving two nodes in a hierarchy:</span></span>  
  
```  
CREATE FUNCTION CommonAncestor (@node1 hierarchyid, @node2 hierarchyid)  
RETURNS hierarchyid  
AS  
EXTERNAL NAME HierarchyId_Operations.HierarchyId_Operations.CommonAncestor  
GO  
```  
  
 <span data-ttu-id="526df-258">Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="526df-258">Example of usage:</span></span>  
  
```  
DECLARE @h1 hierarchyid, @h2 hierarchyid  
  
SELECT @h1 = OrgNode   
FROM  HumanResources.EmployeeDemo   
WHERE LoginID = 'adventure-works\jossef0' -- Node is /1/1/3/  
  
SELECT @h2 = OrgNode   
FROM HumanResources.EmployeeDemo    
WHERE LoginID = 'adventure-works\janice0' -- Node is /1/1/5/2/  
  
SELECT OrgNode.ToString() AS LogicalNode, LoginID   
FROM HumanResources.EmployeeDemo    
WHERE OrgNode = dbo.CommonAncestor(@h1, @h2) ;  
```  
  
 <span data-ttu-id="526df-259">Der resultierende Knoten ist /1/1/</span><span class="sxs-lookup"><span data-stu-id="526df-259">The resultant node is /1/1/</span></span>  
  
  
###  <a name="moving-subtrees"></a><a name="BKMK_MovingSubtrees"></a> <span data-ttu-id="526df-260">Verschieben von Teilstrukturen</span><span class="sxs-lookup"><span data-stu-id="526df-260">Moving Subtrees</span></span>  
 <span data-ttu-id="526df-261">Ein anderer allgemeiner Vorgang ist das Verschieben von Teilstrukturen.</span><span class="sxs-lookup"><span data-stu-id="526df-261">Another common operation is moving subtrees.</span></span> <span data-ttu-id="526df-262">Das folgende Verfahren bewirkt, dass die Teilstruktur von **@oldMgr** und (einschließlich **@oldMgr** ) zu einer Teilstruktur von wird **@newMgr** .</span><span class="sxs-lookup"><span data-stu-id="526df-262">The procedure below takes the subtree of **@oldMgr** and makes it (including **@oldMgr**) a subtree of **@newMgr**.</span></span>  
  
```  
CREATE PROCEDURE MoveOrg(@oldMgr nvarchar(256), @newMgr nvarchar(256) )  
AS  
BEGIN  
DECLARE @nold hierarchyid, @nnew hierarchyid  
SELECT @nold = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @oldMgr ;  
  
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
BEGIN TRANSACTION  
SELECT @nnew = OrgNode FROM HumanResources.EmployeeDemo WHERE LoginID = @newMgr ;  
  
SELECT @nnew = @nnew.GetDescendant(max(OrgNode), NULL)   
FROM HumanResources.EmployeeDemo WHERE OrgNode.GetAncestor(1)=@nnew ;  
  
UPDATE HumanResources.EmployeeDemo    
SET OrgNode = OrgNode.GetReparentedValue(@nold, @nnew)  
WHERE OrgNode.IsDescendantOf(@nold) = 1 ;  
  
COMMIT TRANSACTION  
END ;  
GO  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="526df-263">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="526df-263">See Also</span></span>  
 <span data-ttu-id="526df-264">[hierarchyid-Datentyp-Methodenverweis](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span><span class="sxs-lookup"><span data-stu-id="526df-264">[hierarchyid Data Type Method Reference](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) </span></span>  
 <span data-ttu-id="526df-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="526df-265">[Tutorial: Using the hierarchyid Data Type](../relational-databases/tables/tutorial-using-the-hierarchyid-data-type.md) </span></span>  
 [<span data-ttu-id="526df-266">hierarchyid &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="526df-266">hierarchyid &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/hierarchyid-data-type-method-reference)  
  
  
