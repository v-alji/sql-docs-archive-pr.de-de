---
title: Failover zu einer sekundären Datenbank für den Protokollversand (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718664"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="b4966-102">Failover zu einer sekundären Datenbank für den Protokollversand (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b4966-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="b4966-103">Wenn die primäre Serverinstanz ausfällt oder gewartet werden muss, kann ein Failover zu einer sekundären Datenbank für den Protokollversand ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b4966-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="b4966-104">Vorbereitungen für ein kontrolliertes Failover</span><span class="sxs-lookup"><span data-stu-id="b4966-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="b4966-105">Normalerweise sind die primäre und die sekundäre Datenbank nicht synchronisiert, da die primäre Datenbank nach dem letzten Sicherungsauftrag weiterhin aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b4966-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="b4966-106">In manchen Fällen wurden möglicherweise auch die aktuellen Sicherungen des Transaktionsprotokolls nicht auf die sekundären Serverinstanzen kopiert, oder die Protokollsicherungen wurden zwar kopiert, jedoch noch nicht vollständig auf die sekundäre Datenbank angewendet.</span><span class="sxs-lookup"><span data-stu-id="b4966-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="b4966-107">Es wird empfohlen, nach Möglichkeit zunächst alle sekundären Datenbanken mit der primären Datenbank zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b4966-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="b4966-108">Informationen zu Protokollversandaufträgen finden Sie unter [Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4966-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="b4966-109">Ausführen eines Failovers</span><span class="sxs-lookup"><span data-stu-id="b4966-109">Failing Over</span></span>  
 <span data-ttu-id="b4966-110">So führen Sie ein Failover zu einer sekundären Datenbank aus</span><span class="sxs-lookup"><span data-stu-id="b4966-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="b4966-111">Kopieren Sie alle noch nicht kopierten Sicherungsdateien aus der Sicherungsfreigabe in den für den Kopiervorgang verwendeten Zielordner jedes sekundären Servers.</span><span class="sxs-lookup"><span data-stu-id="b4966-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="b4966-112">Wenden Sie der Reihe nach alle noch nicht angewendeten Transaktionsprotokollsicherungen auf jede sekundäre Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="b4966-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="b4966-113">Weitere Informationen finden Sie unter [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4966-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="b4966-114">Sichern Sie, wenn auf die primäre Datenbank zugegriffen werden kann, das aktive Transaktionsprotokoll, und wenden Sie die Protokollsicherung auf die sekundären Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="b4966-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="b4966-115">Wenn die ursprüngliche, primäre Serverinstanz nicht beschädigt ist, sichern Sie das Transaktionsprotokollfragment der primären Datenbank mit der Option WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="b4966-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="b4966-116">Dadurch verbleibt die Datenbank im Wiederherstellungsstatus und steht somit Benutzern nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b4966-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="b4966-117">Sie können letztendlich auf diese Datenbank ein Rollforward ausführen, indem Sie Transaktionsprotokollsicherungen aus der primären Ersatzdatenbank anwenden.</span><span class="sxs-lookup"><span data-stu-id="b4966-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="b4966-118">Weitere Informationen finden Sie unter [Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4966-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="b4966-119">Nach der Synchronisierung der sekundären Server können Sie auf Wunsch ein Failover zu einem von ihnen ausführen, indem Sie seine sekundäre Datenbank wiederherstellen und Clients zu dieser Serverinstanz umleiten.</span><span class="sxs-lookup"><span data-stu-id="b4966-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="b4966-120">Beim Wiederherstellen wird die Datenbank in einen konsistenten Status versetzt und online geschaltet.</span><span class="sxs-lookup"><span data-stu-id="b4966-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b4966-121">Wenn Sie eine sekundäre Datenbank verfügbar machen, sollten Sie sicherstellen, dass die Metadaten konsistent mit den Metadaten der ursprünglichen, ersten Datenbank sind.</span><span class="sxs-lookup"><span data-stu-id="b4966-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="b4966-122">Weitere Informationen finden Sie unter [Verwalten von Metadaten beim Bereitstellen einer Datenbank auf einer anderen Serverinstanz &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4966-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="b4966-123">Nachdem Sie die sekundäre Datenbank wiederhergestellt haben, können Sie sie so konfigurieren, dass sie für die anderen sekundären Datenbanken als erste Datenbank dient.</span><span class="sxs-lookup"><span data-stu-id="b4966-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="b4966-124">Wenn keine andere sekundäre Datenbank verfügbar ist, siehe [Konfigurieren des Protokollversands &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b4966-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b4966-125">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b4966-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b4966-126">Ändern der Rollen zwischen primärem und sekundärem Protokollversandserver &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b4966-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="b4966-127">Verwaltung von Anmeldenamen und Aufträgen nach einem Rollenwechsel &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b4966-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4966-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4966-128">See Also</span></span>  
 <span data-ttu-id="b4966-129">[Protokollversandtabellen und gespeicherte Prozeduren](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b4966-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="b4966-130">[Informationen zum Protokollversand &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b4966-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="b4966-131">Sicherungen des Protokollfragments &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b4966-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
