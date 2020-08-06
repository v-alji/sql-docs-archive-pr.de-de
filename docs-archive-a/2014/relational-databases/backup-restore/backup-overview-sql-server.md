---
title: Übersicht zu Sicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server], backing up data
- backups [SQL Server]
- database backups [SQL Server]
- backup types [SQL Server]
- data backups [SQL Server]
- backing up tables [SQL Server]
- database restores [SQL Server], backups
- backing up [SQL Server], about backing up
- restoring [SQL Server], backup types
- backups [SQL Server], about
- backups [SQL Server], table-level backups unsupported
ms.assetid: 09a6e0c2-d8fd-453f-9aac-4ff24a97dc1f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60fbd0341c4e29c6f98cc4d5fe5a2cfabc9b703f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622728"
---
# <a name="backup-overview-sql-server"></a><span data-ttu-id="58b6e-102">Backup Overview (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="58b6e-102">Backup Overview (SQL Server)</span></span>
  <span data-ttu-id="58b6e-103">Dieses Thema bietet eine Einführung in die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungskomponente.</span><span class="sxs-lookup"><span data-stu-id="58b6e-103">This topic introduces the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup component.</span></span> <span data-ttu-id="58b6e-104">Die Sicherung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank ist wichtig für den Schutz Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="58b6e-104">Backing up your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is essential for protecting your data.</span></span> <span data-ttu-id="58b6e-105">In dieser Diskussion werden Sicherungstypen und Sicherungseinschränkungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="58b6e-105">This discussion covers backup types, and backup restrictions.</span></span> <span data-ttu-id="58b6e-106">Darüber hinaus bietet das Thema eine Einführung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungsmedien und -Sicherungsgeräte.</span><span class="sxs-lookup"><span data-stu-id="58b6e-106">The topic also introduces [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup devices and backup media.</span></span>  
  
 <span data-ttu-id="58b6e-107">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="58b6e-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="58b6e-108">Komponenten und Konzepte</span><span class="sxs-lookup"><span data-stu-id="58b6e-108">Components and Concepts</span></span>](#TermsAndDefinitions)  
  
-   [<span data-ttu-id="58b6e-109">Sicherungs Komprimierung</span><span class="sxs-lookup"><span data-stu-id="58b6e-109">Backup Compression</span></span>](#BackupCompression)  
  
-   [<span data-ttu-id="58b6e-110">Einschränkungen für Sicherungsvorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="58b6e-110">Restrictions on Backup Operations in SQL Server</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="58b6e-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="58b6e-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="components-and-concepts"></a><a name="TermsAndDefinitions"></a> <span data-ttu-id="58b6e-112">Komponenten und Konzepte</span><span class="sxs-lookup"><span data-stu-id="58b6e-112">Components and Concepts</span></span>  
 <span data-ttu-id="58b6e-113">Sichern [Verb]</span><span class="sxs-lookup"><span data-stu-id="58b6e-113">back up [verb]</span></span>  
 <span data-ttu-id="58b6e-114">Kopiert die Daten oder Protokolldatensätze aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank oder aus deren Transaktionsprotokoll auf ein Sicherungsmedium, z. B. einen Datenträger, um eine Datensicherung oder Protokollsicherung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-114">Copies the data or log records from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or its transaction log to a backup device, such as a disk, to create a data backup or log backup.</span></span>  
  
 <span data-ttu-id="58b6e-115">Sicherung [Substantiv]</span><span class="sxs-lookup"><span data-stu-id="58b6e-115">backup [noun]</span></span>  
 <span data-ttu-id="58b6e-116">Eine Kopie der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Daten, die zum Wiederherstellen der Daten nach einem Fehler verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="58b6e-116">A copy of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data that can be used to restore and recover the data after a failure.</span></span> <span data-ttu-id="58b6e-117">Eine Sicherung der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Daten wird auf Datenbankebene für Dateien oder Dateigruppen erstellt.</span><span class="sxs-lookup"><span data-stu-id="58b6e-117">A backup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data is created at the level of a database or one or more of its files or filegroups.</span></span> <span data-ttu-id="58b6e-118">Sicherungen auf Tabellenebene können nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-118">Table-level backups cannot be created.</span></span> <span data-ttu-id="58b6e-119">Zusätzlich zu Datensicherungen ist beim vollständigen Wiederherstellungsmodell die Erstellung von Sicherungen des Transaktionsprotokolls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58b6e-119">In addition to data backups, the full recovery model requires creating backups of the transaction log.</span></span>  
  
 [<span data-ttu-id="58b6e-120">Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="58b6e-120">recovery model</span></span>](recovery-models-sql-server.md)  
 <span data-ttu-id="58b6e-121">Eine Datenbankeigenschaft, die die Pflege der Transaktionsprotokolle auf einer Datenbank steuert.</span><span class="sxs-lookup"><span data-stu-id="58b6e-121">A database property that controls transaction log maintenance on a database.</span></span> <span data-ttu-id="58b6e-122">Es stehen drei Wiederherstellungsmodelle zur Verfügung: einfach, vollständig und massenprotokolliert.</span><span class="sxs-lookup"><span data-stu-id="58b6e-122">Three recovery models exist: simple, full, and bulk-logged.</span></span> <span data-ttu-id="58b6e-123">Das Wiederherstellungsmodell der Datenbank bestimmt die Sicherungs- und Wiederherstellungsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-123">The recovery model of database determines its backup and restore requirements.</span></span>  
  
 [<span data-ttu-id="58b6e-124">restore</span><span class="sxs-lookup"><span data-stu-id="58b6e-124">restore</span></span>](restore-and-recovery-overview-sql-server.md)  
 <span data-ttu-id="58b6e-125">Ein aus mehreren Phasen bestehender Prozess, in dem alle Daten und Protokollseiten aus einer angegebenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherung in eine angegebene Datenbank kopiert werden und ein Rollforward für alle Transaktionen ausgeführt wird, die in der Sicherung protokolliert sind. Dies wird erreicht, indem die Daten durch die Übernahme protokollierter Änderungen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-125">A multi-phase process that copies all the data and log pages from a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup to a specified database, and then rolls forward all the transactions that are logged in the backup by applying logged changes to bring the data forward in time.</span></span>  
  
 <span data-ttu-id="58b6e-126">**Typen von Sicherungen**</span><span class="sxs-lookup"><span data-stu-id="58b6e-126">**Types of Backups**</span></span>  
  
 [<span data-ttu-id="58b6e-127">Kopiesicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-127">copy-only backup</span></span>](copy-only-backups-sql-server.md)  
 <span data-ttu-id="58b6e-128">Eine Sicherung zur besonderen Verwendung, die unabhängig von der normalen Sequenz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="58b6e-128">A special-use backup that is independent of the regular sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
 <span data-ttu-id="58b6e-129">Datensicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-129">data backup</span></span>  
 <span data-ttu-id="58b6e-130">Eine Sicherung von Daten einer vollständigen Datenbank (Datenbanksicherung), einer partiellen Datenbank (partielle Sicherung) oder einem Satz von Datendateien oder Dateigruppen (Dateisicherung).</span><span class="sxs-lookup"><span data-stu-id="58b6e-130">A backup of data in a complete database (a database backup), a partial database (a partial backup), or a set of data files or filegroups (a file backup).</span></span>  
  
 [<span data-ttu-id="58b6e-131">Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-131">database backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="58b6e-132">Eine Sicherung einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="58b6e-132">A backup of a database.</span></span> <span data-ttu-id="58b6e-133">Vollständige Datenbanksicherungen stellen die gesamte Datenbank zum Zeitpunkt dar, an dem die Sicherung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="58b6e-133">Full database backups represent the whole database at the time the backup finished.</span></span> <span data-ttu-id="58b6e-134">Differenzielle Datenbanksicherungen enthalten nur Änderungen, die seit der letzten vollständigen Datenbanksicherung an der Datenbank vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-134">Differential database backups contain only changes made to the database since its most recent full database backup.</span></span>  
  
 [<span data-ttu-id="58b6e-135">Differenzielle Sicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-135">differential backup</span></span>](full-database-backups-sql-server.md)  
 <span data-ttu-id="58b6e-136">Eine Datensicherung, die auf der letzten vollständigen Sicherung einer vollständigen oder partiellen Datenbank oder einem Satz von Datendateien oder Dateigruppen ( *differenzielle Basis*) basiert und nur die Datenblöcke enthält, die sich seit der differenziellen Basis geändert haben.</span><span class="sxs-lookup"><span data-stu-id="58b6e-136">A data backup that is based on the latest full backup of a complete or partial database or a set of data files or filegroups (the *differential base*) and that contains only the data extents that have changed since the differential base.</span></span>  
  
 <span data-ttu-id="58b6e-137">Bei einer differenziellen Teilsicherung werden nur die Datenblöcke aufgezeichnet, die seit der vorherigen Teilsicherung geändert wurden, die als Basis der differenziellen Sicherung bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="58b6e-137">A differential partial backup records only the data extents that have changed in the filegroups since the previous partial backup, known as the base for the differential.</span></span>  
  
 <span data-ttu-id="58b6e-138">Vollständige Sicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-138">full backup</span></span>  
 <span data-ttu-id="58b6e-139">Eine Datensicherung, die alle Daten in einer bestimmten Datenbank oder einem Satz von Dateigruppen oder Dateien enthält. Außerdem muss die Sicherung genügend Protokolle enthalten, um die Wiederherstellung dieser Daten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-139">A data backup that contains all the data in a specific database or set of filegroups or files, and also enough log to allow for recovering that data.</span></span>  
  
 [<span data-ttu-id="58b6e-140">Protokollsicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-140">log backup</span></span>](transaction-log-backups-sql-server.md)  
 <span data-ttu-id="58b6e-141">Eine Sicherung von Transaktionsprotokollen, die alle Protokolldatensätze enthält, die nicht in einer vorherigen Protokollsicherung gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-141">A backup of transaction logs that includes all log records that were not backed up in a previous log backup.</span></span> <span data-ttu-id="58b6e-142">(Vollständiges Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="58b6e-142">(full recovery model)</span></span>  
  
 [<span data-ttu-id="58b6e-143">Dateisicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-143">file backup</span></span>](full-file-backups-sql-server.md)  
 <span data-ttu-id="58b6e-144">Eine Sicherung aller Datenbankdateien oder -dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-144">A backup of one or more database files or filegroups.</span></span>  
  
 [<span data-ttu-id="58b6e-145">Teilsicherung</span><span class="sxs-lookup"><span data-stu-id="58b6e-145">partial backup</span></span>](partial-backups-sql-server.md)  
 <span data-ttu-id="58b6e-146">Enthält Daten aus nur einigen der Dateigruppen in einer Datenbank, einschließlich Daten in der primären Dateigruppe, alle Dateigruppen mit Lese-/Schreibzugriff und aller optional angegebenen schreibgeschützten Dateien.</span><span class="sxs-lookup"><span data-stu-id="58b6e-146">Contains data from only some of the filegroups in a database, including the data in the primary filegroup, every read/write filegroup, and any optionally-specified read-only files.</span></span>  
  
 <span data-ttu-id="58b6e-147">**Begriffe und Definitionen für Sicherungsmedien**</span><span class="sxs-lookup"><span data-stu-id="58b6e-147">**Backup Media Terms and Definitions**</span></span>  
  
 [<span data-ttu-id="58b6e-148">Sicherungsgerät</span><span class="sxs-lookup"><span data-stu-id="58b6e-148">backup device</span></span>](backup-devices-sql-server.md)  
 <span data-ttu-id="58b6e-149">Ein Datenträger oder Bandmedium, auf den bzw. das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungen geschrieben werden und von dem sie wiederhergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="58b6e-149">A disk or tape device to which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups are written and from which they can be restored.</span></span> <span data-ttu-id="58b6e-150">SQL Server-Sicherungen können auch in einen Azure Blob Storage-Dienst geschrieben werden. Das **URL**-Format wird verwendet, um das Ziel und den Namen der Sicherungsdatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="58b6e-150">SQL Server backups can also be written to an Azure Blob storage service, and **URL** format is used to specify the destination and the name of the backup file..</span></span> <span data-ttu-id="58b6e-151">Weitere Informationen finden Sie im Artikel zu [SQL Server-Sicherung und -Wiederherstellung mit dem Azure Blob Storage-Dienst](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="58b6e-151">For more information, see [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 [<span data-ttu-id="58b6e-152">Sicherungsmedien</span><span class="sxs-lookup"><span data-stu-id="58b6e-152">backup media</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="58b6e-153">Bänder oder Datenträgerdateien, auf die Sicherungen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-153">One or more tapes or disk files to which one or more backup have been written.</span></span>  
  
 [<span data-ttu-id="58b6e-154">Sicherungssatz</span><span class="sxs-lookup"><span data-stu-id="58b6e-154">backup set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="58b6e-155">Der Sicherungsinhalt, der bei einem erfolgreichen Sicherungsvorgang einem Mediensatz hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="58b6e-155">The backup content that is added to a media set by a successful backup operation.</span></span>  
  
 [<span data-ttu-id="58b6e-156">Medienfamilie</span><span class="sxs-lookup"><span data-stu-id="58b6e-156">media family</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="58b6e-157">Sicherungen, die auf einem einzelnen, nicht gespiegelten Medium oder auf einem Satz gespiegelter Medien in einem Mediensatz erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-157">Backups created on a single nonmirrored device or a set of mirrored devices in a media set</span></span>  
  
 [<span data-ttu-id="58b6e-158">Mediensatz</span><span class="sxs-lookup"><span data-stu-id="58b6e-158">media set</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
 <span data-ttu-id="58b6e-159">Eine geordnete Auflistung von Sicherungsmedien, Bändern oder Dateien auf Datenträgern, die in mindestens einem Sicherungsvorgang mithilfe eines festen Typs sowie einer festen Anzahl von Sicherungsmedien beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="58b6e-159">An ordered collection of backup media, tapes or disk files, to which one or more backup operations have written using a fixed type and number of backup devices.</span></span>  
  
 [<span data-ttu-id="58b6e-160">Gespiegelter Mediensatz</span><span class="sxs-lookup"><span data-stu-id="58b6e-160">mirrored media set</span></span>](mirrored-backup-media-sets-sql-server.md)  
 <span data-ttu-id="58b6e-161">Mehrere Kopien (Spiegel) eines Mediensatzes.</span><span class="sxs-lookup"><span data-stu-id="58b6e-161">Multiple copies (mirrors) of a media set.</span></span>  
  
##  <a name="backup-compression"></a><a name="BackupCompression"></a><span data-ttu-id="58b6e-162">Sicherungs Komprimierung</span><span class="sxs-lookup"><span data-stu-id="58b6e-162">Backup Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="58b6e-163">können Sicherungen komprimiert werden, und ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ist die Wiederherstellung komprimierter Sicherungen möglich.</span><span class="sxs-lookup"><span data-stu-id="58b6e-163">and later versions support compressing backups, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions can restore a compressed backup.</span></span> <span data-ttu-id="58b6e-164">Weitere Informationen finden Sie unter [Sicherungskomprimierung &#40;SQL Server&#41;](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="58b6e-164">For more information, see [Backup Compression &#40;SQL Server&#41;](backup-compression-sql-server.md).</span></span>  
  
##  <a name="restrictions-on-backup-operations-in-sql-server"></a><a name="Restrictions"></a><span data-ttu-id="58b6e-165">Einschränkungen für Sicherungs Vorgänge in SQL Server</span><span class="sxs-lookup"><span data-stu-id="58b6e-165">Restrictions on Backup Operations in SQL Server</span></span>  
 <span data-ttu-id="58b6e-166">Eine Sicherung kann erfolgen, während die Datenbank online ist und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58b6e-166">Backup can occur while the database is online and being used.</span></span> <span data-ttu-id="58b6e-167">Es gelten dabei jedoch folgende Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-167">However, the following restrictions exist.</span></span>  
  
### <a name="offline-data-cannot-be-backed-up"></a><span data-ttu-id="58b6e-168">Offlinedaten können nicht gesichert werden</span><span class="sxs-lookup"><span data-stu-id="58b6e-168">Offline Data Cannot Be Backed Up</span></span>  
 <span data-ttu-id="58b6e-169">Wenn im Rahmen eines Sicherungsvorgangs implizit oder explizit auf Offlinedaten verwiesen wird, tritt bei diesem Vorgang ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="58b6e-169">Any backup operation that implicitly or explicitly references data that is offline fails.</span></span> <span data-ttu-id="58b6e-170">Einige typische Fälle:</span><span class="sxs-lookup"><span data-stu-id="58b6e-170">Some typical examples include the following:</span></span>  
  
-   <span data-ttu-id="58b6e-171">Sie fordern eine vollständige Datenbanksicherung an, wobei eine Dateigruppe der Datenbank offline ist.</span><span class="sxs-lookup"><span data-stu-id="58b6e-171">You request a full database backup, but one filegroup of the database is offline.</span></span> <span data-ttu-id="58b6e-172">Da bei der vollständigen Datenbanksicherung implizit alle Dateigruppen berücksichtigt werden, ist der Vorgang fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="58b6e-172">Because all filegroups are implicitly included in a full database backup, this operation fails.</span></span>  
  
     <span data-ttu-id="58b6e-173">Zum Sichern dieser Datenbank können Sie eine Dateisicherung verwenden und nur die Dateigruppen angeben, die online sind.</span><span class="sxs-lookup"><span data-stu-id="58b6e-173">To back up this database, you can use a file backup and specify only the filegroups that are online.</span></span>  
  
-   <span data-ttu-id="58b6e-174">Sie fordern eine Teilsicherung an, wobei eine Dateigruppe mit Lese-/Schreibzugriff offline ist.</span><span class="sxs-lookup"><span data-stu-id="58b6e-174">You request a partial backup, but a read/write filegroup is offline.</span></span> <span data-ttu-id="58b6e-175">Da bei der Teilsicherung alle Dateigruppen mit Lese-/Schreibzugriff berücksichtigt werden müssen, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="58b6e-175">Because all read/write filegroups are required for a partial backup, the operation fails.</span></span>  
  
-   <span data-ttu-id="58b6e-176">Sie fordern eine Sicherung bestimmter Dateien an, wobei eine Datei nicht online ist.</span><span class="sxs-lookup"><span data-stu-id="58b6e-176">You request a file backup of specific files, but one of the files is not online.</span></span> <span data-ttu-id="58b6e-177">Dabei tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="58b6e-177">The operation fails.</span></span> <span data-ttu-id="58b6e-178">Wenn Sie Onlinedateien sichern möchten, können Sie die Offlinedatei in der Dateiliste auslassen und den Vorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="58b6e-178">To back up the online files, you can omit the offline file from the file list and repeat the operation.</span></span>  
  
 <span data-ttu-id="58b6e-179">Im Allgemeinen wird eine Protokollsicherung erfolgreich ausgeführt, selbst wenn eine oder mehrere Datendateien nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58b6e-179">Typically, a log backup succeeds even if one or more data files are unavailable.</span></span> <span data-ttu-id="58b6e-180">Wenn in einer Datei jedoch massenprotokollierte Änderungen enthalten sind, die im massenprotokollierten Wiederherstellungsmodell erfolgt sind, müssen alle Dateien online sein, damit die Sicherung erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="58b6e-180">However, if any file contains bulk-logged changes made under the bulk-logged recovery model, all the files must be online for the backup to succeed.</span></span>  
  
### <a name="concurrency-restrictions-during-backup"></a><span data-ttu-id="58b6e-181">Einschränkungen hinsichtlich der Parallelität bei Sicherungen</span><span class="sxs-lookup"><span data-stu-id="58b6e-181">Concurrency Restrictions During Backup</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58b6e-182">wird ein Onlinesicherungsprozess verwendet, um das Ausführen einer Datenbanksicherung zu ermöglichen, während die Datenbank weiterhin verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58b6e-182">uses an online backup process to allow for a database backup while the database is still being used.</span></span> <span data-ttu-id="58b6e-183">Bei einer Sicherung sind die meisten Vorgänge möglich, so sind z. B. die Anweisungen INSERT, UPDATE oder DELETE bei einem Sicherungsvorgang zulässig.</span><span class="sxs-lookup"><span data-stu-id="58b6e-183">During a backup, most operations are possible; for example, INSERT, UPDATE, or DELETE statements are allowed during a backup operation.</span></span> <span data-ttu-id="58b6e-184">Beim Versuch, einen Sicherungsvorgang zu starten, während eine Datenbankdatei erstellt oder gelöscht wird, wird der Sicherungsvorgang so lange verzögert, bis der Erstellungs- oder Löschvorgang abgeschlossen ist oder das Timeout für die Sicherung erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="58b6e-184">However, if you try to start a backup operation while a database file is being created or deleted, the backup operation waits until the create or delete operation is finished or the backup times out.</span></span>  
  
 <span data-ttu-id="58b6e-185">Folgende Vorgänge können nicht ausgeführt werden, während eine Datenbank oder ein Transaktionsprotokoll gesichert wird:</span><span class="sxs-lookup"><span data-stu-id="58b6e-185">Operations that cannot run during a database backup or transaction log backup include the following:</span></span>  
  
-   <span data-ttu-id="58b6e-186">Vorgänge, die die Dateiverwaltung betreffen, z. B. die ALTER DATABASE-Anweisung mit der Option ADD FILE oder REMOVE FILE.</span><span class="sxs-lookup"><span data-stu-id="58b6e-186">File-management operations such as the ALTER DATABASE statement with either the ADD FILE or REMOVE FILE options.</span></span>  
  
-   <span data-ttu-id="58b6e-187">Vorgänge zum Verkleinern der Datenbank oder von Dateien.</span><span class="sxs-lookup"><span data-stu-id="58b6e-187">Shrink database or shrink file operations.</span></span> <span data-ttu-id="58b6e-188">Dazu gehören auch Vorgänge zum automatischen Verkleinern.</span><span class="sxs-lookup"><span data-stu-id="58b6e-188">This includes auto-shrink operations.</span></span>  
  
-   <span data-ttu-id="58b6e-189">Wenn Sie versuchen, eine Datenbankdatei während des Sicherungsvorgangs zu erstellen oder zu löschen, tritt beim Erstellungs- oder Löschvorgang ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="58b6e-189">If you try to create or delete a database file while a backup operation is in progress, the create or delete operation fails.</span></span>  
  
 <span data-ttu-id="58b6e-190">Wenn sich ein Sicherungsvorgang mit einem Dateiverwaltungsvorgang oder einem Verkleinerungsvorgang überschneidet, tritt ein Konflikt auf.</span><span class="sxs-lookup"><span data-stu-id="58b6e-190">If a backup operation overlaps with a file-management operation or shrink operation, a conflict occurs.</span></span> <span data-ttu-id="58b6e-191">Unabhängig davon, welcher am Konflikt beteiligte Vorgang zuerst begonnen hat, wartet der zweite Vorgang auf das Timeout der Sperre, die vom ersten Vorgang festgelegt wurde. (Der Timeoutzeitraum wird durch eine Timeouteinstellung für die Sitzung gesteuert.) Wenn die Sperre während des Timeoutzeitraums aufgehoben wird, wird der zweite Vorgang fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="58b6e-191">Regardless of which of the conflicting operation began first, the second operation waits for the lock set by the first operation to time out. (The time-out period is controlled by a session time-out setting.) If the lock is released during the time-out period, the second operation continues.</span></span> <span data-ttu-id="58b6e-192">Wenn das Timeout für die Sperre eintritt, erzeugt der zweite Vorgang einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="58b6e-192">If the lock times out, the second operation fails.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="58b6e-193">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="58b6e-193">Related Tasks</span></span>  
 <span data-ttu-id="58b6e-194">**So arbeiten Sie mit Sicherungsgeräten und Sicherungsmedien**</span><span class="sxs-lookup"><span data-stu-id="58b6e-194">**To work with backup devices and backup media**</span></span>  
  
-   [<span data-ttu-id="58b6e-195">Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-195">Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-disk-file-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-196">Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-196">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-197">Angeben eines Datenträgers oder ein Bands als Sicherungsziel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-197">Specify a Disk or Tape As a Backup Destination &#40;SQL Server&#41;</span></span>](specify-a-disk-or-tape-as-a-backup-destination-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-198">Löschen eines Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-198">Delete a Backup Device &#40;SQL Server&#41;</span></span>](delete-a-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-199">Festlegen des Ablaufdatums für eine Sicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-199">Set the Expiration Date on a Backup &#40;SQL Server&#41;</span></span>](set-the-expiration-date-on-a-backup-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-200">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-200">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-201">Anzeigen der Daten und Protokolldateien in einem Sicherungssatz &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-201">View the Data and Log Files in a Backup Set &#40;SQL Server&#41;</span></span>](view-the-data-and-log-files-in-a-backup-set-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-202">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-202">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-203">Wiederherstellung einer Sicherung von einem Medium &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-203">Restore a Backup from a Device &#40;SQL Server&#41;</span></span>](restore-a-backup-from-a-device-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-204">Tutorial: SQL Server-Sicherung und -Wiederherstellung mit dem Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="58b6e-204">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
 <span data-ttu-id="58b6e-205">**So erstellen Sie eine Sicherung**</span><span class="sxs-lookup"><span data-stu-id="58b6e-205">**To create a backup**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58b6e-206">Verwenden Sie für Teilsicherungen oder Kopiesicherungen die [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) -Anweisung mit der Option PARTIAL bzw. COPY_ONLY.</span><span class="sxs-lookup"><span data-stu-id="58b6e-206">For partial or copy-only backups, you must use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement with the PARTIAL or COPY_ONLY option, respectively.</span></span>  
  
-   [<span data-ttu-id="58b6e-207">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-207">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-208">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-208">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-209">Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-209">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-210">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-210">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-211">Sichern des Transaktionsprotokolls bei beschädigter Datenbank &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-211">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-212">Aktivieren oder deaktivieren von Sicherungsprüfsummen während der Sicherung oder Wiederherstellung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-212">Enable or Disable Backup Checksums During Backup or Restore &#40;SQL Server&#41;</span></span>](enable-or-disable-backup-checksums-during-backup-or-restore-sql-server.md)  
  
-   [<span data-ttu-id="58b6e-213">Angeben, ob ein Sicherungs- oder Wiederherstellungsvorgang fortgesetzt wird, nachdem ein Fehler festgestellt wurde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-213">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
-   [<span data-ttu-id="58b6e-214">Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-214">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="58b6e-215">Tutorial: SQL Server-Sicherung und -Wiederherstellung mit dem Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="58b6e-215">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>](../tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md)  
  
## <a name="see-also"></a><span data-ttu-id="58b6e-216">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58b6e-216">See Also</span></span>  
 <span data-ttu-id="58b6e-217">[Sichern und Wiederherstellen von SQL Server-Datenbanken](back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="58b6e-217">[Back Up and Restore of SQL Server Databases](back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="58b6e-218">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="58b6e-218">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="58b6e-219">[Wartungspläne](../maintenance-plans/maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="58b6e-219">[Maintenance Plans](../maintenance-plans/maintenance-plans.md) </span></span>  
 <span data-ttu-id="58b6e-220">[Das Transaktionsprotokoll &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="58b6e-220">[The Transaction Log &#40;SQL Server&#41;](../logs/the-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="58b6e-221">Wiederherstellungsmodelle &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58b6e-221">Recovery Models &#40;SQL Server&#41;</span></span>](recovery-models-sql-server.md)  
  
  
