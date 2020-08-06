---
title: TYPE-Direktive in FOR XML-Abfragen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622450"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="77a76-102">TYPE-Direktive in FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="77a76-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="77a76-103">durch die Unterstützung der [XML-&#40;Transact-SQL-&#41;](/sql/t-sql/xml/xml-transact-sql) können Sie optional anfordern, dass das Ergebnis einer for XML-Abfrage als-Datentyp zurückgegeben wird, `xml` indem Sie die Type-Direktive angeben.</span><span class="sxs-lookup"><span data-stu-id="77a76-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="77a76-104">Dies ermöglicht Ihnen, das Ergebnis einer FOR XML-Abfrage auf dem Server zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="77a76-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="77a76-105">Sie können z. b. eine XQuery dafür angeben, das Ergebnis einer `xml` Typvariablen zuweisen oder [für XML-Abfragen eingefügte](use-nested-for-xml-queries.md)Daten schreiben.</span><span class="sxs-lookup"><span data-stu-id="77a76-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="77a76-106">gibt Instanzdaten vom Datentyp `xml` als Ergebnis verschiedener Serverkonstrukte wie FOR XML-Abfragen, die die TYPE-Direktive verwenden, an den Client zurück, oder um XML-Instanzdatenwerte aus SQL-Tabellen und Ausgabeparametern zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="77a76-106">returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="77a76-107">Im Code der Clientanwendung erfordert der ADO.NET-Anbieter, dass die Informationen vom XML-Datentyp im Binärcode vom Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="77a76-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="77a76-108">Wenn Sie jedoch FOR XML ohne die TYPE-Direktive verwenden, werden die XML-Daten als Zeichenfolgentyp zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="77a76-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="77a76-109">Der Clientanbieter ist in jedem Fall fähig, beide XML-Formate zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="77a76-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="77a76-110">Beachten Sie, dass FOR XML der obersten Ebene ohne die TYPE-Direktive nicht mit Cursorn verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="77a76-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="77a76-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="77a76-111">Examples</span></span>  
 <span data-ttu-id="77a76-112">Die folgenden Beispiele veranschaulichen die Verwendung der TYPE-Direktive für FOR XML-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="77a76-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="77a76-113">Abrufen von FOR XML-Abfrageergebnissen als XML-Typ</span><span class="sxs-lookup"><span data-stu-id="77a76-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="77a76-114">Die folgende Abfrage ruft Informationen zu Kundenkontakten aus der `Contacts` -Tabelle auf.</span><span class="sxs-lookup"><span data-stu-id="77a76-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="77a76-115">In `TYPE` ist die `FOR XML`-Direktive angegeben, daher wird das Ergebnis als `xml`-Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77a76-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="77a76-116">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="77a76-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="77a76-117">Zuweisen von FOR XML-Abfrageergebnissen zu einer Variablen vom Typ XML</span><span class="sxs-lookup"><span data-stu-id="77a76-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="77a76-118">Im folgenden Beispiel wird das Ergebnis einer FOR XML-Abfrage einer Variablen vom Typ `xml`, `@x`, zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="77a76-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="77a76-119">Die Abfrage ruft die Kontaktinformationen, wie z `BusinessEntityID` . b `FirstName` .,, `LastName` , sowie zusätzliche Telefonnummern aus der `AdditionalContactInfo` Spalte von ab `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="77a76-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="77a76-120">Die XML-Daten werden als `xml`-Typ zurückgegeben, da in der `FOR XML`-Klausel die `TYPE`-Direktive angegeben ist, und anschließend einer Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="77a76-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="77a76-121">Abfragen von Ergebnissen einer FOR XML-Abfrage</span><span class="sxs-lookup"><span data-stu-id="77a76-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="77a76-122">FOR XML-Abfragen geben XML-Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="77a76-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="77a76-123">Folglich können Sie auf das von FOR XML-Abfragen zurückgegebene XML-Ergebnis Methoden vom Typ `xml` wie `query()` und `value()` anwenden.</span><span class="sxs-lookup"><span data-stu-id="77a76-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="77a76-124">In der folgenden Abfrage wird die `query()`-Methode vom Datentyp `xml` verwendet, um das Ergebnis einer `FOR XML`-Abfrage abzufragen.</span><span class="sxs-lookup"><span data-stu-id="77a76-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="77a76-125">Weitere Informationen finden Sie unter [query&#40;&#41;-Methode &#40;xml-Datentyp&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="77a76-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="77a76-126">Die innere `SELECT ... FOR XML`-Abfrage gibt ein Ergebnis vom Typ `xml` zurück, auf das das äußere `SELECT` die `query()`-Methode vom Typ `xml` anwendet.</span><span class="sxs-lookup"><span data-stu-id="77a76-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="77a76-127">Beachten Sie, dass die `TYPE` -Direktive angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="77a76-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="77a76-128">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="77a76-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="77a76-129">In der folgenden Abfrage wird die `value()`-Methode vom Datentyp `xml` verwendet, um einen Wert aus dem XML-Ergebnis einer `SELECT...FOR XML`-Abfrage abzurufen.</span><span class="sxs-lookup"><span data-stu-id="77a76-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="77a76-130">Weitere Informationen finden Sie unter [value&#40;&#41;-Methode &#40;xml-Datentyp&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="77a76-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="77a76-131">Der XQuery-Pfadausdruck in der `value()` -Methode ruft die erste Telefonnummer des Kundenkontakts mit der `BusinessEntityID``1`ab.</span><span class="sxs-lookup"><span data-stu-id="77a76-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77a76-132">Wenn die TYPE-Direktive nicht angegeben ist, wird das Ergebnis der FOR XML-Abfrage als `nvarchar(max)` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="77a76-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="77a76-133">Verwenden von FOR XML-Abfrageergebnissen in INSERT-, UPDATE- und DELETE-Anweisungen (Transact-SQL-DML)</span><span class="sxs-lookup"><span data-stu-id="77a76-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="77a76-134">Das folgende Beispiel stellt dar, wie FOR XML-Abfragen in DML-Anweisungen (DML, Data Manipulation Language) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="77a76-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="77a76-135">In diesem Beispiel gibt die `FOR XML`-Abfrage eine Instanz vom Typ `xml` zurück.</span><span class="sxs-lookup"><span data-stu-id="77a76-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="77a76-136">Die `INSERT` -Anweisung fügt diese XML-Daten in eine Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="77a76-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="77a76-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77a76-137">See Also</span></span>  
 [<span data-ttu-id="77a76-138">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77a76-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
