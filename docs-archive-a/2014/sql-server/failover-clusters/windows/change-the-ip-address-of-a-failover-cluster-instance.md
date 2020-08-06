---
title: Ändern der IP-Adresse einer Failoverclusterinstanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617573"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="f786b-102">Ändern der IP-Adresse einer Failoverclusterinstanz</span><span class="sxs-lookup"><span data-stu-id="f786b-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="f786b-103">In diesem Thema wird beschrieben, wie die IP-Adressressource in einer AlwaysOn-Failoverclusterinstanz (FCI) mithilfe des Failovercluster-Manager-Snap-Ins geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f786b-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="f786b-104">Das Failovercluster-Manager-Snap-In ist die Clusterverwaltungsanwendung für den WSFC (Windows Server Failover Clustering)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="f786b-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="f786b-105">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="f786b-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f786b-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f786b-106">Before You Begin</span></span>  
 <span data-ttu-id="f786b-107">Bevor Sie beginnen, lesen Sie sich das folgende Thema in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Onlinedokumentation durch: [Vor dem Installieren des Failoverclusterings](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="f786b-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f786b-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f786b-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f786b-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f786b-109">Permissions</span></span>  
 <span data-ttu-id="f786b-110">Zum Warten oder Aktualisieren einer FCI müssen Sie ein lokaler Administrator sein und über die Berechtigung verfügen, sich bei allen Knoten der FCI als Dienst anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f786b-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="f786b-111">Verwenden des Failovercluster-Manager-Snap-Ins</span><span class="sxs-lookup"><span data-stu-id="f786b-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="f786b-112">**So ändern Sie die IP-Adressressource für eine FCI**</span><span class="sxs-lookup"><span data-stu-id="f786b-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="f786b-113">Öffnen Sie des Failovercluster-Manager-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="f786b-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="f786b-114">Erweitern Sie den Knoten **Dienste und Anwendungen** im linken Bereich, und klicken Sie auf die FCI.</span><span class="sxs-lookup"><span data-stu-id="f786b-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="f786b-115">Klicken Sie im rechten Bereich unter der Kategorie **Servername** mit der rechten Maustaste auf die SQL Server-Instanz, und wählen Sie die Option **Eigenschaften** , um das Dialogfeld **Eigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f786b-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="f786b-116">Ändern Sie auf der Registerkarte **Allgemein** die IP-Adressressource.</span><span class="sxs-lookup"><span data-stu-id="f786b-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="f786b-117">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f786b-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="f786b-118">Klicken Sie im rechten Fensterbereich mit der rechten Maustaste auf „SQL IP Address1(Name der Failoverclusterinstanz)“, und wählen Sie **Offline schalten**aus.</span><span class="sxs-lookup"><span data-stu-id="f786b-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="f786b-119">SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name) und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Statusänderung von Online in Ausstehende Offlineschaltung und anschließend Offline werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f786b-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="f786b-120">Klicken Sie im rechten Fensterbereich mit der rechten Maustaste auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], und klicken Sie dann auf **Online schalten**.</span><span class="sxs-lookup"><span data-stu-id="f786b-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="f786b-121">SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name) und die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Statusänderung von Offline in Ausstehende Onlineschaltung und anschließend Online werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f786b-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="f786b-122">Schließen Sie das Failovercluster-Manager-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="f786b-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
