---
title: Erstellen von benutzerdefinierten Hierarchien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined hierarchies [Analysis Services]
ms.assetid: 16715b85-0630-4a8e-99b0-c0d213cade26
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17e870a2b20125132342db1845689b7c2481d623
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700323"
---
# <a name="create-user-defined-hierarchies"></a><span data-ttu-id="524c9-102">Erstellen von benutzerdefinierten Hierarchien</span><span class="sxs-lookup"><span data-stu-id="524c9-102">Create User-Defined Hierarchies</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="524c9-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]ermöglicht das Erstellen benutzerdefinierter Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="524c9-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] lets you create user-defined hierarchies.</span></span> <span data-ttu-id="524c9-104">Eine Hierarchie ist eine Auflistung von Ebenen, die auf Attributen basiert.</span><span class="sxs-lookup"><span data-stu-id="524c9-104">A hierarchy is a collection of levels based on attributes.</span></span> <span data-ttu-id="524c9-105">So kann beispielsweise eine Zeithierarchie die Ebenen Jahr, Quartal, Monat, Woche und Tag enthalten.</span><span class="sxs-lookup"><span data-stu-id="524c9-105">For example, a time hierarchy might contain the Year, Quarter, Month, Week, and Day levels.</span></span> <span data-ttu-id="524c9-106">In einigen Hierarchien impliziert jedes Elementattribut das jeweils übergeordnete Elementattribut.</span><span class="sxs-lookup"><span data-stu-id="524c9-106">In some hierarchies, each member attribute uniquely implies the member attribute above it.</span></span> <span data-ttu-id="524c9-107">Dies wird auch als natürliche Hierarchie bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="524c9-107">This is sometimes referred to as a natural hierarchy.</span></span> <span data-ttu-id="524c9-108">Eine Hierarchie kann von Endbenutzern verwendet werden, um Cubedaten zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="524c9-108">A hierarchy can be used by end users to browse cube data.</span></span> <span data-ttu-id="524c9-109">Zum Definieren von Hierarchien verwenden Sie den Bereich Hierarchien des Dimensions-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="524c9-109">Define hierarchies by using the Hierarchies pane of Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="524c9-110">Wenn Sie eine benutzerdefinierte Hierarchie erstellen, kann die Hierarchie *unregelmäßig*werden.</span><span class="sxs-lookup"><span data-stu-id="524c9-110">When you create a user-defined hierarchy, the hierarchy might become *ragged*.</span></span> <span data-ttu-id="524c9-111">In einer unregelmäßigen Hierarchie befindet sich das logisch übergeordnete Element mindestens eines Elements nicht auf der Ebene unmittelbar über dem betreffenden Element.</span><span class="sxs-lookup"><span data-stu-id="524c9-111">A ragged hierarchy is where the logical parent member of at least one member is not in the level immediately above the member.</span></span> <span data-ttu-id="524c9-112">Wenn Sie über eine unregelmäßige Hierarchie verfügen, können Sie festlegen, ob die fehlenden Elemente sichtbar sind und wie sie angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="524c9-112">If you have a ragged hierarchy, there are settings that control whether the missing members are visible and how to display the missing members.</span></span> <span data-ttu-id="524c9-113">Weitere Informationen finden Sie unter [Unregelmäßige Hierarchien](user-defined-hierarchies-ragged-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="524c9-113">For more information, see [Ragged Hierarchies](user-defined-hierarchies-ragged-hierarchies.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="524c9-114">Weitere Informationen zu Leistungsproblemen im Zusammenhang mit dem Design und der Konfiguration von benutzerdefinierten Hierarchien finden Sie im [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span><span class="sxs-lookup"><span data-stu-id="524c9-114">For more information about performance issues related to the design and configuration of user-defined hierarchies, see the [SQL Server 2005 Analysis Services Performance Guide](https://docsbay.net/Microsoft-SQL-Server-2005-Analysis-Services-Performance-Guide).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524c9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="524c9-115">See Also</span></span>  
 <span data-ttu-id="524c9-116">[Eigenschaften der Benutzer Hierarchie](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span><span class="sxs-lookup"><span data-stu-id="524c9-116">[User Hierarchy Properties](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md) </span></span>  
 <span data-ttu-id="524c9-117">[Eigenschaften der Ebene &#91;&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span><span class="sxs-lookup"><span data-stu-id="524c9-117">[Level Properties &#91;Paved Over&#93;](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies-level-properties.md) </span></span>  
 [<span data-ttu-id="524c9-118">Über-und untergeordnete Hierarchie</span><span class="sxs-lookup"><span data-stu-id="524c9-118">Parent-Child Hierarchy</span></span>](parent-child-dimension.md)  
  
  
