---
title: Unterstütztes MDX (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- MDX [Analysis Services], statements
- MDX [Analysis Services], functions
ms.assetid: 308bc0b3-4fd6-4435-972b-5e40d9e3c99b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e8df6a2aa6da6b88a07a2abdef99d6ea03d8eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721914"
---
# <a name="supported-mdx-mdx"></a><span data-ttu-id="20f46-102">Unterstütztes MDX (MDX)</span><span class="sxs-lookup"><span data-stu-id="20f46-102">Supported MDX (MDX)</span></span>
  <span data-ttu-id="20f46-103">Die folgenden Anweisungen und Funktionen werden in MDX-Skripts (Multidimensional Expressions) unterstützt:</span><span class="sxs-lookup"><span data-stu-id="20f46-103">The following statements and functions are supported within Multidimensional Expressions (MDX) Script:</span></span>  
  
 [<span data-ttu-id="20f46-104">&#40;Kommentar&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-104">&#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="20f46-105">-- &#40;Kommentar&#41; &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-105">-- &#40;Comment&#41; &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="20f46-106">Kommentar &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-106">Comment &#40;MDX&#41;</span></span>](/sql/mdx/comment-mdx)  
  
 [<span data-ttu-id="20f46-107">ALTER CUBE-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-107">ALTER CUBE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-alter-cube)  
  
> [!NOTE]  
>  <span data-ttu-id="20f46-108">In MDX-Skripts wird nur das Ändern des Standardelements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20f46-108">Only altering the default member is supported in MDX Scripting.</span></span>  
  
 [<span data-ttu-id="20f46-109">CALCULATE-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-109">CALCULATE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-calculate)  
  
 [<span data-ttu-id="20f46-110">CASE-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-110">CASE Statement &#40;MDX&#41;</span></span>](/sql/mdx/case-statement-mdx)  
  
 [<span data-ttu-id="20f46-111">CREATE CELL CALCULATION-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-111">CREATE CELL CALCULATION Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-cell-calculation)  
  
 [<span data-ttu-id="20f46-112">CREATE MEMBER-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-112">CREATE MEMBER Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-member)  
  
 [<span data-ttu-id="20f46-113">CREATE SET-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-113">CREATE SET Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-definition-create-set)  
  
 [<span data-ttu-id="20f46-114">EXISTING-Schlüsselwort &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-114">EXISTING Keyword &#40;MDX&#41;</span></span>](mdx-query-existing-keyword.md)  
  
 [<span data-ttu-id="20f46-115">FREEZE-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-115">FREEZE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-freeze)  
  
 [<span data-ttu-id="20f46-116">IF-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-116">IF Statement  &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-if)  
  
 [<span data-ttu-id="20f46-117">This &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-117">This &#40;MDX&#41;</span></span>](/sql/mdx/this-mdx)  
  
> [!NOTE]  
>  <span data-ttu-id="20f46-118">MDX unterstützt Zuweisungen für folgende Zelleigenschaften: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME` und `FONT_SIZE`.</span><span class="sxs-lookup"><span data-stu-id="20f46-118">MDX supports assignment to the following cell properties: `BACK_COLOR`, `FORE_COLOR`, `FORMAT_STRING`, `FONT_FLAGS`, `FONT_NAME`, and `FONT_SIZE`.</span></span> <span data-ttu-id="20f46-119">Weitere Informationen finden Sie unter [Verwenden von Zelleigenschaften &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="20f46-119">For more information, see [Using Cell Properties &#40;MDX&#41;](mdx-cell-properties-using-cell-properties.md).</span></span> <span data-ttu-id="20f46-120">MDX unterstützt auch die Zuweisung zur- `NON_EMPTY_BEHAVIOR` Eigenschaft der [Create Member](/sql/mdx/mdx-data-definition-create-member) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="20f46-120">MDX also supports assignment to the `NON_EMPTY_BEHAVIOR` property of the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span>  
  
 [<span data-ttu-id="20f46-121">SCOPE-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-121">SCOPE Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-scripting-scope)  
  
## <a name="see-also"></a><span data-ttu-id="20f46-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20f46-122">See Also</span></span>  
 [<span data-ttu-id="20f46-123">Grundlegendes MDX-Skript &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="20f46-123">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)  
  
  
