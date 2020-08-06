---
title: Reparieren einer SQL Server 2014-Installation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 90c11b28-892b-44d6-978e-0eee48c75b7d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e382137a971b3f8b23cf1d814bff9908f04150
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701541"
---
# <a name="drop-a-sql-server-2014-installation"></a><span data-ttu-id="eeebb-102">Entfernen einer SQL Server 2014-Installation</span><span class="sxs-lookup"><span data-stu-id="eeebb-102">Drop a SQL Server 2014 Installation</span></span>
  <span data-ttu-id="eeebb-103">Der Reparaturvorgang kann in den folgenden Szenarien verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="eeebb-103">Repair operation can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="eeebb-104">Reparieren einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die beschädigt ist, nachdem sie erfolgreich installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="eeebb-104">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is corrupted after it was successfully installed.</span></span>  
  
-   <span data-ttu-id="eeebb-105">Reparieren einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , falls der Upgradevorgang abgebrochen wird oder ein Fehler auftritt, nachdem der Instanzname der neu aktualisierten Instanz zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="eeebb-105">Repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if the upgrade operation is cancelled or fails after the instance name is mapped to the newly-upgraded instance.</span></span>  
  
    -   <span data-ttu-id="eeebb-106">Wenn im Zusammenfassungsprotokoll die folgende Meldung angezeigt wird, können Sie die fehlerhafte Upgradeinstanz reparieren:</span><span class="sxs-lookup"><span data-stu-id="eeebb-106">If you see the following message in the summary log, you can repair the failed upgrade instance:</span></span>  
  
         <span data-ttu-id="eeebb-107">"Fehler beim Upgrade von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ."</span><span class="sxs-lookup"><span data-stu-id="eeebb-107">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="eeebb-108">Untersuchen Sie die Fehlerursache, beheben Sie das Problem, und reparieren Sie die Installation, um den Vorgang fortzusetzen."</span><span class="sxs-lookup"><span data-stu-id="eeebb-108">To continue, investigate the reason for the failure, correct the problem, and then repair your installation."</span></span>  
  
    -   <span data-ttu-id="eeebb-109">Wenn im Zusammenfassungsprotokoll die folgende Meldung angezeigt wird, müssen Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]deinstallieren und neu installieren.</span><span class="sxs-lookup"><span data-stu-id="eeebb-109">If you see the following message in the summary log, you need to uninstall and reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eeebb-110">Sie können die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz dann nicht reparieren.</span><span class="sxs-lookup"><span data-stu-id="eeebb-110">You cannot repair the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
         <span data-ttu-id="eeebb-111">"Fehler beim Upgrade von[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ."</span><span class="sxs-lookup"><span data-stu-id="eeebb-111">"[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade failed.</span></span> <span data-ttu-id="eeebb-112">Untersuchen Sie die Fehlerursache, und beheben Sie das Problem, um den Vorgang fortzusetzen."</span><span class="sxs-lookup"><span data-stu-id="eeebb-112">To continue, investigate the reason for the failure, correct the problem."</span></span>  
  
 <span data-ttu-id="eeebb-113">Beim Reparieren einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird Folgendes durchgeführt:</span><span class="sxs-lookup"><span data-stu-id="eeebb-113">When you repair an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="eeebb-114">Alle fehlenden oder beschädigten Dateien werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="eeebb-114">All missing or corrupt files are replaced.</span></span>  
  
-   <span data-ttu-id="eeebb-115">Alle fehlenden oder beschädigten Registrierungsschlüssel werden ersetzt.</span><span class="sxs-lookup"><span data-stu-id="eeebb-115">All missing or corrupt registry keys are replaced.</span></span>  
  
-   <span data-ttu-id="eeebb-116">Alle fehlenden oder ungültigen Konfigurationswerte werden auf die Standardwerte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eeebb-116">All missing or invalid configuration values are set to default values.</span></span>  
  
 <span data-ttu-id="eeebb-117">Bevor Sie den Vorgang fortsetzen, sollten Sie für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster die folgenden wichtigen Informationen überprüfen:</span><span class="sxs-lookup"><span data-stu-id="eeebb-117">Before you continue, for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover clusters, review the following important information:</span></span>  
  
-   <span data-ttu-id="eeebb-118">Die Reparatur muss auf jedem Clusterknoten einzeln ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eeebb-118">Repair must be run on individual cluster nodes.</span></span>  
  
-   <span data-ttu-id="eeebb-119">Verwenden Sie zum Reparieren eines Failoverclusterknotens nach Fehlern bei einem Vorbereitungsvorgang die Option **Knoten entfernen** , und führen Sie anschließend den Vorbereitungsschritt erneut aus.</span><span class="sxs-lookup"><span data-stu-id="eeebb-119">To repair a failover cluster node after a failed Prepare operation, use **Remove node** and then perform the Prepare step again.</span></span> <span data-ttu-id="eeebb-120">Weitere Informationen finden Sie unter [Hinzufügen oder Entfernen von Knoten in einem SQL Server-Failovercluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="eeebb-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-from-the-installation-center"></a><span data-ttu-id="eeebb-121">So reparieren Sie eine fehlerhafte Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über das Installationscenter</span><span class="sxs-lookup"><span data-stu-id="eeebb-121">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the Installation Center</span></span>  
  
1.  <span data-ttu-id="eeebb-122">Starten Sie auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installationsmedium das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setupprogramm (setup.exe).</span><span class="sxs-lookup"><span data-stu-id="eeebb-122">Launch the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program (setup.exe) from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span>  
  
2.  <span data-ttu-id="eeebb-123">Nachdem die erforderlichen Komponenten installiert wurden und die Systemüberprüfung durchgeführt wurde, zeigt das Setupprogramm das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installationscenter an.</span><span class="sxs-lookup"><span data-stu-id="eeebb-123">After prerequisites and system verification, the Setup program will display the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Center page.</span></span>  
  
3.  <span data-ttu-id="eeebb-124">Klicken Sie im linken Navigationsbereich auf **Wartung** , und klicken Sie dann auf **Reparieren** , um den Reparaturvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="eeebb-124">Click **Maintenance** in the left-hand navigation area, and then click **Repair** to start the repair operation.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="eeebb-125">Wenn das Installationscenter über das Startmenü gestartet wurde, müssen Sie zu dieser Zeit den Speicherort der Installationsmedien angeben.</span><span class="sxs-lookup"><span data-stu-id="eeebb-125">If the Installation Center was launched using the start menu, you will need to provide the location of the installation media at this time.</span></span>  
  
4.  <span data-ttu-id="eeebb-126">Es werden Unterstützungsregeln für Setup und Dateiroutinen ausgeführt, um sicherzustellen, dass die erforderlichen Komponenten auf dem System installiert sind und dass der Computer den Setupüberprüfungsregeln entspricht.</span><span class="sxs-lookup"><span data-stu-id="eeebb-126">Setup support rule and file routines will run to ensure that your system has prerequisites installed and that the computer passes Setup validation rules.</span></span> <span data-ttu-id="eeebb-127">Klicken Sie zum Fortsetzen auf **OK** oder auf **Installieren** .</span><span class="sxs-lookup"><span data-stu-id="eeebb-127">Click **OK** or **Install** to continue.</span></span>  
  
5.  <span data-ttu-id="eeebb-128">Wählen Sie auf der Seite **Instanz auswählen** die zu reparierende Instanz aus, und klicken Sie dann zum Fortsetzen auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="eeebb-128">On the Select Instance page, select the instance to repair, and then click **Next** to continue.</span></span>  
  
6.  <span data-ttu-id="eeebb-129">Die Reparaturregeln werden ausgeführt, um den Vorgang zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eeebb-129">The repair rules will run to validate the operation.</span></span> <span data-ttu-id="eeebb-130">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="eeebb-130">To continue, click **Next**.</span></span>  
  
7.  <span data-ttu-id="eeebb-131">Wenn die Seite Bereit zum Reparieren angezeigt wird, kann der Vorgang fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="eeebb-131">The Ready to Repair page indicates that the operation is ready to proceed.</span></span> <span data-ttu-id="eeebb-132">Klicken Sie zum Fortsetzen auf **Reparieren**.</span><span class="sxs-lookup"><span data-stu-id="eeebb-132">To continue, click **Repair**.</span></span>  
  
8.  <span data-ttu-id="eeebb-133">Auf der Seite Reparaturstatus wird der Status des Reparaturvorgangs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eeebb-133">The Repair Progress page shows the status of the repair operation.</span></span> <span data-ttu-id="eeebb-134">Wenn die Seite Abgeschlossen angezeigt wird, wurde der Vorgang abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="eeebb-134">The Complete page indicates that the operation is finished.</span></span>  
  
### <a name="to-repair-a-failed-installation-of-ssnoversion-using-command-prompt"></a><span data-ttu-id="eeebb-135">So reparieren Sie eine fehlerhafte Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über die Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="eeebb-135">To repair a failed installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Command Prompt</span></span>  
  
1.  <span data-ttu-id="eeebb-136">Führen Sie an der Eingabeaufforderung den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="eeebb-136">Run the following command at a command prompt:</span></span>  
  
    ```  
    Setup.exe /q /ACTION=Repair /INSTANCENAME=instancename  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eeebb-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eeebb-137">See Also</span></span>  
 <span data-ttu-id="eeebb-138">[Lesen und Anzeigen der Setupprotokolldateien von SQL Server](view-and-read-sql-server-setup-log-files.md) </span><span class="sxs-lookup"><span data-stu-id="eeebb-138">[View and Read SQL Server Setup Log Files](view-and-read-sql-server-setup-log-files.md) </span></span>  
 [<span data-ttu-id="eeebb-139">Themen zu Vorgehensweisen für die Installation</span><span class="sxs-lookup"><span data-stu-id="eeebb-139">Installation How-to Topics</span></span>](../../sql-server/install/installation-how-to-topics.md)  
  
  
