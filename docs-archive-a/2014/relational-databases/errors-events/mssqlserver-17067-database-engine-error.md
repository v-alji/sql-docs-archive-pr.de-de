---
title: MSSQLSERVER_17067 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17067 (Database Engine error)
ms.assetid: 32c1f0e8-db70-4836-95b2-8833be9e0ad1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4ff3de7ed2fbe54a32aaa501979a3acb6b452947
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620936"
---
# <a name="mssqlserver_17067"></a><span data-ttu-id="3f6f0-102">MSSQLSERVER_17067</span><span class="sxs-lookup"><span data-stu-id="3f6f0-102">MSSQLSERVER_17067</span></span>
    
## <a name="details"></a><span data-ttu-id="3f6f0-103">Details</span><span class="sxs-lookup"><span data-stu-id="3f6f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f6f0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3f6f0-104">Product Name</span></span>|<span data-ttu-id="3f6f0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f6f0-105">SQL Server</span></span>|  
|<span data-ttu-id="3f6f0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3f6f0-106">Event ID</span></span>|<span data-ttu-id="3f6f0-107">17067</span><span class="sxs-lookup"><span data-stu-id="3f6f0-107">17067</span></span>|  
|<span data-ttu-id="3f6f0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3f6f0-108">Event Source</span></span>|<span data-ttu-id="3f6f0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3f6f0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3f6f0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3f6f0-110">Component</span></span>|<span data-ttu-id="3f6f0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3f6f0-111">SQLEngine</span></span>|  
|<span data-ttu-id="3f6f0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3f6f0-112">Symbolic Name</span></span>|<span data-ttu-id="3f6f0-113">SQLASSERT_MESG</span><span class="sxs-lookup"><span data-stu-id="3f6f0-113">SQLASSERT_MESG</span></span>|  
|<span data-ttu-id="3f6f0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3f6f0-114">Message Text</span></span>|<span data-ttu-id="3f6f0-115">SQL Server-Assertion: Datei: \<%s>, Zeile = %d %s.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-115">SQL Server Assertion: File: \<%s>, line = %d %s.</span></span> <span data-ttu-id="3f6f0-116">Dieser Fehler hängt möglicherweise mit dem Ausführungszeitpunkt zusammen.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-116">This error may be timing-related.</span></span> <span data-ttu-id="3f6f0-117">Wenn der Fehler nach dem erneuten Ausführen der Anweisung weiterhin auftritt, überprüfen Sie die Datenbank mit DBCC CHECKDB auf strukturelle Integrität, oder starten Sie den Server neu, um sicherzustellen, dass keine speicherresidenten Datenstrukturen beschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f6f0-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3f6f0-118">Explanation</span></span>  
 <span data-ttu-id="3f6f0-119">Dieser Fehler kann von vorübergehenden Zeitsteuerungsfehlern oder durch Datenbeschädigung im Speicher oder auf dem Datenträger verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f6f0-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3f6f0-120">User Action</span></span>  
 <span data-ttu-id="3f6f0-121">Führen Sie die Anweisung, die die Ausnahme ausgelöst hat, erneut aus.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="3f6f0-122">Wenn der Fehler von einem Zeitsteuerungsereignis verursacht wurde, tritt er möglicherweise nicht wieder auf.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="3f6f0-123">Wenn das Problem weiterhin auftritt, führen Sie DBCC CHECKDB zur Überprüfung auf Beschädigungen auf dem Datenträger aus.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="3f6f0-124">Starten Sie den Server neu, um sicherzustellen, dass die speicherinternen Datenstrukturen nicht beschädigt sind.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-124">Restart the server to ensure that the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6f0-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f6f0-125">See Also</span></span>  
 [<span data-ttu-id="3f6f0-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f6f0-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
