---
title: Angeben einer Achse (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- XPath queries [SQLXML], location paths
- self axis
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- location path for XPath query
- axes [SQLXML]
ms.assetid: 65631795-3389-40cf-90ea-85e9438956c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e43281fe31d323a7eea19e749b80b59458752b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618584"
---
# <a name="specifying-an-axis-sqlxml-40"></a><span data-ttu-id="7c3f7-102">Angeben einer Achse (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7c3f7-102">Specifying an Axis (SQLXML 4.0)</span></span>
    
-   <span data-ttu-id="7c3f7-103">Die Achse gibt die Strukturbeziehung zwischen den vom Positionsschritt ausgewählten Knoten und dem Kontextknoten an.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-103">The axis specifies the tree relationship between the nodes selected by the location step and the context node.</span></span> <span data-ttu-id="7c3f7-104">Die folgenden Achsen werden unterstützt: `child`</span><span class="sxs-lookup"><span data-stu-id="7c3f7-104">The following axes are supported:  `child`</span></span>  
  
     <span data-ttu-id="7c3f7-105">Enthält das untergeordnete Element des Kontextknotens.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-105">Contains the child of the context node.</span></span>  
  
     <span data-ttu-id="7c3f7-106">Der folgende XPath-Ausdruck (Speicherort Pfad) wählt alle untergeordneten Elemente aus dem aktuellen Kontext Knoten aus **\<Customer>** :</span><span class="sxs-lookup"><span data-stu-id="7c3f7-106">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children:</span></span>  
  
    ```  
    child::Customer  
    ```  
  
     <span data-ttu-id="7c3f7-107">In der folgenden XPath-Abfrage ist `child` die Achse.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-107">In the following XPath query, `child` is the axis.</span></span> <span data-ttu-id="7c3f7-108">`Customer` ist der Knotentest.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-108">`Customer` is the node test.</span></span>  
  
-   `parent`  
  
     <span data-ttu-id="7c3f7-109">Enthält das übergeordnete Element des Kontextknotens.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-109">Contains the parent of the context node.</span></span>  
  
     <span data-ttu-id="7c3f7-110">Der folgende XPath-Ausdruck wählt alle **\<Customer>** übergeordneten Elemente der untergeordneten Elemente aus **\<Order>** :</span><span class="sxs-lookup"><span data-stu-id="7c3f7-110">The following XPath expression selects all the **\<Customer>** parents of the **\<Order>** children:</span></span>  
  
    ```  
    child::Customer/child::Order[parent::Customer/@customerID="ALFKI"]  
    ```  
  
     <span data-ttu-id="7c3f7-111">Dies entspricht exakt der Angabe `child::Customer`.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-111">This is the same as specifying `child::Customer`.</span></span> <span data-ttu-id="7c3f7-112">In dieser XPath-Abfrage sind `child` und `parent` die Achsen.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-112">In this XPath query, `child` and `parent` are the axes.</span></span> <span data-ttu-id="7c3f7-113">`Customer` und `Order` sind die Knotentests.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-113">`Customer` and `Order` are the node tests.</span></span>  
  
-   `attribute`  
  
     <span data-ttu-id="7c3f7-114">Enthält das Attribut des Kontextknotens.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-114">Contains the attribute of the context node.</span></span>  
  
     <span data-ttu-id="7c3f7-115">Der folgende XPath-Ausdruck wählt das **CustomerID-** Attribut des Kontext Knotens aus:</span><span class="sxs-lookup"><span data-stu-id="7c3f7-115">The following XPath expression selects the **CustomerID** attribute of the context node:</span></span>  
  
    ```  
    attribute::CustomerID  
    ```  
  
-   `self`  
  
     <span data-ttu-id="7c3f7-116">Enthält den Kontextknoten selbst.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-116">Contains the context node itself.</span></span>  
  
     <span data-ttu-id="7c3f7-117">Der folgende XPath-Ausdruck wählt den aktuellen Knoten aus, wenn er der **\<Order>** Knoten ist:</span><span class="sxs-lookup"><span data-stu-id="7c3f7-117">The following XPath expression selects the current node if it is the **\<Order>** node:</span></span>  
  
    ```  
    self::Order  
    ```  
  
     <span data-ttu-id="7c3f7-118">In dieser XPath-Abfrage ist `self` die Achse und `Order` der Knotentest.</span><span class="sxs-lookup"><span data-stu-id="7c3f7-118">In this XPath query, `self` is the axis and `Order` is the node test.</span></span>  
  
  
