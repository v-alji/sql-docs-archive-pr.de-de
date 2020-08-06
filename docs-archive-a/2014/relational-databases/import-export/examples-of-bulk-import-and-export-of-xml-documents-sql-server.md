---
title: Beispiele für den Massenimport und -export von XML-Dokumenten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- field terminators [SQL Server]
- bulk importing [SQL Server], data formats
- row terminators [SQL Server]
- OPENROWSET function, XML bulk load
- terminators [SQL Server]
- bulk exporting [SQL Server], data formats
- XML bulk load [SQL Server]
ms.assetid: dff99404-a002-48ee-910e-f37f013d946d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d72c84a7ed84503e0c88d2a46c808196903900b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620390"
---
# <a name="examples-of-bulk-import-and-export-of-xml-documents-sql-server"></a><span data-ttu-id="2ff47-102">Beispiele für den Massenimport und -export von XML-Dokumenten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2ff47-102">Examples of Bulk Import and Export of XML Documents (SQL Server)</span></span>
    
##  <a name="you-can-bulk-import-xml-documents-into-a-ssnoversion-database-or-bulk-export-them-from-a-ssnoversion-database-this-topic-provides-examples-of-both"></a><a name="top"></a><span data-ttu-id="2ff47-103">Sie können XML-Dokumente per Massen Import in eine- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank importieren oder aus einer- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ff47-103">You can bulk import XML documents into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or bulk export them from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="2ff47-104">Dieses Thema bietet Beispiele für diese beiden Situationen.</span><span class="sxs-lookup"><span data-stu-id="2ff47-104">This topic provides examples of both.</span></span>  
  
 <span data-ttu-id="2ff47-105">Verwenden Sie für den Massenimport von Daten aus einer Datendatei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle oder eine nicht partitionierte Sicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2ff47-105">To bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or non-partitioned view, you can use the following:</span></span>  
  
-   <span data-ttu-id="2ff47-106">**bcp** (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="2ff47-106">**bcp** utility</span></span>  
  
     <span data-ttu-id="2ff47-107">Sie können das **bcp** -Hilfsprogramm auch verwenden, um Daten von einem beliebigen Speicherort in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank zu exportieren, wo eine SELECT-Anweisung verwendet werden kann, einschließlich partitionierter Sichten.</span><span class="sxs-lookup"><span data-stu-id="2ff47-107">You can also use the **bcp** utility to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that a SELECT statement works, including partitioned views.</span></span>  
  
-   <span data-ttu-id="2ff47-108">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="2ff47-108">BULK INSERT</span></span>  
  
-   <span data-ttu-id="2ff47-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="2ff47-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="2ff47-110">Weitere Informationen finden Sie unter [importieren und Exportieren von Massendaten mithilfe des Hilfsprogramms bcp &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) und [Importieren von Massendaten mithilfe von BULK INSERT oder OPENROWSET&#40;&#41; &#40;Bulk... SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ff47-110">For more information, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) and [Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2ff47-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2ff47-111">Examples</span></span>  
 <span data-ttu-id="2ff47-112">Es werden folgende Beispiele aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="2ff47-112">The examples are the following:</span></span>  
  
-   <span data-ttu-id="2ff47-113">A.</span><span class="sxs-lookup"><span data-stu-id="2ff47-113">A.</span></span> [<span data-ttu-id="2ff47-114">Massen Import von XML-Daten als binärer Byte Datenstrom</span><span class="sxs-lookup"><span data-stu-id="2ff47-114">BULK importing XML data as a binary byte stream</span></span>](#binary_byte_stream)  
  
-   <span data-ttu-id="2ff47-115">B.</span><span class="sxs-lookup"><span data-stu-id="2ff47-115">B.</span></span> [<span data-ttu-id="2ff47-116">Massen Import von XML-Daten in eine vorhandene Zeile</span><span class="sxs-lookup"><span data-stu-id="2ff47-116">Bulk importing XML data in an existing row</span></span>](#existing_row)  
  
-   <span data-ttu-id="2ff47-117">C.</span><span class="sxs-lookup"><span data-stu-id="2ff47-117">C.</span></span> [<span data-ttu-id="2ff47-118">Massen Import von XML-Daten aus einer Datei, die eine DTD enthält</span><span class="sxs-lookup"><span data-stu-id="2ff47-118">Bulk importing XML data from a file that contains a DTD</span></span>](#file_contains_dtd)  
  
-   <span data-ttu-id="2ff47-119">D:</span><span class="sxs-lookup"><span data-stu-id="2ff47-119">D.</span></span> [<span data-ttu-id="2ff47-120">Explizites Angeben des Feld Abschluss Zeichens mithilfe einer Format Datei</span><span class="sxs-lookup"><span data-stu-id="2ff47-120">Specifying the field terminator explicitly using a format file</span></span>](#field_terminator_in_format_file)  
  
-   <span data-ttu-id="2ff47-121">E.</span><span class="sxs-lookup"><span data-stu-id="2ff47-121">E.</span></span> [<span data-ttu-id="2ff47-122">Massen Export von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2ff47-122">Bulk exporting XML data</span></span>](#bulk_export_xml_data)  
  
###  <a name="a-bulk-importing-xml-data-as-a-binary-byte-stream"></a><a name="binary_byte_stream"></a> <span data-ttu-id="2ff47-123">A.</span><span class="sxs-lookup"><span data-stu-id="2ff47-123">A.</span></span> <span data-ttu-id="2ff47-124">Massenimport von XML-Daten als binärer Bytedatenstrom</span><span class="sxs-lookup"><span data-stu-id="2ff47-124">Bulk importing XML data as a binary byte stream</span></span>  
 <span data-ttu-id="2ff47-125">Geben Sie beim Massenimportieren von XML-Daten aus einer Datei mit einer Codierungsdeklaration, die Sie anwenden möchten, die Option SINGLE_BLOB in der OPENROWSET(BULK...)-Klausel an.</span><span class="sxs-lookup"><span data-stu-id="2ff47-125">When you bulk import XML data from a file that contains an encoding declaration that you want to apply, specify the SINGLE_BLOB option in the OPENROWSET(BULK...) clause.</span></span> <span data-ttu-id="2ff47-126">Mit der Option SINGLE_BLOB stellen Sie sicher, dass der XML-Parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Daten gemäß dem in der XML-Deklaration angegebenen Codierungsschema importiert.</span><span class="sxs-lookup"><span data-stu-id="2ff47-126">The SINGLE_BLOB option makes sure that the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imports the data according to the encoding scheme specified in the XML declaration.</span></span>  
  
#### <a name="sample-table"></a><span data-ttu-id="2ff47-127">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="2ff47-127">Sample Table</span></span>  
 <span data-ttu-id="2ff47-128">Zum Testen des Beispiels A müssen Sie die folgende Beispieltabelle `T`erstellen:</span><span class="sxs-lookup"><span data-stu-id="2ff47-128">To test example A, you must create sample table `T`.</span></span>  
  
```  
USE tempdb  
CREATE TABLE T (IntCol int, XmlCol xml);  
GO  
```  
  
#### <a name="sample-data-file"></a><span data-ttu-id="2ff47-129">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-129">Sample Data File</span></span>  
 <span data-ttu-id="2ff47-130">Bevor Sie Beispiel A ausführen können, müssen Sie die UTF-8-codierte Datei (`C:\SampleFolder\SampleData3.txt`) erstellen, die die folgende Beispielinstanz enthält, die das `UTF-8` -Codierungsschema angibt.</span><span class="sxs-lookup"><span data-stu-id="2ff47-130">Before you can run example A, you must create a UTF-8 encoded file (`C:\SampleFolder\SampleData3.txt`) that contains the following sample instance that specifies the `UTF-8` encoding scheme.</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<Root>  
          <ProductDescription ProductModelID="5">  
             <Summary>Some Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-a"></a><span data-ttu-id="2ff47-131">Beispiel A</span><span class="sxs-lookup"><span data-stu-id="2ff47-131">Example A</span></span>  
 <span data-ttu-id="2ff47-132">In diesem Beispiel wird die `SINGLE_BLOB` -Option in einer `INSERT ... SELECT * FROM OPENROWSET(BULK...)` -Anweisung verwendet, um die Daten aus einer Datei namens `SampleData3.txt` zu importieren und eine XML-Instanz in eine Beispieltabelle mit einer einzelnen Spalte `T`einzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ff47-132">This example uses the `SINGLE_BLOB` option in an `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement to import data from a file named `SampleData3.txt` and insert an XML instance in the single-column table, sample table `T`.</span></span>  
  
```  
INSERT INTO T(XmlCol)  
SELECT * FROM OPENROWSET(  
   BULK 'c:\SampleFolder\SampleData3.txt',  
   SINGLE_BLOB) AS x;  
```  
  
#### <a name="remarks"></a><span data-ttu-id="2ff47-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2ff47-133">Remarks</span></span>  
 <span data-ttu-id="2ff47-134">Indem Sie SINGLE_BLOB verwenden, können Sie vermeiden, dass die Codierung des XML-Dokuments (wie in der XML-Codierungsdeklaration angegeben) und die Codierung der vom Server implizierten Codepage nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2ff47-134">By using SINGLE_BLOB in this case, you can avoid a mismatch between the encoding of the XML document (as specified by the XML encoding declaration) and the string codepage implied by the server.</span></span>  
  
 <span data-ttu-id="2ff47-135">Wenn beim Verwenden der Datentypen NCLOB oder CLOB Codepage- oder Codierungskonflikte auftreten, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ff47-135">If you use NCLOB or CLOB data types and run into a codepage or encoding conflict, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="2ff47-136">Entfernen Sie die XML-Deklaration, um den Inhalt der XML-Datendatei erfolgreich zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2ff47-136">Remove the XML declaration to successfully import the contents of the XML data file.</span></span>  
  
-   <span data-ttu-id="2ff47-137">Geben Sie eine dem Codierungsschema der XML-Deklaration entsprechende Codepage in der CODEPAGE-Option der Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="2ff47-137">Specify a code page in the CODEPAGE option of the query that matches the encoding scheme that is used in the XML declaration.</span></span>  
  
-   <span data-ttu-id="2ff47-138">Stellen Sie eine Übereinstimmung oder Auflösung zwischen den Einstellungen der Datenbanksortierung und einem Nicht-Unicode-XML-Codierungsschema her.</span><span class="sxs-lookup"><span data-stu-id="2ff47-138">Match, or resolve, the database collation settings with a non-Unicode XML encoding scheme.</span></span>  
  
 [<span data-ttu-id="2ff47-139">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="2ff47-139">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="b-bulk-importing-xml-data-in-an-existing-row"></a><a name="existing_row"></a> <span data-ttu-id="2ff47-140">B.</span><span class="sxs-lookup"><span data-stu-id="2ff47-140">B.</span></span> <span data-ttu-id="2ff47-141">Massenimport von XML-Daten in eine vorhandene Zeile</span><span class="sxs-lookup"><span data-stu-id="2ff47-141">Bulk importing XML data in an existing row</span></span>  
 <span data-ttu-id="2ff47-142">In diesem Beispiel wird der `OPENROWSET` -Massenrowsetanbieter verwendet, um eine XML-Instanz einer vorhandenen Zeile bzw. vorhandenen Zeilen in der Beispieltabelle `T`hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ff47-142">This example uses the `OPENROWSET` bulk rowset provider to add an XML instance to an existing row or rows in sample table `T`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ff47-143">Bevor Sie dieses Beispiel ausführen können, müssen Sie zunächst das Testskript aus Beispiel A abschließen. In Beispiel A wird nämlich die `tempdb.dbo.T` -Tabelle erstellt und der Massenimport von Daten aus `SampleData3.txt`durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="2ff47-143">To run this example, you must first complete the test script provided in example A. That example creates the `tempdb.dbo.T` table and bulk imports data from `SampleData3.txt`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="2ff47-144">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-144">Sample Data File</span></span>  
 <span data-ttu-id="2ff47-145">In Beispiel B wird eine veränderte Version der Beispieldatendatei `SampleData3.txt` aus dem vorhergehenden Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ff47-145">Example B uses a modified version of the `SampleData3.txt` sample data file from the preceding example.</span></span> <span data-ttu-id="2ff47-146">Ändern Sie den Inhalt dieser Datei wie folgt, um dieses Beispiel auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2ff47-146">To run this example, modify the content of this file as follows:</span></span>  
  
```  
<Root>  
          <ProductDescription ProductModelID="10">  
             <Summary>Some New Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-b"></a><span data-ttu-id="2ff47-147">Beispiel B</span><span class="sxs-lookup"><span data-stu-id="2ff47-147">Example B</span></span>  
  
```  
-- Query before update shows initial state of XmlCol values.  
SELECT * FROM T  
UPDATE T  
SET XmlCol =(  
SELECT * FROM OPENROWSET(  
   BULK 'C:\SampleFolder\SampleData3.txt',  
           SINGLE_BLOB  
) AS x  
)  
WHERE IntCol = 1;  
GO  
```  
  
 [<span data-ttu-id="2ff47-148">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="2ff47-148">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="c-bulk-importing-xml-data-from-a-file-that-contains-a-dtd"></a><a name="file_contains_dtd"></a> <span data-ttu-id="2ff47-149">C.</span><span class="sxs-lookup"><span data-stu-id="2ff47-149">C.</span></span> <span data-ttu-id="2ff47-150">Massenimport von XML-Daten aus einer Datei, die eine DTD enthält</span><span class="sxs-lookup"><span data-stu-id="2ff47-150">Bulk importing XML data from a file that contains a DTD</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ff47-151">Es wird nicht empfohlen, die Unterstützung für DTDs (Document Type Definitions) zu aktivieren, es sei denn, dies ist in Ihrer XML-Umgebung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ff47-151">We recommended that you not enable support for Document Type Definitions (DTDs) if it is not required in your XML environment.</span></span> <span data-ttu-id="2ff47-152">Das Aktivieren der DTD-Unterstützung erhöht die Angriffsfläche Ihres Servers, und kann ihn einem Denial-of-Service-Angriff aussetzen.</span><span class="sxs-lookup"><span data-stu-id="2ff47-152">Turning on DTD support increases the attackable surface area of your server, and may expose it to a denial-of-service attack.</span></span> <span data-ttu-id="2ff47-153">Wenn Sie die Unterstützung von DTDs aktivieren müssen, können Sie dieses Sicherheitsrisiko reduzieren, indem Sie ausschließlich vertrauenswürdige XML-Dokumente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2ff47-153">If you must enable DTD support, you can reduce this security risk by processing only trusted XML documents.</span></span>  
  
 <span data-ttu-id="2ff47-154">Wenn versucht wird, einen [bcp](../../tools/bcp-utility.md) -Befehl zum Importieren von XML-Daten aus einer Datei mit DTD zu verwenden, tritt möglicherweise ein Fehler wie der folgende auf:</span><span class="sxs-lookup"><span data-stu-id="2ff47-154">During an attempt to use a [bcp](../../tools/bcp-utility.md) command to import XML data from a file that contains a DTD, an error similar to the following can occur:</span></span>  
  
 <span data-ttu-id="2ff47-155">"SQLState = 42000, NativeError = 6359"</span><span class="sxs-lookup"><span data-stu-id="2ff47-155">"SQLState = 42000, NativeError = 6359"</span></span>  
  
 <span data-ttu-id="2ff47-156">"Error = [Microsoft][SQL Server Native Client][SQL Server]Das Analysieren von XML mit internen Teilmengen-DTDs ist unzulässig.</span><span class="sxs-lookup"><span data-stu-id="2ff47-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]Parsing XML with internal subset DTDs not allowed.</span></span> <span data-ttu-id="2ff47-157">Verwenden Sie CONVERT mit der Formatoption '2', um die begrenzte Unterstützung interner Teilmengen-DTDs zu ermöglichen."</span><span class="sxs-lookup"><span data-stu-id="2ff47-157">Use CONVERT with style option 2 to enable limited internal subset DTD support."</span></span>  
  
 <span data-ttu-id="2ff47-158">"Fehler beim Kopieren von %s mit BCP"</span><span class="sxs-lookup"><span data-stu-id="2ff47-158">"BCP copy %s failed"</span></span>  
  
 <span data-ttu-id="2ff47-159">Um dieses Problem zu umgehen, können Sie die XML-Daten aus einer Datendatei mit DTD importieren, indem Sie die `OPENROWSET(BULK...)` -Funktion verwenden und die `CONVERT` -Option in der `SELECT` -Klausel des Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="2ff47-159">To work around this problem, you can import XML data from a data file that contains a DTD by using the `OPENROWSET(BULK...)` function and then specifying the `CONVERT` option in the `SELECT` clause of the command.</span></span> <span data-ttu-id="2ff47-160">Die Hauptsyntax für diesen Befehl lautet:</span><span class="sxs-lookup"><span data-stu-id="2ff47-160">The basic syntax for the command is:</span></span>  
  
 `INSERT ... SELECT CONVERT(...) FROM OPENROWSET(BULK...)`  
  
#### <a name="sample-data-file"></a><span data-ttu-id="2ff47-161">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-161">Sample Data File</span></span>  
 <span data-ttu-id="2ff47-162">Bevor Sie dieses Beispiel für den Massenimport testen, müssen Sie zunächst die Datei`C:\temp\Dtdfile.xml`erstellen, die die folgende Beispielinstanz enthält:</span><span class="sxs-lookup"><span data-stu-id="2ff47-162">Before you can test this bulk import example, create a file (`C:\temp\Dtdfile.xml`) that contains the following sample instance:</span></span>  
  
```  
<!DOCTYPE DOC [<!ATTLIST elem1 attr1 CDATA "defVal1">]><elem1>January</elem1>  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="2ff47-163">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="2ff47-163">Sample Table</span></span>  
 <span data-ttu-id="2ff47-164">In Beispiel C wird die Beispieltabelle `T1` verwendet, die Sie durch die folgende `CREATE TABLE` -Anweisung erstellen:</span><span class="sxs-lookup"><span data-stu-id="2ff47-164">Example C uses the `T1` sample table that is created by the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE T1(XmlCol xml);  
GO  
```  
  
#### <a name="example-c"></a><span data-ttu-id="2ff47-165">Beispiel C</span><span class="sxs-lookup"><span data-stu-id="2ff47-165">Example C</span></span>  
 <span data-ttu-id="2ff47-166">In diesem Beispiel wird mit `OPENROWSET(BULK...)` die `CONVERT` -Option in der `SELECT` -Klausel angegeben, um die XML-Daten aus `Dtdfile.xml` in die Beispieltabelle `T1`zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2ff47-166">This example uses `OPENROWSET(BULK...)` and specifies the `CONVERT` option in the `SELECT` clause to import the XML data from `Dtdfile.xml` into sample table `T1`.</span></span>  
  
```  
INSERT T1  
  SELECT CONVERT(xml, BulkColumn, 2) FROM   
    OPENROWSET(Bulk 'c:\temp\Dtdfile.xml', SINGLE_BLOB) [rowsetresults];  
```  
  
 <span data-ttu-id="2ff47-167">Nach dem Ausführen der `INSERT` -Anweisung wird die DTD aus der XML-Datei entfernt und in der Tabelle `T1` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2ff47-167">After the `INSERT` statement executes, the DTD is stripped from the XML and stored in the `T1` table.</span></span>  
  
 [<span data-ttu-id="2ff47-168">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="2ff47-168">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="d-specifying-the-field-terminator-explicitly-using-a-format-file"></a><a name="field_terminator_in_format_file"></a> <span data-ttu-id="2ff47-169">D.</span><span class="sxs-lookup"><span data-stu-id="2ff47-169">D.</span></span> <span data-ttu-id="2ff47-170">Explizites Angeben des Feldabschlusszeichens mithilfe einer Formatdatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-170">Specifying the field terminator explicitly using a format file</span></span>  
 <span data-ttu-id="2ff47-171">Im folgenden Beispiel wird gezeigt, wie das XML-Dokument `Xmltable.dat`per Massenimport importiert wird.</span><span class="sxs-lookup"><span data-stu-id="2ff47-171">The following example shows how to bulk import the following XML document, `Xmltable.dat`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="2ff47-172">Beispieldatendatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-172">Sample Data File</span></span>  
 <span data-ttu-id="2ff47-173">Das Dokument in `Xmltable.dat` enthält zwei XML-Werte; einen für jede Zeile.</span><span class="sxs-lookup"><span data-stu-id="2ff47-173">The document in `Xmltable.dat` contains two XML values, one for each row.</span></span> <span data-ttu-id="2ff47-174">Der erste XML-Wert ist UTF-16-codiert, der zweite ist UTF-8-codiert:</span><span class="sxs-lookup"><span data-stu-id="2ff47-174">The first XML value is encoded with UTF-16, and the second value is encoded with UTF-8.</span></span>  
  
 <span data-ttu-id="2ff47-175">Der Inhalt dieser Datendatei wird im folgenden Hexadezimalabbild gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2ff47-175">The contents of this data file are shown in the following Hex dump:</span></span>  
  
```  
FF FE 3C 00 3F 00 78 00-6D 00 6C 00 20 00 76 00  *..<.?.x.m.l. .v.*  
65 00 72 00 73 00 69 00-6F 00 6E 00 3D 00 22 00  *e.r.s.i.o.n.=.".*  
31 00 2E 00 30 00 22 00-20 00 65 00 6E 00 63 00  *1...0.". .e.n.c.*  
6F 00 64 00 69 00 6E 00-67 00 3D 00 22 00 75 00  *o.d.i.n.g.=.".u.*  
74 00 66 00 2D 00 31 00-36 00 22 00 3F 00 3E 00  *t.f.-.1.6.".?.>.*  
3C 00 72 00 6F 00 6F 00-74 00 3E 00 A2 4F 9C 76  *<.r.o.o.t.>..O.v*  
0C FA 77 E4 80 00 89 00-00 06 90 06 91 2E 9B 2E  *..w.............*  
99 34 A2 34 86 00 83 02-92 20 7F 02 4E C5 E4 A3  *.4.4..... ..N...*  
34 B2 B7 B3 B7 FE F8 FF-F8 00 3C 00 2F 00 72 00  *4.........<./.r.*  
6F 00 6F 00 74 00 3E 00-00 00 00 00 7A EF BB BF  *o.o.t.>.....z...*  
3C 3F 78 6D 6C 20 76 65-72 73 69 6F 6E 3D 22 31  *<?xml version="1*  
2E 30 22 20 65 6E 63 6F-64 69 6E 67 3D 22 75 74  *.0" encoding="ut*  
66 2D 38 22 3F 3E 3C 72-6F 6F 74 3E E4 BE A2 E7  *f-8"?><root>....*  
9A 9C EF A8 8C EE 91 B7-C2 80 C2 89 D8 80 DA 90  *................*  
E2 BA 91 E2 BA 9B E3 92-99 E3 92 A2 C2 86 CA 83  *................*  
E2 82 92 C9 BF EC 95 8E-EA 8F A4 EB 88 B4 EB 8E  *................*  
B7 EF BA B7 EF BF B8 C3-B8 3C 2F 72 6F 6F 74 3E  *.........</root>*  
00 00 00 00 7A                                   *....z*  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="2ff47-176">Beispieltabelle</span><span class="sxs-lookup"><span data-stu-id="2ff47-176">Sample Table</span></span>  
 <span data-ttu-id="2ff47-177">Beim Massenimport oder -export eines XML-Dokuments sollten Sie ein [Feldabschlusszeichen](specify-field-and-row-terminators-sql-server.md) verwenden, das keinesfalls in einem der Dokumente auftritt, beispielsweise eine Reihe von vier Nullen (`\0`) gefolgt vom Buchstaben `z`: `\0\0\0\0z`.</span><span class="sxs-lookup"><span data-stu-id="2ff47-177">When you bulk import or export an XML document, you should use a [field terminator](specify-field-and-row-terminators-sql-server.md) that cannot possibly appear in any of the documents; for example, a series of four nulls (`\0`) followed by the letter `z`: `\0\0\0\0z`.</span></span>  
  
 <span data-ttu-id="2ff47-178">In diesem Beispiel wird gezeigt, wie Sie dieses Feldabschlusszeichen in der Beispieltabelle `xTable` verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ff47-178">This example shows how to use this field terminator for the `xTable` sample table.</span></span> <span data-ttu-id="2ff47-179">Verwenden Sie zum Erstellen dieser Beispieltabelle die folgende `CREATE TABLE` -Anweisung:</span><span class="sxs-lookup"><span data-stu-id="2ff47-179">To create this sample table, use the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE xTable (xCol xml);  
GO  
```  
  
#### <a name="sample-format-file"></a><span data-ttu-id="2ff47-180">Beispielformatdatei</span><span class="sxs-lookup"><span data-stu-id="2ff47-180">Sample Format File</span></span>  
 <span data-ttu-id="2ff47-181">Das Feldabschlusszeichen muss in der Formatdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ff47-181">The field terminator must be specified in the format file.</span></span> <span data-ttu-id="2ff47-182">In Beispiel D wird eine Nicht-XML-Formatdatei namens `Xmltable.fmt` verwendet, die Folgendes enthält:</span><span class="sxs-lookup"><span data-stu-id="2ff47-182">Example D uses a non-XML format file named `Xmltable.fmt` that contains the following:</span></span>  
  
```  
9.0  
1  
1       SQLBINARY     0       0       "\0\0\0\0z"    1     xCol         ""  
```  
  
 <span data-ttu-id="2ff47-183">Sie können diese Formatdatei für den Massenimport von XML-Dokumenten in die `xTable` -Tabelle verwenden und dazu entweder einen `bcp` -Befehl oder eine `BULK INSERT` - oder eine `INSERT ... SELECT * FROM OPENROWSET(BULK...)` -Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ff47-183">You can use this format file to bulk import XML documents into the `xTable` table by using a `bcp` command or a `BULK INSERT` or `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="2ff47-184">Beispiel D</span><span class="sxs-lookup"><span data-stu-id="2ff47-184">Example D</span></span>  
 <span data-ttu-id="2ff47-185">In diesem Beispiel wird die `Xmltable.fmt` -Formatdatei in einer `BULK INSERT` -Anweisung verwendet, um den Inhalt einer XML-Datendatei namens `Xmltable.dat`zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2ff47-185">This example uses the `Xmltable.fmt` format file in a `BULK INSERT` statement to import the contents of an XML data file named `Xmltable.dat`.</span></span>  
  
```  
BULK INSERT xTable   
FROM 'C:\Xmltable.dat'  
WITH (FORMATFILE = 'C:\Xmltable.fmt');  
GO  
```  
  
 [<span data-ttu-id="2ff47-186">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="2ff47-186">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="e-bulk-exporting-xml-data"></a><a name="bulk_export_xml_data"></a> <span data-ttu-id="2ff47-187">E.</span><span class="sxs-lookup"><span data-stu-id="2ff47-187">E.</span></span> <span data-ttu-id="2ff47-188">Massenexport von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="2ff47-188">Bulk exporting XML data</span></span>  
 <span data-ttu-id="2ff47-189">Im folgenden Beispiel werden XML-Daten mithilfe von `bcp` per Massenexport aus der im vorherigen Beispiel erstellten Tabelle exportiert. Dabei wird dieselbe XML-Formatdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ff47-189">The following example uses `bcp` to bulk export XML data from the table that is created in the preceding example by using the same XML format file.</span></span> <span data-ttu-id="2ff47-190">Im folgenden `bcp` -Befehl stellen `<server_name>` und `<instance_name>` Platzhalter dar, die durch die entsprechenden Werte ersetzt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="2ff47-190">In the following `bcp` command, `<server_name>` and `<instance_name>` represent placeholders that must be replaced with appropriate values:</span></span>  
  
```  
bcp bulktest..xTable out a-wn.out -N -T -S<server_name>\<instance_name>  
```  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ff47-191">speichert die XML-Codierung nicht, wenn XML-Daten in der Datenbank persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2ff47-191">does not save the XML encoding when XML data is persisted in the database.</span></span> <span data-ttu-id="2ff47-192">Die ursprüngliche Codierung der XML-Felder ist also nicht mehr verfügbar, wenn die XML-Daten exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="2ff47-192">Therefore, the original encoding of XML fields is not available when XML data is exported.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ff47-193">verwendet für den Export von XML-Daten die UTF-16-Codierung.</span><span class="sxs-lookup"><span data-stu-id="2ff47-193">uses UTF-16 encoding when exporting XML data.</span></span>  
  
 [<span data-ttu-id="2ff47-194">&#91;Nach oben&#93;</span><span class="sxs-lookup"><span data-stu-id="2ff47-194">&#91;Top&#93;</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="2ff47-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ff47-195">See Also</span></span>  
 <span data-ttu-id="2ff47-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ff47-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="2ff47-197">[FOR-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ff47-197">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="2ff47-198">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="2ff47-198">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="2ff47-199">[Massenimport und -export von Daten &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2ff47-199">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="2ff47-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2ff47-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="2ff47-201">OPENROWSET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ff47-201">OPENROWSET &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openrowset-transact-sql)  
  
  
