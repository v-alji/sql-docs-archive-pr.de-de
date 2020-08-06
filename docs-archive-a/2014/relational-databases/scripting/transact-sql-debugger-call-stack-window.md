---
title: Fenster 'Aufrufliste'
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: rothja
ms.author: jroth
ms.openlocfilehash: b4b72e484ade696be81ebac8ea4eed9be295edf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621454"
---
# <a name="call-stack-window"></a><span data-ttu-id="2a0e1-102">Fenster 'Aufrufliste'</span><span class="sxs-lookup"><span data-stu-id="2a0e1-102">Call Stack Window</span></span>
  <span data-ttu-id="2a0e1-103">Im Fenster **Aufrufliste** werden die Module in der Aufrufliste angezeigt sowie die Datentypen und die Werte aller Parameter, die an die Module übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-103">The **Call Stack** window displays the modules on the call stack, and the data types and values of any parameters that are passed to the modules.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="2a0e1-104">-Module umfassen gespeicherte Prozeduren, benutzerdefinierte Funktionen und Trigger.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-104">modules include stored procedures, functions, and triggers.</span></span> <span data-ttu-id="2a0e1-105">Um die Aufrufliste anzuzeigen, müssen Sie sich im Debugmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-105">To display the call stack, you must be in debug mode.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2a0e1-106">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="2a0e1-106">Task List</span></span>  
 <span data-ttu-id="2a0e1-107">**So greifen Sie auf das Fenster Aufrufliste zu**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-107">**To access the Call Stack window**</span></span>  
  
-   <span data-ttu-id="2a0e1-108">Klicken Sie im Menü **Debuggen** auf **Fenster**und dann auf **Aufrufliste**.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-108">On the **Debug** menu, click **Windows**, and then click **Call Stack**.</span></span>  
  
 <span data-ttu-id="2a0e1-109">**So ändern Sie den aktuellen Aufruflistenrahmen**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-109">**To change the current Call Stack frame**</span></span>  
  
 <span data-ttu-id="2a0e1-110">Sie können eine der folgenden Prozeduren verwenden, um einen Stapelrahmen zum aktuellen Rahmen zu machen:</span><span class="sxs-lookup"><span data-stu-id="2a0e1-110">You can use either of the following procedures to make a stack frame the current frame:</span></span>  
  
-   <span data-ttu-id="2a0e1-111">Klicken Sie mit der rechten Maustaste auf den Stapelrahmen, und klicken Sie dann auf **Zu Rahmen wechseln**.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-111">Right-click the stack frame, and then click **Switch To Frame**.</span></span>  
  
-   <span data-ttu-id="2a0e1-112">Doppelklicken Sie auf den Stapelrahmen.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-112">Double-click the stack frame.</span></span>  
  
 <span data-ttu-id="2a0e1-113">**So zeigen Sie die Quelle eines anderen Rahmens an, der nicht der aktuelle Rahmen ist**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-113">**To view the source of a frame other than the current frame**</span></span>  
  
-   <span data-ttu-id="2a0e1-114">Klicken Sie mit der rechten Maustaste auf den Stapelrahmen, und klicken Sie dann auf **Gehe zu Quellcode**.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-114">Right-click the stack frame, and then click **Go To Source Code**.</span></span>  
  
## <a name="stack-frames"></a><span data-ttu-id="2a0e1-115">Stapelrahmen</span><span class="sxs-lookup"><span data-stu-id="2a0e1-115">Stack Frames</span></span>  
 <span data-ttu-id="2a0e1-116">Jede Zeile im Fenster **Aufrufliste** wird als Stapelrahmen bezeichnet und stellt entweder einen Aufruf aus einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei zu einem Modul oder einen Aufruf von einem Modul zu einem anderen dar.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-116">Each row in the **Call Stack** window is called a stack frame and represents either a call from a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file to a module or a call from one module to another.</span></span> <span data-ttu-id="2a0e1-117">Der untere Stapelrahmen im Anzeigebereich gibt die Zeile im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fenster an, die den ersten Aufruf an den Stapel ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-117">The bottom stack frame in the display indicates the line in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window that made the first call into the stack.</span></span> <span data-ttu-id="2a0e1-118">Die oberste Zeile gibt die Zeile an, an der der Debugger die Ausführung angehalten hat und die am linken Rand des Fensters durch einen gelben Pfeil gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-118">The top row indicates the line on which the debugger paused execution, and is identified by a yellow arrow in the left margin of the window.</span></span> <span data-ttu-id="2a0e1-119">Jede dazwischen liegende Zeile gibt das Modul und die Zeilennummer des Quellcodes an, der den nächsthöheren Stapelrahmen aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-119">Each intermediate row indicates the module and the line number of the source code that called the next higher stack frame.</span></span>  
  
 <span data-ttu-id="2a0e1-120">Alle Ausdrücke in den Fenstern **Lokal**, **Überwachung**und **Schnellüberwachung** werden auf Grundlage des aktuellen Stapelrahmens ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-120">All expressions in the **Locals**, **Watch**, and **QuickWatch** windows are evaluated based on the current stack frame.</span></span> <span data-ttu-id="2a0e1-121">Im Abfrage-Editor-Fenster wird der Code für den aktuellen Rahmen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-121">The Query Editor window displays the code for the current frame.</span></span> <span data-ttu-id="2a0e1-122">Standardmäßig ist der aktuelle Stapelrahmen der Rahmen, in dem der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger die Ausführung angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-122">By default, the current stack frame is the frame in which the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger paused execution.</span></span> <span data-ttu-id="2a0e1-123">Wenn Sie den aktuellen Stapelrahmen zu einem anderen Rahmen ändern, werden die Ausdrücke in den Fenstern **Lokal**, **Überwachung**und **Schnellüberwachung** im Kontext des neuen Rahmens neu ausgewertet, und der Quellcode des neuen Rahmens wird im Abfrage-Editor-Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-123">When you change the current stack frame to another frame, the expressions in the **Locals**, **Watch**, and **QuickWatch** windows are reevaluated in the context of the new frame, and the source code of the new frame is displayed in the Query Editor window.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="2a0e1-124">Spalten</span><span class="sxs-lookup"><span data-stu-id="2a0e1-124">Columns</span></span>  
 <span data-ttu-id="2a0e1-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-125">**Name**</span></span>  
 <span data-ttu-id="2a0e1-126">Zeigt Informationen über ein Modul in der Aufrufliste an.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-126">Displays information about a module on the call stack.</span></span>  
  
 <span data-ttu-id="2a0e1-127">Für die letzte Zeile in der Aufrufliste werden unter **Name** das Abfrage-Editor-Quellcodefenster und die Zeilennummer des ersten Aufrufs an den Stapel aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-127">For the bottom row in the call stack, **Name** lists the Query Editor source window and line number of the first call into the stack.</span></span> <span data-ttu-id="2a0e1-128">Für die anderen Zeilen hat **Name** das Format **Modul(Instanz.Datenbank)(Parameterliste) Zeilennummer**.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-128">For the other rows, **Name** has the format **Module(Instance.Database)(ParmList) LineNumber**.</span></span>  
  
 <span data-ttu-id="2a0e1-129">**Modul**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-129">**Module**</span></span>  
 <span data-ttu-id="2a0e1-130">Der Name der gespeicherten Prozedur, Funktion oder gespeicherten Prozedur, die einen Aufruf zum nächsten Rahmen ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-130">Is the name of the stored procedure, function, or stored procedure that called to the next frame.</span></span>  
  
 <span data-ttu-id="2a0e1-131">**Instanz.Datenbank**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-131">**Instance.Database**</span></span>  
 <span data-ttu-id="2a0e1-132">Die Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] sowie die Datenbank, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-132">Is the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the database that is holding the module.</span></span>  
  
 <span data-ttu-id="2a0e1-133">**Parameterliste**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-133">**ParmList**</span></span>  
 <span data-ttu-id="2a0e1-134">Gibt für jeden Parameter, der während des Aufrufs an das Modul übergeben wird, den Datentyp, Namen und Wert an.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-134">Indicates the data type, name, and value for each parameter that is passed in during the call to the module.</span></span>  
  
 <span data-ttu-id="2a0e1-135">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-135">**LineNumber**</span></span>  
 <span data-ttu-id="2a0e1-136">Für alle Zeilen mit Ausnahme der obersten gibt **Zeilennummer** an, welche Zeile im Modul einen Aufruf zum Rahmen ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-136">For all rows except the top row, **LineNumber** indicates which line in the module called to the frame.</span></span> <span data-ttu-id="2a0e1-137">Für die oberste Zeile gibt **Zeilennummer** die Zeile an, auf die der Debugger gerade fokussiert ist.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-137">For the top row, **LineNumber** indicates the line on which the debugger is currently focused.</span></span>  
  
 <span data-ttu-id="2a0e1-138">**Sprache**</span><span class="sxs-lookup"><span data-stu-id="2a0e1-138">**Language**</span></span>  
 <span data-ttu-id="2a0e1-139">Zeigt **Transact-SQL** für [!INCLUDE[tsql](../../includes/tsql-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="2a0e1-139">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0e1-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a0e1-140">See Also</span></span>  
 <span data-ttu-id="2a0e1-141">[Transact-SQL-Debugger](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="2a0e1-141">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="2a0e1-142">[Informationen zum Transact-SQL-Debugger](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="2a0e1-142">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 [<span data-ttu-id="2a0e1-143">Schrittweises Durchlaufen von Transact-SQL-Code</span><span class="sxs-lookup"><span data-stu-id="2a0e1-143">Step Through Transact-SQL Code</span></span>](step-through-transact-sql-code.md)  
