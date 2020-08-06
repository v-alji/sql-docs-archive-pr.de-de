---
title: Verwenden von XML in berechneten Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695446"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="4c9cb-102">Verwenden von XML in berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="4c9cb-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="4c9cb-103">XML-Instanzen können als Quelle für eine berechnete Spalte oder als Typ einer berechneten Spalte auftreten.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="4c9cb-104">In den Beispielen in diesem Thema wird gezeigt, wie XML mit berechneten Spalten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="4c9cb-105">Erstellen berechneter Spalten aus XML-Spalten</span><span class="sxs-lookup"><span data-stu-id="4c9cb-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="4c9cb-106">In der folgenden `CREATE TABLE` -Anweisung wird eine Spalte vom Typ `xml` (`col2`) aus `col1`berechnet:</span><span class="sxs-lookup"><span data-stu-id="4c9cb-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="4c9cb-107">Der `xml` -Datentyp kann auch als Quelle für das Erstellen einer berechneten Spalte dienen, wie es in der folgenden `CREATE TABLE` -Anweisung gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="4c9cb-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="4c9cb-108">Sie können eine berechnete Spalte erstellen, indem Sie einen Wert aus einer Spalte vom Typ `xml` extrahieren, wie es im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="4c9cb-109">Da die `xml`-Datentypmethoden nicht direkt zum Erstellen von berechneten Spalten verwendet werden können, wird in diesem Beispiel zunächst eine Funktion definiert (`my_udf`), die einen Wert aus einer XML-Instanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="4c9cb-110">Die Funktion dient als Wrapper für die `value()` -Methode des `xml` -Typs.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="4c9cb-111">Der Name der Funktion wird dann in der `CREATE TABLE` -Anweisung für die berechnete Spalte angegeben.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="4c9cb-112">Wie im vorherigen Beispiel wird auch im folgenden Beispiel eine Funktion definiert, um für eine berechnete Spalte eine Instanz des `xml`-Typs zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="4c9cb-113">Innerhalb der Funktion ruft die `query()` -Methode des `xml` -Datentyps einen Wert aus einem Parameter vom Typ `xml` ab.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="4c9cb-114">In der folgenden `CREATE TABLE` -Anweisung ist `Col2` eine berechnete Spalte, die die von der Funktion zurückgegebenen XML-Daten (das`<Features>` -Element) verwendet:</span><span class="sxs-lookup"><span data-stu-id="4c9cb-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="4c9cb-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4c9cb-115">In This Section</span></span>  
  
|<span data-ttu-id="4c9cb-116">Thema</span><span class="sxs-lookup"><span data-stu-id="4c9cb-116">Topic</span></span>|<span data-ttu-id="4c9cb-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4c9cb-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4c9cb-118">Heraufstufen häufig verwendeter XML-Werte mit berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="4c9cb-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="4c9cb-119">Beschreibt, wie die Eigenschaftenhöherstufung mit berechneten Spalten und Eigenschaftentabellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c9cb-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
