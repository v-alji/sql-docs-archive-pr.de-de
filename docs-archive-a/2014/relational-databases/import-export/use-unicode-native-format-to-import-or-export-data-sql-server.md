---
title: Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724702"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="ff175-102">Verwenden des systemeigenen Unicode-Formats zum Importieren oder Exportieren von Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ff175-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="ff175-103">Das native Unicode-Format ist hilfreich, wenn Informationen von einer Installation von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in eine andere kopiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ff175-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="ff175-104">Durch die Verwendung des systemeigenen Formats bei nicht auf Zeichen basierenden Daten kann Zeit eingespart werden, da die unnötige Konvertierung der Datentypen in und aus dem Zeichenformat entfällt.</span><span class="sxs-lookup"><span data-stu-id="ff175-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="ff175-105">Die Verwendung des Unicode-Zeichenformats für alle Zeichendaten verhindert, dass es zum Verlust von erweiterten Zeichen beim Massenübertragen von Daten zwischen Servern mit unterschiedlichen Codepages kommt.</span><span class="sxs-lookup"><span data-stu-id="ff175-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="ff175-106">Eine Datendatei im systemeigenen Unicode-Format kann von jeder Massenimportmethode gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ff175-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="ff175-107">Das systemeigene Unicode-Format wird für die Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die Sonderzeichen oder DBCS-Zeichen enthält, empfohlen.</span><span class="sxs-lookup"><span data-stu-id="ff175-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="ff175-108">Für nicht auf Zeichen basierende Daten verwendet das systemeigene Unicode-Format systemeigene (Datenbank-)Datentypen.</span><span class="sxs-lookup"><span data-stu-id="ff175-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="ff175-109">Für Zeichendaten, wie z. B. `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)` und `ntext`, verwendet das systemeigene Unicode-Format das Unicode-Zeichendatenformat.</span><span class="sxs-lookup"><span data-stu-id="ff175-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="ff175-110">Die `sql_variant`-Daten, die in einer Datendatei im systemeigenen Unicode-Format als SQLVARIANT gespeichert werden, funktionieren auf die gleiche Weise wie in einer Datendatei im systemeigenen Format, mit der Ausnahme, dass Werte der Typen `char` und `varchar` in `nchar` und `nvarchar` konvertiert werden. Hierdurch verdoppelt sich der für die entsprechenden Spalten benötigte Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="ff175-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="ff175-111">Die ursprünglichen Metadaten bleiben erhalten, und die Werte werden zurück in die ursprünglichen Datentypen `char` und `varchar` konvertiert, wenn sie in eine Tabellenspalte massenimportiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff175-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="ff175-112">Befehlsoptionen für das systemeigene Unicode-Format</span><span class="sxs-lookup"><span data-stu-id="ff175-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="ff175-113">Sie können Daten im nativen Unicode-Format in eine Tabelle importieren, indem Sie **bcp**, BULK INSERT oder INSERT... Select \* FROM OPENROWSET (BULK...). Bei einem **bcp** -Befehl oder einer BULK INSERT-Anweisung können Sie das Datenformat in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="ff175-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="ff175-114">Für eine INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung müssen Sie das Datenformat in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ff175-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="ff175-115">Das systemeigene Unicode-Format wird von den folgenden Optionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ff175-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="ff175-116">Get-Help</span><span class="sxs-lookup"><span data-stu-id="ff175-116">Command</span></span>|<span data-ttu-id="ff175-117">Option</span><span class="sxs-lookup"><span data-stu-id="ff175-117">Option</span></span>|<span data-ttu-id="ff175-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff175-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="ff175-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="ff175-119">**bcp**</span></span>|<span data-ttu-id="ff175-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="ff175-120">**-N**</span></span>|<span data-ttu-id="ff175-121">Bewirkt, dass das Hilfsprogramm **bcp** das Native Unicode-Format verwendet, das Native (Datenbank-) Datentypen für alle nicht-Zeichendaten und das Unicode-Zeichendaten Format für alle Zeichendaten (,,, `char` `nchar` `varchar` `nvarchar` , `text` und `ntext` ) verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff175-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="ff175-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ff175-122">BULK INSERT</span></span>|<span data-ttu-id="ff175-123">DataFileType **= '** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="ff175-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="ff175-124">Gibt an, dass das systemeigene Unicode-Format beim Massenimportieren von Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff175-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="ff175-125">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) oder [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ff175-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ff175-126">Alternativ können Sie die Formatierung pro Feld in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ff175-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="ff175-127">Weitere Informationen finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff175-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ff175-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ff175-128">Examples</span></span>  
 <span data-ttu-id="ff175-129">Die folgenden Beispiele zeigen, wie ein Massenexport nativer Daten mithilfe von **bcp** und wie ein Massenimport derselben Daten mithilfe von BULK INSERT ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff175-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="ff175-130">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="ff175-130">Sample Table</span></span>  
 <span data-ttu-id="ff175-131">Für die Beispiele ist es erforderlich, dass eine Tabelle namens **myTestUniNativeData** in der **AdventureWorks**-Beispieldatenbank unter dem **dbo**-Schema erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ff175-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="ff175-132">Vor dem Ausführen dieser Beispiele müssen Sie diese Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff175-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="ff175-133">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ff175-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="ff175-134">Führen Sie zum Auffüllen dieser Tabelle und zum Anzeigen der resultierenden Inhalte die folgenden Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="ff175-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="ff175-135">Verwenden von bcp für den Massenexport systemeigener Daten</span><span class="sxs-lookup"><span data-stu-id="ff175-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="ff175-136">Verwenden Sie zum Exportieren von Daten aus der Tabelle in die Datendatei **bcp** mit der Option **out** und den folgenden Qualifizierern:</span><span class="sxs-lookup"><span data-stu-id="ff175-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="ff175-137">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="ff175-137">Qualifiers</span></span>|<span data-ttu-id="ff175-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff175-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ff175-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="ff175-139">**-N**</span></span>|<span data-ttu-id="ff175-140">Gibt systemeigene Datentypen an.</span><span class="sxs-lookup"><span data-stu-id="ff175-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="ff175-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="ff175-141">**-T**</span></span>|<span data-ttu-id="ff175-142">Gibt an, dass das Hilfsprogramm **bcp** die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe integrierter Sicherheit über eine vertrauenswürdige Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="ff175-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="ff175-143">Wenn **-T** nicht angegeben wird, müssen Sie **-U** und **-P** angeben, um sich erfolgreich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="ff175-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="ff175-144">Das folgende Beispiel führt einen Massenexport von Daten im systemeigenen Format aus der `myTestUniNativeData`-Tabelle in eine neue Datendatei namens `myTestUniNativeData-N.Dat` aus.</span><span class="sxs-lookup"><span data-stu-id="ff175-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="ff175-145">Geben Sie an der Eingabeaufforderung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff175-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="ff175-146">Verwenden von BULK INSERT für den Massenimport systemeigener Daten</span><span class="sxs-lookup"><span data-stu-id="ff175-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="ff175-147">Im folgenden Beispiel wird BULK INSERT verwendet, um die Daten in der Datendatei `myTestUniNativeData-N.Dat` in die `myTestUniNativeData` -Tabelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ff175-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="ff175-148">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ff175-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ff175-149">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="ff175-149">Related Tasks</span></span>  
 <span data-ttu-id="ff175-150">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="ff175-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="ff175-151">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="ff175-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="ff175-152">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ff175-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ff175-153">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ff175-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="ff175-154">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ff175-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff175-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff175-155">See Also</span></span>  
 <span data-ttu-id="ff175-156">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ff175-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="ff175-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ff175-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ff175-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ff175-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="ff175-159">Datentypen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ff175-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
