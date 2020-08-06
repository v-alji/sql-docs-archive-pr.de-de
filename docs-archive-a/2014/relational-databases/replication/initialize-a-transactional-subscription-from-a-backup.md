---
title: Initialisieren eines Transaktions Abonnements von einer Sicherung (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609080"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="751c4-102">Initialisieren eines Transaktionsabonnements von einer Sicherung (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="751c4-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="751c4-103">Obwohl ein Abonnement für eine Transaktionsveröffentlichung in der Regel mit einer Momentaufnahme initialisiert wird, kann ein Abonnement auch mit gespeicherten Replikationsprozeduren von einer Sicherung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="751c4-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="751c4-104">Weitere Informationen finden Sie unter [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md)initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="751c4-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="751c4-105">So initialisieren Sie einen Transaktionsabonnenten von einer Sicherung</span><span class="sxs-lookup"><span data-stu-id="751c4-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="751c4-106">Stellen Sie bei einer bestehenden Veröffentlichung sicher, dass die Veröffentlichung die Fähigkeit unterstützt, von einer Sicherung initialisieren zu können. Führen Sie dazu [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="751c4-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="751c4-107">Notieren Sie den Wert von **allow_initialize_from_backup** im Resultset.</span><span class="sxs-lookup"><span data-stu-id="751c4-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="751c4-108">Wenn der Wert **1**ist, unterstützt die Veröffentlichung diese Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="751c4-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="751c4-109">Ist der Wert **0**, führen Sie [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="751c4-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="751c4-110">Geben Sie den Wert **allow_initialize_from_backup** für die- \*\* \@ Eigenschaft\*\* und den Wert `true` für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="751c4-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="751c4-111">Führen Sie für eine neue Veröffentlichung [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="751c4-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="751c4-112">Geben Sie den Wert `true` für **allow_initialize_from_backup**an.</span><span class="sxs-lookup"><span data-stu-id="751c4-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="751c4-113">Weitere Informationen finden Sie unter [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="751c4-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="751c4-114">Um fehlende Abonnentendaten zu vermeiden, wenn Sie **sp_addpublication** mit `@allow_initialize_from_backup = N'true'`verwenden, sollten Sie immer `@immediate_sync = N'true'`verwenden.</span><span class="sxs-lookup"><span data-stu-id="751c4-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="751c4-115">Erstellen Sie mit der [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql)-Anweisung eine Sicherung der Veröffentlichungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="751c4-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="751c4-116">Stellen Sie die Sicherung auf dem Abonnenten mit der [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)-Anweisung wieder her.</span><span class="sxs-lookup"><span data-stu-id="751c4-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="751c4-117">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank die gespeicherte Prozedur [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="751c4-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="751c4-118">Geben Sie die folgenden Parameter an:</span><span class="sxs-lookup"><span data-stu-id="751c4-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="751c4-119">\*\* \@ sync_type\*\* -der Wert **initialisieren with Backup**.</span><span class="sxs-lookup"><span data-stu-id="751c4-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="751c4-120">\*\* \@ backupdevicetype\*\* : der Typ des Sicherungs Mediums: **logisch** (Standard **), Daten**Träger oder **Band**.</span><span class="sxs-lookup"><span data-stu-id="751c4-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="751c4-121">\*\* \@ backupdevicename\*\* : das logische oder physische Sicherungsmedium, das für die Wiederherstellung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="751c4-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="751c4-122">Für ein logisches Gerät geben Sie den Namen des Sicherungsmediums an, der beim Erstellen des Geräts mit **sp_addumpdevice** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="751c4-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="751c4-123">Geben Sie für ein physisches Gerät einen vollständigen Pfad und einen Dateinamen an, z. B. `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` oder `TAPE = '\\.\TAPE0'`.</span><span class="sxs-lookup"><span data-stu-id="751c4-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="751c4-124">Optionale \*\* \@ Password\*\* : ein Kennwort, das angegeben wurde, als der Sicherungs Satz erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="751c4-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="751c4-125">Optionale \*\* \@ Media Password\*\* : ein Kennwort, das angegeben wurde, als der Medien Satz formatiert wurde.</span><span class="sxs-lookup"><span data-stu-id="751c4-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="751c4-126">Optionale " \*\* \@ fleidhint\*\* ": Bezeichner für den Sicherungs Satz, der wieder hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="751c4-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="751c4-127">**1** gibt z. B. den ersten Sicherungssatz auf dem Sicherungsmedium an und **2** den zweiten Sicherungssatz.</span><span class="sxs-lookup"><span data-stu-id="751c4-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="751c4-128">(Optional für Bandgeräte) \*\* \@ entladen\*\* : Geben Sie den Wert **1** (Standardwert) an, wenn das Band nach Abschluss der Wiederherstellung vom Laufwerk entladen werden soll, und **0** , wenn es nicht entladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="751c4-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="751c4-129">(Optional) Führen Sie für ein Pullabonnement [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) und [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) im Abonnenten für die Abonnementdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="751c4-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="751c4-130">Weitere Informationen finden Sie unter [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="751c4-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="751c4-131">(Optional) Starten Sie den Verteilungs-Agent.</span><span class="sxs-lookup"><span data-stu-id="751c4-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="751c4-132">Weitere Informationen finden Sie unter [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) oder [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="751c4-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751c4-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="751c4-133">See Also</span></span>  
 <span data-ttu-id="751c4-134">[Kopieren von Datenbanken durch Sichern und Wiederherstellen](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="751c4-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="751c4-135">Sichern und Wiederherstellen von SQL Server-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="751c4-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
