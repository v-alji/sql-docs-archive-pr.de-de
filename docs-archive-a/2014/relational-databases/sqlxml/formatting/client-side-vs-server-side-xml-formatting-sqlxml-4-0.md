---
title: Client seitige und Server seitige XML-Formatierung (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619711"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="73526-102">Clientseitige im Vergleich zur serverseitigen XML-Formatierung (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="73526-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="73526-103">In diesem Thema werden die allgemeinen Unterschiede zwischen clientseitiger und serverseitiger XML-Formatierung in SQLXML beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73526-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="73526-104">Keine Unterstützung von mehreren Rowset-Abfragen bei der clientseitigen Formatierung</span><span class="sxs-lookup"><span data-stu-id="73526-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="73526-105">Abfragen, die mehrere Rowsets generieren, werden bei einer clientseitigen XML-Formatierung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73526-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="73526-106">Beispiel: Sie haben ein virtuelles Verzeichnis, für das eine clientseitige Formatierung angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="73526-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="73526-107">Beachten Sie diese Beispiel Vorlage mit zwei SELECT-Anweisungen in einem- **\<sql:query>** Block:</span><span class="sxs-lookup"><span data-stu-id="73526-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-108">Sie können diese Vorlage im Anwendungscode ausführen, es wird ein Fehler zurückgegeben, da die clientseitige XML-Formatierung keine Formatierung mehrerer Rowsets unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73526-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="73526-109">Wenn Sie die Abfragen in zwei separaten **\<sql:query>** Blöcken angeben, erhalten Sie die gewünschten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="73526-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="73526-110">Unterschiedliche timestamp-Zuordnungen bei der client- und serverseitigen Formatierung</span><span class="sxs-lookup"><span data-stu-id="73526-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="73526-111">Bei der serverseitigen XML-Formatierung wird die Datenbankspalte des `timestamp`-Typs dem i8 XDR-Typ zugeordnet (wenn die XMLDATA-Option in der Abfrage angegeben wurde).</span><span class="sxs-lookup"><span data-stu-id="73526-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="73526-112">Bei der clientseitigen XML-Formatierung wird die Datenbankspalte des `timestamp`-Typs entweder dem `uri`- oder dem `bin.base64` XDR-Typ zugeordnet. (Dies ist davon abhängig, ob die Binär-base64-Option in der Abfrage angegeben wurde.)</span><span class="sxs-lookup"><span data-stu-id="73526-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="73526-113">Der `bin.base64` XDR-Typ ist nützlich, wenn Sie die Features Update Gram und Bulkload verwenden, da dieser Typ in den-Typ konvertiert wird [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` .</span><span class="sxs-lookup"><span data-stu-id="73526-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="73526-114">Auf diese Art werden die Einfüge-, Update- oder Löschvorgänge erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="73526-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="73526-115">Bei serverseitiger Formatierung werden tiefe VARIANTs verwendet</span><span class="sxs-lookup"><span data-stu-id="73526-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="73526-116">Bei der serverseitigen XML-Formatierung werden tiefe Typen eines VARIANT-Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="73526-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="73526-117">Bei der clientseitigen XML-Formatierung werden die Varianten in Unicode-Zeichenfolgen konvertiert und die Untertypen von VARIANT werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="73526-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="73526-118">NESTED-Modus im Vergleich zum AUTO-Modus</span><span class="sxs-lookup"><span data-stu-id="73526-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="73526-119">Der NESTED-Modus des clientseitigen FOR XML ähnelt dem AUTO-Modus des serverseitigen FOR XML. Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="73526-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="73526-120">Wenn Sie Sichten mit AUTO-Modus serverseitig abfragen, wird der Sichtname als Elementname in der resultierenden XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="73526-121">Nehmen Sie beispielsweise an, dass die folgende Ansicht für die Person. Contact-Tabelle in der adventureworksdatabase-Datenbank erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="73526-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="73526-122">Die folgende Vorlage gibt eine Abfrage der ContactView-Sicht und die serverseitige XML-Formatierung an:</span><span class="sxs-lookup"><span data-stu-id="73526-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-123">Wenn Sie die Vorlage ausführen, wird die folgende XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="73526-124">(Es werden nur partielle Ergebnisse angezeigt.) Beachten Sie, dass die Elementnamen die Namen der Sichten sind, für die die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73526-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="73526-125">Wenn Sie die clientseitige XML-Formatierung mit dem entsprechenden NESTED-Modus angeben, werden die Basistabellennamen als Elementnamen in der resultierenden XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="73526-126">Beispielsweise führt die folgende überarbeitete Vorlage dieselbe SELECT-Anweisung aus, die XML-Formatierung wird jedoch auf der Clientseite ausgeführt (d. h., **Client-Side-XML** wird in der Vorlage auf true festgelegt):</span><span class="sxs-lookup"><span data-stu-id="73526-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-127">Durch die Ausführung der Vorlage wird die folgende XML erstellt.</span><span class="sxs-lookup"><span data-stu-id="73526-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="73526-128">Beachten Sie, dass in diesem Fall der Elementname der Basistabellenname ist.</span><span class="sxs-lookup"><span data-stu-id="73526-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="73526-129">Wenn Sie den AUTO-Modus des serverseitigen FOR XML verwenden, werden die in der Abfrage angegebenen Tabellenaliasse als Elementnamen in der resultierenden XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="73526-130">Betrachten Sie z. B. die folgende Vorlage:</span><span class="sxs-lookup"><span data-stu-id="73526-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-131">Durch die Ausführung der Vorlage wird die folgende XML erstellt:</span><span class="sxs-lookup"><span data-stu-id="73526-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="73526-132">Wenn Sie den NESTED-Modus des clientseitigen FOR XML verwenden, werden die Tabellennamen als Elementnamen in der resultierenden XML zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="73526-133">(Tabellen Aliase, die in der Abfrage angegeben werden, werden nicht verwendet.) Sehen Sie sich beispielsweise die folgende Vorlage an:</span><span class="sxs-lookup"><span data-stu-id="73526-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-134">Durch die Ausführung der Vorlage wird die folgende XML erstellt:</span><span class="sxs-lookup"><span data-stu-id="73526-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="73526-135">Wenn eine Abfrage Spalten als dbobject-Abfragen zurückgibt, können Sie keine Aliasse für diese Spalten verwenden.</span><span class="sxs-lookup"><span data-stu-id="73526-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="73526-136">Die folgende Vorlage führt beispielsweise eine Abfrage aus, die eine Mitarbeiter-ID und ein Foto zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="73526-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-137">Wenn Sie diese Vorlage ausführen, wird die Photo-Spalte als eine dbobject-Abfrage zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73526-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="73526-138">In dieser dbobject-Abfrage verweist `@P` auf einen Spaltennamen, der nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="73526-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-139">Wenn die XML-Formatierung auf dem Server (**Client-Side-XML = "0"**) ausgeführt wird, können Sie den Alias für die Spalten verwenden, die dbobject-Abfragen zurückgeben, in denen tatsächliche Tabellen-und Spaltennamen zurückgegeben werden (auch wenn Sie Aliase angegeben haben).</span><span class="sxs-lookup"><span data-stu-id="73526-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="73526-140">Die folgende Vorlage führt z. b. eine Abfrage aus, und die XML-Formatierung erfolgt auf dem Server (die **Client seitige XML-** Option ist nicht angegeben, und die Option **auf Client ausführen** ist für das virtuelle Stammverzeichnis nicht ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="73526-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="73526-141">Die Abfrage gibt auch den AUTO-Modus an (nicht den clientseitigen NESTED-Modus).</span><span class="sxs-lookup"><span data-stu-id="73526-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="73526-142">Wenn diese Vorlage ausgeführt wird, wird das folgende XML-Dokument zurückgegeben (beachten Sie, dass die Aliasse nicht in der dbobject-Abfrage für die LargePhoto-Spalte verwendet werden):</span><span class="sxs-lookup"><span data-stu-id="73526-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="73526-143">Clientseitiger im Vergleich zu serverseitigem XPath</span><span class="sxs-lookup"><span data-stu-id="73526-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="73526-144">Clientseitiger XPath und serverseitiger XPath funktionieren gleichermaßen, weisen jedoch die folgenden Unterschiede auf:</span><span class="sxs-lookup"><span data-stu-id="73526-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="73526-145">Die Datenkonvertierungen, die angewendet werden, wenn Sie clientseitige XPath-Abfragen verwenden, unterscheiden sich von jenen, die angewendet werden, wenn Sie serverseitige XPath-Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="73526-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="73526-146">Clientseitiger XPath verwendet CAST anstelle von CONVERT-Modus 126.</span><span class="sxs-lookup"><span data-stu-id="73526-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="73526-147">Wenn Sie **Client-Side-XML = "0"** (false) in einer Vorlage angeben, fordern Sie die serverseitige XML-Formatierung an.</span><span class="sxs-lookup"><span data-stu-id="73526-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="73526-148">Sie können somit nicht FOR XML NESTED angeben, da der Server die NESTED-Option nicht erkennt.</span><span class="sxs-lookup"><span data-stu-id="73526-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="73526-149">In diesem Fall wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="73526-149">This generates an error.</span></span> <span data-ttu-id="73526-150">Sie müssen die Modi AUTO, RAW oder EXPLICIT verwenden, die der Server erkennt.</span><span class="sxs-lookup"><span data-stu-id="73526-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="73526-151">Wenn Sie **Client-Side-XML = "1"** (true) in einer Vorlage angeben, fordern Sie eine Client seitige XML-Formatierung an.</span><span class="sxs-lookup"><span data-stu-id="73526-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="73526-152">In diesem Fall können Sie FOR XML NESTED angeben.</span><span class="sxs-lookup"><span data-stu-id="73526-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="73526-153">Wenn Sie for XML Auto angeben, erfolgt die XML-Formatierung auf der Serverseite, obwohl **Client-Side-XML = "1"** in der Vorlage angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="73526-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73526-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73526-154">See Also</span></span>  
 <span data-ttu-id="73526-155">[Informationen zu den XML-Sicherheitsüberlegungen &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="73526-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="73526-156">[Client seitige XML-Formatierung &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="73526-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="73526-157">Server seitige XML-Formatierung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="73526-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
