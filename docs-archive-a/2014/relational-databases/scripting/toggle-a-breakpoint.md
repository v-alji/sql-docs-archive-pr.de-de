---
title: Ein- und Ausschalten eines Breakpoints
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620797"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="49d3b-102">Ein- und Ausschalten eines Breakpoints</span><span class="sxs-lookup"><span data-stu-id="49d3b-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="49d3b-103">Das Festlegen eines Haltepunkts für eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wird als Umschalten eines Haltepunkts bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="49d3b-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="49d3b-104">Breakpoints</span><span class="sxs-lookup"><span data-stu-id="49d3b-104">Breakpoints</span></span>  
 <span data-ttu-id="49d3b-105">Sobald der Haltepunkt festgelegt wurde, wird er durch ein Symbol auf der grauen Leiste links von der Anweisung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="49d3b-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="49d3b-106">Das Symbol wird als Haltepunktsymbol bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="49d3b-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="49d3b-107">-Haltepunkte werden auf eine vollständige [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung angewendet.</span><span class="sxs-lookup"><span data-stu-id="49d3b-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="49d3b-108">Wenn ein Breakpoint eingeschaltet ist, hebt der Debugger die zugeordnete [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung hervor.</span><span class="sxs-lookup"><span data-stu-id="49d3b-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="49d3b-109">Wenn eine Zeile mehrere [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen enthält, können Sie für jede Anweisung einen Breakpoint umschalten.</span><span class="sxs-lookup"><span data-stu-id="49d3b-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="49d3b-110">Wenn Sie auf die graue Leiste auf der linken Seite des Fensters klicken, wird ein Breakpoint für die erste Anweisung in der Zeile umgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="49d3b-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="49d3b-111">Sie können einen Breakpoint in einer nachfolgenden Anweisung umschalten, indem Sie einen beliebigen Teil der Anweisung markieren oder den Cursor in die Anweisung bewegen und dann F9 drücken. Oder klicken Sie im Menü **Debuggen** auf **Haltepunkt ein/aus** .</span><span class="sxs-lookup"><span data-stu-id="49d3b-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="49d3b-112">Wenn eine Zeile mehrere Haltepunkte enthält, befindet sich links auf der grauen Leiste nur ein Haltepunktsymbol.</span><span class="sxs-lookup"><span data-stu-id="49d3b-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="49d3b-113">Nachdem ein Haltepunkt umgeschaltet wurde, können Sie verschiedene Aktionen für den Haltepunkt durchführen, z. B. seine Eigenschaften bearbeiten oder ihn vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="49d3b-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="49d3b-114">Weitere Informationen finden Sie weiter unten unter [Transact-SQL-Breakpoints](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="49d3b-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="49d3b-115">Ein- und Ausschalten eines Breakpoints</span><span class="sxs-lookup"><span data-stu-id="49d3b-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="49d3b-116">**So schalten Sie einen Haltepunkt in einer Transact-SQL-Anweisung um**</span><span class="sxs-lookup"><span data-stu-id="49d3b-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="49d3b-117">Klicken Sie auf die graue Leiste auf der linken Seite der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="49d3b-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="49d3b-118">Alternativ können Sie einen beliebigen Teil der Anweisung markieren oder den Cursor in die Anweisung bewegen, und dann eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="49d3b-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="49d3b-119">Drücken Sie F9.</span><span class="sxs-lookup"><span data-stu-id="49d3b-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="49d3b-120">Klicken Sie im Menü **Debuggen** auf **Haltepunkt ein/aus**.</span><span class="sxs-lookup"><span data-stu-id="49d3b-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
