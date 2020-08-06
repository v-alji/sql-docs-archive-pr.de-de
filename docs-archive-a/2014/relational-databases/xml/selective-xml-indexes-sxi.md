---
title: Selektive XML-Indizes (SXI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622453"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="2ced0-102">Selektive XML-Indizes (SXI)</span><span class="sxs-lookup"><span data-stu-id="2ced0-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="2ced0-103">Selektive XML-Indizes sind ein weiterer Typ von XML-Index, der Ihnen zusätzlich zu den herkömmlichen XML-Indizes zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="2ced0-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="2ced0-104">Die Ziele der selektiven XML-Indexfunktion sind Folgende:</span><span class="sxs-lookup"><span data-stu-id="2ced0-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="2ced0-105">Verbessern der Leistung von Abfragen zu XML-Daten, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="2ced0-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2ced0-106">Unterstützen einer schnelleren Indizierung großer XML-Datenlasten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="2ced0-107">Verbessern der Skalierbarkeit durch das Reduzieren der Speicherkosten für XML-Indizes.</span><span class="sxs-lookup"><span data-stu-id="2ced0-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="2ced0-108">Die Haupteinschränkung bei herkömmlichen XML-Indizes liegt darin, dass sie das gesamte XML-Dokument indizieren.</span><span class="sxs-lookup"><span data-stu-id="2ced0-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="2ced0-109">Dies führt zu mehreren bedeutenden Nachteilen, z. B. verringerter Abfrageleistung und höheren Kosten für die Indexwartung, die sich in der Regel auf die Indexspeicherkosten beziehen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="2ced0-110">Mit der selektiven XML-Indexfunktion können Sie nur bestimmte Pfade aus den XML-Dokumenten zum Index höherstufen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="2ced0-111">Bei der Indexerstellung werden diese Pfade ausgewertet, und die Knoten, auf die sie verweisen, werden aufgeteilt und in einer relationalen Tabelle in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2ced0-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ced0-112">Diese Funktion verwendet einen effizienten Zuordnungsalgorithmus, der in Zusammenarbeit mit dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Produktteam von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Research entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ced0-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="2ced0-113">Dieser Algorithmus ordnet die XML-Knoten einer einzelnen relationalen Tabelle zu und erzielt eine herausragende Leistung bei sehr geringem Speicherbedarf.</span><span class="sxs-lookup"><span data-stu-id="2ced0-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="2ced0-114">Die selektive XML-Indexfunktion unterstützt auch sekundäre selektive XML-Indizes für Knoten, die von einem selektiven XML-Index indiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="2ced0-115">Diese sekundären selektiven Indizes sind effizient und verbessern die Leistung von Abfragen noch weiter.</span><span class="sxs-lookup"><span data-stu-id="2ced0-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="2ced0-116">Vorteile selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="2ced0-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="2ced0-117">Selektive XML-Indizes bieten die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="2ced0-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="2ced0-118">Deutlich verbesserte Abfrageleistung für den XML-Datentyp bei typische Abfragelasten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="2ced0-119">Im Vergleich zu herkömmlichen XML-Indizes reduzierte Speicheranforderungen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="2ced0-120">Im Vergleich zu herkömmlichen XML-Indizes reduzierte Indexwartungskosten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="2ced0-121">Anwendungen müssen nicht aktualisiert werden, um die Vorteile selektiver XML-Indizes nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="2ced0-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="2ced0-122">Selektive XML-Indizes und primäre XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="2ced0-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ced0-123">Im Hinblick auf eine bessere Leistung und einen effizienteren Speicher erstellen Sie in den meisten Fällen einen selektiven XML-Index anstatt eines gewöhnlichen XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="2ced0-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="2ced0-124">Ein selektiver XML-Index wird jedoch nicht empfohlen, wenn eine der beiden folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2ced0-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="2ced0-125">Sie ordnen eine große Anzahl von Knotenpfaden zu.</span><span class="sxs-lookup"><span data-stu-id="2ced0-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="2ced0-126">Sie unterstützen Abfragen für unbekannte Elemente oder Elemente in einer unbekannten Position in der Dokumentstruktur.</span><span class="sxs-lookup"><span data-stu-id="2ced0-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="2ced0-127">Einfaches Beispiel für einen selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="2ced0-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="2ced0-128">Betrachten Sie das folgende XML-Fragment, das ein XML-Dokument in einer Tabelle mit ungefähr 500.000 Zeilen darstellt:</span><span class="sxs-lookup"><span data-stu-id="2ced0-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="2ced0-129">Die Erstellung eines primären XML-Index über so viele Zeilen dieses einfachen Schemas hinweg dauert sehr lange.</span><span class="sxs-lookup"><span data-stu-id="2ced0-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="2ced0-130">Die Abfrage dieser Daten wird zusätzlich noch dadurch erschwert, dass ein primärer XML-Index keine selektive Indizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="2ced0-131">Wenn Sie diese Daten nur über den `/book/title` -Pfad und den `/book/subjects` -Pfad abfragen müssen, können Sie den folgenden selektiven XML-Index erstellen:</span><span class="sxs-lookup"><span data-stu-id="2ced0-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="2ced0-132">Die vorangehende Anweisung ist ein gutes Beispiel für die CREATE-Syntax, die Sie zum Erstellen eines selektiven XML-Index verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="2ced0-133">Sie geben in der CREATE-Anweisung zuerst einen Namen für den Index an und identifizieren die Tabelle und die XML-Spalte, die Sie indizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="2ced0-134">Anschließend stellen Sie die zu indizierende Pfade bereit.</span><span class="sxs-lookup"><span data-stu-id="2ced0-134">Then you provide the paths to index.</span></span> <span data-ttu-id="2ced0-135">Ein Pfad besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="2ced0-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="2ced0-136">Einem Namen, der den Pfad eindeutig angibt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="2ced0-137">Einem XQuery-Ausdruck, der den Pfad beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="2ced0-138">Optionalen Optimierungshinweise.</span><span class="sxs-lookup"><span data-stu-id="2ced0-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="2ced0-139">Weitere Informationen zu diesen Elementen finden Sie unter [Verwandte Aufgaben](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="2ced0-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="2ced0-140">Unterstützte Funktionen, Voraussetzungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2ced0-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="2ced0-141">Unterstützte XML-Funktionen</span><span class="sxs-lookup"><span data-stu-id="2ced0-141">Supported XML Features</span></span>  
 <span data-ttu-id="2ced0-142">Selektive XML-Indizes unterstützen die XQuery, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in den exist()-, value()- und nodes()-Methoden unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="2ced0-143">Für die exist()-, value()- und nodes()-Methoden enthalten selektive XML-Indizes ausreichende Informationen, um den gesamten Ausdruck zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="2ced0-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="2ced0-144">Für die query()- und modify()-Methoden können selektive XML-Indizes möglicherweise nur zum Filtern von Knoten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="2ced0-145">Für die query()-Methode werden selektive XML-Indizes nicht zum Abrufen von Ergebnissen verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ced0-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="2ced0-146">Für die modify()-Methode werden selektive XML-Indizes nicht zum Aktualisieren von XML-Dokumenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ced0-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="2ced0-147">Nicht unterstützte XML-Funktionen</span><span class="sxs-lookup"><span data-stu-id="2ced0-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="2ced0-148">Selektive XML-Indizes unterstützen nicht die folgenden Funktionen, die in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Implementierung von XML unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="2ced0-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="2ced0-149">Indizieren von Knoten mit komplexen XS-Typen: Union-Typen, Sequenztypen, und Listtypen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="2ced0-150">Indizieren von Knoten mit binären XS-Typen: z. B. base64Binary und hexBinary.</span><span class="sxs-lookup"><span data-stu-id="2ced0-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="2ced0-151">Angeben von Knoten, die mit XPath-Ausdrücken indiziert werden sollen und am Ende das Platzhalterzeichen `*` aufweisen: z. B. `/a/b/c/*`, `/a//b/*` oder `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="2ced0-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="2ced0-152">Indizieren einer anderen Achse als untergeordnetes Element, Attribut oder Nachfolger.</span><span class="sxs-lookup"><span data-stu-id="2ced0-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="2ced0-153">Der `//<step>` -Fall ist als spezieller Fall zulässig.</span><span class="sxs-lookup"><span data-stu-id="2ced0-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="2ced0-154">Indizieren von XML-Verarbeitungsanweisungen und -Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="2ced0-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="2ced0-155">Angeben und Abrufen des Bezeichners für einen Knoten mit der id()-Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ced0-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="2ced0-156">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2ced0-156">Prerequisites</span></span>  
 <span data-ttu-id="2ced0-157">Die folgenden Voraussetzungen müssen erfüllt sein, bevor Sie einen selektiven XML-Index für eine XML-Spalte in einer Benutzertabelle erstellen können:</span><span class="sxs-lookup"><span data-stu-id="2ced0-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="2ced0-158">Für den Primärschlüssel der Benutzertabelle muss ein gruppierter Index vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2ced0-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="2ced0-159">Der Primärschlüssel der Benutzertabelle ist auf eine Größe von 128 Byte beschränkt, wenn er zusammen mit selektiven XML-Indizes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ced0-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="2ced0-160">Der Gruppierungsschlüssel der Benutzertabelle ist auf 15 Spalten beschränkt, wenn er zusammen mit selektiven XML-Indizes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ced0-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="2ced0-161">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2ced0-161">Limitations</span></span>  
 <span data-ttu-id="2ced0-162">**Allgemeine Anforderungen und Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="2ced0-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="2ced0-163">Jeder selektive XML-Index kann nur für eine einzige XML-Spalte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="2ced0-164">Für eine Spalte, die keine XML-Spalte ist, kann kein selektiver XML-Index erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="2ced0-165">Jede XML-Spalte in einer Tabelle kann nur über einen selektiven XML-Index verfügen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="2ced0-166">Jede Tabelle kann bis zu 249 selektive XML-Indizes enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="2ced0-167">**Einschränkungen für unterstützte Objekte**</span><span class="sxs-lookup"><span data-stu-id="2ced0-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="2ced0-168">Für die folgenden Objekte können keine selektiven XML-Indizes erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="2ced0-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="2ced0-169">XML-Spalten in einer Sicht.</span><span class="sxs-lookup"><span data-stu-id="2ced0-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="2ced0-170">Tabellenwertvariable mit XML-Spalten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="2ced0-171">XML-Typvariablen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="2ced0-172">Berechnete XML Spalten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="2ced0-173">XML-Spalten mit einer Tiefe von mehr als 128 geschachtelten Knoten.</span><span class="sxs-lookup"><span data-stu-id="2ced0-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="2ced0-174">**Auf Speicher bezogene Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="2ced0-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="2ced0-175">Die Anzahl der Knoten aus dem XML-Dokument, die dem Index hinzugefügt werden können, ist beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="2ced0-176">Ein selektiver XML-Index ordnet XML-Dokumente einer einzelnen relationalen Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="2ced0-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="2ced0-177">Daher kann er nicht mehr als 1024 Spalten mit Nicht-NULL-Werten in den Spalten der Tabelle aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2ced0-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="2ced0-178">Weiterhin gelten viele der Einschränkungen von Sparsespalten auch für selektive XML-Indizes, da die Indizes Sparsespalten zum Speichern verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="2ced0-179">Die maximale Anzahl von Nicht-NULL-Spalten, die in einer Zeile unterstützt werden, hängt von der Größe der Daten in den Spalten ab:</span><span class="sxs-lookup"><span data-stu-id="2ced0-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="2ced0-180">Im besten Fall werden 1024 Nicht-NULL-Spalten unterstützt, wenn alle Spalten den Typ **bit**haben.</span><span class="sxs-lookup"><span data-stu-id="2ced0-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="2ced0-181">Im schlimmsten Fall werden nur 236 Nicht-NULL-Spalten unterstützt, wenn alle Spalten große Objekte des Typs **varchar**sind.</span><span class="sxs-lookup"><span data-stu-id="2ced0-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="2ced0-182">Selektive XML-Indizes verwenden intern ein bis vier Spalten für jeden Knotenpfad, der indiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2ced0-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="2ced0-183">Die Gesamtzahl der Knoten, die indizierte werden können, reicht von 60 bis zu mehreren hundert Knoten, abhängig von der tatsächlichen Größe der Daten in den indizierten Pfaden.</span><span class="sxs-lookup"><span data-stu-id="2ced0-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="2ced0-184">Im schlimmsten Fall, wenn einige oder alle Knoten in der Knotenpfaddefinition mit `//` zugeordnet sind, beträgt die maximale Anzahl indizierter Knoten 60.</span><span class="sxs-lookup"><span data-stu-id="2ced0-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="2ced0-185">Im besten Fall, wenn Knoten ohne `//` in der Knotenpfaddefinition zugeordnet werden, beträgt die maximale Anzahl indizierter Knoten 200.</span><span class="sxs-lookup"><span data-stu-id="2ced0-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="2ced0-186">**Selektive XML-Indizes werden neu erstellt, wenn Sie CREATE oder ALTER für den Index ausführen.**</span><span class="sxs-lookup"><span data-stu-id="2ced0-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="2ced0-187">Wenn Sie einen selektiven XML-Index erstellen (CREATE) oder ändern (ALTER), wird er im Singlethread-Offlinemodus neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="2ced0-188">Die häufige Verwendung von ALTER-Anweisungen wirkt sich negativ auf die Leistung von Abfragen für die XML-Dokumente aus.</span><span class="sxs-lookup"><span data-stu-id="2ced0-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="2ced0-189">**Weitere Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="2ced0-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="2ced0-190">Selektive XML-Indizes werden nicht in Abfragehinweisen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="2ced0-191">Selektive XML-Indizes und sekundäre selektive XML-Indizes werden nicht vom Datenbankoptimierungsratgeber unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ced0-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="2ced0-192">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2ced0-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ced0-193">**Aufgabe**</span><span class="sxs-lookup"><span data-stu-id="2ced0-193">**Task**</span></span>|<span data-ttu-id="2ced0-194">**Thema**</span><span class="sxs-lookup"><span data-stu-id="2ced0-194">**Topic**</span></span>|  
|<span data-ttu-id="2ced0-195">Angeben der zu indizierenden Knotenpfade und optionalen Optimierungshinweise, wenn Sie einen selektiven XML-Index erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="2ced0-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="2ced0-196">Angeben von Pfaden und Optimierungshinweisen für selektive XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="2ced0-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="2ced0-197">Erstellen, Ändern oder Löschen eines selektiven XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="2ced0-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="2ced0-198">Erstellen, Ändern und Löschen selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="2ced0-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="2ced0-199">Erstellen, Ändern oder Löschen eines sekundären selektiven XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="2ced0-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="2ced0-200">Erstellen, Ändern und Löschen sekundärer, selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="2ced0-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
