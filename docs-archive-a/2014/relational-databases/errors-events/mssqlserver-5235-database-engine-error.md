---
title: MSSQLSERVER_5235 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723913"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="df5f9-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="df5f9-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="df5f9-103">Details</span><span class="sxs-lookup"><span data-stu-id="df5f9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df5f9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="df5f9-104">Product Name</span></span>|<span data-ttu-id="df5f9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="df5f9-105">SQL Server</span></span>|  
|<span data-ttu-id="df5f9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="df5f9-106">Event ID</span></span>|<span data-ttu-id="df5f9-107">5235</span><span class="sxs-lookup"><span data-stu-id="df5f9-107">5235</span></span>|  
|<span data-ttu-id="df5f9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="df5f9-108">Event Source</span></span>|<span data-ttu-id="df5f9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="df5f9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="df5f9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="df5f9-110">Component</span></span>|<span data-ttu-id="df5f9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="df5f9-111">SQLEngine</span></span>|  
|<span data-ttu-id="df5f9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="df5f9-112">Symbolic Name</span></span>|<span data-ttu-id="df5f9-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="df5f9-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="df5f9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="df5f9-114">Message Text</span></span>|<span data-ttu-id="df5f9-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS wurde von USER_NAME ausgeführt, wurde jedoch fehlerbedingt mit dem Fehlerzustand ERROR_STATE beendet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="df5f9-116">Verstrichene Zeit: HOURS Stunden, MINUTES Minuten, SECONDS Sekunden.</span><span class="sxs-lookup"><span data-stu-id="df5f9-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df5f9-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="df5f9-117">Explanation</span></span>  
 <span data-ttu-id="df5f9-118">Dies ist die Zusammenfassungsmeldung, die von DBCC an das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll ausgegeben wird, wenn während der Ausführung des Befehls eine unerwartete Beendigung auftritt.</span><span class="sxs-lookup"><span data-stu-id="df5f9-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="df5f9-119">Mit dem Fehlerzustand, der in der Meldung angegeben wird, wird der Typ der unerwarteten Beendigung definiert.</span><span class="sxs-lookup"><span data-stu-id="df5f9-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="df5f9-120">In der folgenden Tabelle werden die Fehlerzustände aufgeführt und definiert.</span><span class="sxs-lookup"><span data-stu-id="df5f9-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="df5f9-121">Fehlerzustand</span><span class="sxs-lookup"><span data-stu-id="df5f9-121">Error state</span></span>|<span data-ttu-id="df5f9-122">Definition</span><span class="sxs-lookup"><span data-stu-id="df5f9-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="df5f9-123">Status 0</span><span class="sxs-lookup"><span data-stu-id="df5f9-123">State 0</span></span>|<span data-ttu-id="df5f9-124">Die Anweisung wurde aufgrund einer schwerwiegenden Beschädigung der Metadaten beendet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="df5f9-125">Diese Meldung wird von mindestens einer Instanz des Fehlers 8930 begleitet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="df5f9-126">Status 1</span><span class="sxs-lookup"><span data-stu-id="df5f9-126">State 1</span></span>|<span data-ttu-id="df5f9-127">Die Anweisung wurde aufgrund eines internen Überprüfungsfehlers beendet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="df5f9-128">Diese Meldung wird von mindestens einer Instanz des Fehlers 8967 begleitet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="df5f9-129">Status 2</span><span class="sxs-lookup"><span data-stu-id="df5f9-129">State 2</span></span>|<span data-ttu-id="df5f9-130">Bei den grundlegenden Systemtabellenüberprüfungen der zentralen Speicher-Engine-Systemtabellen ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="df5f9-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="df5f9-131">Diese Meldung wird von mindestens einer Instanz des Fehlers [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), oder [7988](mssqlserver-7988-database-engine-error.md) begleitet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="df5f9-132">Status 3</span><span class="sxs-lookup"><span data-stu-id="df5f9-132">State 3</span></span>|<span data-ttu-id="df5f9-133">Bei der DBCC-Reparatur im Notfallmodus ist ein Fehler aufgetreten, da die Datenbank nach der erneuten Erstellung des Transaktionsprotokolls nicht gestartet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="df5f9-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="df5f9-134">Diese Meldung wird von Fehler 7909 begleitet.</span><span class="sxs-lookup"><span data-stu-id="df5f9-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="df5f9-135">Status 4</span><span class="sxs-lookup"><span data-stu-id="df5f9-135">State 4</span></span>|<span data-ttu-id="df5f9-136">Während der Ausführung des Befehls ist ein Fehler bei der Assertion oder eine Zugriffsverletzung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="df5f9-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="df5f9-137">Status 5</span><span class="sxs-lookup"><span data-stu-id="df5f9-137">State 5</span></span>|<span data-ttu-id="df5f9-138">Ein unbekannter Fehler ist aufgetreten, durch den der DBCC-Befehl unerwartet beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="df5f9-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="df5f9-139">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="df5f9-139">User Action</span></span>  
 <span data-ttu-id="df5f9-140">In der folgenden Tabelle wird die Benutzeraktion angegeben, die für den angegebenen Fehlerzustand angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="df5f9-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="df5f9-141">Fehlerzustand</span><span class="sxs-lookup"><span data-stu-id="df5f9-141">Error state</span></span>|<span data-ttu-id="df5f9-142">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="df5f9-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="df5f9-143">Status 0</span><span class="sxs-lookup"><span data-stu-id="df5f9-143">State 0</span></span>|<span data-ttu-id="df5f9-144">Nehmen Sie eine Wiederherstellung von einer Sicherung vor.</span><span class="sxs-lookup"><span data-stu-id="df5f9-144">Restore from backup.</span></span>|  
|<span data-ttu-id="df5f9-145">Status 1</span><span class="sxs-lookup"><span data-stu-id="df5f9-145">State 1</span></span>|<span data-ttu-id="df5f9-146">Wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df5f9-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="df5f9-147">Status 2</span><span class="sxs-lookup"><span data-stu-id="df5f9-147">State 2</span></span>|<span data-ttu-id="df5f9-148">Nehmen Sie eine Wiederherstellung von einer Sicherung vor.</span><span class="sxs-lookup"><span data-stu-id="df5f9-148">Restore from backup.</span></span>|  
|<span data-ttu-id="df5f9-149">Status 3</span><span class="sxs-lookup"><span data-stu-id="df5f9-149">State 3</span></span>|<span data-ttu-id="df5f9-150">Nehmen Sie eine Wiederherstellung von einer Sicherung vor.</span><span class="sxs-lookup"><span data-stu-id="df5f9-150">Restore from backup.</span></span>|  
|<span data-ttu-id="df5f9-151">Status 4</span><span class="sxs-lookup"><span data-stu-id="df5f9-151">State 4</span></span>|<span data-ttu-id="df5f9-152">Wenden Sie sich an den Kundenservice und -support.</span><span class="sxs-lookup"><span data-stu-id="df5f9-152">Contact CSS.</span></span>|  
|<span data-ttu-id="df5f9-153">Status 5</span><span class="sxs-lookup"><span data-stu-id="df5f9-153">State 5</span></span>|<span data-ttu-id="df5f9-154">Führen Sie den Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="df5f9-154">Run the command again.</span></span> <span data-ttu-id="df5f9-155">Wenden Sie sich an den Kundenservice und -support, wenn das Problem weiterhin auftritt.</span><span class="sxs-lookup"><span data-stu-id="df5f9-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df5f9-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df5f9-156">See Also</span></span>  
 [<span data-ttu-id="df5f9-157">DBCC &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df5f9-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
