---
title: Transact-SQL-Breakpoints
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620796"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="17055-102">Transact-SQL-Breakpoints</span><span class="sxs-lookup"><span data-stu-id="17055-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="17055-103">Haltepunkte legen fest, dass der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger die Ausführung bei einer bestimmten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung unterbricht. Sie können dann den Status der Codeelemente an diesem Punkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="17055-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="17055-104">Breakpoints</span><span class="sxs-lookup"><span data-stu-id="17055-104">Breakpoints</span></span>  
 <span data-ttu-id="17055-105">Wenn Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger ausführen, können Sie einen Haltepunkt auf bestimmten Anweisungen umschalten.</span><span class="sxs-lookup"><span data-stu-id="17055-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="17055-106">Wenn die Ausführung eine Anweisung mit einem Haltepunkt erreicht, hält der Debugger die Ausführung an, damit Sie Debuginformationen anzeigen können, z. B. die in Variablen und Parametern vorhandenen Werte.</span><span class="sxs-lookup"><span data-stu-id="17055-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="17055-107">Sie können Haltepunkte im Editorfenster einzeln verwalten, oder alle zusammen im Fenster **Haltepunkte** .</span><span class="sxs-lookup"><span data-stu-id="17055-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="17055-108">Sie können Haltepunkte bearbeiten, um bestimmte Elemente festzulegen, wie z. B. die speziellen Bedingungen, unter denen der Haltepunkt die Ausführung anhalten soll, oder die Aktionen, die beim Ausführen des Haltepunkts durchgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="17055-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="17055-109">Haltepunkttasks</span><span class="sxs-lookup"><span data-stu-id="17055-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="17055-110">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="17055-110">Task Description</span></span>|<span data-ttu-id="17055-111">Thema</span><span class="sxs-lookup"><span data-stu-id="17055-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="17055-112">Beschreibt, wie die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung angegeben wird, bei der der Debugger angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="17055-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="17055-113">Ein- und Ausschalten eines Breakpoints</span><span class="sxs-lookup"><span data-stu-id="17055-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="17055-114">Beschreibt, wie ein Haltepunkt vorübergehend deaktiviert und später erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="17055-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="17055-115">Beschreibt darüber hinaus, wie ein Haltepunkt gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="17055-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="17055-116">Aktivieren, Deaktivieren und Löschen von Breakpoints</span><span class="sxs-lookup"><span data-stu-id="17055-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="17055-117">Beschreibt, wie eine Bedingung angegeben wird, die definiert, ob Haltepunkte auf Grundlage der Auswertung eines angegebenen Transact-SQL-Ausdrucks unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="17055-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="17055-118">Angeben einer Breakpointbedingung</span><span class="sxs-lookup"><span data-stu-id="17055-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="17055-119">Beschreibt, wie eine Trefferanzahl festgelegt wird, die dazu führt, dass ein Haltepunkt nur dann unterbrochen wird, wenn die Anweisung, die den Haltepunkt enthält, mit einer festgelegten Häufigkeit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="17055-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="17055-120">Angeben einer Trefferanzahl</span><span class="sxs-lookup"><span data-stu-id="17055-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="17055-121">Beschreibt, wie ein Filter festgelegt wird, der bewirkt, dass ein Haltepunkt nur für angegebene Prozesse oder Threads unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="17055-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="17055-122">Angeben eines Breakpointfilters</span><span class="sxs-lookup"><span data-stu-id="17055-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="17055-123">Beschreibt, wie eine **Bei Treffer** -Aktion festgelegt wird, bei der es sich um einen Vorgang handelt, der beim Ausführen der Haltepunktanweisung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17055-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="17055-124">Ein Beispiel hierfür ist das Drucken einer Meldung.</span><span class="sxs-lookup"><span data-stu-id="17055-124">An example would be to print a message.</span></span>|[<span data-ttu-id="17055-125">Angeben einer Breakpointaktion</span><span class="sxs-lookup"><span data-stu-id="17055-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="17055-126">Beschreibt, wie die Position eines Haltepunkts bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="17055-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="17055-127">Bearbeiten einer Breakpointposition</span><span class="sxs-lookup"><span data-stu-id="17055-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="17055-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17055-128">See Also</span></span>  
 [<span data-ttu-id="17055-129">Transact-SQL-Debuggerinformationen</span><span class="sxs-lookup"><span data-stu-id="17055-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
