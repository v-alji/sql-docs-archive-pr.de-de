---
title: Syntax für Elementpfade für XML-Berichtsdaten (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726561"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="2639b-102">Syntax für Elementpfade für XML-Berichtsdaten (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2639b-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="2639b-103">Im Berichts-Designer geben Sie die Daten, die für einen Bericht aus einer XML-Datenquelle verwendet werden sollen, durch Definieren eines Elementpfades (mit Unterscheidung von Groß-/Kleinschreibung) an.</span><span class="sxs-lookup"><span data-stu-id="2639b-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="2639b-104">Mit einem Elementpfad wird angegeben, wie die hierarchischen XML-Knoten und ihre Attribute in der XML-Datenquelle durchsucht werden können.</span><span class="sxs-lookup"><span data-stu-id="2639b-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="2639b-105">Lassen Sie die Datasetabfrage oder den XML-`ElementPath` der XML-`Query` leer, um den Standardelementpfad zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2639b-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="2639b-106">Wenn Daten aus der XML-Datenquelle abgerufen werden, werden Elementknoten mit Textwerten und Elementknotenattribute im Resultset zu Spalten.</span><span class="sxs-lookup"><span data-stu-id="2639b-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="2639b-107">Die Werte der Knoten und Attribute werden beim Ausführen der Abfrage zu Zeilendaten.</span><span class="sxs-lookup"><span data-stu-id="2639b-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="2639b-108">Die Spalten werden als Datasetfeldauflistung im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2639b-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="2639b-109">In diesem Thema wird die Syntax für Elementpfade beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2639b-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2639b-110">Die Syntax von Elementpfaden ist nicht vom Namespace abhängig.</span><span class="sxs-lookup"><span data-stu-id="2639b-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="2639b-111">Um Namespaces in einem Element Pfad zu verwenden, verwenden Sie die XML-Abfrage Syntax, die ein XML-Element enthält, das `ElementPath` in [XML Query-Syntax für XML-Berichtsdaten &#40;SSRS-&#41;](report-data-ssrs.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2639b-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="2639b-112">In der folgenden Tabelle werden Konventionen für das Definieren eines Elementpfades beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2639b-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="2639b-113">Konvention</span><span class="sxs-lookup"><span data-stu-id="2639b-113">Convention</span></span>|<span data-ttu-id="2639b-114">Syntaxelemente</span><span class="sxs-lookup"><span data-stu-id="2639b-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="2639b-115">**Fett**</span><span class="sxs-lookup"><span data-stu-id="2639b-115">**bold**</span></span>|<span data-ttu-id="2639b-116">Text, der genau so geschrieben werden muss wie dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2639b-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="2639b-117">&#124; (senkrechter Strich)</span><span class="sxs-lookup"><span data-stu-id="2639b-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="2639b-118">Trennt Syntaxelemente voneinander.</span><span class="sxs-lookup"><span data-stu-id="2639b-118">Separates syntax items.</span></span> <span data-ttu-id="2639b-119">Sie können nur eines der Elemente auswählen.</span><span class="sxs-lookup"><span data-stu-id="2639b-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="2639b-120">Optionale Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="2639b-120">Optional syntax items.</span></span> <span data-ttu-id="2639b-121">Geben Sie die eckigen Klammern nicht mit ein.</span><span class="sxs-lookup"><span data-stu-id="2639b-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="2639b-122">**{}** (geschweifte Klammern)</span><span class="sxs-lookup"><span data-stu-id="2639b-122">**{ }** (braces)</span></span>|<span data-ttu-id="2639b-123">Begrenzt Parameter für Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="2639b-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="2639b-124">[ **,** ...*n*]</span><span class="sxs-lookup"><span data-stu-id="2639b-124">[**,**...*n*]</span></span>|<span data-ttu-id="2639b-125">Zeigt an, dass das vorherige Element *n* -mal wiederholt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2639b-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="2639b-126">Die einzelnen Vorkommen werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="2639b-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="2639b-127">Syntax</span><span class="sxs-lookup"><span data-stu-id="2639b-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="2639b-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2639b-128">Remarks</span></span>  
 <span data-ttu-id="2639b-129">In der folgenden Tabelle sind Begriffe für Pfadelemente zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="2639b-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="2639b-130">Die Beispiele in der Tabelle beziehen sich auf das XML-Beispieldokument Customers.xml, das im Abschnitt mit Beispielen in diesem Thema enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2639b-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2639b-131">Bei XML-Tags wird zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="2639b-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="2639b-132">Wenn Sie im Elementpfad einen Elementknoten (ElementNode) angeben, müssen die XML-Tags in der Datenquelle genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2639b-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="2639b-133">Begriff</span><span class="sxs-lookup"><span data-stu-id="2639b-133">Term</span></span>|<span data-ttu-id="2639b-134">Definition</span><span class="sxs-lookup"><span data-stu-id="2639b-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2639b-135">Elementpfad</span><span class="sxs-lookup"><span data-stu-id="2639b-135">Element path</span></span>|<span data-ttu-id="2639b-136">Definiert die zu durchsuchende Sequenz von Knoten im XML-Dokument, um Felddaten für ein Dataset mit einer XML-Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2639b-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="2639b-137">Der XML-Knoten im XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="2639b-137">The XML node in the XML document.</span></span> <span data-ttu-id="2639b-138">Knoten werden durch Tags gekennzeichnet und sind in einer hierarchischen Beziehung mit anderen Knoten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2639b-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="2639b-139">Beispielsweise \<Customers> ist der Stamm Elementknoten.</span><span class="sxs-lookup"><span data-stu-id="2639b-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="2639b-140">\<Customer>ist ein untergeordnetes Element von \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="2639b-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="2639b-141">Der Name des Knotens.</span><span class="sxs-lookup"><span data-stu-id="2639b-141">The name of the node.</span></span> <span data-ttu-id="2639b-142">Der Name des Knotens Customers ist beispielsweise Customers.</span><span class="sxs-lookup"><span data-stu-id="2639b-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="2639b-143">Für `XMLName` kann ein Namespacebezeichner als Präfix verwendet werden, um jeden Knoten eindeutig zu benennen.</span><span class="sxs-lookup"><span data-stu-id="2639b-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="2639b-144">Gibt an, dass der `Value` für dieses Element codiertes XML darstellt und decodiert werden sowie als untergeordnetes Element dieses Elements aufgenommen muss.</span><span class="sxs-lookup"><span data-stu-id="2639b-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="2639b-145">Definiert eine Gruppe von Elementen und Attributen, die zum Abrufen von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2639b-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="2639b-146">Wenn dieses Element nicht angegeben wird, werden alle Attribute und untergeordneten Elemente als Felder verwendet.</span><span class="sxs-lookup"><span data-stu-id="2639b-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="2639b-147">Wenn die leere Feldliste angegeben wird ( **{}** ), werden keine Felder von diesem Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="2639b-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="2639b-148">Eine `FieldList` kann nicht gleichzeitig einen `Value` und ein `Element` oder einen `ElementNode` enthalten.</span><span class="sxs-lookup"><span data-stu-id="2639b-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="2639b-149">Gibt die Daten an, die als Datasetfeld abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2639b-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="2639b-150">Ein Name/Wert-Paar im `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="2639b-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="2639b-151">Beispielsweise ist im-Elementknoten \<Customer ID="1"> `ID` ein Attribut und `@ID(Integer)` gibt "1" als ganzzahligen Typ im entsprechenden Datenfeld zurück `ID` .</span><span class="sxs-lookup"><span data-stu-id="2639b-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="2639b-152">Der Wert des Elements.</span><span class="sxs-lookup"><span data-stu-id="2639b-152">The value of the element.</span></span> <span data-ttu-id="2639b-153">`Value` kann nur für den letzten `ElementNode` im Elementpfad verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2639b-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="2639b-154">Da z. b \<Return> . ein Blattknoten ist, wenn Sie ihn am Ende eines Element Pfads einschließen, ist der Wert `Return {@}` von `Chair` .</span><span class="sxs-lookup"><span data-stu-id="2639b-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="2639b-155">Der Wert des benannten untergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="2639b-155">The value of the named subelement.</span></span> <span data-ttu-id="2639b-156">Beispielsweise werden mithilfe von Customers {}/Customer {}/LastName nur Werte für das LastName-Element abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2639b-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="2639b-157">Der optionale Datentyp, der für das aus diesem Element erstellte Feld zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="2639b-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="2639b-158">`NamespacePrefix` wird im XML-Abfrageelement definiert.</span><span class="sxs-lookup"><span data-stu-id="2639b-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="2639b-159">Wenn kein XML-Abfrageelement vorhanden ist, werden Namespaces im XML-`ElementPath` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2639b-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="2639b-160">Wenn ein XML-Abfrageelement vorhanden ist, verfügt der XML-`ElementPath` über das optionale Attribut `IgnoreNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="2639b-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="2639b-161">Wenn IgnoreNamespaces ist `true` , werden Namespaces im XML `ElementPath` -und XML-Dokument ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2639b-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="2639b-162">Weitere Informationen finden Sie unter [XML-Abfragesyntax für XML-Berichtsdaten (SSRS)](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2639b-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="2639b-163">Beispiel – Keine Namespaces</span><span class="sxs-lookup"><span data-stu-id="2639b-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="2639b-164">In den folgenden Beispiele wird das XML-Dokument "Customers.xml" verwendet.</span><span class="sxs-lookup"><span data-stu-id="2639b-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="2639b-165">Diese Tabelle zeigt Beispiele zur Syntax von Elementpfaden und die Ergebnisse beim Verwenden des Elementpfades in einer Abfrage an, die ein Dataset anhand eines als Datenquelle dienenden XML-Dokuments definiert.</span><span class="sxs-lookup"><span data-stu-id="2639b-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="2639b-166">Beachten Sie Folgendes: Wenn der Element Pfad leer ist, wird in der Abfrage der Standardelement Pfad verwendet: der erste Pfad zu einer Blattknoten Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2639b-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="2639b-167">Im ersten Beispiel entspricht das Leerlassen des Elementpfades dem Angeben des Elementpfades /Customers/Customer/Orders/Order.</span><span class="sxs-lookup"><span data-stu-id="2639b-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="2639b-168">Alle Knotenwerte und -attribute entlang dieses Pfades werden im Resultset zurückgegeben, und die Knotennamen und -attribute werden als Datasetfelder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2639b-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="2639b-169">*Leer*</span><span class="sxs-lookup"><span data-stu-id="2639b-169">*Empty*</span></span>  
  
    |<span data-ttu-id="2639b-170">Order</span><span class="sxs-lookup"><span data-stu-id="2639b-170">Order</span></span>|<span data-ttu-id="2639b-171">Qty (Menge)</span><span class="sxs-lookup"><span data-stu-id="2639b-171">Qty</span></span>|<span data-ttu-id="2639b-172">id</span><span class="sxs-lookup"><span data-stu-id="2639b-172">ID</span></span>|<span data-ttu-id="2639b-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="2639b-173">FirstName</span></span>|<span data-ttu-id="2639b-174">LastName</span><span class="sxs-lookup"><span data-stu-id="2639b-174">LastName</span></span>|<span data-ttu-id="2639b-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="2639b-175">Customer.ID</span></span>|<span data-ttu-id="2639b-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="2639b-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="2639b-177">Chair</span><span class="sxs-lookup"><span data-stu-id="2639b-177">Chair</span></span>|<span data-ttu-id="2639b-178">6</span><span class="sxs-lookup"><span data-stu-id="2639b-178">6</span></span>|<span data-ttu-id="2639b-179">1</span><span class="sxs-lookup"><span data-stu-id="2639b-179">1</span></span>|<span data-ttu-id="2639b-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="2639b-180">Bobby</span></span>|<span data-ttu-id="2639b-181">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-181">Moore</span></span>|<span data-ttu-id="2639b-182">11</span><span class="sxs-lookup"><span data-stu-id="2639b-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2639b-183">Tabelle</span><span class="sxs-lookup"><span data-stu-id="2639b-183">Table</span></span>|<span data-ttu-id="2639b-184">1</span><span class="sxs-lookup"><span data-stu-id="2639b-184">1</span></span>|<span data-ttu-id="2639b-185">2</span><span class="sxs-lookup"><span data-stu-id="2639b-185">2</span></span>|<span data-ttu-id="2639b-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="2639b-186">Bobby</span></span>|<span data-ttu-id="2639b-187">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-187">Moore</span></span>|<span data-ttu-id="2639b-188">11</span><span class="sxs-lookup"><span data-stu-id="2639b-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2639b-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="2639b-189">Sofa</span></span>|<span data-ttu-id="2639b-190">2</span><span class="sxs-lookup"><span data-stu-id="2639b-190">2</span></span>|<span data-ttu-id="2639b-191">8</span><span class="sxs-lookup"><span data-stu-id="2639b-191">8</span></span>|<span data-ttu-id="2639b-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="2639b-192">Crystal</span></span>|<span data-ttu-id="2639b-193">Hu</span><span class="sxs-lookup"><span data-stu-id="2639b-193">Hu</span></span>|<span data-ttu-id="2639b-194">20</span><span class="sxs-lookup"><span data-stu-id="2639b-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="2639b-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="2639b-195">EndTables</span></span>|<span data-ttu-id="2639b-196">2</span><span class="sxs-lookup"><span data-stu-id="2639b-196">2</span></span>|<span data-ttu-id="2639b-197">15</span><span class="sxs-lookup"><span data-stu-id="2639b-197">15</span></span>|<span data-ttu-id="2639b-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2639b-198">Wyatt</span></span>|<span data-ttu-id="2639b-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="2639b-199">Diaz</span></span>|<span data-ttu-id="2639b-200">33</span><span class="sxs-lookup"><span data-stu-id="2639b-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="2639b-201">FirstName</span><span class="sxs-lookup"><span data-stu-id="2639b-201">FirstName</span></span>|<span data-ttu-id="2639b-202">LastName</span><span class="sxs-lookup"><span data-stu-id="2639b-202">LastName</span></span>|<span data-ttu-id="2639b-203">id</span><span class="sxs-lookup"><span data-stu-id="2639b-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="2639b-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="2639b-204">Bobby</span></span>|<span data-ttu-id="2639b-205">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-205">Moore</span></span>|<span data-ttu-id="2639b-206">11</span><span class="sxs-lookup"><span data-stu-id="2639b-206">11</span></span>|  
    |<span data-ttu-id="2639b-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="2639b-207">Crystal</span></span>|<span data-ttu-id="2639b-208">Hu</span><span class="sxs-lookup"><span data-stu-id="2639b-208">Hu</span></span>|<span data-ttu-id="2639b-209">20</span><span class="sxs-lookup"><span data-stu-id="2639b-209">20</span></span>|  
    |<span data-ttu-id="2639b-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2639b-210">Wyatt</span></span>|<span data-ttu-id="2639b-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="2639b-211">Diaz</span></span>|<span data-ttu-id="2639b-212">33</span><span class="sxs-lookup"><span data-stu-id="2639b-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="2639b-213">LastName</span><span class="sxs-lookup"><span data-stu-id="2639b-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="2639b-214">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-214">Moore</span></span>|  
    |<span data-ttu-id="2639b-215">Hu</span><span class="sxs-lookup"><span data-stu-id="2639b-215">Hu</span></span>|  
    |<span data-ttu-id="2639b-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="2639b-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="2639b-217">Order</span><span class="sxs-lookup"><span data-stu-id="2639b-217">Order</span></span>|<span data-ttu-id="2639b-218">Qty (Menge)</span><span class="sxs-lookup"><span data-stu-id="2639b-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="2639b-219">Chair</span><span class="sxs-lookup"><span data-stu-id="2639b-219">Chair</span></span>|<span data-ttu-id="2639b-220">6</span><span class="sxs-lookup"><span data-stu-id="2639b-220">6</span></span>|  
    |<span data-ttu-id="2639b-221">Tabelle</span><span class="sxs-lookup"><span data-stu-id="2639b-221">Table</span></span>|<span data-ttu-id="2639b-222">1</span><span class="sxs-lookup"><span data-stu-id="2639b-222">1</span></span>|  
    |<span data-ttu-id="2639b-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="2639b-223">Sofa</span></span>|<span data-ttu-id="2639b-224">2</span><span class="sxs-lookup"><span data-stu-id="2639b-224">2</span></span>|  
    |<span data-ttu-id="2639b-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="2639b-225">EndTables</span></span>|<span data-ttu-id="2639b-226">2</span><span class="sxs-lookup"><span data-stu-id="2639b-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="2639b-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="2639b-227">Order.ID</span></span>|<span data-ttu-id="2639b-228">FirstName</span><span class="sxs-lookup"><span data-stu-id="2639b-228">FirstName</span></span>|<span data-ttu-id="2639b-229">LastName</span><span class="sxs-lookup"><span data-stu-id="2639b-229">LastName</span></span>|<span data-ttu-id="2639b-230">id</span><span class="sxs-lookup"><span data-stu-id="2639b-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="2639b-231">1</span><span class="sxs-lookup"><span data-stu-id="2639b-231">1</span></span>|<span data-ttu-id="2639b-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="2639b-232">Bobby</span></span>|<span data-ttu-id="2639b-233">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-233">Moore</span></span>|<span data-ttu-id="2639b-234">11</span><span class="sxs-lookup"><span data-stu-id="2639b-234">11</span></span>|  
    |<span data-ttu-id="2639b-235">2</span><span class="sxs-lookup"><span data-stu-id="2639b-235">2</span></span>|<span data-ttu-id="2639b-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="2639b-236">Bobby</span></span>|<span data-ttu-id="2639b-237">Moore</span><span class="sxs-lookup"><span data-stu-id="2639b-237">Moore</span></span>|<span data-ttu-id="2639b-238">11</span><span class="sxs-lookup"><span data-stu-id="2639b-238">11</span></span>|  
    |<span data-ttu-id="2639b-239">8</span><span class="sxs-lookup"><span data-stu-id="2639b-239">8</span></span>|<span data-ttu-id="2639b-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="2639b-240">Crystal</span></span>|<span data-ttu-id="2639b-241">Hu</span><span class="sxs-lookup"><span data-stu-id="2639b-241">Hu</span></span>|<span data-ttu-id="2639b-242">20</span><span class="sxs-lookup"><span data-stu-id="2639b-242">20</span></span>|  
    |<span data-ttu-id="2639b-243">15</span><span class="sxs-lookup"><span data-stu-id="2639b-243">15</span></span>|<span data-ttu-id="2639b-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="2639b-244">Wyatt</span></span>|<span data-ttu-id="2639b-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="2639b-245">Diaz</span></span>|<span data-ttu-id="2639b-246">33</span><span class="sxs-lookup"><span data-stu-id="2639b-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="2639b-247">XML-Dokument: Customers.xml</span><span class="sxs-lookup"><span data-stu-id="2639b-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="2639b-248">Um die Elementpfadbeispiele im vorherigen Abschnitt auszuprobieren, können Sie dieses XML-Dokument kopieren und unter einer URL speichern, auf die der Berichts-Designer zugreifen kann. Anschließend können Sie das XML-Dokument als XML-Datenquelle verwenden: z. B. `http://localhost/Customers.xml`</span><span class="sxs-lookup"><span data-stu-id="2639b-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="2639b-249">Sie können auch eine XML-Datenquelle ohne Verbindungszeichenfolge erstellen und Customers.XML in die Abfrage einbetten. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2639b-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="2639b-250">So betten Sie Customers.XML in einer Abfrage ein</span><span class="sxs-lookup"><span data-stu-id="2639b-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="2639b-251">Erstellen Sie eine XML-Datenquelle mit einer leeren Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2639b-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="2639b-252">Erstellen Sie ein neues Dataset für die XML-Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="2639b-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="2639b-253">Klicken Sie im Dialogfeld **Dataseteigenschaften** auf **Abfrage-Designer**.</span><span class="sxs-lookup"><span data-stu-id="2639b-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="2639b-254">Das textbasierte Dialogfeld des Abfrage-Designers wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2639b-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="2639b-255">Geben Sie die folgenden Zeilen im Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="2639b-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="2639b-256">Kopieren Sie die Datei Customers.XML, und fügen Sie den Text im Abfragebereich nach der Zeile `<XmlData>`ein.</span><span class="sxs-lookup"><span data-stu-id="2639b-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="2639b-257">Löschen Sie im Abfragebereich die erste Zeile, die Sie aus der Datei Customers.XML kopiert haben: `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="2639b-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="2639b-258">Fügen Sie am Ende der Abfrage die beiden folgenden Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="2639b-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="2639b-259">Klicken Sie auf **Abfrage ausführen** (!).</span><span class="sxs-lookup"><span data-stu-id="2639b-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="2639b-260">Das Resultset zeigt vier Datenzeilen mit den folgenden Spalten an: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`</span><span class="sxs-lookup"><span data-stu-id="2639b-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2639b-261">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2639b-261">See Also</span></span>  
 <span data-ttu-id="2639b-262">[XML-Verbindungstyp &#40;SSRS-&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2639b-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="2639b-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2639b-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="2639b-264">Hinzufügen, Bearbeiten und Aktualisieren von Feldern im Berichtsdatenbereich &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2639b-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
