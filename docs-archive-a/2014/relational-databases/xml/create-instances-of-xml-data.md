---
title: Erstellen Sie Instanzen der XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726794"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="5b202-102">Erstellen von Instanzen der XML-Daten</span><span class="sxs-lookup"><span data-stu-id="5b202-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="5b202-103">In diesem Thema wird beschrieben, wie XML-Instanzen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="5b202-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gibt es folgende Möglichkeiten, XML-Instanzen zu generieren:</span><span class="sxs-lookup"><span data-stu-id="5b202-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="5b202-105">Typumwandlung von Zeichenfolgeninstanzen</span><span class="sxs-lookup"><span data-stu-id="5b202-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="5b202-106">Verwenden der SELECT-Anweisung mit der FOR XML-Klausel</span><span class="sxs-lookup"><span data-stu-id="5b202-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="5b202-107">Verwenden von Konstantenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="5b202-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="5b202-108">Verwenden von Massenladen</span><span class="sxs-lookup"><span data-stu-id="5b202-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="5b202-109">Typumwandlung von Zeichenfolgen und Binärinstanzen</span><span class="sxs-lookup"><span data-stu-id="5b202-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="5b202-110">Sie können alle Zeichen folgen- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentypen, z. b. [**n**] [**var**]**char**, **[n] Text**, **varbinary**und **Image**, im-Datentyp analysieren, `xml` indem Sie die Zeichenfolge umwandeln (cast) oder konvertieren (Convert) `xml` .</span><span class="sxs-lookup"><span data-stu-id="5b202-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="5b202-111">Nicht typisiertes XML wird überprüft, um die Wohlgeformtheit zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5b202-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="5b202-112">Wenn dem Typ ein Schema zugeordnet ist `xml` , wird auch die Validierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5b202-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="5b202-113">Weitere Informationen finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="5b202-114">XML-Dokumente können unterschiedlich codiert werden (z. B.: UTF-8, UTF-16, Windows-1252).</span><span class="sxs-lookup"><span data-stu-id="5b202-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="5b202-115">Im Folgenden werden die Regeln erläutert, nach denen Zeichenfolgen- und Binärtypen mit der Codierung des XML-Dokuments interagieren und die das Verhalten des Parsers steuern.</span><span class="sxs-lookup"><span data-stu-id="5b202-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="5b202-116">Da **nvarchar** eine Doppelbyte-Unicode-Codierung wie UTF-16 oder UCS-2 annimmt, behandelt der XML-Parser den Zeichenfolgenwert als Doppelbyte-Unicode-codiertes XML-Dokument oder -Fragment.</span><span class="sxs-lookup"><span data-stu-id="5b202-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="5b202-117">Dies bedeutet, dass auch das XML-Dokument in Doppelbyte-Unicode codiert sein muss, um mit dem Quelldatentyp kompatibel zu sein.</span><span class="sxs-lookup"><span data-stu-id="5b202-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="5b202-118">Ein UTF-16-codiertes XML-Dokument kann eine UTF-16-Bytereihenfolgemarke (BOM, Byte Order Mark) besitzen, benötigt diese aber nicht, da der Kontext des Quelltyps deutlich macht, dass es sich nur um ein Doppelbyte-Unicode-Dokument handeln kann.</span><span class="sxs-lookup"><span data-stu-id="5b202-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="5b202-119">Der Inhalt einer **varchar** -Zeichenfolge wird vom XML-Parser als Einzelbyte-XML-Dokument/-Fragment behandelt.</span><span class="sxs-lookup"><span data-stu-id="5b202-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="5b202-120">Da der Quellzeichenfolge **varchar** eine Codepage zugeordnet ist, verwendet der Parser diese Codepage für die Codierung, wenn im XML-Code keine explizite Codierung angegeben ist. Wenn eine XML-Instanz eine BOM- oder eine Codierungsdeklaration besitzt, muss diese zur Codepage passen. Andernfalls gibt der Parser einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="5b202-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="5b202-121">Der Inhalt von **varbinary** wird als Codepointdatenstrom behandelt, der direkt an den XML-Parser übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5b202-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="5b202-122">Daher muss das XML-Dokument oder -Fragment die BOM- oder eine andere Codierungsangabe inline enthalten.</span><span class="sxs-lookup"><span data-stu-id="5b202-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="5b202-123">Der Parser bestimmt die Codierung ausschließlich anhand des Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="5b202-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="5b202-124">Dies bedeutet, dass UTF-16-codiertes XML die UTF-16-BOM enthalten muss, und dass eine Instanz ohne BOM und ohne Deklaration als UTF-8 interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b202-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="5b202-125">Wenn die Codierung des XML-Dokuments im Vorfeld nicht bekannt ist und die Daten vor der Konvertierung in XML als Zeichenfolgen- oder als Binärdaten übergeben werden, sollten die Daten als **varbinary**behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="5b202-126">Wenn z.B. Daten aus einer XML-Datei mit OpenRowset() gelesen werden, sollten die zu lesenden Daten als **varbinary(max)** -Wert festgelegt sein:</span><span class="sxs-lookup"><span data-stu-id="5b202-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b202-127">stellt XML intern in einer effizienten Binärdarstellung dar, die UTF-16-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b202-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="5b202-128">Vom Benutzer bereitgestellte Codierung wird nicht beibehalten, während des Analysevorgangs jedoch berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5b202-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="5b202-129">Typumwandlung benutzerdefinierter CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="5b202-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="5b202-130">Wenn ein benutzerdefinierter CLR-Typ eine XML-Serialisierung besitzt, können Instanzen dieses Typs explizit in einen XML-Datentyp umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="5b202-131">Weitere Einzelheiten zur XML-Serialisierung von benutzerdefinierten CLR-Typen finden Sie unter [XML-Serialisierung auf Grundlage von CLR-Datenbankobjekten](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="5b202-132">Leerzeichenbehandlung in typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="5b202-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="5b202-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]werden Leerzeichen in Elementinhalten als unbedeutend betrachtet, wenn diese in einer Sequenz von Nur-Leerzeichen-Zeichendaten auftreten, die durch ein Markup wie z. B. Begin- oder End-Tags getrennt und nicht in Entitäten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="5b202-134">(CDATA-Abschnitte werden ignoriert). Diese Behandlung von Leerzeichen unterscheidet sich von der Beschreibung von Leerzeichen in der XML 1.0-Spezifikation, die vom W3C (World Wide Web Consortium) veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="5b202-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="5b202-135">Die Ursache ist darin zu suchen, dass der XML-Parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nur eine beschränkte Anzahl der in XML 1.0 definierten DTD-Teilmengen erkennt.</span><span class="sxs-lookup"><span data-stu-id="5b202-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="5b202-136">Weitere Informationen zu den beschränkten DTD-Teilmengen, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt werden, finden Sie unter [CAST und CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b202-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="5b202-137">Standardmäßig verwirft der XML-Parser insignifikante Leerzeichen, wenn Zeichenfolgendaten in XML konvertiert werden, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5b202-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="5b202-138">`The xml:space` -Attribut ist nicht für ein Element oder seine Vorgängerelemente definiert.</span><span class="sxs-lookup"><span data-stu-id="5b202-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="5b202-139">Das `xml:space` -Attribut für ein Element oder eines seiner Vorgängerelemente weist den Standardwert auf.</span><span class="sxs-lookup"><span data-stu-id="5b202-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="5b202-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5b202-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="5b202-141">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="5b202-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="5b202-142">Sie können dieses Verhalten jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="5b202-142">However, you can change this behavior.</span></span> <span data-ttu-id="5b202-143">Um Leerzeichen für eine xml DT-Instanz beizubehalten, verwenden Sie den CONVERT-Operator und seinen optionalen *style* -Parameter, um einen Wert von 1 festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5b202-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="5b202-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5b202-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="5b202-145">Wenn der *style* -Parameter nicht verwendet oder sein Wert auf 0 festgelegt wird, werden insignifikante Leerzeichen für die Konvertierung der xml DT-Instanz nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5b202-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="5b202-146">Weitere Informationen zum Verwenden des CONVERT-Operators und seines *style*-Parameters beim Konvertieren von Zeichenfolgendaten in XML DT-Instanzen finden Sie unter [CAST und CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5b202-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="5b202-147">Beispiel: Umwandeln eines Zeichenfolgenwerts in typisiertes XML und Zuweisen des Werts zu einer Spalte</span><span class="sxs-lookup"><span data-stu-id="5b202-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="5b202-148">Im folgenden Beispiel wird eine Zeichen folgen Variable, die ein XML-Fragment enthält, in den `xml` -Datentyp umgewandelt und dann in der `xml` Type-Spalte gespeichert:</span><span class="sxs-lookup"><span data-stu-id="5b202-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="5b202-149">Der folgende INSERT-Vorgang konvertiert implizit eine Zeichenfolge in den- `xml` Typ:</span><span class="sxs-lookup"><span data-stu-id="5b202-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="5b202-150">Sie können die Zeichenfolge explizit in den Typ umwandeln `xml` :</span><span class="sxs-lookup"><span data-stu-id="5b202-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="5b202-151">Sie können auch convert() wie im folgenden Beispiel gezeigt verwenden:</span><span class="sxs-lookup"><span data-stu-id="5b202-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="5b202-152">Beispiel: Konvertieren einer Zeichenfolge in typisiertes XML und Zuweisen der Zeichenfolge zu einer Spalte</span><span class="sxs-lookup"><span data-stu-id="5b202-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="5b202-153">Im folgenden Beispiel wird eine Zeichenfolge in den `xml` -Typ konvertiert und einer Variablen des- `xml` Datentyps zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="5b202-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="5b202-154">Verwenden der SELECT-Anweisung mit einer FOR XML-Klausel</span><span class="sxs-lookup"><span data-stu-id="5b202-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="5b202-155">Sie können die FOR XML-Klausel in einer SELECT-Anweisung verwenden, um Ergebnisse als XML zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5b202-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="5b202-156">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5b202-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="5b202-157">Die SELECT-Anweisung gibt ein XML-Textfragment zurück, das dann während der Zuweisung zur `xml` Variablen des-Datentyps analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b202-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="5b202-158">Sie können auch die [Type-Direktive](type-directive-in-for-xml-queries.md) in der for XML-Klausel verwenden, die direkt ein for XML-Abfrageergebnis als Typ zurückgibt `xml` :</span><span class="sxs-lookup"><span data-stu-id="5b202-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="5b202-159">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="5b202-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="5b202-160">Im folgenden Beispiel wird das typisierte `xml` Ergebnis einer for XML-Abfrage in eine `xml` Spalte vom Typ eingefügt:</span><span class="sxs-lookup"><span data-stu-id="5b202-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="5b202-161">Weitere Informationen zu FOR XML finden Sie unter [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b202-162">Von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden `xml`-Datentypinstanzen an den Client zurückgegeben, die das Ergebnis unterschiedlicher Serverkonstrukte sind (z. B. FOR XML-Abfragen, für die die TYPE-Direktive verwendet wird, oder bei denen der `xml`-Datentyp verwendet wird, um XML aus SQL-Spalten, -Variablen und -Ausgabeparametern zurückzugeben).</span><span class="sxs-lookup"><span data-stu-id="5b202-162">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="5b202-163">Im Clientanwendungscode wird vom ADO.NET-Anbieter angefordert, dass diese `xml`-Datentypinformationen als Binärcode vom Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="5b202-164">Wenn Sie FOR XML jedoch ohne die TYPE-Direktive verwenden, werden die XML-Daten als Zeichenfolgentyp zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b202-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="5b202-165">Der Clientanbieter ist in jedem Fall fähig, beide XML-Formate zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b202-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="5b202-166">Verwenden von Konstantenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="5b202-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="5b202-167">Eine Zeichen folgen Konstante kann verwendet werden, wenn eine Instanz des- `xml` Datentyps erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="5b202-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="5b202-168">Dies entspricht einer impliziten CAST-Anweisung für die Zeichenfolge in XML.</span><span class="sxs-lookup"><span data-stu-id="5b202-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="5b202-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5b202-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="5b202-170">Im vorherigen Beispiel wird die Zeichenfolge implizit in den `xml` -Datentyp konvertiert und einer `xml` Variablen vom Typ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5b202-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="5b202-171">Im folgenden Beispiel wird eine Konstante Zeichenfolge in eine `xml` Spalte vom Typ eingefügt:</span><span class="sxs-lookup"><span data-stu-id="5b202-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="5b202-172">Für typisiertes XML wird das XML für das angegebene Schema überprüft.</span><span class="sxs-lookup"><span data-stu-id="5b202-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="5b202-173">Weitere Informationen finden Sie unter [Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="5b202-174">Verwenden von Massenkopieren</span><span class="sxs-lookup"><span data-stu-id="5b202-174">Using Bulk Load</span></span>  
 <span data-ttu-id="5b202-175">Die verbesserten [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) -Funktionen ermöglichen das Massenkopieren von XML-Dokumenten in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5b202-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="5b202-176">Sie können XML-Instanzen aus Dateien in die `xml` Typspalten in der Datenbank Massen laden.</span><span class="sxs-lookup"><span data-stu-id="5b202-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="5b202-177">Funktionierende Beispiele finden Sie unter [Beispiele für den Massenimport und -export von XML-Dokumenten &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="5b202-178">Weitere Informationen über das Laden von XML-Dokumenten finden Sie unter [Laden von XML-Daten](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="5b202-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b202-179">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b202-179">In This Section</span></span>  
  
|<span data-ttu-id="5b202-180">Thema</span><span class="sxs-lookup"><span data-stu-id="5b202-180">Topic</span></span>|<span data-ttu-id="5b202-181">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b202-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5b202-182">Abrufen und Abfragen von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="5b202-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="5b202-183">Beschreibt die Teile von XML-Instanzen, die nicht beibehalten werden, wenn sie in Datenbanken gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5b202-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b202-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b202-184">See Also</span></span>  
 <span data-ttu-id="5b202-185">[Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="5b202-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="5b202-186">[XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="5b202-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="5b202-187">[XML DML &#40;Data Modification Language&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="5b202-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="5b202-188">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5b202-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
