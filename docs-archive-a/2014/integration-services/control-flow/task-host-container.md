---
title: Taskhostcontainer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.taskhostcontainer.f1
helpviewer_keywords:
- containers [Integration Services], Task Host
- Task Host container
ms.assetid: 7394a2c2-1b07-427d-b94a-9792e7783d35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4429d564cea0f08d5c2408199a8f1837b38389b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621122"
---
# <a name="task-host-container"></a><span data-ttu-id="f04a5-102">Taskhostcontainer</span><span class="sxs-lookup"><span data-stu-id="f04a5-102">Task Host Container</span></span>
  <span data-ttu-id="f04a5-103">Der Taskhostcontainer kapselt einen einzelnen Task.</span><span class="sxs-lookup"><span data-stu-id="f04a5-103">The task host container encapsulates a single task.</span></span> <span data-ttu-id="f04a5-104">Im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer wird der Taskhost nicht separat konfiguriert. Er wird stattdessen konfiguriert, wenn Sie die Eigenschaften des gekapselten Tasks festlegen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-104">In [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the task host is not configured separately; instead, it is configured when you set the properties of the task it encapsulates.</span></span> <span data-ttu-id="f04a5-105">Weitere Informationen zu den Tasks, die die Taskhostcontainer kapseln, finden Sie unter [Integration Services Tasks](integration-services-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-105">For more information about the tasks that the task host containers encapsulate, see [Integration Services Tasks](integration-services-tasks.md).</span></span>  
  
 <span data-ttu-id="f04a5-106">Dieser Container erweitert die Verwendung von Variablen und Ereignishandlern auf die Taskebene.</span><span class="sxs-lookup"><span data-stu-id="f04a5-106">This container extends the use of variables and event handlers to the task level.</span></span> <span data-ttu-id="f04a5-107">Weitere Informationen finden Sie unter [Integration Services-Ereignishandler &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) und [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-107">For more information, see [Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) and [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md).</span></span>  
  
## <a name="configuration-of-the-task-host"></a><span data-ttu-id="f04a5-108">Konfiguration des Taskhosts</span><span class="sxs-lookup"><span data-stu-id="f04a5-108">Configuration of the Task Host</span></span>  
 <span data-ttu-id="f04a5-109">Eigenschaften können Sie im Fenster **Eigenschaften** von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="f04a5-109">You can set properties in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or programmatically.</span></span>  
  
 <span data-ttu-id="f04a5-110">Informationen über die Festlegung dieser Eigenschaften in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="f04a5-110">For information about setting these properties in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
 <span data-ttu-id="f04a5-111">Weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span><span class="sxs-lookup"><span data-stu-id="f04a5-111">For information about programmatically setting these properties, see <xref:Microsoft.SqlServer.Dts.Runtime.TaskHost>.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f04a5-112">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f04a5-112">Related Tasks</span></span>  
  
-   [<span data-ttu-id="f04a5-113">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="f04a5-113">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="f04a5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f04a5-114">See Also</span></span>  
 [<span data-ttu-id="f04a5-115">SQL Server Integration Services-Container</span><span class="sxs-lookup"><span data-stu-id="f04a5-115">Integration Services Containers</span></span>](integration-services-containers.md)  
  
  
