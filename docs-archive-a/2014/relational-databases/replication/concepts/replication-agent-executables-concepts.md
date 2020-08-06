---
title: Ausführbare Konzepte für die Programmierung von Replikations-Agents | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725534"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="c50b6-102">Ausführbare Konzepte für die Programmierung von Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="c50b6-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="c50b6-103">Replikations-Agents können wie folgt programmgesteuert kontrolliert werden:</span><span class="sxs-lookup"><span data-stu-id="c50b6-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="c50b6-104">Mit den verwalteten Schnittstellen für die Agent-Programmierung im <xref:Microsoft.SqlServer.Replication> Namespace</span><span class="sxs-lookup"><span data-stu-id="c50b6-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="c50b6-105">Durch Aufrufen von ausführbaren Dateien von Agents mit einem angegebenen Satz von Parametern von der Eingabeaufforderung aus</span><span class="sxs-lookup"><span data-stu-id="c50b6-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="c50b6-106">Das direkte Aufrufen von Replikations-Agents von der Eingabeaufforderung aus ermöglicht den programmgesteuerten Zugriff auf Agents vom Befehlszeilenskript in Batchdateien.</span><span class="sxs-lookup"><span data-stu-id="c50b6-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="c50b6-107">Wenn ein Agent von der Eingabeaufforderung aus aufgerufen wird, wird er unter dem [!INCLUDE[msCoName](../../../includes/msconame-md.md)]-Windows-Sicherheitskonto des Benutzers ausgeführt, der den Agent aufgerufen oder die Batchdatei gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="c50b6-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="c50b6-108">Instanzen der folgenden Replikations-Agents können mit ausführbaren Dateien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c50b6-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="c50b6-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="c50b6-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="c50b6-110">Replikationsprotokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="c50b6-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="c50b6-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="c50b6-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="c50b6-112">Replication Queue Reader Agent</span><span class="sxs-lookup"><span data-stu-id="c50b6-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="c50b6-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="c50b6-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="c50b6-114">Beim Aufrufen von Replikations-Agents können Sie Leistungsprofile verwenden, um einen definierten Satz von Parametern automatisch an die ausführbare Datei des Agents zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c50b6-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="c50b6-115">Weitere Informationen finden Sie unter [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c50b6-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c50b6-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c50b6-116">Examples</span></span>  
 <span data-ttu-id="c50b6-117">Die folgenden Beispiele zeigen, wie Replikations-Agents von der Eingabeaufforderung aus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c50b6-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="c50b6-118">Replikations-Agents können auch mit Replikationsverwaltungsobjekten (Replication Management Objects, RMO) aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c50b6-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="c50b6-119">Weitere Informationen finden Sie unter [Synchronisieren von Abonnements](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="c50b6-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c50b6-120">Zeilenumbrüche wurden in diesen Beispielen hinzugefügt, um die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="c50b6-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="c50b6-121">In einer Batchdatei müssen Befehle in einer einzelnen Zeile stehen.</span><span class="sxs-lookup"><span data-stu-id="c50b6-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="c50b6-122">Ausführen des Momentaufnahme-Agents</span><span class="sxs-lookup"><span data-stu-id="c50b6-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="c50b6-123">Mit dieser Beispielbatchdatei wird der Momentaufnahme-Agent von der Befehlsaufforderung aus aufgerufen, um eine Momentaufnahme für die **AdvWorksSalesOrdersMerge**-Veröffentlichung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c50b6-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="c50b6-124">Ausführen des Verteilungs-Agents</span><span class="sxs-lookup"><span data-stu-id="c50b6-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="c50b6-125">Mit dieser Beispielbatchdatei wird der Verteilungs-Agent von der Eingabeaufforderung aus aufgerufen, um Änderungen der **AdvWorksProductTran**-Veröffentlichung kontinuierlich an einen Pushabonnenten zu replizieren.</span><span class="sxs-lookup"><span data-stu-id="c50b6-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="c50b6-126">Ausführen des Merge-Agents</span><span class="sxs-lookup"><span data-stu-id="c50b6-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="c50b6-127">Mit dieser Beispielbatchdatei wird der Merge-Agent von der Eingabeaufforderung aus aufgerufen, um ein Pullabonnement für die **AdvWorksSalesOrdersMerge**-Veröffentlichung zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="c50b6-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
