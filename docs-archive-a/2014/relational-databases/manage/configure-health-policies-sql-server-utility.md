---
title: Konfigurieren von Integritätsrichtlinien (SQL Server-Hilfsprogramm) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609894"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="3e09b-102">Konfigurieren von Integritätsrichtlinien (SQL Server-Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="3e09b-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="3e09b-103">Verwenden Sie das Dashboard des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , um Ressourcenparameter des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms für verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und Datenebenenanwendungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3e09b-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="3e09b-104">Weitere Informationen finden Sie unter [Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="3e09b-105">Um Ergebnisse der Integritätsrichtlinien des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms anzuzeigen, stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Steuerungspunkt für das Hilfsprogramm her.</span><span class="sxs-lookup"><span data-stu-id="3e09b-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="3e09b-106">Weitere Informationen finden Sie unter [Verwenden des Hilfsprogramm-Explorers zum Verwalten des SQL Server-Hilfsprogramms](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e09b-107">Integritätsrichtlinien des Hilfsprogramms können für Datenebenenanwendungen und verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3e09b-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e09b-108">Integritätsrichtlinien können global für alle Datenebenenanwendungen und verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm definiert werden, oder Sie definieren sie für jede Datenebenenanwendung und jede verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einzeln im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="3e09b-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="3e09b-109">Überwachen von Richtlinien für Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="3e09b-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="3e09b-110">Folgende Richtlinien gelten für die Über- und Unterauslastung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenebenenanwendungen:</span><span class="sxs-lookup"><span data-stu-id="3e09b-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="3e09b-111">Prozessorauslastung der Datenebenenanwendung</span><span class="sxs-lookup"><span data-stu-id="3e09b-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="3e09b-112">Dateispeicherplatz der Datenebenenanwendung für Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="3e09b-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="3e09b-113">Dateispeicherplatz der Datenebenenanwendung für Speichervolumes</span><span class="sxs-lookup"><span data-stu-id="3e09b-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="3e09b-114">Prozessorauslastung des Computers</span><span class="sxs-lookup"><span data-stu-id="3e09b-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e09b-115">Speichervolume und Prozessorauslastung sind für Datenebenenanwendungen schreibgeschützte Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="3e09b-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="3e09b-116">Weitere Informationen zum Anzeigen oder Ändern globaler Überwachungsrichtlinien für Datenebenenanwendungen finden Sie unter [Hilfsprogrammverwaltung &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="3e09b-117">Weitere Informationen zum Anzeigen oder Ändern globaler Überwachungsrichtlinien für Datenebenenanwendungen finden Sie unter [Details zu bereitgestellten Datenebenenanwendungen &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="3e09b-118">Überwachen von Richtlinien für verwaltete SQL Server-Instanzen</span><span class="sxs-lookup"><span data-stu-id="3e09b-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="3e09b-119">Richtlinien zur Über- und Unterauslastung für verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3e09b-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e09b-120">-Instanz</span><span class="sxs-lookup"><span data-stu-id="3e09b-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e09b-121">-Instanz für Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="3e09b-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3e09b-122">-Instanz für Speichervolumes</span><span class="sxs-lookup"><span data-stu-id="3e09b-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="3e09b-123">Prozessorauslastung des Computers</span><span class="sxs-lookup"><span data-stu-id="3e09b-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="3e09b-124">Weitere Informationen zum Anzeigen oder Ändern globaler Überwachungsrichtlinien von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finden Sie unter [Hilfsprogrammverwaltung &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="3e09b-125">Weitere Informationen zum Anzeigen oder Ändern von Überwachungsrichtlinien für einzelne verwaltete Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finden Sie unter [Details zu verwalteten Instanzen &#40;SQL Server-Hilfsprogramm&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3e09b-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e09b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e09b-126">See Also</span></span>  
 <span data-ttu-id="3e09b-127">[Funktionen und Tasks im SQL Server-Hilfsprogramm](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="3e09b-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="3e09b-128">Reduzieren von Informationsrauschen bei Richtlinien zur CPU-Auslastung &#40;SQL Server-Hilfsprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="3e09b-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
