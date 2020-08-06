---
title: Konfigurieren der (All)-Ebene für Attribut Hierarchien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698696"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="7f98d-102">Konfigurieren der Ebene (aller Ebenen) für Attributhierarchien</span><span class="sxs-lookup"><span data-stu-id="7f98d-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="7f98d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] handelt es sich bei der (All)-Ebene um eine optionale, vom systemgenerierte Ebene.</span><span class="sxs-lookup"><span data-stu-id="7f98d-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="7f98d-104">Sie enthält nur ein Element, dessen Wert die Aggregation der Werte aller Elemente in der direkt untergeordneten Ebene ist.</span><span class="sxs-lookup"><span data-stu-id="7f98d-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="7f98d-105">Dieses Element wird als Alle-Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7f98d-105">This member is called the All member.</span></span> <span data-ttu-id="7f98d-106">Das vom System erzeugte Element ist nicht in der Dimensionstabelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f98d-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="7f98d-107">Da sich das Element in der Gesamtergebnisebene an oberster Stelle in der Hierarchie befindet, ist der Wert des Elements die konsolidierte Aggregation der Werte aller Elemente in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="7f98d-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="7f98d-108">Das Alle-Element dient häufig als Standardelement einer Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="7f98d-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="7f98d-109">Ob eine Alle-Ebene in einer Attributhierarchie vorhanden ist, hängt von der Einstellung der `IsAggregatable`-Eigenschaft für das Attribut ab. Ob eine Alle-Ebene in einer benutzerdefinierten Hierarchie vorhanden ist, hängt von der `IsAggregatable`-Eigenschaft des Attributs auf der obersten Ebene der benutzerdefinierten Hierarchie ab.</span><span class="sxs-lookup"><span data-stu-id="7f98d-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="7f98d-110">Wenn die `IsAggregatable`-Eigenschaft auf `True` festgelegt ist, ist eine Alle-Ebene vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7f98d-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="7f98d-111">In einer Hierarchie ist keine Alle-Ebene vorhanden, wenn die `IsAggregatable`-Eigenschaft auf `False` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7f98d-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="7f98d-112">Einrichten der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="7f98d-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="7f98d-113">Wenn die `IsAggregatable`-Eigenschaft für das Quellattribut einer Ebene in einer Hierarchie auf `False` festgelegt ist, kann in der Hierarchie über dieser Ebene keine Aggregatebene vorkommen.</span><span class="sxs-lookup"><span data-stu-id="7f98d-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="7f98d-114">Eine Nichtaggregatebene muss die oberste Ebene jeder Hierarchie sein, oder die `IsAggregatable`-Eigenschaft der Quellattribute für alle Ebenen darüber müssen ebenfalls auf `False` festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="7f98d-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="7f98d-115">Alle-Element und Alle-Ebene</span><span class="sxs-lookup"><span data-stu-id="7f98d-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="7f98d-116">Das einzige Element der Alle-Ebene wird als Alle-Element bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7f98d-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="7f98d-117">Die- `AttributeAllMemberName` Eigenschaft einer Dimension gibt den Namen des alle-Elements für Attribute in einer Dimension an.</span><span class="sxs-lookup"><span data-stu-id="7f98d-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="7f98d-118">Die `AllMemberName`-Eigenschaft in einer Hierarchie gibt den Namen des Alle-Elements für die Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="7f98d-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f98d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f98d-119">See Also</span></span>  
 [<span data-ttu-id="7f98d-120">Definieren eines Standardelements</span><span class="sxs-lookup"><span data-stu-id="7f98d-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
