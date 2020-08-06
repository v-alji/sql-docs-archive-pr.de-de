---
title: MSSQL_ENG014010 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014010 error
ms.assetid: 6ea84f2f-e7a2-4028-9ea9-af0d2eba660e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c3d989eb7ae78562fb77d9896545539ba4ca3c7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608563"
---
# <a name="mssql_eng014010"></a><span data-ttu-id="8e6b5-102">MSSQL_ENG014010</span><span class="sxs-lookup"><span data-stu-id="8e6b5-102">MSSQL_ENG014010</span></span>
    
## <a name="message-details"></a><span data-ttu-id="8e6b5-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="8e6b5-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8e6b5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8e6b5-104">Product Name</span></span>|<span data-ttu-id="8e6b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8e6b5-105">SQL Server</span></span>|  
|<span data-ttu-id="8e6b5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8e6b5-106">Event ID</span></span>|<span data-ttu-id="8e6b5-107">14010</span><span class="sxs-lookup"><span data-stu-id="8e6b5-107">14010</span></span>|  
|<span data-ttu-id="8e6b5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8e6b5-108">Event Source</span></span>|<span data-ttu-id="8e6b5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8e6b5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8e6b5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8e6b5-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="8e6b5-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8e6b5-111">Symbolic Name</span></span>||  
|<span data-ttu-id="8e6b5-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8e6b5-112">Message Text</span></span>|<span data-ttu-id="8e6b5-113">Der Server '%1!s!' ist nicht als Abonnementserver definiert.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-113">The server '%s' is not defined as a subscription server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8e6b5-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8e6b5-114">Explanation</span></span>  
 <span data-ttu-id="8e6b5-115">Die Replikation erwartet, dass alle Server in einer Topologie mithilfe des Computernamens mit einem optionalen Instanznamen (bei Clusterinstanzen mithilfe des virtuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Servernamens mit dem optionalen Instanznamen) registriert werden.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-115">Replication expects all servers in a topology to be registered using the computer name with an optional instance name (in the case of a clustered instance, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtual server name with the optional instance name).</span></span> <span data-ttu-id="8e6b5-116">Damit die Replikation ordnungsgemäß funktioniert, muss der von `SELECT @@SERVERNAME` für jeden Server in der Topologie zurückgegebene Wert mit dem Computernamen bzw. dem virtuellen Servernamen mit dem optionalen Instanznamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-116">For replication to function properly, the value returned by `SELECT @@SERVERNAME` for each server in the topology should match the computer name or virtual server name with the optional instance name.</span></span>  
  
 <span data-ttu-id="8e6b5-117">Die Replikation wird nicht unterstützt, wenn Sie eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen registriert haben.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-117">Replication is not supported if you have registered any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances by IP address or by Fully Qualified Domain Name (FQDN).</span></span> <span data-ttu-id="8e6b5-118">Dieser Fehler kann ausgelöst werden, wenn beim Konfigurieren der Replikation eine der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen über die IP-Adresse oder den vollqualifizierten Domänennamen in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] registriert ist.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-118">If you have any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances registered by IP address or by FQDN in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] when you configured replication, this error could be raised.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8e6b5-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8e6b5-119">User Action</span></span>  
 <span data-ttu-id="8e6b5-120">Überprüfen Sie, dass alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen der Topologie ordnungsgemäß registriert sind.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-120">Verify that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances in the topology are registered properly.</span></span> <span data-ttu-id="8e6b5-121">Wenn der Netzwerkname des Computers und der Name der SQL Server-Instanz nicht identisch sind, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8e6b5-121">If the network name of the computer and the name of the SQL Server instance differ, either:</span></span>  
  
-   <span data-ttu-id="8e6b5-122">Fügen Sie den SQL Server-Instanznamen als gültigen Netzwerknamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-122">Add the SQL Server instance name as a valid network name.</span></span> <span data-ttu-id="8e6b5-123">Eine Möglichkeit, einen alternativen Netzwerknamen festzulegen, besteht darin, diesen Namen der lokalen Hostdatei hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-123">One method to set an alternative network name is to add it to the local hosts file.</span></span> <span data-ttu-id="8e6b5-124">Die lokale Hostdatei befindet sich im Verzeichnis WINDOWS\system32\drivers\usw. oder WINNT\system32\drivers\usw. Weitere Informationen finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-124">The local hosts file is located by default at WINDOWS\system32\drivers\etc or WINNT\system32\drivers\etc. For more information, see the Windows documentation.</span></span>  
  
     <span data-ttu-id="8e6b5-125">Wenn der Computername z. B. comp1 ist und die IP-Adresse des Computers 10.193.17.129 lautet und wenn der Instanzname inst1/instname ist, ist der Hostdatei der folgende Eintrag hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8e6b5-125">For example, if the computer name is comp1 and the computer has an IP address of 10.193.17.129, and the instance name is inst1/instname, add the following entry to the hosts file:</span></span>  
  
     <span data-ttu-id="8e6b5-126">10.193.17.129 inst1</span><span class="sxs-lookup"><span data-stu-id="8e6b5-126">10.193.17.129 inst1</span></span>  
  
-   <span data-ttu-id="8e6b5-127">Entfernen Sie die Replikation, registrieren Sie einzelne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen, und stellen Sie dann die Replikation wieder her.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-127">Remove replication, register each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, and then reestablish replication.</span></span> <span data-ttu-id="8e6b5-128">Wenn der @@SERVERNAME-Wert für eine nicht in einem Cluster befindliche Instanz falsch ist, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8e6b5-128">If the value of @@SERVERNAME is not correct for a nonclustered instance, follow these steps:</span></span>  
  
    ```  
    sp_dropserver '<old_name>', 'droplogins'  
    go  
    sp_addserver '<new_name>', 'local'  
    go  
    ```  
  
     <span data-ttu-id="8e6b5-129">Nachdem Sie die gespeicherte Prozedur [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)ausgeführt haben, müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst neu starten, damit die Änderung an @@SERVERNAME wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-129">After you execute the [sp_addserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql) stored procedure, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service for the change to @@SERVERNAME to take effect.</span></span>  
  
     <span data-ttu-id="8e6b5-130">Wenn der @@SERVERNAME-Wert für eine in einem Cluster befindliche Instanz falsch ist, müssen Sie mithilfe der Clusterverwaltung den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="8e6b5-130">If the value of @@SERVERNAME is not correct for a clustered instance, you must change the name using Cluster Administrator.</span></span> <span data-ttu-id="8e6b5-131">Weitere Informationen finden Sie unter [AlwaysOn-Failoverclusterinstanzen &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="8e6b5-131">For more information, see [AlwaysOn Failover Cluster Instances &#40;SQL Server&#41;](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6b5-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e6b5-132">See Also</span></span>  
 <span data-ttu-id="8e6b5-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8e6b5-133">[@@SERVERNAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/servername-transact-sql) </span></span>  
 [<span data-ttu-id="8e6b5-134">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="8e6b5-134">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
