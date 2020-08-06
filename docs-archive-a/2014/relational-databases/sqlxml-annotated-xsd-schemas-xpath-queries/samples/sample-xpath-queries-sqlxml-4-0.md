---
title: XPath-Beispielabfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- examples [SQLXML], XPath
- sample applications [SQLXML]
- sample XPath queries [SQLXML]
- mapping schema [SQLXML], queries
- XPath queries [SQLXML], samples
ms.assetid: 1595c2d4-0e9c-4969-84c8-a793a32df57d
author: rothja
ms.author: jroth
ms.openlocfilehash: 08ed32433e9bed4cc1542d6700ad73dc96f3c2dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608494"
---
# <a name="sample-xpath-queries-sqlxml-40"></a><span data-ttu-id="ab706-102">XPath-Beispielabfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ab706-102">Sample XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="ab706-103">Dieser Abschnitt enthält Beispiele für XPath-Abfragen für SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="ab706-103">This section provides examples of XPath queries for SQLXML 4.0.</span></span> <span data-ttu-id="ab706-104">Zur Veranschaulichung werden diese XPath-Beispielabfragen in einer Vorlage angegeben, die mithilfe von ADO ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab706-104">For illustration purposes, these example XPath queries are specified in a template executed using ADO.</span></span> <span data-ttu-id="ab706-105">Deshalb müssen Sie die Zuordnungsschemadatei SampleSchema1.xml verwenden, die auch in diesem Abschnitt bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ab706-105">Therefore, you must use a mapping schema file, SampleSchema1.xml, which is also provided in this section.</span></span> <span data-ttu-id="ab706-106">Speichern Sie diese Datei in dem Verzeichnis, in dem die Vorlagen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="ab706-106">Save this file in the directory where your templates are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab706-107">Die Beispielabfragen in diesem Abschnitt sind nach dem Typ des von der Abfrage durchgeführten XPath-Vorgangs gruppiert.</span><span class="sxs-lookup"><span data-stu-id="ab706-107">The sample queries in this section are grouped by the type of XPath operation that is performed by the query.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab706-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ab706-108">In This Section</span></span>  
 [<span data-ttu-id="ab706-109">Beispiel-XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-109">Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;</span></span>](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-110">Verwenden Sie diese Datei mit den XPath-Beispielabfragen, die in diesem Abschnitt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ab706-110">Use this file with the XPath query examples provided in this section.</span></span>  
  
 [<span data-ttu-id="ab706-111">Angeben von Achsen in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-111">Specifying Axes in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-axes-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-112">Zeigt, wie Achsen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-112">Illustrates how axes are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-113">Angeben von Prädikaten mit booleschen Werten in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-113">Specifying Boolean-Valued Predicates in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-114">Veranschaulicht, wie Prädikate mit booleschen Werten in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-114">Illustrates how Boolean-valued predicates are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-115">Angeben von relationalen Operatoren in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-115">Specifying Relational Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-relational-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-116">Veranschaulicht, wie relationale Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-116">Illustrates how relational operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-117">Angeben arithmetischer Operatoren in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-117">Specifying Arithmetic Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-arithmetic-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-118">Illustriert, wie arithmetische Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-118">Illustrates how arithmetic operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-119">Angeben von expliziten Konvertierungs Funktionen in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-119">Specifying Explicit Conversion Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-120">Veranschaulicht, wie explizite Konvertierungsfunktionen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-120">Illustrates how explicit conversion functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-121">Angeben von booleschen Operatoren in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-121">Specifying Boolean Operators in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-operators-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-122">Zeigt, wie boolesche Operatoren in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-122">Illustrates how Boolean operators are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-123">Angeben von booleschen Funktionen in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-123">Specifying Boolean Functions in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-boolean-functions-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-124">Zeigt, wie boolesche Funktionen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-124">Illustrates how Boolean functions are specified in XPath queries.</span></span>  
  
 [<span data-ttu-id="ab706-125">Angeben von XPath-Variablen in XPath-Abfragen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ab706-125">Specifying XPath Variables in XPath Queries &#40;SQLXML 4.0&#41;</span></span>](specifying-xpath-variables-in-xpath-queries-sqlxml-4-0.md)  
 <span data-ttu-id="ab706-126">Veranschaulicht, wie XPath-Variablen in XPath-Abfragen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ab706-126">Illustrates how XPath variables are specified in XPath queries.</span></span>  
  
  
