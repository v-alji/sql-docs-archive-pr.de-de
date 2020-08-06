---
title: Erstellen berechneter Elemente im Bereich einer Sitzung (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- CREATE MEMBER statement
- session-scoped calculated members [MDX]
ms.assetid: 2875ed89-2c26-4645-8ed9-8848479d110f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8fe7a9f137d8b74eaa5bad104dbfdb471dd14588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620616"
---
# <a name="creating-session-scoped-calculated-members-mdx"></a><span data-ttu-id="f7f91-102">Erstellen berechneter Elemente im Bereich einer Sitzung (MDX)</span><span class="sxs-lookup"><span data-stu-id="f7f91-102">Creating Session-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="f7f91-103">Zum Erstellen eines berechneten Elements, das während einer gesamten MDX-Sitzung (Multidimensional Expressions) verfügbar ist, verwenden Sie die [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f7f91-103">To create a calculated member that is available throughout a Multidimensional Expressions (MDX) session, you use the [CREATE MEMBER](/sql/mdx/mdx-data-definition-create-member) statement.</span></span> <span data-ttu-id="f7f91-104">Ein berechnetes Element, das mit der CREATE MEMBER-Anweisung erstellt wurde, wird erst entfernt, nachdem die MDX-Sitzung geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="f7f91-104">A calculated member that is created by using the CREATE MEMBER statement will not be removed until after the MDX session closes.</span></span>  
  
 <span data-ttu-id="f7f91-105">Wie in diesem Thema erläutert wird, ist die Syntax der CREATE MEMBER-Anweisung unkompliziert und einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7f91-105">As discussed in this topic, the syntax of the CREATE MEMBER statement is straightforward and easy to use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7f91-106">Weitere Informationen zu berechneten Elementen finden Sie unter [Erstellen von berechneten Elementen in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="f7f91-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="create-member-syntax"></a><span data-ttu-id="f7f91-107">Syntax von CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="f7f91-107">CREATE MEMBER Syntax</span></span>  
 <span data-ttu-id="f7f91-108">Verwenden Sie die folgende Syntax, um der MDX-Anweisung die CREATE MEMBER-Anweisung hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f7f91-108">Use the following syntax to add the CREATE MEMBER statement to the MDX statement:</span></span>  
  
```  
CREATE [SESSION] MEMBER [<cube-name>.]<fully-qualified-member-name> AS <expression> [,<property-definition-list>]  
<cube name> ::= CURRENTCUBE | <Cube Name>  
<property-definition-list> ::= <property-definition>  
  | <property-definition>, <property-definition-list>  
<property-definition> ::= <property-identifier> = <property-value>  
<property-identifier> ::= VISIBLE | SOLVEORDER | SOLVE_ORDER | FORMAT_STRING | NON_EMPTY_BEHAVIOR <ole db member properties>  
```  
  
 <span data-ttu-id="f7f91-109">In der Syntax für die CREATE MEMBER-Anweisung entspricht der `fully-qualified-member-name` -Wert dem vollqualifizierten Namen des berechneten Elements.</span><span class="sxs-lookup"><span data-stu-id="f7f91-109">In the syntax for the CREATE MEMBER statement, the `fully-qualified-member-name` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="f7f91-110">Der vollqualifizierte Name enthält die Dimension oder Ebene, der das berechnete Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f7f91-110">The fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="f7f91-111">Der `expression` -Wert gibt den Wert des berechneten Elements zurück, nachdem der Wert des Ausdrucks ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="f7f91-111">The `expression` value returns the value of the calculated member after the expression value has been evaluated,.</span></span>  
  
## <a name="create-member-example"></a><span data-ttu-id="f7f91-112">Beispiel zu CREATE MEMBER</span><span class="sxs-lookup"><span data-stu-id="f7f91-112">CREATE MEMBER Example</span></span>  
 <span data-ttu-id="f7f91-113">Im folgenden Beispiel wird die CREATE MEMBER-Anweisung dazu verwendet, das berechnete Element `LastFourStores` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7f91-113">The following example uses the CREATE MEMBER statement to create the `LastFourStores` calculated member.</span></span> <span data-ttu-id="f7f91-114">Dieses berechnete Element gibt die Summe der verkauften Einheiten für die letzten vier Filialen zurück und ist während der gesamten Cubesitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7f91-114">This calculated member returns the sum of units sold for the last four stores, and will be available throughout the whole session of the cube.</span></span>  
  
```  
Create Session Member [Store].[Measures].LastFourStores as   
sum(([Stores].[ByLocation].Lag(3) :  
[Stores].[ByLocation].NextMember), [Measures].[Units Sold])  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7f91-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7f91-115">See Also</span></span>  
 [<span data-ttu-id="f7f91-116">Erstellen berechneter Elemente im Bereich einer Abfrage &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="f7f91-116">Creating Query-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-query-scoped-calculated-members.md)  
  
  
