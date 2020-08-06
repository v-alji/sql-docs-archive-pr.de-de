---
title: Erstellen von Sichten über XML-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- views [XML in SQL Server]
ms.assetid: eb5f0439-1f69-49c2-8759-e59bda1633b7
author: rothja
ms.author: jroth
ms.openlocfilehash: bf06f1107cbf4875eb63fe6747775b5c5c04810c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722614"
---
# <a name="create-views-over-xml-columns"></a><span data-ttu-id="4a3b6-102">Erstellen von Sichten über XML-Spalten</span><span class="sxs-lookup"><span data-stu-id="4a3b6-102">Create Views over XML Columns</span></span>
  <span data-ttu-id="4a3b6-103">Sie können eine Spalte vom Typ `xml` zum Erstellen von Sichten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-103">You can use an `xml` type column to create views.</span></span> <span data-ttu-id="4a3b6-104">Im folgenden Beispiel wird eine Sicht erstellt, in der mithilfe der `value()`-Methode des `xml`-Datentyps der Wert aus einer Spalte vom Typ `xml` abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-104">The following example creates a view in which the value from an `xml` type column is retrieved using the `value()` method of the `xml` data type.</span></span>  
  
```  
-- Create the table.  
CREATE TABLE T (  
    ProductID          int primary key,   
    CatalogDescription xml)  
GO  
-- Insert sample data.  
INSERT INTO T values(1,'<ProductDescription ProductID="1" ProductName="SomeName" />')  
GO  
-- Create view (note the value() method used to retrieve ProductName   
-- attribute value from the XML).  
CREATE VIEW MyView AS   
  SELECT ProductID,  
         CatalogDescription.value('(/ProductDescription/@ProductName)[1]', 'varchar(40)') AS PName  
  FROM T  
GO   
```  
  
 <span data-ttu-id="4a3b6-105">Führen Sie die folgende Abfrage für die Sicht aus:</span><span class="sxs-lookup"><span data-stu-id="4a3b6-105">Execute the following query against the view:</span></span>  
  
```  
SELECT *   
FROM   MyView  
```  
  
 <span data-ttu-id="4a3b6-106">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="4a3b6-106">This is the result:</span></span>  
  
```  
ProductID   PName        
----------- ------------  
1           SomeName   
```  
  
 <span data-ttu-id="4a3b6-107">Beachten Sie die folgenden Punkte in Bezug auf das Erstellen von Sichten mit dem `xml`-Datentyp:</span><span class="sxs-lookup"><span data-stu-id="4a3b6-107">Note the following points about using the `xml` data type to create views:</span></span>  
  
-   <span data-ttu-id="4a3b6-108">Der XML-Datentyp kann in einer materialisierten Sicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-108">The xml data type can be created in a materialized view.</span></span> <span data-ttu-id="4a3b6-109">Die materialisierte Sicht kann nicht auf einer xml-Datentypmethode basieren.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-109">The materialized view cannot be based on an xml data type method.</span></span> <span data-ttu-id="4a3b6-110">Er kann jedoch in eine XML-Schemaauflistung umgewandelt werden, die sich von der XML-Typspalte der Basistabelle unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-110">However, it can be cast to an XML schema collection that is different from the xml type column in the base table.</span></span>  
  
-   <span data-ttu-id="4a3b6-111">Der `xml`-Datentyp kann nicht in verteilten partitionierten Sichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-111">The `xml` data type cannot be used in Distributed Partitioned Views.</span></span>  
  
-   <span data-ttu-id="4a3b6-112">SQL-Prädikate, die für die Sicht ausgeführt werden, werden nicht in die XQuery der Sichtdefinition verschoben.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-112">SQL predicates running against the view will not be pushed into the XQuery of the view definition.</span></span>  
  
-   <span data-ttu-id="4a3b6-113">XML-Datentypmethoden in einer Sicht sind nicht aktualisierbar.</span><span class="sxs-lookup"><span data-stu-id="4a3b6-113">XML data type methods in a view are not updatable.</span></span>  
  
  
