---
title: Erstellen und Verwenden von Eigenschafts Werten (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- property values [MDX]
- queries [MDX], property values
- MDX [Analysis Services], property values
- Multidimensional Expressions [Analysis Services], property values
ms.assetid: 0cafb269-03c8-4183-b6e9-220f071e4ef2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 67eadc6bc2f0bf6f318f20ad42a5cc9e7a5afa5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618945"
---
# <a name="creating-and-using-property-values-mdx"></a><span data-ttu-id="07d18-102">Erstellen und Verwenden von Eigenschaftswerten (MDX)</span><span class="sxs-lookup"><span data-stu-id="07d18-102">Creating and Using Property Values (MDX)</span></span>
  <span data-ttu-id="07d18-103">MDX (Multidimensional Expressions) unterstützt systeminterne und benutzerdefinierte Eigenschaften für Dimensionen, Ebenen, Elemente und Zellen.</span><span class="sxs-lookup"><span data-stu-id="07d18-103">Multidimensional Expressions (MDX) supports intrinsic and user-defined properties for dimensions, levels, members, and cells.</span></span> <span data-ttu-id="07d18-104">Die systeminternen Eigenschaften stellen eindeutige Namen, Beschriftungen, Formatierungen und Schriftgrade für einzelne Zellen bereit.</span><span class="sxs-lookup"><span data-stu-id="07d18-104">The intrinsic properties provide unique names, captions, and even formatting and font sizes for individual cells.</span></span> <span data-ttu-id="07d18-105">Benutzerdefinierte Eigenschaften können dagegen fast alle Arten von zusätzlichen Attributen für Elemente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="07d18-105">User-defined properties, on the other hand, can provide almost any kind of additional attribute to members.</span></span>  
  
 <span data-ttu-id="07d18-106">Systeminterne und benutzerdefinierte Eigenschaften sind auf folgenden Ebenen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="07d18-106">Intrinsic and user-defined properties are available at the following levels:</span></span>  
  
 <span data-ttu-id="07d18-107">**Element Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="07d18-107">**Member properties**</span></span>  
 <span data-ttu-id="07d18-108">Elementeigenschaften enthalten die grundlegenden Informationen zu jedem Element in jedem Tupel.</span><span class="sxs-lookup"><span data-stu-id="07d18-108">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="07d18-109">Zu den grundlegenden Informationen gehören der Elementname, die übergeordnete Ebene, die Anzahl der untergeordneten Elemente usw.</span><span class="sxs-lookup"><span data-stu-id="07d18-109">This basic information includes the member name, parent level, the number of children, and so on.</span></span>  
  
 <span data-ttu-id="07d18-110">Weitere Informationen zu Elementeigenschaften und deren Verwendung finden Sie unter [Verwenden von Elementeigenschaften &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="07d18-110">For information about member properties and how to use them, see [Using Member Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-member-properties.md).</span></span>  
  
 <span data-ttu-id="07d18-111">**Zelleigenschaften**</span><span class="sxs-lookup"><span data-stu-id="07d18-111">**Cell properties**</span></span>  
 <span data-ttu-id="07d18-112">Zelleigenschaften enthalten Informationen zum Inhalt und Format von Zellen in einer mehrdimensionalen Datenquelle (z. B. einem Cube).</span><span class="sxs-lookup"><span data-stu-id="07d18-112">Cell properties contain information about the content and format of cells in a multidimensional data source, such as a cube.</span></span>  
  
 <span data-ttu-id="07d18-113">Weitere Informationen zu Zelleigenschaften und ihrer Verwendung finden Sie unter [Verwenden von Zelleigenschaften &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span><span class="sxs-lookup"><span data-stu-id="07d18-113">For more information about cell properties and how to use them, see [Using Cell Properties &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-using-cell-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d18-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07d18-114">See Also</span></span>  
 [<span data-ttu-id="07d18-115">Grundlegendes zu MDX-Abfragen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="07d18-115">MDX Query Fundamentals &#40;Analysis Services&#41;</span></span>](multidimensional-models/mdx/mdx-query-fundamentals-analysis-services.md)  
  
  
