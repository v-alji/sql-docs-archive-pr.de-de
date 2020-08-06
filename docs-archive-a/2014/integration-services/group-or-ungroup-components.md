---
title: Gruppieren von Komponenten oder Aufheben der Gruppierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609328"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="d9ce9-102">Gruppieren von Komponenten oder Aufheben der Gruppierung</span><span class="sxs-lookup"><span data-stu-id="d9ce9-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="d9ce9-103">Die Registerkarten **Ablaufsteuerung**, **Datenfluss**und **Ereignishandler** im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer unterstützen die reduzierbare Gruppierung.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="d9ce9-104">Wenn ein Paket viele Komponenten enthält, kann dies zu einer Überlastung der Registerkarten führen. In diesem Fall ist es schwierig, alle Komponenten gleichzeitig anzuzeigen und das gewünschte Element zu finden.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="d9ce9-105">Mit der Funktion für reduzierbare Gruppierung kann Platz auf der Arbeitsoberfläche gespart und die Arbeit mit großen Paketen erleichtert werden.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="d9ce9-106">Sie wählen die Komponenten aus, die Sie gruppieren möchten, gruppieren sie und erweitern bzw. reduzieren dann die Gruppen entsprechend Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="d9ce9-107">Das Erweitern einer Gruppe ermöglicht den Zugriff auf die Eigenschaften der Komponenten in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="d9ce9-108">Die Rangfolgeneinschränkungen, die Tasks und Container verbinden, werden automatisch in die Gruppe eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="d9ce9-109">Folgende Überlegungen gelten im Zusammenhang mit dem Gruppieren von Komponenten.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="d9ce9-110">Um Komponenten gruppieren zu können, muss die Ablaufsteuerung, der Datenfluss oder der Ereignishandler mehrere Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="d9ce9-111">Gruppen können auch geschachtelt werden, wodurch Gruppen innerhalb von Gruppen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="d9ce9-112">Die Entwurfsoberfläche kann mehrere nicht geschachtelte Gruppen implementieren, eine Komponente kann aber nur einer Gruppe angehören, sofern die Gruppen nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="d9ce9-113">Wenn ein Paket gespeichert wird, speichert der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer die Gruppierung, diese hat jedoch keine Auswirkung auf die Paketausführung.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="d9ce9-114">Die Möglichkeit der Gruppierung von Komponenten ist eine Entwurfszeitfunktion. Das Laufzeitverhalten des Pakets ist nicht davon betroffen.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="d9ce9-115">So gruppieren Sie Komponenten</span><span class="sxs-lookup"><span data-stu-id="d9ce9-115">To group components</span></span>  
  
1.  <span data-ttu-id="d9ce9-116">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d9ce9-117">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d9ce9-118">Klicken Sie auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="d9ce9-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="d9ce9-119">Wählen Sie auf der Entwurfsoberfläche der Registerkarte die Komponenten aus, die Sie gruppieren möchten, klicken Sie mit der rechten Maustaste auf eine ausgewählte Komponente, und klicken Sie anschließend auf **Gruppieren**.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="d9ce9-120">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="d9ce9-121">So heben Sie die Gruppierung von Komponenten auf</span><span class="sxs-lookup"><span data-stu-id="d9ce9-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="d9ce9-122">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d9ce9-123">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d9ce9-124">Klicken Sie auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="d9ce9-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="d9ce9-125">Wählen Sie auf der Entwurfsoberfläche der Registerkarte die Gruppe mit der Komponente aus, deren Gruppierung Sie aufheben möchten, führen Sie einen Rechtsklick aus, und klicken Sie anschließend auf **Gruppierung aufheben**.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="d9ce9-126">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d9ce9-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ce9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9ce9-127">See Also</span></span>  
 [<span data-ttu-id="d9ce9-128">Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="d9ce9-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="d9ce9-129">Verbinden von Tasks und Containern mithilfe einer Standardrangfolgen-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="d9ce9-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
