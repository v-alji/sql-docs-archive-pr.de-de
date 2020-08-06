---
title: Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- mapping columns to fields during import [SQL Server]
- format files [SQL Server], mapping columns to fields
ms.assetid: e7ee4f7e-24c4-4eb7-84d2-41e57ccc1ef1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7de0b5ce486f187a1bdd27197984aa3c411f4a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615389"
---
# <a name="use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server"></a><span data-ttu-id="21195-102">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="21195-102">Use a Format File to Map Table Columns to Data-File Fields (SQL Server)</span></span>
  <span data-ttu-id="21195-103">Eine Datendatei kann Felder in einer anderen Reihenfolge als die der entsprechenden Spalten in der Tabelle aufweisen.</span><span class="sxs-lookup"><span data-stu-id="21195-103">A data file can contain fields arranged in a different order from the corresponding columns in the table.</span></span> <span data-ttu-id="21195-104">In diesem Thema werden Nicht-XML-Formatdateien und XML-Formatdateien dargestellt, die zum Anpassen an eine Datendatei, deren Felder eine andere Reihenfolge als die Tabellenspalten aufweisen, geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="21195-104">This topic presents both non-XML and XML format files that have been modified to accommodate a data file whose fields are arranged in a different order from the table columns.</span></span> <span data-ttu-id="21195-105">Die geänderte Formatdatei ordnet die Datenfelder den entsprechenden Tabellenspalten zu.</span><span class="sxs-lookup"><span data-stu-id="21195-105">The modified format file maps the data fields to their corresponding table columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21195-106">Eine nicht-XML-Format Datei oder eine XML-Format Datei kann verwendet werden, um einen Massen Import einer Datendatei in die-Tabelle mit einem **bcp** -Befehl, einer BULK INSERT-Anweisung oder einer INSERT... SELECT \* FROM OPENROWSET (BULK...)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="21195-106">Either a non-XML format file or an XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="21195-107">Weitere Informationen finden Sie unter [Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="21195-107">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="21195-108">Beispieltabelle und Datendatei</span><span class="sxs-lookup"><span data-stu-id="21195-108">Sample Table and Data File</span></span>  
 <span data-ttu-id="21195-109">Die in diesem Thema enthaltenen Beispiele über die geänderten Formatdateien basieren auf der folgenden Tabelle und Datendatei.</span><span class="sxs-lookup"><span data-stu-id="21195-109">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="21195-110">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="21195-110">Sample Table</span></span>  
 <span data-ttu-id="21195-111">Für die Beispiele in diesem Thema muss in der `myTestOrder` -Beispieldatenbank unter dem [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] -Schema eine Tabelle namens `dbo` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="21195-111">The examples in this topic require that a table named `myTestOrder` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="21195-112">Führen Sie den folgenden Code aus, um diese Tabelle im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="21195-112">To create this table, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestOrder   
   (  
   Col1 smallint,  
   Col2 nvarchar(50) ,  
   Col3 nvarchar(50) ,   
   Col4 nvarchar(50)   
   );  
GO  
  
```  
  
### <a name="data-file"></a><span data-ttu-id="21195-113">Datendatei</span><span class="sxs-lookup"><span data-stu-id="21195-113">Data File</span></span>  
 <span data-ttu-id="21195-114">Die Datendatei `myTestOrder-c.txt`enthält die folgenden Datensätze:</span><span class="sxs-lookup"><span data-stu-id="21195-114">The data file, `myTestOrder-c.txt`, contains the following records:</span></span>  
  
```  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
  
```  
  
 <span data-ttu-id="21195-115">Zum Massenimportieren der Daten von `myTestSkipCol2-c.dat` in die Tabelle `myTestSkipCol` muss in der Formatdatei das erste Datenfeld der Spalte `Col3`, das zweite Datenfeld der Spalte `Col2`, das dritte Datenfeld der Spalte `Col1` und das vierte Datenfeld der Spalte `Col4` zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="21195-115">To bulk import data from `myTestSkipCol2-c.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col3`, the second data field to `Col2`, the third data field to `Col1`, and the fourth data field to `Col4`.</span></span>  
  
## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="21195-116">Verwenden einer Nicht-XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="21195-116">Using a Non-XML Format File</span></span>  
 <span data-ttu-id="21195-117">Sie können die Reihenfolge einer Spaltenzuordnung ändern, indem Sie zur Positionsangabe des entsprechenden Datenfelds den Reihenfolgenwert der Spalte ändern.</span><span class="sxs-lookup"><span data-stu-id="21195-117">You can change the order of a column mapping by changing the order value for the column to indicate the position of the corresponding data field.</span></span>  
  
 <span data-ttu-id="21195-118">Die folgende Beispielformatdatei im Nicht-XML-Format, `myTestOrder.fmt`, ordnet die Felder in `myTestOrder-c.txt` den Spalten der `myTestOrder`-Tabelle zu.</span><span class="sxs-lookup"><span data-stu-id="21195-118">The following sample non-XML format file presents a format file, `myTestOrder.fmt`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table.</span></span> <span data-ttu-id="21195-119">Informationen zum Erstellen der Datendatei und der Tabelle finden Sie unter "Beispieltabelle und Datendatei" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="21195-119">For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="21195-120">Die Formatdatei verwendet das Zeichendatenformat.</span><span class="sxs-lookup"><span data-stu-id="21195-120">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="21195-121">Die Formatdatei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="21195-121">The format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       100     ","     3     Col3               SQL_Latin1_General_CP1_CI_AS  
2       SQLCHAR       0       100     ","     2     Col2               SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       7       ","     1     Col1               ""  
4       SQLCHAR       0       100     "\r\n"  4     Col4               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="21195-122">Weitere Informationen zum Layout von Nicht-XML-Formatdateien finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="21195-122">For more information about the layout of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="21195-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21195-123">Example</span></span>  
 <span data-ttu-id="21195-124">Im folgenden Beispiel wird eine `BULK INSERT`-Anweisung verwendet, um mithilfe der Nicht-XML-Formatdatei `myTestOrder-c.txt` einen Massenimport der Daten aus der Datendatei `myTestOrder` in die `myTestOrder.fmt`-Beispieltabelle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="21195-124">The following example uses a `BULK INSERT` statement to bulk import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.fmt` non-XML format file.</span></span>  
  
 <span data-ttu-id="21195-125">Führen Sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="21195-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestOrder  
FROM 'C:\myTestOrder-c.txt'   
WITH (formatfile='C:\myTestOrder.fmt');  
GO  
  
```  
  
## <a name="using-an-xml-format-file"></a><span data-ttu-id="21195-126">Verwenden einer XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="21195-126">Using an XML Format File</span></span>  
 <span data-ttu-id="21195-127">Die folgende Beispielformatdatei im Nicht-XML-Format, `myTestOrder.xml`, ordnet den Spalten der `myTestOrder-c.txt`-Tabelle die Felder in `myTestOrder` zu. Informationen zum Erstellen der Datendatei und der Tabelle finden Sie weiter oben in diesem Thema unter "Beispieltabelle und Datendatei".</span><span class="sxs-lookup"><span data-stu-id="21195-127">The following sample non-XML format file presents a format file, `myTestOrder.xml`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="21195-128">Die Formatdatei `myTestOrder.xml` enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="21195-128">The `myTestOrder.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="3" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="1" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="21195-129">Informationen über die Syntax eines XML-Schemas und weitere Beispiele von XML-Formatdateien finden Sie unter [XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="21195-129">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="21195-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21195-130">Example</span></span>  
 <span data-ttu-id="21195-131">Im folgenden Beispiel wird der BULK-Rowsetanbieter `OPENROWSET` verwendet, um mithilfe der XML-Formatdatei `myTestOrder-c.txt` einen Datenimport aus der Datendatei `myTestOrder` in die `myTestOrder.xml` -Beispieltabelle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="21195-131">The following example uses the `OPENROWSET` bulk rowset provider to import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.xml` XML format file.</span></span> <span data-ttu-id="21195-132">Die `INSERT... SELECT` -Anweisung gibt die Spaltenliste in der Auswahlliste an.</span><span class="sxs-lookup"><span data-stu-id="21195-132">The `INSERT... SELECT` statement specifies the column list in the select list.</span></span>  
  
 <span data-ttu-id="21195-133">Führen Sie im Abfrage-Editor von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="21195-133">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestOrder   
  SELECT Col1, Col2, Col3, Col4  
      FROM  OPENROWSET(BULK  'C:\myTestOrder-c.txt',  
      FORMATFILE='C:\myTestOrder.Xml'    
       ) AS t1;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="21195-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21195-134">See Also</span></span>  
 <span data-ttu-id="21195-135">[Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="21195-135">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="21195-136">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="21195-136">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
  
