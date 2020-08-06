---
title: Verwenden des nativen Formats zum Importieren oder Exportieren von Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724717"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="23ab8-102">Verwenden des systemeigenen Formats zum Importieren oder Exportieren von Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="23ab8-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="23ab8-103">Das systemeigene Format wird für die Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei empfohlen, die keinen erweiterten oder Doppelbyte-Zeichensatz (Double-Byte Character Set, DBCS) enthält.</span><span class="sxs-lookup"><span data-stu-id="23ab8-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23ab8-104">Für die Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die erweiterte Zeichen oder DBCS-Zeichen enthält, sollten Sie das systemeigene Unicode-Format verwenden.</span><span class="sxs-lookup"><span data-stu-id="23ab8-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="23ab8-105">Weitere Informationen finden Sie unter [Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="23ab8-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="23ab8-106">Das systemeigene Format erhält die systemeigenen Datentypen einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="23ab8-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="23ab8-107">Das systemeigene Format ist für die Hochgeschwindigkeitsübertragung von Daten zwischen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabellen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="23ab8-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="23ab8-108">Wenn Sie eine Formatdatei verwenden, müssen Quell- und Zieltabelle nicht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="23ab8-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="23ab8-109">Die Datenübertragung besteht aus zwei Schritten:</span><span class="sxs-lookup"><span data-stu-id="23ab8-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="23ab8-110">Massenexportieren der Daten aus einer Quelltabelle in eine Datendatei</span><span class="sxs-lookup"><span data-stu-id="23ab8-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="23ab8-111">Massenimportieren der Daten aus der Datendatei in die Zieltabelle</span><span class="sxs-lookup"><span data-stu-id="23ab8-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="23ab8-112">Durch die Verwendung des systemeigenen Formats zwischen identischen Tabellen wird die unnötige Konvertierung von Datentypen in das und aus dem Zeichenformat vermieden und somit Zeit und Speicherplatz gespart.</span><span class="sxs-lookup"><span data-stu-id="23ab8-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="23ab8-113">Um eine optimale Übertragungsrate zu erreichen, werden jedoch wenige Überprüfungen der Datenformatierung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="23ab8-114">Berücksichtigen Sie, um Probleme mit den geladenen Daten zu verhindern, die folgende Einschränkungsliste.</span><span class="sxs-lookup"><span data-stu-id="23ab8-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="23ab8-115">Beschränkungen</span><span class="sxs-lookup"><span data-stu-id="23ab8-115">Restrictions</span></span>  
 <span data-ttu-id="23ab8-116">Um Daten im systemeigenen Format erfolgreich zu importieren, müssen folgende Punkte sichergestellt sein:</span><span class="sxs-lookup"><span data-stu-id="23ab8-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="23ab8-117">Die Datendatei liegt im systemeigenen Format vor.</span><span class="sxs-lookup"><span data-stu-id="23ab8-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="23ab8-118">Die Zieltabelle muss mit der Datendatei kompatibel sein (Spaltenanzahl, Datentyp, Länge, NULL-Status usw. müssen richtig sein), oder Sie müssen eine Formatdatei verwenden, um jedes Feld den entsprechenden Spalten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23ab8-119">Wenn Sie Daten aus einer Datei importieren, die nicht mit der Zieltabelle übereinstimmt, kann der Importvorgang zwar erfolgreich sein, aber die in die Zieltabelle eingefügten Datenwerte sind wahrscheinlich falsch.</span><span class="sxs-lookup"><span data-stu-id="23ab8-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="23ab8-120">Das liegt daran, dass die Daten aus der Datei mithilfe des Formats der Zieltabelle interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="23ab8-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="23ab8-121">Daher hat jede fehlende Übereinstimmung die Einfügung falscher Werte zur Folge.</span><span class="sxs-lookup"><span data-stu-id="23ab8-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="23ab8-122">Eine derartige fehlende Übereinstimmung kann jedoch unter keinen Umständen logische oder physische Inkonsistenzen in der Datenbank verursachen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="23ab8-123">Weitere Informationen zur Verwendung von Formatdateien finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="23ab8-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="23ab8-124">Ein erfolgreicher Import beschädigt die Zieltabelle nicht.</span><span class="sxs-lookup"><span data-stu-id="23ab8-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="23ab8-125">Behandlung von Daten im systemeigenen Format durch bcp</span><span class="sxs-lookup"><span data-stu-id="23ab8-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="23ab8-126">Dieser Abschnitt enthält spezielle Überlegungen zum Exportieren und Importieren von Daten im systemeigenen Format durch das Hilfsprogramm **bcp** .</span><span class="sxs-lookup"><span data-stu-id="23ab8-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="23ab8-127">Nicht auf Zeichen basierende Daten</span><span class="sxs-lookup"><span data-stu-id="23ab8-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="23ab8-128">Das Hilfsprogramm bcp verwendet das interne binäre Datenformat von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , um nicht auf Zeichen basierende Daten aus einer Tabelle in eine Datendatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="23ab8-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="23ab8-129">Daten vom Typ `char` oder `varchar`</span><span class="sxs-lookup"><span data-stu-id="23ab8-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="23ab8-130">Am Anfang der einzelnen- `char` oder- `varchar` Felder fügt **bcp** die Präfix Länge hinzu.</span><span class="sxs-lookup"><span data-stu-id="23ab8-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="23ab8-131">Wenn der einheitliche Modus verwendet wird, konvertiert das Hilfsprogramm **bcp** standardmäßig Zeichen aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in OEM-Zeichen, bevor Sie in eine Datendatei kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="23ab8-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="23ab8-132">Das Hilfsprogramm **bcp** konvertiert Zeichen aus einer Datendatei in ANSI-Zeichen, bevor Sie in eine Tabelle Massen importiert werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23ab8-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="23ab8-133">Während dieser Konvertierungen kann es zum Verlust von Daten mit erweiterten Zeichen kommen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="23ab8-134">Verwenden Sie für erweiterte Zeichen entweder das systemeigene Unicode-Format, oder geben Sie eine Codepage an.</span><span class="sxs-lookup"><span data-stu-id="23ab8-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="23ab8-135">Daten vom Typ `sql_variant`</span><span class="sxs-lookup"><span data-stu-id="23ab8-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="23ab8-136">Wenn `sql_variant`-Daten als SQLVARIANT in einer Datendatei im systemeigenen Format gespeichert werden, behalten die Daten alle Merkmale.</span><span class="sxs-lookup"><span data-stu-id="23ab8-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="23ab8-137">Die Metadaten, die den Datentyp jedes Datenwerts aufzeichnen, werden zusammen mit dem Datenwert gespeichert.</span><span class="sxs-lookup"><span data-stu-id="23ab8-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="23ab8-138">Diese Metadaten werden verwendet, um den Datenwert mit demselben Datentyp in einer `sql_variant`-Zielspalte neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="23ab8-139">Wenn der Datentyp der Zielspalte nicht `sql_variant` ist, werden alle Datenwerte unter Einhaltung der üblichen Regeln der impliziten Datenkonvertierung in den Datentyp der Zielspalte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="23ab8-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="23ab8-140">Wenn während der Datenkonvertierung ein Fehler auftritt, wird für den aktuellen Batch ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23ab8-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="23ab8-141">Bei Werten vom Typ `char` und `varchar`, die zwischen `sql_variant`-Spalten übertragen werden, treten möglicherweise Probleme bei der Codepagekonvertierung auf.</span><span class="sxs-lookup"><span data-stu-id="23ab8-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="23ab8-142">Weitere Informationen zur Datenkonvertierung finden Sie unter [Datentypkonvertierung &#40;Datenbank-Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="23ab8-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="23ab8-143">Befehlsoptionen für das systemeigene Format</span><span class="sxs-lookup"><span data-stu-id="23ab8-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="23ab8-144">Sie können Daten im nativen Format in eine Tabelle importieren, indem Sie **bcp**, BULK INSERT oder INSERT... Select \* FROM OPENROWSET (BULK...). Bei einem **bcp** -Befehl oder einer BULK INSERT-Anweisung können Sie das Datenformat in der Befehlszeile angeben.</span><span class="sxs-lookup"><span data-stu-id="23ab8-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="23ab8-145">Für eine INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung müssen Sie das Datenformat in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="23ab8-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="23ab8-146">Das systemeigene Format wird durch die folgenden Befehlszeilenoptionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="23ab8-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="23ab8-147">Get-Help</span><span class="sxs-lookup"><span data-stu-id="23ab8-147">Command</span></span>|<span data-ttu-id="23ab8-148">Option</span><span class="sxs-lookup"><span data-stu-id="23ab8-148">Option</span></span>|<span data-ttu-id="23ab8-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23ab8-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="23ab8-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="23ab8-150">**bcp**</span></span>|<span data-ttu-id="23ab8-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="23ab8-151">**-n**</span></span>|<span data-ttu-id="23ab8-152">Bewirkt, dass das Hilfsprogramm **bcp** die nativen Datentypen der Daten verwendet. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="23ab8-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="23ab8-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="23ab8-153">BULK INSERT</span></span>|<span data-ttu-id="23ab8-154">DataFileType **= '** Native **'**</span><span class="sxs-lookup"><span data-stu-id="23ab8-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="23ab8-155">Verwendet die systemeigenen Datentypen (native oder widenative) der Daten.</span><span class="sxs-lookup"><span data-stu-id="23ab8-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="23ab8-156">Beachten Sie, dass DATAFILETYPE nicht erforderlich ist, wenn eine Formatdatei die Datentypen angibt.</span><span class="sxs-lookup"><span data-stu-id="23ab8-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="23ab8-157"><sup>1</sup> um systemeigene Daten (**-n**) in ein Format zu laden, das mit früheren Versionen von- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Clients kompatibel ist, verwenden Sie den Schalter **-V** .</span><span class="sxs-lookup"><span data-stu-id="23ab8-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="23ab8-158">Weitere Informationen finden Sie unter [Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="23ab8-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="23ab8-159">Weitere Informationen finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) oder [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="23ab8-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23ab8-160">Alternativ können Sie die Formatierung pro Feld in einer Formatdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="23ab8-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="23ab8-161">Weitere Informationen finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23ab8-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="23ab8-162">Beispiele</span><span class="sxs-lookup"><span data-stu-id="23ab8-162">Examples</span></span>  
 <span data-ttu-id="23ab8-163">Die folgenden Beispiele zeigen, wie ein Massenexport nativer Daten mithilfe von **bcp** und wie ein Massenimport derselben Daten mithilfe von BULK INSERT ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="23ab8-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="23ab8-164">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="23ab8-164">Sample Table</span></span>  
 <span data-ttu-id="23ab8-165">Die Beispiele erfordern, dass eine Tabelle mit dem Namen **myTestNativeData** in der **AdventureWorks** -Beispieldatenbank unter dem Schema **dbo** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="23ab8-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="23ab8-166">Vor dem Ausführen dieser Beispiele müssen Sie diese Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="23ab8-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="23ab8-167">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="23ab8-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="23ab8-168">Führen Sie zum Auffüllen dieser Tabelle und zum Anzeigen der resultierenden Inhalte die folgenden Anweisungen aus:</span><span class="sxs-lookup"><span data-stu-id="23ab8-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="23ab8-169">Verwenden von bcp für den Massenexport systemeigener Daten</span><span class="sxs-lookup"><span data-stu-id="23ab8-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="23ab8-170">Verwenden Sie zum Exportieren von Daten aus der Tabelle in die Datendatei **bcp** mit der Option **out** und den folgenden Qualifizierern:</span><span class="sxs-lookup"><span data-stu-id="23ab8-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="23ab8-171">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="23ab8-171">Qualifiers</span></span>|<span data-ttu-id="23ab8-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23ab8-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="23ab8-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="23ab8-173">**-n**</span></span>|<span data-ttu-id="23ab8-174">Gibt systemeigene Datentypen an.</span><span class="sxs-lookup"><span data-stu-id="23ab8-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="23ab8-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="23ab8-175">**-T**</span></span>|<span data-ttu-id="23ab8-176">Gibt an, dass das Hilfsprogramm **bcp** die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe integrierter Sicherheit über eine vertrauenswürdige Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="23ab8-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="23ab8-177">Wenn **-T** nicht angegeben wird, müssen Sie **-U** und **-P** angeben, um sich erfolgreich anzumelden.</span><span class="sxs-lookup"><span data-stu-id="23ab8-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="23ab8-178">Das folgende Beispiel führt einen Massenexport von Daten im systemeigenen Format aus der `myTestNativeData`-Tabelle in eine neue Datendatei namens `myTestNativeData-n.Dat` aus.</span><span class="sxs-lookup"><span data-stu-id="23ab8-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="23ab8-179">Geben Sie an der Eingabeaufforderung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="23ab8-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="23ab8-180">Verwenden von BULK INSERT für den Massenimport systemeigener Daten</span><span class="sxs-lookup"><span data-stu-id="23ab8-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="23ab8-181">Im folgenden Beispiel wird BULK INSERT verwendet, um die Daten in der Datendatei `myTestNativeData-n.Dat` in die `myTestNativeData` -Tabelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="23ab8-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="23ab8-182">Führen Sie im [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="23ab8-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="23ab8-183">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="23ab8-183">Related Tasks</span></span>  
 <span data-ttu-id="23ab8-184">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="23ab8-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="23ab8-185">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="23ab8-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="23ab8-186">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="23ab8-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="23ab8-187">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="23ab8-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="23ab8-188">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="23ab8-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="23ab8-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23ab8-189">See Also</span></span>  
 <span data-ttu-id="23ab8-190">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="23ab8-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="23ab8-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23ab8-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="23ab8-192">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23ab8-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="23ab8-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23ab8-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="23ab8-194">[Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="23ab8-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="23ab8-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23ab8-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="23ab8-196">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="23ab8-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
