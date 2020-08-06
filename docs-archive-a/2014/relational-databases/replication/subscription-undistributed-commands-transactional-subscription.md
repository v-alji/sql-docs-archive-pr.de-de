---
title: Abonnement, nicht verteilte Befehle (Transaktions Abonnement, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.performance.f1
ms.assetid: 5451561e-0ce3-4bb5-844a-88cd15b0b371
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6bbd82b4f4855c99076404d8b621edca11a7e1e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699446"
---
# <a name="subscription-undistributed-commands-transactional-subscription-sql-server-2005-and-later"></a><span data-ttu-id="46d7d-102">Abonnement, Nicht verteilte Befehle (Transaktionsabonnement, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="46d7d-102">Subscription, Undistributed Commands (Transactional Subscription, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="46d7d-103">Mithilfe der Registerkarte **Nicht verteilte Befehle** können Sie Informationen zur Anzahl der Befehle in der Verteilungsdatenbank anzeigen, die nicht an den ausgewählten Abonnenten übermittelt wurden, sowie die geschätzte Zeit zur Übermittlung dieser Befehle.</span><span class="sxs-lookup"><span data-stu-id="46d7d-103">The **Undistributed Commands** tab displays information about the number of commands in the distribution database that have not been delivered to the selected Subscriber, and the estimated time to deliver those commands.</span></span> <span data-ttu-id="46d7d-104">Weitere Informationen zum Anzeigen der Befehle in der Verteilungsdatenbank finden Sie unter [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="46d7d-104">For information about viewing the commands in the distribution database, see [sp_replshowcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replshowcmds-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="46d7d-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="46d7d-105">Options</span></span>  
 <span data-ttu-id="46d7d-106">**Anzahl von Befehlen in der Verteilungsdatenbank, die darauf warten, auf diesen Abonnenten angewendet zu werden**</span><span class="sxs-lookup"><span data-stu-id="46d7d-106">**Number of commands in the distribution database waiting to be applied to this Subscriber**</span></span>  
 <span data-ttu-id="46d7d-107">Die Anzahl von Befehlen in der Verteilungsdatenbank, die nicht an den ausgewählten Abonnenten übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="46d7d-107">The number of commands in the distribution database that have not been delivered to the selected Subscriber.</span></span> <span data-ttu-id="46d7d-108">Ein Befehl besteht aus einer Transact-SQL-DML-Anweisung (Data Manipulation Language, Datenbearbeitungssprache) oder einer DDL-Anweisung (Data Definition Language, Datendefinitionssprache).</span><span class="sxs-lookup"><span data-stu-id="46d7d-108">A command consists of one Transact-SQL data manipulation language (DML) statement or one data definition language (DDL) statement.</span></span>  
  
 <span data-ttu-id="46d7d-109">**Geschätzte Zeit, um diese Befehle anzuwenden, basierend auf der früheren Leistung**</span><span class="sxs-lookup"><span data-stu-id="46d7d-109">**Estimated time to apply these commands, based on past performance**</span></span>  
 <span data-ttu-id="46d7d-110">Die geschätzte Zeitdauer für die Übermittlung von Befehlen an den Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="46d7d-110">The estimated amount of time to deliver commands to the Subscriber.</span></span> <span data-ttu-id="46d7d-111">Wenn dieser Wert größer ist, als die zum Generieren und Anwenden einer Momentaufnahme auf den Abonnenten erforderliche Zeit, sollten Sie eine erneute Initialisierung des Abonnenten in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="46d7d-111">If this value is greater than the amount of time required to generate and apply a snapshot to the Subscriber, consider reinitializing the Subscriber.</span></span> <span data-ttu-id="46d7d-112">Weitere Informationen finden Sie unter [Erneutes Initialisieren von Abonnements](reinitialize-subscriptions.md).</span><span class="sxs-lookup"><span data-stu-id="46d7d-112">For more information, see [Reinitialize Subscriptions](reinitialize-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d7d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46d7d-113">See Also</span></span>  
 <span data-ttu-id="46d7d-114">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="46d7d-114">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="46d7d-115">[Leistungsüberwachung mit dem Replikations Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="46d7d-115">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 [<span data-ttu-id="46d7d-116">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="46d7d-116">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
