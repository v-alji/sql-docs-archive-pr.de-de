---
title: Generieren von XML aus Rowsets mit FOR XML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726738"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="53def-102">Generieren von XML aus Rowsets mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="53def-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="53def-103">Sie können eine- `xml` Datentyp Instanz aus einem Rowset generieren, indem Sie for XML mit der neuen **Type** -Direktive verwenden.</span><span class="sxs-lookup"><span data-stu-id="53def-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="53def-104">Das Ergebnis kann einer `xml` Spalte, einer Variablen oder einem Parameter des Datentyps zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="53def-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="53def-105">Außerdem kann FOR XML geschachtelt werden, um jede beliebige hierarchische Struktur zu generieren.</span><span class="sxs-lookup"><span data-stu-id="53def-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="53def-106">Damit kann geschachteltes FOR XML viel bequemer geschrieben werden als FOR XML EXPLICIT, es zeigt aber möglicherweise eine weniger gute Leistung bei tiefen Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="53def-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="53def-107">FOR XML führt auch einen neuen PATH-Modus ein.</span><span class="sxs-lookup"><span data-stu-id="53def-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="53def-108">Dieser neue Modus gibt den Pfad im XML-Baum an, in dem der Wert einer Spalte erscheint.</span><span class="sxs-lookup"><span data-stu-id="53def-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="53def-109">Die neue **FOR XML TYPE** -Direktive kann verwendet werden, um schreibgeschützte XML-Sichten für relationale Daten mit SQL-Syntax zu definieren.</span><span class="sxs-lookup"><span data-stu-id="53def-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="53def-110">Die Sicht kann mit SQL-Anweisungen und eingebettetem XQuery abgefragt werden, wie das im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="53def-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="53def-111">Sie können auf diese SQL-Sichten auch in gespeicherten Prozeduren verweisen.</span><span class="sxs-lookup"><span data-stu-id="53def-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="53def-112">Beispiel: SQL-Ansicht zum Zurückgeben des generierten xml-Datentyps</span><span class="sxs-lookup"><span data-stu-id="53def-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="53def-113">Die folgende SQL-Sichtdefinition erstellt eine XML-Sicht für eine relationale Spalte pk und ruft die Buchautoren aus einer XML-Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="53def-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="53def-114">Die V-Sicht enthält eine einzelne Zeile mit einem einzelnen columnxmlval des XML-Typs `.` . diese kann wie eine reguläre `xml` Datentyp Instanz abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="53def-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="53def-115">Beispielsweise gibt die folgende Abfrage den Autor zurück, dessen Vorname "David" ist:</span><span class="sxs-lookup"><span data-stu-id="53def-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="53def-116">SQL-Sichtdefinitionen ähneln in gewisser Weise XML-Sichten, indem Sie durch Verwenden von Schemas mit Anmerkungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="53def-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="53def-117">Es gibt jedoch auch wichtige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="53def-117">However, there are important differences.</span></span> <span data-ttu-id="53def-118">Die SQL-Sichtdefinition ist schreibgeschützt und muss mit eingebettetem XQuery bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="53def-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="53def-119">Die XML-Sichten werden ebenfalls durch Verwenden von Schemas mit Anmerkungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="53def-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="53def-120">Darüber hinaus materialisiert die SQL-Sicht das XML-Ergebnis, bevor der XQuery-Ausdruck angewendet wird, während die XPath-Abfragen für XML-Sichten SQL-Abfragen für die zugrunde liegenden Tabellen auswerten.</span><span class="sxs-lookup"><span data-stu-id="53def-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53def-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53def-121">See Also</span></span>  
 [<span data-ttu-id="53def-122">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="53def-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
