---
title: Aktualisieren des Auftragsaktivitätsmonitors | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617976"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="920e6-102">Aktualisieren des Auftragsaktivitätsmonitors</span><span class="sxs-lookup"><span data-stu-id="920e6-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="920e6-103">Mithilfe des Dialogfelds **Aktualisierungseinstellungen** können Sie konfigurieren, wie oft durch den Auftragsaktivitätsmonitor neue Informationen zur Serveraktivität abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="920e6-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="920e6-104">Der Auftragsaktivitätsmonitor muss Abfragen an die überwachten Server ausführen, um Informationen für das Raster des Auftragsaktivitätsmonitors zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="920e6-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="920e6-105">Wenn für das Intervall für die automatische Aktualisierung weniger als 30 Sekunden festgelegt ist, kann die für die Ausführung der Abfragen benötigte Zeit die Serverleistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="920e6-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="920e6-106">Zum Öffnen dieses Dialogfelds klicken Sie im Abschnitt **Status**des Auftragsaktivitätsmonitors auf **Aktualisierungseinstellungen anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="920e6-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="920e6-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="920e6-107">Options</span></span>  
 <span data-ttu-id="920e6-108">**Automatische Aktualisierung alle**</span><span class="sxs-lookup"><span data-stu-id="920e6-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="920e6-109">Wählen Sie diese Option, um die automatische Aktualisierung der Aktivitätsmonitorinformationen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="920e6-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="920e6-110">Standardmäßig ist die automatische Aktualisierung ausgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="920e6-110">This is off by default.</span></span>  
  
 <span data-ttu-id="920e6-111">**Sekunden**</span><span class="sxs-lookup"><span data-stu-id="920e6-111">**seconds**</span></span>  
 <span data-ttu-id="920e6-112">Anzahl der Sekunden zwischen den automatischen Aktualisierungsversuchen.</span><span class="sxs-lookup"><span data-stu-id="920e6-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="920e6-113">Der Standardwert ist 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="920e6-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="920e6-114">Wenn der Wert auf 5 oder weniger festgelegt ist, erfolgt die Aktualisierung alle 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="920e6-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920e6-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="920e6-115">See Also</span></span>  
 [<span data-ttu-id="920e6-116">Überwachen der Auftragsaktivität</span><span class="sxs-lookup"><span data-stu-id="920e6-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
