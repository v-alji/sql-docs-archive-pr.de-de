---
title: Angeben eines Knoten Tests im Speicherort Pfad (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], location paths
- principal node types [SQLXML]
- node tests [SQLXML]
- location path for XPath query
ms.assetid: f46c30bf-1e24-4435-9ac2-f8ba43a8ff94
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d8535154f4b481c8a47bfdb8b801e3136a1ef0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618586"
---
# <a name="specifying-a-node-test-in-the-location-path-sqlxml-40"></a><span data-ttu-id="20cbf-102">Angeben eines Knotentests unter dem Speicherortpfad (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="20cbf-102">Specifying a Node Test in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="20cbf-103">Ein Knotentest gibt den vom Positionsschritt ausgewählten Knotentyp an.</span><span class="sxs-lookup"><span data-stu-id="20cbf-103">A node test specifies the node type selected by the location step.</span></span> <span data-ttu-id="20cbf-104">Jede Achse ( `child` , `parent` , `attribute` oder `self` ) hat einen Prinzipal Knotentyp.</span><span class="sxs-lookup"><span data-stu-id="20cbf-104">Every axis (`child`, `parent`, `attribute`, or `self`) has a principal node type.</span></span> <span data-ttu-id="20cbf-105">Für die- `attribute` Achse ist der Haupt Knotentyp **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="20cbf-105">For the `attribute` axis, the principal node type is **\<attribute>**.</span></span> <span data-ttu-id="20cbf-106">Für die `parent` `child` Achsen, und `self` ist der Haupt Knotentyp **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="20cbf-106">For the `parent`, `child`, and `self` axes, the principal node type is **\<element>**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20cbf-107">Der Platzhalterknotentest \* (z. B. `child::*`) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20cbf-107">The wildcard node test \* (for example, `child::*`) is not supported.</span></span>  
  
## <a name="node-test-example-1"></a><span data-ttu-id="20cbf-108">Knoten Test: Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="20cbf-108">Node Test: Example 1</span></span>  
 <span data-ttu-id="20cbf-109">Der Speicherort Pfad wählt untergeordnete `child::Customer` **\<Customer>** Elemente des Kontext Knotens aus.</span><span class="sxs-lookup"><span data-stu-id="20cbf-109">The location path `child::Customer` selects **\<Customer>** element children of the context node.</span></span>  
  
 <span data-ttu-id="20cbf-110">In diesem Beispiel ist `child` die Achse, und `Customer` ist der Knotentest.</span><span class="sxs-lookup"><span data-stu-id="20cbf-110">In this example, `child` is the axis and `Customer` is the node test.</span></span> <span data-ttu-id="20cbf-111">Der Haupt Knotentyp für die- `child` Achse ist **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="20cbf-111">The principal node type for the `child` axis is **\<element>**.</span></span> <span data-ttu-id="20cbf-112">Daher ist der Knoten Test true, wenn der **\<Customer>** Knoten ein- **\<element>** Knoten ist.</span><span class="sxs-lookup"><span data-stu-id="20cbf-112">Therefore, the node test is TRUE if the **\<Customer>** node is an **\<element>** node.</span></span> <span data-ttu-id="20cbf-113">Wenn der Kontext Knoten keine untergeordneten Elemente besitzt **\<Customer>** , wird eine leere Gruppe von Knoten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20cbf-113">If the context node has no **\<Customer>** children, an empty set of nodes is returned.</span></span>  
  
## <a name="node-test-example-2"></a><span data-ttu-id="20cbf-114">Knotentest: Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="20cbf-114">Node Test: Example 2</span></span>  
 <span data-ttu-id="20cbf-115">Der Speicherort Pfad `attribute::CustomerID` wählt das **CustomerID-** Attribut des Kontext Knotens aus.</span><span class="sxs-lookup"><span data-stu-id="20cbf-115">The location path `attribute::CustomerID` selects the **CustomerID** attribute of the context node.</span></span>  
  
 <span data-ttu-id="20cbf-116">Im Beispiel ist `attribute` die Achse, und `CustomerID` ist der Knotentest.</span><span class="sxs-lookup"><span data-stu-id="20cbf-116">In the example, `attribute` is the axis and `CustomerID` is the node test.</span></span> <span data-ttu-id="20cbf-117">Der Haupt Knotentyp der `attribute` Achse ist **\<attribute>** .</span><span class="sxs-lookup"><span data-stu-id="20cbf-117">The principal node type of the `attribute` axis is **\<attribute>**.</span></span> <span data-ttu-id="20cbf-118">Daher ist der Knoten Test true, wenn **CustomerID** ein **\<attribute>** Knoten ist.</span><span class="sxs-lookup"><span data-stu-id="20cbf-118">Therefore, the node test is TRUE if **CustomerID** is an **\<attribute>** node.</span></span> <span data-ttu-id="20cbf-119">Wenn der Kontext Knoten über keine **CustomerID**verfügt, wird ein leerer Knoten Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20cbf-119">If the context node has no **CustomerID**, an empty set of nodes is returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20cbf-120">In dieser Implementierung von XPath wird ein Fehler generiert, wenn ein Location-Step auf einen **\<element>** oder einen Typ verweist, **\<attribute>** der nicht im Schema deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="20cbf-120">In this implementation of XPath, if a location step refers to an **\<element>** or an **\<attribute>** type that is not declared in the schema, an error is generated.</span></span> <span data-ttu-id="20cbf-121">Dies unterscheidet sich von der Implementierung von XPath in MSXML, bei der ein leerer Knotensatz zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="20cbf-121">This is different from the implementation of XPath in MSXML, which returns an empty node set.</span></span>  
  
## <a name="abbreviated-syntax-for-the-axes"></a><span data-ttu-id="20cbf-122">Abgekürzte Syntax für die Achsen</span><span class="sxs-lookup"><span data-stu-id="20cbf-122">Abbreviated Syntax for the Axes</span></span>  
 <span data-ttu-id="20cbf-123">Es wird die folgende abgekürzte Syntax für den Speicherortpfad unterstützt:</span><span class="sxs-lookup"><span data-stu-id="20cbf-123">The following abbreviated syntax for the location path is supported:</span></span>  
  
-   <span data-ttu-id="20cbf-124">`attribute::` kann als `@` abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="20cbf-124">`attribute::` can be abbreviated to `@`.</span></span>  
  
     <span data-ttu-id="20cbf-125">Der Speicherortpfad `Customer[@CustomerID="ALFKI"]` entspricht `child::Customer[attribute::CustomerID="ALFKI"]`.</span><span class="sxs-lookup"><span data-stu-id="20cbf-125">The location path `Customer[@CustomerID="ALFKI"]` is the same as `child::Customer[attribute::CustomerID="ALFKI"]`.</span></span>  
  
-   <span data-ttu-id="20cbf-126">`child::` kann von einem Speicherortschritt ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="20cbf-126">`child::` can be omitted from a location step.</span></span>  
  
     <span data-ttu-id="20cbf-127">Daher ist `child` die Standardachse.</span><span class="sxs-lookup"><span data-stu-id="20cbf-127">Thus, `child` is the default axis.</span></span> <span data-ttu-id="20cbf-128">Der Speicherortpfad `Customer/Order` entspricht `child::Customer/child::Order`.</span><span class="sxs-lookup"><span data-stu-id="20cbf-128">The location path `Customer/Order` is the same as `child::Customer/child::Order`.</span></span>  
  
-   <span data-ttu-id="20cbf-129">`self::node()` kann zu einem Punkt (.) abgekürzt werden, und `parent::node()` kann zu zwei Punkten (..) abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="20cbf-129">`self::node()` can be abbreviated to one period (.), and `parent::node()` can be abbreviated to two periods (..).</span></span>  
  
  
