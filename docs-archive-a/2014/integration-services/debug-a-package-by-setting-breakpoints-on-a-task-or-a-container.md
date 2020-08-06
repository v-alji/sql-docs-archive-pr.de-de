---
title: Debuggen eines Pakets durch Festlegen von Breakpoints für einen Task oder Container | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609967"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="ae529-102">Debuggen eines Pakets durch Festlegen von Breakpoints auf einem Task oder Container</span><span class="sxs-lookup"><span data-stu-id="ae529-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="ae529-103">In diesem Verfahren wird beschrieben, wie in einem Paket, Task, For-Schleifencontainer, Foreach-Schleifencontainer oder einem Sequenzcontainer Breakpoints festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ae529-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="ae529-104">So legen Sie Breakpoints in einem Paket, einem Task oder einem Container fest</span><span class="sxs-lookup"><span data-stu-id="ae529-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="ae529-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="ae529-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="ae529-106">Doppelklicken Sie auf das Paket, in dem Sie Breakpoints festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="ae529-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="ae529-107">Gehen Sie im SSIS-Designer wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ae529-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="ae529-108">Um Breakpoints im Paketobjekt festzulegen, klicken Sie auf die Registerkarte **Ablaufsteuerung,** setzen den Cursor an eine beliebige Stelle im Hintergrund der Entwurfsoberfläche, klicken mit der rechten Maustaste und wählen dann **Breakpoints bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ae529-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="ae529-109">Um Breakpoints in einer Paketablaufsteuerung festzulegen, klicken Sie auf die Registerkarte **Ablaufsteuerung** , klicken mit der rechten Maustaste auf einen Task, einen For-Schleifencontainer, einen Foreach-Schleifencontainer oder einen Sequenzcontainer und dann auf **Breakpoints bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ae529-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="ae529-110">Um Breakpoints in einem Ereignishandler festzulegen, klicken Sie auf die Registerkarte **Ereignishandler** , klicken mit der rechten Maustaste auf einen Task, einen For-Schleifencontainer, einen Foreach-Schleifencontainer oder einen Sequenzcontainer und dann auf **Breakpoints bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ae529-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="ae529-111">Wählen Sie im Dialogfeld **Breakpoints festlegen\<container name>** die zu aktivierenden Breakpoints aus.</span><span class="sxs-lookup"><span data-stu-id="ae529-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="ae529-112">Ändern Sie wahlweise den Typ der Trefferanzahl und die Trefferanzahl für jeden Breakpoint.</span><span class="sxs-lookup"><span data-stu-id="ae529-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="ae529-113">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ae529-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae529-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae529-114">See Also</span></span>  
 <span data-ttu-id="ae529-115">[Tools zur Problembehandlung für die Paketentwicklung](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="ae529-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="ae529-116">[Debuggen eines Skripts durch Festlegen von Breakpoints in einem Skript Task und einer Skript Komponente](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="ae529-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="ae529-117">[Codieren und Debuggen des Skript Tasks](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="ae529-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="ae529-118">Codieren und Debuggen der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="ae529-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
