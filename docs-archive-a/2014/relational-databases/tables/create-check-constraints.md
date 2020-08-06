---
title: Erstellen von CHECK-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table constraints [SQL Server]
- attaching check constraints
- columns [SQL Server], constraints
- constraints [SQL Server], check
- CHECK constraints, attaching
ms.assetid: b8756304-9454-4d39-996a-64516831b7df
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7795ee6eca85a22bdd4e84c90ce49a9449ddff28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630600"
---
# <a name="create-check-constraints"></a><span data-ttu-id="555e4-102">Erstellen von CHECK-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="555e4-102">Create Check Constraints</span></span>
  <span data-ttu-id="555e4-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in einer Tabelle eine CHECK-Einschränkung erstellen, um die Datenwerte anzugeben, die in einer oder mehreren Spalten in [!INCLUDE[tsql](../../includes/tsql-md.md)] akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="555e4-103">You can create a check constraint in a table to specify the data values that are acceptable in one or more columns in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="555e4-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="555e4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="555e4-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="555e4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="555e4-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="555e4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="555e4-107">**So erstellen Sie eine neue CHECK-Einschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="555e4-107">**To create a new check constraint using:**</span></span>  
  
     [<span data-ttu-id="555e4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="555e4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="555e4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="555e4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="555e4-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="555e4-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="555e4-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="555e4-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="555e4-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="555e4-112">Permissions</span></span>  
 <span data-ttu-id="555e4-113">Erfordert ALTER-Berechtigungen für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="555e4-113">Requires ALTER permissions on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="555e4-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="555e4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="555e4-115">So erstellen Sie eine neue CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="555e4-115">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="555e4-116">Erweitern Sie im **Objekt-Explorer**die Tabelle, der Sie eine CHECK-Einschränkung hinzufügen möchten, klicken Sie mit der rechten Maustaste auf **Einschränkungen**, und klicken Sie auf **Neue Einschränkung**.</span><span class="sxs-lookup"><span data-stu-id="555e4-116">In **Object Explorer**, expand the table to which you want to add a check constraint, right-click **Constraints** and click **New Constraint**.</span></span>  
  
2.  <span data-ttu-id="555e4-117">Klicken Sie im Dialogfeld **Einschränkungen überprüfen** auf das Feld **Ausdruck** und dann auf die Auslassungspunkte **(…)** .</span><span class="sxs-lookup"><span data-stu-id="555e4-117">In the **Check Constraints** dialog box, click in the **Expression** field and then click the ellipses **(...)**.</span></span>  
  
3.  <span data-ttu-id="555e4-118">Geben Sie im Dialogfeld **CHECK-Einschränkungen** die SQL-Ausdrücke für die CHECK-Einschränkungen ein.</span><span class="sxs-lookup"><span data-stu-id="555e4-118">In the **Check Constraint Expression** dialog box, type the SQL expressions for the check constraint.</span></span> <span data-ttu-id="555e4-119">Um die Einträge in der Spalte `SellEndDate` der Tabelle `Product` auf einen Wert zu beschränken, der entweder größer oder gleich dem Datum in der Spalte `SellStartDate` ist oder ein NULL-Wert ist, geben Sie z. B. Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="555e4-119">For example, to limit the entries in the `SellEndDate` column of the `Product` table to a value that is either greater than or equal to the date in the `SellStartDate` column or is a NULL value, type:</span></span>  
  
    ```  
    SellEndDate >= SellStartDate OR SellEndDate IS NULL  
    ```  
  
     <span data-ttu-id="555e4-120">Wenn die Einträge in der Spalte `zip` aus 5 Ziffern bestehen sollen, müssen Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="555e4-120">Or, to require entries in the `zip` column to be 5 digits, type:</span></span>  
  
    ```  
    zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="555e4-121">Achten Sie darauf, dass nichtnumerische Einschränkungswerte in einfache Anführungszeichen (') eingeschlossen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="555e4-121">Make sure to enclose any non-numeric constraint values in single quotation marks (').</span></span>  
  
4.  <span data-ttu-id="555e4-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="555e4-122">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="555e4-123">In der Kategorie **Identität** können Sie den Namen der CHECK-Einschränkung ändern und eine Beschreibung (erweiterte Eigenschaft) für die Einschränkung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="555e4-123">In the **Identity** category, you can change the name of the check constraint and add a description (extended property) for the constraint.</span></span>  
  
6.  <span data-ttu-id="555e4-124">In der **Tabellen-Designer**-Kategorie können Sie festlegen, unter welchen Bedingungen die Einschränkung erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="555e4-124">In the **Table Designer** category, you can set when the constraint is enforced.</span></span>  
  
    |<span data-ttu-id="555e4-125">**An:**</span><span class="sxs-lookup"><span data-stu-id="555e4-125">**To:**</span></span>|<span data-ttu-id="555e4-126">**Wählen Sie in den folgenden Feldern Ja aus:**</span><span class="sxs-lookup"><span data-stu-id="555e4-126">**Select Yes in the Following Fields:**</span></span>|  
    |-------------|---------------------------------------------|  
    |<span data-ttu-id="555e4-127">Einschränkung für Daten überprüfen, die vorhanden waren, bevor Sie die Einschränkung erstellt haben</span><span class="sxs-lookup"><span data-stu-id="555e4-127">Test the constraint on data that existed before you created the constraint</span></span>|<span data-ttu-id="555e4-128">**Vorhandene Daten bei Erstellung oder Reaktivierung überprüfen**</span><span class="sxs-lookup"><span data-stu-id="555e4-128">**Check Existing Data On Creation Or Enabling**</span></span>|  
    |<span data-ttu-id="555e4-129">Die Einschränkung jedes Mal erzwingen, wenn ein Replikationsvorgang mit dieser Tabelle auftritt</span><span class="sxs-lookup"><span data-stu-id="555e4-129">Enforce the constraint whenever a replication operation occurs on this table</span></span>|<span data-ttu-id="555e4-130">**Für Replikation erzwingen**</span><span class="sxs-lookup"><span data-stu-id="555e4-130">**Enforce For Replication**</span></span>|  
    |<span data-ttu-id="555e4-131">Die Einschränkung jedes Mal erzwingen, wenn eine Zeile in diese Tabelle eingefügt wird oder darin aktualisiert wird</span><span class="sxs-lookup"><span data-stu-id="555e4-131">Enforce the constraint whenever a row of this table is inserted or updated</span></span>|<span data-ttu-id="555e4-132">**Für INSERTs und UPDATEs erzwingen**</span><span class="sxs-lookup"><span data-stu-id="555e4-132">**Enforce For INSERTs And UPDATEs**</span></span>|  
  
7.  <span data-ttu-id="555e4-133">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="555e4-133">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="555e4-134">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="555e4-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-check-constraint"></a><span data-ttu-id="555e4-135">So erstellen Sie eine neue CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="555e4-135">To create a new check constraint</span></span>  
  
1.  <span data-ttu-id="555e4-136">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="555e4-136">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="555e4-137">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="555e4-137">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="555e4-138">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="555e4-138">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
       ADD ColumnD int NULL   
       CONSTRAINT CHK_ColumnD_DocExc   
       CHECK (ColumnD > 10 AND ColumnD < 50);  
    GO  
    -- Adding values that will pass the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (49);  
    GO  
    -- Adding values that will fail the check constraint  
    INSERT INTO dbo.DocExc (ColumnD) VALUES (55);  
    GO  
  
    ```  
  
 <span data-ttu-id="555e4-139">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="555e4-139">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
