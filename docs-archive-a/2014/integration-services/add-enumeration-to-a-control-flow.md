---
title: Hinzufügen einer Enumeration zu einer Ablauf Steuerung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding enumerations
- Foreach Loop containers
- control flow [Integration Services], enumerations
- repeating workflows
- enumerations [Integration Services]
ms.assetid: f212b5fb-3cc4-422e-9b7c-89eb769a812a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59b8569880fdf1a49f5f2ca1f6841841f9790af6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617247"
---
# <a name="add-enumeration-to-a-control-flow"></a><span data-ttu-id="8ec80-102">Hinzufügen einer Enumeration zu einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="8ec80-102">Add Enumeration to a Control Flow</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8ec80-103">umfasst den Foreach-Schleifencontainer. Dabei handelt es sich um ein Ablaufsteuerungselement, mit dem Sie auf einfache Weise eine Schleifenkonstruktion zum Aufzählen der Dateien und Objekte in der Ablaufsteuerung eines Pakets einbinden können.</span><span class="sxs-lookup"><span data-stu-id="8ec80-103">includes the Foreach Loop container, a control flow element that makes it simple to include a looping construct that enumerates files and objects in the control flow of a package.</span></span> <span data-ttu-id="8ec80-104">Weitere Informationen finden Sie unter [Foreach-Schleifencontainer](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8ec80-104">For more information, see [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="8ec80-105">Der Foreach-Schleifencontainer bietet keine Funktionalität, sondern stellt lediglich eine Struktur bereit, in der Sie eine wiederholbare Ablaufsteuerung erstellen, einen Enumeratortyp angeben und den Enumerator konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ec80-105">The Foreach Loop container provides no functionality; it provides only the structure in which you build the repeatable control flow, specify an enumerator type, and configure the enumerator.</span></span> <span data-ttu-id="8ec80-106">Sie müssen mindestens einen Task in den Foreach-Schleifencontainer einschließen, um eine Containerfunktionalität bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8ec80-106">To provide container functionality, you must include at least one task in the Foreach Loop container.</span></span> <span data-ttu-id="8ec80-107">Weitere Informationen finden Sie unter [Integration Services-Tasks](control-flow/integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8ec80-107">For more information, see [Integration Services Tasks](control-flow/integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="8ec80-108">Der Foreach-Schleifencontainer kann eine Ablaufsteuerung mit mehreren Tasks und weiteren Containern einschließen.</span><span class="sxs-lookup"><span data-stu-id="8ec80-108">The Foreach Loop container can include a control flow with multiple tasks and other containers.</span></span> <span data-ttu-id="8ec80-109">Das Hinzufügen von Tasks und Containern zu einem Foreach-Schleifencontainer ähnelt dem Hinzufügen von Tasks und Containern zu einem Paket, nur ziehen Sie die Tasks und Container nicht auf das Paket, sondern auf den Foreach-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="8ec80-109">Adding tasks and containers to a Foreach Loop container is similar to adding them to a package, except you drag the tasks and containers to the Foreach Loop container instead of to the package.</span></span> <span data-ttu-id="8ec80-110">Falls der Foreach-Schleifencontainer mehrere Tasks oder Container umfasst, können Sie diese wie bei einem Paket mithilfe von Rangfolgeneinschränkungen verbinden.</span><span class="sxs-lookup"><span data-stu-id="8ec80-110">If the Foreach Loop container includes more than one task or container, you can connect them using precedence constraints just as you do in a package.</span></span> <span data-ttu-id="8ec80-111">Weitere Informationen finden Sie unter [Rangfolgeneinschränkungen](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="8ec80-111">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
### <a name="to-implement-a-foreach-loop-container-in-a-control-flow"></a><span data-ttu-id="8ec80-112">So implementieren Sie einen Foreach-Schleifencontainer in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="8ec80-112">To implement a Foreach Loop container in a control flow</span></span>  
  
1.  <span data-ttu-id="8ec80-113">Fügen Sie den Foreach-Schleifencontainer zum Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ec80-113">Add the Foreach Loop container to the package.</span></span> <span data-ttu-id="8ec80-114">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablauf Steuerung](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="8ec80-114">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="8ec80-115">.</span><span class="sxs-lookup"><span data-stu-id="8ec80-115">.</span></span>  
  
2.  <span data-ttu-id="8ec80-116">Fügen Sie dem Foreach-Schleifencontainer Tasks und Container hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ec80-116">Add tasks and containers to the Foreach Loop container.</span></span> <span data-ttu-id="8ec80-117">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablauf Steuerung](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .</span><span class="sxs-lookup"><span data-stu-id="8ec80-117">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="8ec80-118">.</span><span class="sxs-lookup"><span data-stu-id="8ec80-118">.</span></span>  
  
3.  <span data-ttu-id="8ec80-119">Verbinden Sie Tasks und Container im Foreach-Schleifencontainer mithilfe von Rangfolgeneinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="8ec80-119">Connect tasks and containers in the Foreach Loop container using precedence constraints.</span></span> <span data-ttu-id="8ec80-120">Weitere Informationen finden Sie unter [Verbinden von Tasks und Containern mithilfe einer Standardrangfolgeneinschränkung](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="8ec80-120">For more information, see [Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md).</span></span>  
  
4.  <span data-ttu-id="8ec80-121">Konfigurieren Sie den Foreach-Schleifencontainer.</span><span class="sxs-lookup"><span data-stu-id="8ec80-121">Configure the Foreach Loop container.</span></span> <span data-ttu-id="8ec80-122">Weitere Informationen finden Sie unter [Konfigurieren eines Foreach-Schleifencontainers](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8ec80-122">For more information, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec80-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ec80-123">See Also</span></span>  
 <span data-ttu-id="8ec80-124">[Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablauf Steuerung](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8ec80-124">[Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) </span></span>  
 <span data-ttu-id="8ec80-125">[Gruppieren oder Deaktivieren von Komponenten](group-or-ungroup-components.md) </span><span class="sxs-lookup"><span data-stu-id="8ec80-125">[Group or Ungroup Components](group-or-ungroup-components.md) </span></span>  
 <span data-ttu-id="8ec80-126">[Rang folgen Einschränkungen](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="8ec80-126">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="8ec80-127">[Hinzufügen einer Iterationen zu einer Ablauf Steuerung](add-iteration-to-a-control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="8ec80-127">[Add Iteration to a Control Flow](add-iteration-to-a-control-flow.md) </span></span>  
 [<span data-ttu-id="8ec80-128">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="8ec80-128">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
