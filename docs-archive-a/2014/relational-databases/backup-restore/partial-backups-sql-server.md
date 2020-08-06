---
title: Teilsicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- partial backups [SQL Server]
- READ_WRITE_FILEGROUPS option
- database backups [SQL Server], about backing up databases
ms.assetid: fe6b6bb1-38d0-46c4-bab8-31df14e8999c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0c03cf2fb4d3af6fe87459e881e26c48cfacc232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620478"
---
# <a name="partial-backups-sql-server"></a><span data-ttu-id="1bade-102">Teilsicherungen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1bade-102">Partial Backups (SQL Server)</span></span>
  <span data-ttu-id="1bade-103">Alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Wiederherstellungsmodelle unterstützen Teilsicherungen, deshalb ist dieses Thema für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant.</span><span class="sxs-lookup"><span data-stu-id="1bade-103">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recovery models support partial backups, so this topic is relevant for all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="1bade-104">Teilsicherungen wurden jedoch für die Verwendung mit dem einfachen Sicherungsmodell konzipiert, und zwar mit der Absicht, die Flexibilität bei der Sicherung sehr großer Datenbanken mit einer oder mehreren schreibgeschützten Dateigruppen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="1bade-104">However, partial backups are designed for use under the simple recovery model to improve flexibility for backing up very large databases that contain one or more read-only filegroups.</span></span>  
  
 <span data-ttu-id="1bade-105">Teilsicherungen erweisen sich besonders dann als nützlich, wenn Sie bestimmte schreibgeschützte Dateigruppen aus der Sicherung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bade-105">Partial backups are useful whenever you want to exclude read-only filegroups.</span></span> <span data-ttu-id="1bade-106">Eine *Teilsicherung* ähnelt einer vollständigen Datenbanksicherung. Sie enthält jedoch nicht alle Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="1bade-106">A *partial backup* resembles a full database backup, but a partial backup does not contain all the filegroups.</span></span> <span data-ttu-id="1bade-107">Stattdessen enthält eine Teilsicherung für eine Datenbank mit Lese-/Schreibzugriff alle Daten in der primären Dateigruppe, alle Lese-/Schreibdateigruppen sowie alle optional angegebenen schreibgeschützten Dateien.</span><span class="sxs-lookup"><span data-stu-id="1bade-107">Instead, for a read-write database, a partial backup contains the data in the primary filegroup, every read-write filegroup, and, optionally, one or more read-only files.</span></span> <span data-ttu-id="1bade-108">Eine Teilsicherung einer schreibgeschützten Datenbank enthält nur die primäre Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="1bade-108">A partial backup of a read-only database contains only the primary filegroup.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bade-109">Wenn eine schreibgeschützte Datenbank nach einer Teilsicherung in eine Datenbank mit Lese-/Schreibzugriff geändert wird, können sekundäre Dateigruppen mit Lese-/Schreibzugriff vorhanden sein, die nicht in der Teilsicherung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1bade-109">If a read-only database is changed to read/write after a partial backup, there might be read/write secondary filegroups that are not in the partial backup.</span></span> <span data-ttu-id="1bade-110">Wenn Sie in diesem Fall versuchen, eine differenzielle Teilsicherung zu erstellen, tritt bei der Sicherung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="1bade-110">In this case, if you try to take a differential partial backup, the backup fails.</span></span> <span data-ttu-id="1bade-111">Bevor Sie eine differenzielle Teilsicherung der Datenbank erstellen können, müssen Sie eine weitere Teilsicherung erstellen.</span><span class="sxs-lookup"><span data-stu-id="1bade-111">Before you can take a differential partial backup of the database, you must take another partial backup.</span></span> <span data-ttu-id="1bade-112">Die neue Teilsicherung enthält alle sekundären Dateigruppen mit Lese-/Schreibzugriff und kann als Basis für differenzielle Teilsicherungen dienen.</span><span class="sxs-lookup"><span data-stu-id="1bade-112">The new partial backup contains every read/write secondary filegroup and can serve as the base for differential partial backups.</span></span>  
  
 <span data-ttu-id="1bade-113">Dateisicherungen von schreibgeschützten Dateigruppen können mit Teilsicherungen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="1bade-113">File backups of read-only filegroups can be combined with partial backups.</span></span> <span data-ttu-id="1bade-114">Informationen zu Dateisicherungen finden Sie unter [Vollständige Dateisicherungen &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bade-114">For information about file backups, see [Full File Backups &#40;SQL Server&#41;](full-file-backups-sql-server.md).</span></span>  
  
 <span data-ttu-id="1bade-115">Eine Teilsicherung kann als *differenzielle Basis* für differenzielle Teilsicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bade-115">A partial backup can serve as the *differential base* for differential partial backups.</span></span> <span data-ttu-id="1bade-116">Weitere Informationen finden Sie unter [Differenzielle Sicherungen &#40;SQL Server&#41;](differential-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1bade-116">For more information, see [Differential Backups &#40;SQL Server&#41;](differential-backups-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1bade-117">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1bade-117">Related Tasks</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1bade-118">Teilsicherungen werden nicht von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder vom Wartungsplanungs-Assistenten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1bade-118">Partial backups are not supported by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the Maintenance Plan Wizard.</span></span>  
  
 <span data-ttu-id="1bade-119">**So erstellen Sie eine Teilsicherung**</span><span class="sxs-lookup"><span data-stu-id="1bade-119">**To create a partial backup**</span></span>  
  
-   <span data-ttu-id="1bade-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP-Option nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="1bade-120">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) (READ_WRITE_FILEGROUPS; FILEGROUP option, if needed)</span></span>  
  
 <span data-ttu-id="1bade-121">**So verwenden Sie eine Teilsicherung in einer Wiederherstellungssequenz**</span><span class="sxs-lookup"><span data-stu-id="1bade-121">**To use a partial backup in a restore sequence**</span></span>  
  
-   [<span data-ttu-id="1bade-122">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="1bade-122">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="1bade-123">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="1bade-123">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bade-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bade-124">See Also</span></span>  
 <span data-ttu-id="1bade-125">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1bade-125">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="1bade-126">[Dateiwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="1bade-126">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 [<span data-ttu-id="1bade-127">Schrittweise Wiederherstellungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1bade-127">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
