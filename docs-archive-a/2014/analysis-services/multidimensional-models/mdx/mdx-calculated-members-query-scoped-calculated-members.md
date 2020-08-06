---
title: Erstellen berechneter Elemente im Bereich einer Abfrage (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616738"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="0f5ca-102">Erstellen berechneter Elemente im Bereich einer Abfrage (MDX)</span><span class="sxs-lookup"><span data-stu-id="0f5ca-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="0f5ca-103">Wenn ein berechnetes Element nur für eine einzelne MDX-Abfrage (Multidimensional Expressions) benötigt wird, können Sie das berechnete Element mit dem WITH-Schlüsselwort definieren.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="0f5ca-104">Ein berechnetes Element, das mit dem WITH-Schlüsselwort erstellt wird, ist nach der Ausführung der Abfrage nicht länger vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="0f5ca-105">Wie in diesem Thema erläutert wird, ist die Syntax des WITH-Schlüsselworts sehr flexibel und ermöglicht sogar die Definition berechneter Elemente auf der Grundlage eines anderen berechneten Elements.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f5ca-106">Weitere Informationen zu berechneten Elementen finden Sie unter [Erstellen von berechneten Elementen in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="0f5ca-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="0f5ca-107">WITH-Schlüsselwort (Syntax)</span><span class="sxs-lookup"><span data-stu-id="0f5ca-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="0f5ca-108">Verwenden Sie die folgende Syntax, um einer SELECT-Anweisung von MDX das WITH-Schlüsselwort hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0f5ca-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="0f5ca-109">In der Syntax für das WITH-Schlüsselwort entspricht der `Member_Identifier` -Wert dem vollgekennzeichneten Namen des berechneten Elements.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="0f5ca-110">Dieser vollgekennzeichnete Name enthält die Dimension oder Ebene, der das berechnete Element zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="0f5ca-111">Der `MDX_Expression` -Wert gibt den Wert des berechneten Elements zurück, nachdem der Wert des Ausdrucks ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="0f5ca-112">Die Werte systeminterner Zelleneigenschaften für ein berechnetes Element können optional angegeben werden, indem der Name der Zelleneigenschaft im `MemberProperty_Identifier` -Wert und der Wert der Zelleneigenschaft im `Scalar_Expression` -Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="0f5ca-113">WITH-Schlüsselwort (Beispiele)</span><span class="sxs-lookup"><span data-stu-id="0f5ca-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="0f5ca-114">Der folgende MDX-Ausdruck definiert ein berechnetes Element, `[Measures].[Special Discount]`, durch das ein bestimmter Rabatt, basierend auf dem ursprünglichen Rabattbetrag, berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="0f5ca-115">Sie können berechnete Elemente an jedem beliebigen Punkt in einer Hierarchie erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="0f5ca-116">Die folgende MDX-Abfrage definiert beispielsweise das berechnete Element `[BigSeller]` für einen hypothetischen Sales-Cube.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="0f5ca-117">Dieses berechnete Element bestimmt, ob ein bestimmtes Geschäft mindestens 100,00 Stück der Produkte Bier und Wein umgesetzt hat.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="0f5ca-118">Die Abfrage erstellt jedoch das berechnete Element `[BigSeller]` nicht als untergeordnetes Element der `[Product]` -Dimension, sondern als untergeordnetes Element des `[Beer and Wine]` -Elements.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="0f5ca-119">Berechnete Elemente müssen nicht nur von vorhandenen Elementen in einem Cube abhängen.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="0f5ca-120">Berechnete Elemente können auch auf anderen berechneten Elementen basieren, die in demselben MDX-Ausdruck definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="0f5ca-121">Die folgende MDX-Abfrage verwendet beispielsweise den Wert, der im ersten berechneten Element, `[Measures].[Special Discount]`, erstellt wird, um den Wert des zweiten berechneten Elements, `[Measures].[Special Discounted Amount]`, zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0f5ca-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f5ca-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f5ca-122">See Also</span></span>  
 <span data-ttu-id="0f5ca-123">[MDX-Funktionsreferenz &#40;MDX-&#41;](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="0f5ca-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="0f5ca-124">[SELECT-Anweisung &#40;MDX-&#41;](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="0f5ca-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="0f5ca-125">Erstellen berechneter Elemente im Bereich einer Sitzung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="0f5ca-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
