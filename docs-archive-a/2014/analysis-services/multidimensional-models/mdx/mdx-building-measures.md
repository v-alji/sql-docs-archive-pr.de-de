---
title: Entwickeln von Measures in MDX | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0347835-4983-4d26-acbb-6c8fae7992bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac49d37f11584bfbc5d372241056da39e7dd8c93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616740"
---
# <a name="building-measures-in-mdx"></a><span data-ttu-id="a16a7-102">Erstellen von Measures in MDX</span><span class="sxs-lookup"><span data-stu-id="a16a7-102">Building Measures in MDX</span></span>
  <span data-ttu-id="a16a7-103">In MDX (Multidimensional Expressions) ist ein Measure ein benannter DAX-Ausdruck, der durch das Berechnen des Ausdrucks aufgelöst wird, um einen Wert in einem tabellarischen Modell zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a16a7-103">In Multidimensional Expressions (MDX), a measure is a named DAX expression that is resolved by calculating the expression to return a value in a Tabular Model.</span></span> <span data-ttu-id="a16a7-104">Diese einfach klingende Definition hat immense Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="a16a7-104">This innocuous definition covers an incredible amount of ground.</span></span> <span data-ttu-id="a16a7-105">Die Erstellung und Verwendung von Measures in einer MDX-Abfrage eröffnet umfassende Änderungsmöglichkeiten für Tabellendaten.</span><span class="sxs-lookup"><span data-stu-id="a16a7-105">The ability to construct and use measures in an MDX query provides a great deal of manipulation capability for tabular data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a16a7-106">Measures können nur in tabellarischen Modellen definiert werden. Wenn die Datenbank auf den mehrdimensionalen Modus festgelegt ist, tritt beim Erstellen eines Measures ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="a16a7-106">Measures can only be defined in tabular models; if your database is set in multidimensional mode, creating a measure will generate an error</span></span>  
  
 <span data-ttu-id="a16a7-107">Mit dem WITH-Schlüsselwort können Sie ein Measure erstellen, das als Teil einer MDX-Abfrage definiert ist und deren Bereich daher auf die Abfrage beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="a16a7-107">To create a measure that is defined as part of an MDX query, and therefore whose scope is limited to the query, you use the WITH keyword.</span></span> <span data-ttu-id="a16a7-108">Anschließend können Sie das Measure in einer SELECT-Anweisung von MDX verwenden.</span><span class="sxs-lookup"><span data-stu-id="a16a7-108">You can then use the measure within an MDX SELECT statement.</span></span> <span data-ttu-id="a16a7-109">Bei dieser Vorgehensweise kann das mit dem WITH-Schlüsselwort erstellte berechnete Element geändert werden, ohne dass die SELECT-Anweisung davon beeinflusst wird.</span><span class="sxs-lookup"><span data-stu-id="a16a7-109">Using this approach, the calculated member created by using the WITH keyword can be changed without disturbing the SELECT statement.</span></span> <span data-ttu-id="a16a7-110">In MDX wird auf das Measure jedoch auf andere Weise als in DAX-Ausdrücken verwiesen. Zum Verweisen auf das Measure benennen Sie es als Mitglied der [Measures]-Dimension, wie im folgenden MDX-Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a16a7-110">However, in MDX you reference the measure in a different way than when in DAX expressions; to reference the measure you name it as a member of the [Measures] dimension, see the following MDX example:</span></span>  
  
```  
with measure  'Sales Territory'[Total Sales Amount] = SUM('Internet Sales'[Sales Amount]) + SUM('Reseller Sales'[Sales Amount])  
select measures.[Total Sales Amount] on columns  
     ,NON EMPTY [Date].[Calendar Year].children on rows  
from [Model]  
  
```  
  
 <span data-ttu-id="a16a7-111">Nach der Ausführung werden die folgenden Daten zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a16a7-111">It will return the following data when executed:</span></span>  
  
||<span data-ttu-id="a16a7-112">Total Sales Amount</span><span class="sxs-lookup"><span data-stu-id="a16a7-112">Total Sales Amount</span></span>||  
|-|------------------------|-|  
|<span data-ttu-id="a16a7-113">2001</span><span class="sxs-lookup"><span data-stu-id="a16a7-113">2001</span></span>|<span data-ttu-id="a16a7-114">11331808.96</span><span class="sxs-lookup"><span data-stu-id="a16a7-114">11331808.96</span></span>||  
|<span data-ttu-id="a16a7-115">2002</span><span class="sxs-lookup"><span data-stu-id="a16a7-115">2002</span></span>|<span data-ttu-id="a16a7-116">30674773.18</span><span class="sxs-lookup"><span data-stu-id="a16a7-116">30674773.18</span></span>||  
|<span data-ttu-id="a16a7-117">2003</span><span class="sxs-lookup"><span data-stu-id="a16a7-117">2003</span></span>|<span data-ttu-id="a16a7-118">41993729.72</span><span class="sxs-lookup"><span data-stu-id="a16a7-118">41993729.72</span></span>||  
|<span data-ttu-id="a16a7-119">2004</span><span class="sxs-lookup"><span data-stu-id="a16a7-119">2004</span></span>|<span data-ttu-id="a16a7-120">25808962.34</span><span class="sxs-lookup"><span data-stu-id="a16a7-120">25808962.34</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a16a7-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a16a7-121">See Also</span></span>  
 <span data-ttu-id="a16a7-122">[Create Member-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-definition-create-member) </span><span class="sxs-lookup"><span data-stu-id="a16a7-122">[CREATE MEMBER Statement &#40;MDX&#41;](/sql/mdx/mdx-data-definition-create-member) </span></span>  
 <span data-ttu-id="a16a7-123">[MDX-Funktionsreferenz &#40;MDX-&#41;](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="a16a7-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 [<span data-ttu-id="a16a7-124">SELECT-Anweisung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="a16a7-124">SELECT Statement &#40;MDX&#41;</span></span>](/sql/mdx/mdx-data-manipulation-select)  
  
  
