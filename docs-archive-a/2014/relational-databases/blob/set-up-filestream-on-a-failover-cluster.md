---
title: Einrichten von FILESTREAM auf einem Failovercluster | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695722"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="5724e-102">Einrichten von FILESTREAM auf einem Failovercluster</span><span class="sxs-lookup"><span data-stu-id="5724e-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="5724e-103">In diesem Thema erfahren Sie, wie Sie FILESTREAM auf einem Failovercluster aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5724e-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="5724e-104">Zur Durchführung dieser Prozedur müssen Sie mit [Failoverclustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) vertraut sein, und FILESTREAM muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="5724e-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="5724e-105">Informationen zum Aktivieren von FILESTREAM finden Sie unter [Aktivieren und Konfigurieren von FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="5724e-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="5724e-106">So richten Sie FILESTREAM auf einem Failovercluster ein</span><span class="sxs-lookup"><span data-stu-id="5724e-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="5724e-107">Richten Sie den primären Knoten für den Failovercluster ein.</span><span class="sxs-lookup"><span data-stu-id="5724e-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="5724e-108">Aktivieren Sie anschließend mit dem **SQL Server-Konfigurations-Manager**FILESTREAM auf dem primären Knoten.</span><span class="sxs-lookup"><span data-stu-id="5724e-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="5724e-109">Hierdurch werden die Einstellungen aktiviert, die Windows-Administratorrechte erfordern.</span><span class="sxs-lookup"><span data-stu-id="5724e-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="5724e-110">Wenn Remotezugriff erforderlich ist, wählen Sie **Streamingzugriff von Remoteclients auf FILESTREAM-Daten zulassen**.</span><span class="sxs-lookup"><span data-stu-id="5724e-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="5724e-111">Hierdurch wird eine geclusterte Dateifreigaberessource erstellt.</span><span class="sxs-lookup"><span data-stu-id="5724e-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="5724e-112">Richten Sie einen passiven Knoten ein.</span><span class="sxs-lookup"><span data-stu-id="5724e-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="5724e-113">Aktivieren Sie anschließend mit dem **SQL Server-Konfigurations-Manager**FILESTREAM auf dem passiven Knoten.</span><span class="sxs-lookup"><span data-stu-id="5724e-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="5724e-114">Der unter **Windows-Freigabename** angegebene Name muss auf allen Knoten im Cluster einheitlich sein.</span><span class="sxs-lookup"><span data-stu-id="5724e-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="5724e-115">Wiederholen Sie Schritt 2, um weitere passive Knoten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5724e-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="5724e-116">Nachdem Sie alle Knoten hinzugefügt haben, schließen Sie den Prozess ab, indem Sie die gespeicherte Prozedur sp_configure auf jeder Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="5724e-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="5724e-117">Wiederholen Sie die Schritte 2, 3 und 4, um dem Cluster weitere Knoten hinzuzufügen und diese zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5724e-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5724e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5724e-118">See Also</span></span>  
 <span data-ttu-id="5724e-119">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5724e-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="5724e-120">[Erstellen eines neuen SQL Server-Failoverclusters &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="5724e-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="5724e-121">[Entfernen einer SQL Server-Failoverclusterinstanz &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="5724e-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="5724e-122">Hinzufügen oder Entfernen von Knoten in einem SQL Server-Failovercluster &#40;Setup&#41;</span><span class="sxs-lookup"><span data-stu-id="5724e-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  