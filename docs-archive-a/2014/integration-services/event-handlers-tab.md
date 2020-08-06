---
title: Registerkarte "Ereignishandler" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618809"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="2001f-102">Registerkarte Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="2001f-102">Event Handlers Tab</span></span>
  <span data-ttu-id="2001f-103">Verwenden Sie die Registerkarte **Ereignishandler** von [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer zum Erstellen eines Steuerungsflusses in einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="2001f-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="2001f-104">Ein Ereignishandler wird als Reaktion auf ein Ereignis ausgeführt, das von einem Paket, Task oder Container ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="2001f-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2001f-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2001f-105">Options</span></span>  
 <span data-ttu-id="2001f-106">**Ausführbare Datei**</span><span class="sxs-lookup"><span data-stu-id="2001f-106">**Executable**</span></span>  
 <span data-ttu-id="2001f-107">Wählen Sie die ausführbare Datei aus, für die Sie einen Ereignishandler erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2001f-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="2001f-108">Bei der ausführbaren Datei kann es sich um ein Paket, einen Task oder Container im Paket handeln.</span><span class="sxs-lookup"><span data-stu-id="2001f-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="2001f-109">**Ereignishandler**</span><span class="sxs-lookup"><span data-stu-id="2001f-109">**Event handler**</span></span>  
 <span data-ttu-id="2001f-110">Wählen Sie einen Typ von Ereignishandler aus.</span><span class="sxs-lookup"><span data-stu-id="2001f-110">Select a type of event handler.</span></span> <span data-ttu-id="2001f-111">Erstellen Sie den Ereignishandler, indem Sie Elemente aus der **Toolbox**ziehen.</span><span class="sxs-lookup"><span data-stu-id="2001f-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="2001f-112">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="2001f-112">**Delete**</span></span>  
 <span data-ttu-id="2001f-113">Wählen Sie einen Ereignishandler aus, und entfernen Sie ihn anschließend aus dem Paket, indem Sie auf **Löschen** klicken.</span><span class="sxs-lookup"><span data-stu-id="2001f-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="2001f-114">**Klicken Sie hier, um einen \<event handler name> für die ausführbare Datei \<executable name>** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2001f-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="2001f-115">Klicken Sie, um den Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2001f-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="2001f-116">Erstellen Sie den Steuerungsfluss, indem Sie grafische Objekte, die [!INCLUDE[ssIS](../includes/ssis-md.md)] -Tasks und -Container darstellen, aus der **Toolbox** auf die Entwurfsoberfläche der Registerkarte **Ereignishandler** ziehen und diese Objekte dann verbinden, indem Sie Rangfolgeneinschränkungen zum Definieren der Ausführungssequenz verwenden.</span><span class="sxs-lookup"><span data-stu-id="2001f-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="2001f-117">Klicken Sie außerdem mit der rechten Maustaste auf die Entwurfsoberfläche, um Anmerkungen hinzuzufügen, und klicken Sie anschließend im Menü auf **Anmerkung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2001f-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2001f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2001f-118">See Also</span></span>  
 <span data-ttu-id="2001f-119">[Integration Services-Ereignishandler &#40;SSIS&#41;](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="2001f-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="2001f-120">[Ablaufsteuerung](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="2001f-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="2001f-121">[SSIS-Designer](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2001f-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="2001f-122">Integration Services-Ereignishandler &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="2001f-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
