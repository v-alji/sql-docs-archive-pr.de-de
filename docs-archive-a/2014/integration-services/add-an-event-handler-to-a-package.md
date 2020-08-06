---
title: Hinzufügen eines Ereignis Handlers zu einem Paket | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- event handlers [Integration Services], creating
ms.assetid: 5e56885d-8658-480a-bed9-3f2f8003fd78
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 007d81a395e06ac5a97210cd3e3ed6eea91aee57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617259"
---
# <a name="add-an-event-handler-to-a-package"></a><span data-ttu-id="dcfa9-102">Hinzufügen eines Ereignishandlers zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="dcfa9-102">Add an Event Handler to a Package</span></span>
  <span data-ttu-id="dcfa9-103">Zur Laufzeit werden von Containern und Tasks Ereignisse ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-103">At run time, containers and tasks raise events.</span></span> <span data-ttu-id="dcfa9-104">Sie können benutzerdefinierte Ereignishandler erstellen, die auf diese Ereignisse antworten, indem Sie einen Workflow ausführen, wenn das Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-104">You can create custom event handlers that respond to these events by running a workflow when the event is raised.</span></span> <span data-ttu-id="dcfa9-105">Beispielsweise können Sie einen Ereignishandler erstellen, der eine E-Mail-Nachricht sendet, wenn bei einem Task ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-105">For example, you can create an event handler that sends an e-mail message when a task fails.</span></span>  
  
 <span data-ttu-id="dcfa9-106">Ein Ereignishandler ist mit einem Paket vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-106">An event handler is similar to a package.</span></span> <span data-ttu-id="dcfa9-107">Ein Ereignishandler kann wie ein Paket einen Bereich für Variablen bereitstellen und enthält eine Ablaufsteuerung und optionale Datenflüsse.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-107">Like a package, an event handler can provide scope for variables, and includes a control flow and optional data flows.</span></span> <span data-ttu-id="dcfa9-108">Sie können Ereignishandler für Pakete, den Foreach-Schleifencontainer, den For-Schleifencontainer, den Sequenzcontainer und alle Tasks erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-108">You can build event handlers for packages, the Foreach Loop container, the For Loop container, the Sequence container, and all tasks.</span></span>  
  
 <span data-ttu-id="dcfa9-109">Ereignishandler erstellen Sie mithilfe der Entwurfsoberfläche der Registerkarte **Ereignishandler** im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-109">You create event handlers by using the design surface of the **Event Handlers** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="dcfa9-110">Wenn die Registerkarte **Ereignishandler** aktiv ist, enthalten die Knoten **Ablaufsteuerungselemente** und **Wartungsplantasks** der Toolbox im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer den Task und die Container zum Erstellen der Ablaufsteuerung im Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-110">When the **Event Handlers** tab is active, the **Control Flow Items** and **Maintenance Plan Tasks** nodes of the Toolbox in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer contain the task and containers for building the control flow in the event handler.</span></span> <span data-ttu-id="dcfa9-111">Die Knoten **Datenflussquellen**, **Transformationen**und **Datenflussziele** enthalten die Datenquellen, Transformationen und Ziele zum Erstellen der Datenflüsse im Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-111">The **Data Flow Sources**, **Transformations**, **and Data Flow Destinations** nodes contain the data sources, transformations, and destinations for building the data flows in the event handler.</span></span> <span data-ttu-id="dcfa9-112">Weitere Informationen finden Sie unter [Control Flow](control-flow/control-flow.md) und [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa9-112">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="dcfa9-113">Die Registerkarte **Ereignishandler** enthält auch den Bereich **Verbindungs-Manager** , in dem Sie die Verbindungs-Manager erstellen und ändern können, mit deren Hilfe Ereignishandler eine Verbindung mit Servern und Datenquellen herstellen.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-113">The **Event Handlers** tab also includes the **Connections** Managers area where you can create and modify the connection managers that event handlers use to connect to servers and data sources.</span></span> <span data-ttu-id="dcfa9-114">Weitere Informationen finden Sie unter [Erstellen von Verbindungs-Managern](../../2014/integration-services/create-connection-managers.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa9-114">For more information, see [Create Connection Managers](../../2014/integration-services/create-connection-managers.md).</span></span>  
  
### <a name="to-create-an-event-handler"></a><span data-ttu-id="dcfa9-115">So erstellen Sie einen Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="dcfa9-115">To create an event handler</span></span>  
  
1.  <span data-ttu-id="dcfa9-116">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="dcfa9-117">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="dcfa9-118">Klicken Sie auf die Registerkarte **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="dcfa9-118">Click the **Event Handlers** tab.</span></span>  
  
     <span data-ttu-id="dcfa9-119">![Screenshot der Entwurfsoberfläche mit Ereignishandler](media/eventhandlers.gif "Screenshot der Entwurfsoberfläche mit Ereignishandler")</span><span class="sxs-lookup"><span data-stu-id="dcfa9-119">![Screenshot of design surface with event handler](media/eventhandlers.gif "Screenshot of design surface with event handler")</span></span>  
  
     <span data-ttu-id="dcfa9-120">Das Erstellen der Ablaufsteuerung und der Datenflüsse in einem Ereignishandler ist mit dem Erstellen der Ablaufsteuerung und der Datenflüsse in einem Paket vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-120">Creating the control flow and data flows in an event handler is similar to creating the control flow and data flows in a package.</span></span> <span data-ttu-id="dcfa9-121">Weitere Informationen finden Sie unter [Control Flow](control-flow/control-flow.md) und [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa9-121">For more information, see [Control Flow](control-flow/control-flow.md) and [Data Flow](data-flow/data-flow.md).</span></span>  
  
4.  <span data-ttu-id="dcfa9-122">Wählen Sie in der Liste **Ausführbare Datei** die ausführbare Datei aus, für die Sie einen Ereignishandler erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-122">In the **Executable** list, select the executable for which you want to create an event handler.</span></span>  
  
5.  <span data-ttu-id="dcfa9-123">Wählen Sie in der Liste **Ereignishandler** den Ereignishandler aus, den Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-123">In the **Event handler** list, select the event handler you want to build.</span></span>  
  
6.  <span data-ttu-id="dcfa9-124">Klicken Sie auf den Link auf der Entwurfsoberfläche der Registerkarte **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="dcfa9-124">Click the link on the design surface of the **Event Handler** tab.</span></span>  
  
7.  <span data-ttu-id="dcfa9-125">Fügen Sie dem Ereignishandler Ablaufsteuerungselemente hinzu, und verbinden Sie die Elemente mithilfe einer Rangfolgeneinschränkung, indem Sie die Einschränkung von einem Ablaufsteuerungselement auf ein anderes ziehen.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-125">Add control flow items to the event handler, and connect items using a precedence constraint by dragging the constraint from one control flow item to another.</span></span> <span data-ttu-id="dcfa9-126">Weitere Informationen finden Sie unter [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa9-126">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
8.  <span data-ttu-id="dcfa9-127">Fügen Sie wahlweise einen Datenfluss-Task hinzu, und erstellen Sie auf der Entwurfsoberfläche der Registerkarte **Datenfluss** einen Datenfluss für den Ereignis-Handler.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-127">Optionally, add a Data Flow task, and on the design surface of the **Data Flow** tab, create a data flow for the event handler.</span></span> <span data-ttu-id="dcfa9-128">Weitere Informationen finden Sie unter [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="dcfa9-128">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
9. <span data-ttu-id="dcfa9-129">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das neue Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dcfa9-129">On the **File** menu, click **Save Selected Items** to save the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfa9-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dcfa9-130">See Also</span></span>  
 <span data-ttu-id="dcfa9-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="dcfa9-131">[SQL Server Integration Services](../../2014/integration-services/sql-server-integration-services.md) </span></span>  
 [<span data-ttu-id="dcfa9-132">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="dcfa9-132">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
