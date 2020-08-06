---
title: Erstellen von Fremdschlüssel-Beziehungen | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], creating
ms.assetid: 867a54b8-5be4-46e6-9702-49ae6dabf67c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ee0de3311eb6abffcdb71ab725d0650fe96b04c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630596"
---
# <a name="create-foreign-key-relationships"></a><span data-ttu-id="55925-102">Erstellen von Fremdschlüssel-Beziehungen</span><span class="sxs-lookup"><span data-stu-id="55925-102">Create Foreign Key Relationships</span></span>
  <span data-ttu-id="55925-103">In diesem Thema wird beschrieben, wie Fremdschlüsselbeziehungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="55925-103">This topic describes how to create foreign key relationships in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="55925-104">Sie erstellen eine Beziehung zwischen zwei Tabellen, wenn Sie die Zeilen der einen Tabelle mit den Zeilen der anderen Tabelle verknüpfen möchten.</span><span class="sxs-lookup"><span data-stu-id="55925-104">You create a relationship between two tables when you want to associate rows of one table with rows of another.</span></span>  
  
 <span data-ttu-id="55925-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="55925-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="55925-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="55925-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="55925-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="55925-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="55925-108">Security</span><span class="sxs-lookup"><span data-stu-id="55925-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="55925-109">**So erstellen Sie Fremdschlüsselbeziehungen mit:**</span><span class="sxs-lookup"><span data-stu-id="55925-109">**To Create Foreign Key Relationships by using:**</span></span>  
  
     [<span data-ttu-id="55925-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55925-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="55925-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55925-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="55925-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="55925-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="55925-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="55925-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="55925-114">Eine FOREIGN KEY-Einschränkung muss nicht notwendigerweise mit einer PRIMARY KEY-Einschränkung in einer anderen Tabelle verknüpft sein; sie kann auch so definiert werden, dass sie auf die Spalten einer UNIQUE-Einschränkung in einer anderen Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="55925-114">A foreign key constraint does not have to be linked only to a primary key constraint in another table; it can also be defined to reference the columns of a UNIQUE constraint in another table.</span></span>  
  
-   <span data-ttu-id="55925-115">Wenn ein anderer Wert als NULL in die Spalte einer FOREIGN KEY-Einschränkung eingegeben wird, muss der Wert in der Spalte vorhanden sein, auf die verwiesen wird; andernfalls wird eine Fremdschlüsselverletzungs-Fehlermeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="55925-115">When a value other than NULL is entered into the column of a FOREIGN KEY constraint, the value must exist in the referenced column; otherwise, a foreign key violation error message is returned.</span></span> <span data-ttu-id="55925-116">Um sicherzustellen, dass alle Werte einer zusammengesetzten FOREIGN KEY-Einschränkung überprüft werden, legen Sie NOT NULL für alle betroffenen Spalten fest.</span><span class="sxs-lookup"><span data-stu-id="55925-116">To make sure that all values of a composite foreign key constraint are verified, specify NOT NULL on all the participating columns.</span></span>  
  
-   <span data-ttu-id="55925-117">FOREIGN KEY-Einschränkungen können nur auf Tabellen verweisen, die sich innerhalb derselben Datenbank auf demselben Server befinden.</span><span class="sxs-lookup"><span data-stu-id="55925-117">FOREIGN KEY constraints can reference only tables within the same database on the same server.</span></span> <span data-ttu-id="55925-118">Datenbankübergreifende referenzielle Integrität muss durch Trigger implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="55925-118">Cross-database referential integrity must be implemented through triggers.</span></span> <span data-ttu-id="55925-119">Weitere Informationen finden Sie unter [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55925-119">For more information, see [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
-   <span data-ttu-id="55925-120">FOREIGN KEY-Einschränkungen können auf eine andere Spalte in derselben Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="55925-120">FOREIGN KEY constraints can reference another column in the same table.</span></span> <span data-ttu-id="55925-121">Ein solcher Verweis wird als Eigenverweis bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="55925-121">This is referred to as a self-reference.</span></span>  
  
-   <span data-ttu-id="55925-122">Eine auf Spaltenebene angegebene FOREIGN KEY-Einschränkung kann nur eine Verweisspalte auflisten.</span><span class="sxs-lookup"><span data-stu-id="55925-122">A FOREIGN KEY constraint specified at the column level can list only one reference column.</span></span> <span data-ttu-id="55925-123">Diese Spalte muss denselben Datentyp aufweisen wie die Spalte, für die die Einschränkung definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="55925-123">This column must have the same data type as the column on which the constraint is defined.</span></span>  
  
-   <span data-ttu-id="55925-124">Eine auf Tabellenebene angegebene FOREIGN KEY-Einschränkung muss ebenso viele Verweisspalten haben, wie sich Spalten in der Einschränkungsspaltenliste befinden.</span><span class="sxs-lookup"><span data-stu-id="55925-124">A FOREIGN KEY constraint specified at the table level must have the same number of reference columns as the number of columns in the constraint column list.</span></span> <span data-ttu-id="55925-125">Der Datentyp jeder Verweisspalte muss ebenfalls mit dem der entsprechenden Spalte in der Spaltenliste übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="55925-125">The data type of each reference column must also be the same as the corresponding column in the column list.</span></span>  
  
-   <span data-ttu-id="55925-126">Das [!INCLUDE[ssDE](../../includes/ssde-md.md)] verfügt über keine vordefinierte Grenze hinsichtlich der Anzahl von FOREIGN KEY-Einschränkungen, die eine Tabelle, die auf andere Tabellen verweist, enthalten kann, oder hinsichtlich der Anzahl von FOREIGN KEY-Einschränkungen im Besitz anderer Tabellen, die auf eine bestimmte Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="55925-126">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not have a predefined limit on either the number of FOREIGN KEY constraints a table can contain that reference other tables, or the number of FOREIGN KEY constraints that are owned by other tables that reference a specific table.</span></span> <span data-ttu-id="55925-127">Nichtsdestotrotz ist die tatsächliche Anzahl von FOREIGN KEY-Einschränkungen , die verwendet werden können, durch die Hardwarekonfiguration und den Entwurf der Datenbank und der Anwendung begrenzt.</span><span class="sxs-lookup"><span data-stu-id="55925-127">Nevertheless, the actual number of FOREIGN KEY constraints that can be used is limited by the hardware configuration and by the design of the database and application.</span></span> <span data-ttu-id="55925-128">Als Empfehlung gilt, dass eine Tabelle maximal 253 FOREIGN KEY-Einschränkungen enthalten sollte und dass maximal 253 FOREIGN KEY-Einschränkungen auf eine Tabelle verweisen sollten.</span><span class="sxs-lookup"><span data-stu-id="55925-128">We recommend that a table contain no more than 253 FOREIGN KEY constraints, and that it be referenced by no more than 253 FOREIGN KEY constraints.</span></span>  
  
-   <span data-ttu-id="55925-129">FOREIGN KEY-Einschränkungen werden nicht auf temporäre Tabellen angewendet.</span><span class="sxs-lookup"><span data-stu-id="55925-129">FOREIGN KEY constraints are not enforced on temporary tables.</span></span>  
  
-   <span data-ttu-id="55925-130">Wenn ein Fremdschlüssel für eine Spalte eines CLR-benutzerdefinierten Typs definiert wird, muss die Implementierung des Typs eine binäre Sortierreihenfolge unterstützen.</span><span class="sxs-lookup"><span data-stu-id="55925-130">If a foreign key is defined on a CLR user-defined type column, the implementation of the type must support binary ordering.</span></span> <span data-ttu-id="55925-131">Weitere Informationen finden Sie unter [Benutzerdefinierte CLR-Typen](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="55925-131">For more information, see [CLR User-Defined Types](../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md).</span></span>  
  
-   <span data-ttu-id="55925-132">Eine Spalte vom Typ `varchar(max)` kann nur dann in eine FOREIGN KEY-Einschränkung einbezogen werden, wenn der Primärschlüssel, auf den verwiesen wird, ebenfalls als `varchar(max)`-Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="55925-132">A column of type `varchar(max)` can participate in a FOREIGN KEY constraint only if the primary key it references is also defined as type `varchar(max)`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="55925-133">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="55925-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="55925-134">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="55925-134">Permissions</span></span>  
 <span data-ttu-id="55925-135">Zum Erstellen einer neuen Tabelle mit einem Fremdschlüssel sind die CREATE TABLE-Berechtigung für die Datenbank und die ALTER-Berechtigung für das Schema erforderlich, in dem die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="55925-135">Creating a new table with a foreign key requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>  
  
 <span data-ttu-id="55925-136">Zum Erstellen eines Fremdschlüssels für eine vorhandene Tabelle ist die ALTER-Berechtigung für die Tabelle erforderlich.</span><span class="sxs-lookup"><span data-stu-id="55925-136">Creating a foreign key in an existing table requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="55925-137">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="55925-137">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-foreign-key-relationship-in-table-designer"></a><span data-ttu-id="55925-138">So erstellen Sie eine Fremdschlüsselbeziehung im Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="55925-138">To create a foreign key relationship in Table Designer</span></span>  
  
1.  <span data-ttu-id="55925-139">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, die sich auf der Fremdschlüsselseite der Beziehung befinden soll, und klicken Sie auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="55925-139">In Object Explorer, right-click the table that will be on the foreign-key side of the relationship and click **Design**.</span></span>  
  
     <span data-ttu-id="55925-140">Die Tabelle wird im **Tabellen-Designer** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="55925-140">The table opens in **Table Designer**.</span></span>  
  
2.  <span data-ttu-id="55925-141">Klicken Sie im Menü **Tabellen-Designer** auf **Beziehungen**.</span><span class="sxs-lookup"><span data-stu-id="55925-141">From the **Table Designer** menu, click **Relationships**.</span></span>  
  
3.  <span data-ttu-id="55925-142">Klicken Sie im Dialogfeld **Fremdschlüsselbeziehungen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="55925-142">In the **Foreign-key Relationships** dialog box, click **Add**.</span></span>  
  
     <span data-ttu-id="55925-143">Die Beziehung wird in der Liste **Selected Relationship** (Ausgewählte Beziehung) mit einem vom System bereitgestellten Namen im Format FK_\<*tablename*>_\<*tablename*> angezeigt, wobei *tablename* dem Namen der Fremdschlüsseltabelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="55925-143">The relationship appears in the **Selected Relationship** list with a system-provided name in the format FK_\<*tablename*>_\<*tablename*>, where *tablename* is the name of the foreign key table.</span></span>  
  
4.  <span data-ttu-id="55925-144">Klicken Sie in der Liste **Ausgewählte Beziehung** auf die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="55925-144">Click the relationship in the **Selected Relationship** list.</span></span>  
  
5.  <span data-ttu-id="55925-145">Klicken Sie im Datenblatt rechts auf **Tabellen- und Spaltenspezifikation**, und klicken Sie anschließend auf die rechts neben der Eigenschaft angezeigten Auslassungspunkte ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="55925-145">Click **Tables and Columns Specification** in the grid to the right and click the ellipses (**...**) to the right of the property.</span></span>  
  
6.  <span data-ttu-id="55925-146">Wählen Sie im Dialogfeld **Tabellen und Spalten** in der Dropdownliste **Primärschlüssel** die Tabelle aus, die sich auf der Primärschlüsselseite der Beziehung befinden soll.</span><span class="sxs-lookup"><span data-stu-id="55925-146">In the **Tables and Columns** dialog box, in the **Primary Key** drop-down list, choose the table that will be on the primary-key side of the relationship.</span></span>  
  
7.  <span data-ttu-id="55925-147">Wählen Sie im darunter angezeigten Datenblatt die Spalten aus, die für den Primärschlüssel der Tabelle verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="55925-147">In the grid beneath, choose the columns contributing to the table's primary key.</span></span> <span data-ttu-id="55925-148">Geben Sie in die jeweils links neben den einzelnen Spalten angrenzende Datenblattzelle die entsprechende Fremdschlüsselspalte aus der Fremdschlüsseltabelle ein.</span><span class="sxs-lookup"><span data-stu-id="55925-148">In the adjacent grid cell to the left of each column, choose the corresponding foreign-key column of the foreign-key table.</span></span>  
  
     <span data-ttu-id="55925-149">Der**Tabellen-Designer** schlägt einen Namen für die Beziehung vor.</span><span class="sxs-lookup"><span data-stu-id="55925-149">**Table Designer** suggests a name for the relationship.</span></span> <span data-ttu-id="55925-150">Wenn Sie diesen Namen ändern möchten, bearbeiten Sie den Inhalt des Textfelds **Beziehungsname** .</span><span class="sxs-lookup"><span data-stu-id="55925-150">To change this name, edit the contents of the **Relationship Name** text box.</span></span>  
  
8.  <span data-ttu-id="55925-151">Klicken Sie auf **OK** , um die Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="55925-151">Choose **OK** to create the relationship.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="55925-152">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="55925-152">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-foreign-key-in-a-new-table"></a><span data-ttu-id="55925-153">So erstellen Sie einen Fremdschlüssel in einer neuen Tabelle</span><span class="sxs-lookup"><span data-stu-id="55925-153">To create a foreign key in a new table</span></span>  
  
1.  <span data-ttu-id="55925-154">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="55925-154">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55925-155">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="55925-155">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55925-156">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="55925-156">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55925-157">Im Beispiel wird eine Tabelle erstellt und eine Fremdschlüsseleinschränkung für die Spalte `TempID` definiert, die auf die Spalte `SalesReasonID` in der Tabelle `Sales.SalesReason` verweist.</span><span class="sxs-lookup"><span data-stu-id="55925-157">The example creates a table and defines a foreign key constraint on the column `TempID` that references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span> <span data-ttu-id="55925-158">Die Klauseln ON DELETE CASCADE und ON UPDATE CASCADE werden verwendet, um sicherzustellen, dass an der `Sales.SalesReason` -Tabelle vorgenommene Änderungen automatisch an die Tabelle `Sales.TempSalesReason` weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="55925-158">The ON DELETE CASCADE and ON UPDATE CASCADE clauses are used to ensure that changes made to `Sales.SalesReason` table are automatically propagated to the `Sales.TempSalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE Sales.TempSalesReason (TempID int NOT NULL, Name nvarchar(50),   
    CONSTRAINT PK_TempSales PRIMARY KEY NONCLUSTERED (TempID),   
    CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    );GO  
  
    ```  
  
#### <a name="to-create-a-foreign-key-in-an-existing-table"></a><span data-ttu-id="55925-159">So erstellen Sie einen Fremdschlüssel in einer vorhandenen Tabelle</span><span class="sxs-lookup"><span data-stu-id="55925-159">To create a foreign key in an existing table</span></span>  
  
1.  <span data-ttu-id="55925-160">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="55925-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="55925-161">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="55925-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="55925-162">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="55925-162">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="55925-163">Im Beispiel wird ein Fremdschlüssel für die Spalte `TempID` erstellt und auf die Spalte `SalesReasonID` in der Tabelle `Sales.SalesReason` verwiesen.</span><span class="sxs-lookup"><span data-stu-id="55925-163">The example creates a foreign key on the column `TempID` and references the column `SalesReasonID` in the `Sales.SalesReason` table.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Sales.TempSalesReason   
    ADD CONSTRAINT FK_TempSales_SalesReason FOREIGN KEY (TempID)   
        REFERENCES Sales.SalesReason (SalesReasonID)   
        ON DELETE CASCADE  
        ON UPDATE CASCADE  
    ;  
    GO  
  
    ```  
  
     <span data-ttu-id="55925-164">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) und [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55925-164">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql), [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql), and [table_constraint &#40;Transact-SQL&#41;](/sql/relational-databases/system-information-schema-views/table-constraints-transact-sql).</span></span>  
  
  
