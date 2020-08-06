---
title: Verwenden des AUTO-Modus mit FOR XML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, AUTO mode
- ELEMENTS option
- FOR XML AUTO mode
- AUTO FOR XML mode
ms.assetid: 7140d656-1d42-4f01-a533-5251429f4450
author: rothja
ms.author: jroth
ms.openlocfilehash: 232cc046667c6d31cb9657a7abdc862204507d23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618563"
---
# <a name="use-auto-mode-with-for-xml"></a><span data-ttu-id="c7081-102">Verwenden des AUTO-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="c7081-102">Use AUTO Mode with FOR XML</span></span>
  <span data-ttu-id="c7081-103">Wie in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md)beschrieben, gibt der AUTO-Modus Abfrageergebnisse als geschachtelte XML-Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="c7081-103">As described in [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md), AUTO mode returns query results as nested XML elements.</span></span> <span data-ttu-id="c7081-104">Damit ist jedoch keine genaue Steuerungsmöglichkeit über die Form des XML-Codes gegeben, der aus einem Abfrageergebnis generiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7081-104">This does not provide much control over the shape of the XML generated from a query result.</span></span> <span data-ttu-id="c7081-105">Die AUTO-Modusabfragen sind nützlich, wenn Sie einfache Hierarchien generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c7081-105">The AUTO mode queries are useful if you want to generate simple hierarchies.</span></span> <span data-ttu-id="c7081-106">Allerdings können Sie durch [Verwenden des EXPLICIT-Modus mit FOR XML](use-explicit-mode-with-for-xml.md) und [Verwenden des PATH-Modus mit FOR XML](use-path-mode-with-for-xml.md) bessere Steuerungsmöglichkeiten und eine höhere Flexibilität in Bezug auf die Form des aus einem Abfrageergebnis generierten XML-Codes erzielen.</span><span class="sxs-lookup"><span data-stu-id="c7081-106">However, [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) and [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) provide more control and flexibility in deciding the shape of the XML from a query result.</span></span>  
  
 <span data-ttu-id="c7081-107">Jede Tabelle in der FROM-Klausel, aus der mindestens eine Spalte in der SELECT-Klausel aufgeführt ist, wird als ein XML-Element dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c7081-107">Each table in the FROM clause, from which at least one column is listed in the SELECT clause, is represented as an XML element.</span></span> <span data-ttu-id="c7081-108">Die in der SELECT-Klausel aufgelisteten Spalten werden den entsprechenden Attributen oder Unterelementen zugeordnet, wenn die wahlweise Option ELEMENTS in der FOR XML-Klausel angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c7081-108">The columns listed in the SELECT clause are mapped to attributes or subelements, if the optional ELEMENTS option is specified in the FOR XML clause.</span></span>  
  
 <span data-ttu-id="c7081-109">Die XML-Hierarchie, also die Schachtelung der Elemente, im resultierenden XML-Code basiert auf der Tabellenreihenfolge, die durch die Spalten identifiziert wird, die in der SELECT-Klausel angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c7081-109">The XML hierarchy, nesting of the elements, in the resulting XML is based on the order of tables identified by the columns specified in the SELECT clause.</span></span> <span data-ttu-id="c7081-110">Deshalb ist die Reihenfolge, in der die Spaltennamen in der SELECT-Klausel angegeben werden, von großer Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="c7081-110">Therefore, the order in which column names are specified in the SELECT clause is significant.</span></span> <span data-ttu-id="c7081-111">Die erste identifizierte Tabelle von links bildet das oberste Element in dem resultierenden XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="c7081-111">The first, leftmost table that is identified forms the top element in the resulting XML document.</span></span> <span data-ttu-id="c7081-112">Die zweite Tabelle von links (identifiziert durch die Spalten in der SELECT-Anweisung) bildet ein Unterelement im obersten Element usw.</span><span class="sxs-lookup"><span data-stu-id="c7081-112">The second leftmost table, identified by columns in the SELECT statement, forms a subelement within the top element, and so on.</span></span>  
  
 <span data-ttu-id="c7081-113">Falls ein in der SELECT-Klausel aufgeführter Spaltenname aus einer Tabelle stammt, die bereits durch eine zuvor angegebene Spalte in der SELECT-Klausel identifiziert wird, wird die Spalte als Attribut zu dem bereits erstellten Element hinzugefügt. Es wird also keine neue Ebene der Hierarchie geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c7081-113">If a column name listed in the SELECT clause is from a table that is already identified by a previously specified column in the SELECT clause, the column is added as an attribute of the element already created, instead of opening a new level of hierarchy.</span></span> <span data-ttu-id="c7081-114">Wenn die Option ELEMENTS angegeben ist, wird die Spalte als Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-114">If the ELEMENTS option is specified, the column is added as an attribute.</span></span>  
  
 <span data-ttu-id="c7081-115">Führen Sie z. B. die folgende Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="c7081-115">For example, execute this query:</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO  
```  
  
 <span data-ttu-id="c7081-116">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="c7081-116">This is the partial result:</span></span>  
  
```  
<Cust CustomerID="1" CustomerType="S">  
  <OrderHeader CustomerID="1" SalesOrderID="43860" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="44501" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="45283" Status="5" />  
  <OrderHeader CustomerID="1" SalesOrderID="46042" Status="5" />  
</Cust>  
...  
```  
  
 <span data-ttu-id="c7081-117">Beachten Sie in der SELECT-Klausel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c7081-117">Note the following in the SELECT clause:</span></span>  
  
-   <span data-ttu-id="c7081-118">Die CustomerID verweist auf die Cust-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c7081-118">The CustomerID references the Cust table.</span></span> <span data-ttu-id="c7081-119">Deshalb wird ein <`Cust`>-Element erstellt, dem CustomerID als Attribut hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c7081-119">Therefore, a <`Cust`> element is created and CustomerID is added as its attribute.</span></span>  
  
-   <span data-ttu-id="c7081-120">Als Nächstes verweisen die drei Spalten OrderHeader.CustomerID, OrderHeader.SaleOrderID und OrderHeader.Status auf die OrderHeader-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c7081-120">Next, three columns, OrderHeader.CustomerID, OrderHeader.SaleOrderID, and OrderHeader.Status, reference the OrderHeader table.</span></span> <span data-ttu-id="c7081-121">Deshalb wird ein <`OrderHeader`>-Element als Unterelement des <`Cust`>-Elements hinzugefügt, und die drei Spalten werden als Attribute von <`OrderHeader`> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-121">Therefore, an <`OrderHeader`> element is added as a subelement of the <`Cust`> element and the three columns are added as attributes of <`OrderHeader`>.</span></span>  
  
-   <span data-ttu-id="c7081-122">Als Nächstes verweist die Cust.CustomerType-Spalte erneut auf die Cust-Tabelle, die bereits durch die Cust.CustomerID-Spalte identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7081-122">Next, the Cust.CustomerType column again references the Cust table that was already identified by the Cust.CustomerID column.</span></span> <span data-ttu-id="c7081-123">Aus diesem Grund wird kein neues Element erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7081-123">Therefore, no new element is created.</span></span> <span data-ttu-id="c7081-124">Stattdessen wird das CustomerType-Attribut zum zuvor erstellten <`Cust`>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-124">Instead, the CustomerType attribute is added to the <`Cust`> element that was previously created.</span></span>  
  
-   <span data-ttu-id="c7081-125">Die Abfrage gibt Aliasnamen für die Tabellennamen an.</span><span class="sxs-lookup"><span data-stu-id="c7081-125">The query specifies aliases for the table names.</span></span> <span data-ttu-id="c7081-126">Diese Aliasnamen erscheinen als die entsprechenden Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="c7081-126">These aliases appear as corresponding element names.</span></span>  
  
-   <span data-ttu-id="c7081-127">ORDER BY ist erforderlich, um alle untergeordneten Elemente unter einem übergeordneten Element zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="c7081-127">ORDER BY is required to group all children under one parent.</span></span>  
  
 <span data-ttu-id="c7081-128">Diese Abfrage gleicht der vorherigen Abfrage, außer dass in der SELECT-Klausel die Spalten in der OrderHeader-Tabelle vor den Spalten in der Cust-Tabelle angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c7081-128">This query is similar to the previous one, except the SELECT clause specifies columns in the OrderHeader table before the columns in the Cust table.</span></span> <span data-ttu-id="c7081-129">Deshalb wird zuerst das <`OrderHeader`>-Element erstellt und erst danach wird diesem Element das untergeordnete <`Cust`>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-129">Therefore, first <`OrderHeader`> element is created and then the <`Cust`> child element is added to it.</span></span>  
  
```  
select OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerID,   
       Cust.CustomerType  
from Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
where Cust.CustomerID = OrderHeader.CustomerID  
for xml auto  
```  
  
 <span data-ttu-id="c7081-130">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="c7081-130">This is the partial result:</span></span>  
  
```  
<OrderHeader CustomerID="1" SalesOrderID="43860" Status="5">  
  <Cust CustomerID="1" CustomerType="S" />  
</OrderHeader>  
...  
```  
  
 <span data-ttu-id="c7081-131">Wenn die Option ELEMENTS der FOR XML-Klausel hinzugefügt wird, wird elementzentriertes XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7081-131">If the ELEMENTS option is added in the FOR XML clause, element-centric XML is returned.</span></span>  
  
```  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status,  
       Cust.CustomerType  
FROM Sales.Customer Cust, Sales.SalesOrderHeader OrderHeader  
WHERE Cust.CustomerID = OrderHeader.CustomerID  
ORDER BY Cust.CustomerID  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="c7081-132">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="c7081-132">This is the partial result:</span></span>  
  
```  
<Cust>  
  <CustomerID>1</CustomerID>  
  <CustomerType>S</CustomerType>  
  <OrderHeader>  
    <CustomerID>1</CustomerID>  
    <SalesOrderID>43860</SalesOrderID>  
    <Status>5</Status>  
  </OrderHeader>  
   ...  
</Cust>  
...  
```  
  
 <span data-ttu-id="c7081-133">In dieser Abfrage werden die CustomerID-Werte aus einer Zeile mit denen in der nächsten verglichen, wenn die \<Cust>-Elemente erstellt werden, weil CustomerID der Primärschlüssel der Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="c7081-133">In this query, the CustomerID values are compared from one row to the next in creating the \<Cust> elements, because CustomerID is the primary key of the table.</span></span> <span data-ttu-id="c7081-134">Wenn CustomerID nicht als Primärschlüssel für die Tabelle identifiziert wurde, werden alle Spaltenwerte (in dieser Abfrage CustomerID und CustomerType) aus einer Zeile mit denen in der nächsten Zeile verglichen.</span><span class="sxs-lookup"><span data-stu-id="c7081-134">If CustomerID is not identified as the primary key for the table, all the column values (CustomerID, CustomerType in this query) are compared from one row to the next.</span></span> <span data-ttu-id="c7081-135">Wenn die Werte voneinander abweichen, wird dem XML-Code ein neues \<Cust>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-135">If the values differ, a new \<Cust> element is added to the XML.</span></span>  
  
 <span data-ttu-id="c7081-136">Wenn beim Vergleichen dieser Spaltenwerte eine der miteinander zu vergleichenden Spalten den Datentyp **text**, **ntext**, **image**oder **xml**aufweist, nimmt FOR XML an, dass die Werte sich unterscheiden und nicht miteinander verglichen werden, obwohl sie sich gleichen können.</span><span class="sxs-lookup"><span data-stu-id="c7081-136">When comparing these column values, if any of the columns to be compared are of type **text**, **ntext**, **image**, or **xml**, FOR XML assumes that the values are different and not compared, even though they may be the same.</span></span> <span data-ttu-id="c7081-137">Das liegt daran, dass das Vergleichen von großen Objekten nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c7081-137">This is because comparing large objects is not supported.</span></span> <span data-ttu-id="c7081-138">Für jede ausgewählte Zeile werden die Elemente dem Ergebnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-138">Elements are added to the result for each row selected.</span></span> <span data-ttu-id="c7081-139">Beachten Sie, dass die Spalten des Datentyps **(n)varchar(max)** und **varbinary(max)** verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="c7081-139">Note that columns of **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="c7081-140">Wenn eine Spalte in der SELECT-Klausel nicht einer der in der FROM-Klausel identifizierten Tabellen zugeordnet werden kann (z. B. bei Aggregatspalten oder berechneten Spalten), wird die Spalte dem XML-Dokument in der tiefsten Schachtelungsebene hinzugefügt, wenn sie in der Liste entdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="c7081-140">When a column in the SELECT clause cannot be associated with any of the tables identified in the FROM clause, as in the case of an aggregate column or computed column, the column is added in the XML document in the deepest nesting level in place when it is encountered in the list.</span></span> <span data-ttu-id="c7081-141">Wird eine solche Spalte als erste Spalte in der SELECT-Klausel aufgeführt, wird sie dem obersten Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c7081-141">If such a column appears as the first column in the SELECT clause, the column is added to the top element.</span></span>  
  
 <span data-ttu-id="c7081-142">Wenn das Platzhalterzeichen (\*) in der SELECT-Klausel angegeben wurde, wird die Schachtelung auf die gleiche Art wie oben beschrieben bestimmt (d. h. auf der Grundlage der Reihenfolge, in der die Zeilen von der Abfrage-Engine zurückgegeben werden).</span><span class="sxs-lookup"><span data-stu-id="c7081-142">If the asterisk (\*) wildcard character is specified in the SELECT clause, the nesting is determined in the same way as previously described, based on the order that the rows are returned by the query engine.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7081-143">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c7081-143">In This Section</span></span>  
 <span data-ttu-id="c7081-144">Die folgenden Themen enthalten weitere Informationen zum AUTO-Modus:</span><span class="sxs-lookup"><span data-stu-id="c7081-144">The following topics provide more information about AUTO mode:</span></span>  
  
-   [<span data-ttu-id="c7081-145">Verwenden der Option BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="c7081-145">Use the BINARY BASE64 Option</span></span>](use-the-binary-base64-option.md)  
  
-   [<span data-ttu-id="c7081-146">AUTO-Modus-Heuristik beim Ermitteln der Form des zurückgegebenen XML-Codes</span><span class="sxs-lookup"><span data-stu-id="c7081-146">AUTO Mode Heuristics in Shaping Returned XML</span></span>](auto-mode-heuristics-in-shaping-returned-xml.md)  
  
-   [<span data-ttu-id="c7081-147">Beispiele: Verwenden des AUTO-Modus</span><span class="sxs-lookup"><span data-stu-id="c7081-147">Examples: Using AUTO Mode</span></span>](examples-using-auto-mode.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7081-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7081-148">See Also</span></span>  
 <span data-ttu-id="c7081-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7081-149">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="c7081-150">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c7081-150">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
