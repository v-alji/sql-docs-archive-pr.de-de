---
title: Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724733"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="a5ce8-102">Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a5ce8-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="a5ce8-103">Wenn Daten in eine Tabelle importiert werden, werden standardmäßig alle für die Spalten in der Tabelle definierten Standardwerte durch den Befehl **bcp** und die Anweisung BULK INSERT überwacht.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="a5ce8-104">Wenn beispielsweise ein NULL-Feld in einem Datenfeld vorkommt, wird stattdessen der Standardwert für die Spalte geladen.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="a5ce8-105">Sowohl mit dem Befehl **bcp** als auch mit der Anweisung BULK INSERT können Sie angeben, dass NULL-Werte beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="a5ce8-106">Eine reguläre INSERT-Anweisung hingegen behält den NULL-Wert bei, statt einen Standardwert einzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="a5ce8-107">Die INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung zeigt dasselbe grundlegende Verhalten wie eine reguläre INSERT-Anweisung, unterstützt jedoch zusätzlich einen Tabellenhinweis zum Einfügen der Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5ce8-108">Beispielformatdateien, mit denen eine Tabellenspalte übersprungen wird, finden Sie unter [Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5ce8-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="a5ce8-109">Beispieltabelle und Datendatei</span><span class="sxs-lookup"><span data-stu-id="a5ce8-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="a5ce8-110">Zum Ausführen der Beispiele in diesem Thema müssen Sie eine Beispieltabelle und -datendatei erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="a5ce8-111">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="a5ce8-111">Sample Table</span></span>  
 <span data-ttu-id="a5ce8-112">Die Beispiele erfordern, dass eine Tabelle mit dem Namen **MyTestDefaultCol2** in der **AdventureWorks**-Beispieldatenbank unter dem Schema **dbo** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="a5ce8-113">Führen Sie Folgendes aus, um diese Tabelle im [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="a5ce8-114">Beachten Sie, dass die zweite Tabellenspalte `Col2` einen Standardwert hat.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="a5ce8-115">Beispielformatdatei</span><span class="sxs-lookup"><span data-stu-id="a5ce8-115">Sample Format File</span></span>  
 <span data-ttu-id="a5ce8-116">Einige der Massenimportbeispiele verwenden die nicht im XML-Format vorliegende Datei `MyTestDefaultCol2-f-c.Fmt`, die der `MyTestDefaultCol2`-Tabelle genau entspricht.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="a5ce8-117">Geben Sie zum Erstellen dieser Formatdatei an der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="a5ce8-118">Weitere Informationen zum Erstellen von Formatdateien finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md), um Standardwerte zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="a5ce8-119">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="a5ce8-119">Sample Data File</span></span>  
 <span data-ttu-id="a5ce8-120">Das Beispiel verwendet die Beispieldatendatei `MyTestEmptyField2-c.Dat`, die im zweiten Feld keine Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="a5ce8-121">Die Datendatei `MyTestEmptyField2-c.Dat` enthält die folgenden Datensätze.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="a5ce8-122">Beibehalten von NULL-Werten mit "bcp" oder BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="a5ce8-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="a5ce8-123">Die folgenden Qualifizierer geben an, dass ein leeres Feld in der Datendatei seinen NULL-Wert während des Massenimportvorgangs beibehält, statt (ggf.) einen Standardwert für die Tabellenspalten zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="a5ce8-124">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a5ce8-124">Command</span></span>|<span data-ttu-id="a5ce8-125">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="a5ce8-125">Qualifier</span></span>|<span data-ttu-id="a5ce8-126">Qualifizierertyp</span><span class="sxs-lookup"><span data-stu-id="a5ce8-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="a5ce8-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="a5ce8-127">**bcp**</span></span>|`-k`|<span data-ttu-id="a5ce8-128">Schalter</span><span class="sxs-lookup"><span data-stu-id="a5ce8-128">Switch</span></span>|  
|<span data-ttu-id="a5ce8-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="a5ce8-129">BULK INSERT</span></span>|<span data-ttu-id="a5ce8-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a5ce8-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="a5ce8-131">Argument</span><span class="sxs-lookup"><span data-stu-id="a5ce8-131">Argument</span></span>|  
  
 <span data-ttu-id="a5ce8-132"><sup>1</sup> für BULK INSERT, wenn keine Standardwerte verfügbar sind, muss die Tabellenspalte so definiert sein, dass NULL-Werte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5ce8-133">Diese Qualifizierer deaktivieren das Prüfen von DEFAULT-Definitionen in einer Tabelle durch diese Massenimportbefehle.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="a5ce8-134">Für gleichzeitige INSERT-Anweisungen werden jedoch DEFAULT-Definitionen erwartet.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="a5ce8-135">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md) und [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a5ce8-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a5ce8-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a5ce8-136">Examples</span></span>  
 <span data-ttu-id="a5ce8-137">In den Beispielen dieses Abschnitts werden Massenimporte mithilfe von **bcp** oder BULK INSERT ausgeführt und NULL-Werte beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="a5ce8-138">Die zweite Tabellenspalte, **Col2**, hat einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="a5ce8-139">Das entsprechende Feld der Datendatei enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="a5ce8-140">Wenn **bcp** oder BULK INSERT zum Importieren von Daten aus dieser Datendatei in die **MyTestDefaultCol2**-Tabelle verwendet wird, wird standardmäßig der Standardwert von **Col2** eingefügt, sodass das folgende Ergebnis erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="a5ce8-141">Um " `NULL` " anstelle von "" einzufügen `Default value of Col2` , müssen Sie die `-k` Option Switch oder KEEPNULL verwenden, wie in den folgenden **bcp** -und BULK INSERT Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="a5ce8-142">Verwenden von "bcp" und Beibehalten von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="a5ce8-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="a5ce8-143">Das folgende Beispiel zeigt, wie NULL-Werte in einem **bcp**-Befehl beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="a5ce8-144">Der Befehl **bcp** enthält die folgenden Schalter:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="a5ce8-145">Schalter</span><span class="sxs-lookup"><span data-stu-id="a5ce8-145">Switch</span></span>|<span data-ttu-id="a5ce8-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a5ce8-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="a5ce8-147">Gibt an, dass der Befehl eine Formatdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="a5ce8-148">Gibt an, dass während des Vorgangs keine Standardwerte in leere Spalten eingefügt werden, sondern ein NULL-Wert für diese Spalten beibehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="a5ce8-149">Gibt an, dass das Hilfsprogramm "bcp" eine vertrauenswürdige Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellt.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="a5ce8-150">Geben Sie an der Windows-Eingabeaufforderung Folgendes ein.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="a5ce8-151">Verwenden von BULK INSERT und Beibehalten von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="a5ce8-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="a5ce8-152">Das folgende Beispiel zeigt, wie die Option KEEPNULLS in einer BULK INSERT-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="a5ce8-153">Führen Sie von einem Abfragetool, beispielsweise dem [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor, folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="a5ce8-154">Beibehalten von Standardwerten mit INSERT... SELECT \* FROM OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="a5ce8-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="a5ce8-155">Standardmäßig werden alle Spalten, die nicht im Massen Ladevorgang angegeben sind, durch INSERT... SELECT \* FROM OPENROWSET (BULK...). Sie können jedoch angeben, dass die entsprechende Tabellenspalte für ein leeres Feld in der Datendatei den Standardwert (sofern vorhanden) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="a5ce8-156">Zum Verwenden von Standardwerten geben Sie den folgenden Tabellenhinweis an:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="a5ce8-157">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a5ce8-157">Command</span></span>|<span data-ttu-id="a5ce8-158">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="a5ce8-158">Qualifier</span></span>|<span data-ttu-id="a5ce8-159">Qualifizierertyp</span><span class="sxs-lookup"><span data-stu-id="a5ce8-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="a5ce8-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="a5ce8-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="a5ce8-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="a5ce8-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="a5ce8-162">Tabellenhinweis</span><span class="sxs-lookup"><span data-stu-id="a5ce8-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a5ce8-163">Weitere Informationen finden Sie unter [Einfügen &#40;Transact-SQL-&#41;](/sql/t-sql/statements/insert-transact-sql), [Auswählen von &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL-&#41;](/sql/t-sql/functions/openrowset-transact-sql)und [Tabellen Hinweise &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="a5ce8-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a5ce8-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a5ce8-164">Examples</span></span>  
 <span data-ttu-id="a5ce8-165">Der folgende INSERT... SELECT \* FROM OPENROWSET (BULK...) example Massenimporte von Daten und beibehalten der Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="a5ce8-166">Um die Beispiele auszuführen, müssen Sie die **MyTestDefaultCol2**-Beispieltabelle und die Datendatei `MyTestEmptyField2-c.Dat` erstellen und die Formatdatei `MyTestDefaultCol2-f-c.Fmt` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="a5ce8-167">Weitere Informationen zum Erstellen dieser Beispiele finden Sie unter "Beispieltabelle und Datendatei" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="a5ce8-168">Die zweite Tabellenspalte, **Col2**, hat einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="a5ce8-169">Das entsprechende Feld der Datendatei enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="a5ce8-170">Wenn INSERT... Select \* FROM OPENROWSET (BULK...) importieren Sie die Felder dieser Datendatei in die **MyTestDefaultCol2** -Tabelle. Standardmäßig wird NULL anstelle des Standardwerts in **Col2** eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="a5ce8-171">Dieses Standardverhalten führt zu folgendem Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="a5ce8-172">Um den Standardwert "`Default value of Col2`" anstelle von "`NULL`" einzufügen, müssen Sie den Tabellenhinweis KEEPDEFAULTS verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5ce8-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="a5ce8-173">Führen Sie von einem Abfragetool, beispielsweise dem [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor, folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="a5ce8-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a5ce8-174">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a5ce8-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a5ce8-175">Beibehalten von Identitätswerten beim Massenimport von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-176">Vorbereiten von Daten für den Massenexport oder -import &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="a5ce8-177">**So verwenden Sie eine Formatdatei**</span><span class="sxs-lookup"><span data-stu-id="a5ce8-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="a5ce8-178">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-179">Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-180">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-181">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-182">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="a5ce8-183">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="a5ce8-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="a5ce8-184">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="a5ce8-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-185">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-186">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-187">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-188">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="a5ce8-189">**So geben Sie Datenformate für die Kompatibilität bei Verwendung von bcp an**</span><span class="sxs-lookup"><span data-stu-id="a5ce8-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="a5ce8-190">Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-191">Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="a5ce8-192">Angeben des Dateispeichertyps mithilfe von bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5ce8-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5ce8-193">See Also</span></span>  
 <span data-ttu-id="a5ce8-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5ce8-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a5ce8-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5ce8-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="a5ce8-196">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a5ce8-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="a5ce8-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a5ce8-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="a5ce8-198">Tabellenhinweise &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a5ce8-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
