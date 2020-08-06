---
title: Debuggen eines Skripts durch Festlegen von Breakpoints in einem Skripttask und einer Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615449"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="d55e6-102">Debuggen eines Skripts durch Festlegen von Breakpoints in einem Skripttask und einer Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="d55e6-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="d55e6-103">In diesem Verfahren wird beschrieben, wie Sie in den Skripts Breakpoints festlegen, die im Skripttask und in der Skriptkomponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d55e6-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="d55e6-104">Nachdem Sie im Skript Breakpoints festgelegt haben, werden im Dialogfeld **Breakpoints festlegen – \<object name>** die Breakpoints zusammen mit den integrierten Breakpoints aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d55e6-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d55e6-105">In bestimmten Fällen werden Breakpoints im Skripttask und in der Skriptkomponente ignoriert.</span><span class="sxs-lookup"><span data-stu-id="d55e6-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="d55e6-106">Weitere Informationen finden Sie im Abschnitt **Debuggen des Skript** Tasks in [Codieren und Debuggen des Skript](../control-flow/script-task.md) Tasks und im Abschnitt **Debuggen der Skript Komponente** unter [codieren und Debuggen der Skript Komponente] (.). /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="d55e6-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="d55e6-107">So legen Sie einen Breakpoint im Skript fest</span><span class="sxs-lookup"><span data-stu-id="d55e6-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="d55e6-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d55e6-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d55e6-109">Doppelklicken Sie auf das Paket mit dem Skript, in dem Sie Breakpoints festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="d55e6-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="d55e6-110">Um den Skripttask zu öffnen, klicken Sie auf die Registerkarte **Ablaufsteuerung**, und doppelklicken Sie dann auf den Skripttask.</span><span class="sxs-lookup"><span data-stu-id="d55e6-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="d55e6-111">Um die Skriptkomponente zu öffnen, klicken Sie auf die Registerkarte **Datenfluss**, und doppelklicken Sie dann auf die Skriptkomponente.</span><span class="sxs-lookup"><span data-stu-id="d55e6-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="d55e6-112">Klicken Sie auf **Skript** und dann auf **Skript bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d55e6-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="d55e6-113">Suchen Sie in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) die Skriptzeile, für die Sie einen Breakpoint festlegen möchten, klicken Sie mit der rechten Maustaste auf diese Zeile, zeigen Sie auf **Breakpoint**, und wählen Sie dann **Breakpoint einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d55e6-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="d55e6-114">Das Breakpointsymbol wird in der Codezeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d55e6-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="d55e6-115">Klicken Sie im Menü **Datei** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="d55e6-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="d55e6-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d55e6-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d55e6-117">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d55e6-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
