---
title: MSSQLSERVER_3159 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3159 (Database Engine error)
ms.assetid: c93c1003-0e3a-40aa-9873-44a0f5b8b57e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b469842b2aab15980c72ea01e46270c55ef29e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618025"
---
# <a name="mssqlserver_3159"></a><span data-ttu-id="46f74-102">MSSQLSERVER_3159</span><span class="sxs-lookup"><span data-stu-id="46f74-102">MSSQLSERVER_3159</span></span>
    
## <a name="details"></a><span data-ttu-id="46f74-103">Details</span><span class="sxs-lookup"><span data-stu-id="46f74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46f74-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="46f74-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="46f74-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="46f74-105">Event ID</span></span>|<span data-ttu-id="46f74-106">3159</span><span class="sxs-lookup"><span data-stu-id="46f74-106">3159</span></span>|  
|<span data-ttu-id="46f74-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="46f74-107">Event Source</span></span>|<span data-ttu-id="46f74-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46f74-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46f74-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="46f74-109">Component</span></span>|<span data-ttu-id="46f74-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46f74-110">SQLEngine</span></span>|  
|<span data-ttu-id="46f74-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="46f74-111">Symbolic Name</span></span>|<span data-ttu-id="46f74-112">LDDB_LOGNOTBACKEDUP</span><span class="sxs-lookup"><span data-stu-id="46f74-112">LDDB_LOGNOTBACKEDUP</span></span>|  
|<span data-ttu-id="46f74-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="46f74-113">Message Text</span></span>|<span data-ttu-id="46f74-114">Das Protokollfragment für die "%ls"-Datenbank wurde nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="46f74-114">The tail of the log for the database "%ls" has not been backed up.</span></span> <span data-ttu-id="46f74-115">Sichern Sie das Protokoll mit BACKUP LOG WITH NORECOVERY, falls es Daten enthält, die Sie nicht verlieren möchten.</span><span class="sxs-lookup"><span data-stu-id="46f74-115">Use BACKUP LOG WITH NORECOVERY to back up the log if it contains work that you do not want to lose.</span></span> <span data-ttu-id="46f74-116">Verwenden Sie die WITH REPLACE- oder WITH STOPAT-Klausel der RESTORE-Anweisung, um den Inhalt des Protokolls zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="46f74-116">Use the WITH REPLACE or WITH STOPAT clause of the RESTORE statement to just overwrite the contents of the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46f74-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="46f74-117">Explanation</span></span>  
 <span data-ttu-id="46f74-118">In den meisten Fällen ist es bei Verwendung des vollständigen oder des massenprotokollierten Wiederherstellungsmodells in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erforderlich, das Protokollfragment zu sichern, um die Protokolldatensätze aufzuzeichnen, die noch nicht gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="46f74-118">In most cases, under the full or bulk-logged recovery models, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that you back up the tail of the log to capture the log records that have not yet been backed up.</span></span> <span data-ttu-id="46f74-119">Eine Protokollsicherung des Protokollfragments, die unmittelbar vor einem Wiederherstellungsvorgang erstellt wurde, wird als Sicherung des Protokollfragments bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="46f74-119">A log backup taken of the tail of the log just before a restore operation is called a tail-log backup.</span></span>  
  
 <span data-ttu-id="46f74-120">Wenn Sie eine Datenbank bis zum Zeitpunkt des Fehlers wiederherstellen, ist die Sicherung des Protokollfragments im Wiederherstellungsplan die letzte relevante Sicherung.</span><span class="sxs-lookup"><span data-stu-id="46f74-120">When you are recovering a database to the point of a failure, the tail-log backup is the last backup of interest in the recovery plan.</span></span> <span data-ttu-id="46f74-121">Wenn Sie das Protokollfragment nicht sichern können, kann eine Datenbank nur bis zum Ende der letzten Sicherung wiederhergestellt werden, die vor dem Fehler erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="46f74-121">If you cannot back up the tail of the log, you can recover a database only to the end of the last backup that was created before the failure.</span></span>  
  
 <span data-ttu-id="46f74-122">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist es normalerweise erforderlich, eine Sicherung des Protokollfragments auszuführen, bevor die Wiederherstellung einer Datenbank gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="46f74-122">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usually requires that you take a tail-log backup before you start to restore a database.</span></span> <span data-ttu-id="46f74-123">Durch die Sicherung des Protokollfragments wird Datenverlust verhindert und die Protokollkette intakt gehalten.</span><span class="sxs-lookup"><span data-stu-id="46f74-123">The tail-log backup prevents work loss and keeps the log chain intact.</span></span> <span data-ttu-id="46f74-124">Nicht für alle Wiederherstellungsszenarien ist jedoch eine Sicherung des Protokollfragments erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46f74-124">However, not all restore scenarios require a tail-log backup.</span></span> <span data-ttu-id="46f74-125">Es ist keine Sicherung des Protokollfragments erforderlich, wenn der Wiederherstellungspunkt in einer früheren Protokollsicherung enthalten ist oder wenn Sie die Datenbank verschieben oder ersetzen (überschreiben) und sie nicht für einen Zeitpunkt nach der letzten Sicherung wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="46f74-125">You do not have to have a tail-log backup if the recovery point is included in an earlier log backup, or if you are moving or replacing (overwriting) the database and do not need to restore it to a point of time after the most recent backup.</span></span> <span data-ttu-id="46f74-126">Wenn die Protokolldateien beschädigt sind und keine Sicherung des Protokollfragments erstellt werden kann, müssen Sie zudem die Datenbank ohne Verwendung einer Sicherung des Protokollfragments wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="46f74-126">Also, if the log files are damaged and a tail-log backup cannot be created, you must restore the database without using a tail-log backup.</span></span> <span data-ttu-id="46f74-127">Dabei gehen alle Transaktionen verloren, die nach der letzten Protokollsicherung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="46f74-127">Any transactions committed after the latest log backup are lost.</span></span> <span data-ttu-id="46f74-128">Weitere Informationen finden Sie im Folgenden unter „Wiederherstellen ohne Verwendung einer Sicherung des Protokollfragments“.</span><span class="sxs-lookup"><span data-stu-id="46f74-128">For more information, see "Restoring Without Using a Tail-Log Backup," later in this topic.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="46f74-129">REPLACE sollte selten und nur nach sorgfältiger Überlegung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46f74-129">REPLACE should be used rarely, and only after careful consideration.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46f74-130">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="46f74-130">User Action</span></span>  
 <span data-ttu-id="46f74-131">Nehmen Sie eine Sicherung des Protokollfragments vor, und wiederholen Sie den Wiederherstellungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="46f74-131">Take a tail-log backup, and retry the restore operation.</span></span>  
  
 <span data-ttu-id="46f74-132">Wenn Sie das Protokollfragment nicht sichern können, verwenden Sie in Ihren RESTORE-Anweisungen WITH STOPAT oder WITH REPLACE.</span><span class="sxs-lookup"><span data-stu-id="46f74-132">If you cannot back up the tail of the log, use WITH STOPAT or WITH REPLACE in your RESTORE statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f74-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46f74-133">See Also</span></span>  
 <span data-ttu-id="46f74-134">[Wiederherstellen einer SQL Server-Datenbank zu einem Zeitpunkt &#40;vollständiges Wiederherstellungsmodell&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="46f74-134">[Restore a SQL Server Database to a Point in Time &#40;Full Recovery Model&#41;](../backup-restore/restore-a-sql-server-database-to-a-point-in-time-full-recovery-model.md) </span></span>  
 <span data-ttu-id="46f74-135">[Sichern Sie das Transaktionsprotokoll, wenn die Datenbank &#40;SQL Server beschädigt ist&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="46f74-135">[Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;](../backup-restore/back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md) </span></span>  
 <span data-ttu-id="46f74-136">[Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="46f74-136">[Back Up a Transaction Log &#40;SQL Server&#41;](../backup-restore/back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="46f74-137">Sicherungen des Protokollfragments &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="46f74-137">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/tail-log-backups-sql-server.md)  
  
  
