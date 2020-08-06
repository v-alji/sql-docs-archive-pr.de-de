---
title: Angeben von berechneten Spalten in einer Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- computed columns, define
ms.assetid: 731a4576-09c1-47f0-a8f6-edd0b55679f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e4df8d67b61e50383ffd8e33f982990ff3f2ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620755"
---
# <a name="specify-computed-columns-in-a-table"></a><span data-ttu-id="98038-102">Angeben von berechneten Spalten in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="98038-102">Specify Computed Columns in a Table</span></span>
  <span data-ttu-id="98038-103">Eine berechnete Spalte ist eine virtuelle Spalte, die nicht physisch in der Tabelle gespeichert ist, es sei denn, die Spalte wurde (mit PERSISTED) als persistente Spalte markiert.</span><span class="sxs-lookup"><span data-stu-id="98038-103">A computed column is a virtual column that is not physically stored in the table, unless the column is marked PERSISTED.</span></span> <span data-ttu-id="98038-104">Der Ausdruck für eine berechnete Spalte kann aus Daten anderer Spalten einen Wert für die Spalte berechnen, der er zuwiesen ist.</span><span class="sxs-lookup"><span data-stu-id="98038-104">A computed column expression can use data from other columns to calculate a value for the column to which it belongs.</span></span> <span data-ttu-id="98038-105">Sie können mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)] einen Ausdruck für eine berechnete Spalte in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] angeben.</span><span class="sxs-lookup"><span data-stu-id="98038-105">You can specify an expression for a computed column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="98038-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="98038-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98038-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="98038-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98038-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="98038-108">Limitations and Restrictions</span></span>](#Limitations)  
  
     [<span data-ttu-id="98038-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="98038-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98038-110">**So geben Sie eine berechnete Spalte an mit:**</span><span class="sxs-lookup"><span data-stu-id="98038-110">**To specify a computed column, using:**</span></span>  
  
     [<span data-ttu-id="98038-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98038-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98038-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98038-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98038-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="98038-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Limitations"></a> <span data-ttu-id="98038-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="98038-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="98038-115">Eine berechnete Spalte kann nicht als DEFAULT- oder FOREIGN KEY-Einschränkungsdefinition oder mit einer NOT NULL-Einschränkungsdefinition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98038-115">A computed column cannot be used as a DEFAULT or FOREIGN KEY constraint definition or with a NOT NULL constraint definition.</span></span> <span data-ttu-id="98038-116">Eine berechnete Spalte kann jedoch als Schlüsselspalte in einem Index oder als Teil einer PRIMARY KEY- oder UNIQUE-Einschränkung verwendet werden, wenn der Wert der berechneten Spalte durch einen deterministischen Ausdruck definiert ist und der Datentyp des Ergebnisses in Indexspalten zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="98038-116">However, if the computed column value is defined by a deterministic expression and the data type of the result is allowed in index columns, a computed column can be used as a key column in an index or as part of any PRIMARY KEY or UNIQUE constraint.</span></span> <span data-ttu-id="98038-117">Falls die Tabelle z. B. die Spalten "a" und "b" vom Datentyp int aufweist, kann die berechnete Spalte "a + b" indiziert werden. Dagegen kann die berechnete Spalte "a + DATEPART(dd, GETDATE())" nicht indiziert werden, da sich der Wert in späteren Aufrufen ändern kann.</span><span class="sxs-lookup"><span data-stu-id="98038-117">For example, if the table has integer columns a and b, the computed column a + b may be indexed, but computed column a + DATEPART(dd, GETDATE()) cannot be indexed, because the value might change in subsequent invocations.</span></span>  
  
-   <span data-ttu-id="98038-118">Eine berechnete Spalte kann nicht das Ziel einer INSERT- oder UPDATE-Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="98038-118">A computed column cannot be the target of an INSERT or UPDATE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98038-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="98038-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98038-120">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="98038-120">Permissions</span></span>  
 <span data-ttu-id="98038-121">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="98038-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98038-122">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98038-122">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-add-a-new-computed-column"></a><a name="NewColumn"></a> <span data-ttu-id="98038-123">So fügen Sie eine neue berechnete Spalte hinzu</span><span class="sxs-lookup"><span data-stu-id="98038-123">To add a new computed column</span></span>  
  
1.  <span data-ttu-id="98038-124">Erweitern Sie in **Objekt-Explorer**die Tabelle, der Sie die neue berechnete Spalte hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="98038-124">In **Object Explorer**, expand the table for which you want to add the new computed column.</span></span> <span data-ttu-id="98038-125">Klicken Sie mit der rechten Maustaste auf **Spalten** , und wählen Sie **Neue Spalte**aus.</span><span class="sxs-lookup"><span data-stu-id="98038-125">Right-click **Columns** and select **New Column**.</span></span>  
  
2.  <span data-ttu-id="98038-126">Geben Sie den Spaltennamen ein, und akzeptieren Sie den Standarddatentyp (`nchar`(10)).</span><span class="sxs-lookup"><span data-stu-id="98038-126">Enter the column name and accept the default data type (`nchar`(10)).</span></span> <span data-ttu-id="98038-127">[!INCLUDE[ssDE](../../includes/ssde-md.md)] ermittelt den Datentyp der berechneten Spalte, indem die Regeln zur Rangfolge von Datentypen auf Ausdrücke angewendet werden, die in der Formel angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="98038-127">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines the data type of the computed column by applying the rules of data type precedence to the expressions specified in the formula.</span></span> <span data-ttu-id="98038-128">Wenn die Formel beispielsweise auf eine Spalte vom Typ `money` und eine Spalte vom Typ `int` verweist, weist die berechnete Spalte den Typ `money` auf, da dieser Datentyp die höhere Rangfolge hat.</span><span class="sxs-lookup"><span data-stu-id="98038-128">For example, if the formula references a column of type `money` and a column of type `int`, the computed column will be of type `money` because that data type has the higher precedence.</span></span> <span data-ttu-id="98038-129">Weitere Informationen finden Sie unter [Rangfolge der Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98038-129">For more information, see [Data Type Precedence &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-type-precedence-transact-sql).</span></span>  
  
3.  <span data-ttu-id="98038-130">Erweitern Sie auf der Registerkarte **Spalteneigenschaften** die **BerechneteSpalteSpezifikation** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="98038-130">In the **Column Properties** tab, expand the **Computed Column Specification** property.</span></span>  
  
4.  <span data-ttu-id="98038-131">Geben Sie für die untergeordnete Eigenschaft **(Formel)** in der Datenblattzelle auf der rechten Seite den Ausdruck für diese Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="98038-131">In the **(Formula)** child property, enter the expression for this column in the grid cell to the right.</span></span> <span data-ttu-id="98038-132">In einer `SalesTotal` -Spalte kann die eingegebene Formel z. B. `SubTotal+TaxAmt+Freight`lauten, wodurch für jede Tabellenzeile der Wert in diesen Spalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="98038-132">For example, in a `SalesTotal` column, the formula you enter might be `SubTotal+TaxAmt+Freight`, which adds the value in these columns for each row in the table.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="98038-133">Wenn in einer Formel zwei Ausdrücke verschiedener Datentypen kombiniert sind, geben die Rangfolgeregeln für Datentypen an, dass der Datentyp mit der niedrigeren Rangfolge in den Datentyp mit der höheren Rangfolge konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="98038-133">When a formula combines two expressions of different data types, the rules for data type precedence specify that the data type with the lower precedence is converted to the data type with the higher precedence.</span></span> <span data-ttu-id="98038-134">Wenn es sich bei der Konvertierung nicht um eine unterstützte implizite Konvertierung handelt, wird der Fehler "`Error validating the formula for column column_name.`" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98038-134">If the conversion is not a supported implicit conversion, the error "`Error validating the formula for column column_name.`" is returned.</span></span> <span data-ttu-id="98038-135">Verwenden Sie die CAST-Funktion oder CONVERT-Funktion, um den Datentypkonflikt aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="98038-135">Use the CAST or CONVERT function to resolve the data type conflict.</span></span> <span data-ttu-id="98038-136">Wenn beispielsweise eine Spalte vom Typ `nvarchar` mit einer Spalte vom Typ `int` kombiniert wird, muss der ganzzahlige Typ in `nvarchar` konvertiert werden, wie in der folgenden Formel `('Prod'+CONVERT(nvarchar(23),ProductID))` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="98038-136">For example, if a column of type `nvarchar` is combined with a column of type `int`, the integer type must be converted to `nvarchar` as shown in this formula `('Prod'+CONVERT(nvarchar(23),ProductID))`.</span></span> <span data-ttu-id="98038-137">Weitere Informationen finden Sie unter [CAST und CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98038-137">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
5.  <span data-ttu-id="98038-138">Geben Sie an, ob die Daten persistent gespeichert werden sollen, indem Sie im Dropdownfeld für die untergeordnete Eigenschaft **IsPersisted** die Option **Ja** oder **Nein** wählen.</span><span class="sxs-lookup"><span data-stu-id="98038-138">Indicate whether the data is persisted by choosing **Yes** or **No** from the drop-down for the **Is Persisted** child property.</span></span>  
  
6.  <span data-ttu-id="98038-139">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="98038-139">On the **File** menu, click **Save**_table name_.</span></span>  
  
#### <a name="to-add-a-computed-column-definition-to-an-existing-column"></a><span data-ttu-id="98038-140">So fügen Sie einer vorhandenen Spalte die Definition einer berechneten Spalte hinzu</span><span class="sxs-lookup"><span data-stu-id="98038-140">To add a computed column definition to an existing column</span></span>  
  
1.  <span data-ttu-id="98038-141">Klicken Sie im **Objekt-Explorer** mit der rechten Maustaste auf die Tabelle mit der Spalte, für die Sie den Ordner **Spalten** ändern und erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="98038-141">In **Object Explorer**, right-click the table with the column for which you want to change and expand the **Columns** folder.</span></span>  
  
2.  <span data-ttu-id="98038-142">Klicken Sie mit der rechten Maustaste auf die Spalte, für die Sie die Formel einer berechneten Spalte angeben möchten, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="98038-142">Right-click the column for which you want to specify a computed column formula and click **Delete**.</span></span> <span data-ttu-id="98038-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="98038-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="98038-144">Fügen Sie eine neue Spalte hinzu, und geben Sie die Formel der berechneten Spalte an, indem Sie die vorangehenden Schritte ausführen, um eine neue berechnete Spalte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="98038-144">Add a new column and specify the computed column formula by following the previous procedure to add a new computed column.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98038-145">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98038-145">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-computed-column-when-creating-a-table"></a><span data-ttu-id="98038-146">So fügen Sie eine berechnete Spalte beim Erstellen einer Tabelle hinzu</span><span class="sxs-lookup"><span data-stu-id="98038-146">To add a computed column when creating a table</span></span>  
  
1.  <span data-ttu-id="98038-147">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="98038-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98038-148">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="98038-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98038-149">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="98038-149">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="98038-150">Im Beispiel wird eine Tabelle mit einer berechneten Spalte erstellt, die den Wert in der Spalte `QtyAvailable` mit dem Wert in der Spalte `UnitPrice` multipliziert.</span><span class="sxs-lookup"><span data-stu-id="98038-150">The example creates a table with a computed column that multiplies the value in the `QtyAvailable` column times the value in the `UnitPrice` column.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products   
    (  
        ProductID int IDENTITY (1,1) NOT NULL  
      , QtyAvailable smallint  
      , UnitPrice money  
      , InventoryValue AS QtyAvailable * UnitPrice  
    );  
  
    -- Insert values into the table.  
    INSERT INTO dbo.Products (QtyAvailable, UnitPrice)  
    VALUES (25, 2.00), (10, 1.5);  
  
    -- Display the rows in the table.  
    SELECT ProductID, QtyAvailable, UnitPrice, InventoryValue  
    FROM dbo.Products;  
  
    ```  
  
#### <a name="to-add-a-new-computed-column-to-an-existing-table"></a><span data-ttu-id="98038-151">So fügen Sie einer vorhandenen Tabelle eine neue berechnete Spalte hinzu</span><span class="sxs-lookup"><span data-stu-id="98038-151">To add a new computed column to an existing table</span></span>  
  
1.  <span data-ttu-id="98038-152">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="98038-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98038-153">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="98038-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98038-154">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="98038-154">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="98038-155">Im folgenden Beispiel wird der im vorangehenden Beispiel erstellten Tabelle eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98038-155">The following example adds a new column to the table created in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.35);  
  
    ```  
  
#### <a name="to-change-an-existing-column-to-a-computed-column"></a><span data-ttu-id="98038-156">So ändern Sie eine vorhandene Spalte in eine berechnete Spalte</span><span class="sxs-lookup"><span data-stu-id="98038-156">To change an existing column to a computed column</span></span>  
  
1.  <span data-ttu-id="98038-157">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="98038-157">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="98038-158">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="98038-158">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="98038-159">Um eine vorhandene Spalte in eine berechnete Spalte zu ändern, müssen Sie die berechnete Spalte entfernen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98038-159">To change an existing column to a computed column you must drop and re-create the computed column.</span></span> <span data-ttu-id="98038-160">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="98038-160">Copy and paste the following example into the query window and then click **Execute**.</span></span> <span data-ttu-id="98038-161">Im folgenden Beispiel wird die im vorangehenden Beispiel hinzugefügte Spalte geändert.</span><span class="sxs-lookup"><span data-stu-id="98038-161">The following example modifies the column added in the previous example.</span></span>  
  
    ```  
    ALTER TABLE dbo.Products DROP COLUMN RetailValue;  
    GO  
    ALTER TABLE dbo.Products ADD RetailValue AS (QtyAvailable * UnitPrice * 1.5);  
  
    ```  
  
     <span data-ttu-id="98038-162">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98038-162">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
