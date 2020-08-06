---
title: Veröffentlichungsinformationen, Warnungen (Mergeveröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.merge.f1
ms.assetid: 9bef3565-5f13-42ac-8723-ebe55b0c11e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75f58a4cd9bd84791acf7fd9d28147ef3bbd6232
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618655"
---
# <a name="publication-information-warnings-merge-publication-sql-server-2005-and-later"></a><span data-ttu-id="8a438-102">Veröffentlichungsinformationen, Warnungen (Mergeveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="8a438-102">Publication Information, Warnings (Merge Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="8a438-103"> Die Registerkarte **Warnungen** ist für Verteiler verfügbar, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8a438-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="8a438-104">Auf der Registerkarte **Warnungen** können Sie folgende Tasks für die ausgewählte Veröffentlichung ausführen:</span><span class="sxs-lookup"><span data-stu-id="8a438-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="8a438-105">Aktivieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="8a438-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="8a438-106">Angeben von Schwellenwerten, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8a438-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="8a438-107">Festlegen von Hinweisen, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8a438-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="8a438-108">Warnungen, Schwellenwerte und Warnhinweise</span><span class="sxs-lookup"><span data-stu-id="8a438-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="8a438-109">Standardmäßig werden vom Replikationsmonitor Warnungen zu nicht initialisierten Abonnements angezeigt: auf den Seiten mit den Abonnementinformationen wird in der Spalte **Status** - der Status **Nicht initialisiertes Abonnement** als Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a438-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="8a438-110">Sie können angeben, ob durch folgende weitere Bedingungen bei Mergeveröffentlichungen eine Warnung ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="8a438-110">For merge publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="8a438-111">Bevorstehender Abonnementablauf.</span><span class="sxs-lookup"><span data-stu-id="8a438-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="8a438-112">Diese Bedingung entspricht der Option **Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft**.</span><span class="sxs-lookup"><span data-stu-id="8a438-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="8a438-113">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Läuft demnächst ab/Abgelaufen** angezeigt (wenn kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="8a438-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="8a438-114">Die angegebene Synchronisierungszeit wird überschritten.</span><span class="sxs-lookup"><span data-stu-id="8a438-114">Exceeding the specified synchronization time.</span></span>  
  
     <span data-ttu-id="8a438-115">Diese Bedingung entspricht den Optionen **Warnung, wenn eine Zusammenführungslänge für DFÜ-Verbindungen den Schwellenwert überschreitet** und **Warnung, wenn eine Zusammenführungslänge für LAN-Verbindungen den Schwellenwert überschreitet**.</span><span class="sxs-lookup"><span data-stu-id="8a438-115">This corresponds to the options **Warn if a merge length for dialup connections exceeds the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="8a438-116">Beide Schwellenwerte können festgelegt werden, aber nur ein Wert wird während einer Synchronisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a438-116">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="8a438-117">Der Merge-Agent wendet auf der Grundlage des Verbindungstyps den entsprechenden Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="8a438-117">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="8a438-118">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Langer Mergevorgang** angezeigt (falls kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="8a438-118">If the specified threshold is met or exceeded, the subscription status is displayed as **Long-running merge** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="8a438-119">Die angegebene Zahl von Zeilen konnte nicht innerhalb der festgelegten Zeit verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8a438-119">Falling short of processing the specified number of rows in a given amount of time.</span></span>  
  
     <span data-ttu-id="8a438-120">Diese Bedingung entspricht den Optionen **Warnung, wenn der Wert für zusammengeführte Zeilen pro Sekunde für DFÜ-Verbindungen kleiner als der Schwellenwert ist** und **Warnung, wenn eine Zusammenführungslänge für LAN-Verbindungen den Schwellenwert überschreitet**.</span><span class="sxs-lookup"><span data-stu-id="8a438-120">This corresponds to the options **Warn if rows merged per second for dialup connections is less than the threshold** and **Warn if a merge length for LAN connections exceeds the threshold**.</span></span> <span data-ttu-id="8a438-121">Beide Schwellenwerte können festgelegt werden, aber nur ein Wert wird während einer Synchronisierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a438-121">Both of these thresholds can be set, but only one is used during a given synchronization.</span></span> <span data-ttu-id="8a438-122">Der Merge-Agent wendet auf der Grundlage des Verbindungstyps den entsprechenden Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="8a438-122">The Merge Agent applies the appropriate threshold based on the connection type.</span></span>  
  
     <span data-ttu-id="8a438-123">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Leistungskritisch** angezeigt (falls kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="8a438-123">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="8a438-124">Wenn Sie eine Warnung aktivieren, müssen Sie auch einen Schwellenwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="8a438-124">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="8a438-125">Wenn Sie z. B. die Warnung **Warnung, wenn eine Zusammenführungslänge für LAN-Verbindungen den Schwellenwert überschreitet**aktivieren, legen Sie die maximal zulässige Zeit für eine Mergesynchronisierung fest.</span><span class="sxs-lookup"><span data-stu-id="8a438-125">For example, if you enable the warning **Warn if a merge length for LAN connections exceeds the threshold**, set the maximum allowable length of time for a merge synchronization.</span></span>  
  
 <span data-ttu-id="8a438-126">Neben der Warnung im Replikationsmonitor kann bei Erreichen eines Schwellenwerts auch ein Warnhinweis ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="8a438-126">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="8a438-127">Zum Definieren eines Warnhinweises klicken Sie auf **Warnungen konfigurieren** , und stellen Sie im Dialogfeld **Replikationswarnungen konfigurieren** die entsprechenden Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="8a438-127">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8a438-128">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8a438-128">Options</span></span>  
 <span data-ttu-id="8a438-129">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="8a438-129">**Enabled**</span></span>  
 <span data-ttu-id="8a438-130">Wählen Sie diese Option aus, um eine Warnung zu aktivieren und einen Schwellenwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8a438-130">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="8a438-131">**Warnung**</span><span class="sxs-lookup"><span data-stu-id="8a438-131">**Alert**</span></span>  
 <span data-ttu-id="8a438-132">Wählen Sie diese Option aus, um die Warnungseinstellung für eine angegebene Replikationswarnung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a438-132">Select to enable the alert setting for a given replication warning.</span></span>  
  
 <span data-ttu-id="8a438-133">**Warnung**</span><span class="sxs-lookup"><span data-stu-id="8a438-133">**Warning**</span></span>  
 <span data-ttu-id="8a438-134">Eine Beschreibung der Warnung, die einem Schwellenwert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8a438-134">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="8a438-135">**Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="8a438-135">**Threshold**</span></span>  
 <span data-ttu-id="8a438-136">Geben Sie einen Wert für den Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="8a438-136">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="8a438-137">**Konfigurieren von Warnungen**</span><span class="sxs-lookup"><span data-stu-id="8a438-137">**Configure Alerts**</span></span>  
 <span data-ttu-id="8a438-138">Wählen Sie im Raster **Warnungen** die gewünschte Zeile aus, und klicken Sie auf **Warnungen konfigurieren** , um das Dialogfeld **Replikationswarnungen konfigurieren** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8a438-138">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="8a438-139">In dem Dialogfeld können Sie einen Warnhinweis definieren, der dem ausgewählten Schwellenwert und der Warnung zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="8a438-139">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="8a438-140">**Änderungen verwerfen**</span><span class="sxs-lookup"><span data-stu-id="8a438-140">**Discard Changes**</span></span>  
 <span data-ttu-id="8a438-141">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8a438-141">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a438-142">Die Schaltfläche **Änderungen verwerfen** hat keine Auswirkungen auf die im Dialogfeld **Replikationswarnungen konfigurieren** definierten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="8a438-142">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="8a438-143">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="8a438-143">**Save Changes**</span></span>  
 <span data-ttu-id="8a438-144">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8a438-144">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a438-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a438-145">See Also</span></span>  
 <span data-ttu-id="8a438-146">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8a438-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="8a438-147">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8a438-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="8a438-148">[Leistungsüberwachung mit dem Replikations Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="8a438-148">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="8a438-149">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="8a438-149">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="8a438-150">Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="8a438-150">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
