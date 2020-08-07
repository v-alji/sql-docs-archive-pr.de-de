---
title: SQL Server Eigenschaften (Registerkarte "hohe Verfügbarkeit" von AlwaysOn) | Microsoft-Dokumentation
description: Erfahren Sie, wie Sie die AlwaysOn-Verfügbarkeitsgruppen Funktion in SQL Server 2014 aktivieren oder deaktivieren. Anzeige Voraussetzungen anzeigen, die die Serverinstanz für dieses Feature erfüllen muss.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719276"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="88aa9-104">SQL Server-Eigenschaften (Registerkarte Hohe Verfügbarkeit (immer aktiviert))</span><span class="sxs-lookup"><span data-stu-id="88aa9-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="88aa9-105">Verwenden Sie die Registerkarte **Hohe Verfügbarkeit (immer aktiviert)** des Dialogfelds **SQL Server-Eigenschaften** im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager, um die Funktion AlwaysOn-Verfügbarkeitsgruppen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="88aa9-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="88aa9-106">Die Aktivierung von AlwaysOn-Verfügbarkeitsgruppen ist eine Voraussetzung dafür, dass eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz Verfügbarkeitsgruppen als Lösung für Hochverfügbarkeit und Notfallwiederherstellung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="88aa9-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="88aa9-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="88aa9-107">Prerequisites</span></span>  
 <span data-ttu-id="88aa9-108">Damit eine Serverinstanz für AlwaysOn-Verfügbarkeitsgruppen aktiviert werden kann, muss sie die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="88aa9-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="88aa9-109">Die Serverinstanz muss sich auf einem WSFC-Knoten (Windows Server Failover Clustering) befinden.</span><span class="sxs-lookup"><span data-stu-id="88aa9-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="88aa9-110">Instanzen müssen sich im gleichen WSFC-Cluster befinden, damit sie derselben Verfügbarkeitsgruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="88aa9-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="88aa9-111">Eine Verfügbarkeitsgruppe kann sich nicht über mehrere WSFC-Cluster erstrecken.</span><span class="sxs-lookup"><span data-stu-id="88aa9-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="88aa9-112">Auf der Serverinstanz muss eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Edition mit [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]-Unterstützung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88aa9-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="88aa9-113">AlwaysOn-Verfügbarkeitsgruppen sollten jeweils nur für eine Serverinstanz aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="88aa9-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="88aa9-114">Warten Sie nach der Aktivierung von AlwaysOn-Verfügbarkeitsgruppen, bis der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst neu gestartet wurde, bevor Sie die nächste Serverinstanz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88aa9-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88aa9-115">Informationen zur Funktionsunterstützung sowie zu zusätzlichen Voraussetzungen, Einschränkungen und Empfehlungen zu [!INCLUDE[ssHADR](../../includes/sshadr-md.md)]finden Sie in der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="88aa9-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="88aa9-116">Dialogfeldoptionen</span><span class="sxs-lookup"><span data-stu-id="88aa9-116">Dialog Options</span></span>  
 <span data-ttu-id="88aa9-117">**Name des Windows-Failoverclusters**</span><span class="sxs-lookup"><span data-stu-id="88aa9-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="88aa9-118">Zeigt den Namen des WSFC-Clusters an, in dem der lokale Computer einen Knoten darstellt.</span><span class="sxs-lookup"><span data-stu-id="88aa9-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="88aa9-119">**Aktivieren von AlwaysOn-Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="88aa9-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="88aa9-120">Verwenden Sie dieses Kontrollkästchen, um AlwaysOn-Verfügbarkeitsgruppen auf dieser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz wie folgt zu aktivieren oder deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="88aa9-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="88aa9-121">Wenn dieses Kontrollkästchen leer ist, sind AlwaysOn-Verfügbarkeitsgruppen derzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="88aa9-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="88aa9-122">Aktivieren Sie dieses Kontrollkästchen, um AlwaysOn-Verfügbarkeitsgruppen zu aktivieren, klicken Sie auf **OK**, und starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst manuell erneut.</span><span class="sxs-lookup"><span data-stu-id="88aa9-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="88aa9-123">Wenn dieses Kontrollkästchen bereits aktiviert ist, sind AlwaysOn-Verfügbarkeitsgruppen derzeit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88aa9-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="88aa9-124">Um AlwaysOn-Verfügbarkeitsgruppen zu deaktivieren, deaktivieren Sie das Kontrollkästchen und klicken auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="88aa9-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="88aa9-125">Dadurch wird die Serverinstanz neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="88aa9-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="88aa9-126">Nach der Deaktivierung von AlwaysOn-Verfügbarkeitsgruppen sollten Sie alle lokalen Verfügbarkeitsreplikate aus der Serverinstanz entfernen.</span><span class="sxs-lookup"><span data-stu-id="88aa9-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="88aa9-127">Nachdem Sie das letzte Replikat einer bestimmten Verfügbarkeitsgruppe entfernt haben, sollten Sie auch die Gruppe entfernen.</span><span class="sxs-lookup"><span data-stu-id="88aa9-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="88aa9-128">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="88aa9-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88aa9-129">Weitere Informationen zu den Schritten, die im Anschluss an die Deaktivierung von AlwaysOn-Verfügbarkeitsgruppen erforderlich sind, sowie Informationen zum Erstellen und Konfigurieren von Verfügbarkeitsgruppen finden Sie in der [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="88aa9-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
