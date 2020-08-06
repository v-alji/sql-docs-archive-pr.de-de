---
title: Verwenden von Element Eigenschaften (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698619"
---
# <a name="using-member-properties-mdx"></a><span data-ttu-id="d4483-102">Verwenden von Elementeigenschaften (MDX)</span><span class="sxs-lookup"><span data-stu-id="d4483-102">Using Member Properties (MDX)</span></span>
  <span data-ttu-id="d4483-103">Elementeigenschaften enthalten die grundlegenden Informationen zu jedem Element in jedem Tupel.</span><span class="sxs-lookup"><span data-stu-id="d4483-103">Member properties cover the basic information about each member in each tuple.</span></span> <span data-ttu-id="d4483-104">Zu den grundlegenden Informationen gehören der Elementname, die übergeordnete Ebene, die Anzahl der untergeordneten Elemente usw.</span><span class="sxs-lookup"><span data-stu-id="d4483-104">This basic information includes the member name, parent level, the number of children, and so on.</span></span> <span data-ttu-id="d4483-105">Elementeigenschaften sind für alle Elemente auf der jeweiligen Ebene verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d4483-105">Member properties are available for all members at a given level.</span></span> <span data-ttu-id="d4483-106">Organisatorisch werden Elementeigenschaften als in Dimensionen organisierte Daten behandelt, die in einer einzigen Dimension gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d4483-106">In terms of organization, member properties are treated as dimensionally organized data, stored on a single dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4483-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]werden Elementeigenschaften als Attributbeziehungen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d4483-107">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], member properties are know as attribute relationships.</span></span> <span data-ttu-id="d4483-108">Weitere Informationen finden Sie unter [Attributbeziehungen](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-108">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
 <span data-ttu-id="d4483-109">Eine Elementeigenschaft ist entweder *systemintern* oder *benutzerdefiniert*:</span><span class="sxs-lookup"><span data-stu-id="d4483-109">Member properties are either *intrinsic* or *custom*:</span></span>  
  
 <span data-ttu-id="d4483-110">Systeminterne Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4483-110">Intrinsic member properties</span></span>  
 <span data-ttu-id="d4483-111">Alle Elemente unterstützen systeminterne Elementeigenschaften, wie z. B. den formatierten Wert eines Elements. Dimensionen und Ebenen stellen dagegen zusätzliche systeminterne dimensions- und ebenenspezifische Elementeigenschaften, wie die ID eines Elements, bereit.</span><span class="sxs-lookup"><span data-stu-id="d4483-111">All members support intrinsic member properties, such as the formatted value of a member, while dimensions and levels supply additional intrinsic dimension and level member properties, such as the ID of a member.</span></span>  
  
 <span data-ttu-id="d4483-112">Weitere Informationen finden Sie unter [Integrierte Elementeigenschaften &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-112">For more information, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
 <span data-ttu-id="d4483-113">Benutzerdefinierte Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4483-113">User-defined member properties</span></span>  
 <span data-ttu-id="d4483-114">Elemente haben häufig weitere ihnen zugeordnete Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d4483-114">Members often have additional properties associated with them.</span></span> <span data-ttu-id="d4483-115">Die Products-Ebene kann z. B. die Eigenschaften SKU (Stock Keeping Unit), SRP (Suggested Retail Price), Weight und Volume für jedes Produkt bieten.</span><span class="sxs-lookup"><span data-stu-id="d4483-115">For example, the Products level may offer the SKU, SRP, Weight, and Volume properties for each product.</span></span> <span data-ttu-id="d4483-116">Diese Eigenschaften sind keine Elemente, sondern enthalten zusätzliche Informationen zu Elementen auf der Products-Ebene.</span><span class="sxs-lookup"><span data-stu-id="d4483-116">These properties are not members, but contain additional information about members at the Products level.</span></span>  
  
 <span data-ttu-id="d4483-117">Weitere Informationen finden Sie unter [Benutzerdefinierte Elementeigenschaften &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-117">For more information, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
 <span data-ttu-id="d4483-118">Sowohl intrinsische als auch benutzerdefinierte Element Eigenschaften können mithilfe des- `PROPERTIES` Schlüssel Worts oder der [Properties](/sql/mdx/properties-mdx) -Funktion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d4483-118">Both intrinsic and user-defined member properties can be retrieved through the use of the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
## <a name="using-the-properties-keyword"></a><span data-ttu-id="d4483-119">Verwenden des PROPERTIES-Schlüsselworts</span><span class="sxs-lookup"><span data-stu-id="d4483-119">Using the PROPERTIES Keyword</span></span>  
 <span data-ttu-id="d4483-120">Das `PROPERTIES`-Schlüsselwort gibt die Elementeigenschaften an, die für eine bestimmte Achsendimension verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d4483-120">The `PROPERTIES` keyword specifies the member properties that are to be used for a given axis dimension.</span></span> <span data-ttu-id="d4483-121">Das `PROPERTIES` Schlüsselwort ist in der- `<axis specification>` Klausel der [Select](/sql/mdx/mdx-data-manipulation-select) -Anweisung von MDX verborgen:</span><span class="sxs-lookup"><span data-stu-id="d4483-121">The `PROPERTIES` keyword is buried within the `<axis specification>` clause of the MDX [SELECT](/sql/mdx/mdx-data-manipulation-select) statement:</span></span>  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 <span data-ttu-id="d4483-122">Die `<axis_specification>` -Klausel enthält eine optionale `<dim_props>` -Klausel (siehe folgende Syntax):</span><span class="sxs-lookup"><span data-stu-id="d4483-122">The `<axis_specification>` clause includes an optional `<dim_props>` clause, as shown in the following syntax:</span></span>  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d4483-123">Weitere Informationen zu den Werten `<set>` und `<axis_name>` finden Sie unter [Angeben des Inhalts einer Abfrageachse &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-123">For more information about the `<set>` and `<axis_name>` values, see [Specifying the Contents of a Query Axis &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).</span></span>  
  
 <span data-ttu-id="d4483-124">Die `<dim_props>`-Klausel ermöglicht es Ihnen, mithilfe des `PROPERTIES`-Schlüsselworts Dimensions-, Ebenen- und Elementeigenschaften abzufragen.</span><span class="sxs-lookup"><span data-stu-id="d4483-124">The `<dim_props>` clause lets you query dimension, level, and member properties using the `PROPERTIES` keyword.</span></span> <span data-ttu-id="d4483-125">Nachstehend ist die Syntax der `<dim_props>` -Klausel definiert:</span><span class="sxs-lookup"><span data-stu-id="d4483-125">The following syntax shows the formatting of the `<dim_props>` clause:</span></span>  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 <span data-ttu-id="d4483-126">Die Aufteilung der Syntax von `<property>` variiert abhängig davon, welche Eigenschaft abgefragt wird:</span><span class="sxs-lookup"><span data-stu-id="d4483-126">The breakdown of the `<property>` syntax varies depending on the property that you are querying:</span></span>  
  
-   <span data-ttu-id="d4483-127">Bei einer kontextabhängigen systeminternen Elementeigenschaft muss der Name der Dimension oder der Ebene vor der Eigenschaft stehen.</span><span class="sxs-lookup"><span data-stu-id="d4483-127">Context sensitive intrinsic member properties must be preceded with the name of the dimension or level.</span></span> <span data-ttu-id="d4483-128">Nicht kontextabhängige systeminterne Elementeigenschaften können dagegen nicht durch den Dimensions- oder Ebenennamen qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d4483-128">However, non-context sensitive intrinsic member properties cannot be qualified by the dimension or level name.</span></span> <span data-ttu-id="d4483-129">Weitere Informationen zur Verwendung des-Schlüssel Worts mit systeminternen Element Eigenschaften finden Sie unter systeminterne Element `PROPERTIES` [Eigenschaften &#40;MDX-&#41;](mdx-member-properties-intrinsic-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-129">For more information about how to use the `PROPERTIES` keyword with intrinsic member properties, see [Intrinsic Member Properties &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).</span></span>  
  
-   <span data-ttu-id="d4483-130">Bei einer benutzerdefinierten Elementeigenschaft sollte der Name der Ebene vorangestellt werden, in der sie sich befindet.</span><span class="sxs-lookup"><span data-stu-id="d4483-130">User-defined member properties should be preceded by the name of the level in which they reside.</span></span> <span data-ttu-id="d4483-131">Weitere Informationen zur Verwendung des `PROPERTIES` Schlüssel Worts mit benutzerdefinierten Element Eigenschaften finden Sie unter [benutzerdefinierte Element Eigenschaften &#40;MDX-&#41;](mdx-member-properties-user-defined-member-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4483-131">For more information about how to use the `PROPERTIES` keyword with user-defined member properties, see [User-Defined Member Properties &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4483-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4483-132">See Also</span></span>  
 [<span data-ttu-id="d4483-133">Erstellen und Verwenden von Eigenschaftswerten &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="d4483-133">Creating and Using Property Values &#40;MDX&#41;</span></span>](../../creating-and-using-property-values-mdx.md)  
  
  
