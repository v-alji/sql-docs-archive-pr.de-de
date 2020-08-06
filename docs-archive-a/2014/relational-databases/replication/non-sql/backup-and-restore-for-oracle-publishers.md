---
title: Sichern und Wiederherstellen bei Oracle-Verlegern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608556"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="159a9-102">Sichern und Wiederherstellen bei Oracle-Verlegern</span><span class="sxs-lookup"><span data-stu-id="159a9-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="159a9-103">Beachten Sie beim Sichern und Wiederherstellen die folgenden Hinweise:</span><span class="sxs-lookup"><span data-stu-id="159a9-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="159a9-104">Stellen Sie sicher, dass der Protokolllese-Agent nicht ausgeführt wird und dass es beim Sichern des Verlegers zu keiner anderen Datenbankaktivität in den veröffentlichten Tabellen kommt.</span><span class="sxs-lookup"><span data-stu-id="159a9-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="159a9-105">Sichern Sie den Verleger und den Verteiler gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="159a9-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="159a9-106">Wenn der Verleger oder der Verteiler wiederhergestellt wird, initialisieren Sie alle Abonnements erneut.</span><span class="sxs-lookup"><span data-stu-id="159a9-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="159a9-107">Zum Wiederherstellen eines Abonnenten aus einer Sicherung (ohne dabei die Abonnements erneut initialisieren zu müssen) müssen die Transaktionen, die nach der letzten vollständigen Sicherung der Abonnementdatenbank an die Verteilungsdatenbank geliefert wurden, noch verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="159a9-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="159a9-108">Wie lange Transaktionen verfügbar sind, hängt von den Beibehaltungsdauereinstellungen für die Verteilung ab.</span><span class="sxs-lookup"><span data-stu-id="159a9-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="159a9-109">Informationen finden Sie unter [Abonnementablauf und -deaktivierung](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="159a9-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="159a9-110">Wenn der Verleger oder der Verteiler nach einer Datenbankwiederherstellung nicht mehr synchronisiert ist, protokollieren die Replikations-Agents Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="159a9-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="159a9-111">In diesem Fall müssen Sie alle relevanten Veröffentlichungen und Abonnements löschen und erneut erstellen:</span><span class="sxs-lookup"><span data-stu-id="159a9-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="159a9-112">Erstellen Sie ein Skript für die Definition der Veröffentlichungen und Abonnements.</span><span class="sxs-lookup"><span data-stu-id="159a9-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="159a9-113">Weitere Informationen finden Sie unter [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="159a9-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="159a9-114">Wenn sich die Definition der Veröffentlichungen zwischen den Statusversionen des Verlegers und des Verteilers geändert hat, müssen Sie die Skripts entsprechend ändern.</span><span class="sxs-lookup"><span data-stu-id="159a9-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="159a9-115">Löschen Sie die Veröffentlichungen und Abonnements.</span><span class="sxs-lookup"><span data-stu-id="159a9-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="159a9-116">Führen Sie die in Schritt 1 erstellten Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="159a9-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="159a9-117">Wenn der Verleger gelöscht und erneut konfiguriert werden muss, löschen Sie das öffentliche **MSSQLSERVERDISTRIBUTOR** -Synonym und den konfigurierten Oracle-Replikationsbenutzer mit der **CASCADE** -Option, um alle Replikationsobjekte vom Oracle-Verleger zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="159a9-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159a9-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="159a9-118">See Also</span></span>  
 <span data-ttu-id="159a9-119">[Sichern und Wiederherstellen von replizierten Datenbanken](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="159a9-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="159a9-120">[Konfigurieren eines Oracle-Verlegers](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="159a9-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="159a9-121">Veröffentlichungen mit Oracle (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="159a9-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
