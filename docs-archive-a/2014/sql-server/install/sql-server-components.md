---
title: SQL Server Komponenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726461"
---
# <a name="sql-server-components"></a><span data-ttu-id="8e591-102">SQL Server-Komponenten</span><span class="sxs-lookup"><span data-stu-id="8e591-102">SQL Server Components</span></span>
  <span data-ttu-id="8e591-103">Sie können den Analyse-Assistenten des Upgrade Advisors auf einem lokalen Computer oder einem Remote Computer ausführen, auf dem [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8e591-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="8e591-104">Der erste Schritt bei der Analyse vor dem Upgrade besteht darin, den Computer und die Komponenten für die Analyse zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8e591-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e591-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8e591-105">Options</span></span>  
 <span data-ttu-id="8e591-106">**Computername**</span><span class="sxs-lookup"><span data-stu-id="8e591-106">**Computer name**</span></span>  
 <span data-ttu-id="8e591-107">Gibt den Namen des zu analysierenden Computers an.</span><span class="sxs-lookup"><span data-stu-id="8e591-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="8e591-108">Der Upgrade Advisor füllt das Feld **Server Name** mit dem Namen des lokalen Computers auf.</span><span class="sxs-lookup"><span data-stu-id="8e591-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="8e591-109">Sie können auch "." und "localhost" verwenden, um die Verbindung mit dem lokalen Computer herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8e591-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="8e591-110">Wenn Sie einen anderen Computer analysieren, beachten Sie die folgenden Hinweise:</span><span class="sxs-lookup"><span data-stu-id="8e591-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="8e591-111">Um nicht gruppierte Instanzen zu scannen, geben Sie den Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="8e591-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="8e591-112">Um gruppierte Instanzen zu scannen, geben Sie den Namen der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Failoverclusterinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="8e591-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="8e591-113">Um nicht gruppierte Komponenten zu scannen, die auf einem Knoten eines Clusters installiert sind, geben Sie den Computernamen des Failoverclusterknotens ein.</span><span class="sxs-lookup"><span data-stu-id="8e591-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8e591-114">Geben Sie nicht den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanznamen an.</span><span class="sxs-lookup"><span data-stu-id="8e591-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="8e591-115">Statt den Computernamen anzugeben, können Sie auch die IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="8e591-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="8e591-116">Wenn Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scannen, müssen Sie den Namen des lokalen Computers angeben.</span><span class="sxs-lookup"><span data-stu-id="8e591-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="8e591-117">Der Upgrade Advisor scannt nur lokale Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="8e591-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="8e591-118">**Detect**</span><span class="sxs-lookup"><span data-stu-id="8e591-118">**Detect**</span></span>  
 <span data-ttu-id="8e591-119">Die Schaltfläche **ermitteln** greift auf den angegebenen Computer zu und erkennt die zu analysierenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="8e591-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="8e591-120">Wenn Sie auf einem Remotecomputer eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz analysieren, müssen Sie die Remoteregistrierungsdienste auf dem Remotecomputer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8e591-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8e591-121">wird erkannt, wenn eine Instanz von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] in der Registrierung des Computers gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8e591-121">is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="8e591-122">wird erkannt, wenn eine Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in der Registrierung des Computers gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8e591-122">is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="8e591-123">wird erkannt, wenn [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in der Registrierung des Computers gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8e591-123">is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="8e591-124">Allerdings scannt der Upgrade Advisor nur lokale Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="8e591-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="8e591-125">**Komponenten**</span><span class="sxs-lookup"><span data-stu-id="8e591-125">**Components**</span></span>  
 <span data-ttu-id="8e591-126">Wählen Sie die zu analysierenden Komponenten aus.</span><span class="sxs-lookup"><span data-stu-id="8e591-126">Select the components to analyze.</span></span> <span data-ttu-id="8e591-127">Sie können auf die Schaltfläche **erkennen** klicken, um alle auf dem Computer installierten Komponenten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="8e591-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="8e591-128">Ein Häkchen wird neben den Komponenten angezeigt, die als auf dem Computer installiert erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="8e591-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="8e591-129">Sie können die zu analysierenden Komponenten auch manuell auswählen, indem Sie die Kontrollkästchen neben den Komponenten aktivieren bzw. deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8e591-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e591-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e591-130">See Also</span></span>  
 <span data-ttu-id="8e591-131">[Arbeiten mit Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="8e591-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="8e591-132">Benutzeroberflächenreferenz des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="8e591-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
