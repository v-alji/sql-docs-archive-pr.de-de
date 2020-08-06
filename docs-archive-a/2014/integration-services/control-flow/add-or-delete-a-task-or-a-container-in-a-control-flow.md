---
title: Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], adding
- adding tasks
- adding containers
- tasks [Integration Services], adding
ms.assetid: 653084c6-87a3-45d5-b458-914ecf24d56a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8338a4143358d732a974287e587f482dc5c36a22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618858"
---
# <a name="add-or-delete-a-task-or-a-container-in-a-control-flow"></a><span data-ttu-id="20f23-102">Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="20f23-102">Add or Delete a Task or a Container in a Control Flow</span></span>
  <span data-ttu-id="20f23-103">Wenn Sie im Ablaufsteuerungs-Designer arbeiten, werden in der Toolbox im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer die Tasks aufgeführt, die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zum Erstellen einer Ablaufsteuerung in einem Paket bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="20f23-103">When you are working in the control flow designer, the Toolbox in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer lists the tasks that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides for building control flow in a package.</span></span> <span data-ttu-id="20f23-104">Weitere Informationen über die Toolbox finden Sie unter [SSIS Toolbox](../ssis-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="20f23-104">For more information about the Toolbox, see [SSIS Toolbox](../ssis-toolbox.md).</span></span>  
  
 <span data-ttu-id="20f23-105">Ein Paket kann mehrere Instanzen desselben Tasks einschließen.</span><span class="sxs-lookup"><span data-stu-id="20f23-105">A package can include multiple instances of the same task.</span></span> <span data-ttu-id="20f23-106">Jede Instanz eines Tasks wird im Paket eindeutig identifiziert, und Sie können jede Instanz unterschiedlich konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="20f23-106">Each instance of a task is uniquely identified in the package, and you can configure each instance differently.</span></span>  
  
 <span data-ttu-id="20f23-107">Wenn Sie einen Task löschen, werden die Rangfolgeneinschränkungen, die den Task mit anderen Tasks und Container in der Ablaufsteuerung verbinden, ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="20f23-107">If you delete a task, the precedence constraints that connect the task to other tasks and containers in the control flow are also deleted.</span></span>  
  
 <span data-ttu-id="20f23-108">Im Folgenden wird beschrieben, wie ein Task oder Container zur Ablaufsteuerung eines Pakets hinzugefügt oder in dieser gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="20f23-108">The following procedures describe how to add or delete a task or container in the control flow of a package.</span></span>  
  
### <a name="to-add-a-task-or-a-container-to-a-control-flow"></a><span data-ttu-id="20f23-109">So fügen Sie einer Ablaufsteuerung einen Task oder Container hinzu</span><span class="sxs-lookup"><span data-stu-id="20f23-109">To add a task or a container to a control flow</span></span>  
  
1.  <span data-ttu-id="20f23-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="20f23-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="20f23-111">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20f23-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="20f23-112">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="20f23-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="20f23-113">Klicken Sie im Menü **Ansicht**auf **Toolbox** , um **Toolbox** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20f23-113">To open the **Toolbox**, click **Toolbox** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="20f23-114">Erweitern Sie **Ablaufsteuerungselemente** und **Wartungstasks**.</span><span class="sxs-lookup"><span data-stu-id="20f23-114">Expand **Control Flow Items** and **Maintenance Tasks**.</span></span>  
  
6.  <span data-ttu-id="20f23-115">Ziehen Sie Tasks und Container aus der **Toolbox** auf die Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="20f23-115">Drag tasks and containers from the **Toolbox** to the design surface of the **Control Flow** tab.</span></span>  
  
7.  <span data-ttu-id="20f23-116">Verbinden Sie einen Task oder Container innerhalb der Paketablaufsteuerung, indem Sie dessen Konnektor auf eine andere Komponente in der Ablaufsteuerung ziehen.</span><span class="sxs-lookup"><span data-stu-id="20f23-116">Connect a task or container within the package control flow by dragging its connector to another component in the control flow.</span></span>  
  
8.  <span data-ttu-id="20f23-117">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="20f23-117">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-task-or-a-container-from-a-control-flow"></a><span data-ttu-id="20f23-118">So löschen Sie einen Task oder Container aus einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="20f23-118">To delete a task or a container from a control flow</span></span>  
  
1.  <span data-ttu-id="20f23-119">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="20f23-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="20f23-120">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20f23-120">In Solution Explorer, double-click the package to open it.</span></span> <span data-ttu-id="20f23-121">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="20f23-121">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="20f23-122">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , klicken Sie mit der rechten Maustaste auf den Task oder Container, den Sie entfernen möchten, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="20f23-122">Click the **Control Flow** tab, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
    -   <span data-ttu-id="20f23-123">Öffnen Sie **Paket-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="20f23-123">Open **Package Explorer**.</span></span> <span data-ttu-id="20f23-124">Klicken Sie im Ordner **Ausführbare Dateien** mit der rechten Maustaste auf den Task oder Container, den Sie entfernen möchten, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="20f23-124">From the **Executables** folder, right-click the task or container that you want to remove, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="20f23-125">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="20f23-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f23-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20f23-126">See Also</span></span>  
 <span data-ttu-id="20f23-127">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="20f23-127">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 <span data-ttu-id="20f23-128">[Integration Services Container](integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="20f23-128">[Integration Services Containers](integration-services-containers.md) </span></span>  
 [<span data-ttu-id="20f23-129">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="20f23-129">Control Flow</span></span>](control-flow.md)  
  
  
