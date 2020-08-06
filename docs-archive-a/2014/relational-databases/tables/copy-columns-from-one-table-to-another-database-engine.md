---
title: Kopieren von Spalten von einer Tabelle in eine andere Tabelle (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying columns
- columns [SQL Server], copying
ms.assetid: 5f5e70dc-69f9-44b8-bc48-b5d51ac20d77
author: stevestein
ms.author: sstein
ms.openlocfilehash: 37b98bf0910cbbb4c2a1d7fe01f11d52703ec88c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630604"
---
# <a name="copy-columns-from-one-table-to-another-database-engine"></a><span data-ttu-id="761fd-102">Kopieren von Spalten von einer Tabelle in eine andere Tabelle (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="761fd-102">Copy Columns from One Table to Another (Database Engine)</span></span>
  <span data-ttu-id="761fd-103">In diesem Thema wird beschrieben, wie Sie Spalten einer Tabelle in eine andere Tabelle kopieren. Dabei kopieren Sie entweder nur die Spaltendefinition oder die Definition und Daten in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="761fd-103">This topic describes how to copy columns from one table to another, copying either just the column definition, or the definition and data in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="761fd-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="761fd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="761fd-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="761fd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="761fd-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="761fd-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="761fd-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="761fd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="761fd-108">**So kopieren Sie Spalten mit:**</span><span class="sxs-lookup"><span data-stu-id="761fd-108">**To coy columns, using:**</span></span>  
  
     [<span data-ttu-id="761fd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="761fd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="761fd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="761fd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="761fd-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="761fd-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="761fd-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="761fd-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="761fd-113">Wenn Sie eine Spalte mit einem Aliasdatentyp aus einer Datenbank in eine andere kopieren, steht der Aliasdatentyp in der Zieldatenbank möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="761fd-113">When you copy a column that has an alias data type from one database to another, the alias data type may not be available in the destination database.</span></span> <span data-ttu-id="761fd-114">In diesem Fall wird der Spalte der ähnlichste Grunddatentyp zugewiesen, der in der Datenbank verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="761fd-114">In such a case, the column will be assigned the nearest matching base data type available in that database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="761fd-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="761fd-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="761fd-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="761fd-116">Permissions</span></span>  
 <span data-ttu-id="761fd-117">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="761fd-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="761fd-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="761fd-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="761fd-119">So kopieren Sie Spaltendefinitionen von einer Tabelle in eine andere</span><span class="sxs-lookup"><span data-stu-id="761fd-119">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="761fd-120">Öffnen Sie die Tabelle mit den zu kopierenden Spalten und diejenige, in die Sie die Spalten kopieren möchten, indem Sie mit der rechten Maustaste auf die Tabellen und dann auf **Entwerfen**klicken.</span><span class="sxs-lookup"><span data-stu-id="761fd-120">Open the table with columns you want to copy and the one you want to copy into by right-clicking the tables, and then clicking **Design**.</span></span>  
  
2.  <span data-ttu-id="761fd-121">Klicken Sie auf die Registerkarte für die Tabelle mit den zu kopierenden Spalten, und wählen Sie diese Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="761fd-121">Click the tab for the table with the columns you want to copy and select those columns.</span></span>  
  
3.  <span data-ttu-id="761fd-122">Klicken Sie im Menü **Bearbeiten** auf den Befehl **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="761fd-122">From the **Edit** menu, click **Copy**.</span></span>  
  
4.  <span data-ttu-id="761fd-123">Klicken Sie auf die Registerkarte der Tabelle, in die Sie die Spalten kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="761fd-123">Click the tab for the table into which you want to copy the columns.</span></span>  
  
5.  <span data-ttu-id="761fd-124">Wählen Sie die Spalte aus, die den eingefügten Spalten folgen soll, und klicken Sie im Menü **Bearbeiten** auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="761fd-124">Select the column you want to follow the inserted columns and, from the **Edit** menu, click **Paste**.</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="761fd-125">So kopieren Sie Daten von einer Tabelle in eine andere</span><span class="sxs-lookup"><span data-stu-id="761fd-125">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="761fd-126">Befolgen Sie die obigen Anweisungen zum Kopieren von Spaltendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="761fd-126">Follow the directions for copying column definitions above.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="761fd-127">Bevor Sie Daten von einer Tabelle in eine andere kopieren, stellen Sie sicher, dass die Datentypen in den Zielspalten mit denen der Quellspalten kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="761fd-127">Before you begin to copy data from one table to another, make sure that the data types in the destination columns are compatible with the data types of the source columns</span></span>  
  
2.  <span data-ttu-id="761fd-128">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Knoten **Sichten** , und klicken Sie dann auf **Neue Sicht**.</span><span class="sxs-lookup"><span data-stu-id="761fd-128">In Object Explorer, right-click the **Views** node, and then click **New View**.</span></span>  
  
3.  <span data-ttu-id="761fd-129">Zeigen Sie im Menü **Abfrage-Designer** auf **Typ ändern**, und klicken Sie dann auf **Ergebnisse einfügen**.</span><span class="sxs-lookup"><span data-stu-id="761fd-129">From the **Query Designer** menu, point to **Change Type**, and then click **Insert Results**.</span></span>  
  
4.  <span data-ttu-id="761fd-130">Wählen Sie im Dialogfeld **Zieltabelle für Anfügeabfrage auswählen** die Tabelle aus, in die Sie die Daten kopieren möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="761fd-130">In the **Choose Target Table for Insert Results** dialog box, select the table into which you want to copy the data, and then click **OK**.</span></span>  
  
     <span data-ttu-id="761fd-131">Wenn Sie Zeilen innerhalb einer Tabelle kopieren, können Sie die Quelltabelle als Zieltabelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="761fd-131">If you are copying rows within a table, you can add the source table as a destination table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="761fd-132">Der**Abfrage-Designer** kann nicht im Voraus bestimmen, welche Tabellen und Sichten Sie aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="761fd-132">**Query Designer** cannot determine in advance which tables and views you can update.</span></span> <span data-ttu-id="761fd-133">Daher werden im Dialogfeld **Zieltabelle für Anfügeabfrage auswählen** in der Tabellenliste alle in der abgefragten Datenverbindung verfügbaren Tabellen und Sichten angezeigt, d. h. auch diejenigen, in die möglicherweise keine Zeilen kopiert werden können.</span><span class="sxs-lookup"><span data-stu-id="761fd-133">Therefore, the list of tables in the **Choose Target Table for Insert Results** dialog box shows all available tables and views in the data connection you are querying, even those that you might not be able to copy rows to.</span></span>  
  
5.  <span data-ttu-id="761fd-134">Klicken Sie mit der rechten Maustaste auf den Diagrammbereich und dann im Kontextmenü auf **Tabelle zu Diagramm hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="761fd-134">Right-click in the body of the diagram pane and, from the shortcut menu, click **Add Table to Diagram**.</span></span>  
  
6.  <span data-ttu-id="761fd-135">Wählen Sie im Dialogfeld **Tabelle hinzufügen** alle Tabellen aus, aus denen Sie Daten kopieren möchten. Klicken Sie auf **Hinzufügen**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="761fd-135">In the **Add Table** dialog box, select each table from which you want to copy data, click **Add**, and then click **Close**.</span></span>  
  
     <span data-ttu-id="761fd-136">Die Tabellen werden in abgekürzter Form im Diagrammbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="761fd-136">The tables, in an abbreviated form, appear in the diagram pane.</span></span>  
  
7.  <span data-ttu-id="761fd-137">Aktivieren Sie in den abgekürzten Tabellen die einzelnen Kontrollkästchen für die Spalten, aus denen Sie Daten kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="761fd-137">In the abbreviated tables, check the boxes for any columns from which you want to copy data.</span></span>  
  
8.  <span data-ttu-id="761fd-138">Wählen Sie Im Kriterienbereich in der Spalte **Anfügen** für jede Zielspalte eine Spalte aus, aus der Sie Daten kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="761fd-138">In the criteria pane, in the **Append** column, for each target column choose a column from which you want to copy data.</span></span>  
  
9. <span data-ttu-id="761fd-139">Legen Sie im Kriterienbereich durch Eingabe von Suchbedingungen fest, welche Zeilen kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="761fd-139">Specify the rows to copy by entering search conditions in the criteria pane.</span></span> <span data-ttu-id="761fd-140">Weitere Informationen finden Sie unter [Angeben von Suchbedingungen &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="761fd-140">For details, see [Specify Search Conditions &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="761fd-141">Wenn Sie keine Suchbedingung festlegen, werden alle Zeilen der Quelltabelle in die Zieltabelle kopiert.</span><span class="sxs-lookup"><span data-stu-id="761fd-141">If you do not specify a search condition, all rows from the source table will be copied to the destination table.</span></span>  
  
10. <span data-ttu-id="761fd-142">Wenn Sie Zusammenfassungs Informationen kopieren möchten, geben Sie **Group by** -Optionen an.</span><span class="sxs-lookup"><span data-stu-id="761fd-142">If you want to copy summary information, specify **Group By** options.</span></span> <span data-ttu-id="761fd-143">Weitere Informationen finden Sie unter [Wertzusammenfassung oder -aggregation für alle Zeilen in einer Tabelle &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="761fd-143">For details, see [Summarize or Aggregate Values for All Rows in a Table &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools.md).</span></span>  
  
11. <span data-ttu-id="761fd-144">Klicken Sie auf die Schaltfläche **SQL ausführen** , um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="761fd-144">Click the **Execute SQL button** to run the query.</span></span>  
  
     <span data-ttu-id="761fd-145">Beim Ausführen einer Abfrage zum Einfügen von Ergebnissen werden im [Ergebnisbereich](../../ssms/visual-db-tools/results-pane-visual-database-tools.md)keine Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="761fd-145">When you execute an insert results query, no results are reported in the [Results Pane](../../ssms/visual-db-tools/results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="761fd-146">Stattdessen wird eine Meldung mit der Anzahl der kopierten Zeilen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="761fd-146">Instead, a message appears indicating how many rows were copied.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="761fd-147">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="761fd-147">Using Transact-SQL</span></span>  
  
#### <a name="to-copy-column-definitions-from-one-table-to-another"></a><span data-ttu-id="761fd-148">So kopieren Sie Spaltendefinitionen von einer Tabelle in eine andere</span><span class="sxs-lookup"><span data-stu-id="761fd-148">To copy column definitions from one table to another</span></span>  
  
1.  <span data-ttu-id="761fd-149">Anhand von Transact-SQL-Anweisungen können Sie keine einzelnen Spalten aus einer Tabelle in eine andere vorhandene Tabelle kopieren.</span><span class="sxs-lookup"><span data-stu-id="761fd-149">You cannot copy individual columns from one table to another existing table by using Transact-SQL statements.</span></span> <span data-ttu-id="761fd-150">Mit SELECT INTO können Sie jedoch eine neue Tabelle in der Standarddateigruppe erstellen, und die Ergebniszeilen aus der Abfrage werden darin eingefügt.</span><span class="sxs-lookup"><span data-stu-id="761fd-150">However, you can create a new table in the default filegroup and inserts the resulting rows from the query into it by using SELECT INTO.</span></span> <span data-ttu-id="761fd-151">Weitere Informationen finden Sie unter [INTO-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="761fd-151">For more information, see [INTO Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-into-clause-transact-sql).</span></span>  
  
#### <a name="to-copy-data-from-one-table-to-another"></a><span data-ttu-id="761fd-152">So kopieren Sie Daten von einer Tabelle in eine andere</span><span class="sxs-lookup"><span data-stu-id="761fd-152">To copy data from one table to another</span></span>  
  
1.  <span data-ttu-id="761fd-153">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="761fd-153">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="761fd-154">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="761fd-154">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="761fd-155">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="761fd-155">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.EmployeeSales  
    ( BusinessEntityID   varchar(11) NOT NULL,  
      SalesYTD money NOT NULL  
    );  
    GO  
    INSERT INTO dbo.EmployeeSales  
        SELECT BusinessEntityID, SalesYTD   
        FROM Sales.SalesPerson;  
    GO  
    ```  
  
  
