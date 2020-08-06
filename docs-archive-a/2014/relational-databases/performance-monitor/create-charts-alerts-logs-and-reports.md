---
title: Erstellen von Diagrammen, Warnungen, Protokollen und Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], charts and reports
- charts [SQL Server]
- reports [SQL Server]
- reports [SQL Server], creating
- Windows System Monitor [SQL Server], charts and reports
- logs [SQL Server], System Monitor
- System Monitor [SQL Server], logs
- Windows System Monitor [SQL Server], logs
ms.assetid: c9162b37-e5dc-43d1-a3aa-1e9ebc69fecc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a0c95c3f483a8af3e3e68d9c5c7d3caf44350d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723730"
---
# <a name="create-charts-alerts-logs-and-reports"></a><span data-ttu-id="9adc6-102">Erstellen von Diagrammen, Warnungen, Protokollen und Berichten</span><span class="sxs-lookup"><span data-stu-id="9adc6-102">Create Charts, Alerts, Logs, and Reports</span></span>
  <span data-ttu-id="9adc6-103">Der Systemmonitor ermöglicht Ihnen das Erstellen von Diagrammen, Warnungen, Protokollen und Berichten für die Überwachung einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9adc6-103">System Monitor lets you create charts, alerts, logs, and reports to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="charts"></a><span data-ttu-id="9adc6-104">Diagramme</span><span class="sxs-lookup"><span data-stu-id="9adc6-104">Charts</span></span>  
 <span data-ttu-id="9adc6-105">Mit Diagrammen lässt sich die aktuelle Leistung ausgewählter Objekte und Leistungsindikatoren überwachen, wie z. B. CPU-Nutzung oder Datenträger-E/A.</span><span class="sxs-lookup"><span data-stu-id="9adc6-105">Charts can monitor the current performance of selected objects and counters; for example, the CPU usage or disk I/O.</span></span> <span data-ttu-id="9adc6-106">Sie können verschiedene Kombinationen von Systemmonitorobjekten und -Leistungsindikatoren zu einem Diagramm hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-106">You can add to a chart various combinations of System Monitor objects and counters.</span></span> <span data-ttu-id="9adc6-107">Darüber hinaus können Sie einem Diagramm [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Objekte und -Leistungsindikatoren hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-107">You also can add [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows objects and counters to a chart.</span></span>  
  
 <span data-ttu-id="9adc6-108">Jedes Diagramm stellt eine Teilmenge der Informationen dar, die Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="9adc6-108">Each chart represents a subset of information you want to monitor.</span></span> <span data-ttu-id="9adc6-109">So kann ein Diagramm beispielsweise die Statistiken über die Speicherauslastung und ein zweites Diagramm die Statistiken über die Datenträger-E/A nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-109">For example, one chart can track memory usage statistics and a second chart can track disk I/O statistics.</span></span>  
  
 <span data-ttu-id="9adc6-110">Die Verwendung eines Diagramms kann sich für die folgenden Aufgaben als nützlich erweisen:</span><span class="sxs-lookup"><span data-stu-id="9adc6-110">Using a chart can be useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="9adc6-111">Überprüfen, weshalb ein Computer oder eine Anwendung langsam oder ineffizient ist</span><span class="sxs-lookup"><span data-stu-id="9adc6-111">Investigating why a computer or application is slow or inefficient.</span></span>  
  
-   <span data-ttu-id="9adc6-112">Kontinuierliches Überwachen der Systeme, um Leistungsprobleme, die stoßweise auftreten, zu erkennen</span><span class="sxs-lookup"><span data-stu-id="9adc6-112">Continually monitoring systems to find intermittent performance problems.</span></span>  
  
-   <span data-ttu-id="9adc6-113">Feststellen, weshalb die Kapazität erhöht werden muss</span><span class="sxs-lookup"><span data-stu-id="9adc6-113">Discovering why you need to increase capacity.</span></span>  
  
-   <span data-ttu-id="9adc6-114">Anzeigen einer Tendenz in einem Liniendiagramm</span><span class="sxs-lookup"><span data-stu-id="9adc6-114">Displaying a trend as a line chart.</span></span>  
  
-   <span data-ttu-id="9adc6-115">Anzeigen eines Vergleichs in einem Histogramm</span><span class="sxs-lookup"><span data-stu-id="9adc6-115">Displaying a comparison as a histogram chart.</span></span>  
  
 <span data-ttu-id="9adc6-116">Diagramme sind für das kurzfristige Überwachen in Echtzeit von lokalen Computern oder Remotecomputern nützlich, z. B. wenn Sie ein Ereignis überwachen möchten, während es eintritt.</span><span class="sxs-lookup"><span data-stu-id="9adc6-116">Charts are useful for short-term, real-time monitoring of a local or remote computer (for example, when you want to monitor an event as it occurs).</span></span>  
  
## <a name="alerts"></a><span data-ttu-id="9adc6-117">Alerts</span><span class="sxs-lookup"><span data-stu-id="9adc6-117">Alerts</span></span>  
 <span data-ttu-id="9adc6-118">Mithilfe von Warnungen kann der Systemmonitor bestimmte Ereignisse nachverfolgen und Sie ggf. von diesen Ereignissen in Kenntnis setzen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-118">Using alerts, System Monitor tracks specific events and notifies you of these events as requested.</span></span> <span data-ttu-id="9adc6-119">Ein Warnungsprotokoll kann die aktuelle Leistung ausgewählter Leistungsindikatoren und Instanzen für Objekte in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]überwachen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-119">An alert log can monitor the current performance of selected counters and instances for objects in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9adc6-120">Wenn ein Leistungsindikator einen bestimmten Wert überschreitet, zeichnet das Protokoll das Datum und den Zeitpunkt des Ereignisses auf.</span><span class="sxs-lookup"><span data-stu-id="9adc6-120">When a counter exceeds a given value, the log records the date and time of the event.</span></span> <span data-ttu-id="9adc6-121">Ein Ereignis kann auch eine Netzwerkwarnung generieren.</span><span class="sxs-lookup"><span data-stu-id="9adc6-121">An event can also generate a network alert.</span></span> <span data-ttu-id="9adc6-122">Sie können ein angegebenes Programm ausführen lassen, wenn ein Ereignis zum ersten Mal eintritt, oder jedes Mal, wenn das Ereignis eintritt.</span><span class="sxs-lookup"><span data-stu-id="9adc6-122">You can have a specified program run the first time or every time an event occurs.</span></span> <span data-ttu-id="9adc6-123">So kann eine Warnung beispielsweise eine Netzwerknachricht an alle Systemadministratoren senden, dass die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nur noch wenig Speicherplatz aufweist.</span><span class="sxs-lookup"><span data-stu-id="9adc6-123">For example, an alert can send a network message to all system administrators that the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is getting low on disk space.</span></span>  
  
## <a name="logs"></a><span data-ttu-id="9adc6-124">Protokolle</span><span class="sxs-lookup"><span data-stu-id="9adc6-124">Logs</span></span>  
 <span data-ttu-id="9adc6-125">Protokolle ermöglichen es Ihnen, Informationen über die aktuelle Aktivität ausgewählter Objekte und Computer aufzuzeichnen, um sie später anzuzeigen oder zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="9adc6-125">Logs allow you to record information on the current activity of selected objects and computers for later viewing and analysis.</span></span> <span data-ttu-id="9adc6-126">Sie können Daten von mehreren Systemen in einer einzelnen Protokolldatei auflisten.</span><span class="sxs-lookup"><span data-stu-id="9adc6-126">You can collect data from multiple systems into a single log file.</span></span> <span data-ttu-id="9adc6-127">So können Sie beispielsweise verschiedene Protokolle erstellen, um Informationen zur Leistung ausgewählter Objekte auf verschiedenen Computern aufzulisten, und sie später auswerten.</span><span class="sxs-lookup"><span data-stu-id="9adc6-127">For example, you can create different logs to accumulate information about the performance of selected objects on various computers for future analysis.</span></span> <span data-ttu-id="9adc6-128">Sie können diese Auswahlen unter einem Dateinamen speichern und wiederverwenden, wenn Sie zu Vergleichszwecken ein anderes Protokoll mit ähnlichen Informationen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9adc6-128">You can save these selections under a file name and reuse them when you want to create another log of similar information for comparison.</span></span>  
  
 <span data-ttu-id="9adc6-129">Protokolldateien enthalten umfangreiche Informationen für die Problembehandlung oder Planung.</span><span class="sxs-lookup"><span data-stu-id="9adc6-129">Log files provide a wealth of information for troubleshooting or planning.</span></span> <span data-ttu-id="9adc6-130">Während Diagramme, Warnungen und Berichte Informationen über die aktuelle Aktivität bereitstellen, können Sie mit Protokolldateien Leistungsindikatoren über eine längere Zeitspanne nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-130">Whereas charts, alerts, and reports on current activity provide instant feedback, log files enable you to track counters over a long period of time.</span></span> <span data-ttu-id="9adc6-131">Auf diese Weise können Sie die Informationen gründlich analysieren und die Systemleistung längerfristig dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="9adc6-131">Thus, you can examine information more thoroughly and document system performance.</span></span>  
  
## <a name="reports"></a><span data-ttu-id="9adc6-132">Berichte</span><span class="sxs-lookup"><span data-stu-id="9adc6-132">Reports</span></span>  
 <span data-ttu-id="9adc6-133">Berichte ermöglichen es Ihnen, Werte für Leistungsindikatoren und Instanzen, die sich ständig ändern, für ausgewählte Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9adc6-133">Reports allow you to display constantly changing counter and instance values for selected objects.</span></span> <span data-ttu-id="9adc6-134">Werte werden in Spalten für jede Instanz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9adc6-134">Values appear in columns for each instance.</span></span> <span data-ttu-id="9adc6-135">Sie können die Intervalle für Berichte anpassen, Momentaufnahmen drucken und Daten exportieren.</span><span class="sxs-lookup"><span data-stu-id="9adc6-135">You can adjust report intervals, print snapshots, and export data.</span></span> <span data-ttu-id="9adc6-136">Wenn Sie die reinen Zahlen anzeigen möchten, eignen sich Berichte am besten.</span><span class="sxs-lookup"><span data-stu-id="9adc6-136">Use reports when you need to display the raw numbers.</span></span>  
  
 <span data-ttu-id="9adc6-137">Weitere Informationen zum Erstellen von Diagrammen, Warnungen, Protokollen und Berichten sowie zu Windows-Objekten und -Leistungsindikatoren finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="9adc6-137">For more information about creating charts, alerts, logs, and reports, or about Windows objects and counters, see the Windows documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9adc6-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9adc6-138">See Also</span></span>  
 [<span data-ttu-id="9adc6-139">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="9adc6-139">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
