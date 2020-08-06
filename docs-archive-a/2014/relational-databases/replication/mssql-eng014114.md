---
title: MSSQL_ENG014114 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014114 error
ms.assetid: f5f04590-e1c6-40d8-ab2b-98c791a0fc44
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ba2a1fde59f55eecbfeeec46555567cde964f8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607679"
---
# <a name="mssql_eng014114"></a><span data-ttu-id="4ec63-102">MSSQL_ENG014114</span><span class="sxs-lookup"><span data-stu-id="4ec63-102">MSSQL_ENG014114</span></span>
    
## <a name="message-details"></a><span data-ttu-id="4ec63-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="4ec63-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ec63-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4ec63-104">Product Name</span></span>|<span data-ttu-id="4ec63-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ec63-105">SQL Server</span></span>|  
|<span data-ttu-id="4ec63-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4ec63-106">Event ID</span></span>|<span data-ttu-id="4ec63-107">14114</span><span class="sxs-lookup"><span data-stu-id="4ec63-107">14114</span></span>|  
|<span data-ttu-id="4ec63-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4ec63-108">Event Source</span></span>|<span data-ttu-id="4ec63-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4ec63-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4ec63-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4ec63-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="4ec63-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4ec63-111">Symbolic Name</span></span>||  
|<span data-ttu-id="4ec63-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4ec63-112">Message Text</span></span>|<span data-ttu-id="4ec63-113">'%1!s!' ist nicht als Verteiler konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4ec63-113">'%s' is not configured as a Distributor.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4ec63-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4ec63-114">Explanation</span></span>  
 <span data-ttu-id="4ec63-115">Wenn in der Fehlermeldung eine konkrete Instanz und nicht 'null' angegeben wird, wurde die genannte Instanz nicht so konfiguriert, dass sie als Verteiler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4ec63-115">If the error message specifies a particular instance, rather than 'null', the instance specified has not been properly configured to be recognized as a Distributor.</span></span>  
  
 <span data-ttu-id="4ec63-116">Wenn in der Fehlermeldung als Verteiler 'null' angegeben wird, ist in der **master** -Datenbank kein Eintrag für den lokalen Server vorhanden, oder der Eintrag ist falsch (weil der Computer z. B. umbenannt worden ist).</span><span class="sxs-lookup"><span data-stu-id="4ec63-116">If the message specifies 'null' as a Distributor, there is no entry for the local server in **master** database, or the entry is incorrect (perhaps because the computer was renamed).</span></span> <span data-ttu-id="4ec63-117">Die Replikation erwartet, dass alle Server in einer Topologie mithilfe des Computernamens mit einem optionalen Instanznamen (bei Clusterinstanzen mithilfe des virtuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Servernamens mit dem optionalen Instanznamen) registriert werden.</span><span class="sxs-lookup"><span data-stu-id="4ec63-117">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="4ec63-118">Damit die Replikation ordnungsgemäß funktioniert, muss der von `SELECT @@SERVERNAME` für jeden Server in der Topologie zurückgegebene Wert mit dem Computernamen bzw. dem virtuellen Servernamen mit dem optionalen Instanznamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4ec63-118">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="4ec63-119">Die Replikation wird nicht unterstützt, wenn Sie eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen registriert haben.</span><span class="sxs-lookup"><span data-stu-id="4ec63-119">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="4ec63-120">Dieser Fehler kann ausgelöst werden, wenn beim Konfigurieren der Replikation eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] registriert war.</span><span class="sxs-lookup"><span data-stu-id="4ec63-120">If you had any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4ec63-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4ec63-121">User Action</span></span>  
 <span data-ttu-id="4ec63-122">Wenn in der Fehlermeldung eine konkrete Instanz genannt wird, konfigurieren Sie den Server als Verteiler.</span><span class="sxs-lookup"><span data-stu-id="4ec63-122">If the error message specifies a particular instance, configure the server as a Distributor.</span></span> <span data-ttu-id="4ec63-123">Weitere Informationen finden Sie unter [Configure Distribution](configure-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="4ec63-123">For more information, see [Configure Distribution](configure-distribution.md).</span></span>  
  
 <span data-ttu-id="4ec63-124">Wenn in der Fehlermeldung keine konkrete Instanz angegeben wird ('null'), überprüfen Sie, dass die Verteilerinstanz ordnungsgemäß registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4ec63-124">If the message does not specify a particular instance ('null'), verify that the Distributor instance is registered properly.</span></span> <span data-ttu-id="4ec63-125">Wenn der Netzwerkname des Computers und der Name der SQL Server-Instanz nicht identisch sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="4ec63-125">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="4ec63-126">Fügen Sie den SQL Server-Instanznamen als gültigen Netzwerknamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ec63-126">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="4ec63-127">Eine Möglichkeit, einen alternativen Netzwerknamen festzulegen, besteht darin, diesen Namen der lokalen Hostdatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4ec63-127">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="4ec63-128">Die lokale Hostdatei befindet sich im Verzeichnis WINDOWS\system32\drivers\usw. oder WINNT\system32\drivers\usw. Weitere Informationen finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4ec63-128">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="4ec63-129">Wenn der Computername z. B. comp1 ist und die IP-Adresse des Computers 10.193.17.129 lautet und wenn der Instanzname inst1/instname ist, ist der Hostdatei der folgende Eintrag hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="4ec63-129">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="4ec63-130">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="4ec63-130">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="4ec63-131">Deaktivieren Sie die Verteilung, registrieren Sie die Instanz, und stellen Sie dann die Verteilung wieder her.</span><span class="sxs-lookup"><span data-stu-id="4ec63-131">Disable distribution, register the instance, and then reestablish distribution.</span></span> <span data-ttu-id="4ec63-132">Wenn der @@SERVERNAME-Wert für eine nicht in einem Cluster befindliche Instanz falsch ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4ec63-132">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="4ec63-133">Nachdem Sie die gespeicherte Prozedur [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)ausgeführt haben, müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst neu starten, damit die Änderung an @@SERVERNAME wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="4ec63-133">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="4ec63-134">Wenn der @@SERVERNAME-Wert für eine in einem Cluster befindliche Instanz falsch ist, müssen Sie mithilfe der Clusterverwaltung den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="4ec63-134">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="4ec63-135">Weitere Informationen finden Sie unter [ Always On-Failoverclusterinstanzen (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4ec63-135">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec63-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ec63-136">See Also</span></span>  
 [<span data-ttu-id="4ec63-137">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="4ec63-137">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
