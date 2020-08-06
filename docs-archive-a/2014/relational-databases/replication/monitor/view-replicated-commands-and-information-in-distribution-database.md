---
title: Anzeigen replizierter Befehle und anderer Informationen in der Verteilungs Datenbank (Replikations Programmierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_browsereplcmds
- transactional replication, monitoring
- distribution databases [SQL Server replication], viewing replicated commands
- viewing replicated commands
ms.assetid: 9c20acec-8fab-4483-b9c1-dfe3768f85dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fb5850277d685f2ecf6471fa4bf9814579b2843e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725486"
---
# <a name="view-replicated-commands-and-other-information-in-the-distribution-database-replication-transact-sql-programming"></a><span data-ttu-id="1f282-102">Anzeigen replizierter Befehle und anderer Informationen in der Verteilungsdatenbank (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1f282-102">View Replicated Commands and Other Information in the Distribution Database (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="1f282-103">Bei Verwendung der Transaktionsreplikation werden Transaktionsbefehle in der Verteilungsdatenbank gespeichert, bis sie vom Verteilungs-Agent an alle Abonnenten weitergegeben oder bis die Änderungen von einem Verteilungs-Agent abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f282-103">When using transactional replication, transaction commands are stored in the distribution database until the Distribution Agent propagates them to all Subscribers or a Distribution Agent at the Subscriber pulls the changes.</span></span> <span data-ttu-id="1f282-104">Diese ausstehenden Befehle in der Verteilungsdatenbank können programmgesteuert mit gespeicherten Replikationsprozeduren angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f282-104">These pending commands in the distribution database can be viewed programmatically using replication stored procedures.</span></span> <span data-ttu-id="1f282-105">Weitere Informationen finden Sie unter [Gespeicherte Replikationsprozeduren &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f282-105">For more information, see [Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-from-all-transactional-publications-in-the-distribution-database"></a><span data-ttu-id="1f282-106">So zeigen Sie replizierte Befehle für alle Transaktionsveröffentlichungen in der Verteilungsdatenbank an</span><span class="sxs-lookup"><span data-stu-id="1f282-106">To view replicated commands from all transactional publications in the distribution database</span></span>  
  
1.  <span data-ttu-id="1f282-107">Führen Sie auf dem Verteiler für die Verteilungsdatenbank [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="1f282-107">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span>  
  
### <a name="to-view-replicated-commands-in-the-distribution-database-from-a-specific-article-or-from-a-specific-database-published-using-transactional-replication"></a><span data-ttu-id="1f282-108">So zeigen Sie replizierte Befehle in der Verteilungsdatenbank für einen bestimmten Artikel oder für eine bestimmte Datenbank an, der bzw. die mithilfe der Transaktionsreplikation veröffentlicht wurde</span><span class="sxs-lookup"><span data-stu-id="1f282-108">To view replicated commands in the distribution database from a specific article or from a specific database published using transactional replication</span></span>  
  
1.  <span data-ttu-id="1f282-109">(Optional) Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="1f282-109">(Optional) At the Publisher on the publication database, execute [sp_helparticle](/sql/relational-databases/system-stored-procedures/sp-helparticle-transact-sql).</span></span> <span data-ttu-id="1f282-110">\*\* \@ Veröffentlichung\*\* und \*\* \@ Artikel\*\*angeben.</span><span class="sxs-lookup"><span data-stu-id="1f282-110">Specify **\@publication** and **\@article**.</span></span> <span data-ttu-id="1f282-111">Beachten Sie den Wert von **article id** im Resultset.</span><span class="sxs-lookup"><span data-stu-id="1f282-111">Note the value of **article id** in the result set.</span></span>  
  
2.  <span data-ttu-id="1f282-112">Führen Sie auf dem Verteiler für die Verteilungsdatenbank [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="1f282-112">At the Distributor on the distribution database, execute [sp_browsereplcmds](/sql/relational-databases/system-stored-procedures/sp-browsemergesnapshotfolder-transact-sql).</span></span> <span data-ttu-id="1f282-113">Optionale Geben Sie die Artikel-ID aus Schritt 2 für \*\* \@ article_id\*\*an.</span><span class="sxs-lookup"><span data-stu-id="1f282-113">(Optional) Specify the article ID from step 2 for **\@article_id**.</span></span> <span data-ttu-id="1f282-114">Optionale Geben Sie die ID der Veröffentlichungs Datenbank für \*\* \@ publisher_database_id\*\*an, die aus der **database_id** Spalte in der [sys. Database](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) -Katalog Sicht abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1f282-114">(Optional) Specify the ID of the publication database for **\@publisher_database_id**, which can be obtained from the **database_id** column in the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f282-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f282-115">See Also</span></span>  
 [<span data-ttu-id="1f282-116">Programmgesteuertes Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="1f282-116">Programmatically Monitor Replication</span></span>](../monitoring-replication.md)  
  
  
