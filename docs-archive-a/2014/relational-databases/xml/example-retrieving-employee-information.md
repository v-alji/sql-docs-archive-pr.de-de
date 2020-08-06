---
title: 'Beispiel: Abrufen von Informationen zu Mitarbeitern | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- EXPLICIT mode
ms.assetid: 63cd6569-2600-485b-92b4-1f6ba09db219
author: rothja
ms.author: jroth
ms.openlocfilehash: ae4578aedb7dbcc63388d5ef797e3a0bf5d8c306
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618566"
---
# <a name="example-retrieving-employee-information"></a><span data-ttu-id="7d7f0-102">Beispiel: Abrufen von Informationen zu Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="7d7f0-102">Example: Retrieving Employee Information</span></span>
  <span data-ttu-id="7d7f0-103">In diesem Beispiel werden die ID und der Name jedes Mitarbeiters abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-103">This example retrieves an employee ID and employee name for each employee.</span></span> <span data-ttu-id="7d7f0-104">In der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank kann employeeID aus der BusinessEntityID-Spalte in der Employee-Tabelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-104">In the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, the employeeID can be obtained from the BusinessEntityID column in the Employee table.</span></span> <span data-ttu-id="7d7f0-105">Die Namen der Mitarbeiter werden aus der Person-Tabelle abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-105">Employee names can be obtained from the Person table.</span></span> <span data-ttu-id="7d7f0-106">Die BusinessEntityID-Spalte kann zum Join der Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-106">The BusinessEntityID column can be used to join the tables.</span></span>  
  
 <span data-ttu-id="7d7f0-107">Angenommen, Sie möchten mithilfe einer FOR XML EXPLICIT-Transformation ein XML-Dokument generieren, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7d7f0-107">Assume that you want FOR XML EXPLICIT transformation to generate XML as shown in the following:</span></span>  
  
```  
<Employee EmpID="1" >  
  <Name FName="Ken" LName="S??nchez" />  
</Employee>  
...  
```  
  
 <span data-ttu-id="7d7f0-108">Nachdem die Hierarchie zwei Ebenen aufweist, schreiben Sie zwei `SELECT` -Abfragen und wenden UNION ALL an.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-108">Because there are two levels in the hierarchy, you would write two `SELECT` queries and apply UNION ALL.</span></span> <span data-ttu-id="7d7f0-109">Im Folgenden wird die erste Abfrage gezeigt, die die Werte für das <`Employee`>-Element sowie dessen Attribute abruft.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-109">This is the first query that retrieves values for the <`Employee`> element and its attributes.</span></span> <span data-ttu-id="7d7f0-110">In der Abfrage wird dem <`Employee`>-Element der `1`-Wert `Tag` und der `Parent`-Wert NULL zugewiesen, da es sich um das Element auf oberster Ebene handelt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-110">The query assigns `1` as `Tag` value for the <`Employee`> element and NULL as `Parent`, because it is the top-level element.</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID AS [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="7d7f0-111">Im Folgenden wird die zweite Abfrage gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-111">This is the second query.</span></span> <span data-ttu-id="7d7f0-112">Sie ruft die Werte für das <`Name`>-Element ab.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-112">It retrieves values for the <`Name`> element.</span></span> <span data-ttu-id="7d7f0-113">In der Abfrage wird dem <`2`>-Element der `Tag`-Wert `Name` und der `1`-Tagwert  `Parent` zugewiesen, wodurch <`Employee`> als übergeordnetes Element identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-113">It assigns `2` as `Tag` value for the <`Name`> element and `1` as `Parent` tag value identifying <`Employee`> as the parent.</span></span>  
  
```  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID;  
```  
  
 <span data-ttu-id="7d7f0-114">Kombinieren Sie diese Abfragen nun mit `UNION AL`L, wenden Sie `FOR XML EXPLICIT`an, und geben Sie die erforderliche `ORDER BY` -Klausel an.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-114">You combine these queries with `UNION AL`L, apply `FOR XML EXPLICIT`, and specify the required `ORDER BY` clause.</span></span> <span data-ttu-id="7d7f0-115">Sie müssen das Rowset zuerst nach `BusinessEntityID` und dann nach Namen sortieren, sodass die NULL-Werte in den Namen an erster Stelle aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-115">You must sort the rowset first by `BusinessEntityID` and then by name so that the NULL values in the name appear first.</span></span> <span data-ttu-id="7d7f0-116">Führen Sie die folgende Abfrage ohne FOR XML-Klausel aus, um die generierte Universaltabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-116">By executing the following query without the FOR XML clause, you can see the universal table generated.</span></span>  
  
 <span data-ttu-id="7d7f0-117">So sieht die endgültige Abfrage aus:</span><span class="sxs-lookup"><span data-stu-id="7d7f0-117">This is the final query:</span></span>  
  
```  
SELECT 1    as Tag,  
       NULL as Parent,  
       E.BusinessEntityID as [Employee!1!EmpID],  
       NULL       as [Name!2!FName],  
       NULL       as [Name!2!LName]  
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
       E.BusinessEntityID,  
       FirstName,   
       LastName   
FROM   HumanResources.Employee AS E  
INNER JOIN Person.Person AS P  
ON  E.BusinessEntityID = P.BusinessEntityID  
ORDER BY [Employee!1!EmpID],[Name!2!FName]  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="7d7f0-118">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="7d7f0-118">This is the partial result:</span></span>  
  
 `<Employee EmpID="1">`  
  
 `<Name FName="Ken" LName="S??nchez" />`  
  
 `</Employee>`  
  
 `<Employee EmpID="2">`  
  
 `<Name FName="Terri" LName="Duffy" />`  
  
 `</Employee>`  
  
 `...`  
  
 <span data-ttu-id="7d7f0-119">Die erste `SELECT` -Anweisung gibt die Spaltennamen des Rowsets des Ergebnisses an.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-119">The first `SELECT` specifies names for columns in the resulting rowset.</span></span> <span data-ttu-id="7d7f0-120">Diese Namen bilden zwei Spaltengruppen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-120">These names form two column groups.</span></span> <span data-ttu-id="7d7f0-121">Die Gruppe mit dem `Tag` -Wert `1` im Spaltennamen identifiziert `Employee` als Element und `EmpID` als Attribut.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-121">The group that has `Tag` value `1` in the column name identifies `Employee` as an element and `EmpID` as the attribute.</span></span> <span data-ttu-id="7d7f0-122">Die andere Spaltengruppe besitzt den `Tag`-Wert `2` im Spaltennamen und identifiziert <`Name`> als Element und `FName` und `LName` als Attribute.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-122">The other column group has `Tag` value `2` in the column and identifies <`Name`> as the element and `FName` and `LName` as the attributes.</span></span>  
  
 <span data-ttu-id="7d7f0-123">In der folgenden Tabelle wird das von der Abfrage generierte partielle Rowset gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7d7f0-123">The following table shows the partial rowset generated by the query:</span></span>  
  
 `Tag Parent  Employee!1!EmpID Name!2!FName Name!2!LName`  
  
 `--- ------  ---------------- ------------ ------------`  
  
 `1   NULL    1                NULL         NULL`  
  
 `2   1       1                Ken          S??nchez`  
  
 `1   NULL    2                NULL         NULL`  
  
 `2   1       2                Terri        Duffy`  
  
 `1   NULL    3                NULL         NULL`  
  
 `2   1       3                Roberto      Tamburello`  
  
 `...`  
  
 <span data-ttu-id="7d7f0-124">Die Zeilen in der Universaltabelle werden auf folgende Weise verarbeitet, um die resultierende XML-Struktur zu erzeugen:</span><span class="sxs-lookup"><span data-stu-id="7d7f0-124">This is how the rows in the universal table are processed to produce the resulting XML tree:</span></span>  
  
 <span data-ttu-id="7d7f0-125">Die erste Zeile identifiziert den `Tag` -Wert `1`.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-125">The first row identifies `Tag` value `1`.</span></span> <span data-ttu-id="7d7f0-126">Deshalb wird die Spaltengruppe, die über den `Tag` -Wert `1` verfügt, als `Employee!1!EmpID`identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-126">Therefore, the column group that has the `Tag` value `1` is identified, `Employee!1!EmpID`.</span></span> <span data-ttu-id="7d7f0-127">Diese Spalte identifiziert `Employee` als Elementname.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-127">This column identifies `Employee` as the element name.</span></span> <span data-ttu-id="7d7f0-128">Ein <`Employee`>-Element mit `EmpID`-Attributen wird nun erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-128">An <`Employee`> element is then created that has `EmpID` attributes.</span></span> <span data-ttu-id="7d7f0-129">Diesen Attributen werden entsprechende Spaltenwerte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-129">Corresponding column values are assigned to these attributes.</span></span>  
  
 <span data-ttu-id="7d7f0-130">Die zweite Zeile verfügt über den `Tag` -Wert `2`.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-130">The second row has the `Tag` value `2`.</span></span> <span data-ttu-id="7d7f0-131">Daher wird die Spaltengruppe, die im Spaltennamen über den `Tag` -Wert `2` verfügt, als `Name!2!FName`, `Name!2!LName`identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-131">Therefore, the column group that has the `Tag` value `2` in the column name, `Name!2!FName`, `Name!2!LName`, is identified.</span></span> <span data-ttu-id="7d7f0-132">Diese Spaltennamen identifizieren `Name` als Elementname.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-132">These column names identify `Name` as element name.</span></span> <span data-ttu-id="7d7f0-133">Ein <`Name`>-Element mit `FName`- und `LName`-Attributen wird nun erstellt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-133">A <`Name`> element is created that has `FName` and `LName` attributes.</span></span> <span data-ttu-id="7d7f0-134">Diesen Attributen werden entsprechende Spaltenwerte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-134">Corresponding column values are then assigned to these attributes.</span></span> <span data-ttu-id="7d7f0-135">Diese Zeile identifiziert `1` als `Parent`-Element.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-135">This row identifies `1` as `Parent`.</span></span> <span data-ttu-id="7d7f0-136">Dieses untergeordnete Element wird dem vorhergehenden <`Employee`>-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-136">This element child is added to the previous <`Employee`> element.</span></span>  
  
 <span data-ttu-id="7d7f0-137">Dieser Prozess wird für die restlichen Zeilen des Rowsets wiederholt.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-137">This process is repeated for rest of the rows in the rowset.</span></span> <span data-ttu-id="7d7f0-138">Beachten Sie, dass die Anordnung der Zeilen in der Universaltabelle wichtig ist, damit FOR XML EXPLICIT das Rowset in der richtigen Reihenfolge verarbeitet und die erwünschte XML-Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="7d7f0-138">Note the importance of ordering the rows in the universal table so that FOR XML EXPLICIT can process the rowset in order and generate the XML you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7f0-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d7f0-139">See Also</span></span>  
 [<span data-ttu-id="7d7f0-140">Verwenden des EXPLICIT-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="7d7f0-140">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
