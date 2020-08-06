---
title: Grundlegendes zu MDX-Skripts (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620611"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="6b220-102">Grundlegendes zu MDX-Skripts (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="6b220-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="6b220-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]besteht ein MDX-Skript (Multidimensional Expressions) aus einem oder mehreren MDX-Ausdrücken oder -Anweisungen, die einen Cube mit Berechnungen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="6b220-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="6b220-104">In einem MDX-Skript wird der Berechnungsprozess für einen Cube definiert.</span><span class="sxs-lookup"><span data-stu-id="6b220-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="6b220-105">Ein MDX-Skript wird auch als Teil des Cubes selbst angesehen.</span><span class="sxs-lookup"><span data-stu-id="6b220-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="6b220-106">Daher bewirkt ein Ändern eines MDX-Skripts, das einem Cube zugeordnet ist, dass der Berechnungsprozess für den Cube sofort geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6b220-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="6b220-107">Um MDX-Skripts zu erstellen, können Sie den Cube-Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b220-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6b220-108">Weitere Informationen finden Sie unter [Definieren von Zuweisungen und anderen Skriptbefehlen](../define-assignments-and-other-script-commands.md) und [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892)(Einführung in MDX-Skripts in Microsoft SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="6b220-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="6b220-109">Informationen zu Leistungsproblemen im Zusammenhang mit MDX-Abfragen und -Berechnungen finden Sie im Abschnitt zur MDX-Optimierung im [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="6b220-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b220-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6b220-110">In This Section</span></span>  
  
|<span data-ttu-id="6b220-111">Thema</span><span class="sxs-lookup"><span data-stu-id="6b220-111">Topic</span></span>|<span data-ttu-id="6b220-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b220-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6b220-113">Grundlegendes MDX-Skript &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="6b220-114">Beschreibt ausführlich das grundlegende MDX-Skript (samt dem MDX-Standardskript, das in jedem Cube bereitgestellt wird), und beschreibt, wie MDX-Skripts in einem Cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]im Grundsatz funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6b220-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="6b220-115">Verwalten von Gültigkeitsbereich und Kontext &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="6b220-116">Beschreibt, wie die [CALCULATE](/sql/mdx/mdx-scripting-calculate) -Anweisung, die [SCOPE](/sql/mdx/mdx-scripting-scope) -Anweisung und die [This](/sql/mdx/this-mdx) -Funktion dazu verwendet werden, in einem MDX-Skript den Kontext und den Gültigkeitsbereich zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6b220-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="6b220-117">Verwenden von Variablen und Parametern &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="6b220-118">Beschreibt, wie Variablen und Parameter in einem MDX-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b220-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="6b220-119">Fehlerbehandlung &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="6b220-120">Erläutert die Fehlerbehandlung innerhalb eines MDX-Skripts.</span><span class="sxs-lookup"><span data-stu-id="6b220-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="6b220-121">Unterstütztes MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="6b220-122">Stellt eine Liste der MDX-Operatoren, -Anweisungen und -Funktionen bereit, die in einem MDX-Skript unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6b220-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b220-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b220-123">See Also</span></span>  
 [<span data-ttu-id="6b220-124">MDX-Sprachreferenz &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="6b220-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
