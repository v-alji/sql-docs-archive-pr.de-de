---
title: Kopieren von Paketobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615499"
---
# <a name="copy-package-objects"></a><span data-ttu-id="a2c61-102">Kopieren von Paketobjekten</span><span class="sxs-lookup"><span data-stu-id="a2c61-102">Copy Package Objects</span></span>
  <span data-ttu-id="a2c61-103">In diesem Thema wird beschrieben, wie Sie Ablaufsteuerungs- und Datenflusselemente sowie Verbindungs-Manager innerhalb eines Pakets bzw. von einem Paket in ein anderes kopieren.</span><span class="sxs-lookup"><span data-stu-id="a2c61-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="a2c61-104">So kopieren Sie Ablaufsteuerungs- und Datenflusselemente</span><span class="sxs-lookup"><span data-stu-id="a2c61-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="a2c61-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, mit dem Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a2c61-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="a2c61-106">Doppelklicken Sie im Projektmappen-Explorer auf die Pakete, die untereinander kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a2c61-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="a2c61-107">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte des Pakets, in dem die zu kopierenden Elemente enthalten sind, und klicken Sie auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="a2c61-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="a2c61-108">Wählen Sie die zu kopierenden Ablaufsteuerungs- oder Datenflusselemente aus.</span><span class="sxs-lookup"><span data-stu-id="a2c61-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="a2c61-109">Sie können jeweils ein Element auswählen, indem Sie die UMSCHALTTASTE drücken und auf das Element klicken, oder die Elemente als eine Gruppe auswählen, indem Sie den Zeiger über die auszuwählenden Elemente ziehen.</span><span class="sxs-lookup"><span data-stu-id="a2c61-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a2c61-110">Die die Elemente verbindenden Rangfolgeneinschränkungen und Pfade werden bei Auswahl zwei verbundener Elemente nicht automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a2c61-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="a2c61-111">Stellen Sie sicher, dass Sie auch die Rangfolgeneinschränkungen und Pfade kopieren, damit ein geordneter Workflow, also ein Ablaufsteuerungs- oder Datenflusssegment, kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2c61-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="a2c61-112">Klicken Sie mit der rechten Maustaste auf ein ausgewähltes Element, und klicken Sie auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="a2c61-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="a2c61-113">Wenn Sie Elemente in ein anderes Paket kopieren, klicken Sie auf das Paket, in das kopiert werden soll, und klicken Sie dann auf die entsprechende Registerkarte des jeweiligen Elementtyps.</span><span class="sxs-lookup"><span data-stu-id="a2c61-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a2c61-114">Sie können einen Datenfluss nur in ein Paket kopieren, wenn das Paket mindestens einen Datenflusstask enthält.</span><span class="sxs-lookup"><span data-stu-id="a2c61-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="a2c61-115">Klicken Sie auf die rechte Maustaste, und klicken Sie auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="a2c61-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="a2c61-116">So kopieren Sie Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="a2c61-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="a2c61-117">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, mit dem Sie arbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a2c61-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="a2c61-118">Doppelklicken Sie im Projektmappen-Explorer auf das Paket.</span><span class="sxs-lookup"><span data-stu-id="a2c61-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="a2c61-119">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="a2c61-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="a2c61-120">Klicken Sie im Bereich **Verbindungs-Manager** mit der rechten Maustaste auf den Verbindungs-Manager, und klicken Sie anschließen auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="a2c61-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="a2c61-121">Sie können jeweils nur einen Verbindungs-Manager kopieren.</span><span class="sxs-lookup"><span data-stu-id="a2c61-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="a2c61-122">Wenn Sie Elemente in ein anderes Paket kopieren, klicken Sie auf das Paket, in das kopiert werden soll, und klicken Sie dann auf die Registerkarte **Ablaufsteuerung**, **Datenfluss**oder **Ereignishandler** .</span><span class="sxs-lookup"><span data-stu-id="a2c61-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="a2c61-123">Klicken Sie mit der rechten Maustaste in den Bereich **Verbindungs-Manager** , und klicken Sie auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="a2c61-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c61-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2c61-124">See Also</span></span>  
 <span data-ttu-id="a2c61-125">[Ablaufsteuerung](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a2c61-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="a2c61-126">[Datenfluss](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a2c61-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="a2c61-127">[Integration Services (SSIS) Connections (Integration Services-Verbindungen (SSIS))](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="a2c61-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="a2c61-128">Kopieren von Projektelementen</span><span class="sxs-lookup"><span data-stu-id="a2c61-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
