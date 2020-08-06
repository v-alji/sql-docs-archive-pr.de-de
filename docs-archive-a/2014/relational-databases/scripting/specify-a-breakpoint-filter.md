---
title: Angeben eines Breakpointfilters
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint filter
ms.assetid: 7bf1dddd-7b0b-4c47-8a7b-28a5569b4fa5
author: rothja
ms.author: jroth
ms.openlocfilehash: 9fc320397da1bddc0d28191c359c4d311b23e044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618620"
---
# <a name="specify-a-breakpoint-filter"></a><span data-ttu-id="7dd05-102">Angeben eines Breakpointfilters</span><span class="sxs-lookup"><span data-stu-id="7dd05-102">Specify a Breakpoint Filter</span></span>
  <span data-ttu-id="7dd05-103">Bei Verwendung eines Breakpointfilters wird ein Breakpoint nur auf angegebene Computer, Betriebssystemprozesse und Threads angewendet.</span><span class="sxs-lookup"><span data-stu-id="7dd05-103">A breakpoint filter limits the breakpoint to acting only on specified computers, operating system processes, and threads.</span></span> <span data-ttu-id="7dd05-104">Breakpointfilter werden meist beim Debuggen paralleler Anwendungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dd05-104">Breakpoint filters are typically used when debugging parallel applications.</span></span>  
  
##  <a name="filter-considerations"></a><a name="BKMK_ActionConsiderations"></a> <span data-ttu-id="7dd05-105">Filteraspekte</span><span class="sxs-lookup"><span data-stu-id="7dd05-105">Filter Considerations</span></span>  
 <span data-ttu-id="7dd05-106">Breakpointfilter werden selten mit dem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger verwendet, da es sich bei [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts und gespeicherte Prozeduren nicht um parallele Anwendungen handelt.</span><span class="sxs-lookup"><span data-stu-id="7dd05-106">Breakpoint filters are not typically used with the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger because [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and stored procedures are not parallel applications.</span></span>  
  
#### <a name="to-specify-a-breakpoint-filter"></a><span data-ttu-id="7dd05-107">So geben Sie einen Breakpointfilter an</span><span class="sxs-lookup"><span data-stu-id="7dd05-107">To Specify a Breakpoint Filter</span></span>  
  
1.  <span data-ttu-id="7dd05-108">Klicken Sie im Editor-Fenster mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Filter** .</span><span class="sxs-lookup"><span data-stu-id="7dd05-108">In the editor window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="7dd05-109">Oder</span><span class="sxs-lookup"><span data-stu-id="7dd05-109">-or-</span></span>  
  
     <span data-ttu-id="7dd05-110">Klicken Sie im Fenster **Breakpoint** mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Filter** .</span><span class="sxs-lookup"><span data-stu-id="7dd05-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Filter** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="7dd05-111">Geben Sie im Dialogfeld **Haltepunktfilter** im Feld **Filter** Computer mit Namen oder Betriebssystemprozesse und Threads mit Namen oder ID-Nummer an:</span><span class="sxs-lookup"><span data-stu-id="7dd05-111">In the **Breakpoint Filters** dialog box, use the **Filter** box to specify computers by name, or operating system processes and threads by either name or ID number:</span></span>  
  
    -   <span data-ttu-id="7dd05-112">`MachineName` gibt den Computer an, auf dem die Instanz der Datenbank-Engine ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7dd05-112">`MachineName` is the computer running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="7dd05-113">ph x="1" /&gt; und `ProcessName` geben den Betriebssystemprozess an, von dem die Instanz der Datenbank-Engine ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7dd05-113">`ProcessID`, and `ProcessName` are the operating system process running the instance of the Database Engine.</span></span>  
  
    -   <span data-ttu-id="7dd05-114">`ThreadID` und `ThreadName` geben den Betriebssystemthread an, unter dem der Batch, die Prozedur oder die Funktion von [!INCLUDE[tsql](../../includes/tsql-md.md)] in der Instanz der Datenbank-Engine ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7dd05-114">`ThreadID` and `ThreadName` are the operating system thread running the [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, procedure, or function in the instance of the Database Engine.</span></span>  
  
3.  <span data-ttu-id="7dd05-115">Klicken Sie auf **OK** , um die Änderungen zu implementieren, oder auf **Abbrechen** , um den Vorgang zu beenden, ohne die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7dd05-115">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd05-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7dd05-116">See Also</span></span>  
 <span data-ttu-id="7dd05-117">[Angeben einer Breakpointbedingung](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="7dd05-117">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 <span data-ttu-id="7dd05-118">[Angeben einer Trefferanzahl](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="7dd05-118">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="7dd05-119">Angeben einer Breakpointaktion</span><span class="sxs-lookup"><span data-stu-id="7dd05-119">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
