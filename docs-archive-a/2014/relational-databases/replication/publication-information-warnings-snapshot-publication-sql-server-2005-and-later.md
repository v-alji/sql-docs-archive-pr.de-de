---
title: Veröffentlichungsinformationen, Warnungen (Momentaufnahme Veröffentlichung, SQL Server 2005 und höher) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717905"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="15dc4-102">Veröffentlichungsinformationen, Warnungen (Momentaufnahmeveröffentlichung, SQL Server 2005 und höher)</span><span class="sxs-lookup"><span data-stu-id="15dc4-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="15dc4-103">Die Registerkarte **Warnungen** ist für Verteiler verfügbar, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höhere Versionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="15dc4-104">Auf der Registerkarte **Warnungen** können Sie folgende Tasks für die ausgewählte Veröffentlichung ausführen:</span><span class="sxs-lookup"><span data-stu-id="15dc4-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="15dc4-105">Aktivieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="15dc4-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="15dc4-106">Angeben von Schwellenwerten, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="15dc4-107">Festlegen von Hinweisen, die den Warnungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="15dc4-108">Warnungen, Schwellenwerte und Warnhinweise</span><span class="sxs-lookup"><span data-stu-id="15dc4-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="15dc4-109">Standardmäßig werden vom Replikationsmonitor Warnungen zu nicht initialisierten Abonnements angezeigt: auf den Seiten mit den Abonnementinformationen wird in der Spalte **Status** - der Status **Nicht initialisiertes Abonnement** als Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15dc4-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="15dc4-110">Für Momentaufnahmeveröffentlichungen können Sie auch angeben, dass ein bevorstehender Abonnementablauf zu einer Warnung führt. Legen Sie hierzu die Option **Warnung, wenn ein Abonnement innerhalb des Schwellenwerts abläuft**fest.</span><span class="sxs-lookup"><span data-stu-id="15dc4-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="15dc4-111">Wenn der angegebene Schwellenwert erreicht oder überschritten wird, wird als Abonnementstatus **Läuft demnächst ab/Abgelaufen** angezeigt (wenn kein Problem mit einer höheren Priorität angezeigt werden muss).</span><span class="sxs-lookup"><span data-stu-id="15dc4-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="15dc4-112">Neben der Warnung im Replikationsmonitor kann bei Erreichen eines Schwellenwerts auch ein Warnhinweis ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="15dc4-113">Zum Definieren eines Warnhinweises klicken Sie auf **Warnungen konfigurieren** , und stellen Sie im Dialogfeld **Replikationswarnungen konfigurieren** die entsprechenden Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="15dc4-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15dc4-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="15dc4-114">Options</span></span>  
 <span data-ttu-id="15dc4-115">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="15dc4-115">**Enabled**</span></span>  
 <span data-ttu-id="15dc4-116">Wählen Sie diese Option aus, um eine Warnung zu aktivieren und einen Schwellenwert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="15dc4-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="15dc4-117">**Warning**</span><span class="sxs-lookup"><span data-stu-id="15dc4-117">**Warning**</span></span>  
 <span data-ttu-id="15dc4-118">Eine Beschreibung der Warnung, die einem Schwellenwert zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="15dc4-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="15dc4-119">**Schwellenwert**</span><span class="sxs-lookup"><span data-stu-id="15dc4-119">**Threshold**</span></span>  
 <span data-ttu-id="15dc4-120">Geben Sie einen Wert für den Schwellenwert an.</span><span class="sxs-lookup"><span data-stu-id="15dc4-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="15dc4-121">**Konfigurieren von Warnungen**</span><span class="sxs-lookup"><span data-stu-id="15dc4-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="15dc4-122">Wählen Sie im Raster **Warnungen** die gewünschte Zeile aus, und klicken Sie auf **Warnungen konfigurieren** , um das Dialogfeld **Replikationswarnungen konfigurieren** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="15dc4-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="15dc4-123">In dem Dialogfeld können Sie einen Warnhinweis definieren, der dem ausgewählten Schwellenwert und der Warnung zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="15dc4-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="15dc4-124">**Änderungen verwerfen**</span><span class="sxs-lookup"><span data-stu-id="15dc4-124">**Discard Changes**</span></span>  
 <span data-ttu-id="15dc4-125">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="15dc4-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15dc4-126">Die Schaltfläche **Änderungen verwerfen** hat keine Auswirkungen auf die im Dialogfeld **Replikationswarnungen konfigurieren** definierten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="15dc4-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="15dc4-127">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="15dc4-127">**Save Changes**</span></span>  
 <span data-ttu-id="15dc4-128">Klicken Sie hier, um die Änderungen an Warnungen und Schwellenwerten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="15dc4-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15dc4-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15dc4-129">See Also</span></span>  
 <span data-ttu-id="15dc4-130">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="15dc4-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="15dc4-131">[View information and perform tasks using Replication Monitor (Anzeigen von Informationen und Ausführen von Aufgaben mit dem Replikationsmonitor)](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="15dc4-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="15dc4-132">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="15dc4-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
