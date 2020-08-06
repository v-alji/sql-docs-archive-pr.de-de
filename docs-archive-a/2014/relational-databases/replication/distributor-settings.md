---
title: Dialogfeld "Verteiler Einstellungen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609118"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="ec737-102">Dialogfeld "Verteiler Einstellungen" SQL Server-Replikation</span><span class="sxs-lookup"><span data-stu-id="ec737-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="ec737-103">Im Dialogfeld **Verteilereinstellungen** können Sie die Einstellungen für Verteiler ändern, die dem linken Bereich des Replikationsmonitors hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ec737-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ec737-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ec737-104">Options</span></span>  
 <span data-ttu-id="ec737-105">**Beim Starten des Replikationsmonitors automatisch Verbindung herstellen**</span><span class="sxs-lookup"><span data-stu-id="ec737-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="ec737-106">Wählen Sie diese Option aus, damit der Replikationsmonitor eine Verbindung mit dem Verteiler herstellen und Statusinformationen abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="ec737-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="ec737-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="ec737-107">**Connection**</span></span>  
 <span data-ttu-id="ec737-108">Klicken Sie hier, um das Dialogfeld **Verbindung mit Server herstellen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec737-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="ec737-109">In diesem Dialogfeld können Sie die Verbindungseigenschaften und die Anmeldeinformationen anzeigen, die vom Replikationsmonitor zum Herstellen einer Verbindung mit dem Verteiler verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec737-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="ec737-110">**Status dieses Verteilers und seiner Veröffentlichungen automatisch aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="ec737-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="ec737-111">Wählen Sie diese Option aus, damit der Replikationsmonitor automatisch den Status für den Verteiler aktualisieren kann.</span><span class="sxs-lookup"><span data-stu-id="ec737-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="ec737-112">Wenn diese Option ausgewählt ist, ruft der Replikationsmonitor die Statusinformationen für den Verteiler anhand des Abrufintervalls ab, das mit der Option **Aktualisierungsrate** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec737-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="ec737-113">Weitere Informationen zum Aktualisieren im Replikationsmonitor finden Sie unter [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="ec737-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="ec737-114">**Aktualisierungsrate**</span><span class="sxs-lookup"><span data-stu-id="ec737-114">**Refresh rate**</span></span>  
 <span data-ttu-id="ec737-115">Geben Sie einen Wert (in Sekunden) ein, um anzugeben, wie oft der Replikationsmonitor Statusinformationen über den Verteiler abrufen soll.</span><span class="sxs-lookup"><span data-stu-id="ec737-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="ec737-116">Niedrigere Werte bedeuten häufigere Abrufe.</span><span class="sxs-lookup"><span data-stu-id="ec737-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="ec737-117">Dies kann die Leistung des Verteilers beeinträchtigen, wenn Sie viele Verleger überwachen.</span><span class="sxs-lookup"><span data-stu-id="ec737-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="ec737-118">Es wird empfohlen, das eigene System zu testen, um einen angemessenen Wert zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ec737-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="ec737-119">Die Einstellung **Aktualisierungsrate** wird ebenfalls verwendet, wenn Sie in einem der Detailfenster des Replikationsmonitors die Option **Automatisch aktualisieren** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ec737-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="ec737-120">**Alle Verleger dieses Verteilers in folgender Gruppe anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ec737-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="ec737-121">Wählen Sie eine Verlegergruppe aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ec737-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="ec737-122">Der Verleger wird unter dieser Gruppe im linken Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec737-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="ec737-123">Gruppen stellen eine Möglichkeit zum Organisieren von Verlegern dar und haben keinen Einfluss auf die Funktion der Replikation.</span><span class="sxs-lookup"><span data-stu-id="ec737-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="ec737-124">**Neue Gruppe**</span><span class="sxs-lookup"><span data-stu-id="ec737-124">**New Group**</span></span>  
 <span data-ttu-id="ec737-125">Klicken Sie auf diese Option, um eine neue Verlegergruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec737-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="ec737-126">Eine Verlegergruppe stellt eine einfache Möglichkeit dar, um die Verleger innerhalb des Replikationsmonitors zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="ec737-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="ec737-127">Gruppen haben keinen Einfluss auf die Replikation der Daten oder die Beziehungen zwischen den Servern in der Replikationstopologie.</span><span class="sxs-lookup"><span data-stu-id="ec737-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec737-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec737-128">See Also</span></span>  
 <span data-ttu-id="ec737-129">[Starten des Replikationsmonitors](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="ec737-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="ec737-130">Überwachen der Replikation</span><span class="sxs-lookup"><span data-stu-id="ec737-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
