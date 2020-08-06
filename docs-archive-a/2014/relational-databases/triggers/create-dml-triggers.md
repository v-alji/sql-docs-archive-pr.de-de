---
title: Erstellen von DML-Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], DML triggers
- deferred name resolution, DML triggers
- WITH ENCRYPTION clause
- IF UPDATE
- SET statement, DML triggers
- DML triggers, programming
- testing column changes
- results [SQL Server], DML triggers
ms.assetid: b2b52258-642b-462e-8e0f-18c09d2eccf4
author: rothja
ms.author: jroth
ms.openlocfilehash: f843513ba634bcb3479e373eb9ac978ab584588d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621936"
---
# <a name="create-dml-triggers"></a><span data-ttu-id="2efe0-102">Erstellen von DML-Triggern</span><span class="sxs-lookup"><span data-stu-id="2efe0-102">Create DML Triggers</span></span>
  <span data-ttu-id="2efe0-103">In diesem Thema wird beschrieben, wie ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -DML-Trigger mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] unter Verwendung der [!INCLUDE[tsql](../../includes/tsql-md.md)] - CREATE TRIGGER-Anweisung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2efe0-103">This topic describes how to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] DML trigger by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TRIGGER statement.</span></span>  
  
##  <a name="before-you-begin"></a><a name="Top"></a> <span data-ttu-id="2efe0-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2efe0-104">Before You Begin</span></span>  
  
### <a name="limitations-and-restrictions"></a><span data-ttu-id="2efe0-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2efe0-105">Limitations and Restrictions</span></span>  
 <span data-ttu-id="2efe0-106">Eine Liste der Einschränkungen in Zusammenhang mit der Erstellung von DML-Triggern finden Sie unter [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efe0-106">For a list of limitations and restrictions related to creating DML triggers, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2efe0-107">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2efe0-107">Permissions</span></span>  
 <span data-ttu-id="2efe0-108">Es ist die ALTER-Berechtigung für die Tabelle oder Sicht erforderlich, für die der Trigger erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2efe0-108">Requires ALTER permission on the table or view on which the trigger is being created.</span></span>  
  
##  <a name="how-to-create-a-dml-trigger"></a><a name="Procedures"></a> <span data-ttu-id="2efe0-109">So erstellen Sie einen DML-Trigger</span><span class="sxs-lookup"><span data-stu-id="2efe0-109">How to Create a DML Trigger</span></span>  
 <span data-ttu-id="2efe0-110">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="2efe0-110">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="2efe0-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2efe0-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="2efe0-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2efe0-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2efe0-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2efe0-113">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="2efe0-114">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="2efe0-114">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2efe0-115">Erweitern Sie **Datenbanken**, die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank und **Tabellen** , und erweitern Sie dann die Tabelle **Purchasing.PurchaseOrderHeader**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-115">Expand **Databases**, expand the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, expand **Tables** and then expand the table **Purchasing.PurchaseOrderHeader**.</span></span>  
  
3.  <span data-ttu-id="2efe0-116">Klicken Sie mit der rechten Maustaste auf **Trigger**, und wählen Sie **Neuer Trigger**aus.</span><span class="sxs-lookup"><span data-stu-id="2efe0-116">Right-click **Triggers**, and then select **New Trigger**.</span></span>  
  
4.  <span data-ttu-id="2efe0-117">Klicken Sie im Menü **Abfrage** auf **Werte für Vorlagenparameter angeben**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-117">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span> <span data-ttu-id="2efe0-118">Alternativ können Sie die Tastenkombination STRG+UMSCHALT+M drücken, um das Dialogfeld **Werte für Vorlagenparameter angeben** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2efe0-118">Alternatively, you can press (Ctrl-Shift-M) to open the **Specify Values for Template Parameters** dialog box.</span></span>  
  
5.  <span data-ttu-id="2efe0-119">Geben Sie im Dialogfeld **Werte für Vorlagenparameter angeben** die folgenden Werte für die angezeigten Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="2efe0-119">In the **Specify Values for Template Parameters** dialog box, enter the following values for the parameters shown.</span></span>  
  
    |<span data-ttu-id="2efe0-120">Parameter</span><span class="sxs-lookup"><span data-stu-id="2efe0-120">Parameter</span></span>|<span data-ttu-id="2efe0-121">value</span><span class="sxs-lookup"><span data-stu-id="2efe0-121">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="2efe0-122">Autor</span><span class="sxs-lookup"><span data-stu-id="2efe0-122">Author</span></span>|<span data-ttu-id="2efe0-123">*Ihr Name*</span><span class="sxs-lookup"><span data-stu-id="2efe0-123">*Your name*</span></span>|  
    |<span data-ttu-id="2efe0-124">Erstellt am</span><span class="sxs-lookup"><span data-stu-id="2efe0-124">Create Date</span></span>|<span data-ttu-id="2efe0-125">*Das heutige Datum*</span><span class="sxs-lookup"><span data-stu-id="2efe0-125">*Today's date*</span></span>|  
    |<span data-ttu-id="2efe0-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2efe0-126">Description</span></span>|<span data-ttu-id="2efe0-127">Überprüft die Anbieterbonität, bevor eine neue Bestellung mit dem einzufügenden Anbieter zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="2efe0-127">Checks the vendor credit rating before allowing a new purchase order with the vendor to be inserted.</span></span>|  
    |<span data-ttu-id="2efe0-128">Schema_Name</span><span class="sxs-lookup"><span data-stu-id="2efe0-128">Schema_Name</span></span>|<span data-ttu-id="2efe0-129">Erwerb</span><span class="sxs-lookup"><span data-stu-id="2efe0-129">Purchasing</span></span>|  
    |<span data-ttu-id="2efe0-130">Trigger_Name</span><span class="sxs-lookup"><span data-stu-id="2efe0-130">Trigger_Name</span></span>|<span data-ttu-id="2efe0-131">NewPODetail2</span><span class="sxs-lookup"><span data-stu-id="2efe0-131">NewPODetail2</span></span>|  
    |<span data-ttu-id="2efe0-132">Table_Name</span><span class="sxs-lookup"><span data-stu-id="2efe0-132">Table_Name</span></span>|<span data-ttu-id="2efe0-133">PurchaseOrderDetail</span><span class="sxs-lookup"><span data-stu-id="2efe0-133">PurchaseOrderDetail</span></span>|  
    |<span data-ttu-id="2efe0-134">Data_Modification_Statement</span><span class="sxs-lookup"><span data-stu-id="2efe0-134">Data_Modification_Statement</span></span>|<span data-ttu-id="2efe0-135">UPDATE und DELETE aus der Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="2efe0-135">Remove UPDATE and DELETE from the list.</span></span>|  
  
6.  <span data-ttu-id="2efe0-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-136">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="2efe0-137">Ersetzen Sie im **Abfrage-Editor**den Kommentar `-- Insert statements for trigger here` durch die folgende Anweisung:</span><span class="sxs-lookup"><span data-stu-id="2efe0-137">In the **Query Editor**, replace the comment `-- Insert statements for trigger here` with the following statement:</span></span>  
  
    ```sql  
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
  
8.  <span data-ttu-id="2efe0-138">Zum Überprüfen der Syntax klicken Sie im Menü **Abfrage** auf **Analysieren**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-138">To verify the syntax is valid, on the **Query** menu, click **Parse**.</span></span> <span data-ttu-id="2efe0-139">Wenn eine Fehlermeldung zurückgegeben wird, vergleichen Sie die Anweisung mit den Informationen oben, korrigieren diese gegebenenfalls und wiederholen diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="2efe0-139">If an error message is returned, compare the statement with the information above and correct as needed and repeat this step.</span></span>  
  
9. <span data-ttu-id="2efe0-140">Zum Erstellen des DML-Triggers klicken Sie im Menü **Abfrage** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-140">To create the DML trigger, from the **Query** menu, click **Execute**.</span></span> <span data-ttu-id="2efe0-141">Der DML-Trigger wird als Objekt in der Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="2efe0-141">The DML trigger is created as an object in the database.</span></span>  
  
10. <span data-ttu-id="2efe0-142">Zum Anzeigen des DML-Triggers im Objekt-Explorer klicken Sie mit der rechten Maustaste auf **Trigger** und wählen **Aktualisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="2efe0-142">To see the DML trigger listed in Object Explorer, right-click **Triggers** and select **Refresh**.</span></span>  
  
 [<span data-ttu-id="2efe0-143">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2efe0-143">Before You Begin</span></span>](#Top)  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2efe0-144">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2efe0-144">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="2efe0-145">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="2efe0-145">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2efe0-146">Klicken Sie im Menü **Datei** auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-146">From the **File** menu, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2efe0-147">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2efe0-147">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2efe0-148">In diesem Beispiel wird derselbe gespeicherte DML-Trigger wie oben erstellt.</span><span class="sxs-lookup"><span data-stu-id="2efe0-148">This example creates the same stored DML trigger as above.</span></span>  
  
    ```sql
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
