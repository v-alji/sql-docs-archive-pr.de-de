---
title: Angeben von Auswahl Prädikaten im Speicherort Pfad (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618581"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="ddaa9-102">Angeben von Auswahlprädikaten im Speicherortpfad (SQLXML 4.0) </span><span class="sxs-lookup"><span data-stu-id="ddaa9-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="ddaa9-103">Ein Prädikat filtert eine Knotengruppe in Bezug auf eine Achse (ähnlich einer WHERE-Klausel in einer SELECT-Anweisung).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="ddaa9-104">Das Prädikat wird zwischen Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="ddaa9-105">Für jeden Knoten in der zu filternden Knotengruppe wird der Prädikatausdruck mit dem entsprechenden Knoten als Kontextknoten ausgewertet. Die Anzahl der Knoten in der Knotengruppe dient dabei als Kontextgröße.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="ddaa9-106">Ergibt die Auswertung des Prädikatausdrucks für den betreffenden Knoten TRUE, wird dieser Knoten in die resultierende Knotengruppe aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="ddaa9-107">XPath ermöglicht auch die positionsbasierte Filterung.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="ddaa9-108">Ein Prädikatausdruck, der eine Zahl ergibt, wählt diesen Ordinalzahlenknoten aus.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="ddaa9-109">Beispielsweise gibt der Speicherortpfad `Customer[3]` den dritten Kunden zurück.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="ddaa9-110">Solche numerische Prädikate werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="ddaa9-111">Nur Prädikatausdrücke, die ein boolesches Ergebnis zurückgeben, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddaa9-112">Informationen zu den Einschränkungen dieser XPath-Implementierung von XPath und den Unterschieden zwischen der XPath-Implementierung und der W3C-Spezifikation finden Sie unter [Einführung in die Verwendung von XPath-Abfragen &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="ddaa9-113">Auswahl Prädikat: Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="ddaa9-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="ddaa9-114">Der folgende XPath-Ausdruck (Speicherort Pfad) wählt alle untergeordneten Elemente des aktuellen Kontext Knotens aus **\<Customer>** , die das **CustomerID-** Attribut mit dem Wert "ALFKI" aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="ddaa9-115">In dieser XPath-Abfrage sind `child` und `attribute` die Achsennamen.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="ddaa9-116">`Customer`ist der Knoten Test (true `Customer` , wenn ein ist **\<element node>** , da **\<element>** der Haupt Knotentyp für die-Achse ist `child` ).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="ddaa9-117">`attribute::CustomerID="ALFKI"` ist das Prädikat.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="ddaa9-118">Im Prädikat `attribute` ist die Achse und `CustomerID` ist der Knoten Test (true, wenn **CustomerID** ein Attribut des Kontext Knotens ist, da **\<attribute>** der Haupt Knotentyp der `attribute` Achse ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="ddaa9-119">In abgekürzter Syntax kann die XPath-Abfrage auch wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="ddaa9-120">Auswahl Prädikat: Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="ddaa9-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="ddaa9-121">Der folgende XPath-Ausdruck (Speicherort Pfad) wählt alle untergeordneten Knoten aus dem aktuellen Kontext Knoten aus **\<Order>** , die über das **SalesOrderID** -Attribut mit dem Wert 1 verfügen:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="ddaa9-122">In diesem XPath-Ausdruck sind `child` und `attribute` die Achsennamen.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="ddaa9-123">`Customer`, `Order` und `SalesOrderID` sind die Knotentests.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="ddaa9-124">`attribute::OrderID="1"` ist das Prädikat.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="ddaa9-125">In abgekürzter Syntax kann die XPath-Abfrage auch wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="ddaa9-126">Auswahl Prädikat: Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="ddaa9-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="ddaa9-127">Der folgende XPath-Ausdruck (Speicherort Pfad) wählt alle untergeordneten Elemente aus dem aktuellen Kontext Knoten aus **\<Customer>** , die über ein oder mehrere untergeordnete Elemente verfügen **\<ContactName>** :</span><span class="sxs-lookup"><span data-stu-id="ddaa9-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="ddaa9-128">In diesem Beispiel wird davon ausgegangen, dass ein untergeordnetes **\<ContactName>** Element des- **\<Customer>** Elements im XML-Dokument ist, das in einem XSD-Schema mit Anmerkungen als *Element zentrierte Zuordnung* bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="ddaa9-129">In diesem XPath-Ausdruck ist `child` der Achsenname.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="ddaa9-130">`Customer`ist der Knoten Test (true `Customer` , wenn ein- **\<element>** Knoten ist, da **\<element>** der Haupt Knotentyp für die- `child` Achse ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="ddaa9-131">`child::ContactName` ist das Prädikat.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="ddaa9-132">Im Prädikat `child` ist die Achse und `ContactName` ist der Knoten Test (true, wenn `ContactName` ein- **\<element>** Knoten ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="ddaa9-133">Dieser Ausdruck gibt nur die untergeordneten **\<Customer>** Elemente des Kontext Knotens zurück, die über untergeordnete **\<ContactName>** Elemente verfügen.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="ddaa9-134">In abgekürzter Syntax kann die XPath-Abfrage auch wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="ddaa9-135">Auswahl Prädikat: Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="ddaa9-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="ddaa9-136">Der folgende XPath-Ausdruck wählt untergeordnete- **\<Customer>** Elemente des Kontext Knotens aus, die keine untergeordneten **\<ContactName>** Elemente aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="ddaa9-137">In diesem Beispiel wird davon ausgegangen, dass ein untergeordnetes **\<ContactName>** Element des **\<Customer>** -Elements im XML-Dokument ist und das ContactName-Feld in der Datenbank nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="ddaa9-138">In diesem Beispiel ist `child` die Achse.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="ddaa9-139">`Customer`ist der Knoten Test (true, wenn `Customer` ein- \<element> Knoten ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="ddaa9-140">`not(child::ContactName)` ist das Prädikat.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="ddaa9-141">Im Prädikat `child` ist die Achse und `ContactName` ist der Knoten Test (true, wenn `ContactName` ein- \<element> Knoten ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="ddaa9-142">In abgekürzter Syntax kann die XPath-Abfrage auch wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="ddaa9-143">Auswahl Prädikat: Beispiel 5</span><span class="sxs-lookup"><span data-stu-id="ddaa9-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="ddaa9-144">Der folgende XPath-Ausdruck wählt alle untergeordneten Elemente mit **\<Customer>** dem **CustomerID-** Attribut aus dem aktuellen Kontext Knoten aus:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="ddaa9-145">In diesem Beispiel `child` ist die Achse und der `Customer` Knoten Test (true, wenn `Customer` ein- \<element> Knoten ist).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="ddaa9-146">`attribute::CustomerID` ist das Prädikat.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="ddaa9-147">Im Prädikat `attribute` ist die Achse und `CustomerID` das Prädikat (true, wenn ein- `CustomerID` Knoten ist **\<attribute>** ).</span><span class="sxs-lookup"><span data-stu-id="ddaa9-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="ddaa9-148">In abgekürzter Syntax kann die XPath-Abfrage auch wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="ddaa9-149">Auswahlprädikat: Beispiel 6</span><span class="sxs-lookup"><span data-stu-id="ddaa9-149">Selection Predicate: Example 6</span></span>  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="ddaa9-150">SQLXML 4.0 unterstützt XPath-Abfragen mit einem Kreuzprodukt im Prädikat, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ddaa9-150">SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="ddaa9-151">Durch diese Abfrage werden alle Kunden mit einer `Order` ausgewählt, bei der `OrderDate` dem `ShipDate` für eine beliebige `Order`entspricht.</span><span class="sxs-lookup"><span data-stu-id="ddaa9-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddaa9-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddaa9-152">See Also</span></span>  
 <span data-ttu-id="ddaa9-153">[Einführung in XSD-Schemas mit Anmerkungen &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="ddaa9-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="ddaa9-154">Client seitige XML-Formatierung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ddaa9-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
