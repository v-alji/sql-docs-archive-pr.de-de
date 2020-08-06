---
title: Benutzerdefinierte Element Eigenschaften (MDX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698624"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="5b8f3-102">Benutzerdefinierte Elementeigenschaften (MDX)</span><span class="sxs-lookup"><span data-stu-id="5b8f3-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="5b8f3-103">Benutzerdefinierte Elementeigenschaften können einer bestimmten benannten Ebene in einer Dimension als Attributbeziehungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="5b8f3-104">Benutzerdefinierte Elementeigenschaften können weder der `(All)`-Ebene einer Hierarchie noch der Hierarchie selbst hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="5b8f3-105">Erstellen von benutzerdefinierten Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b8f3-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="5b8f3-106">Benutzerdefinierte Elementeigenschaften können serverbasierten Dimensionen oder Cubes entweder über die Benutzeroberfläche oder programmgesteuert hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="5b8f3-107">Um benutzerdefinierte Elementeigenschaften über die Benutzeroberfläche hinzuzufügen, verwenden Sie den Dimensions-Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b8f3-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5b8f3-108">Weitere Informationen finden Sie unter [Definieren von Attributbeziehungen](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="5b8f3-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="5b8f3-109">Um benutzerdefinierte Elementeigenschaften programmgesteuert hinzuzufügen, kann Ihre Anwendung entweder Analysis Management Objects (AMO) oder eine Kombination aus XMLA (XML for Analysis) und ASSL (Analysis Services Scripting Language) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="5b8f3-110">Weitere Informationen finden Sie unter [Attributbeziehungen](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="5b8f3-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="5b8f3-111">Abrufen von benutzerdefinierten Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b8f3-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="5b8f3-112">Benutzerdefinierte Element Eigenschaften können mithilfe des- `PROPERTIES` Schlüssel Worts oder der [Properties](/sql/mdx/properties-mdx) -Funktion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="5b8f3-113">Verwenden des PROPERTIES-Schlüsselworts zum Abrufen von benutzerdefinierten Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b8f3-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="5b8f3-114">Die Syntax für das Abrufen von benutzerdefinierten Elementeigenschaften gleicht der Syntax, mit der systeminterne Eigenschaften von Ebenenelementen abgerufen werden. Die folgende Syntax verdeutlicht dies:</span><span class="sxs-lookup"><span data-stu-id="5b8f3-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="5b8f3-115">Das `PROPERTIES`-Schlüsselwort steht hinter dem Mengenausdruck der Achsenspezifikation.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="5b8f3-116">In der folgende MDX-Abfrage ruft das `PROPERTIES`-Schlüsselwort beispielsweise die benutzerdefinierten Elementeigenschaften `List Price` und `Dealer Price` ab und wird nach dem Mengenausdruck angegeben, der die im Januar verkauften Produkte identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="5b8f3-117">Verwenden der Properties-Funktion zum Abrufen von benutzerdefinierten Elementeigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b8f3-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="5b8f3-118">Für das Zugreifen auf benutzerdefinierte Elementeigenschaften kann auch die `Properties`-Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b8f3-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="5b8f3-119">Die folgende MDX-Abfrage verwendet beispielsweise das `WITH`-Schlüsselwort, um ein berechnetes Element zu erstellen, das aus der `List Price`-Elementeigenschaft besteht:</span><span class="sxs-lookup"><span data-stu-id="5b8f3-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="5b8f3-120">Weitere Informationen zum Erstellen berechneter Elemente finden Sie unter [Erstellen von berechneten Elementen in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="5b8f3-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8f3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b8f3-121">See Also</span></span>  
 <span data-ttu-id="5b8f3-122">[Verwenden von Element Eigenschaften &#40;MDX-&#41;](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="5b8f3-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="5b8f3-123">Properties &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="5b8f3-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
