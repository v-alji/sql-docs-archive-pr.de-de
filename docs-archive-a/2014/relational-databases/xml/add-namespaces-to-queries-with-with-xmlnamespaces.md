---
title: Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608451"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="e596e-102">Hinzufügen von Namespaces zu Abfragen mit WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="e596e-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="e596e-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) bietet folgende Namespace-URI-Unterstützung:</span><span class="sxs-lookup"><span data-stu-id="e596e-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="e596e-104">Macht das Namespacepräfix für die URI-Zuordnung bei Abfragen mit [Erstellen von XML mit FOR XML](for-xml-sql-server.md) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e596e-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="e596e-105">Macht die Namespace-URI-Zuordnung für den statischen Namespacekontext für [XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e596e-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="e596e-106">Verwenden von WITH XMLNAMESPACES in FOR XML-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e596e-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="e596e-107">Mit WITH XMLNAMESPACES können Sie XML-Namespaces in FOR XML-Abfragen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="e596e-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="e596e-108">Nehmen Sie beispielsweise folgende FOR XML-Abfrage:</span><span class="sxs-lookup"><span data-stu-id="e596e-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="e596e-109">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e596e-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="e596e-110">Um Namespaces zu dem durch die FOR XML-Abfrage erstellten XML hinzuzufügen, legen Sie zuerst mit der WITH NAMESPACES-Klausel die Zuordnungen der Namespacepräfixe zu URIs fest.</span><span class="sxs-lookup"><span data-stu-id="e596e-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="e596e-111">Verwenden Sie anschließend in der folgenden geänderten Abfrage die Namespacepräfixe, um die in der Abfrage verwendeten Namen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e596e-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="e596e-112">Die WITH XMLNAMESPACES-Klausel legt die Zuordnung des Namespacepräfixes (`ns1`) zum URI (`uri`) fest.</span><span class="sxs-lookup"><span data-stu-id="e596e-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="e596e-113">Das `ns1` -Präfix wird dann beim Festlegen der Element- und Attributnamen verwendet, die durch die FOR XML-Abfrage erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e596e-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="e596e-114">Das XML-Ergebnis enthält die Namespacepräfixe:</span><span class="sxs-lookup"><span data-stu-id="e596e-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="e596e-115">Für die WITH XMLNAMESPACES-Klausel gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e596e-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="e596e-116">Sie wird nur im RAW-, AUTO- und PATH-Modus der FOR XML-Abfragen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e596e-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="e596e-117">Der EXPLICIT-Modus wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e596e-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="e596e-118">Sie wirkt sich nur auf die Namespacepräfixe von FOR XML-Abfragen und auf die **xml** -Datentypmethode aus – aber nicht auf den XML-Parser.</span><span class="sxs-lookup"><span data-stu-id="e596e-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="e596e-119">Die folgende Abfrage gibt beispielsweise einen Fehler zurück, weil das XML-Dokument keine Namespacedeklaration für das myNS-Präfix enthält.</span><span class="sxs-lookup"><span data-stu-id="e596e-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="e596e-120">Die FOR XML-Direktiven XMLSCHEMA und XMLDATA können nicht zusammen mit der WITH XMLNAMESPACES-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e596e-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="e596e-121">Verwenden der XSINIL-Direktive</span><span class="sxs-lookup"><span data-stu-id="e596e-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="e596e-122">Wenn Sie die ELEMENTS XSINIL-Direktive verwenden, können Sie das xsi-Präfix nicht in der WITH XMLNAMESPACES-Klausel definieren.</span><span class="sxs-lookup"><span data-stu-id="e596e-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="e596e-123">Es wird stattdessen automatisch hinzugefügt, wenn Sie ELEMENTS XSINIL verwenden.</span><span class="sxs-lookup"><span data-stu-id="e596e-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="e596e-124">Die folgende Abfrage verwendet ELEMENTS XSINIL, die elementzentriertes XML generiert, wo Elementen, deren **xsi:nil** -Attribut auf TRUE festgelegt ist, Nullwerte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e596e-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="e596e-125">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e596e-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="e596e-126">Angeben von Standardnamespaces</span><span class="sxs-lookup"><span data-stu-id="e596e-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="e596e-127">Statt ein Namespacepräfix zu deklarieren, können Sie mit dem DEFAULT-Schlüsselwort einen Standardnamespace deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e596e-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="e596e-128">In der FOR XML-Abfrage wird der Standardnamespace mit den XML-Knoten des resultierenden XML verbunden.</span><span class="sxs-lookup"><span data-stu-id="e596e-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="e596e-129">Im folgenden Beispiel definiert WITH XMLNAMESPACES zwei Namespacepräfixe, die gemeinsam über einen Standardnamespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e596e-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="e596e-130">Die FOR XML-Abfrage generiert elementzentriertes XML.</span><span class="sxs-lookup"><span data-stu-id="e596e-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="e596e-131">Die Abfrage verwendet bei der Knotenbenennung beide Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="e596e-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="e596e-132">In der SELECT-Klausel legen ProductID, Name und Color keine Namen mit einem Präfix fest.</span><span class="sxs-lookup"><span data-stu-id="e596e-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="e596e-133">Daher gehören die entsprechenden Elemente des resultierenden XML zum Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="e596e-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="e596e-134">Die folgende Abfrage ähnelt der vorherigen, allerdings ist der FOR XML AUTO-Modus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e596e-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="e596e-135">Verwenden vordefinierter Namespaces</span><span class="sxs-lookup"><span data-stu-id="e596e-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="e596e-136">Wenn Sie vordefinierte Namespaces verwenden, müssen Sie (mit Ausnahme von xml-Namespace und xsi-Namespace, wenn ELEMENTS XSINIL verwendet wird) die Namespacebindung mit  WITH XMLNAMESPACES explizit festlegen.</span><span class="sxs-lookup"><span data-stu-id="e596e-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="e596e-137">Die folgende Abfrage definiert explizit den Namespacepräfix für die URI-Bindung für den vordefinierten Namespace (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="e596e-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="e596e-138">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e596e-138">This is the result.</span></span> <span data-ttu-id="e596e-139">SQLXML-Benutzer kennen diese XML-Vorlage.</span><span class="sxs-lookup"><span data-stu-id="e596e-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="e596e-140">Weitere Informationen finden Sie unter [SQLXML 4.0-Programmierkonzepte](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e596e-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="e596e-141">Nur das xml-Namespacepräfix kann verwendet werden ohne explizit in WITH XMLNAMESPACES definiert zu sein, was die folgende Abfrage im PATH-Modus zeigt.</span><span class="sxs-lookup"><span data-stu-id="e596e-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="e596e-142">Wenn das Präfix deklariert wird, muss es außerdem mit dem Namespace http://www.w3.org/XML/1998/namespace verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="e596e-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="e596e-143">Die in der SELECT-Klausel festgelegten Namen verweisen auf das xml-Namespacepräfix, das nicht explizit mit WITH XMLNAMESPACES definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e596e-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="e596e-144">Die @xml:lang-Attribute verwenden den vordefinierten XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e596e-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="e596e-145">Da in XML Version 1.0 keine explizite Deklaration der xml-Namespacebindung notwendig ist, enthält das Ergebnis keine explizite Deklaration der Namespacebindung.</span><span class="sxs-lookup"><span data-stu-id="e596e-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="e596e-146">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="e596e-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="e596e-147">Verwenden von WITH XMLNAMESPACES mit den xml-Datentypmethoden</span><span class="sxs-lookup"><span data-stu-id="e596e-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="e596e-148">Alle in einer SELECT-Abfrage oder in UPDATE (bei der [modify()](/sql/t-sql/xml/xml-data-type-methods) -Methode) festgelegten **xml-Datentypmethoden** müssen die Namespacedeklaration in ihrem Prolog wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e596e-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="e596e-149">Dies kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="e596e-149">This can be time-consuming.</span></span> <span data-ttu-id="e596e-150">Die folgende Abfrage ruft beispielsweise Produktmodell-IDs ab, deren Katalogbeschreibungen eine Spezifikation enthalten.</span><span class="sxs-lookup"><span data-stu-id="e596e-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="e596e-151">Dies geschieht, wenn das Element <`Specifications`> vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e596e-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="e596e-152">In der vorherigen Abfrage deklarieren die **query()** - und die **exist()** -Methode in ihrem Prolog denselben Namespace.</span><span class="sxs-lookup"><span data-stu-id="e596e-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="e596e-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e596e-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="e596e-154">Alternativ können Sie zuerst WITH XMLNAMESPACES deklarieren und in der Abfrage dann die Namespacepräfixe verwenden.</span><span class="sxs-lookup"><span data-stu-id="e596e-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="e596e-155">In diesem Fall enthalten die **query()** - und die **exist()** -Methode im Prolog keine Namespacedeklaration.</span><span class="sxs-lookup"><span data-stu-id="e596e-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="e596e-156">Eine explizite Deklaration im XQuery-Prolog überschreibt das in der WITH-Klausel definierte Namespacepräfix und den Standardelementnamespace.</span><span class="sxs-lookup"><span data-stu-id="e596e-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e596e-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e596e-157">See Also</span></span>  
 <span data-ttu-id="e596e-158">[XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="e596e-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="e596e-159">[XQuery-Sprachreferenz &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="e596e-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="e596e-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="e596e-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="e596e-161">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e596e-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
