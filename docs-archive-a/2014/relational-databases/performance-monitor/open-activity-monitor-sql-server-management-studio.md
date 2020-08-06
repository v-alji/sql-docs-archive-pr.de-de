---
title: Öffnen des Aktivitätsmonitors (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server], setting the refresh interval
- refresh interval for Activity Monitor
- Activity Monitor [SQL Server], opening
- opening Activity Monitor
ms.assetid: 0a6eeb16-f02b-479d-9a60-543e40ebf46b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea74122ad18a0a1ede5eef1e09684606ca0ce073
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723718"
---
# <a name="open-activity-monitor-sql-server-management-studio"></a><span data-ttu-id="7b9be-102">Öffnen des Aktivitätsmonitors (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7b9be-102">Open Activity Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7b9be-103">In diesem Thema wird das Öffnen des Aktivitätsmonitors beschrieben, der Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozesse und deren Auswirkungen auf die aktuelle Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gibt.</span><span class="sxs-lookup"><span data-stu-id="7b9be-103">This topic describes how to open the Activity Monitor to obtain information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b9be-104">Zudem wird beschrieben, wie Sie das Aktualisierungsintervall des Aktivitätsmonitors festgelegen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-104">It also describes how to set the refresh interval of the Activity Monitor.</span></span>  
  
 <span data-ttu-id="7b9be-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7b9be-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7b9be-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7b9be-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7b9be-107">Security</span><span class="sxs-lookup"><span data-stu-id="7b9be-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7b9be-108">**So öffnen Sie den Aktivitätsmonitor mit:**</span><span class="sxs-lookup"><span data-stu-id="7b9be-108">**To open the Activity Monitor using:**</span></span>  
  
     [<span data-ttu-id="7b9be-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b9be-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="7b9be-110">**Festlegen des Aktualisierungsintervalls mit:**  [SQL Server Management Studio](#Refresh)</span><span class="sxs-lookup"><span data-stu-id="7b9be-110">**To set the refresh interval using:**  [SQL Server Management Studio](#Refresh)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7b9be-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7b9be-111">Before You Begin</span></span>  
 <span data-ttu-id="7b9be-112">Der Aktivitätsmonitor führt Abfragen auf der überwachten Instanz aus, um Informationen für die Anzeigebereiche des Aktivitätsmonitors abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-112">Activity Monitor runs queries on the monitored instance to obtain information for the Activity Monitor display panes.</span></span> <span data-ttu-id="7b9be-113">Wenn für das Intervall für die automatische Aktualisierung weniger als 10 Sekunden festgelegt sind, kann die für die Ausführung der Abfragen benötigte Zeit die Serverleistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-113">When the refresh interval is set to less than 10 seconds, the time that is used to run these queries can affect server performance</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7b9be-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7b9be-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7b9be-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7b9be-115">Permissions</span></span>  
 <span data-ttu-id="7b9be-116">Zum Anzeigen des Aktivitätsmonitors muss ein Benutzer über die VIEW SERVER STATE-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-116">To view the Activity Monitor, a user must have VIEW SERVER STATE permission.</span></span> <span data-ttu-id="7b9be-117">Sie müssen zum Anzeigen des Abschnitts "Datendatei-E/A" des Aktivitätsmonitors neben VIEW SERVER STATE über die CREATE DATABASE-, ALTER ANY DATABASE- oder VIEW ANY DEFINITION-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-117">To view the Data File I/O section of Activity Monitor, you must have CREATE DATABASE, ALTER ANY DATABASE, or VIEW ANY DEFINITION permission in addition to VIEW SERVER STATE.</span></span>  
  
 <span data-ttu-id="7b9be-118">Zum Ausführen von KILL für einen Prozess muss ein Benutzer Mitglied der festen Serverrolle sysadmin oder processadmin sein.</span><span class="sxs-lookup"><span data-stu-id="7b9be-118">To KILL a process, a user must be a member of the sysadmin or processadmin fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7b9be-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b9be-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-open-activity-monitor-in-sql-server-management-studio"></a><span data-ttu-id="7b9be-120">So öffnen Sie den Aktivitätsmonitor in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b9be-120">To open Activity Monitor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="7b9be-121">Klicken Sie auf der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Standardsymbolleiste auf **Aktivitätsmonitor**.</span><span class="sxs-lookup"><span data-stu-id="7b9be-121">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] standard toolbar, click **Activity Monitor**.</span></span>  
  
2.  <span data-ttu-id="7b9be-122">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** den Servernamen und den Authentifizierungsmodus aus, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="7b9be-122">In the **Connect to Server** dialog box, select the server name and authentication mode, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="7b9be-123">Sie können den Aktivitätsmonitor außerdem jederzeit öffnen, indem Sie STRG+ALT+A drücken.</span><span class="sxs-lookup"><span data-stu-id="7b9be-123">You can also open Activity Monitor at any time by pressing CTRL+ALT A.</span></span>  
  
#### <a name="to-open-activity-monitor-in-object-explorer"></a><span data-ttu-id="7b9be-124">So öffnen Sie den Aktivitätsmonitor im Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="7b9be-124">To open Activity Monitor in Object Explorer</span></span>  
  
-   <span data-ttu-id="7b9be-125">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Instanznamen, und wählen Sie dann den **Aktivitätsmonitor**aus.</span><span class="sxs-lookup"><span data-stu-id="7b9be-125">In Object Explorer, right-click the instance name, and then select **Activity Monitor**.</span></span>  
  
#### <a name="to-open-activity-monitor-when-opening-sql-server-management-studio"></a><span data-ttu-id="7b9be-126">So öffnen Sie den Aktivitätsmonitor beim Öffnen des SQL Server Management Studios</span><span class="sxs-lookup"><span data-stu-id="7b9be-126">To open Activity Monitor when opening SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="7b9be-127">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="7b9be-127">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="7b9be-128">Erweitern Sie im Dialogfeld **Optionen** die Option **Umgebung**, und wählen Sie dann **Allgemein**aus.</span><span class="sxs-lookup"><span data-stu-id="7b9be-128">In the **Options** dialog box, expand **Environment**, and then select **General**.</span></span>  
  
3.  <span data-ttu-id="7b9be-129">Wählen Sie im Feld **Beim Start** die Option **Objekt-Explorer und Aktivitätsmonitor öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="7b9be-129">In the **At startup** box, select **Open Object Explorer and Activity Monitor**.</span></span>  
  
4.  <span data-ttu-id="7b9be-130">Damit diese Änderungen aktiv werden, müssen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]schließen und erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="7b9be-130">To activate the changes, close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-set-the-activity-monitor-refresh-interval"></a><a name="Refresh"></a><span data-ttu-id="7b9be-131">So legen Sie das Aktualisierungs Intervall für den Aktivitäts Monitor fest</span><span class="sxs-lookup"><span data-stu-id="7b9be-131">To Set the Activity Monitor Refresh Interval</span></span>  
  
-   <span data-ttu-id="7b9be-132">Öffnen Sie Aktivitätsmonitor.</span><span class="sxs-lookup"><span data-stu-id="7b9be-132">Open the Activity Monitor.</span></span>  
  
-   <span data-ttu-id="7b9be-133">Klicken Sie mit der rechten Maustaste auf **Übersicht**, wählen Sie **Aktualisierungsintervall**aus, und wählen Sie anschließend das Intervall aus, in dem der Aktivitätsmonitor neue Instanzinformationen abrufen soll.</span><span class="sxs-lookup"><span data-stu-id="7b9be-133">Right-click **Overview**, select **Refresh Interval**, and then select the interval in which Activity Monitor should obtain new instance information.</span></span>  
  
  
