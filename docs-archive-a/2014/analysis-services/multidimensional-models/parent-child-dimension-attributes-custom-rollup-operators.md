---
title: Benutzerdefinierte Rollup-Operatoren in über-und untergeordneten Dimensionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- child rollup operations
- UnaryOperatorColumn property
- custom rollup operators [Analysis Services]
- unary operators
- parent-child dimensions [Analysis Services]
ms.assetid: a3ddd9fc-5fa3-4227-9322-8c45a5b5c2c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: db12ccc6703ee4863dd3b6bd598d2317b54fce6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619407"
---
# <a name="custom-rollup-operators-in-parent-child-dimensions"></a><span data-ttu-id="0f6f3-102">Benutzerdefinierte Rollupoperatoren in über- und untergeordneten Dimensionen</span><span class="sxs-lookup"><span data-stu-id="0f6f3-102">Custom Rollup Operators in Parent-Child Dimensions</span></span>
  <span data-ttu-id="0f6f3-103">Mit benutzerdefinierten Rollup-Operatoren können Sie auf einfache Weise steuern, wie Rollups von Elementwerten zu übergeordneten Werten in einer Hierarchie mit über- und untergeordneten Elementen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-103">Custom rollup operators provide a simple way to control how member values are rolled up into parent values in a parent-child hierarchy.</span></span> <span data-ttu-id="0f6f3-104">In einer Dimension mit einer Über-/Unterordnungsbeziehung geben Sie eine Spalte mit unären Operatoren an, die einen Rollup für alle nicht berechneten Elemente des übergeordneten Attributs angeben.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-104">In a dimension containing a parent-child relationship, you specify a column that contains unary operators that specify rollup for all noncalculated members of the parent attribute.</span></span> <span data-ttu-id="0f6f3-105">Der unäre Operator wird immer dann auf die Elemente angewendet, wenn die Werte des übergeordneten Elements ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-105">The unary operator is applied to members whenever the values of the parent members are evaluated.</span></span>  
  
 <span data-ttu-id="0f6f3-106">Die unären Operatoren werden in der Spalte gespeichert, die durch die `UnaryOperatorColumn`-Eigenschaft des übergeordneten Attributs definiert ist, und werden auf jedes Element des Attributs angewendet.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-106">The unary operators are stored in column defined by the `UnaryOperatorColumn` property of the parent attribute, and they are applied to each member of the attribute.</span></span> <span data-ttu-id="0f6f3-107">Die durch diese Eigenschaft angegebene Spalte kann sich in der Dimensionstabelle oder in einer Tabelle befinden, die durch einen Fremdschlüssel in der Dimensionstabelle mit der Dimensionstabelle verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-107">The column specified by this property can reside either in the dimension table or in a table related to the dimension table by a foreign key in the dimension table.</span></span>  
  
 <span data-ttu-id="0f6f3-108">Benutzerdefinierte Rollup-Operatoren stellen eine Funktionalität bereit, die der von benutzerdefinierten Elementformeln ähnelt, jedoch einfacher ist.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-108">Custom rollup operators provide functionality similar to, but more simplified than, custom member formulas.</span></span> <span data-ttu-id="0f6f3-109">Eine benutzerdefinierte Elementformel bestimmt mithilfe von MDX-Ausdrücken (Multidimensional Expressions), wie der Rollup für die Elemente ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-109">A custom member formula uses Multidimensional Expressions (MDX) expressions to determine how the members are rolled up.</span></span> <span data-ttu-id="0f6f3-110">Im Gegensatz dazu bestimmt ein benutzerdefinierter Rollup-Operator mithilfe eines einfachen unären Operators, wie sich der Wert eines Elements auf das übergeordnete Element auswirkt.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-110">In contrast, a custom rollup operator uses a simple unary operator to determine how the value of a member affects the parent.</span></span> <span data-ttu-id="0f6f3-111">Benutzerdefinierte Elementformeln der vorherigen Ebene in einer Dimension überschreiben den benutzerdefinierten Rollup-Operator einer Ebene.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-111">Custom member formulas of the preceding level in a dimension override a level's custom rollup operator.</span></span>  
  
## <a name="custom-rollup-precedence"></a><span data-ttu-id="0f6f3-112">Rangfolge von benutzerdefinierten Rollup-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0f6f3-112">Custom Rollup Precedence</span></span>  
 <span data-ttu-id="0f6f3-113">Im Hinblick auf die Rangfolge überschreiben die benutzerdefinierten Rollup-Operatoren des Quellattributs für eine Ebene in einer Hierarchie die benutzerdefinierten Elementformeln der vorherigen Ebene</span><span class="sxs-lookup"><span data-stu-id="0f6f3-113">In terms of precedence, the custom rollup operators of the source attribute for a level in a hierarchy override the custom member formulas of the previous level.</span></span> <span data-ttu-id="0f6f3-114">Die benutzerdefinierten Elementformeln der vorhergehenden Ebene überschreiben jedoch die benutzerdefinierten Rollup-Operatoren einer Ebene.</span><span class="sxs-lookup"><span data-stu-id="0f6f3-114">However, the custom member formulas of the preceding level override the custom rollup operators of a level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6f3-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f6f3-115">See Also</span></span>  
 <span data-ttu-id="0f6f3-116">[Definieren von benutzerdefinierten Element Formeln](attribute-properties-define-custom-member-formulas.md) </span><span class="sxs-lookup"><span data-stu-id="0f6f3-116">[Define Custom Member Formulas](attribute-properties-define-custom-member-formulas.md) </span></span>  
 [<span data-ttu-id="0f6f3-117">Unäre Operatoren in über- und untergeordneten Dimensionen</span><span class="sxs-lookup"><span data-stu-id="0f6f3-117">Unary Operators in Parent-Child Dimensions</span></span>](parent-child-dimension-attributes-unary-operators.md)  
  
  
