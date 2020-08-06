---
title: Cluster Netzwerkkonfiguration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617499"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="6f6d5-102">Netzwerkkonfiguration für Cluster</span><span class="sxs-lookup"><span data-stu-id="6f6d5-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="6f6d5-103">Verwenden Sie die Seite **Netzwerkauswahl für Cluster** , um die Netzwerkressourcen für die Failoverclusterinstanz anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f6d5-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6f6d5-104">Options</span></span>  
 <span data-ttu-id="6f6d5-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Netzwerk Name des Failoverclusters\*\* : Dies ist der Name, der zum Identifizieren der Failoverclusterinstanz im Netzwerk verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="6f6d5-106">**Netzwerkeinstellungen** – Geben Sie den IP-Typ und die IP-Adresse für die Failoverclusterinstanz an.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="6f6d5-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zeigt während der Vorgänge Knoten hinzufügen und Knoten entfernen eine schreibgeschützte Liste vorhandener IP-Adressen für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster an.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="6f6d5-108">Integrierte Installation:</span><span class="sxs-lookup"><span data-stu-id="6f6d5-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="6f6d5-109">Wenn Sie einen Knoten hinzufügen, der einen identischen Satz von Netzwerksubnetzen unterstützt, der von den vorhandenen Knoten des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failoverclusters unterstützt wird, können keine zusätzlichen IP-Adressen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="6f6d5-110">Die Abhängigkeitseinstellung bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="6f6d5-111">Wenn Sie einen Knoten hinzufügen, der eine Teilmenge der Subnetze unterstützt, die von den vorhandenen Knoten im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster unterstützt werden, können keine zusätzlichen IP-Adressressourcen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="6f6d5-112">Die Abhängigkeit der IP-Adressressource ist auf OR festgelegt, da nicht alle angegebenen IP-Adressen für alle Clusterknoten gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="6f6d5-113">Wenn Sie einen Knoten hinzufügen, der zusätzlich zu den Subnetzen, die von den bereits im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster vorhandenen Knoten unterstützt werden, weitere Subnetze unterstützt, können Sie neue gültige IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="6f6d5-114">Bei der Angabe neuer IP-Adressen wird die Abhängigkeit der IP-Adressressource auf OR festgelegt, da nicht alle angegebenen IP-Adressen für alle Clusterknoten gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="6f6d5-115">Wenn Sie einen Knoten hinzufügen, der zusätzliche Netzwerksubnetze unterstützt, jedoch keines der Subnetze, das von den im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster vorhandenen Knoten unterstützt wird, müssen Sie zusätzliche IP-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="6f6d5-116">Die Abhängigkeit der IP-Adressressource ist auf OR festgelegt, da nicht alle angegebenen IP-Adressen für alle Clusterknoten gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="6f6d5-117">Erweiterte Installation: Geben Sie während des Schritts Abschließen der Installation die IP-Adresse sämtlicher Knoten und Subnetze für die Failoverclusterinstanz an.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="6f6d5-118">Sie können für einen Multisubnetz-Failovercluster mehrere IP-Adressen angeben, jedoch wird nur eine IP-Adresse pro Subnetz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="6f6d5-119">Jeder vorbereitete Knoten sollte Besitzer von mindestens einer IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="6f6d5-120">Wenn im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Failovercluster mehrere Subnetze vorhanden sind, werden Sie aufgefordert, die Abhängigkeit der IP-Adressressource auf OR festzulegen. Knoten entfernen:</span><span class="sxs-lookup"><span data-stu-id="6f6d5-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="6f6d5-121">Wenn die restlichen IP-Adressen in allen restlichen Knoten unterstützt werden, werden Sie aufgefordert, die Abhängigkeit der IP-Adressressource auf AND festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="6f6d5-122">Wenn die restlichen IP-Adressen nicht in allen restlichen Knoten unterstützt werden, bleibt die Abhängigkeit der IP-Adressressource auf OR festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f6d5-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
