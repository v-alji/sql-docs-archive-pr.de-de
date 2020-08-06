---
title: Definieren der Serialisierung von XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622455"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="6f3df-102">Definieren der Serialisierung von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="6f3df-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="6f3df-103">Beim expliziten oder impliziten Umwandeln des XML-Datentyps in eine SQL-Zeichenfolge oder einen Binärtyp wird der Inhalt des XML-Datentyps entsprechend der in diesem Thema beschriebenen Regeln serialisiert.</span><span class="sxs-lookup"><span data-stu-id="6f3df-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="6f3df-104">Serialisierungscodierung</span><span class="sxs-lookup"><span data-stu-id="6f3df-104">Serialization Encoding</span></span>  
 <span data-ttu-id="6f3df-105">Wenn der SQL-Zieltyp VARBINARY ist, erfolgt die Serialisierung des Ergebnisses in UTF-16 mit einer UTF-16-Markierung für die Bytereihenfolge am Anfang, jedoch ohne eine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6f3df-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="6f3df-106">Wenn der Zieltyp zu klein ist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6f3df-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="6f3df-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f3df-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="6f3df-108">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="6f3df-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="6f3df-109">Wenn der SQL-Zieltyp NVARCHAR oder NCHAR ist, erfolgt die Serialisierung des Ergebnisses in UTF-16 ohne die Markierung für die Bytereihenfolge am Anfang und ohne eine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6f3df-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="6f3df-110">Wenn der Zieltyp zu klein ist, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6f3df-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="6f3df-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f3df-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="6f3df-112">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="6f3df-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="6f3df-113">Wenn der SQL-Zieltyp VARCHAR oder NCHAR ist, erfolgt die Serialisierung des Ergebnisses in der Codierung, die der Codepage der Datenbanksortierung entspricht, ohne Markierung zur Bytereihenfolge oder XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="6f3df-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="6f3df-114">Wenn der Zieltyp zu klein ist oder der Wert nicht zur Codeseite der Zielsortierung zugeordnet werden kann, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6f3df-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="6f3df-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f3df-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="6f3df-116">Dies kann zu einem Fehler führen, wenn die Codepage der aktuellen Sortierung nicht das Unicode-Zeichen & # x10300; darstellen kann, oder es wird in der spezifischen Codierung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6f3df-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="6f3df-117">Beim Zurückgeben der XML-Ergebnisse an die Clientseite werden die Daten in UTF-16-Codierung gesendet.</span><span class="sxs-lookup"><span data-stu-id="6f3df-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="6f3df-118">Der clientseitige Anbieter macht die Daten dann entsprechend seinen API-Regeln verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f3df-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="6f3df-119">Serialisierung der XML-Strukturen</span><span class="sxs-lookup"><span data-stu-id="6f3df-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="6f3df-120">Der Inhalt eines **xml** -Datentyps wird auf die herkömmliche Art und Weise serialisiert.</span><span class="sxs-lookup"><span data-stu-id="6f3df-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="6f3df-121">Das heißt konkret, dass Elementknoten dem Elementmarkup zugeordnet und Textknoten dem Textinhalt zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="6f3df-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="6f3df-122">Die Umstände, unter denen die Zeichen in Entitäten geändert werden, und die Modalitäten beim Serialisieren von atomaren Werten werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f3df-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="6f3df-123">Ändern von XML-Zeichen in Entitäten bei der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6f3df-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="6f3df-124">Jede serialisierte XML-Struktur muss in der Lage sein, neu analysiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="6f3df-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="6f3df-125">Deshalb müssen einige Zeichen so serialisiert werden, dass sie in eine Entität geändert werden, damit die Roundtripfähigkeit der Zeichen in der gesamten Normalisierungsphase des XML-Parsers erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="6f3df-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="6f3df-126">Allerdings müssen einige Zeichen so in Entitäten geändert werden, dass das Dokument wohlgeformt ist und somit analysiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6f3df-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="6f3df-127">Im Folgenden sind die bei der Serialisierung geltenden Regeln für das Ändern in Entitäten aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6f3df-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="6f3df-128">Die Zeichen „&“, und „\<, and >“ werden immer in die Entitäten &amp;, &lt; oder &gt; geändert, wenn sie in einem Attributwert oder Elementinhalt auftreten.</span><span class="sxs-lookup"><span data-stu-id="6f3df-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="6f3df-129">Da SQL Server ein Anführungszeichen (U+0022) zum Einschließen von Attributwerten verwendet, wird das Anführungszeichen in Attributwerten bei der Änderung in Entitäten zu &quot;.</span><span class="sxs-lookup"><span data-stu-id="6f3df-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="6f3df-130">Ein Ersatzpaar wird beim Ändern in Entitäten zu einem einzelnen numerischen Zeichenverweis, wenn die Umwandlung nur auf dem Server erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6f3df-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="6f3df-131">So wird z.B. das Ersatzpaar U+D800 U+DF00 beim Ändern in Entitäten zum numerischen Zeichenverweis &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="6f3df-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="6f3df-132">Um zu verhindern, dass ein Tabstopp (U+0009) und ein Zeilenvorschub (LF, U+000A) beim Analysieren normalisiert werden, werden sie beim Ändern in Entitäten zu ihren numerischen Zeichenverweisen &\#x9; bzw. &\#xA; innerhalb von Attributwerten.</span><span class="sxs-lookup"><span data-stu-id="6f3df-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="6f3df-133">Um zu verhindern, dass ein Wagenrücklauf (CR, U+000D) beim Analysieren normalisiert wird, wird er beim Ändern in Entitäten zu seinem numerischen Zeichenverweis &\#xD; sowohl innerhalb von Attributwerten als auch in Elementinhalt.</span><span class="sxs-lookup"><span data-stu-id="6f3df-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="6f3df-134">Um Textknoten zu schützen, die ausschließlich Leerzeichen enthalten, wird eines der Leerzeichen – zumeist das letzte – beim Ändern in Entitäten zu dessen numerischem Zeichenverweis.</span><span class="sxs-lookup"><span data-stu-id="6f3df-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="6f3df-135">Auf diese Weise bleibt der Leerzeichentextknoten beim Neuanalysieren erhalten, und zwar unabhängig von der Einstellung zur Handhabung von Leerzeichen beim Analysieren.</span><span class="sxs-lookup"><span data-stu-id="6f3df-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="6f3df-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f3df-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="6f3df-137">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="6f3df-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="6f3df-138">Wenn Sie die letzte Leerzeichenschutzregel nicht anwenden wollen, können Sie die explizite CONVERT-Option 1 beim Umwandeln von **xml** in einen Zeichenfolgen- oder Binärtyp verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f3df-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="6f3df-139">Sie können z. B. folgende Aktionen ausführen, um das Ändern in Entitäten zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="6f3df-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="6f3df-140">Beachten Sie, dass die [query()-Methode (xml-Datentyp)](/sql/t-sql/xml/query-method-xml-data-type) eine xml-Datentypinstanz ergibt.</span><span class="sxs-lookup"><span data-stu-id="6f3df-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="6f3df-141">Deshalb wird jedes Ergebnis der **query()** -Methode, das in einen Zeichenfolgen- oder Binärtyp umgewandelt wird, entsprechend den zuvor beschriebenen Regeln in Entitäten geändert.</span><span class="sxs-lookup"><span data-stu-id="6f3df-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="6f3df-142">Wenn Sie Zeichenfolgenwerte erhalten wollen, die nicht in Entitäten geändert wurden, sollten Sie stattdessen die [value()-Methode (xml-Datentyp)](/sql/t-sql/xml/value-method-xml-data-type) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f3df-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="6f3df-143">Es folgt ein Beispiel zum Verwenden der **query()** -Methode:</span><span class="sxs-lookup"><span data-stu-id="6f3df-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="6f3df-144">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="6f3df-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="6f3df-145">Es folgt ein Beispiel zum Verwenden der **query(** )-Methode:</span><span class="sxs-lookup"><span data-stu-id="6f3df-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="6f3df-146">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="6f3df-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="6f3df-147">Serialisieren eines typisierten xml-Datentyps</span><span class="sxs-lookup"><span data-stu-id="6f3df-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="6f3df-148">Eine typisierte **xml** -Datentypinstanz enthält Werte, die entsprechend ihren XML-Schematypen typisiert sind.</span><span class="sxs-lookup"><span data-stu-id="6f3df-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="6f3df-149">Diese Werte werden entsprechend ihrem XML-Schematyp in dasselbe Format serialisiert, wie es bei der XQuery-Umwandlung in xs:string entsteht.</span><span class="sxs-lookup"><span data-stu-id="6f3df-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="6f3df-150">Weitere Informationen finden Sie unter [Typumwandlungsregeln in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="6f3df-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="6f3df-151">So wird z. B. der xs:double-Wert 1.34e1 zu 13.4 serialisiert, wie das im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6f3df-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="6f3df-152">Es wird der Zeichenfolgenwert 13.4 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f3df-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3df-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f3df-153">See Also</span></span>  
 <span data-ttu-id="6f3df-154">[Typumwandlungsregeln in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="6f3df-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="6f3df-155">CAST und CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6f3df-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
