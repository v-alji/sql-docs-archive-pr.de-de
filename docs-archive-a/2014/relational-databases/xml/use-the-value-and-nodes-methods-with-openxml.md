---
title: Verwenden der value()-Methode und der nodes()-Methode mit OPENXML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722582"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="3fce5-102">Verwenden der value()-Methode und der nodes()-Methode mit OPENXML</span><span class="sxs-lookup"><span data-stu-id="3fce5-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="3fce5-103">Sie können mehrere **value ()** -Methoden für `xml` den-Datentyp in einer **Select** -Klausel verwenden, um ein Rowset von extrahierten Werten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3fce5-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="3fce5-104">Die **nodes()** -Methode ergibt einen internen Verweis für jeden ausgewählten Knoten, der für zusätzliche Abfragen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fce5-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="3fce5-105">Die Kombination der Methoden **nodes()** und **value()** kann beim Generieren des Rowsets effizienter sein, wenn es über mehrere Spalten verfügt und möglicherweise auch, wenn die zu seiner Generierung verwendeten Pfadausdrücke komplex sind.</span><span class="sxs-lookup"><span data-stu-id="3fce5-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="3fce5-106">Die **Nodes ()** -Methode ergibt Instanzen eines besonderen `xml` Datentyps, von denen jeder den Kontext auf einen anderen ausgewählten Knoten festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="3fce5-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="3fce5-107">Diese Art der XML-Instanz unterstützt **query()** -, **value()** -, **nodes()** - und **exist()** -Methoden und kann in **count(\*)** -Aggregationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3fce5-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="3fce5-108">Alle anderen Verwendungen verursachen einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="3fce5-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="3fce5-109">Beispiel: Verwenden von nodes()</span><span class="sxs-lookup"><span data-stu-id="3fce5-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="3fce5-110">Angenommen, Sie wollen die Vornamen und Nachnamen von Autoren extrahieren, und der Vorname soll nicht "David" sein.</span><span class="sxs-lookup"><span data-stu-id="3fce5-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="3fce5-111">Außerdem wollen Sie diese Informationen als ein Rowset extrahieren, das die beiden Spalten FirstName und LastName enthält.</span><span class="sxs-lookup"><span data-stu-id="3fce5-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="3fce5-112">Durch Verwenden der Methoden **nodes()** und **value()** können Sie dieses Ziel erreichen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3fce5-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="3fce5-113">In diesem Beispiel ergibt `nodes('//author')` ein Rowset aus Verweisen auf `<author>` -Elemente für jede XML-Instanz.</span><span class="sxs-lookup"><span data-stu-id="3fce5-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="3fce5-114">Die Vor- und Nachnamen der Autoren werden abgerufen, indem die **value()** -Methoden im Verhältnis zu diesen Verweisen ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="3fce5-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="3fce5-115">SQL Server 2000 bietet die Möglichkeit zum Generieren eines Rowsets aus einer XML-Instanz durch Verwenden von **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="3fce5-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="3fce5-116">Sie können das relationale Schema für das Rowset angeben sowie, wie die Werte in der XML-Instanz den Spalten im Rowset zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3fce5-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="3fce5-117">Beispiel: Verwenden von OpenXml() für den XML-Datentyp</span><span class="sxs-lookup"><span data-stu-id="3fce5-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="3fce5-118">Die Abfrage aus dem vorherigen Beispiel kann mithilfe von **OpenXml()** umgeschrieben werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fce5-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="3fce5-119">Dies geschieht durch Erstellen eines Cursors, der jede XML-Instanz in eine XML-Variable einliest und dann für OpenXML auf sie anwendet:</span><span class="sxs-lookup"><span data-stu-id="3fce5-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="3fce5-120">**OpenXml()** erstellt eine arbeitsspeicherinterne Darstellung und verwendet Arbeitstabellen anstelle des Abfrageprozessors.</span><span class="sxs-lookup"><span data-stu-id="3fce5-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="3fce5-121">Sie greift nicht auf die XQuery-Engine zurück, sondern auf den XPath-Prozessor Version 1.0 von MSXML Version 3.0.</span><span class="sxs-lookup"><span data-stu-id="3fce5-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="3fce5-122">Die Arbeitstabellen werden nicht von mehreren Aufrufen von **OpenXml()** gemeinsam genutzt, selbst auf der gleichen XML-Instanz nicht.</span><span class="sxs-lookup"><span data-stu-id="3fce5-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="3fce5-123">Damit ist ihre Skalierbarkeit eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="3fce5-123">This limits its scalability.</span></span> <span data-ttu-id="3fce5-124">**OpenXml()** ermöglicht Ihnen das Zugreifen auf ein Rahmentabellenformat für die XML-Daten, wenn die WITH-Klausel nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3fce5-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="3fce5-125">Außerdem ermöglicht es Ihnen das Verwenden des übrigen XML-Wertes in einer getrennten "Überlaufspalte".</span><span class="sxs-lookup"><span data-stu-id="3fce5-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="3fce5-126">Die Kombination aus den **nodes()** - und **value()** -Funktionen sorgt für eine effektive XML-Indizierung.</span><span class="sxs-lookup"><span data-stu-id="3fce5-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="3fce5-127">Im Ergebnis kann diese Kombination eine größere Skalierbarkeit als **OpenXml**aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3fce5-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fce5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fce5-128">See Also</span></span>  
 [<span data-ttu-id="3fce5-129">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3fce5-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
