---
title: Massenimport von Daten mithilfe einer Formatdatei (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630656"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="fce5f-102">Massenimport von Daten mithilfe einer Formatdatei (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fce5f-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="fce5f-103">In diesem Thema wird die Verwendung einer Formatdatei bei Massenimportvorgängen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fce5f-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="fce5f-104">Durch die Formatdatei werden die Felder der Datendatei den Spalten der Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="fce5f-105">Sie können eine nicht-XML-oder XML-Format Datei für den Massen Import von Daten verwenden, wenn Sie einen **bcp** -Befehl oder eine BULK INSERT-oder INSERT... SELECT \* FROM OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] s.</span><span class="sxs-lookup"><span data-stu-id="fce5f-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fce5f-106">Damit eine Formatdatei mit einer Datendatei mit Unicode-Zeichen verwendet werden kann, müssen alle Eingabefelder Unicode-Textzeichenfolgen sein (d. h., entweder Unicode-Zeichenfolgen einer festen Länge oder Unicode-Zeichenfolgen mit Abschlusszeichen).</span><span class="sxs-lookup"><span data-stu-id="fce5f-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fce5f-107">Wenn Sie mit Format Dateien nicht vertraut sind, finden Sie weitere Informationen unter [nicht-XML-Format Dateien &#40;SQL Server&#41;](xml-format-files-sql-server.md) und [XML-Format Dateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fce5f-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="fce5f-108">Formatdateioptionen für Massenimportbefehle</span><span class="sxs-lookup"><span data-stu-id="fce5f-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="fce5f-109">In der folgenden Tabelle sind die Formatdateioptionen für die einzelnen Massenimportbefehle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fce5f-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="fce5f-110">Massenladebefehle</span><span class="sxs-lookup"><span data-stu-id="fce5f-110">Bulk-load Command</span></span>|<span data-ttu-id="fce5f-111">Verwenden der Formatdateioption</span><span class="sxs-lookup"><span data-stu-id="fce5f-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="fce5f-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fce5f-112">BULK INSERT</span></span>|<span data-ttu-id="fce5f-113">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="fce5f-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="fce5f-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="fce5f-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="fce5f-115">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="fce5f-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="fce5f-116">**bcp** ... **in**</span><span class="sxs-lookup"><span data-stu-id="fce5f-116">**bcp** ... **in**</span></span>|<span data-ttu-id="fce5f-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="fce5f-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="fce5f-118">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) oder [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fce5f-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fce5f-119">Verwenden Sie in der Formatdatei einen der folgenden Datentypen für den Massenexport oder -import von SQLXML-Daten: SQLCHAR oder SQLVARYCHAR (die Daten werden in der Clientcodepage oder in der Codepage, die durch die Sortierung impliziert wird, gesendet), SQLNCHAR oder SQLNVARCHAR (die Daten werden als Unicode gesendet) oder SQLBINARY oder SQLVARYBIN (die Daten werden ohne Konvertierung gesendet).</span><span class="sxs-lookup"><span data-stu-id="fce5f-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fce5f-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fce5f-120">Examples</span></span>  
 <span data-ttu-id="fce5f-121">Die Beispiele in diesem Abschnitt veranschaulichen die Verwendung von Format Dateien für den Massen Import von Daten mithilfe des **bcp** -Befehls und des BULK INSERT und einfügen... SELECT \* FROM OPENROWSET (BULK...)-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fce5f-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="fce5f-122">Bevor Sie eines der Beispiele für den Massenimport nachvollziehen können, müssen Sie eine entsprechende Tabelle, eine Datendatei und eine Formatdatei für das Beispiel erstellen.</span><span class="sxs-lookup"><span data-stu-id="fce5f-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="fce5f-123">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="fce5f-123">Sample Table</span></span>  
 <span data-ttu-id="fce5f-124">Damit die Beispiele nachvollzogen werden können, muss im **dbo**-Schema in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)]-Beispieldatenbank eine Tabelle mit der Bezeichnung **myTestFormatFiles** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fce5f-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="fce5f-125">Führen Sie Folgendes aus, um diese Tabelle im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fce5f-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="fce5f-126">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="fce5f-126">Sample Data File</span></span>  
 <span data-ttu-id="fce5f-127">Für die Beispiele wird eine Beispieldatendatei `myTestFormatFiles-c.Dat` verwendet, die die folgenden Datensätze enthält.</span><span class="sxs-lookup"><span data-stu-id="fce5f-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="fce5f-128">Geben Sie zur Erstellung der Datendatei an der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fce5f-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="fce5f-129">Beispielformatdateien</span><span class="sxs-lookup"><span data-stu-id="fce5f-129">Sample Format Files</span></span>  
 <span data-ttu-id="fce5f-130">Bei einigen Beispielen in diesem Abschnitt werden XML-Formatdateien, `myTestFormatFiles-f-x-c.Xml`, verwendet, während in anderen Beispielen Dateien in einem anderen Format verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fce5f-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="fce5f-131">Beide Formatdateitypen verwenden Zeichendatenformate und ein Feldabschlusszeichen (,), das nicht dem Standard entspricht.</span><span class="sxs-lookup"><span data-stu-id="fce5f-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="fce5f-132">Beispieldatei – Nicht im XML-Format</span><span class="sxs-lookup"><span data-stu-id="fce5f-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="fce5f-133">Im folgenden Beispiel wird zur Generierung einer XML-Formatdatei aus der `myTestFormatFiles`-Tabelle der Befehl **bcp** verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="fce5f-134">Die Datei `myTestFormatFiles.Fmt` enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="fce5f-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="fce5f-135">Wenn zur Erstellung dieser Formatdatei der **bcp**-Befehl mit der Option **format** verwendet werden soll, geben Sie an der Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fce5f-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="fce5f-136">Weitere Informationen zum Erstellen einer Formatdatei finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="fce5f-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="fce5f-137">Beispieldatei – Im XML-Format</span><span class="sxs-lookup"><span data-stu-id="fce5f-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="fce5f-138">Im folgenden Beispiel wird zur Erstellung einer XML-Formatdatei aus der `myTestFormatFiles`-Tabelle der Befehl **bcp** verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="fce5f-139">Die Datei `myTestFormatFiles.Xml` enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="fce5f-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="fce5f-140">Wenn zur Erstellung dieser Formatdatei der **bcp**-Befehl mit der Option **format** verwendet werden soll, geben Sie an der Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fce5f-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="fce5f-141">Verwenden von "bcp"</span><span class="sxs-lookup"><span data-stu-id="fce5f-141">Using bcp</span></span>  
 <span data-ttu-id="fce5f-142">Im nachfolgenden Beispiel wird der Befehl **bcp** für den Massenimport von Daten aus der `myTestFormatFiles-c.Dat`-Datendatei in die `HumanResources.myTestFormatFiles`-Tabelle der Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="fce5f-143">In diesem Beispiel wird die XML-Formatdatei `MyTestFormatFiles.Xml` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="fce5f-144">Vorhandene Tabellenzeilen werden in diesem Beispiel vor dem Import der Datendatei gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fce5f-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="fce5f-145">Geben Sie an der Windows-Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="fce5f-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fce5f-146">Weitere Informationen zu diesem Befehl finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="fce5f-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="fce5f-147">Verwenden von BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="fce5f-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="fce5f-148">Im nachfolgenden Beispiel wird BULK INSERT für den Massenimport von Daten aus der `myTestFormatFiles-c.Dat`-Datendatei in die `HumanResources.myTestFormatFiles`-Tabelle in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)]-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="fce5f-149">Im Beispiel wird die XML-Formatdatei `MyTestFormatFiles.Fmt` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="fce5f-150">Vorhandene Tabellenzeilen werden in diesem Beispiel vor dem Import der Datendatei gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fce5f-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="fce5f-151">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fce5f-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fce5f-152">Weitere Informationen zu dieser Anweisung finden Sie unter [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fce5f-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="fce5f-153">Verwenden des OPENROWSET-Bulk-Rowsetanbieters</span><span class="sxs-lookup"><span data-stu-id="fce5f-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="fce5f-154">Im nachfolgenden Beispiel wird `INSERT ... SELECT * FROM OPENROWSET(BULK...)` für den Massenimport von Daten aus der `myTestFormatFiles-c.Dat`-Datendatei in die `HumanResources.myTestFormatFiles`-Tabelle in der `AdventureWorks`-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="fce5f-155">In diesem Beispiel wird die XML-Formatdatei `MyTestFormatFiles.Xml` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fce5f-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="fce5f-156">Vorhandene Tabellenzeilen werden in diesem Beispiel vor dem Import der Datendatei gelöscht.</span><span class="sxs-lookup"><span data-stu-id="fce5f-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="fce5f-157">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fce5f-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="fce5f-158">Wenn Sie die Beispieltabelle nicht mehr benötigen, können Sie sie mit der folgenden Anweisung löschen:</span><span class="sxs-lookup"><span data-stu-id="fce5f-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fce5f-159">Weitere Informationen zur OPENROWSET BULK-Klausel finden Sie unter [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)zu markieren.</span><span class="sxs-lookup"><span data-stu-id="fce5f-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="fce5f-160">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="fce5f-160">Additional Examples</span></span>  
 [<span data-ttu-id="fce5f-161">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fce5f-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="fce5f-162">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fce5f-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="fce5f-163">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fce5f-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="fce5f-164">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fce5f-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="fce5f-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fce5f-165">See Also</span></span>  
 <span data-ttu-id="fce5f-166">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fce5f-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="fce5f-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fce5f-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="fce5f-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fce5f-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="fce5f-169">[Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fce5f-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="fce5f-170">XML-Formatdateien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fce5f-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
