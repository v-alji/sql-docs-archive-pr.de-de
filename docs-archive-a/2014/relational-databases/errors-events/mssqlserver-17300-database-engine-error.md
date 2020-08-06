---
title: MSSQLSERVER_17300 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17300 (Database Engine error)
ms.assetid: c1d6bfb6-28af-4df6-8087-25807602d282
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f77e39c71901166085d011d6d00f9a4a379bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696905"
---
# <a name="mssqlserver_17300"></a><span data-ttu-id="67aa7-102">MSSQLSERVER_17300</span><span class="sxs-lookup"><span data-stu-id="67aa7-102">MSSQLSERVER_17300</span></span>
    
## <a name="details"></a><span data-ttu-id="67aa7-103">Details</span><span class="sxs-lookup"><span data-stu-id="67aa7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67aa7-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="67aa7-104">Product Name</span></span>|<span data-ttu-id="67aa7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="67aa7-105">SQL Server</span></span>|  
|<span data-ttu-id="67aa7-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="67aa7-106">Event ID</span></span>|<span data-ttu-id="67aa7-107">17300</span><span class="sxs-lookup"><span data-stu-id="67aa7-107">17300</span></span>|  
|<span data-ttu-id="67aa7-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="67aa7-108">Event Source</span></span>|<span data-ttu-id="67aa7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="67aa7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="67aa7-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="67aa7-110">Component</span></span>|<span data-ttu-id="67aa7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="67aa7-111">SQLEngine</span></span>|  
|<span data-ttu-id="67aa7-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="67aa7-112">Symbolic Name</span></span>|<span data-ttu-id="67aa7-113">PROC_OUT_OF_SYSTASK_SESSIONS</span><span class="sxs-lookup"><span data-stu-id="67aa7-113">PROC_OUT_OF_SYSTASK_SESSIONS</span></span>|  
|<span data-ttu-id="67aa7-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="67aa7-114">Message Text</span></span>|<span data-ttu-id="67aa7-115">Der SQL Server war nicht in der Lage, einen neuen Systemtask auszuführen, entweder aufgrund von unzureichendem Speicher oder weil die Anzahl der konfigurierten Sitzungen die maximale Anzahl der auf dem Server zulässigen Sitzungen übersteigt.</span><span class="sxs-lookup"><span data-stu-id="67aa7-115">SQL Server was unable to run a new system task, either because there is insufficient memory or the number of configured sessions exceeds the maximum allowed in the server.</span></span> <span data-ttu-id="67aa7-116">Überprüfen Sie, ob der Server über ausreichenden Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="67aa7-116">Verify that the server has adequate memory.</span></span> <span data-ttu-id="67aa7-117">Sie können mithilfe von sp_configure und der Option ‚Benutzerverbindungen’ die maximale Anzahl der zulässigen Benutzerverbindungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="67aa7-117">Use sp_configure with option 'user connections' to check the maximum number of user connections allowed.</span></span> <span data-ttu-id="67aa7-118">Verwenden Sie sys.dm_exec_sessions, um die aktuelle Anzahl von Sitzungen einschließlich der Benutzerprozesse zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="67aa7-118">Use sys.dm_exec_sessions to check the current number of sessions, including user processes.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67aa7-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="67aa7-119">Explanation</span></span>  
 <span data-ttu-id="67aa7-120">Die Ausführung eines neuen Systemtasks ist aufgrund von unzureichendem Speicher oder weil die Anzahl der konfigurierten Sitzungen auf dem Server überschritten wurde, fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="67aa7-120">An attempt to run a new system task failed because of insufficient memory or because the number of configured sessions in the server was exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67aa7-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="67aa7-121">User Action</span></span>  
 <span data-ttu-id="67aa7-122">Überprüfen Sie, ob der Server über ausreichenden Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="67aa7-122">Verify that the server has enough memory.</span></span> <span data-ttu-id="67aa7-123">Überprüfen Sie die aktuelle Anzahl von Systemtasks mit sys.dm_exec_sessions und überprüfen Sie den konfigurierten Wert der maximalen Anzahl von Benutzerverbindungen mit sp_configure.</span><span class="sxs-lookup"><span data-stu-id="67aa7-123">Verify the current number of system tasks by using sys.dm_exec_sessions, and verify the configured value of maximum user connections by using sp_configure.</span></span>  
  
 <span data-ttu-id="67aa7-124">Führen Sie die folgenden Tasks entsprechend aus:</span><span class="sxs-lookup"><span data-stu-id="67aa7-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="67aa7-125">Fügen Sie dem Server mehr Arbeitsspeicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="67aa7-125">Add more memory to the server.</span></span>  
  
-   <span data-ttu-id="67aa7-126">Beenden Sie eine oder mehrere Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="67aa7-126">Terminate one or more sessions.</span></span>  
  
-   <span data-ttu-id="67aa7-127">Erhöhen Sie die maximal zulässige Anzahl von Benutzerverbindungen auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="67aa7-127">Increase the maximum number of user connections allowed on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67aa7-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67aa7-128">See Also</span></span>  
 <span data-ttu-id="67aa7-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67aa7-129">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="67aa7-130">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="67aa7-130">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="67aa7-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67aa7-131">[sys.dm_exec_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) </span></span>  
 <span data-ttu-id="67aa7-132">[Konfigurieren der Server Konfigurations Option "Benutzer Verbindungen"](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="67aa7-132">[Configure the user connections Server Configuration Option](../../database-engine/configure-windows/configure-the-user-connections-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="67aa7-133">KILL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67aa7-133">KILL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/kill-transact-sql)  
  
  
