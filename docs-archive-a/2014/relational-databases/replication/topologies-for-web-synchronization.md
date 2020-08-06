---
title: Topologien für die Websynchronisierung | Microsoft Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618642"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="0b658-102">Topologies for Web Synchronization</span><span class="sxs-lookup"><span data-stu-id="0b658-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="0b658-103">Sie können aus unterschiedlichen Websynchronisierungs-Replikationstopologien von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auswählen.</span><span class="sxs-lookup"><span data-stu-id="0b658-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="0b658-104">Hier einige der gängigen Konfigurationsmethoden für die Websynchronisierung:</span><span class="sxs-lookup"><span data-stu-id="0b658-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="0b658-105">Einzelserver</span><span class="sxs-lookup"><span data-stu-id="0b658-105">Single server</span></span>  
  
-   <span data-ttu-id="0b658-106">Zwei Server</span><span class="sxs-lookup"><span data-stu-id="0b658-106">Two servers</span></span>  
  
-   <span data-ttu-id="0b658-107">Mehrere Systeme mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internetinformationsdiensten (IIS, Internet Information Services) und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Wiederveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="0b658-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="0b658-108">Informationen zur Konfiguration der Websynchronisierung finden Sie unter [Konfigurieren der Websynchronisierung](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="0b658-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="0b658-109">Einzelner Server</span><span class="sxs-lookup"><span data-stu-id="0b658-109">Single Server</span></span>  
 <span data-ttu-id="0b658-110">In der einfachsten Topologie befinden sich IIS, der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verleger sowie der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verteiler auf einem einzigen Server.</span><span class="sxs-lookup"><span data-stu-id="0b658-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="0b658-111">Die Abonnenten führen den Synchronisierungsvorgang aus, indem sie mit IIS auf dem Verleger eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="0b658-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="0b658-112">Der Verleger kann sich hinter einer Firewall befinden.</span><span class="sxs-lookup"><span data-stu-id="0b658-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b658-113">Diese Konfiguration wird nur für Intranetszenarien empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0b658-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="0b658-114">Bei anderen Szenarien sollten sich der IIS-Server und der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verleger/-Verteiler auf separaten Computern befinden.</span><span class="sxs-lookup"><span data-stu-id="0b658-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="0b658-115">![Websynchronisierung mit einem einzelnen Server](media/web-sync02.gif "Websynchronisierung mit einem einzelnen Server")</span><span class="sxs-lookup"><span data-stu-id="0b658-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="0b658-116">Zwei Server</span><span class="sxs-lookup"><span data-stu-id="0b658-116">Two Servers</span></span>  
 <span data-ttu-id="0b658-117">Sie können IIS auf dem einen Server installieren und den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verleger/-Verteiler auf dem anderen Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0b658-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="0b658-118">Der Server, auf dem IIS ausgeführt wird, kann durch eine Firewall vom Internet isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="0b658-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="0b658-119">Die Abonnenten führen den Synchronisierungsvorgang aus, indem sie mit IIS auf dem Verleger eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="0b658-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="0b658-120">![Websynchronisierung mit zwei Servern](media/web-sync03.gif "Websynchronisierung mit zwei Servern")</span><span class="sxs-lookup"><span data-stu-id="0b658-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="0b658-121">Mehrere IIS-Systeme und SQL Server-Wiederveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="0b658-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="0b658-122">Wenn eine große Anzahl an Abonnenten unterstützt werden müssen, die gleichzeitig synchronisieren, kann die Arbeitsauslastung auf mehrere Computer verteilt werden, auf denen IIS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0b658-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="0b658-123">![Websynchronisierung mit mehreren IIS-Servern](media/web-sync04.gif "Websynchronisierung mit mehreren IIS-Servern")</span><span class="sxs-lookup"><span data-stu-id="0b658-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="0b658-124">Wenn auf dem Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt ist, weiterer Lastenausgleich erforderlich ist, können Sie auf mehreren Computern eine Wiederveröffentlichungshierarchie erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b658-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="0b658-125">Der Verleger der obersten Ebene veröffentlicht Daten für Abonnenten, die die Daten wiederum erneut veröffentlichen; hierbei erfolgt der Lastenausgleich hinsichtlich Anforderungen von Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="0b658-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b658-126">Abonnenten können nur mit einem bestimmten Verleger synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0b658-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="0b658-127">Beispielsweise kann ein Abonnent von Neuverleger A nicht mit Neuverleger B synchronisiert werden, wenn A nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b658-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="0b658-128">![Websynchronisierung mit Wiederveröffentlichung](media/web-sync05.gif "Websynchronisierung mit Wiederveröffentlichung")</span><span class="sxs-lookup"><span data-stu-id="0b658-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b658-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b658-129">See Also</span></span>  
 <span data-ttu-id="0b658-130">[Konfigurieren der Websynchronisierung](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="0b658-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="0b658-131">Websynchronisierung für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="0b658-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
