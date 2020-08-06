---
title: Mehrere Rang folgen Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618096"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="4a324-102">Mehrere Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a324-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="4a324-103">Eine Rangfolgeneinschränkung verbindet zwei ausführbare Dateien: zwei Tasks, zwei Container oder einen Task und einen Container.</span><span class="sxs-lookup"><span data-stu-id="4a324-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="4a324-104">Sie werden als ausführbare Datei der Rangfolge und als eingeschränkte ausführbare Datei bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4a324-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="4a324-105">Eine eingeschränkte ausführbare Datei kann mehrere Rangfolgeneinschränkungen haben.</span><span class="sxs-lookup"><span data-stu-id="4a324-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="4a324-106">Weitere Informationen finden Sie unter [Rangfolgeneinschränkungen](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="4a324-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="4a324-107">Wenn Sie komplexe Einschränkungsszenarien durch Gruppieren von Einschränkungen zusammenfassen, können Sie eine komplexe Ablaufsteuerung in Paketen implementieren.</span><span class="sxs-lookup"><span data-stu-id="4a324-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="4a324-108">Beispielsweise ist in der folgenden Abbildung der Task D mit dem Task A durch eine `Success`-Einschränkung verlinkt, der Task D ist mit dem Task B durch eine `Failure`-Einschränkung verlinkt, und der Task D ist mit dem Task C durch eine `Success`-Einschränkung verlinkt.</span><span class="sxs-lookup"><span data-stu-id="4a324-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="4a324-109">Die Rangfolgeneinschränkungen zwischen Task D und Task A, zwischen Task D und Task B sowie zwischen Task D und Task C nehmen an einer logischen *AND* -Beziehung teil.</span><span class="sxs-lookup"><span data-stu-id="4a324-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="4a324-110">Damit Task D ausgeführt wird, muss Task A erfolgreich ausgeführt werden, bei Task B muss ein Fehler auftreten, und Task C muss erfolgreich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4a324-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="4a324-111">![Durch Rangfolgeneinschränkungen verknüpfte Tasks](media/precedenceconstraints.gif "Durch Rangfolgeneinschränkungen verknüpfte Tasks")</span><span class="sxs-lookup"><span data-stu-id="4a324-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="4a324-112">LogicalAnd-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="4a324-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="4a324-113">Falls ein Task oder ein Container mehrere Einschränkungen aufweist, gibt die `LogicalAnd`-Eigenschaft an, ob eine Rangfolgeneinschränkung einzeln oder zusammen mit anderen Einschränkungen ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4a324-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="4a324-114">Sie können die- `LogicalAnd` Eigenschaft mithilfe des Rangfolgeneinschränkungs- **Editors** im- [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer oder in der Eigenschaftenfenster festlegen, die [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="4a324-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4a324-115">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4a324-115">Related Tasks</span></span>  
 [<span data-ttu-id="4a324-116">Festlegen der Eigenschaften von Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="4a324-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
