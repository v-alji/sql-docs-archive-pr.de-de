---
title: Erstellen von geschachtelten Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- recursive DML triggers [SQL Server]
- DML triggers, nested
- triggers [SQL Server], nested
- direct recursion [SQL Server]
- triggers [SQL Server], recursive
- DML triggers, recursive
- RECURSIVE_TRIGGERS option
- indirect recursion [SQL Server]
- nested DML triggers
ms.assetid: cd522dda-b4ab-41b8-82b0-02445bdba7af
author: rothja
ms.author: jroth
ms.openlocfilehash: c0016fc3cdd93ea78ceed56efa076a01bd85be50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621938"
---
# <a name="create-nested-triggers"></a><span data-ttu-id="c54cf-102">Erstellen von geschachtelten Triggern</span><span class="sxs-lookup"><span data-stu-id="c54cf-102">Create Nested Triggers</span></span>
  <span data-ttu-id="c54cf-103">Sowohl DML-Trigger als auch DDL-Trigger werden geschachtelt, wenn ein Trigger eine Aktion ausführt, die einen anderen Trigger auslöst.</span><span class="sxs-lookup"><span data-stu-id="c54cf-103">Both DML and DDL triggers are nested when a trigger performs an action that initiates another trigger.</span></span> <span data-ttu-id="c54cf-104">Diese Aktionen können andere Trigger auslösen usw.</span><span class="sxs-lookup"><span data-stu-id="c54cf-104">These actions can initiate other triggers, and so on.</span></span> <span data-ttu-id="c54cf-105">DML- und DDL-Trigger können bis auf 32 Ebenen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="c54cf-105">DML and DDL triggers can be nested up to 32 levels.</span></span> <span data-ttu-id="c54cf-106">Sie können über die **Geschachtelte Trigger** -Serverkonfigurationsoption steuern, ob AFTER-Trigger geschachtelt werden können.</span><span class="sxs-lookup"><span data-stu-id="c54cf-106">You can control whether AFTER triggers can be nested through the **nested triggers** server configuration option.</span></span> <span data-ttu-id="c54cf-107">INSTEAD OF-Trigger (nur DML-Trigger können INSTEAD OF-Trigger sein) können unabhängig von dieser Einstellung geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="c54cf-107">INSTEAD OF triggers (only DML triggers can be INSTEAD OF triggers) can be nested regardless of this setting.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c54cf-108">Alle Verweise auf verwalteten Code aus einem Trigger von [!INCLUDE[tsql](../../includes/tsql-md.md)] zählen als eine Ebene hinsichtlich der Schachtelungsgrenze von 32 Ebenen.</span><span class="sxs-lookup"><span data-stu-id="c54cf-108">Any reference to managed code from a [!INCLUDE[tsql](../../includes/tsql-md.md)] trigger counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="c54cf-109">Methoden, die aus verwaltetem Code aufgerufen werden, werden nicht mitgezählt.</span><span class="sxs-lookup"><span data-stu-id="c54cf-109">Methods invoked from within managed code do not count against this limit.</span></span>  
  
 <span data-ttu-id="c54cf-110">Wenn geschachtelte Trigger zulässig sind und ein Trigger in der Kette eine Endlosschleife einleitet, wird die Anzahl der maximal zulässigen Schachtelungsebenen überschritten und der Trigger demzufolge beendet.</span><span class="sxs-lookup"><span data-stu-id="c54cf-110">If nested triggers are allowed and a trigger in the chain starts an infinite loop, the nesting level is exceeded and the trigger terminates.</span></span>  
  
 <span data-ttu-id="c54cf-111">Sie können geschachtelte Trigger verwenden, um nützliche Verwaltungsfunktionen durchzuführen, wie z. B. das Speichern einer Sicherungskopie von Zeilen, die von einem vorherigen Trigger betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c54cf-111">You can use nested triggers to perform useful housekeeping functions such as storing a backup copy of rows affected by a previous trigger.</span></span> <span data-ttu-id="c54cf-112">Es ist beispielsweise möglich, einen Trigger für `PurchaseOrderDetail` zu erstellen, der eine Sicherungskopie der `PurchaseOrderDetail` -Zeilen speichert, die vom `delcascadetrig` -Trigger gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="c54cf-112">For example, you can create a trigger on `PurchaseOrderDetail` that saves a backup copy of the `PurchaseOrderDetail` rows that the `delcascadetrig` trigger deleted.</span></span> <span data-ttu-id="c54cf-113">Wenn der `delcascadetrig` -Trigger wirksam ist, führt das Löschen von `PurchaseOrderID` 1965 aus `PurchaseOrderHeader` dazu, dass die entsprechende(n) Zeile(n) aus `PurchaseOrderDetail`gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c54cf-113">With the `delcascadetrig` trigger in effect, deleting `PurchaseOrderID` 1965 from `PurchaseOrderHeader` deletes the corresponding row or rows from `PurchaseOrderDetail`.</span></span> <span data-ttu-id="c54cf-114">Zum Speichern der Daten erstellen Sie einen DELETE-Trigger für `PurchaseOrderDetail` , der die gelöschten Daten in einer getrennt erstellten Tabelle, `del_save`, speichert.</span><span class="sxs-lookup"><span data-stu-id="c54cf-114">To save the data, you can create a DELETE trigger on `PurchaseOrderDetail` that saves the deleted data into another separately created table, `del_save`.</span></span> <span data-ttu-id="c54cf-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c54cf-115">For example:</span></span>  
  
```  
CREATE TRIGGER Purchasing.savedel  
   ON Purchasing.PurchaseOrderDetail  
FOR DELETE  
AS  
   INSERT del_save;  
   SELECT * FROM deleted;  
```  
  
 <span data-ttu-id="c54cf-116">Das Verwenden geschachtelter Trigger wird nicht für eine Sequenz empfohlen, in der die Reihenfolge wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="c54cf-116">We do not recommend using nested triggers in an order-dependent sequence.</span></span> <span data-ttu-id="c54cf-117">Verwenden Sie getrennte Trigger, um Datenänderungen kaskadierend weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="c54cf-117">Use separate triggers to cascade data modifications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c54cf-118">Da Trigger innerhalb einer Transaktion ausgeführt werden, führt ein Fehler auf einer beliebigen Ebene einer Reihe geschachtelter Trigger zum Abbruch der gesamten Transaktion und zum Rollback für alle Datenänderungen.</span><span class="sxs-lookup"><span data-stu-id="c54cf-118">Because triggers execute within a transaction, a failure at any level of a set of nested triggers cancels the entire transaction, and all data modifications are rolled back.</span></span> <span data-ttu-id="c54cf-119">Fügen Sie PRINT-Anweisungen in die Trigger ein, sodass Sie ermitteln können, wo der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c54cf-119">Include PRINT statements in your triggers so that you can determine where the failure has occurred.</span></span>  
  
## <a name="recursive-triggers"></a><span data-ttu-id="c54cf-120">Rekursive Trigger</span><span class="sxs-lookup"><span data-stu-id="c54cf-120">Recursive Triggers</span></span>  
 <span data-ttu-id="c54cf-121">Ein AFTER-Trigger kann sich nur dann rekursiv aufrufen, wenn die Datenbankoption RECURSIVE_TRIGGERS festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c54cf-121">An AFTER trigger does not call itself recursively unless the RECURSIVE_TRIGGERS database option is set.</span></span>  
  
 <span data-ttu-id="c54cf-122">Die folgenden zwei Rekursionsarten stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c54cf-122">There are two types of recursion:</span></span>  
  
-   <span data-ttu-id="c54cf-123">Direkte Rekursion</span><span class="sxs-lookup"><span data-stu-id="c54cf-123">Direct recursion</span></span>  
  
     <span data-ttu-id="c54cf-124">Diese Rekursion tritt auf, wenn ein Trigger ausgelöst wird und eine Aktion ausführt, die das erneute Auslösen desselben Triggers verursacht.</span><span class="sxs-lookup"><span data-stu-id="c54cf-124">This recursion occurs when a trigger fires and performs an action that causes the same trigger to fire again.</span></span> <span data-ttu-id="c54cf-125">Eine Anwendung aktualisiert z. B. die **T3**-Tabelle, wodurch der **Trig3** -Trigger ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-125">For example, an application updates table **T3**; this causes trigger **Trig3** to fire.</span></span> <span data-ttu-id="c54cf-126">**Trig3** aktualisiert **T3** erneut, sodass der **Trig3** -Trigger erneut ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-126">**Trig3** updates table **T3** again; this causes trigger **Trig3** to fire again.</span></span>  
  
     <span data-ttu-id="c54cf-127">Die direkte Rekursion kann auch auftreten, wenn derselbe Trigger erneut aufgerufen wird, jedoch erst nach dem Aufruf eines weiteren Triggers, der einen anderen Typ aufweist (AFTER oder INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="c54cf-127">Direct recursion can also occur when the same trigger is called again, but after a trigger of a different type (AFTER or INSTEAD OF) is called.</span></span> <span data-ttu-id="c54cf-128">Mit anderen Worten: Die direkte Rekursion eines INSTEAD OF-Triggers kann auftreten, wenn derselbe INSTEAD OF-Trigger ein zweites Mal aufgerufen wird, auch wenn zwischendurch mindestens ein AFTER-Trigger aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-128">In other words, direct recursion of an INSTEAD OF trigger can occur when the same INSTEAD OF trigger is called for a second time, even if one or more AFTER triggers are called in between.</span></span> <span data-ttu-id="c54cf-129">Auf gleiche Weise kann die direkte Rekursion eines AFTER-Triggers auftreten, wenn derselbe AFTER-Trigger ein zweites Mal aufgerufen wird, auch wenn zwischendurch mindestens ein INSTEAD OF-Trigger aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-129">Likewise, direct recursion of an AFTER trigger can occur when the same AFTER trigger is called for a second time, even if one or more INSTEAD OF triggers are called in between.</span></span> <span data-ttu-id="c54cf-130">Beispielsweise aktualisiert eine Anwendung Tabelle **T4**.</span><span class="sxs-lookup"><span data-stu-id="c54cf-130">For example, an application updates table **T4**.</span></span> <span data-ttu-id="c54cf-131">Durch dieses Update wird das Auslösen von INSTEAD OF-Trigger **Trig4** verursacht.</span><span class="sxs-lookup"><span data-stu-id="c54cf-131">This update causes INSTEAD OF trigger **Trig4** to fire.</span></span> <span data-ttu-id="c54cf-132">**Trig4** aktualisiert Tabelle **T5**.</span><span class="sxs-lookup"><span data-stu-id="c54cf-132">**Trig4** updates table **T5**.</span></span> <span data-ttu-id="c54cf-133">Durch dieses Update wird das Auslösen von AFTER-Trigger **Trig5** verursacht.</span><span class="sxs-lookup"><span data-stu-id="c54cf-133">This update causes AFTER trigger **Trig5** to fire.</span></span> <span data-ttu-id="c54cf-134">**Trig5** aktualisiert wiederum Tabelle **T4**. Dieses Update verursacht erneut das Auslösen von INSTEAD OF-Trigger **Trig4** .</span><span class="sxs-lookup"><span data-stu-id="c54cf-134">**Trig5** updates table **T4**, and this update causes INSTEAD OF trigger **Trig4** to fire again.</span></span> <span data-ttu-id="c54cf-135">Diese Kette von Ereignissen wird als direkte Rekursion für **Trig4**betrachtet.</span><span class="sxs-lookup"><span data-stu-id="c54cf-135">This chain of events is considered direct recursion for **Trig4**.</span></span>  
  
-   <span data-ttu-id="c54cf-136">Indirekte Rekursion</span><span class="sxs-lookup"><span data-stu-id="c54cf-136">Indirect recursion</span></span>  
  
     <span data-ttu-id="c54cf-137">Diese Rekursion tritt auf, wenn ein Trigger ausgelöst wird, der eine Aktion ausführt, die das Auslösen eines anderen Triggers des gleichen Typs verursacht (AFTER oder INSTEAD OF).</span><span class="sxs-lookup"><span data-stu-id="c54cf-137">This recursion occurs when a trigger fires and performs an action that causes another trigger of the same type (AFTER or INSTEAD OF) to fire.</span></span> <span data-ttu-id="c54cf-138">Dieser zweite Trigger führt eine Aktion aus, die das erneute Auslösen des ursprünglichen Triggers bewirkt.</span><span class="sxs-lookup"><span data-stu-id="c54cf-138">This second trigger performs an action that causes the original trigger to fire again.</span></span> <span data-ttu-id="c54cf-139">Mit anderen Worten: Die indirekte Rekursion tritt auf, wenn ein INSTEAD OF-Trigger ein zweites Mal aufgerufen wird, jedoch erst, wenn in der Zwischenzeit ein anderer INSTEAD OF-Trigger aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-139">In other words, indirect recursion can occur when an INSTEAD OF trigger is called for a second time, but not until another INSTEAD OF trigger is called in between.</span></span> <span data-ttu-id="c54cf-140">Die indirekte Rekursion kann gleichermaßen auftreten, wenn ein AFTER-Trigger ein zweites Mal aufgerufen wird, jedoch erst, wenn in der Zwischenzeit ein anderer AFTER-Trigger aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-140">Likewise, indirect recursion can occur when an AFTER trigger is called for a second time, but not until another AFTER trigger is called in between.</span></span> <span data-ttu-id="c54cf-141">Beispielsweise aktualisiert eine Anwendung Tabelle **T1**.</span><span class="sxs-lookup"><span data-stu-id="c54cf-141">For example, an application updates table **T1**.</span></span> <span data-ttu-id="c54cf-142">Durch dieses Update wird das Auslösen von AFTER-Trigger **Trig1** verursacht.</span><span class="sxs-lookup"><span data-stu-id="c54cf-142">This update causes AFTER trigger **Trig1** to fire.</span></span> <span data-ttu-id="c54cf-143">**Trig1** aktualisiert Tabelle **T2**. Dieses Update verursacht wiederum das Auslösen von AFTER-Trigger **Trig2** .</span><span class="sxs-lookup"><span data-stu-id="c54cf-143">**Trig1** updates table **T2**, and this update causes AFTER trigger **Trig2** to fire.</span></span> <span data-ttu-id="c54cf-144">**Trig2** aktualisiert nun wiederum Tabelle **T1** , wodurch der AFTER-Trigger **Trig1** erneut ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-144">**Trig2** in turn updates table **T1** that causes AFTER trigger **Trig1** to fire again.</span></span>  
  
 <span data-ttu-id="c54cf-145">Es wird nur die direkte Rekursion von AFTER-Triggern verhindert, wenn die Datenbankoption RECURSIVE_TRIGGERS auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c54cf-145">Only direct recursion of AFTER triggers is prevented when the RECURSIVE_TRIGGERS database option is set to OFF.</span></span> <span data-ttu-id="c54cf-146">Sie müssen auch die **Geschachtelte Trigger** -Serveroption auf **0**festlegen, um die indirekte Rekursion von AFTER-Triggern zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c54cf-146">To disable indirect recursion of AFTER triggers, also set the **nested triggers** server option to **0**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c54cf-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c54cf-147">Examples</span></span>  
 <span data-ttu-id="c54cf-148">Das folgende Beispiel zeigt die Verwendung rekursiver Trigger zum Auflösen einer auf sich selbst verweisenden Beziehung (auch als transitiver Abschluss bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="c54cf-148">The following example shows using recursive triggers to solve a self-referencing relationship (also known as transitive closure).</span></span> <span data-ttu-id="c54cf-149">Die `emp_mgr` -Tabelle definiert z. B. Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c54cf-149">For example, the table `emp_mgr` defines the following:</span></span>  
  
-   <span data-ttu-id="c54cf-150">Einen Angestellten (`emp`) in einem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="c54cf-150">An employee (`emp`) in a company.</span></span>  
  
-   <span data-ttu-id="c54cf-151">Den Vorgesetzten jedes Angestellten (`mgr`).</span><span class="sxs-lookup"><span data-stu-id="c54cf-151">The manager for each employee (`mgr`).</span></span>  
  
-   <span data-ttu-id="c54cf-152">Die Gesamtzahl der Angestellten in der Hierarchie, die jedem einzelnen Vorgesetzten unterstellt sind (`NoOfReports`).</span><span class="sxs-lookup"><span data-stu-id="c54cf-152">The total number of employees in the organizational tree reporting to each employee (`NoOfReports`).</span></span>  
  
 <span data-ttu-id="c54cf-153">Mithilfe eines rekursiven UPDATE-Triggers kann die `NoOfReports` -Spalte auf dem aktuellen Stand gehalten werden, wenn neue Angestelltendatensätze eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c54cf-153">A recursive UPDATE trigger can be used to keep the `NoOfReports` column up-to-date as new employee records are inserted.</span></span> <span data-ttu-id="c54cf-154">Der INSERT-Trigger aktualisiert die `NoOfReports` -Spalte für den Datensatz des Vorgesetzten, wodurch rekursiv die `NoOfReports` -Spalte anderer Datensätze auf den höheren Hierarchieebenen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c54cf-154">The INSERT trigger updates the `NoOfReports` column of the manager record, which recursively updates the `NoOfReports` column of other records up the management hierarchy.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
-- Turn recursive triggers ON in the database.  
ALTER DATABASE AdventureWorks2012  
   SET RECURSIVE_TRIGGERS ON;  
GO  
CREATE TABLE dbo.emp_mgr (  
   emp char(30) PRIMARY KEY,  
    mgr char(30) NULL FOREIGN KEY REFERENCES emp_mgr(emp),  
    NoOfReports int DEFAULT 0  
);  
GO  
CREATE TRIGGER dbo.emp_mgrins ON dbo.emp_mgr  
FOR INSERT  
AS  
DECLARE @e char(30), @m char(30);  
DECLARE c1 CURSOR FOR  
   SELECT emp_mgr.emp  
   FROM   emp_mgr, inserted  
   WHERE emp_mgr.emp = inserted.mgr;  
  
OPEN c1;  
FETCH NEXT FROM c1 INTO @e;  
WHILE @@fetch_status = 0  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Add 1 for newly  
   WHERE emp_mgr.emp = @e ;                           -- added employee.  
  
   FETCH NEXT FROM c1 INTO @e;  
END  
CLOSE c1;  
DEALLOCATE c1;  
GO  
-- This recursive UPDATE trigger works assuming:  
--   1. Only singleton updates on emp_mgr.  
--   2. No inserts in the middle of the org tree.  
CREATE TRIGGER dbo.emp_mgrupd ON dbo.emp_mgr FOR UPDATE  
AS  
IF UPDATE (mgr)  
BEGIN  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports + 1 -- Increment mgr's  
   FROM inserted                            -- (no. of reports) by  
   WHERE emp_mgr.emp = inserted.mgr;         -- 1 for the new report.  
  
   UPDATE dbo.emp_mgr  
   SET emp_mgr.NoOfReports = emp_mgr.NoOfReports - 1 -- Decrement mgr's  
   FROM deleted                             -- (no. of reports) by 1  
   WHERE emp_mgr.emp = deleted.mgr;          -- for the new report.  
END  
GO  
-- Insert some test data rows.  
INSERT dbo.emp_mgr(emp, mgr) VALUES  
    ('Harry', NULL)  
    ,('Alice', 'Harry')  
    ,('Paul', 'Alice')  
    ,('Joe', 'Alice')  
    ,('Dave', 'Joe');  
GO  
SELECT emp,mgr,NoOfReports  
FROM dbo.emp_mgr;  
GO  
-- Change Dave's manager from Joe to Harry  
UPDATE dbo.emp_mgr SET mgr = 'Harry'  
WHERE emp = 'Dave';  
GO  
SELECT emp,mgr,NoOfReports FROM emp_mgr;  
  
GO  
```  
  
 <span data-ttu-id="c54cf-155">Im Folgenden sehen Sie die Ergebnisse vor dem Update.</span><span class="sxs-lookup"><span data-stu-id="c54cf-155">Here are the results before the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Joe                            0  
Harry                          NULL                           1  
Joe                            Alice                          1  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="c54cf-156">Im Folgenden sehen Sie die Ergebnisse nach dem Update.</span><span class="sxs-lookup"><span data-stu-id="c54cf-156">Here are the results after the update.</span></span>  
  
```  
emp                            mgr                           NoOfReports  
------------------------------ ----------------------------- -----------  
Alice                          Harry                          2  
Dave                           Harry                          0  
Harry                          NULL                           2  
Joe                            Alice                          0  
Paul                           Alice                          0  
```  
  
 <span data-ttu-id="c54cf-157">**So legen Sie die Option für geschachtelte Trigger fest**</span><span class="sxs-lookup"><span data-stu-id="c54cf-157">**To set the nested triggers option**</span></span>  
  
-   [<span data-ttu-id="c54cf-158">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c54cf-158">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
 <span data-ttu-id="c54cf-159">**So legen Sie die Datenbankoption RECURSIVE_TRIGGERS fest**</span><span class="sxs-lookup"><span data-stu-id="c54cf-159">**To set the RECURSIVE_TRIGGERS database option**</span></span>  
  
-   [<span data-ttu-id="c54cf-160">ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c54cf-160">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="c54cf-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c54cf-161">See Also</span></span>  
 <span data-ttu-id="c54cf-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c54cf-162">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="c54cf-163">Konfigurieren der Serverkonfigurationsoption Geschachtelte Trigger</span><span class="sxs-lookup"><span data-stu-id="c54cf-163">Configure the nested triggers Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-nested-triggers-server-configuration-option.md)  
  
  
