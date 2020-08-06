---
title: Auslassen eines Datenfelds mithilfe einer Formatdatei (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630655"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="932c7-102">Auslassen eines Datenfelds mithilfe einer Formatdatei (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="932c7-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="932c7-103">Eine Datendatei kann mehr Felder enthalten, als Spalten in der Tabelle vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="932c7-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="932c7-104">In diesem Thema wird beschrieben, wie Nicht-XML- und XML-Formatdateien an eine Datendatei mit mehr Feldern angepasst werden können, indem die Tabellenspalten den entsprechenden Datenfeldern zugeordnet und die übrigen Felder ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="932c7-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="932c7-105">Eine nicht-XML-oder XML-Format Datei kann verwendet werden, um einen Massen Import einer Datendatei in die-Tabelle mit einem **bcp** -Befehl, einer BULK INSERT-Anweisung oder einer INSERT... SELECT \* FROM OPENROWSET (BULK...)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="932c7-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="932c7-106">Weitere Informationen finden Sie unter [Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="932c7-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="932c7-107">Beispiel für Datendatei und Tabelle</span><span class="sxs-lookup"><span data-stu-id="932c7-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="932c7-108">Die in diesem Thema enthaltenen Beispiele über die geänderten Formatdateien basieren auf der folgenden Tabelle und Datendatei.</span><span class="sxs-lookup"><span data-stu-id="932c7-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="932c7-109">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="932c7-109">Sample Table</span></span>  
 <span data-ttu-id="932c7-110">Für die Beispiele muss in der `myTestSkipField` -Beispieldatenbank unter dem [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Schema eine Tabelle mit dem Namen `dbo` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="932c7-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="932c7-111">Führen Sie zum Erstellen dieser Tabelle im [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Abfrage-Editor den folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="932c7-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="932c7-112">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="932c7-112">Sample Data File</span></span>  
 <span data-ttu-id="932c7-113">Die Datendatei `myTestSkipField-c.dat`enthält die folgenden Datensätze:</span><span class="sxs-lookup"><span data-stu-id="932c7-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="932c7-114">Wenn ein Massenimport für Daten aus `myTestSkipField-c.dat` in die `myTestSkipField` -Tabelle ausgeführt werden soll, muss die Formatdatei folgende Funktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="932c7-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="932c7-115">Der ersten Spalte ( `PersonID`) das erste Datenfeld zuordnen.</span><span class="sxs-lookup"><span data-stu-id="932c7-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="932c7-116">Das zweite Datenfeld auslassen.</span><span class="sxs-lookup"><span data-stu-id="932c7-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="932c7-117">Der zweiten Spalte ( `FirstName`) das dritte Datenfeld zuordnen.</span><span class="sxs-lookup"><span data-stu-id="932c7-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="932c7-118">Der dritten Spalte ( `LastName`) das vierte Datenfeld zuordnen.</span><span class="sxs-lookup"><span data-stu-id="932c7-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="932c7-119">Nicht-XML-Formatdatei für weitere Datenfelder</span><span class="sxs-lookup"><span data-stu-id="932c7-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="932c7-120">Die Formatdatei `myTestSkipField.fmt` ordnet die Felder in `myTestSkipField-c.dat` den Spalten der `myTestSkipField`-Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="932c7-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="932c7-121">Die Formatdatei verwendet das Zeichendatenformat.</span><span class="sxs-lookup"><span data-stu-id="932c7-121">The format file uses character data format.</span></span> <span data-ttu-id="932c7-122">Damit eine Spaltenzuordnung ausgelassen werden kann, muss der Wert für die Spaltenreihenfolge auf 0 festgelegt werden, wie für die `ExtraField` -Spalte in der Formatdatei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="932c7-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="932c7-123">Die Formatdatei `myTestSkipField.fmt` enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="932c7-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="932c7-124">Informationen zur Syntax von Nicht-XML-Formatdateien finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="932c7-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="932c7-125">Beispiele</span><span class="sxs-lookup"><span data-stu-id="932c7-125">Examples</span></span>  
 <span data-ttu-id="932c7-126">Im folgenden Beispiel wird `INSERT ... SELECT * FROM OPENROWSET(BULK...)` mithilfe der Formatdatei `myTestSkipField.fmt` verwendet.</span><span class="sxs-lookup"><span data-stu-id="932c7-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="932c7-127">Die Datendatei `myTestSkipField-c.dat` wird per Massenimport in die `myTestSkipField` -Tabelle übertragen.</span><span class="sxs-lookup"><span data-stu-id="932c7-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="932c7-128">Hinweise zum Erstellen der Beispieltabelle und Datendatei finden Sie unter "Beispiel für Datendatei und Tabelle" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="932c7-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="932c7-129">Führen Sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor den folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="932c7-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="932c7-130">XML-Formatdatei für weitere Datenfelder</span><span class="sxs-lookup"><span data-stu-id="932c7-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="932c7-131">Die in diesem Beispiel verwendete Formatdatei basiert auf einer anderen Formatdatei, `myTestSkipField.xml`, in der durchgängig das Zeichendatenformat verwendet wird und deren Felder der Anzahl und Reihenfolge der Spalten in der `myTestSkipField`-Tabelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="932c7-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="932c7-132">Informationen, wie Sie den Inhalt dieser Formatdatei anzeigen, finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="932c7-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="932c7-133">Die Formatdatei `myTestSkipField.xml` ordnet die Felder in `myTestSkipField-c.dat` den Spalten der `myTestSkipField`-Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="932c7-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="932c7-134">Die Formatdatei verwendet das Zeichendatenformat.</span><span class="sxs-lookup"><span data-stu-id="932c7-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="932c7-135">Die Formatdatei `myTestSkipField.xml` enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="932c7-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="932c7-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="932c7-136">Examples</span></span>  
 <span data-ttu-id="932c7-137">Im folgenden Beispiel wird `INSERT ... SELECT * FROM OPENROWSET(BULK...)` mithilfe der Formatdatei `myTestSkipField.Xml` verwendet.</span><span class="sxs-lookup"><span data-stu-id="932c7-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="932c7-138">Die Datendatei `myTestSkipField-c.dat` wird per Massenimport in die `myTestSkipField` -Tabelle übertragen.</span><span class="sxs-lookup"><span data-stu-id="932c7-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="932c7-139">Hinweise zum Erstellen der Beispieltabelle und Datendatei finden Sie unter "Beispiel für Datendatei und Tabelle" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="932c7-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="932c7-140">Führen Sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor den folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="932c7-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="932c7-141">Informationen über die Syntax eines XML-Schemas und weitere Beispiele von XML-Formatdateien finden Sie unter [XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="932c7-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932c7-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="932c7-142">See Also</span></span>  
 <span data-ttu-id="932c7-143">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="932c7-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="932c7-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="932c7-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="932c7-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="932c7-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="932c7-146">[Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="932c7-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="932c7-147">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="932c7-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
