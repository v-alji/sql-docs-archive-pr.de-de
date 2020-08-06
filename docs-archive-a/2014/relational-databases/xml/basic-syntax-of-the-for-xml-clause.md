---
title: Basissyntax der FOR XML-Klausel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608449"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="9f0a8-102">Basissyntax der FOR XML-Klausel</span><span class="sxs-lookup"><span data-stu-id="9f0a8-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="9f0a8-103">Der FOR XML-Modus kann RAW, AUTO, EXPLICIT oder PATH lauten.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="9f0a8-104">Er bestimmt die Form des erhaltenen XML.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9f0a8-105">Die XMLDATA-Direktive zur FOR XML-Option ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="9f0a8-106">Verwenden Sie XSD-Generierung für RAW- und AUTO-Modus.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="9f0a8-107">Es gibt keinen Ersatz für die XMLDATA-Direktive im EXPLICIT-Modus.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="9f0a8-108">Im folgenden finden Sie die grundlegende Syntax, die in der [for-Klausel (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql)beschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="9f0a8-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f0a8-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="9f0a8-109">Arguments</span></span>  
 <span data-ttu-id="9f0a8-110">RAW[('*ElementName*')]</span><span class="sxs-lookup"><span data-stu-id="9f0a8-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="9f0a8-111">Verwendet das Abfrageergebnis und wandelt jede Zeile im Resultset in ein XML-Element mit einem generischen Bezeichner (\<row />) als Elementtag um.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="9f0a8-112">Sie können optional einen Namen für das Zeilenelement angeben, wenn Sie diese Direktive verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="9f0a8-113">Das sich ergebende XML verwendet den angegebenen *ElementName* als das für jede Zeile generierte Zeilenelement.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="9f0a8-114">Weitere Informationen finden Sie unter [Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="9f0a8-115">AUTO</span></span>  
 <span data-ttu-id="9f0a8-116">Gibt Abfrageergebnisse in einer einfachen, geschachtelten XML-Struktur zurück.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="9f0a8-117">Jede Tabelle in der FROM-Klausel, aus der mindestens eine Spalte in der SELECT-Klausel aufgeführt ist, wird als ein XML-Element dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="9f0a8-118">Die in der SELECT-Klausel aufgelisteten Spalten werden den entsprechenden Elementattributen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="9f0a8-119">Weitere Informationen finden Sie unter [Verwenden des AUTO-Modus mit FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="9f0a8-120">EXPLICIT</span></span>  
 <span data-ttu-id="9f0a8-121">Gibt an, dass die Form der sich ergebenden XML-Struktur explizit definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="9f0a8-122">In diesem Modus müssen die Abfragen jedoch auf eine bestimmte Weise geschrieben werden, sodass zusätzliche Informationen über die gewünschte Schachtelung explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="9f0a8-123">Weitere Informationen finden Sie unter [Verwenden des EXPLICIT-Modus mit FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-124">PATH</span><span class="sxs-lookup"><span data-stu-id="9f0a8-124">PATH</span></span>  
 <span data-ttu-id="9f0a8-125">Stellt ein einfacheres Verfahren zum Mischen von Elementen und Attributen bereit und führt zusätzliche Schachtelung für die Darstellung komplexer Eigenschaften ein.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="9f0a8-126">Sie können Abfragen im FOR XML EXPLICIT-Modus zum Erstellen dieser Art von XML aus einem Rowset verwenden, der PATH-Modus stellt jedoch eine einfachere Alternative zu den möglicherweise aufwendigen Abfragen im EXPLICIT-Modus bereit.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="9f0a8-127">Der PATH-Modus ermöglicht in Kombination mit der Möglichkeit, verschachtelte FOR XML-Abfragen zu schreiben und die TYPE-Direktive zum Zurückgeben von Instanzen des Typs **xml** zu verwenden, das Schreiben von Abfragen mit geringerer Komplexität.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="9f0a8-128">Er bietet eine Alternative zum Schreiben der meisten Abfragen im EXPLICIT-Modus.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="9f0a8-129">Standardmäßig generiert der PATH-Modus einen \<row>-Elementwrapper für jede Zeile im Resultset.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="9f0a8-130">Optional können Sie einen Elementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-130">You can optionally specify an element name.</span></span> <span data-ttu-id="9f0a8-131">Wenn Sie einen Elementnamen angeben, wird der angegebene Name als Wrapperelementname verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="9f0a8-132">Bei einer leeren Zeichenfolge (FOR XML PATH ('')) wird kein Wrapperelement generiert.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="9f0a8-133">Weitere Informationen finden Sie unter [Verwenden des PATH-Modus mit FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="9f0a8-134">XMLDATA</span></span>  
 <span data-ttu-id="9f0a8-135">Gibt an, dass ein XML XDR-Inlineschema zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="9f0a8-136">Das Schema wird dem Dokument als Inlineschema vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="9f0a8-137">Ein funktionierendes Beispiel finden Sie unter [Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="9f0a8-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="9f0a8-139">Gibt ein W3C XML-Inlineschema (XSD) zurück.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="9f0a8-140">Optional können Sie einen Zielnamespace-URI angeben, wenn Sie diese Direktive angeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="9f0a8-141">Auf diese Weise wird der angegebene Namespace im Schema zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="9f0a8-142">Weitere Informationen finden Sie unter [Generieren eines XSD-Inlineschemas](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="9f0a8-143">Ein funktionierendes Beispiel finden Sie unter [Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="9f0a8-144">ELEMENTS</span></span>  
 <span data-ttu-id="9f0a8-145">Wenn die Option ELEMENTS angegeben ist, werden die Spalten als Teilelemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="9f0a8-146">Andernfalls werden sie XML-Attributen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="9f0a8-147">Diese Option wird nur in den Modi RAW, AUTO und PATH unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="9f0a8-148">Optional können Sie XSINIL oder ABSENT angeben, wenn Sie diese Direktive angeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="9f0a8-149">XSINIL gibt an, dass ein Element, dessen **xsi:nil** -Attribut auf True festgelegt ist, für NULL-Spaltenwerte erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="9f0a8-150">Standardmäßig werden keine Elemente für NULL-Werte erstellt. Dies gilt auch, wenn ABSENT zusammen mit ELEMENTS angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="9f0a8-151">Ein funktionierendes Beispiel finden Sie unter [Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md) und unter [Verwenden des AUTO-Modus mit FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="9f0a8-152">BINARY BASE64</span></span>  
 <span data-ttu-id="9f0a8-153">Wenn die Option BINARY Base64 angegeben ist, werden alle von der Abfrage zurückgegebenen Binärdaten im Base64-codierten Format dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="9f0a8-154">Zum Abrufen von Binärdaten mithilfe des Modus RAW oder EXPLICIT muss diese Option angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="9f0a8-155">Standardmäßig werden Binärdaten im AUTO-Modus als Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="9f0a8-156">Ein funktionierendes Beispiel finden Sie unter [Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="9f0a8-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="9f0a8-157">TYPE</span></span>  
 <span data-ttu-id="9f0a8-158">Gibt an, dass die Abfrage die Ergebnisse als **xml** -Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="9f0a8-159">Weitere Informationen finden Sie unter [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9f0a8-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="9f0a8-160">ROOT [('*RootName*')]</span><span class="sxs-lookup"><span data-stu-id="9f0a8-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="9f0a8-161">Gibt an, dass ein einzelnes Element der obersten Ebene dem als Ergebnis zurückgegebenen XML-Dokument hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="9f0a8-162">Optional können Sie den zu generierenden Stammelementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="9f0a8-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="9f0a8-163">Der Standardwert lautet "root".</span><span class="sxs-lookup"><span data-stu-id="9f0a8-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f0a8-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f0a8-164">See Also</span></span>  
 <span data-ttu-id="9f0a8-165">[Verwenden des RAW-Modus mit FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9f0a8-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9f0a8-166">[Verwenden des AUTO-Modus mit FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9f0a8-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9f0a8-167">[Verwenden des EXPLICIT-Modus mit FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9f0a8-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9f0a8-168">[Verwenden des PATH-Modus mit FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9f0a8-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="9f0a8-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9f0a8-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="9f0a8-170">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f0a8-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
