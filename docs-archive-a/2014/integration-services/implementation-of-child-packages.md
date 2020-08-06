---
title: Implementierung von untergeordneten Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- child packages
ms.assetid: ab0c09d7-ce2e-487d-a1ed-a4b5adb6cc01
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4fa4fa7c523c55c595341c7aee6a530c5918a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698451"
---
# <a name="implementation-of-child-packages"></a><span data-ttu-id="2741d-102">Implementierung von untergeordneten Paketen</span><span class="sxs-lookup"><span data-stu-id="2741d-102">Implementation of Child Packages</span></span>
  <span data-ttu-id="2741d-103">Wenn Sie mithilfe von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]den Lastenausgleich implementieren, werden die untergeordneten Pakete auf anderen Servern installiert, um die verfügbare CPU bzw. die Serverzeit zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="2741d-103">When you implement load balancing using [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], child packages are installed on other servers to take advantage of the available CPU or server time.</span></span> <span data-ttu-id="2741d-104">Für das Erstellen und Ausführen der untergeordneten Pakete sind die folgenden Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2741d-104">To create and run the child packages requires the following steps:</span></span>  
  
-   <span data-ttu-id="2741d-105">Entwerfen der untergeordneten Pakete.</span><span class="sxs-lookup"><span data-stu-id="2741d-105">Designing the child packages.</span></span>  
  
-   <span data-ttu-id="2741d-106">Verschieben der Pakete auf den Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="2741d-106">Moving the packages to the remote server.</span></span>  
  
-   <span data-ttu-id="2741d-107">Erstellen eines Auftrags des SQL Server-Agents auf dem Remoteserver, der einen Schritt zum Ausführen des untergeordneten Pakets enthält.</span><span class="sxs-lookup"><span data-stu-id="2741d-107">Creating a SQL Server Agent Job on the remote server that contains a step that runs the child package.</span></span>  
  
-   <span data-ttu-id="2741d-108">Testen und Debuggen des Auftrags des SQL Server-Agents und der untergeordneten Pakete.</span><span class="sxs-lookup"><span data-stu-id="2741d-108">Testing and debugging the SQL Server Agent Job and child packages.</span></span>  
  
 <span data-ttu-id="2741d-109">Beim Entwerfen der untergeordneten Pakete sind die Entwurfsmöglichkeiten unbegrenzt. Dabei können Sie jede beliebige Funktionalität verwenden.</span><span class="sxs-lookup"><span data-stu-id="2741d-109">When you design the child packages, the packages have no limitations in their design, and you can put in any functionality you desire.</span></span> <span data-ttu-id="2741d-110">Beim Zugriff des Pakets auf die Daten müssen Sie jedoch sicherstellen, dass der Server, mit dem das Paket ausgeführt wird, auf die Daten zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="2741d-110">However, if the package accesses data, you must ensure that the server that runs the package has access to the data.</span></span>  
  
 <span data-ttu-id="2741d-111">Um das übergeordnete Paket zu identifizieren, das untergeordnete Pakete ausführt, klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] mit der rechten Maustaste auf das Paket in Projektmappen-Explorer, und klicken Sie dann auf **Einstiegspunktpaket**.</span><span class="sxs-lookup"><span data-stu-id="2741d-111">To identify the parent package that executes child packages, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] right click the package in Solution Explorer and then click **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="2741d-112">Nach dem Entwerfen der untergeordneten Pakete werden diese im nächsten Schritt auf den Remoteservern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2741d-112">After the child packages have been designed, the next step is to deploy them on the remote servers.</span></span>  
  
## <a name="moving-the-child-package-to-the-remote-instance"></a><span data-ttu-id="2741d-113">Verschieben des untergeordneten Pakets auf die Remoteinstanz</span><span class="sxs-lookup"><span data-stu-id="2741d-113">Moving the Child Package to the Remote Instance</span></span>  
 <span data-ttu-id="2741d-114">Es gibt mehrere Möglichkeiten zum Verschieben von Paketen auf andere Server.</span><span class="sxs-lookup"><span data-stu-id="2741d-114">There are multiple ways to move packages to other servers.</span></span> <span data-ttu-id="2741d-115">Es werden die folgenden zwei Methoden vorgeschlagen:</span><span class="sxs-lookup"><span data-stu-id="2741d-115">The two suggested methods are:</span></span>  
  
-   <span data-ttu-id="2741d-116">Exportieren von Paketen mithilfe von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2741d-116">Exporting packages by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="2741d-117">Bereitstellen von Paketen durch Erstellen eines Bereitstellungshilfsprogramms für das Projekt, in dem die bereitzustellenden Pakete enthalten sind, und anschließendes Ausführen des Paketinstallations-Assistenten zum Installieren der Pakete im Dateisystem bzw. in einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2741d-117">Deploying packages by building a deployment utility for the project that contains the packages you want to deploy, and then running the Package Installation Wizard to install the packages to the file system or to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2741d-118">Weitere Informationen finden Sie unter [Paket Bereitstellung &#40;SSIS-&#41;](packages/legacy-package-deployment-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="2741d-118">For more information, see [Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md).</span></span>  
  
 <span data-ttu-id="2741d-119">Sie müssen die Bereitstellung für jeden zu verwendenden Remoteserver wiederholen.</span><span class="sxs-lookup"><span data-stu-id="2741d-119">You must repeat the deployment to each remote server you want to use.</span></span>  
  
## <a name="creating-the-sql-server-agent-jobs"></a><span data-ttu-id="2741d-120">Erstellen der Aufträge des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="2741d-120">Creating the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="2741d-121">Nach dem Bereitstellen der untergeordneten Pakete auf verschiedenen Servern müssen Sie auf jedem Server, auf dem ein untergeordnetes Paket enthalten ist, einen Auftrag des SQL Server-Agents erstellen.</span><span class="sxs-lookup"><span data-stu-id="2741d-121">After the child packages have been deployed to the various servers, create a SQL Server Agent job on each server that contains a child package.</span></span> <span data-ttu-id="2741d-122">Der Auftrag des SQL Server-Agents enthält einen Schritt zum Ausführen der untergeordneten Pakete beim Aufruf des Agentauftrags.</span><span class="sxs-lookup"><span data-stu-id="2741d-122">The SQL Server Agent job contains a step that runs the child package when the job agent is called.</span></span> <span data-ttu-id="2741d-123">Die Aufträge des SQL Server-Agents sind keine geplanten Aufträge. Sie führen die untergeordneten Pakete nur dann aus, wenn Sie vom übergeordneten Paket aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2741d-123">The SQL Server Agent jobs are not scheduled jobs; they run the child packages only when they are called by the parent package.</span></span> <span data-ttu-id="2741d-124">Die Benachrichtigung über den Erfolg oder Misserfolg des Auftrags an das übergeordnete Paket spiegelt den Erfolg oder Misserfolg des Auftrags des SQL Server-Agents wider und gibt an, ob der Auftrag erfolgreich aufgerufen wurde. Die Benachrichtigung beinhaltet jedoch nicht den Erfolg oder Misserfolg des untergeordneten Pakets bzw. eine Benachrichtigung, ob das Paket ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="2741d-124">Notification of success or failure of the job back to the parent package reflects the success or failure of the SQL Server Agent job and whether it was called successfully, not the success or failure of the child package or whether it was executed.</span></span>  
  
## <a name="debugging-the-sql-server-agent-jobs-and-child-packages"></a><span data-ttu-id="2741d-125">Debuggen der Aufträge des SQL Server-Agents und der untergeordneten Pakete</span><span class="sxs-lookup"><span data-stu-id="2741d-125">Debugging the SQL Server Agent Jobs and Child Packages</span></span>  
 <span data-ttu-id="2741d-126">Sie können die Aufträge des SQL Server-Agents und ihre untergeordneten Pakete testen, indem Sie eine der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="2741d-126">You can test the SQL Server Agent jobs and their child packages by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="2741d-127">Ausführen der einzelnen untergeordneten Pakete im SSIS-Designer, indem Sie auf **Debuggen**  /  **Starten ohne Debugging**klicken.</span><span class="sxs-lookup"><span data-stu-id="2741d-127">Running each child package in SSIS Designer, by clicking **Debug** / **Start Without Debugging**.</span></span>  
  
-   <span data-ttu-id="2741d-128">Ausführen der einzelnen Aufträge des SQL Server-Agents auf dem Remotecomputer mithilfe von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], um sicherzustellen, dass die Pakete ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2741d-128">Running the individual SQL Server Agent job on the remote computer by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to make sure that the package runs.</span></span>  
  
 <span data-ttu-id="2741d-129">Weitere Informationen zur Fehlerbehebung bei der Ausführung von Paketen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Aufträgen finden Sie unter [SSIS-Paket wird nicht ausgeführt, wenn das SSIS-Paket von einem SQL Server-Agent-Auftrag abgerufen wird](https://support.microsoft.com/kb/918760) in der [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base für Support.</span><span class="sxs-lookup"><span data-stu-id="2741d-129">For information about how to troubleshoot packages that you run from [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs, see [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760) in the [!INCLUDE[msCoName](../includes/msconame-md.md)] Support Knowledge Base.</span></span>  
  
 <span data-ttu-id="2741d-130">Vom SQL Server-Agent wird der Subsystemzugriff für einen Proxy überprüft und der Zugriff auf den Proxy jedes Mal gewährt, wenn der Auftragsschritt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2741d-130">The SQL Server Agent checks subsystem access for a proxy and gives access to the proxy every time the job step runs.</span></span>  
  
 <span data-ttu-id="2741d-131">Sie können einen Proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="2741d-131">You can create a proxy in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="2741d-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2741d-132">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2741d-133">Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2741d-133">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
## <a name="related-content"></a><span data-ttu-id="2741d-134">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2741d-134">Related Content</span></span>  
  
-   <span data-ttu-id="2741d-135">Blogeintrag zu [SSIS: Zugreifen auf Variablen in einem übergeordneten Paket](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/)auf "andyleonard. Blog".</span><span class="sxs-lookup"><span data-stu-id="2741d-135">Blog entry, [SSIS: Accessing variables in a parent package](https://andyleonard.blog/2015/08/ssis-design-pattern-access-parent-variables-from-a-child-package-in-the-ssis-catalog/), on andyleonard.blog.</span></span>  
  
-   <span data-ttu-id="2741d-136">Artikel [Paket ausführen (Task](../integration-services/control-flow/execute-package-task.md)).</span><span class="sxs-lookup"><span data-stu-id="2741d-136">Article, [Execute Package Task](../integration-services/control-flow/execute-package-task.md).</span></span>  
  
  
