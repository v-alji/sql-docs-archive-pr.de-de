---
title: MSSQL_ENG014117 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014117 error
ms.assetid: e5906a76-9511-4c47-8826-8c765b58a39d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4694aacc7d1f5ee31f4ff54d8cdd4256b48f713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607680"
---
# <a name="mssql_eng014117"></a><span data-ttu-id="4f56e-102">MSSQL_ENG014117</span><span class="sxs-lookup"><span data-stu-id="4f56e-102">MSSQL_ENG014117</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4f56e-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="4f56e-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f56e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4f56e-104">Product Name</span></span>|<span data-ttu-id="4f56e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f56e-105">SQL Server</span></span>|  
|<span data-ttu-id="4f56e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4f56e-106">Event ID</span></span>|<span data-ttu-id="4f56e-107">14117</span><span class="sxs-lookup"><span data-stu-id="4f56e-107">14117</span></span>|  
|<span data-ttu-id="4f56e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4f56e-108">Event Source</span></span>|<span data-ttu-id="4f56e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4f56e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4f56e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4f56e-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4f56e-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4f56e-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4f56e-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4f56e-112">Message Text</span></span>|<span data-ttu-id="4f56e-113">'%1!s!' ist nicht als Verteilungsdatenbank konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4f56e-113">'%s' is not configured as a distribution database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4f56e-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4f56e-114">Explanation</span></span>  
 <span data-ttu-id="4f56e-115">Dieser Fehler kann auftreten, wenn eine oder beide der folgenden Aussagen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="4f56e-115">This error can occur if one or both of the following are true:</span></span>  
  
-   <span data-ttu-id="4f56e-116">In **msdb..MSdistributiondbs**fehlt der Eintrag für die angegebene Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="4f56e-116">The entry for the specified distribution database is missing from **msdb..MSdistributiondbs**.</span></span>  
  
-   <span data-ttu-id="4f56e-117">In der **master** -Datenbank gibt es keinen Eintrag für den lokalen Server, oder es ist zwar ein Eintrag vorhanden, dieser ist aber falsch.</span><span class="sxs-lookup"><span data-stu-id="4f56e-117">There is not an entry for the local server in the **master** database, or the entry that is there is incorrect.</span></span>  
  
     <span data-ttu-id="4f56e-118">Die Replikation erwartet, dass alle Server in einer Topologie mithilfe des Computernamens mit einem optionalen Instanznamen (bei Clusterinstanzen mithilfe des virtuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Servernamens mit dem optionalen Instanznamen) registriert werden.</span><span class="sxs-lookup"><span data-stu-id="4f56e-118">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="4f56e-119">Damit die Replikation ordnungsgemäß funktioniert, muss der von `SELECT @@SERVERNAME` für jeden Server in der Topologie zurückgegebene Wert mit dem Computernamen bzw. dem virtuellen Servernamen mit dem optionalen Instanznamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4f56e-119">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
     <span data-ttu-id="4f56e-120">Die Replikation wird nicht unterstützt, wenn Sie eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen registriert haben.</span><span class="sxs-lookup"><span data-stu-id="4f56e-120">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="4f56e-121">Dieser Fehler kann ausgelöst werden, wenn beim Konfigurieren der Replikation eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] registriert war.</span><span class="sxs-lookup"><span data-stu-id="4f56e-121">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4f56e-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4f56e-122">User Action</span></span>  
 <span data-ttu-id="4f56e-123">Überprüfen Sie, ob die Verteilerinstanz ordnungsgemäß registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4f56e-123">Verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="4f56e-124">Wenn der Netzwerkname des Computers und der Name der SQL Server-Instanz nicht identisch sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4f56e-124">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="4f56e-125">Fügen Sie den SQL Server-Instanznamen als gültigen Netzwerknamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f56e-125">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="4f56e-126">Eine Möglichkeit, einen alternativen Netzwerknamen festzulegen, besteht darin, diesen Namen der lokalen Hostdatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f56e-126">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="4f56e-127">Die lokale Hostdatei befindet sich im Verzeichnis WINDOWS\system32\drivers\usw. oder WINNT\system32\drivers\usw. Weitere Informationen finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4f56e-127">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="4f56e-128">Wenn der Computername z. B. comp1 ist und die IP-Adresse des Computers 10.193.17.129 lautet und wenn der Instanzname inst1/instname ist, ist der Hostdatei der folgende Eintrag hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="4f56e-128">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="4f56e-129">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="4f56e-129">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="4f56e-130">Deaktivieren Sie die Verteilung, registrieren Sie die Instanz, und stellen Sie dann die Verteilung wieder her.</span><span class="sxs-lookup"><span data-stu-id="4f56e-130">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="4f56e-131">Wenn der @@SERVERNAME-Wert für eine nicht in einem Cluster befindliche Instanz falsch ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4f56e-131">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="4f56e-132">Nachdem Sie die gespeicherte Prozedur [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)ausgeführt haben, müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst neu starten, damit die Änderung an @@SERVERNAME wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="4f56e-132">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="4f56e-133">Wenn der @@SERVERNAME-Wert für eine in einem Cluster befindliche Instanz falsch ist, müssen Sie mithilfe der Clusterverwaltung den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="4f56e-133">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="4f56e-134">Weitere Informationen finden Sie unter [ Always On-Failoverclusterinstanzen (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f56e-134">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
 <span data-ttu-id="4f56e-135">Nachdem Sie die ordnungsgemäße Registrierung der Verteilerinstanz geprüft haben, kontrollieren Sie, dass die Verteilungsdatenbank in **msdb..MSdistributiondbs**aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="4f56e-135">After verifying that the Distributor instance is registered properly, verify that the distribution database is listed in **msdb..MSdistributiondbs**.</span></span> <span data-ttu-id="4f56e-136">Falls nicht, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4f56e-136">If it is not listed:</span></span>  
  
1.  <span data-ttu-id="4f56e-137">Erstellen Sie ein Skript für die Verteilungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="4f56e-137">Script out the distribution configuration.</span></span> <span data-ttu-id="4f56e-138">Weitere Informationen finden Sie unter [Scripting Replication](scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="4f56e-138">For more information, see [Scripting Replication](scripting-replication.md).</span></span>  
  
2.  <span data-ttu-id="4f56e-139">Deaktivieren Sie die Verteilung, und aktivieren Sie sie dann erneut.</span><span class="sxs-lookup"><span data-stu-id="4f56e-139">Disable distribution and then re-enable it.</span></span> <span data-ttu-id="4f56e-140">Weitere Informationen finden Sie unter [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="4f56e-140">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f56e-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f56e-141">See Also</span></span>  
 [<span data-ttu-id="4f56e-142">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="4f56e-142">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
