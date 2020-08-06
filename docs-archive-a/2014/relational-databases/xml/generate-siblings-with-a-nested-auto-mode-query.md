---
title: Generieren von gleichgeordneten Elementen mit einer geschachtelten AUTO-Modusabfrage
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- queries [XML in SQL Server], nested AUTO mode
- nested AUTO mode query
ms.assetid: 748d9899-589d-4420-8048-1258e9e67c20
author: rothja
ms.author: jroth
ms.openlocfilehash: 20362942bdd0f7e7537433b664e5e63461ded499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726741"
---
# <a name="generate-siblings-with-a-nested-auto-mode-query"></a><span data-ttu-id="d2dad-102">Generieren von gleichgeordneten Elementen mit einer geschachtelten AUTO-Modusabfrage</span><span class="sxs-lookup"><span data-stu-id="d2dad-102">Generate Siblings with a Nested AUTO Mode Query</span></span>
  <span data-ttu-id="d2dad-103">Im folgenden Beispiel wird das Generieren von gleichgeordneten Elementen durch Verwenden einer geschachtelten Abfrage im AUTO-Modus dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d2dad-103">The following example shows how to generate siblings by using a nested AUTO mode query.</span></span> <span data-ttu-id="d2dad-104">Die einzige Möglichkeit zum Generieren von derartigem XML-Code besteht im Verwenden des EXPLICIT-Modus.</span><span class="sxs-lookup"><span data-stu-id="d2dad-104">The only other way to generate such XML is to use the EXPLICIT mode.</span></span> <span data-ttu-id="d2dad-105">Dies kann jedoch sehr aufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="d2dad-105">However, this can be cumbersome.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2dad-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2dad-106">Example</span></span>  
 <span data-ttu-id="d2dad-107">Diese Abfrage konstruiert XML-Code, der Bestellinformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d2dad-107">This query constructs XML that provides sales order information.</span></span> <span data-ttu-id="d2dad-108">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="d2dad-108">This includes the following:</span></span>  
  
-   <span data-ttu-id="d2dad-109">Auftragskopfzeileninformationen, `SalesOrderID`, `SalesPersonID`und `OrderDate`.</span><span class="sxs-lookup"><span data-stu-id="d2dad-109">Sales order header information, `SalesOrderID`, `SalesPersonID`, and `OrderDate`.</span></span> [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="d2dad-110">speichert diese Informationen in der `SalesOrderHeader` -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d2dad-110">stores this information in the `SalesOrderHeader` table.</span></span>  
  
-   <span data-ttu-id="d2dad-111">Detaillierte Bestellinformationen.</span><span class="sxs-lookup"><span data-stu-id="d2dad-111">Sales order detail information.</span></span> <span data-ttu-id="d2dad-112">Dazu gehören Angaben zu einem oder mehreren bestellten Produkten, zum Einzelpreis und zur bestellten Menge.</span><span class="sxs-lookup"><span data-stu-id="d2dad-112">This includes one or more products ordered, the unit price, and the quantity ordered.</span></span> <span data-ttu-id="d2dad-113">Diese Informationen werden in der `SalesOrderDetail` -Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d2dad-113">This information is stored in the `SalesOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="d2dad-114">Informationen zum Vertriebsmitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="d2dad-114">Sales person information.</span></span> <span data-ttu-id="d2dad-115">Dies ist der Vertriebsmitarbeiter, der die Bestellung entgegengenommen hat.</span><span class="sxs-lookup"><span data-stu-id="d2dad-115">This is the salesperson who took the order.</span></span> <span data-ttu-id="d2dad-116">Die `SalesPerson` -Tabelle stellt die Angaben für `SalesPersonID`bereit.</span><span class="sxs-lookup"><span data-stu-id="d2dad-116">The `SalesPerson` table provides the `SalesPersonID`.</span></span> <span data-ttu-id="d2dad-117">Für diese Abfrage müssen Sie diese Tabelle mit der `Employee` -Tabelle verknüpfen, um den Namen des Vertriebsmitarbeiters zu finden.</span><span class="sxs-lookup"><span data-stu-id="d2dad-117">For this query, you have to join this table to the `Employee` table to find the name of the sales person.</span></span>  
  
 <span data-ttu-id="d2dad-118">Die beiden folgenden unterschiedlichen `SELECT`-Abfragen generieren XML-Code, der in seiner Form einen kleinen Unterschied aufweist.</span><span class="sxs-lookup"><span data-stu-id="d2dad-118">The two distinct `SELECT` queries that follow generate XML with a small difference in shape.</span></span>  
  
 <span data-ttu-id="d2dad-119">Die erste Abfrage generiert XML-Code, in dem <`SalesPerson`> und <`SalesOrderHeader`> als gleichgeordnete Unterelemente von <`SalesOrder`> erscheinen:</span><span class="sxs-lookup"><span data-stu-id="d2dad-119">The first query generates XML in which <`SalesPerson`> and <`SalesOrderHeader`> appear as sibling children of <`SalesOrder`>:</span></span>  
  
```  
SELECT   
      (SELECT top 2 SalesOrderID, SalesPersonID, CustomerID,  
         (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
           from Sales.SalesOrderDetail  
            WHERE  SalesOrderDetail.SalesOrderID =   
                   SalesOrderHeader.SalesOrderID  
            FOR XML AUTO, TYPE)  
        FROM  Sales.SalesOrderHeader  
        WHERE SalesOrderHeader.SalesOrderID = SalesOrder.SalesOrderID  
        for xml auto, type),  
        (SELECT *   
         FROM  (SELECT SalesPersonID, EmployeeID  
              FROM Sales.SalesPerson, HumanResources.Employee  
              WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As   
                     SalesPerson  
         WHERE  SalesPerson.SalesPersonID = SalesOrder.SalesPersonID  
       FOR XML AUTO, TYPE)  
FROM (SELECT SalesOrderHeader.SalesOrderID, SalesOrderHeader.SalesPersonID  
      FROM Sales.SalesOrderHeader, Sales.SalesPerson  
      WHERE SalesOrderHeader.SalesPersonID = SalesPerson.SalesPersonID  
     ) as SalesOrder  
ORDER BY SalesOrder.SalesOrderID  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d2dad-120">In der vorherigen Abfrage bewirkt die äußerste `SELECT`-Anweisung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d2dad-120">In the previous query, the outermost `SELECT` statement does the following:</span></span>  
  
-   <span data-ttu-id="d2dad-121">Sie fragt das Rowset `SalesOrder` ab, das in der `FROM`-Klausel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d2dad-121">Queries the rowset, `SalesOrder`, specified in the `FROM` clause.</span></span> <span data-ttu-id="d2dad-122">Das Ergebnis ist ein XML-Code mit einem oder mehreren <`SalesOrder`>-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d2dad-122">The result is an XML with one or more <`SalesOrder`> elements.</span></span>  
  
-   <span data-ttu-id="d2dad-123">Gibt den `AUTO` -Modus und die `TYPE` -Direktive an.</span><span class="sxs-lookup"><span data-stu-id="d2dad-123">Specifies `AUTO` mode and the `TYPE` directive.</span></span> <span data-ttu-id="d2dad-124">`AUTO`der-Modus wandelt das Abfrageergebnis in XML um, und die- `TYPE` Direktive gibt das Ergebnis als- `xml` Typ zurück.</span><span class="sxs-lookup"><span data-stu-id="d2dad-124">`AUTO` mode transforms the query result into XML, and the `TYPE` directive returns the result as `xml` type.</span></span>  
  
-   <span data-ttu-id="d2dad-125">Sie schließt zwei geschachtelte `SELECT` -Anweisungen ein, die durch ein Komma voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="d2dad-125">Includes two nested `SELECT` statements separated by a comma.</span></span> <span data-ttu-id="d2dad-126">Die erste geschachtelte `SELECT` -Anweisung ruft die Bestellinformationen (Kopfzeile und Details) ab, und die zweite geschachtelte `SELECT` -Anweisung ruft die Informationen zum Vertriebsmitarbeiter ab.</span><span class="sxs-lookup"><span data-stu-id="d2dad-126">The first nested `SELECT` retrieves sales order information, header and details, and the second nested `SELECT` statement retrieves salesperson information.</span></span>  
  
    -   <span data-ttu-id="d2dad-127">Die `SELECT` -Anweisung, die `SalesOrderID`, `SalesPersonID`und `CustomerID` abruft, enthält eine weitere geschachtelte `SELECT ... FOR XML` -Anweisung (mit `AUTO` -Modus und `TYPE` -Direktive), die Detailinformationen zur Bestellung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d2dad-127">The `SELECT` statement that retrieves `SalesOrderID`, `SalesPersonID`, and `CustomerID` itself includes another nested `SELECT ... FOR XML` statement (with `AUTO` mode and `TYPE` directive) that returns sales order detail information.</span></span>  
  
 <span data-ttu-id="d2dad-128">Die `SELECT` -Anweisung, mit der die Informationen zum Vertriebsmitarbeiter abgerufen werden, fragt ein Rowset ( `SalesPerson`) ab, das in der `FROM` -Klausel erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d2dad-128">The `SELECT` statement that retrieves the sales person information queries a rowset, `SalesPerson`, created in the `FROM` clause.</span></span> <span data-ttu-id="d2dad-129">Damit `FOR XML` -Abfragen funktionsfähig sind, müssen Sie einen Namen für das anonyme Rowset bereitstellen, das in der `FROM` -Klausel generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2dad-129">For `FOR XML` queries to work, you must provide a name for the anonymous rowset generated in the `FROM` clause.</span></span> <span data-ttu-id="d2dad-130">In diesem Fall ist der bereitgestellte Name `SalesPerson`.</span><span class="sxs-lookup"><span data-stu-id="d2dad-130">In this case, the name provided is `SalesPerson`.</span></span>  
  
 <span data-ttu-id="d2dad-131">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="d2dad-131">This is the partial result:</span></span>  
  
```  
<SalesOrder>  
  <Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
    <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  </Sales.SalesOrderHeader>  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</SalesOrder>  
...  
```  
  
 <span data-ttu-id="d2dad-132">Die folgende Abfrage generiert dieselben Bestellinformationen, außer dass im resultierenden XML-Code das <`SalesPerson`>-Element als gleichgeordnetes Element von <`SalesOrderDetail`> erscheint:</span><span class="sxs-lookup"><span data-stu-id="d2dad-132">The following query generates the same sales order information, except that in the resulting XML, the <`SalesPerson`> appears as a sibling of <`SalesOrderDetail`>:</span></span>  
  
```  
<SalesOrder>  
    <SalesOrderHeader ...>  
          <SalesOrderDetail .../>  
          <SalesOrderDetail .../>  
          ...  
          <SalesPerson .../>  
    </SalesOrderHeader>  
  
</SalesOrder>  
<SalesOrder>  
  ...  
</SalesOrder>  
```  
  
 <span data-ttu-id="d2dad-133">Im Folgenden wird die Abfrage aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d2dad-133">This is the query:</span></span>  
  
```  
SELECT SalesOrderID, SalesPersonID, CustomerID,  
             (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
              from Sales.SalesOrderDetail  
              WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
              FOR XML AUTO, TYPE),  
              (SELECT *   
               FROM  (SELECT SalesPersonID, EmployeeID  
                    FROM Sales.SalesPerson, HumanResources.Employee  
                    WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
               WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
         FOR XML AUTO, TYPE)  
FROM Sales.SalesOrderHeader  
WHERE SalesOrderID=43659 or SalesOrderID=43660  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="d2dad-134">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="d2dad-134">This is the result:</span></span>  
  
```  
<Sales.SalesOrderHeader SalesOrderID="43659" SalesPersonID="279" CustomerID="676">  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="776" OrderQty="1" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="777" OrderQty="3" UnitPrice="2024.9940" />  
  <Sales.SalesOrderDetail SalesOrderID="43659" ProductID="778" OrderQty="1" UnitPrice="2024.9940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
<Sales.SalesOrderHeader SalesOrderID="43660" SalesPersonID="279" CustomerID="117">  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="762" OrderQty="1" UnitPrice="419.4589" />  
  <Sales.SalesOrderDetail SalesOrderID="43660" ProductID="758" OrderQty="1" UnitPrice="874.7940" />  
  <SalesPerson SalesPersonID="279" EmployeeID="279" />  
</Sales.SalesOrderHeader>  
```  
  
 <span data-ttu-id="d2dad-135">Da die `TYPE`-Direktive Abfrageergebnisse als `xml`-Typ zurückgibt, können Sie den resultierenden XML-Code mithilfe verschiedener `xml`-Datentypmethoden abfragen.</span><span class="sxs-lookup"><span data-stu-id="d2dad-135">Because the `TYPE` directive returns a query result as `xml` type, you can query the resulting XML by using various `xml` data type methods.</span></span> <span data-ttu-id="d2dad-136">Weitere Informationen finden Sie unter [XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="d2dad-136">For more information, see [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span> <span data-ttu-id="d2dad-137">Beachten Sie in der nächsten Abfrage Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d2dad-137">In the following query, note the following:</span></span>  
  
-   <span data-ttu-id="d2dad-138">Die vorherige Abfrage wird in der `FROM` -Klausel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d2dad-138">The previous query is added in the `FROM` clause.</span></span> <span data-ttu-id="d2dad-139">Das Abfrageergebnis wird als Tabelle zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2dad-139">The query result is returned as a table.</span></span> <span data-ttu-id="d2dad-140">Beachten Sie den hinzugefügten `XmlCol` -Alias.</span><span class="sxs-lookup"><span data-stu-id="d2dad-140">Note the `XmlCol` alias that is added.</span></span>  
  
-   <span data-ttu-id="d2dad-141">Die `SELECT` -Klausel gibt eine XQuery-Abfrage für `XmlCol` an, das in der `FROM` -Klausel zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d2dad-141">The `SELECT` clause specifies an XQuery against the `XmlCol` returned in the `FROM` clause.</span></span> <span data-ttu-id="d2dad-142">Die XQuery-Abfrage wird mit der `query()`-Methode des `xml`-Datentyps angegeben.</span><span class="sxs-lookup"><span data-stu-id="d2dad-142">The `query()` method of the `xml` data type is used in specifying the XQuery.</span></span> <span data-ttu-id="d2dad-143">Weitere Informationen finden Sie unter [query&#40;&#41;-Methode &#40;xml-Datentyp&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="d2dad-143">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
    ```  
    SELECT XmlCol.query('<Root> { /* } </Root>')  
    FROM (  
    SELECT SalesOrderID, SalesPersonID, CustomerID,  
                 (select top 3 SalesOrderID, ProductID, OrderQty, UnitPrice  
                  from Sales.SalesOrderDetail  
                  WHERE SalesOrderDetail.SalesOrderID = SalesOrderHeader.SalesOrderID  
                  FOR XML AUTO, TYPE),  
                  (SELECT *   
                   FROM  (SELECT SalesPersonID, EmployeeID  
                        FROM Sales.SalesPerson, HumanResources.Employee  
                        WHERE SalesPerson.SalesPersonID = Employee.EmployeeID) As SalesPerson  
                   WHERE  SalesPerson.SalesPersonID = SalesOrderHeader.SalesPersonID  
             FOR XML AUTO, TYPE)  
    FROM Sales.SalesOrderHeader  
    WHERE SalesOrderID='43659' or SalesOrderID='43660'  
    FOR XML AUTO, TYPE ) as T(XmlCol)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d2dad-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2dad-144">See Also</span></span>  
 [<span data-ttu-id="d2dad-145">Verwenden von geschachtelten FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="d2dad-145">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
