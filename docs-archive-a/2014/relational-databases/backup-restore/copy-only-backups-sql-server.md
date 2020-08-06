---
title: Kopiesicherungen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622711"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="dffcb-102">Kopiesicherungen [SQL Server]</span><span class="sxs-lookup"><span data-stu-id="dffcb-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="dffcb-103">Eine *Kopiesicherung* ist eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherung, die unabhängig von der Sequenz von herkömmlichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherungen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dffcb-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="dffcb-104">Normalerweise wird beim Erstellen einer Sicherung die Datenbank geändert, und außerdem beeinflusst dies die Art und Weise, wie spätere Sicherungen wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dffcb-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="dffcb-105">Manchmal kann es sich jedoch als nützlich erweisen, eine Datensicherung für einen bestimmten Zweck vorzunehmen, ohne die allgemeinen Sicherungs- und Wiederherstellungsprozeduren für die Datenbank zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="dffcb-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="dffcb-106">Kopiesicherungen eignen sich für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="dffcb-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="dffcb-107">Die folgenden Typen von Kopiesicherungen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="dffcb-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="dffcb-108">Vollständige Kopiesicherungen (alle Wiederherstellungsmodelle)</span><span class="sxs-lookup"><span data-stu-id="dffcb-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="dffcb-109">Eine Kopiesicherung kann nicht als differenzielle Basis oder differenzielle Sicherung dienen und wirkt sich nicht auf die differenzielle Basis aus.</span><span class="sxs-lookup"><span data-stu-id="dffcb-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="dffcb-110">Die Wiederherstellung einer vollständigen Kopiesicherung entspricht der Wiederherstellung jeder anderen vollständigen Sicherung.</span><span class="sxs-lookup"><span data-stu-id="dffcb-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="dffcb-111">Protokollkopiesicherungen (nur vollständiges und massenprotokolliertes Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="dffcb-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="dffcb-112">Eine Protokollkopiesicherung behält den vorhandenen Protokollarchivpunkt bei und wirkt sich daher nicht auf die Sequenz von regulären Protokollsicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="dffcb-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="dffcb-113">Protokollkopiesicherungen sind normalerweise nicht nötig.</span><span class="sxs-lookup"><span data-stu-id="dffcb-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="dffcb-114">Erstellen Sie stattdessen eine neue routinemäßige Protokollsicherung (mithilfe von WITH NORECOVERY), und verwenden Sie dann diese Sicherung zusammen mit allen vorherigen Protokollsicherungen, die für die Wiederherstellungssequenz erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dffcb-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="dffcb-115">Eine Protokollkopiesicherung ist manchmal jedoch auch für das Ausführen einer Onlinewiederherstellung nützlich.</span><span class="sxs-lookup"><span data-stu-id="dffcb-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="dffcb-116">Ein Beispiel dafür finden Sie unter [Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="dffcb-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="dffcb-117">Nach einer Kopiesicherung wird das Transaktionsprotokoll nie abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="dffcb-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="dffcb-118">Kopiesicherungen werden in der **is_copy_only** -Spalte der [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) -Tabelle aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dffcb-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="dffcb-119">So erstellen Sie eine Kopiesicherung</span><span class="sxs-lookup"><span data-stu-id="dffcb-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="dffcb-120">Kopiesicherungen können mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]oder PowerShell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dffcb-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dffcb-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dffcb-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="dffcb-122">Wählen Sie im Dialogfeld **Datenbank sichern** auf der Seite **Allgemein** die Option **Kopiesicherung** aus.</span><span class="sxs-lookup"><span data-stu-id="dffcb-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dffcb-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dffcb-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="dffcb-124">Die grundlegende [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dffcb-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="dffcb-125">Für eine vollständige Kopiesicherung:</span><span class="sxs-lookup"><span data-stu-id="dffcb-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="dffcb-126">Daten Bank *database_name* sichern in \<backup_device*> \*... mit COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="dffcb-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dffcb-127">COPY_ONLY ist wirkungslos, wenn gleichzeitig die Option DIFFERENTIAL angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dffcb-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="dffcb-128">Für eine Protokollkopiesicherung:</span><span class="sxs-lookup"><span data-stu-id="dffcb-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="dffcb-129">Sicherungs Protokoll *database_name* *\<*backup_device*>* ... mit COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="dffcb-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="dffcb-130">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="dffcb-130">Using PowerShell</span></span>  
  
<span data-ttu-id="dffcb-131">Verwenden Sie das `Backup-SqlDatabase`-Cmdlet mit dem `-CopyOnly`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="dffcb-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="dffcb-132">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="dffcb-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="dffcb-133">So erstellen Sie eine vollständige oder Protokollsicherung</span><span class="sxs-lookup"><span data-stu-id="dffcb-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="dffcb-134">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dffcb-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="dffcb-135">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dffcb-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="dffcb-136">So zeigen Sie Kopiesicherungen an</span><span class="sxs-lookup"><span data-stu-id="dffcb-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="dffcb-137">backupset &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dffcb-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="dffcb-138">Einrichten und Verwenden des SQL Server PowerShell-Anbieters</span><span class="sxs-lookup"><span data-stu-id="dffcb-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="dffcb-139">SQL Server PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="dffcb-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="dffcb-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dffcb-140">See Also</span></span>  
 <span data-ttu-id="dffcb-141">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dffcb-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="dffcb-142">[Wiederherstellungsmodelle &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="dffcb-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="dffcb-143">[Kopieren von Datenbanken durch Sichern und Wiederherstellen](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="dffcb-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="dffcb-144">Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dffcb-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
