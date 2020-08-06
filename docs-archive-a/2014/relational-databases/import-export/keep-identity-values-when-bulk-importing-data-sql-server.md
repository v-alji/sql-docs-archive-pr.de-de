---
title: Beibehalten von Identitätswerten beim Massenimport von Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- identity values [SQL Server], bulk imports
- data formats [SQL Server], identity values
- bulk importing [SQL Server], identity values
ms.assetid: 45894a3f-2d8a-4edd-9568-afa7d0d3061f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07f6714f27f60afda91134034509ff439d92f071
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620375"
---
# <a name="keep-identity-values-when-bulk-importing-data-sql-server"></a><span data-ttu-id="85cd8-102">Beibehalten von Identitätswerten beim Massenimport von Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="85cd8-102">Keep Identity Values When Bulk Importing Data (SQL Server)</span></span>
  <span data-ttu-id="85cd8-103">Datendateien, die Identitäts Werte enthalten, können per Massen Import in eine Instanz von importiert werden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85cd8-103">Data files that contain identity values can be bulk imported into an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="85cd8-104">Standardmäßig werden die Werte für die Identitätsspalte in der importierten Datendatei ignoriert, und von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden automatisch eindeutige Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="85cd8-104">By default, the values for the identity column in the data file that is imported are ignored and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns unique values automatically.</span></span> <span data-ttu-id="85cd8-105">Die eindeutigen Werte basieren auf dem Ausgangswert und den inkrementellen Werten, die bei der Tabellenerstellung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="85cd8-105">The unique values are based on the seed and increment values that are specified during table creation.</span></span>  
  
 <span data-ttu-id="85cd8-106">Wenn die Datendatei keine Werte für die Bezeichnerspalte in der Tabelle enthält, sollten Sie eine Formatdatei verwenden, um anzugeben, dass die Bezeichnerspalte beim Importieren von Daten ausgelassen werden soll.</span><span class="sxs-lookup"><span data-stu-id="85cd8-106">If the data file does not contain values for the identifier column in the table, use a format file to specify that the identifier column in the table should be skipped when importing data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="85cd8-107">weist der Spalte automatisch eindeutige Werte zu.</span><span class="sxs-lookup"><span data-stu-id="85cd8-107">assigns unique values for the column automatically.</span></span>  
  
 <span data-ttu-id="85cd8-108">Um zu verhindern, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beim Massenimport von Datenzeilen in eine Tabelle Identitätswerte zuweist, verwenden Sie den entsprechenden Qualifizierer für den Befehl zur Identitätsbeibehaltung (keepidentity).</span><span class="sxs-lookup"><span data-stu-id="85cd8-108">To prevent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from assigning identity values while bulk importing data rows into a table, use the appropriate keep-identity command qualifier.</span></span> <span data-ttu-id="85cd8-109">Wenn Sie einen Qualifizierer zur Identitätsbeibehaltung angeben, verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Identitätswerte in der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="85cd8-109">When you specify a keep-identity qualifier, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the identity values in the data file.</span></span> <span data-ttu-id="85cd8-110">Nachfolgend sind diese Qualifizierer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="85cd8-110">These qualifiers are as follows:</span></span>  
  
|<span data-ttu-id="85cd8-111">Get-Help</span><span class="sxs-lookup"><span data-stu-id="85cd8-111">Command</span></span>|<span data-ttu-id="85cd8-112">Qualifizierer zur Identitätsbeibehaltung</span><span class="sxs-lookup"><span data-stu-id="85cd8-112">Keep-identity qualifier</span></span>|<span data-ttu-id="85cd8-113">Qualifizierertyp</span><span class="sxs-lookup"><span data-stu-id="85cd8-113">Qualifier type</span></span>|  
|-------------|------------------------------|--------------------|  
|`bcp`|<span data-ttu-id="85cd8-114">**-E**</span><span class="sxs-lookup"><span data-stu-id="85cd8-114">**-E**</span></span>|<span data-ttu-id="85cd8-115">Schalter</span><span class="sxs-lookup"><span data-stu-id="85cd8-115">Switch</span></span>|  
|<span data-ttu-id="85cd8-116">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="85cd8-116">BULK INSERT</span></span>|<span data-ttu-id="85cd8-117">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="85cd8-117">KEEPIDENTITY</span></span>|<span data-ttu-id="85cd8-118">Argument</span><span class="sxs-lookup"><span data-stu-id="85cd8-118">Argument</span></span>|  
|<span data-ttu-id="85cd8-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="85cd8-119">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="85cd8-120">KEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="85cd8-120">KEEPIDENTITY</span></span>|<span data-ttu-id="85cd8-121">Tabellenhinweis</span><span class="sxs-lookup"><span data-stu-id="85cd8-121">Table hint</span></span>|  
  
 <span data-ttu-id="85cd8-122">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) und [Tabellenhinweise &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="85cd8-122">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85cd8-123">Weitere Informationen zu einer automatisch inkrementierten Zahl, die in mehreren Tabellen verwendet oder aus Anwendungen aufgerufen werden kann, ohne dass auf eine Tabelle verwiesen wird, finden Sie unter [Sequenznummern](../sequence-numbers/sequence-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="85cd8-123">To create an automatically incrementing number that can be used in multiple tables or that can be called from applications without referencing any table, see [Sequence Numbers](../sequence-numbers/sequence-numbers.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="85cd8-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="85cd8-124">Examples</span></span>  
 <span data-ttu-id="85cd8-125">In den Beispielen in diesem Thema wird der Massen Import von Daten mithilfe von INSERT... Wählen Sie \* FROM OPENROWSET (BULK...) aus, und behalten Sie die Standardwerte bei.</span><span class="sxs-lookup"><span data-stu-id="85cd8-125">The examples in this topic bulk import data using INSERT ... SELECT \* FROM OPENROWSET(BULK...) and keeping default values.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="85cd8-126">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="85cd8-126">Sample Table</span></span>  
 <span data-ttu-id="85cd8-127">Für den Massenimport muss eine Tabelle namens **myTestKeepNulls** erstellt werden, und zwar in der **AdventureWorks**-Beispieldatenbank unter dem **dbo**-Schema.</span><span class="sxs-lookup"><span data-stu-id="85cd8-127">The bulk-import examples require that a table named **myTestKeepNulls** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="85cd8-128">Führen Sie zum Erstellen dieser Tabelle</span><span class="sxs-lookup"><span data-stu-id="85cd8-128">To create this table.</span></span> <span data-ttu-id="85cd8-129">im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85cd8-129">in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
SELECT * INTO HumanResources.myDepartment   
   FROM HumanResources.Department  
      WHERE 1=0;  
GO  
SELECT * FROM HumanResources.myDepartment;  
```  
  
 <span data-ttu-id="85cd8-130">Für die **Department**-Tabelle, auf der `myDepartment` basiert, ist IDENTITY_INSERT auf OFF festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85cd8-130">The **Department** table on which `myDepartment` is based has IDENTITY_INSERT is set to OFF.</span></span> <span data-ttu-id="85cd8-131">Wenn Sie also Daten in eine Identitätsspalte importieren möchten, müssen Sie KEEPIDENTITY oder **-E** angeben.</span><span class="sxs-lookup"><span data-stu-id="85cd8-131">Therefore, to import data into an identity column you must specify KEEPIDENTITY or **-E**.</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="85cd8-132">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="85cd8-132">Sample Data File</span></span>  
 <span data-ttu-id="85cd8-133">Die in den Beispielen zum Massenimport verwendete Datendatei enthält massenkopierte Daten, die im systemeigenen Format aus der `HumanResources.Department`-Tabelle exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="85cd8-133">The data file used in the bulk-import examples contains data bulk exported from the `HumanResources.Department` table in native format.</span></span> <span data-ttu-id="85cd8-134">Geben Sie zur Erstellung der Datendatei an der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="85cd8-134">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out myDepartment-n.Dat -n -T  
```  
  
### <a name="sample-format-file"></a><span data-ttu-id="85cd8-135">Beispielformatdatei</span><span class="sxs-lookup"><span data-stu-id="85cd8-135">Sample Format File</span></span>  
 <span data-ttu-id="85cd8-136">In diesen Beispielen für den Massenimport wird eine Datei im XML-Format verwendet (`myDepartment-f-x-n.Xml`), von der wiederum systemeigene Datenformate verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85cd8-136">This bulk-import examples use an XML format file, `myDepartment-f-x-n.Xml`, which uses native data formats.</span></span> <span data-ttu-id="85cd8-137">In diesem Beispiel wird diese Formatdatei mit `bcp` mithilfe der `HumanResources.Department`-Tabelle der `AdventureWorks`-Datenbank generiert.</span><span class="sxs-lookup"><span data-stu-id="85cd8-137">This example uses `bcp` to create to generate this format file from the `HumanResources.Department` table of the `AdventureWorks` database.</span></span> <span data-ttu-id="85cd8-138">Geben Sie an der Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="85cd8-138">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department format nul -n -x -f myDepartment-f-n-x.Xml -T  
```  
  
 <span data-ttu-id="85cd8-139">Weitere Informationen zum Erstellen einer Formatdatei finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="85cd8-139">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="a-using-bcp-and-keeping-identity-values"></a><span data-ttu-id="85cd8-140">A.</span><span class="sxs-lookup"><span data-stu-id="85cd8-140">A.</span></span> <span data-ttu-id="85cd8-141">Mit "bcp" und unter Beibehaltung der Identitätswerte</span><span class="sxs-lookup"><span data-stu-id="85cd8-141">Using bcp and Keeping Identity Values</span></span>  
 <span data-ttu-id="85cd8-142">Anhand des nachfolgenden Beispiels wird veranschaulicht, wie Identitätswerte beibehalten werden können, wenn `bcp` für den Massenimport von Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85cd8-142">The following example demonstrates how to keep identity values when using `bcp` to bulk import data.</span></span> <span data-ttu-id="85cd8-143">Der Befehl `bcp` verwendet die Formatdatei `myDepartment-f-n-x.Xml` und enthält folgende Schalter:</span><span class="sxs-lookup"><span data-stu-id="85cd8-143">The `bcp` command uses the format file, `myDepartment-f-n-x.Xml`, and contains the following switches:</span></span>  
  
|<span data-ttu-id="85cd8-144">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="85cd8-144">Qualifiers</span></span>|<span data-ttu-id="85cd8-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85cd8-145">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="85cd8-146">**-E**</span><span class="sxs-lookup"><span data-stu-id="85cd8-146">**-E**</span></span>|<span data-ttu-id="85cd8-147">Gibt an, dass Identitätswerte in der Datendatei für die Identitätsspalte verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="85cd8-147">Specifies that identity value or values in the data file are to be used for the identity column.</span></span>|  
|<span data-ttu-id="85cd8-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="85cd8-148">**-T**</span></span>|<span data-ttu-id="85cd8-149">Gibt an, dass das `bcp` Hilfsprogramm [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine vertrauenswürdige Verbindung mit herstellt.</span><span class="sxs-lookup"><span data-stu-id="85cd8-149">Specifies that the `bcp` utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="85cd8-150">Geben Sie an der Windows-Eingabeaufforderung Folgendes ein.</span><span class="sxs-lookup"><span data-stu-id="85cd8-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myDepartment in C:\myDepartment-n.Dat -f C:\myDepartment-f-n-x.Xml -E -T  
  
```  
  
### <a name="b-using-bulk-insert-and-keeping-identity-values"></a><span data-ttu-id="85cd8-151">B.</span><span class="sxs-lookup"><span data-stu-id="85cd8-151">B.</span></span> <span data-ttu-id="85cd8-152">Mit BULK INSERT und unter Beibehaltung der Identitätswerte</span><span class="sxs-lookup"><span data-stu-id="85cd8-152">Using BULK INSERT and Keeping Identity Values</span></span>  
 <span data-ttu-id="85cd8-153">Im nachfolgenden Beispiel wird BULK INSERT für den Massenimport von Daten aus der `myDepartment-c.Dat`-Datei in die `AdventureWorks.HumanResources.myDepartment`-Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="85cd8-153">The following example uses BULK INSERT to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="85cd8-154">Die Anweisung verwendet die `myDepartment-f-n-x.Xml`-Formatdatei und nimmt die Option KEEPIDENTITY auf, um sicherzustellen, dass sämtliche Identitätswerte in der Datendatei beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="85cd8-154">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY option to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="85cd8-155">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85cd8-155">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
BULK INSERT HumanResources.myDepartment  
   FROM 'C:\myDepartment-n.Dat'  
   WITH (  
      KEEPIDENTITY,  
      FORMATFILE='C:\myDepartment-f-n-x.Xml'  
   );  
GO  
SELECT * FROM HumanResources.myDepartment;  
  
```  
  
### <a name="c-using-openrowset-and-keeping-identity-values"></a><span data-ttu-id="85cd8-156">C.</span><span class="sxs-lookup"><span data-stu-id="85cd8-156">C.</span></span> <span data-ttu-id="85cd8-157">Mit OPENROWSET und unter Beibehaltung der Identitätswerte</span><span class="sxs-lookup"><span data-stu-id="85cd8-157">Using OPENROWSET and Keeping Identity Values</span></span>  
 <span data-ttu-id="85cd8-158">Im nachfolgenden Beispiel wird der OPENROWSET-Massen-Rowset-Anbieter zum Massenimport von Daten aus der `myDepartment-c.Dat`-Datei in die `AdventureWorks.HumanResources.myDepartment`-Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="85cd8-158">The following example uses the OPENROWSET bulk rowset provider to bulk import data from the `myDepartment-c.Dat` file into the `AdventureWorks.HumanResources.myDepartment` table.</span></span> <span data-ttu-id="85cd8-159">Die Anweisung verwendet die `myDepartment-f-n-x.Xml`-Formatdatei und nimmt den KEEPIDENTITY-Hinweis auf, um sicherzustellen, dass sämtliche Identitätswerte in der Datendatei beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="85cd8-159">The statement uses the `myDepartment-f-n-x.Xml` format file and includes the KEEPIDENTITY hint to ensure that any identity values in the data file are retained.</span></span>  
  
 <span data-ttu-id="85cd8-160">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="85cd8-160">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DELETE HumanResources.myDepartment;  
GO  
  
INSERT INTO HumanResources.myDepartment  
   with (KEEPIDENTITY)  
   (DepartmentID, Name, GroupName, ModifiedDate)  
   SELECT *  
      FROM  OPENROWSET(BULK 'C:\myDepartment-n.Dat',  
      FORMATFILE='C:\myDepartment-f-n-x.Xml') as t1;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="85cd8-161">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="85cd8-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="85cd8-162">Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-162">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-163">Vorbereiten von Daten für den Massenexport oder -import &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-163">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="85cd8-164">**So verwenden Sie eine Formatdatei**</span><span class="sxs-lookup"><span data-stu-id="85cd8-164">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="85cd8-165">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-165">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-166">Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-166">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-167">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-167">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-168">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-168">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-169">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-169">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="85cd8-170">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="85cd8-170">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="85cd8-171">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="85cd8-171">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-172">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-172">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-173">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-173">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-174">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-174">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="85cd8-175">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-175">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="85cd8-176">**So geben Sie Datenformate für die Kompatibilität bei Verwendung von bcp an**</span><span class="sxs-lookup"><span data-stu-id="85cd8-176">**To specify data formats for compatibility when using bcp**</span></span>  
  
1.  [<span data-ttu-id="85cd8-177">Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-177">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
2.  [<span data-ttu-id="85cd8-178">Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-178">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
3.  [<span data-ttu-id="85cd8-179">Angeben des Dateispeichertyps mithilfe von bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-179">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="85cd8-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85cd8-180">See Also</span></span>  
 <span data-ttu-id="85cd8-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85cd8-181">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="85cd8-182">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="85cd8-182">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="85cd8-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85cd8-183">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="85cd8-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85cd8-184">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="85cd8-185">Tabellenhinweise &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85cd8-185">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
