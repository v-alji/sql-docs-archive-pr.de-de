---
title: Konfigurieren der Verteilung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], distribution
- distribution configuration [SQL Server replication]
- remote Distributors [SQL Server replication]
- transactional replication, configuring distribution
- distribution databases [SQL Server replication], sizing
- Distributors [SQL Server replication], configuring
- distribution databases [SQL Server replication], about distribution databases
- distribution databases [SQL Server replication]
- merge replication [SQL Server replication], configuring distribution
ms.assetid: 94d52169-384e-4885-84eb-2304e967d9f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0378fe285ba57e1420b7e6bebf5e2e6fe13d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615943"
---
# <a name="configure-distribution"></a><span data-ttu-id="00e5e-102">Konfigurieren der Verteilung</span><span class="sxs-lookup"><span data-stu-id="00e5e-102">Configure Distribution</span></span>
  <span data-ttu-id="00e5e-103">Bei dem Verteiler handelt es sich um einen Server, der die Verteilungsdatenbank enthält. In der Datenbank sind Metadaten und Verlaufsdaten für alle Replikations- und Transaktionstypen der Transaktionsreplikation gespeichert.</span><span class="sxs-lookup"><span data-stu-id="00e5e-103">The Distributor is a server that contains the distribution database, which stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="00e5e-104">Zum Einrichten der Replikation müssen Sie einen Verteiler konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="00e5e-104">To set up replication, you must configure a Distributor.</span></span> <span data-ttu-id="00e5e-105">Jeder Verleger kann nur einer einzigen Verteilerinstanz zugewiesen werden, es kann jedoch für mehrere ein Verteiler freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="00e5e-105">Each Publisher can be assigned to only a single Distributor instance, but multiple publishers can share a Distributor.</span></span> <span data-ttu-id="00e5e-106">Der Verteiler verwendet die folgenden zusätzlichen Ressourcen auf dem Server, auf dem er sich befindet:</span><span class="sxs-lookup"><span data-stu-id="00e5e-106">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="00e5e-107">Zusätzlichen Speicherplatz, falls die Momentaufnahmedateien für die Veröffentlichung auf dem Verteiler gespeichert werden (was in der Regel der Fall ist).</span><span class="sxs-lookup"><span data-stu-id="00e5e-107">Additional disk space if the snapshot files for the publication are stored on the Distributor (which they typically are).</span></span>  
  
-   <span data-ttu-id="00e5e-108">Zusätzlichen Speicherplatz zum Speichern der Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="00e5e-108">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="00e5e-109">Zusätzliche Prozessornutzung durch Replikations-Agents für auf dem Verteiler ausgeführte Pushabonnements.</span><span class="sxs-lookup"><span data-stu-id="00e5e-109">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="00e5e-110">Der Server, den Sie als Verteiler auswählen, sollte ausreichend Speicherplatz und Prozessorleistung für die Replikation und sonstige Aktivitäten, die auf diesem Server basieren, aufweisen.</span><span class="sxs-lookup"><span data-stu-id="00e5e-110">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span> <span data-ttu-id="00e5e-111">Beim Konfigurieren des Verteilers geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="00e5e-111">When you configure the Distributor, you specify the following:</span></span>  
  
-   <span data-ttu-id="00e5e-112">Einen Momentaufnahmeordner, der standardmäßig für alle Verleger verwendet wird, die diesen Verteiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="00e5e-112">A snapshot folder, which is used, by default, for all Publishers that use this Distributor.</span></span> <span data-ttu-id="00e5e-113">Stellen Sie sicher, dass dieser Ordner bereits freigegeben ist und die richtigen Berechtigungen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="00e5e-113">Ensure that this folder is already shared and has the appropriate permissions set.</span></span> <span data-ttu-id="00e5e-114">Weitere Informationen finden Sie unter [Schützen des Momentaufnahmeordners](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="00e5e-114">For more information, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  
-   <span data-ttu-id="00e5e-115">Einen Namen und Dateispeicherorte für die Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="00e5e-115">A name and file locations for the distribution database.</span></span> <span data-ttu-id="00e5e-116">Die Verteilungsdatenbank kann nach dem Erstellen nicht mehr umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="00e5e-116">The distribution database cannot be renamed after it is created.</span></span> <span data-ttu-id="00e5e-117">Wenn Sie einen anderen Namen für die Datenbank verwenden möchten, müssen Sie die Verteilung deaktivieren und neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="00e5e-117">To use a different name for the database, you must disable distribution and reconfigure it.</span></span>  
  
-   <span data-ttu-id="00e5e-118">Alle Verleger, die den Verteiler verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="00e5e-118">Any Publishers authorized to use the Distributor.</span></span> <span data-ttu-id="00e5e-119">Wenn Sie andere Verleger angeben als die Instanz, auf der der Verteiler ausgeführt wird, müssen Sie auch ein Kennwort für die Verbindungen angeben, die die Verleger mit dem Remoteverteiler herstellen.</span><span class="sxs-lookup"><span data-stu-id="00e5e-119">If you specify Publishers other than the instance on which the Distributor runs, you must also specify a password for the connections the Publishers make to the remote Distributor.</span></span>  
  
 <span data-ttu-id="00e5e-120">Führen Sie bei der Transaktionsreplikation nach dem Konfigurieren der Verteilung folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="00e5e-120">For transactional replication, after you configure distribution, we recommend that you:</span></span>  
  
-   <span data-ttu-id="00e5e-121">Richten Sie eine angemessene Größe für die Verteilungsdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="00e5e-121">Size the distribution database appropriately.</span></span> <span data-ttu-id="00e5e-122">Testen Sie die Replikation unter der typischen Auslastung des Systems, um den Speicherbedarf für Befehle zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="00e5e-122">Test replication with a typical load for your system to determine how much space is required to store commands.</span></span> <span data-ttu-id="00e5e-123">Stellen Sie sicher, dass die Datenbank ausreichend Speicherkapazität für Befehle aufweist, um die häufige automatische Vergrößerung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="00e5e-123">Ensure the database is large enough to store commands without having to auto-grow frequently.</span></span> <span data-ttu-id="00e5e-124">Weitere Informationen zum Ändern der Größe einer Datenbank finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="00e5e-124">For more information about changing the size of a database, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
-   <span data-ttu-id="00e5e-125">Legen Sie die Option **sync with backup** für die Verteilungsdatenbank fest.</span><span class="sxs-lookup"><span data-stu-id="00e5e-125">Set the **sync with backup** option on the distribution database.</span></span> <span data-ttu-id="00e5e-126">Weitere Informationen finden Sie unter [Strategien zum Sichern und Wiederherstellen einer Momentaufnahme- und Transaktionsreplikation](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) und [Aktivieren koordinierter Sicherungen für die Transaktionsreplikation &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="00e5e-126">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md) and [Enable Coordinated Backups for Transactional Replication &#40;Replication Transact-SQL Programming&#41;](administration/enable-coordinated-backups-for-transactional-replication.md).</span></span>  
  
## <a name="local-and-remote-distributors"></a><span data-ttu-id="00e5e-127">Lokale und Remoteverteiler</span><span class="sxs-lookup"><span data-stu-id="00e5e-127">Local and Remote Distributors</span></span>  
 <span data-ttu-id="00e5e-128">Standardmäßig handelt es sich beim Verteiler um den gleichen Server wie beim Verleger (ein lokaler Verteiler), der Verteiler kann jedoch auch ein anderer Server sein als der Verleger (ein Remoteverteiler).</span><span class="sxs-lookup"><span data-stu-id="00e5e-128">By default, the Distributor is the same server as the Publisher (a local Distributor), but it can also be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="00e5e-129">In der Regel verwenden Sie in den folgenden Fällen einen Remoteverteiler:</span><span class="sxs-lookup"><span data-stu-id="00e5e-129">Typically, you would choose to use a remote Distributor if you want to:</span></span>  
  
-   <span data-ttu-id="00e5e-130">Zum Auslagern der Verarbeitung auf einen anderen Computer, wenn sich die Replikation so wenig wie möglich auf den Verleger auswirken soll (z. B. wenn der Verleger ein OLTP-Server ist).</span><span class="sxs-lookup"><span data-stu-id="00e5e-130">Offload processing to another computer if you want minimal impact from replication on the Publisher (for example, if the Publisher is an OLTP server).</span></span>  
  
-   <span data-ttu-id="00e5e-131">Zum Konfigurieren eines zentralen Verteilers für mehrere Verleger.</span><span class="sxs-lookup"><span data-stu-id="00e5e-131">Configure a centralized Distributor for multiple Publishers.</span></span>  
  
 <span data-ttu-id="00e5e-132">Remoteverteiler treten bei der Transaktionsreplikation häufiger auf als bei der Mergereplikation. Dafür gibt es zwei Gründe:</span><span class="sxs-lookup"><span data-stu-id="00e5e-132">Remote Distributors are more common in transactional replication than they are in merge replication for two reasons:</span></span>  
  
-   <span data-ttu-id="00e5e-133">Der Verteiler spielt bei der Transaktionsreplikation eine größere Rolle, da alle replizierten Transaktionen in die Verteilungsdatenbank geschrieben werden oder daraus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="00e5e-133">The Distributor plays a larger role in transactional replication because all replicated transactions are written to and read from the distribution database.</span></span>  
  
-   <span data-ttu-id="00e5e-134">Mergereplikationstoplogien verwenden im Allgemeinen Pullabonnements. Deshalb werden Agents jeweils auf einzelnen Abonnenten und nicht alle auf dem Verteiler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="00e5e-134">Merge replication topologies typically use pull subscriptions, so agents run at each Subscriber, rather than all running at the Distributor.</span></span> <span data-ttu-id="00e5e-135">Weitere Informationen finden Sie unter [Abonnieren von Veröffentlichungen](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="00e5e-135">For more information, see [Subscribe to Publications](subscribe-to-publications.md).</span></span> <span data-ttu-id="00e5e-136">In den meisten Fällen sollten Sie einen lokalen Verteiler für die Mergereplikation verwenden.</span><span class="sxs-lookup"><span data-stu-id="00e5e-136">In most cases, you should use a local Distributor for merge replication.</span></span>  
  
 <span data-ttu-id="00e5e-137">Informationen zum Konfigurieren Sie der Veröffentlichung und Verteilung finden Sie unter [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="00e5e-137">To configure publishing and distribution, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  
  
 <span data-ttu-id="00e5e-138">Informationen zum Ändern der Verleger- und Verteilereigenschaften finden Sie unter [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="00e5e-138">To modify Publisher and Distributor properties, see [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e5e-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00e5e-139">See Also</span></span>  
 <span data-ttu-id="00e5e-140">[Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="00e5e-140">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="00e5e-141">Schützen des Verteilers</span><span class="sxs-lookup"><span data-stu-id="00e5e-141">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
