---
title: Verwalten einer Peer-zu-Peer-Topologie (Replikationsprogrammierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- transactional replication, peer-to-peer replication
ms.assetid: 4d0fa941-f9ea-4a14-aed9-34df593fc6f2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a73af1c1f3a7196d87f77681ee9d62a3ef248a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615966"
---
# <a name="administer-a-peer-to-peer-topology-replication-transact-sql-programming"></a><span data-ttu-id="c84b1-102">Verwalten einer Peer-zu-Peer-Topologie (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c84b1-102">Administer a Peer-to-Peer Topology (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="c84b1-103">Das Verwalten einer Peer-zu-Peer-Topologie ist mit dem Verwalten einer typischen Transaktionsreplikationstopologie zu vergleichen, allerdings sind für einige Bereiche Besonderheiten zu beachten.</span><span class="sxs-lookup"><span data-stu-id="c84b1-103">Administering a peer-to-peer topology is similar to administering a typical transactional replication topology, but there are a number of areas with special considerations.</span></span> <span data-ttu-id="c84b1-104">Der Hauptunterschied beim Verwalten einer Peer-zu-Peer-Topologie besteht darin, dass das System aufgrund einiger Änderungen *in einen inaktiven Status versetzt werden muss*.</span><span class="sxs-lookup"><span data-stu-id="c84b1-104">The principal difference in administering a peer-to-peer topology is that some changes require the system to be *quiesced*.</span></span> <span data-ttu-id="c84b1-105">Um das System in einen inaktiven Status zu versetzen, beenden Sie alle Aktivitäten in veröffentlichten Tabellen auf allen Knoten, und stellen Sie sicher, dass jeder Knoten alle Änderungen sämtlicher anderen Knoten empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="c84b1-105">Quiescing a system involves stopping activity on published tables at all nodes and ensuring that each node has received all changes from all other nodes.</span></span> <span data-ttu-id="c84b1-106">Weitere Informationen finden Sie unter [Versetzen einer Replikationstopologie in einen inaktiven Status &#40;Replikationsprogrammierung mit Transact-SQL&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="c84b1-106">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c84b1-107">In einer Peer-zu-Peer-Topologie kann der Verteiler keine frühere [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Version verwenden als ein Pullabonnent.</span><span class="sxs-lookup"><span data-stu-id="c84b1-107">In a peer-to-peer topology, the distributor cannot be using an earlier version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] than a pull subscriber.</span></span>  
  
### <a name="to-add-an-article-to-an-existing-configuration"></a><span data-ttu-id="c84b1-108">So fügen Sie einer vorhandenen Konfiguration einen Artikel hinzu</span><span class="sxs-lookup"><span data-stu-id="c84b1-108">To add an article to an existing configuration</span></span>  
  
1.  <span data-ttu-id="c84b1-109">Versetzen Sie das System in einen inaktiven Status.</span><span class="sxs-lookup"><span data-stu-id="c84b1-109">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="c84b1-110">Beenden Sie den Verteilungs-Agent in jedem Knoten in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="c84b1-110">Stop the Distribution Agent at each node in the topology.</span></span> <span data-ttu-id="c84b1-111">Weitere Informationen finden Sie unter [Ausführbare Konzepte für die Programmierung von Replikations-Agents](../concepts/replication-agent-executables-concepts.md) oder [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c84b1-111">For more information, see [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md) or [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md).</span></span>  
  
3.  <span data-ttu-id="c84b1-112">Führen Sie die CREATE TABLE-Anweisung aus, um die neue Tabelle in jedem Knoten in der Topologie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c84b1-112">Execute the CREATE TABLE statement to add the new table at each node in the topology.</span></span>  
  
4.  <span data-ttu-id="c84b1-113">Kopieren Sie die Daten mithilfe des [Hilfsprogramms "bcp"](../../../tools/bcp-utility.md)in einem Massenkopiervorgang für die neue Tabelle manuell in alle Knoten.</span><span class="sxs-lookup"><span data-stu-id="c84b1-113">Bulk copy the data for the new table manually at all nodes by using the [bcp utility](../../../tools/bcp-utility.md).</span></span>  
  
5.  <span data-ttu-id="c84b1-114">Führen [Sie sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) aus, um den neuen Artikel in jedem Knoten in der Topologie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c84b1-114">Execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) to create the new article at each node in the topology.</span></span> <span data-ttu-id="c84b1-115">Weitere Informationen finden Sie unter [Definieren eines Artikels](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="c84b1-115">For more information, see [Define an Article](../publish/define-an-article.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c84b1-116">Nach dem Ausführen von [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) fügt die Replikation den Artikel automatisch den Abonnements in der Topologie hinzu.</span><span class="sxs-lookup"><span data-stu-id="c84b1-116">After [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) is executed, replication automatically adds the article to the subscriptions in the topology.</span></span>  
  
6.  <span data-ttu-id="c84b1-117">Starten Sie die Verteilungs-Agents in jedem Knoten in der Topologie neu.</span><span class="sxs-lookup"><span data-stu-id="c84b1-117">Restart the Distribution Agents at each node in the topology.</span></span>  
  
### <a name="to-make-schema-changes-to-a-publication-database"></a><span data-ttu-id="c84b1-118">So nehmen Sie an einer Veröffentlichungsdatenbank Schemaänderungen vor</span><span class="sxs-lookup"><span data-stu-id="c84b1-118">To make schema changes to a publication database</span></span>  
  
1.  <span data-ttu-id="c84b1-119">Versetzen Sie das System in einen inaktiven Status.</span><span class="sxs-lookup"><span data-stu-id="c84b1-119">Quiesce the system.</span></span>  
  
2.  <span data-ttu-id="c84b1-120">Führen Sie die DDL-Anweisungen (Data Definition Language) aus, um das Schema veröffentlichter Tabellen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c84b1-120">Execute the data definition language (DDL) statements to modify the schema of published tables.</span></span> <span data-ttu-id="c84b1-121">Weitere Informationen zu unterstützten Schemaänderungen finden Sie unter [Vornehmen von Schemaänderungen in Veröffentlichungsdatenbanken](../publish/make-schema-changes-on-publication-databases.md).</span><span class="sxs-lookup"><span data-stu-id="c84b1-121">For more information about supported schema changes, see [Make Schema Changes on Publication Databases](../publish/make-schema-changes-on-publication-databases.md).</span></span>  
  
3.  <span data-ttu-id="c84b1-122">Versetzen Sie das System erneut in einen inaktiven Status, bevor Sie die Aktivitäten an veröffentlichten Tabellen fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="c84b1-122">Before you resume activity on published tables, quiesce the system again.</span></span> <span data-ttu-id="c84b1-123">So kann sichergestellt werden, dass alle Knoten die Schemaänderungen erhalten haben, bevor neue Datenänderungen repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="c84b1-123">This ensures that schema changes have been received by all nodes before any new data changes are replicated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c84b1-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c84b1-124">Example</span></span>  
 <span data-ttu-id="c84b1-125">Im folgenden Beispiel wird das Hinzufügen eines neuen Tabellenartikels zu einer vorhandenen Peer-zu-Peer-Topologie mit zwei Knoten veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c84b1-125">The following example demonstrates how to add a new table article to an existing peer-to-peer replication topology that has two nodes.</span></span>  
  
 [!code-sql[HowTo#sp_addp2particle_createtables](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createtables)]  
  
 [!code-sql[HowTo#sp_addp2particle_cmdline](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_cmdline)]  
  
 [!code-sql[HowTo#sp_addp2particle_createarticle](../../../snippets/tsql/SQL15/replication/howto/tsql/addp2particle.sql#sp_addp2particle_createarticle)]  
  
## <a name="see-also"></a><span data-ttu-id="c84b1-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c84b1-126">See Also</span></span>  
 <span data-ttu-id="c84b1-127">[Häufig gestellte Fragen für Replikationsadministratoren](frequently-asked-questions-for-replication-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="c84b1-127">[Replication Administration FAQ](frequently-asked-questions-for-replication-administrators.md) </span></span>  
 <span data-ttu-id="c84b1-128">[Sichern und Wiederherstellen von SQL Server-Datenbanken](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c84b1-128">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="c84b1-129">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="c84b1-129">Peer-to-Peer Transactional Replication</span></span>](../transactional/peer-to-peer-transactional-replication.md)  
  
  
