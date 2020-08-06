---
title: Überspringen einer Tabellenspalte mithilfe einer Formatdatei (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630647"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="7cbfa-102">Überspringen einer Tabellenspalte mithilfe einer Formatdatei (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7cbfa-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="7cbfa-103">In diesem Thema werden Formatdateien beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-103">This topic describes format files.</span></span> <span data-ttu-id="7cbfa-104">Mit einer Formatdatei können Sie das Importieren einer Tabellenspalte überspringen, wenn das zugehörige Feld in der Datendatei nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="7cbfa-105">Eine Datendatei kann nur dann weniger Felder enthalten, als Spalten in der Tabelle vorliegen, wenn die ausgelassenen Spalten NULL-Werte unterstützen und/oder einen Standardwert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="7cbfa-106">Beispieltabelle und Datendatei</span><span class="sxs-lookup"><span data-stu-id="7cbfa-106">Sample Table and Data File</span></span>
 <span data-ttu-id="7cbfa-107">Für die folgenden Beispiele muss in der `myTestSkipCol` -Beispieldatenbank unter dem [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] dbo **-Schema eine Tabelle mit der Bezeichnung** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="7cbfa-108">Erstellen Sie diese Tabelle folgendermaßen</span><span class="sxs-lookup"><span data-stu-id="7cbfa-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="7cbfa-109">In den folgenden Beispielen wird die Beispieldatendatei `myTestSkipCol2.dat`verwendet, in der nur zwei Felder enthalten sind, obwohl die zugehörige Tabelle drei Spalten enthält:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="7cbfa-110">Damit ein Massenimport von Daten aus `myTestSkipCol2.dat` in die `myTestSkipCol` -Tabelle ausgeführt werden kann, muss `Col1` das erste Datenfeld und `Col3` das zweite Feld der Formatdatei zugeordnet werden, während `Col2` übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="7cbfa-111">Verwenden einer Nicht-XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="7cbfa-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="7cbfa-112">Sie können eine Nicht-XML-Formatdatei ändern, um eine Tabellenspalte auszulassen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="7cbfa-113">Im Allgemeinen ist das **bcp** -Hilfsprogramm erforderlich, um eine standardmäßige Nicht-XML-Formatdatei zu erstellen und die Standarddatei in einem Text-Editor zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="7cbfa-114">Die vorhandenen Datenfelder müssen von der geänderten Formatdatei den entsprechenden Tabellenspalten zugeordnet werden, und es muss angegeben werden, welche Tabellenspalten ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="7cbfa-115">Für die Bearbeitung einer standardmäßigen Nicht-XML-Datendatei stehen zwei Alternativen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="7cbfa-116">Beide Alternativen zeigen, dass das Datenfeld in der Datendatei nicht vorhanden ist und dass keine Daten in die entsprechende Tabellenspalte eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="7cbfa-117">Erstellen einer standardmäßigen Nicht-XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="7cbfa-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="7cbfa-118">In diesem Thema wird die standardmäßige Nicht-XML-Formatdatei verwendet, die mithilfe des folgenden `myTestSkipCol` bcp **-Befehls für die** -Beispieltabelle erstellt wurde:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="7cbfa-119">Mit dem zuvor angeführten Befehl wird die Nicht-XML-Formatdatei `myTestSkipCol_Default.fmt`erstellt:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="7cbfa-120">Diese Formatdatei wird auch als *Standardformatdatei* bezeichnet. Es handelt sich hierbei um die Form, in der Dateien von **bcp**generiert werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="7cbfa-121">Im Allgemeinen wird mit einer Standardformatdatei eine 1:1-Entsprechung zwischen den Feldern in der Datendatei und den Spalten in der Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="7cbfa-122">Möglicherweise müssen Sie den Namen der Serverinstanz angeben, mit der Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="7cbfa-123">Außerdem kann es erforderlich sein, den Benutzernamen und das entsprechende Kennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="7cbfa-124">Weitere Informationen finden Sie unter [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="7cbfa-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="7cbfa-125">In der folgenden Abbildung werden Werte in diesen Beispiel-Standardformatdateien gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="7cbfa-126">In der Abbildung werden außerdem die Namen der einzelnen Formatdateifelder angegeben.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="7cbfa-127">![Standardmäßige Nicht-XML-Formatdatei für „myTextSkipCol“](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "Standardmäßige Nicht-XML-Formatdatei für „myTextSkipCol“")</span><span class="sxs-lookup"><span data-stu-id="7cbfa-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="7cbfa-128">Weitere Informationen zu Formatdateifeldern finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7cbfa-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="7cbfa-129">Methoden zum Ändern von Nicht-XML-Formatdateien</span><span class="sxs-lookup"><span data-stu-id="7cbfa-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="7cbfa-130">Sie können eine Tabellenspalte auslassen, indem Sie eine standardmäßige Nicht-XML-Formatdatei bearbeiten und die Datei mithilfe einer der folgenden alternativen Methoden ändern:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="7cbfa-131">Die bevorzugte Methode umfasst drei grundlegende Schritte.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="7cbfa-132">Löschen Sie zuerst alle Formatdateizeilen, in denen Felder beschrieben werden, die in der Datendatei fehlen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="7cbfa-133">Ändern Sie anschließend den Wert "Reihenfolge der Felder der Hostdatei" für die einzelnen Formatdateizeilen, die auf eine gelöschte Zeile folgen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="7cbfa-134">Das Ziel besteht darin, mithilfe der „Host file field order“-Werte (Reihenfolge der Felder der Hostdatei) von 1 bis *n*die eigentliche Position der einzelnen Datenfelder in der Datendatei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="7cbfa-135">Abschließend muss der Wert im Feld "Spaltenanzahl" entsprechend der tatsächlichen Anzahl der Felder in der Datendatei verringert werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="7cbfa-136">Das folgende Beispiel basiert auf der Standardformatdatei für die `myTestSkipCol` -Tabelle, die unter "Erstellen einer standardmäßigen Nicht-XML-Formatdatei" weiter oben in diesem Thema erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="7cbfa-137">In dieser geänderten Formatdatei wird `Col1`das erste Datenfeld zugeordnet, `Col2`wird ausgelassen, und das zweite Datenfeld wird `Col3`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="7cbfa-138">Die Zeile für `Col2` wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="7cbfa-139">Die anderen Änderungen sind fett dargestellt:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="7cbfa-140">Alternativ können Sie eine Tabellenspalte auslassen, indem Sie die Definition der Formatdateizeile ändern, die der Tabellenspalte entspricht.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="7cbfa-141">In dieser Formatdateizeile müssen die Werte "prefix length", "host file data length" und "server column order" auf 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="7cbfa-142">Außerdem müssen die Felder "terminator" und "column collation" auf "" (NULL) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="7cbfa-143">Für "server column name" muss eine Zeichenfolge eingegeben werden, die nicht leer ist; dabei muss es sich jedoch auch nicht um den tatsächlichen Spaltennamen handeln.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="7cbfa-144">Für die verbleibenden Formatfelder sind die entsprechenden Standardwerte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="7cbfa-145">Das folgende Beispiel wird ebenfalls von der Standardformatdatei der `myTestSkipCol` -Tabelle abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="7cbfa-146">Die Werte, die 0 oder NULL sein müssen, werden fett dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="7cbfa-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7cbfa-147">Examples</span></span>
 <span data-ttu-id="7cbfa-148">Die folgenden Beispiele beruhen ebenfalls auf der `myTestSkipCol` -Beispieltabelle und der `myTestSkipCol2.dat` -Beispieldatendatei, die unter "Beispieltabelle und -datendatei" weiter oben in diesem Thema erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="7cbfa-149">Verwenden von BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="7cbfa-149">Using BULK INSERT</span></span>
 <span data-ttu-id="7cbfa-150">Für dieses Beispiel wird eine der geänderten Nicht-XML-Formatdateien verwendet, die weiter oben in diesem Thema unter "Methoden zum Ändern von Nicht-XML-Formatdateien" erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="7cbfa-151">In diesem Beispiel lautet der Name der geänderten Formatdatei `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="7cbfa-152">Führen Sie im Abfrage-Editor von `BULK INSERT` den folgenden Code aus, um mithilfe von `myTestSkipCol2.dat` einen Massenimport der [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Datendatei auszuführen:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="7cbfa-153">Verwenden einer XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="7cbfa-153">Using an XML Format File</span></span>
 <span data-ttu-id="7cbfa-154">Bei einer XML-Formatdatei ist es nicht möglich, beim direkten Importieren in eine Tabelle mit dem Befehl **bcp** oder der BULK INSERT-Anweisung eine Spalte auszulassen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="7cbfa-155">Sie können jedoch Daten in alle Spalten einer Tabelle mit Ausnahme der letzten Spalte importieren.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="7cbfa-156">Wenn Sie eine andere Spalte als die letzte auslassen müssen, müssen Sie eine Sicht der Zieltabelle erstellen, die nur die in der Datendatei enthaltenen Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="7cbfa-157">Anschließend können Sie Daten aus dieser Datei in die Sicht massenimportieren.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="7cbfa-158">Um eine Tabellenspalte mithilfe von OPENROWSET(BULK...) mit einer XML-Formatdatei auszulassen, muss folgendermaßen eine explizite Liste von Spalten in der Auswahlliste und auch in der Zieltabelle angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="7cbfa-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="7cbfa-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="7cbfa-160">Erstellen einer standardmäßigen XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="7cbfa-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="7cbfa-161">Die Beispiele der geänderten Formatdateien beruhen auf der `myTestSkipCol` -Beispieltabelle und der Datendatei, die unter "Beispieltabelle und -datendatei" weiter oben in diesem Thema erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="7cbfa-162">Mit dem folgenden **bcp** -Befehl wird eine standardmäßige XML-Formatdatei für die `myTestSkipCol` -Tabelle erstellt:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="7cbfa-163">In der erstellten standardmäßigen Nicht-XML-Formatdatei wird eine 1:1-Entsprechung zwischen den Feldern in der Datendatei und den Spalten in der Tabelle beschrieben. Dies erfolgt folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="7cbfa-164">Informationen zur Struktur von XML-Formatdateien finden Sie unter [XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7cbfa-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="7cbfa-165">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7cbfa-165">Examples</span></span>
 <span data-ttu-id="7cbfa-166">Für die Beispiele in diesem Abschnitt werden die `myTestSkipCol` -Beispieltabelle und die `myTestSkipCol2.dat` -Beispieldatendatei verwendet, die unter "Beispieltabelle und -datendatei" weiter oben in diesem Thema erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="7cbfa-167">Zum Importieren der Daten aus `myTestSkipCol2.dat` in die `myTestSkipCol` -Tabelle wird in den Beispielen die folgende geänderte XML-Formatdatei verwendet: `myTestSkipCol2-x.xml`.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="7cbfa-168">Diese Datei basiert auf der Formatdatei, die unter "Erstellen einer standardmäßigen XML-Formatdatei" weiter oben in diesem Thema erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="7cbfa-169">Verwenden von OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="7cbfa-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="7cbfa-170">Im folgenden Beispiel werden der Massenrowsetanbieter `OPENROWSET` und die Formatdatei `myTestSkipCol2.xml` verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="7cbfa-171">Die Datendatei `myTestSkipCol2.dat` wird per Massenimport in die `myTestSkipCol` -Tabelle übertragen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="7cbfa-172">Die Anweisung enthält anforderungsgemäß eine explizite Liste der Spalten in der Auswahlliste und in der Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="7cbfa-173">Führen Sie im Abfrage-Editor von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="7cbfa-174">Verwenden von BULK IMPORT für eine Sicht</span><span class="sxs-lookup"><span data-stu-id="7cbfa-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="7cbfa-175">Im folgenden Beispiel wird für die `v_myTestSkipCol` -Tabelle die Sicht `myTestSkipCol` erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="7cbfa-176">In dieser Sicht wird die zweite Tabellenspalte, `Col2`, ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="7cbfa-177">Anschließend wird mit `BULK INSERT` die Datendatei `myTestSkipCol2.dat` in die Sicht importiert.</span><span class="sxs-lookup"><span data-stu-id="7cbfa-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="7cbfa-178">Führen Sie im Abfrage-Editor von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] folgenden Code aus:</span><span class="sxs-lookup"><span data-stu-id="7cbfa-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="7cbfa-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7cbfa-179">See Also</span></span>
 <span data-ttu-id="7cbfa-180">[bcp-Hilfsprogramm](../../tools/bcp-utility.md) [Bulk Insert &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL-&#41;](/sql/t-sql/functions/openrowset-transact-sql) [verwenden Sie eine Format Datei zum Überspringen eines Daten Felds &#40;](use-a-format-file-to-skip-a-data-field-sql-server.md) SQL Server&#41;[verwenden Sie eine Format Datei zum Zuordnen von Tabellen Spalten zu Datendatei Feldern &#40;SQL Server](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)&#41;[eine Format Datei für den Massen Import von Daten &#40;SQL Server verwenden](use-a-format-file-to-bulk-import-data-sql-server.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="7cbfa-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


