---
title: Erstellen von DML-Triggern für die Verarbeitung mehrerer Datenzeilen | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- multiple row DML triggers
- UPDATE statement [SQL Server], DML triggers
- DELETE statement [SQL Server], DML triggers
- multirow DML triggers [SQL Server]
- INSERT statement [SQL Server], DML triggers
- DML triggers, multirow
ms.assetid: d476c124-596b-4b27-a883-812b6b50a735
author: rothja
ms.author: jroth
ms.openlocfilehash: 11ea7aa457a5cdfcafd4a8c4e0ac170ae0e3b9c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621941"
---
# <a name="create-dml-triggers-to-handle-multiple-rows-of-data"></a><span data-ttu-id="4b84f-102">Erstellen von DML-Triggern für die Verarbeitung mehrerer Datenzeilen</span><span class="sxs-lookup"><span data-stu-id="4b84f-102">Create DML Triggers to Handle Multiple Rows of Data</span></span>
  <span data-ttu-id="4b84f-103">Wenn Sie den Code für einen DML-Trigger schreiben, sollten Sie berücksichtigen, dass es sich bei der Anweisung, die zum Auslösen des Triggers führt, um eine einzelne Anweisung handeln kann, die sich jedoch nicht nur auf eine einzelne Zeile, sondern auf mehrere Datenzeilen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4b84f-103">When you write the code for a DML trigger, consider that the statement that causes the trigger to fire can be a single statement that affects multiple rows of data, instead of a single row.</span></span> <span data-ttu-id="4b84f-104">Dieses Verhalten trifft häufig auf UPDATE- und DELETE-Trigger zu, da sich diese Anweisungen oft auf mehrere Zeilen auswirken.</span><span class="sxs-lookup"><span data-stu-id="4b84f-104">This behavior is common for UPDATE and DELETE triggers because these statements frequently affect multiple rows.</span></span> <span data-ttu-id="4b84f-105">Eher ungewöhnlich ist dieses Verhalten für INSERT-Trigger, da durch die einfache INSERT-Anweisung nur eine einzelne Zeile hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4b84f-105">The behavior is less common for INSERT triggers because the basic INSERT statement adds only a single row.</span></span> <span data-ttu-id="4b84f-106">Da ein INSERT-Trigger jedoch durch eine INSERT INTO (*table_name*) SELECT-Anweisung ausgelöst werden kann, kann die Einfügung mehrerer Zeilen zum Aufruf eines einzelnen Triggers führen.</span><span class="sxs-lookup"><span data-stu-id="4b84f-106">However, because an INSERT trigger can be fired by an INSERT INTO (*table_name*) SELECT statement, the insertion of many rows may cause a single trigger invocation.</span></span>  
  
 <span data-ttu-id="4b84f-107">Die Berücksichtigung mehrzeiliger Operationen ist insbesondere dann wichtig, wenn ein Trigger dazu dient, zusammenfassende Werte für eine Tabelle automatisch neu zu berechnen und die Ergebnisse in einer anderen Tabelle zu speichern, um weitere Berechnungen durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="4b84f-107">Multirow considerations are especially important when the function of a DML trigger is to automatically recalculate summary values from one table and store the results in another for ongoing tallies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b84f-108">Die Verwendung von Cursorn in Triggern wird nicht empfohlen, weil dies möglicherweise die Leistung beeinträchtigen kann.</span><span class="sxs-lookup"><span data-stu-id="4b84f-108">We do not recommend using cursors in triggers because they could potentially reduce performance.</span></span> <span data-ttu-id="4b84f-109">Verwenden Sie statt Cursorn rowsetbasierte Logik, um einen Trigger zu erstellen, der sich auf mehrere Zeilen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4b84f-109">To design a trigger that affects multiple rows, use rowset-based logic instead of cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4b84f-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4b84f-110">Examples</span></span>  
 <span data-ttu-id="4b84f-111">Die DML-Trigger in den folgenden Beispielen dienen dazu, die laufende Summe einer Spalte in einer anderen Tabelle der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4b84f-111">The DML triggers in the following examples are designed to store a running total of a column in another table of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
### <a name="a-storing-a-running-total-for-a-single-row-insert"></a><span data-ttu-id="4b84f-112">A.</span><span class="sxs-lookup"><span data-stu-id="4b84f-112">A.</span></span> <span data-ttu-id="4b84f-113">Speichern einer laufenden Summe für die Einfügung einer einzelnen Zeile</span><span class="sxs-lookup"><span data-stu-id="4b84f-113">Storing a running total for a single-row insert</span></span>  
 <span data-ttu-id="4b84f-114">Die erste Version des Triggers funktioniert für die Einfügung einer einzelnen Zeile ordnungsgemäß, wenn eine Datenzeile in die `PurchaseOrderDetail` -Tabelle geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4b84f-114">The first version of the DML trigger works well for a single-row insert when a row of data is loaded into the `PurchaseOrderDetail` table.</span></span> <span data-ttu-id="4b84f-115">Der DML-Trigger wird durch eine INSERT-Anweisung ausgelöst, und die neue Zeile wird für die Dauer der Triggerausführung in die **inserted** -Tabelle geladen.</span><span class="sxs-lookup"><span data-stu-id="4b84f-115">An INSERT statement fires the DML trigger, and the new row is loaded into the **inserted** table for the duration of the trigger execution.</span></span> <span data-ttu-id="4b84f-116">Die `UPDATE` -Anweisung liest den Wert der `LineTotal` -Spalte für diese Zeile und addiert ihn zu dem vorhandenen Wert in der `SubTotal` -Spalte in der `PurchaseOrderHeader` -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4b84f-116">The `UPDATE` statement reads the `LineTotal` column value for the row and adds that value to the existing value in the `SubTotal` column in the `PurchaseOrderHeader` table.</span></span> <span data-ttu-id="4b84f-117">Durch die `WHERE` -Klausel wird sichergestellt, dass die aktualisierte Zeile in der `PurchaseOrderDetail` -Tabelle mit der `PurchaseOrderID` der Zeile in der **inserted** -Tabelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4b84f-117">The `WHERE` clause makes sure that the updated row in the `PurchaseOrderDetail` table matches the `PurchaseOrderID` of the row in the **inserted** table.</span></span>  
  
```  
-- Trigger is valid for single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID ;  
```  
  
### <a name="b-storing-a-running-total-for-a-multirow-or-single-row-insert"></a><span data-ttu-id="4b84f-118">B.</span><span class="sxs-lookup"><span data-stu-id="4b84f-118">B.</span></span> <span data-ttu-id="4b84f-119">Speichern einer laufenden Summe für die Einfügung mehrerer Zeilen oder einer einzelnen Zeile</span><span class="sxs-lookup"><span data-stu-id="4b84f-119">Storing a running total for a multirow or single-row insert</span></span>  
 <span data-ttu-id="4b84f-120">Falls mehrere Zeilen eingefügt werden, funktioniert der DML-Trigger in Beispiel A möglicherweise nicht ordnungsgemäß; der Ausdruck auf der rechten Seite eines Zuweisungsausdrucks in einer UPDATE-Anweisung (`SubTotal` + `LineTotal`) kann nur einem einzelnen Wert und nicht einer Liste von Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4b84f-120">For a multirow insert, the DML trigger in example A might not operate correctly; the expression to the right of an assignment expression in an UPDATE statement (`SubTotal` + `LineTotal`) can be only a single value, not a list of values.</span></span> <span data-ttu-id="4b84f-121">Die Auswirkung des Triggers kann somit folgendermaßen beschrieben werden: Er ruft einen Wert aus einer einzelnen Zeile in der **inserted** -Tabelle ab und fügt diesen Wert dem vorhandenen Wert von `SubTotal` in der `PurchaseOrderHeader` -Tabelle für einen bestimmten `PurchaseOrderID` -Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b84f-121">Therefore, the effect of the trigger is to retrieve a value from any single row in the **inserted** table and add that value to the existing `SubTotal` value in the `PurchaseOrderHeader` table for a specific `PurchaseOrderID` value.</span></span> <span data-ttu-id="4b84f-122">Dieses Verfahren führt möglicherweise nicht zum beabsichtigten Ergebnis, wenn ein einzelner `PurchaseOrderID` -Wert mehrmals in der **inserted** -Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4b84f-122">This operation might not have the expected effect if a single `PurchaseOrderID` value occurred more than one time in the **inserted** table.</span></span>  
  
 <span data-ttu-id="4b84f-123">Damit die `PurchaseOrderHeader` -Tabelle ordnungsgemäß aktualisiert wird, muss der Trigger die Möglichkeit mehrerer Zeilen in der **inserted** -Tabelle berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="4b84f-123">To correctly update the `PurchaseOrderHeader` table, the trigger must allow for the chance of multiple rows in the **inserted** table.</span></span> <span data-ttu-id="4b84f-124">Sie können zu diesem Zweck die `SUM` -Funktion verwenden, die die Gesamtsumme für `LineTotal` für eine Gruppe von Zeilen in der **inserted** -Tabelle für jede `PurchaseOrderID`berechnet.</span><span class="sxs-lookup"><span data-stu-id="4b84f-124">You can do this by using the `SUM` function that calculates the total `LineTotal` for a group of rows in the **inserted** table for each `PurchaseOrderID`.</span></span> <span data-ttu-id="4b84f-125">Die `SUM` -Funktion ist in einer korrelierten Unterabfrage (der `SELECT` -Anweisung in Klammern) enthalten.</span><span class="sxs-lookup"><span data-stu-id="4b84f-125">The `SUM` function is included in a correlated subquery (the `SELECT` statement in parentheses).</span></span> <span data-ttu-id="4b84f-126">Die Unterabfrage gibt einen einzelnen Wert für jede `PurchaseOrderID` in der **inserted** -Tabelle zurück, die einer `PurchaseOrderID` in der `PurchaseOrderHeader` -Tabelle entspricht oder mit dieser korreliert.</span><span class="sxs-lookup"><span data-stu-id="4b84f-126">This subquery returns a single value for each `PurchaseOrderID` in the **inserted** table that matches or is correlated with a `PurchaseOrderID` in the `PurchaseOrderHeader` table.</span></span>  
  
```  
-- Trigger is valid for multirow and single-row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail2  
ON Purchasing.PurchaseOrderDetail  
AFTER INSERT AS  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted);  
```  
  
 <span data-ttu-id="4b84f-127">Dieser Trigger kann auch für die Einfügung einer einzelnen Zeile ordnungsgemäß funktionieren, da in diesem Fall die Summe der `LineTotal` -Wertspalte der Summe einer einzelnen Zeile entspricht.</span><span class="sxs-lookup"><span data-stu-id="4b84f-127">This trigger also works correctly in a single-row insert; the sum of the `LineTotal` value column is the sum of a single row.</span></span> <span data-ttu-id="4b84f-128">Mit diesem Trigger ist jedoch für die korrelierte Unterabfrage und den `IN` -Operator, die in der `WHERE` -Klausel verwendet werden, weitere Verarbeitung durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4b84f-128">However, with this trigger the correlated subquery and the `IN` operator that is used in the `WHERE` clause require additional processing from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4b84f-129">Dies ist für das Einfügen einer einzelnen Zeile überflüssig.</span><span class="sxs-lookup"><span data-stu-id="4b84f-129">This is unnecessary for a single-row insert.</span></span>  
  
### <a name="c-storing-a-running-total-based-on-the-type-of-insert"></a><span data-ttu-id="4b84f-130">C.</span><span class="sxs-lookup"><span data-stu-id="4b84f-130">C.</span></span> <span data-ttu-id="4b84f-131">Speichern einer laufenden Summe in Abhängigkeit von der Einfügungsart</span><span class="sxs-lookup"><span data-stu-id="4b84f-131">Storing a running total based on the type of insert</span></span>  
 <span data-ttu-id="4b84f-132">Sie können den Trigger so ändern, dass er die Methode verwendet, die für die jeweilige Zeilenanzahl am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4b84f-132">You can change the trigger to use the method optimal for the number of rows.</span></span> <span data-ttu-id="4b84f-133">So kann z. B. mithilfe der `@@ROWCOUNT` -Funktion in der Triggerlogik zwischen der Einfügung einer einzelnen Zeile und der Einfügung mehrerer Zeilen unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="4b84f-133">For example, the `@@ROWCOUNT` function can be used in the logic of the trigger to distinguish between a single and a multirow insert.</span></span>  
  
```  
-- Trigger valid for multirow and single row inserts  
-- and optimal for single row inserts.  
USE AdventureWorks2012;  
GO  
CREATE TRIGGER NewPODetail3  
ON Purchasing.PurchaseOrderDetail  
FOR INSERT AS  
IF @@ROWCOUNT = 1  
BEGIN  
   UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal + LineTotal  
   FROM inserted  
   WHERE PurchaseOrderHeader.PurchaseOrderID = inserted.PurchaseOrderID  
END  
ELSE  
BEGIN  
      UPDATE Purchasing.PurchaseOrderHeader  
   SET SubTotal = SubTotal +   
      (SELECT SUM(LineTotal)  
      FROM inserted  
      WHERE PurchaseOrderHeader.PurchaseOrderID  
       = inserted.PurchaseOrderID)  
   WHERE PurchaseOrderHeader.PurchaseOrderID IN  
      (SELECT PurchaseOrderID FROM inserted)  
END;  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b84f-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b84f-134">See Also</span></span>  
 [<span data-ttu-id="4b84f-135">DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="4b84f-135">DML Triggers</span></span>](dml-triggers.md)  
  
  
