---
title: Veröffentlichungsinformationen, Warnungen (Transaktions Veröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.tran.f1
ms.assetid: 4d4baf1d-d0a1-4d09-bec7-137811f43f09
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac7ab0f712fe69d3736985921d70b0ce200d474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717842"
---
# <a name="publication-information-warnings-transactional-publication-sql-server-2005-and-later"></a><span data-ttu-id="cdc99-102">Veröffentlichungsinformationen, Warnungen (Transaktionsveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="cdc99-102">Publication Information, Warnings (Transactional Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="cdc99-103"> Die Registerkarte **Warnungen** ist für Verteiler verfügbar, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cdc99-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="cdc99-104">Auf der Registerkarte **Warnungen** können Sie folgende Tasks für die ausgewählte Veröffentlichung ausführen:</span><span class="sxs-lookup"><span data-stu-id="cdc99-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="cdc99-105">Aktivieren von Warnungen, die im Replikationsmonitor angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cdc99-105">Enable warnings to be displayed in Replication Monitor.</span></span>  
  
-   <span data-ttu-id="cdc99-106">Angeben von Schwellenwerten, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cdc99-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="cdc99-107">Festlegen von Hinweisen, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cdc99-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="cdc99-108">Warnungen, Schwellenwerte und Warnhinweise</span><span class="sxs-lookup"><span data-stu-id="cdc99-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="cdc99-109">Standardmäßig werden vom Replikationsmonitor Warnungen zu nicht initialisierten Abonnements angezeigt: auf den Seiten mit den Abonnementinformationen wird in der Spalte **Status** - der Status **Nicht initialisiertes Abonnement** als Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cdc99-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="cdc99-110">Sie können angeben, ob durch folgende zusätzlichen Bedingungen bei Transaktionsveröffentlichungen eine Warnung ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="cdc99-110">For transactional publications, you can specify whether these additional conditions result in warnings:</span></span>  
  
-   <span data-ttu-id="cdc99-111">Bevorstehender Abonnementablauf.</span><span class="sxs-lookup"><span data-stu-id="cdc99-111">Imminent subscription expiration.</span></span>  
  
     <span data-ttu-id="cdc99-112">Diese Bedingung entspricht der Option **Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft**.</span><span class="sxs-lookup"><span data-stu-id="cdc99-112">This corresponds to the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="cdc99-113">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Läuft demnächst ab/Abgelaufen** angezeigt (wenn kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="cdc99-113">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
-   <span data-ttu-id="cdc99-114">Überschreiten der angegebenen Latenzzeit.</span><span class="sxs-lookup"><span data-stu-id="cdc99-114">Exceeding the specified latency.</span></span> <span data-ttu-id="cdc99-115">Dabei handelt es sich um die Zeit zwischen dem Ausführen eines Commits für eine Transaktion beim Verleger und der entsprechenden Ausführung des Commits für die Transaktion beim Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="cdc99-115">This is the amount of time that elapses between a transaction being committed at the Publisher and the corresponding transaction being committed at the Subscriber.</span></span>  
  
     <span data-ttu-id="cdc99-116">Diese Bedingung entspricht der Option **Warnung, wenn die Latenzzeit den Schwellenwert überschreitet**.</span><span class="sxs-lookup"><span data-stu-id="cdc99-116">This corresponds to the option **Warn if latency exceeds the threshold**.</span></span> <span data-ttu-id="cdc99-117">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Leistungskritisch** angezeigt (falls kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="cdc99-117">If the specified threshold is met or exceeded, the subscription status is displayed as **Performance critical** (unless an issue with a higher priority needs to be displayed).</span></span> <span data-ttu-id="cdc99-118">Mit den Schwellenwerten wird gleichzeitig eine Leistungsbewertung bereitgestellt, die in der **Leistung** -Spalte auf den Seiten mit den Abonnementinformationen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cdc99-118">The threshold is also used to provide a performance rating, which is displayed in the **Performance** column of pages that include subscription information.</span></span> <span data-ttu-id="cdc99-119">Die folgenden Werte sind für die Leistungsbewertung möglich:</span><span class="sxs-lookup"><span data-stu-id="cdc99-119">The performance rating is one of the following values:</span></span>  
  
    -   <span data-ttu-id="cdc99-120">Ausgezeichnet</span><span class="sxs-lookup"><span data-stu-id="cdc99-120">Excellent</span></span>  
  
    -   <span data-ttu-id="cdc99-121">Gut</span><span class="sxs-lookup"><span data-stu-id="cdc99-121">Good</span></span>  
  
    -   <span data-ttu-id="cdc99-122">Mittelmäßig</span><span class="sxs-lookup"><span data-stu-id="cdc99-122">Fair</span></span>  
  
    -   <span data-ttu-id="cdc99-123">Schlecht</span><span class="sxs-lookup"><span data-stu-id="cdc99-123">Poor</span></span>  
  
    -   <span data-ttu-id="cdc99-124">Kritisch</span><span class="sxs-lookup"><span data-stu-id="cdc99-124">Critical</span></span>  
  
 <span data-ttu-id="cdc99-125">Wenn Sie eine Warnung aktivieren, müssen Sie auch einen Schwellenwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="cdc99-125">When you enable a warning, you also set a threshold.</span></span> <span data-ttu-id="cdc99-126">Wenn Sie z. B. die Warnung **Warnung, wenn die Latenzzeit den Schwellenwert überschreitet**aktivieren, müssen Sie die Zeitspanne auswählen, die zwischen dem Ausführen eines Commits für eine Transaktion beim Verleger und der entsprechenden Ausführung des Commits für die Transaktion beim Abonnenten liegt.</span><span class="sxs-lookup"><span data-stu-id="cdc99-126">For example, if you enable the warning **Warn if latency exceeds the threshold**, select the amount of time allowable between a transaction being committed at the Publisher and the transaction being committed at the Subscriber.</span></span>  
  
 <span data-ttu-id="cdc99-127">Neben der Warnung im Replikationsmonitor kann bei Erreichen eines Schwellenwerts auch ein Warnhinweis ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="cdc99-127">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="cdc99-128">Zum Definieren eines Warnhinweises klicken Sie auf **Warnungen konfigurieren** , und stellen Sie im Dialogfeld **Replikationswarnungen konfigurieren** die entsprechenden Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="cdc99-128">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cdc99-129">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cdc99-129">Options</span></span>  
 <span data-ttu-id="cdc99-130">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="cdc99-130">**Enabled**</span></span>  
 <span data-ttu-id="cdc99-131">Wählen Sie diese Option aus, um eine Warnung zu aktivieren und einen Schwellenwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cdc99-131">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="cdc99-132">**Warnung**</span><span class="sxs-lookup"><span data-stu-id="cdc99-132">**Warning**</span></span>  
 <span data-ttu-id="cdc99-133">Eine Beschreibung der Warnung, die einem Schwellenwert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cdc99-133">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="cdc99-134">**Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="cdc99-134">**Threshold**</span></span>  
 <span data-ttu-id="cdc99-135">Geben Sie einen Wert für den Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="cdc99-135">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="cdc99-136">**Konfigurieren von Warnungen**</span><span class="sxs-lookup"><span data-stu-id="cdc99-136">**Configure Alerts**</span></span>  
 <span data-ttu-id="cdc99-137">Wählen Sie im Raster **Warnungen** die gewünschte Zeile aus, und klicken Sie auf **Warnungen konfigurieren** , um das Dialogfeld **Replikationswarnungen konfigurieren** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cdc99-137">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="cdc99-138">In dem Dialogfeld können Sie einen Warnhinweis definieren, der dem ausgewählten Schwellenwert und der Warnung zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="cdc99-138">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="cdc99-139">**Änderungen verwerfen**</span><span class="sxs-lookup"><span data-stu-id="cdc99-139">**Discard Changes**</span></span>  
 <span data-ttu-id="cdc99-140">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="cdc99-140">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cdc99-141">Die Schaltfläche **Änderungen verwerfen** hat keine Auswirkungen auf die im Dialogfeld **Replikationswarnungen konfigurieren** definierten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="cdc99-141">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="cdc99-142">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="cdc99-142">**Save Changes**</span></span>  
 <span data-ttu-id="cdc99-143">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cdc99-143">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc99-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cdc99-144">See Also</span></span>  
 <span data-ttu-id="cdc99-145">[Starten des Replikations Monitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cdc99-145">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="cdc99-146">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cdc99-146">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 <span data-ttu-id="cdc99-147">[Leistungsüberwachung mit dem Replikations Monitor](monitor/monitor-performance-with-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="cdc99-147">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) </span></span>  
 <span data-ttu-id="cdc99-148">[Überwachen der Replikation](monitoring-replication.md) </span><span class="sxs-lookup"><span data-stu-id="cdc99-148">[Monitoring Replication](monitoring-replication.md) </span></span>  
 [<span data-ttu-id="cdc99-149">Festlegen von Schwellenwerten und Warnungen im Replikationsmonitor</span><span class="sxs-lookup"><span data-stu-id="cdc99-149">Set Thresholds and Warnings in Replication Monitor</span></span>](monitor/set-thresholds-and-warnings-in-replication-monitor.md)  
  
  
