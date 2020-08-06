---
title: Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724713"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="d3ae4-102">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d3ae4-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="d3ae4-103">Es wird empfohlen, für die Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die Sonderzeichen oder Zeichen aus dem Doppelbyte-Zeichensatz (Double-Byte Character Set, DBCS) enthält, das Unicode-Zeichenformat zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="d3ae4-104">Mit dem Unicode-Zeichenformat können Daten von einem Server mithilfe einer Codepage exportiert werden, wenn sich diese Codepage von der Codepage unterscheidet, die der Client verwendet, der den Vorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="d3ae4-105">In solchen Fällen bietet die Verwendung des Unicode-Zeichenformats folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="d3ae4-106">Wenn es sich bei den Quell- und Zieldaten um Unicode-Datentypen handelt, bleiben bei Verwendung des Unicode-Zeichenformats alle Zeichendaten erhalten.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="d3ae4-107">Wenn es sich bei den Quell- und Zieldaten nicht um Unicode-Datentypen handelt, wird durch die Verwendung des Unicode-Datenformats der Verlust von Sonderzeichen in Bezug auf die Quelldaten minimiert, die am Ziel nicht dargestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="d3ae4-108">Datendateien im Unicode-Zeichenformat folgen den Konventionen für Unicode-Dateien.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="d3ae4-109">Die ersten zwei Bytes der Datei sind Hexadezimalzahlen (0xFFFE).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="d3ae4-110">Diese Bytes dienen als Markierungen für die Bytereihenfolge, in der angegeben wird, ob in der Datei das höherwertige Byte zuerst oder zuletzt gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3ae4-111">Damit eine Formatdatei mit einer Datendatei mit Unicode-Zeichen verwendet werden kann, müssen alle Eingabefelder Unicode-Textzeichenfolgen sein (d. h., entweder Unicode-Zeichenfolgen einer festen Länge oder Unicode-Zeichenfolgen mit Abschlusszeichen).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="d3ae4-112">Die `sql_variant`-Daten, die in einer Datendatei im Unicode-Zeichenformat gespeichert sind, verhalten sich wie Daten in einer Datendatei im Zeichenformat, außer dass die Daten als `nchar`-Daten und nicht als `char`-Daten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="d3ae4-113">Weitere Informationen zum Zeichenformat finden Sie unter [Sortierung und Unicode-Unterstützung](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="d3ae4-114">Wenn Sie andere Feld- und Zeilenabschlusszeichen als die standardmäßig durch das Unicode-Zeichenformat vorgegebenen verwenden möchten, informieren Sie sich unter [Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="d3ae4-115">Befehlsoptionen für das Unicode-Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="d3ae4-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="d3ae4-116">Sie können Daten im Unicode-Zeichenformat in eine Tabelle importieren, indem Sie **bcp**, BULK INSERT oder INSERT... Select \* FROM OPENROWSET (BULK...). Bei einem **bcp** -Befehl oder einer BULK INSERT-Anweisung können Sie das Datenformat in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="d3ae4-117">Für eine INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung müssen Sie das Datenformat in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="d3ae4-118">Das Unicode-Zeichenformat wird von den folgenden Befehlszeilenoptionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="d3ae4-119">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d3ae4-119">Command</span></span>|<span data-ttu-id="d3ae4-120">Option</span><span class="sxs-lookup"><span data-stu-id="d3ae4-120">Option</span></span>|<span data-ttu-id="d3ae4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3ae4-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="d3ae4-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-122">**bcp**</span></span>|<span data-ttu-id="d3ae4-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-123">**-w**</span></span>|<span data-ttu-id="d3ae4-124">Verwendet das Unicode-Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="d3ae4-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="d3ae4-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="d3ae4-125">BULK INSERT</span></span>|<span data-ttu-id="d3ae4-126">DataFileType **= '** widechar **'**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="d3ae4-127">Verwendet das Unicode-Zeichenformat beim Massenimport von Daten</span><span class="sxs-lookup"><span data-stu-id="d3ae4-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="d3ae4-128">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) oder [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3ae4-129">Alternativ können Sie die Formatierung pro Feld in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="d3ae4-130">Weitere Informationen finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d3ae4-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d3ae4-131">Examples</span></span>  
 <span data-ttu-id="d3ae4-132">Die folgenden Beispiele veranschaulichen den Massenexport von Unicode-Zeichendaten mithilfe von **bcp** und den Massenimport derselben Daten mithilfe von BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="d3ae4-133">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="d3ae4-133">Sample Table</span></span>  
 <span data-ttu-id="d3ae4-134">Für die Beispiele muss in der [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)]-Beispieldatenbank unter dem `myTestUniCharData`-Schema eine Tabelle namens `dbo` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="d3ae4-135">Vor dem Ausführen dieser Beispiele müssen Sie diese Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="d3ae4-136">Führen Sie Folgendes aus, um diese Tabelle im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Abfrage-Editor zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="d3ae4-137">Führen Sie zum Auffüllen dieser Tabelle und zum Anzeigen der resultierenden Inhalte die folgenden Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="d3ae4-138">Verwenden von "bcp" für den Massenexport von Unicode-Zeichendaten</span><span class="sxs-lookup"><span data-stu-id="d3ae4-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="d3ae4-139">Verwenden Sie zum Exportieren von Daten aus der Tabelle in die Datendatei **bcp** mit der Option **out** und den folgenden Qualifizierern:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="d3ae4-140">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="d3ae4-140">Qualifiers</span></span>|<span data-ttu-id="d3ae4-141">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3ae4-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="d3ae4-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-142">**-w**</span></span>|<span data-ttu-id="d3ae4-143">Gibt das Unicode-Zeichenformat an</span><span class="sxs-lookup"><span data-stu-id="d3ae4-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="d3ae4-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="d3ae4-144">**-t** `,`</span></span>|<span data-ttu-id="d3ae4-145">Gibt ein Komma (`,`) als Feldabschlusszeichen an.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="d3ae4-146">Hinweis: das standardmäßige Feld Abschluss Zeichen ist das Tabstopp-Unicode-Zeichen (\t).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="d3ae4-147">Weitere Informationen finden Sie unter [Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d3ae4-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="d3ae4-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-148">**-T**</span></span>|<span data-ttu-id="d3ae4-149">Gibt an, dass das Hilfsprogramm **bcp** die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe integrierter Sicherheit über eine vertrauenswürdige Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="d3ae4-150">Wenn **-T** nicht angegeben wird, müssen Sie **-U** und **-P** angeben, um sich erfolgreich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="d3ae4-151">Im folgenden Beispiel wird ein Massenexport von Daten im Unicode-Zeichenformat aus der `myTestUniCharData`-Tabelle in eine neue Datendatei ausgeführt. Diese Datendatei heißt `myTestUniCharData-w.Dat` und verwendet das Komma (`,`) als Feldabschlusszeichen.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="d3ae4-152">Geben Sie an der Eingabeaufforderung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="d3ae4-153">Verwenden von BULK INSERT für den Massenimport von Unicode-Zeichendaten</span><span class="sxs-lookup"><span data-stu-id="d3ae4-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="d3ae4-154">Im folgenden Beispiel wird `BULK INSERT` zum Importieren der Daten aus der Datendatei `myTestUniCharData-w.Dat` in die `myTestUniCharData`-Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="d3ae4-155">Das nicht standardmäßige Feldabschlusszeichen (`,`) muss in der Anweisung deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d3ae4-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="d3ae4-156">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d3ae4-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d3ae4-157">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="d3ae4-157">Related Tasks</span></span>  
 <span data-ttu-id="d3ae4-158">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="d3ae4-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="d3ae4-159">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="d3ae4-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="d3ae4-160">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ae4-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="d3ae4-161">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ae4-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="d3ae4-162">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ae4-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d3ae4-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3ae4-163">See Also</span></span>  
 <span data-ttu-id="d3ae4-164">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="d3ae4-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="d3ae4-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d3ae4-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="d3ae4-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d3ae4-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="d3ae4-167">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d3ae4-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="d3ae4-168">Collation and Unicode Support</span><span class="sxs-lookup"><span data-stu-id="d3ae4-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
