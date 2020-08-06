---
title: Fenster 'Threads'
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697874"
---
# <a name="threads-window"></a><span data-ttu-id="efa49-102">Fenster 'Threads'</span><span class="sxs-lookup"><span data-stu-id="efa49-102">Threads Window</span></span>
  <span data-ttu-id="efa49-103">Im Fenster **Threads** werden Informationen zu dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Thread angezeigt, der von der gerade gedebuggten [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efa49-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="efa49-104">Sie müssen sich im Debugmodus befinden, um die Threadinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="efa49-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="efa49-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="efa49-105">Task List</span></span>  
 <span data-ttu-id="efa49-106">**So greifen Sie auf das Threadfenster zu**</span><span class="sxs-lookup"><span data-stu-id="efa49-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="efa49-107">Klicken Sie im Menü **Debuggen** auf **Fenster**und dann auf **Threads**.</span><span class="sxs-lookup"><span data-stu-id="efa49-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="efa49-108">Spalten</span><span class="sxs-lookup"><span data-stu-id="efa49-108">Columns</span></span>  
 <span data-ttu-id="efa49-109">**ID**</span><span class="sxs-lookup"><span data-stu-id="efa49-109">**ID**</span></span>  
 <span data-ttu-id="efa49-110">Ist eine eindeutig kennzeichnende Zahl, die der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger dem Thread zuweist.</span><span class="sxs-lookup"><span data-stu-id="efa49-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="efa49-111">Um weitere Informationen zum Thread anzuzeigen, wählen Sie in der dynamischen Verwaltungssicht sys.dm_os_threads eine Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="efa49-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="efa49-112">Wenn die Ausführung nicht im Lightweightpooling-Modus erfolgt, wählen Sie die Zeile aus, in der der Wert in „os_thread_id“ mit dem Wert in der Spalte **ID** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="efa49-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="efa49-113">Wenn die Ausführung im Lightweightpooling-Modus erfolgt, wählen Sie die Zeile aus, in der der Wert in „fiber_context_address“ mit dem Wert in der Spalte **ID** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="efa49-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="efa49-114">**Name**</span><span class="sxs-lookup"><span data-stu-id="efa49-114">**Name**</span></span>  
 <span data-ttu-id="efa49-115">Zeigt Informationen über die [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Sitzung im Format **ComputerName/InstanceName [SPID]** an.</span><span class="sxs-lookup"><span data-stu-id="efa49-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="efa49-116">**Computername**</span><span class="sxs-lookup"><span data-stu-id="efa49-116">**ComputerName**</span></span>  
 <span data-ttu-id="efa49-117">Der Name des Computers, auf dem die Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] ausgeführt wird, mit der die Abfrage-Editor-Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="efa49-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="efa49-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="efa49-118">**InstanceName**</span></span>  
 <span data-ttu-id="efa49-119">Der Name der Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] , mit der die Abfrage-Editor-Sitzung verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="efa49-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="efa49-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="efa49-120">**[SPID]**</span></span>  
 <span data-ttu-id="efa49-121">Die Prozess-ID der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sitzung, die diese Sitzung eindeutig kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="efa49-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="efa49-122">Weitere Informationen über die Sitzung können Sie abrufen, indem Sie in der sys.sysprocesses-Sicht die Zeile auswählen, die in der Spalte spid denselben Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="efa49-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="efa49-123">**Location**</span><span class="sxs-lookup"><span data-stu-id="efa49-123">**Location**</span></span>  
 <span data-ttu-id="efa49-124">Zeigt den Namen der Skriptdatei an, die von der gerade gedebuggten Abfrage-Editor-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="efa49-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="efa49-125">**Priority**</span><span class="sxs-lookup"><span data-stu-id="efa49-125">**Priority**</span></span>  
 <span data-ttu-id="efa49-126">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger unterstützt diese Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="efa49-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="efa49-127">**Angehalten**</span><span class="sxs-lookup"><span data-stu-id="efa49-127">**Suspend**</span></span>  
 <span data-ttu-id="efa49-128">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger unterstützt diese Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="efa49-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa49-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efa49-129">See Also</span></span>  
 <span data-ttu-id="efa49-130">[Transact-SQL-Debugger](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="efa49-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="efa49-131">[Transact-SQL-Debuggerinformationen](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="efa49-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="efa49-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efa49-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="efa49-133">sys.sysprocesses &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="efa49-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
