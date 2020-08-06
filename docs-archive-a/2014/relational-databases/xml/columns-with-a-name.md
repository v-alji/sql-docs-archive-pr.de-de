---
title: Spalten mit Namen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns with
ms.assetid: c994e089-4cfc-4e9b-b7fc-e74f6014b51a
author: rothja
ms.author: jroth
ms.openlocfilehash: 32cfe617b80ed216374249961b85eae401011a67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696529"
---
# <a name="columns-with-a-name"></a><span data-ttu-id="57188-102">Spalten mit Namen</span><span class="sxs-lookup"><span data-stu-id="57188-102">Columns with a Name</span></span>
  <span data-ttu-id="57188-103">Im Folgenden werden die spezifischen Bedingungen aufgeführt, unter denen dem XML-Ergebnis mit Unterscheidung nach Groß-/Kleinschreibung Rowsetspalten mit Namen zugeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="57188-103">The following are the specific conditions in which rowset columns with a name are mapped, case-sensitive, to the resulting XML:</span></span>  
  
-   <span data-ttu-id="57188-104">Der Spaltenname beginnt mit einem At-Zeichen (\@).</span><span class="sxs-lookup"><span data-stu-id="57188-104">The column name starts with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="57188-105">Der Spaltenname beginnt nicht mit einem At-Zeichen (\@).</span><span class="sxs-lookup"><span data-stu-id="57188-105">The column name does not start with an at sign (\@).</span></span>  
  
-   <span data-ttu-id="57188-106">Der Spaltenname beginnt nicht mit einem At-Zeichen (\@) und enthält einen Schrägstrich (/).</span><span class="sxs-lookup"><span data-stu-id="57188-106">The column name does not start with an at sign\@ and contains a slash mark (/).</span></span>  
  
-   <span data-ttu-id="57188-107">Mehrere Spalten verwenden dasselbe Präfix.</span><span class="sxs-lookup"><span data-stu-id="57188-107">Several columns share the same prefix.</span></span>  
  
-   <span data-ttu-id="57188-108">Eine Spalte hat einen unterschiedlichen Namen.</span><span class="sxs-lookup"><span data-stu-id="57188-108">One column has a different name.</span></span>  
  
## <a name="column-name-starts-with-an-at-sign-"></a><span data-ttu-id="57188-109">Spaltenname beginnt mit einem At-Zeichen (\@)</span><span class="sxs-lookup"><span data-stu-id="57188-109">Column Name Starts with an At Sign (\@)</span></span>  
 <span data-ttu-id="57188-110">Wenn der Spaltenname mit einem @-Zeichen ( \@ ) beginnt und keinen Schrägstrich (/) enthält, wird ein Attribut des <`row`> Elements erstellt, das über den entsprechenden Spaltenwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="57188-110">If the column name starts with an at sign (\@) and does not contain a slash mark (/), an attribute of the <`row`> element that has the corresponding column value is created.</span></span> <span data-ttu-id="57188-111">Die folgende Abfrage gibt beispielsweise ein Rowset mit zwei Spalten (\@PmId, Name) zurück.</span><span class="sxs-lookup"><span data-stu-id="57188-111">For example, the following query returns a two-column (\@PmId, Name) rowset.</span></span> <span data-ttu-id="57188-112">Im resultierenden XML-Code wird dem entsprechenden <`row`>-Element ein **PmId**-Attribut hinzugefügt und diesem der Wert ProductModelID zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="57188-112">In the resulting XML, a **PmId** attribute is added to the corresponding <`row`> element and a value of ProductModelID is assigned to it.</span></span>  
  
```  
  
SELECT ProductModelID as "@PmId",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
  
```  
  
 <span data-ttu-id="57188-113">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-113">This is the result:</span></span>  
  
```  
<row PmId="7">  
  <Name>HL Touring Frame</Name>  
</row>  
```  
  
 <span data-ttu-id="57188-114">Beachten Sie, dass Attribute allen anderen Knotentypen, wie z. B. Elementknoten und Textknoten, auf derselben Ebene vorangestellt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="57188-114">Note that attributes must come before any other node types, such as element nodes and text nodes, in the same level.</span></span> <span data-ttu-id="57188-115">Die folgende Abfrage gibt einen Fehler zurück:</span><span class="sxs-lookup"><span data-stu-id="57188-115">The following query will return an error:</span></span>  
  
```  
SELECT Name,  
       ProductModelID as "@PmId"  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign-"></a><span data-ttu-id="57188-116">Spaltenname beginnt nicht mit einem At-Zeichen (\@)</span><span class="sxs-lookup"><span data-stu-id="57188-116">Column Name Does Not Start with an At Sign (\@)</span></span>  
 <span data-ttu-id="57188-117">Wenn der Spaltenname nicht mit einem at-Zeichen ( \@ ) beginnt, keiner der XPath-Knoten Tests ist und keinen Schrägstrich (/) enthält, wird ein XML-Element erstellt, das ein untergeordnetes Element des Row-Elements ist, <`row` standardmäßig>.</span><span class="sxs-lookup"><span data-stu-id="57188-117">If the column name does not start with an at sign (\@), is not one of the XPath node tests, and does not contain a slash mark (/), an XML element that is a subelement of the row element, <`row`> by default, is created.</span></span>  
  
 <span data-ttu-id="57188-118">Die folgende Abfrage gibt den Spaltennamen result an.</span><span class="sxs-lookup"><span data-stu-id="57188-118">The following query specifies the column name, the result.</span></span> <span data-ttu-id="57188-119">Folglich wird dem <`row`>-Element das untergeordnete <`result`>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="57188-119">Therefore, a <`result`> element child is added to the <`row`> element.</span></span>  
  
```  
SELECT 2+2 as result  
for xml PATH  
```  
  
 <span data-ttu-id="57188-120">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-120">This is the result:</span></span>  
  
```  
<row>  
  <result>4</result>  
</row>  
```  
  
 <span data-ttu-id="57188-121">Die folgende Abfrage gibt den Spaltennamen ManuWorkCenterInformation für den XML-Code an, der von der für die Instructions-Spalte vom **xml** -Typ angegebenen XQuery zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="57188-121">The following query specifies the column name, ManuWorkCenterInformation, for the XML returned by the XQuery specified against Instructions column of **xml** type.</span></span> <span data-ttu-id="57188-122">Folglich wird dem <`row`>-Element das untergeordnete <`ManuWorkCenterInformation`>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="57188-122">Therefore, a <`ManuWorkCenterInformation`> element is added as a child of the <`row`> element.</span></span>  
  
```  
SELECT   
       ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') as ManuWorkCenterInformation  
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH   
go  
```  
  
 <span data-ttu-id="57188-123">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-123">This is the result:</span></span>  
  
```  
<row>  
  <ProductModelID>7</ProductModelID>  
  <Name>HL Touring Frame</Name>  
  <ManuWorkCenterInformation>  
    <MI:Location ...LocationID="10" ...></MI:Location>  
    <MI:Location ...LocationID="20" ...></MI:Location>  
     ...  
  </ManuWorkCenterInformation>  
</row>  
```  
  
## <a name="column-name-does-not-start-with-an-at-sign--and-contains-a-slash-mark-"></a><span data-ttu-id="57188-124">Spaltenname beginnt nicht mit einem At-Zeichen (\@) und enthält einen Schrägstrich (/)</span><span class="sxs-lookup"><span data-stu-id="57188-124">Column Name Does Not Start with an At Sign (\@) and Contains a Slash Mark (/)</span></span>  
 <span data-ttu-id="57188-125">Wenn der Spaltenname nicht mit einem At-Zeichen (\@) beginnt, jedoch einen Schrägstrich (/) enthält, zeigt der Spaltenname eine XML-Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="57188-125">If the column name does not start with an at sign (\@), but contains a slash mark (/), the column name indicates an XML hierarchy.</span></span> <span data-ttu-id="57188-126">Wenn der Spaltenname z.B. „Name1/Name2/Name3.../Name***n*** “ lautet, stellt „Name***i*** “ jeweils einen Elementnamen dar, der im aktuellen Zeilenelement geschachtelt ist (für i=1), oder der dem Element mit dem Namen „Name***i-1***“ untergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="57188-126">For example, if the column name is "Name1/Name2/Name3.../Name***n*** ", each Name***i*** represents an element name that is nested in the current row element (for i=1) or that is under the element that has the name Name***i-1***.</span></span> <span data-ttu-id="57188-127">Wenn „Namen***n***“ mit „\@“ beginnt, wird er einem Attribut des „Namen***n-1***“-Elements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="57188-127">If Name***n*** starts with '\@', it is mapped to an attribute of Name***n-1*** element.</span></span>  
  
 <span data-ttu-id="57188-128">Die folgende Abfrage gibt beispielsweise die ID und den Namen eines Mitarbeiters als komplexes Element EmpName zurück, welches zwei Vornamen und einen Nachnamen enthält (FirstName, MiddleName, LastName).</span><span class="sxs-lookup"><span data-stu-id="57188-128">For example, the following query returns an employee ID and name that are represented as a complex element EmpName that contains a First, Middle, and Last name.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="57188-129">Die Spaltennamen werden als Pfad für die Konstruktion des XML-Codes im PATH-Modus verwendet.</span><span class="sxs-lookup"><span data-stu-id="57188-129">The column names are used as a path in constructing XML in the PATH mode.</span></span> <span data-ttu-id="57188-130">Der Spaltenname, der Mitarbeiter-ID-Werte enthält, beginnt mit " \@ ". Daher wird das Attribut " **EmpID**" dem <>-Element hinzugefügt `row` .</span><span class="sxs-lookup"><span data-stu-id="57188-130">The column name that contains employee ID values, starts with '\@'.Therefore, an attribute, **EmpID**, is added to the <`row`> element.</span></span> <span data-ttu-id="57188-131">Alle anderen Spalten enthalten einen eine Hierarchie aufzeigenden Schrägstrich (/) im Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="57188-131">All other columns include a slash mark ('/') in the column name that indicates hierarchy.</span></span> <span data-ttu-id="57188-132">Im resultierenden XML-Code befindet sich das untergeordnete <`EmpName`>-Element unter dem <`row`>-Element, und das untergeordnete <`EmpName`>-Element verfügt über die untergeordneten Elemente <`First`>, <`Middle`> und <`Last`>.</span><span class="sxs-lookup"><span data-stu-id="57188-132">The resulting XML will have the <`EmpName`> child under the <`row`> element, and the <`EmpName`> child will have <`First`>, <`Middle`> and <`Last`> element children.</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="57188-133">Der zweite Vorname des Mitarbeiters ist ein NULL-Wert, welcher standardmäßig der Abwesenheit eines Elements oder Attributs zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="57188-133">The employee middle name is null and, by default, the null value maps to the absence of the element or attribute.</span></span> <span data-ttu-id="57188-134">Wenn Sie jedoch möchten, dass für NULL-Werte Elemente generiert werden, können Sie die ELEMENTS-Direktive mit XSINIL angeben, wie in der folgenden Abfrage gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57188-134">If you want elements generated for the NULL values, you can specify the ELEMENTS directive with XSINIL as shown in this query.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName  "EmpName/First",   
       MiddleName "EmpName/Middle",   
       LastName   "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="57188-135">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-135">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   
      EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
 <span data-ttu-id="57188-136">Standardmäßig generiert der PATH-Modus elementzentrierten XML-Code.</span><span class="sxs-lookup"><span data-stu-id="57188-136">By default, the PATH mode generates element-centric XML.</span></span> <span data-ttu-id="57188-137">Daher hat die Angabe der ELEMENTS-Direktive in einer Abfrage im PATH-Modus keine Wirkung.</span><span class="sxs-lookup"><span data-stu-id="57188-137">Therefore, specifying the ELEMENTS directive in a PATH mode query has no effect.</span></span> <span data-ttu-id="57188-138">Die ELEMENTS-Direktive erweist sich jedoch in Verbindung mit XSINIL als nützlich, um Elemente für NULL-Werte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="57188-138">However, as shown in the previous example, the ELEMENTS directive is useful with XSINIL to generate elements for null values.</span></span>  
  
 <span data-ttu-id="57188-139">Die folgende Abfrage ruft außer der ID und dem Namen die Adresse eines Mitarbeiters ab.</span><span class="sxs-lookup"><span data-stu-id="57188-139">Besides the ID and name, the following query retrieves an employee address.</span></span> <span data-ttu-id="57188-140">Entsprechend dem Pfad in den Spaltennamen für Adressspalten wird dem <`row`>-Element ein untergeordnetes <`Address`>-Element hinzugefügt, und die Adressdetails werden als untergeordnete Elemente des <`Address`>-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="57188-140">As per the path in the column names for address columns, an <`Address`> element child is added to the <`row`> element and the address details are added as element children of the <`Address`> element.</span></span>  
  
```  
SELECT EmployeeID   "@EmpID",   
       FirstName    "EmpName/First",   
       MiddleName   "EmpName/Middle",   
       LastName     "EmpName/Last",  
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City         "Address/City"  
FROM   HumanResources.Employee E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="57188-141">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-141">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Last>Achong</Last>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
</row>  
```  
  
## <a name="several-columns-share-the-same-path-prefix"></a><span data-ttu-id="57188-142">Mehrere Spalten verwenden dasselbe Pfadpräfix</span><span class="sxs-lookup"><span data-stu-id="57188-142">Several Columns Share the Same Path Prefix</span></span>  
 <span data-ttu-id="57188-143">Wenn mehrere aufeinander folgende Spalten dasselbe Pfadpräfix gemeinsam haben, werden sie unter demselben Namen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="57188-143">If several subsequent columns share the same path prefix, they are grouped together under the same name.</span></span> <span data-ttu-id="57188-144">Werden verschiedene Namespacepräfixe verwendet, wird ein Pfad als verschieden betrachtet, auch wenn die Präfixe an denselben Namespace gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="57188-144">If different namespace prefixes are being used even if they are bound to the same namespace, a path is considered different.</span></span> <span data-ttu-id="57188-145">In der vorherigen Abfrage verfügen die Spalten FirstName, MiddleName und LastName über das gleiche EmpName-Präfix. Daher werden sie als untergeordnete Elemente des <`EmpName`>-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="57188-145">In the previous query, the FirstName, MiddleName, and LastName columns share the same EmpName prefix.Therefore, they are added as children of the <`EmpName`> element.</span></span> <span data-ttu-id="57188-146">Dies war auch der Fall, als Sie das <`Address`>-Element im vorherigen Beispiel erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="57188-146">This is also the case when you were creating the <`Address`> element in the previous example.</span></span>  
  
## <a name="one-column-has-a-different-name"></a><span data-ttu-id="57188-147">Eine Spalte hat einen unterschiedlichen Namen</span><span class="sxs-lookup"><span data-stu-id="57188-147">One Column Has a Different Name</span></span>  
 <span data-ttu-id="57188-148">Wenn eine Spalte in einer Reihe von Spalten einen anderen Namen aufweist, wird die Gruppierung unterbrochen, wie in der folgenden, geänderten Abfrage gezeigt.</span><span class="sxs-lookup"><span data-stu-id="57188-148">If a column with a different name appears in between, it will break the grouping, as shown in the following modified query.</span></span> <span data-ttu-id="57188-149">Die Abfrage unterbricht die Gruppierung von FirstName, MiddleName und LastName, die in der vorherigen Abfrage angegeben waren, durch Hinzufügen der Adressspalten zwischen der FirstName- und der MiddleName-Spalte.</span><span class="sxs-lookup"><span data-stu-id="57188-149">The query breaks the grouping of FirstName, MiddleName, and LastName, as specified in the previous query, by adding address columns in between the FirstName and MiddleName columns.</span></span>  
  
```  
SELECT EmployeeID "@EmpID",   
       FirstName "EmpName/First",   
       AddressLine1 "Address/AddrLine1",  
       AddressLine2 "Address/AddrLIne2",  
       City "Address/City",  
       MiddleName "EmpName/Middle",   
       LastName "EmpName/Last"  
FROM   HumanResources.EmployeeAddress E, Person.Contact C, Person.Address A  
WHERE  E.EmployeeID = C.ContactID  
AND    E.AddressID = A.AddressID  
AND    E.EmployeeID=1  
FOR XML PATH  
```  
  
 <span data-ttu-id="57188-150">Daher erstellt die Abfrage zwei <`EmpName`>-Elemente.</span><span class="sxs-lookup"><span data-stu-id="57188-150">As a result, the query creates two <`EmpName`> elements.</span></span> <span data-ttu-id="57188-151">Das erste <`EmpName`>-Element verfügt über das untergeordnete <`FirstName`>-Element, und das zweite <`EmpName`>-Element verfügt über die untergeordneten Elemente <`MiddleName`> und <`LastName`>.</span><span class="sxs-lookup"><span data-stu-id="57188-151">The first <`EmpName`> element has the <`FirstName`> element child and the second <`EmpName`> element has the <`MiddleName`> and <`LastName`> element children.</span></span>  
  
 <span data-ttu-id="57188-152">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="57188-152">This is the result:</span></span>  
  
```  
<row EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
  </EmpName>  
  <Address>  
    <AddrLine1>7726 Driftwood Drive</AddrLine1>  
    <City>Monroe</City>  
  </Address>  
  <EmpName>  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57188-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57188-153">See Also</span></span>  
 [<span data-ttu-id="57188-154">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="57188-154">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
