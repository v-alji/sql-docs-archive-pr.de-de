---
title: Aktivieren koordinierter Sicherungen für die Transaktions Replikation (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, backup and restore
- sp_replicationdboption
- sync with backup [SQL Server replication]
- coordinated backups [SQL Server replication]
- backups [SQL Server replication], transactional replication
ms.assetid: 73a914ba-8b2d-4f4d-ac1b-db9bac676a30
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 77405cd968fa917c3ccc799eb7d168782443eee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725565"
---
# <a name="enable-coordinated-backups-for-transactional-replication-replication-transact-sql-programming"></a><span data-ttu-id="09438-102">Aktivieren koordinierter Sicherungen für die Transaktionsreplikation (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="09438-102">Enable Coordinated Backups for Transactional Replication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="09438-103">Wenn Sie eine Datenbank für die Transaktionsreplikation aktivieren, können Sie angeben, dass alle Transaktionen gesichert werden müssen, bevor sie an die Verteilungsdatenbank übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="09438-103">When enabling a database for transactional replication, you can specify that all transactions must be backed up before being delivered to the distribution database.</span></span> <span data-ttu-id="09438-104">Zudem können Sie auf der Verteilungsdatenbank die koordinierte Sicherung aktivieren, sodass das Transaktionsprotokoll der Veröffentlichungsdatenbank erst dann abgeschnitten wird, nachdem die an den Verteiler weitergegebenen Transaktionen gesichert wurden.</span><span class="sxs-lookup"><span data-stu-id="09438-104">You can also enable coordinated backup on the distribution database so that the transaction log for the publication database is not truncated until transactions that have been propagated to the Distributor have been backed up.</span></span> <span data-ttu-id="09438-105">Weitere Informationen finden Sie unter [Strategien zum Sichern und Wiederherstellen einer Momentaufnahme- und Transaktionsreplikation](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="09438-105">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-database-published-with-transactional-replication"></a><span data-ttu-id="09438-106">So aktivieren Sie koordinierte Sicherungen für eine mit der Transaktionsreplikation veröffentlichte Datenbank</span><span class="sxs-lookup"><span data-stu-id="09438-106">To enable coordinated backups for a database published with transactional replication</span></span>  
  
1.  <span data-ttu-id="09438-107">Verwenden Sie auf dem Verleger die [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql)-Funktion, um die **IsSyncWithBackup**-Eigenschaft der Veröffentlichungsdatenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="09438-107">At the Publisher, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the publication database.</span></span> <span data-ttu-id="09438-108">Wenn die Funktion **1**zurückgibt, sind bereits koordinierte Sicherungen für die veröffentlichte Datenbank aktiviert.</span><span class="sxs-lookup"><span data-stu-id="09438-108">If the function returns **1**, coordinated backups are already enabled for the published database.</span></span>  
  
2.  <span data-ttu-id="09438-109">Wenn die Funktion in Schritt 1 **0** zurückgibt, führen Sie [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="09438-109">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="09438-110">Geben Sie einen Wert **sync with backup** für **\@optname** und **TRUE** für **\@value** an.</span><span class="sxs-lookup"><span data-stu-id="09438-110">Specify a value of **sync with backup** for **\@optname**, and **true** for **\@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="09438-111">Wenn Sie die Option **sync with backup** in **false**ändern, wird der Abschneidepunkt der Veröffentlichungsdatenbank nach Ausführen des Protokolllese-Agents aktualisiert oder, wenn der Protokolllese-Agent fortlaufend ausgeführt wird, nach einem bestimmten Zeitintervall.</span><span class="sxs-lookup"><span data-stu-id="09438-111">If you change the **sync with backup** option to **false**, the truncation point of the publication database will be updated after the Log Reader Agent runs, or after an interval if the Log Reader Agent is running continuously.</span></span> <span data-ttu-id="09438-112">Das Maximalintervall wird vom **-MessageInterval**-Agent-Parameter gesteuert (standardmäßig 30 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="09438-112">The maximum interval is controlled by the **-MessageInterval** agent parameter (which has a default of 30 seconds).</span></span>  
  
### <a name="to-enable-coordinated-backups-for-a-distribution-database"></a><span data-ttu-id="09438-113">So aktivieren Sie koordinierte Sicherungen für eine Verteilungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="09438-113">To enable coordinated backups for a distribution database</span></span>  
  
1.  <span data-ttu-id="09438-114">Verwenden Sie auf dem Verteiler die [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql)-Funktion, um die **IsSyncWithBackup**-Eigenschaft der Verteilungsdatenbank zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="09438-114">At the Distributor, use the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) function to return the **IsSyncWithBackup** property of the distribution database.</span></span> <span data-ttu-id="09438-115">Wenn die Funktion **1**zurückgibt, sind bereits koordinierte Sicherungen für die Verteilungsdatenbank aktiviert.</span><span class="sxs-lookup"><span data-stu-id="09438-115">If the function returns **1**, coordinated backups are already enabled for the distribution database.</span></span>  
  
2.  <span data-ttu-id="09438-116">Wenn die Funktion in Schritt 1 **0** zurückgibt, führen Sie [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) auf dem Verteiler für die Verteilungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="09438-116">If the function in step 1 returns **0**, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) at the Distributor on the distribution database.</span></span> <span data-ttu-id="09438-117">Geben Sie einen Wert **sync with Backup** für \*\* \@ optname\*\* und **true** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="09438-117">Specify a value of **sync with backup** for **\@optname** and **true** for **\@value**.</span></span>  
  
### <a name="to-disable-coordinated-backups"></a><span data-ttu-id="09438-118">So deaktivieren Sie koordinierte Sicherungen</span><span class="sxs-lookup"><span data-stu-id="09438-118">To disable coordinated backups</span></span>  
  
1.  <span data-ttu-id="09438-119">Führen Sie [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql) auf dem Verleger für die Veröffentlichungsdatenbank oder auf dem Verteiler für die Verteilungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="09438-119">At either the Publisher on the publication database or at the Distributor on the distribution database, execute [sp_replicationdboption &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql).</span></span> <span data-ttu-id="09438-120">Geben Sie einen Wert **sync with Backup** für \*\* \@ optname\*\* und **false** für \*\* \@ value\*\*an.</span><span class="sxs-lookup"><span data-stu-id="09438-120">Specify a value of **sync with backup** for **\@optname** and **false** for **\@value**.</span></span>  
  
  
