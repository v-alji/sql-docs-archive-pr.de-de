---
title: Vorhandenes Schlüsselwort (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608887"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="92476-102">EXISTING-Schlüsselwort (MDX)</span><span class="sxs-lookup"><span data-stu-id="92476-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="92476-103">Erzwingt die Auswertung einer angegebenen Menge im aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="92476-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92476-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92476-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="92476-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="92476-105">Arguments</span></span>  
 <span data-ttu-id="92476-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="92476-106">*Set_Expression*</span></span>  
 <span data-ttu-id="92476-107">Ein gültiger MDX-Mengenausdruck (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="92476-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92476-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="92476-108">Remarks</span></span>  
 <span data-ttu-id="92476-109">Standardmäßig werden Mengen im Kontext des Cubes ausgewertet, der die Elemente der Menge enthält.</span><span class="sxs-lookup"><span data-stu-id="92476-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="92476-110">Das `Existing`-Schlüsselwort erzwingt dagegen die Auswertung einer angegebenen Menge im aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="92476-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92476-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92476-111">Example</span></span>  
 <span data-ttu-id="92476-112">Im folgenden Beispiel wird die Anzahl der Wiederverkäufer, deren Umsätze im vergangenen Zeitraum zurückgegangen sind, basierend auf vom Benutzer ausgewählten State-Province-Elementwerten zurückgegeben, die mit der `Aggregate`-Funktion ausgewertet wurden.</span><span class="sxs-lookup"><span data-stu-id="92476-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="92476-113">Das [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) und [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) werden zum Zurückgeben von Werten für zurückgegangene Umsätze in Produktkategorien der Product-Dimension verwendet.</span><span class="sxs-lookup"><span data-stu-id="92476-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="92476-114">Das `Existing` -Schlüsselwort erzwingt die Auswertung der Menge in der `Filter` Funktion im aktuellen Kontext, d. h. für die Washington-und Oregon-Elemente der State-Province-Attribut Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="92476-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="92476-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92476-115">See Also</span></span>  
 <span data-ttu-id="92476-116">[Anzahl &#40;fest geleg&#41; &#40;MDX-&#41;](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="92476-117">[AddCalculatedMembers &#40;MDX-&#41;](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="92476-118">[&#40;MDX-&#41;aggregieren](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="92476-119">[&#40;MDX-&#41;Filtern](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="92476-120">[Eigenschaften &#40;MDX-&#41;](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="92476-121">[DrilldownLevel-&#40;MDX-&#41;](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="92476-122">[Hierarchize &#40;MDX-&#41;](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="92476-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="92476-123">MDX-Funktionsreferenz &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="92476-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
