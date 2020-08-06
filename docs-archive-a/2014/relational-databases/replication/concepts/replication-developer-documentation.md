---
title: Entwickler&#39;s Guide (Replikation) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- developer's guide [SQL Server replication]
- programming [SQL Server replication]
- replication [SQL Server], development
ms.assetid: 7ee134ae-1cab-4a35-8017-8ac6d8fc64b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d9651aec1f02d19ea3494abf242f75049a4f33f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721390"
---
# <a name="developer39s-guide-replication"></a><span data-ttu-id="8c9dc-102">Entwickler&#39;s Guide (Replikation)</span><span class="sxs-lookup"><span data-stu-id="8c9dc-102">Developer&#39;s Guide (Replication)</span></span>
  <span data-ttu-id="8c9dc-103">Durch die Fähigkeit, eine Replikationstopologie programmgesteuert zu konfigurieren, zu warten und zu überwachen, können Sie häufig anfallende Replikationstasks vereinfachen und die Benutzerfreundlichkeit Ihrer replikationsbasierten Anwendungen verbessern.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-103">The ability to programmatically configure, maintain, and monitor a replication topology enables you to both simplify repeated replication tasks and improve the user experience for your replication-based applications.</span></span> <span data-ttu-id="8c9dc-104">Durch die Programmierung der Replikation können den Endbenutzern benutzerdefinierte Replikationsfunktionen bereitgestellt werden, ohne dass diese mit gespeicherten Replikationsprozeduren und ausführbaren Dateien von Replikations-Agents vertraut sein müssen oder die von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] implementierte Replikationsbenutzeroberfläche verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-104">By programming replication, your end-users can be provided with customized replication functionalities without having to be familiar with replication stored procedures and replication agent executables or having to using the replication user interface implemented by [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8c9dc-105">Im Folgenden werden Szenarien vorgestellt, in denen Ihre Anwendungen von einem programmgesteuerten Zugriff auf Replikationsdienste profitieren können:</span><span class="sxs-lookup"><span data-stu-id="8c9dc-105">The following are scenarios in which your applications might benefit from programmatic access to replication services:</span></span>  
  
-   <span data-ttu-id="8c9dc-106">Hinzufügen von Replikationsfunktionen zu einer vorhandenen Endbenutzeranwendung, z. B. Synchronisierung eines Pullabonnements, wenn der Benutzer auf eine Schaltfläche klickt.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-106">Adding replication functionalities to an existing end-user application, such as synchronizing a pull subscription when the user clicks a button.</span></span>   
-   <span data-ttu-id="8c9dc-107">Erstellen einer webbasierten Benutzeroberfläche zur Remoteverwaltung der Replikation.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-107">Creating a Web-based user interface for remotely administering replication.</span></span>    
-   <span data-ttu-id="8c9dc-108">Erstellen einer benutzerdefinierten Benutzeroberfläche, die nur einen Teil der Verwaltungsfunktionen zur Verfügung stellt und zur Remoteverwaltung mehrerer Replikationstopologien von einem einzelnen Speicherort aus verwendet werden kann oder Verwaltungs- und Synchronisierungsfunktionen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-108">Creating a custom user interface that exposes only a subset of administration functionality, can be used to remotely administer multiple replication topologies from a single location, or that combine administration and synchronization functionalities.</span></span>    
-   <span data-ttu-id="8c9dc-109">Verbessern eines vorhandenen Überwachungstools durch Hinzufügen der Funktion zur Überwachung des Status einer Veröffentlichung, eines Abonnements oder des Verteilers.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-109">Improving an existing monitoring tool by adding the ability to monitor the status of a publication, subscription, or at the Distributor.</span></span>    
-   <span data-ttu-id="8c9dc-110">Erstellen einer benutzerdefinierten Anwendung zum Verwalten oder Synchronisieren von Abonnements für einen Oracle-Verleger.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-110">Creating a custom application to administer or synchronize subscriptions to an Oracle publisher.</span></span>    
-   <span data-ttu-id="8c9dc-111">Schreiben von benutzerdefinierten Geschäftsregeln, die ausgeführt werden, wenn ein Mergeabonnement synchronisiert wird.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-111">Writing customized business rules that are executed when a merge subscription is synchronized.</span></span>    
-   <span data-ttu-id="8c9dc-112">Generieren von [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Skripts, die beim Konfigurieren neuer Abonnenten wiederholt ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-112">Generating [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts that can be run repeated when configuring new Subscribers.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="8c9dc-113">ermöglicht es Ihnen, Replikations-Agents programmgesteuert zu kontrollieren und eine Replikationstopologie programmgesteuert zu verwalten und zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-113">enables you to programmatically control replication agents and to programmatically administer and monitor a replication topology.</span></span> <span data-ttu-id="8c9dc-114">Weitere Informationen zum Programmieren der Replikation finden Sie unter [Konzepte für die Replikationsprogrammierung](replication-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="8c9dc-114">To learn more about programming replication, see [Replication Programming Concepts](replication-programming-concepts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c9dc-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8c9dc-115">In This Section</span></span>  
 [<span data-ttu-id="8c9dc-116">Konzepte für die Replikationsprogrammierung</span><span class="sxs-lookup"><span data-stu-id="8c9dc-116">Replication Programming Concepts</span></span>](replication-programming-concepts.md)  
 <span data-ttu-id="8c9dc-117">Beschreibt die Planungsschritte zur Entwicklung einer Anwendung, die die Replikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-117">Describes the planning steps to develop an application that uses replication.</span></span>  
  
 [<span data-ttu-id="8c9dc-118">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="8c9dc-118">Replication System Stored Procedures Concepts</span></span>](replication-system-stored-procedures-concepts.md)  
 <span data-ttu-id="8c9dc-119">Beschreibt, wie gespeicherte Systemprozeduren verwendet werden können, um programmgesteuerten Zugriff in einer Replikationstopologie bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-119">Describes how system stored procedures can be used to proivide programmatic access in a replication topology.</span></span>  
  
 [<span data-ttu-id="8c9dc-120">Replication Management Objects Concepts</span><span class="sxs-lookup"><span data-stu-id="8c9dc-120">Replication Management Objects Concepts</span></span>](replication-management-objects-concepts.md)  
 <span data-ttu-id="8c9dc-121">Erläutert die Konzepte zum Verwenden von Replikationsverwaltungsobjekten (RMO).</span><span class="sxs-lookup"><span data-stu-id="8c9dc-121">Explains the concepts for using Replication Management Objects (RMO).</span></span> <span data-ttu-id="8c9dc-122">Hierbei handelt es sich um eine verwaltete Codeassembly, die Replikationsfunktionen für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] kapselt.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-122">This is a managed code assembly that encapsulates replication functionalities for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8c9dc-123">Ausführbare Konzepte für die Programmierung von Replikations-Agent</span><span class="sxs-lookup"><span data-stu-id="8c9dc-123">Replication Agent Executables Concepts</span></span>](replication-agent-executables-concepts.md)  
 <span data-ttu-id="8c9dc-124">Beschreibt die Verwendung von ausführbaren Dateien von Replikations-Agents.</span><span class="sxs-lookup"><span data-stu-id="8c9dc-124">Describes the use of Replication Agent Executable files.</span></span>  

  
  
