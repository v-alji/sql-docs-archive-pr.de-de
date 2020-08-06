---
title: Laden von XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717545"
---
# <a name="load-xml-data"></a><span data-ttu-id="17a8d-102">Laden von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="17a8d-102">Load XML Data</span></span>
  <span data-ttu-id="17a8d-103">XML-Daten können auf unterschiedliche Weise in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="17a8d-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="17a8d-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17a8d-104">For example:</span></span>  
  
-   <span data-ttu-id="17a8d-105">Wenn sich die Daten in einer [n]text- oder image-Spalte einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank befinden, können Sie die Tabelle mithilfe von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]importieren.</span><span class="sxs-lookup"><span data-stu-id="17a8d-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="17a8d-106">Ändern Sie den Spaltentyp mithilfe der ALTER TABLE-Anweisung zu XML.</span><span class="sxs-lookup"><span data-stu-id="17a8d-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="17a8d-107">Sie können bcp out zum Massenkopieren Ihrer Daten aus einer anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken verwenden, um sie dann mit bcp in als Masseneinfügung in eine aktuellere Datenbankversion einzufügen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="17a8d-108">Wenn Sie über Daten in relationalen Spalten in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank verfügen, erstellen Sie eine neue Tabelle in einer [n]text-Spalte und optional eine Primärschlüsselspalte für einen Zeilenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="17a8d-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="17a8d-109">Rufen Sie mithilfe clientseitiger Programmierung den XML-Code ab, der mit FOR XML auf dem Server generiert wurde, und schreiben Sie ihn in die `[n]text`-Spalte.</span><span class="sxs-lookup"><span data-stu-id="17a8d-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="17a8d-110">Verwenden Sie dann die oben erwähnten Techniken, um die Daten in eine höhere Version der Datenbank zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="17a8d-111">Sie können den XML-Code auch direkt in eine XML-Spalte in der Datenbank der höheren Version schreiben.</span><span class="sxs-lookup"><span data-stu-id="17a8d-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="17a8d-112">Massenladen von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="17a8d-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="17a8d-113">Sie können XML-Daten mit einem Massenladevorgang auf den Server laden, indem Sie die Massenladefunktionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden, z. B. bcp.</span><span class="sxs-lookup"><span data-stu-id="17a8d-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="17a8d-114">Mit OPENROWSET können Sie Daten aus Dateien in eine XML-Spalte laden.</span><span class="sxs-lookup"><span data-stu-id="17a8d-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="17a8d-115">Das folgende Beispiel veranschaulicht diesen Punkt.</span><span class="sxs-lookup"><span data-stu-id="17a8d-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="17a8d-116">Beispiel: Laden von XML-Daten aus Dateien</span><span class="sxs-lookup"><span data-stu-id="17a8d-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="17a8d-117">Dieses Beispiel zeigt, wie eine Zeile in Tabelle T eingefügt wird. Der Wert der XML-Spalte wird aus der Datei C:\MyFile\xmlfile.xml als CLOB geladen, und die integer-Spalte erhält den Wert 10.</span><span class="sxs-lookup"><span data-stu-id="17a8d-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="17a8d-118">Textcodierung</span><span class="sxs-lookup"><span data-stu-id="17a8d-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="17a8d-119">speichert XML-Daten im Unicode (UTF-16)-Format.</span><span class="sxs-lookup"><span data-stu-id="17a8d-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="17a8d-120">Die vom Server abgerufenen XML-Daten liegen UTF-16-codiert vor.</span><span class="sxs-lookup"><span data-stu-id="17a8d-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="17a8d-121">Wenn Sie eine andere Codierung wünschen, müssen Sie die erforderliche Konvertierung für die abgerufenen Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="17a8d-122">Manchmal können die XML-Daten in einer abweichenden Codierung vorliegen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="17a8d-123">Wenn das der Fall ist, müssen Sie beim Laden der Daten mit großer Sorgfalt vorgehen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="17a8d-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17a8d-124">For example:</span></span>  
  
-   <span data-ttu-id="17a8d-125">Wenn Ihre Text-XML-Daten in Unicode (UCS-2, UTF-16) vorliegen, können Sie sie problemlos einer XML-Spalte, einer XML-Variablen oder einem XML-Parameter zuweisen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="17a8d-126">Wenn die Codierung nicht Unicode ist und aufgrund der Quellcodeseite implizit ist, sollte die Zeichenfolgencodeseite in der Datenbank den Codepunkten gleichen oder mit den Codepunkten kompatibel sein, die Sie laden wollen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="17a8d-127">Verwenden Sie falls erforderlich COLLATE.</span><span class="sxs-lookup"><span data-stu-id="17a8d-127">If required, use COLLATE.</span></span> <span data-ttu-id="17a8d-128">Wenn keine solche Servercodeseite vorhanden ist, müssen Sie eine explizite XML-Deklaration mit der richtigen Codierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="17a8d-129">Verwenden Sie entweder den `varbinary()`-Typ, der keinerlei Interaktion mit Codeseiten aufweist, oder einen Zeichenfolgentyp der entsprechenden Codeseite, damit eine explizite Codierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17a8d-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="17a8d-130">Weisen Sie anschließend die Daten einer XML-Spalte, einer XML-Variablen oder einem XML-Parameter zu.</span><span class="sxs-lookup"><span data-stu-id="17a8d-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="17a8d-131">Beispiel: Explizites Angeben einer Codierung</span><span class="sxs-lookup"><span data-stu-id="17a8d-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="17a8d-132">Angenommen, Sie besitzen das XML-Dokument vcdoc, das im Datentyp `varchar(max)` gespeichert ist und keine explizite XML-Deklaration aufweist.</span><span class="sxs-lookup"><span data-stu-id="17a8d-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="17a8d-133">Mit der folgenden Anweisung wird eine XML-Deklaration mit der Codierung "iso8859-1" hinzugefügt, das XML-Dokument verkettet, das Ergebnis in `varbinary(max)` umgewandelt, sodass die Bytedarstellung erhalten bleibt, und das Ergebnis schließlich in XML umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="17a8d-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="17a8d-134">Das ermöglicht es dem XML-Prozessor, die Daten entsprechend der angegebenen Codierung "iso8859-1" zu analysieren und die entsprechende UTF-16-Darstellung für Zeichenfolgenwerte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="17a8d-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="17a8d-135">Inkompatibilitäten bei der Zeichenfolgencodierung</span><span class="sxs-lookup"><span data-stu-id="17a8d-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="17a8d-136">Wenn Sie XML als Zeichenfolgenliteral kopieren und in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Abfrage-Editor einfügen, stellen Sie ggf. Inkompatibilitäten bei [N]VARCHAR-Zeichenfolgencodierungen fest.</span><span class="sxs-lookup"><span data-stu-id="17a8d-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="17a8d-137">Dies hängt von der Codierung Ihrer XML-Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="17a8d-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="17a8d-138">In vielen Fällen möchten Sie die XML-Deklaration möglicherweise entfernen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="17a8d-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17a8d-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="17a8d-140">Dann sollten Sie ein N einfügen, um aus der XML-Instanz eine Unicodeinstanz zu machen.</span><span class="sxs-lookup"><span data-stu-id="17a8d-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="17a8d-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="17a8d-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="17a8d-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17a8d-142">See Also</span></span>  
 [<span data-ttu-id="17a8d-143">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="17a8d-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
