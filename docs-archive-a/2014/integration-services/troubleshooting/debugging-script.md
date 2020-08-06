---
title: Debuggen von Skript | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721566"
---
# <a name="debugging-script"></a><span data-ttu-id="aea3d-102">Debuggen von Skript</span><span class="sxs-lookup"><span data-stu-id="aea3d-102">Debugging Script</span></span>
  <span data-ttu-id="aea3d-103">Sie erstellen in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) die Skripts, die vom Skripttask und der Skriptkomponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aea3d-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="aea3d-104">Sie legen Breakpoints in VSTA fest und erstellen sie.</span><span class="sxs-lookup"><span data-stu-id="aea3d-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="aea3d-105">Breakpoints können in VSTA sowie im Dialogfeld **Breakpoints festlegen** des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="aea3d-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="aea3d-106">Weitere Informationen finden Sie unter [Debugging Control Flow](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="aea3d-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="aea3d-107">Das Dialogfeld **Breakpoints festlegen** schließt die Skriptbreakpoints ein.</span><span class="sxs-lookup"><span data-stu-id="aea3d-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="aea3d-108">Diese Breakpoints werden am Ende der Breakpointliste angezeigt und enthalten die Zeilennummer und den Namen der Funktion, in der der Breakpoint vorkommt.</span><span class="sxs-lookup"><span data-stu-id="aea3d-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="aea3d-109">Skriptbreakpoints können Sie im Dialogfeld **Breakpoints festlegen** löschen.</span><span class="sxs-lookup"><span data-stu-id="aea3d-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="aea3d-110">Zur Laufzeit werden die Breakpoints, die in Codezeilen im Skript festgelegt sind, in die Breakpoints integriert, die für das Paket oder die Tasks und Container im Paket festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="aea3d-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="aea3d-111">Der Debugger kann ab einem Breakpoint im Skript bis zu einem für das Paket, den Task oder den Container festgelegten Breakpoint ausgeführt werden, oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="aea3d-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="aea3d-112">Beispielsweise können für ein Paket Breakpoints für die Unterbrechungsbedingungen festgelegt sein, die auftreten, wenn das Paket die Ereignisse **OnPreExecute** und **OnPostExecute** empfängt, und die auch einen Skripttask mit Breakpoints in den Skriptzeilen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="aea3d-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="aea3d-113">In diesem Szenario kann die Ausführung vom Paket an der Unterbrechungsbedingung angehalten werden, die dem **OnPreExecute** -Ereignis zugeordnet ist, bis zu den Breakpoints im Skript ausgeführt werden und schließlich bis zur Unterbrechungsbedingung ausgeführt werden, die dem **OnPostExecute** -Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="aea3d-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="aea3d-114">Weitere Informationen zum Debuggen des Skripttasks und der Skriptkomponente finden Sie unter [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) und [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="aea3d-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="aea3d-115">So legen Sie in Visual Studio für Applikationen einen Breakpoint fest</span><span class="sxs-lookup"><span data-stu-id="aea3d-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="aea3d-116">Debuggen eines Skripts durch Festlegen von Breakpoints in einem Skripttask und einer Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="aea3d-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="aea3d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aea3d-117">See Also</span></span>  
 [<span data-ttu-id="aea3d-118">Tools zur Problembehandlung für die Paketentwicklung</span><span class="sxs-lookup"><span data-stu-id="aea3d-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
