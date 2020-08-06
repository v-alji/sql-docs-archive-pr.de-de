---
title: MSSQLSERVER_1204 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1204 (Database Engine error)
ms.assetid: de6ece78-79de-484d-9224-ca0f7645815f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ca03c19552b88e391d2de053193a70531571ece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617080"
---
# <a name="mssqlserver_1204"></a><span data-ttu-id="3f382-102">MSSQLSERVER_1204</span><span class="sxs-lookup"><span data-stu-id="3f382-102">MSSQLSERVER_1204</span></span>
    
## <a name="details"></a><span data-ttu-id="3f382-103">Details</span><span class="sxs-lookup"><span data-stu-id="3f382-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f382-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3f382-104">Product Name</span></span>|<span data-ttu-id="3f382-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f382-105">SQL Server</span></span>|  
|<span data-ttu-id="3f382-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3f382-106">Event ID</span></span>|<span data-ttu-id="3f382-107">1204</span><span class="sxs-lookup"><span data-stu-id="3f382-107">1204</span></span>|  
|<span data-ttu-id="3f382-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3f382-108">Event Source</span></span>|<span data-ttu-id="3f382-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3f382-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3f382-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3f382-110">Component</span></span>|<span data-ttu-id="3f382-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3f382-111">SQLEngine</span></span>|  
|<span data-ttu-id="3f382-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3f382-112">Symbolic Name</span></span>|<span data-ttu-id="3f382-113">LK_OUTOF</span><span class="sxs-lookup"><span data-stu-id="3f382-113">LK_OUTOF</span></span>|  
|<span data-ttu-id="3f382-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3f382-114">Message Text</span></span>|<span data-ttu-id="3f382-115">Die Instanz der SQL Server-Datenbank-Engine kann derzeit keine LOCK-Ressource erhalten.</span><span class="sxs-lookup"><span data-stu-id="3f382-115">The instance of the SQL Server Database Engine cannot obtain a LOCK resource at this time.</span></span> <span data-ttu-id="3f382-116">Führen Sie die Anweisung erneut aus, wenn die Zahl der aktiven Benutzer kleiner ist.</span><span class="sxs-lookup"><span data-stu-id="3f382-116">Rerun your statement when there are fewer active users.</span></span> <span data-ttu-id="3f382-117">Bitten Sie den Datenbankadministrator, die Konfiguration der Sperren und des Arbeitsspeichers für diese Instanz zu überprüfen oder nach lange andauernden Transaktionen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="3f382-117">Ask the database administrator to check the lock and memory configuration for this instance, or to check for long-running transactions.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f382-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3f382-118">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3f382-119">kann keine Sperrenressource erhalten.</span><span class="sxs-lookup"><span data-stu-id="3f382-119">cannot obtain a lock resource.</span></span> <span data-ttu-id="3f382-120">Dies kann eine der beiden folgenden Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="3f382-120">This can be caused by either of the following reasons:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3f382-121">kann keinen zusätzlichen Arbeitsspeicher vom Betriebssystem zuordnen, weil der Arbeitsspeicher von anderen Prozessen verwendet wird oder weil der Server mit der konfigurierten Option **Max. Serverarbeitsspeicher** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3f382-121">cannot allocate more memory from the operating system, either because other processes are using it, or because the server is operating with the **max server memory** option configured.</span></span>  
  
-   <span data-ttu-id="3f382-122">Der Sperren-Manager verwendet nicht mehr als 60 Prozent des für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verfügbaren Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="3f382-122">The lock manager will not use more than 60 percent of the memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f382-123">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3f382-123">User Action</span></span>  
 <span data-ttu-id="3f382-124">Wenn Sie vermuten, dass SQL Server nicht genügend Arbeitsspeicher zuordnen kann, können Sie folgende Maßnahmen durchführen:</span><span class="sxs-lookup"><span data-stu-id="3f382-124">If you suspect that SQL Server cannot allocate sufficient memory, try the following:</span></span>  
  
-   <span data-ttu-id="3f382-125">Wenn andere Anwendungen als SQL Server Ressourcen verbrauchen, versuchen Sie, diese Anwendungen zu beenden, oder führen Sie sie auf einem separaten Server aus.</span><span class="sxs-lookup"><span data-stu-id="3f382-125">If applications besides SQL Server are consuming resources, try stopping these applications or consider running them on a separate server.</span></span> <span data-ttu-id="3f382-126">Dadurch wird Arbeitsspeicher von anderen Prozessen für SQL Server freigegeben.</span><span class="sxs-lookup"><span data-stu-id="3f382-126">This will remove release memory from other processes for SQL Server.</span></span>  
  
-   <span data-ttu-id="3f382-127">Wenn Sie die Option Max. Serverarbeitsspeicher konfiguriert haben, erhöhen Sie die Einstellung für diese Option.</span><span class="sxs-lookup"><span data-stu-id="3f382-127">If you have configured max server memory, increase max server memory setting.</span></span>  
  
 <span data-ttu-id="3f382-128">Wenn Sie vermuten, dass der Sperren-Manager die maximale Menge an verfügbarem Arbeitsspeicher verwendet hat, identifizieren Sie die Transaktion, die die meisten Sperren aufrechterhält, und beenden Sie sie.</span><span class="sxs-lookup"><span data-stu-id="3f382-128">If you suspect that the lock manager has used the maximum amount of available memory identify the transaction that is holding the most locks and terminate it.</span></span> <span data-ttu-id="3f382-129">Das folgende Skript identifiziert die Transaktion mit den meisten Sperren:</span><span class="sxs-lookup"><span data-stu-id="3f382-129">The following script will identify the transaction with the most locks:</span></span>  
  
```  
SELECT request_session_id, COUNT (*) num_locks  
FROM sys.dm_tran_locks  
GROUP BY request_session_id   
ORDER BY count (*) DESC  
```  
  
 <span data-ttu-id="3f382-130">Nehmen Sie die höchste Sitzungs-ID, und beenden Sie sie mithilfe des KILL-Befehls.</span><span class="sxs-lookup"><span data-stu-id="3f382-130">Take the highest session id, and terminate it using the KILL command.</span></span>  
  
  
