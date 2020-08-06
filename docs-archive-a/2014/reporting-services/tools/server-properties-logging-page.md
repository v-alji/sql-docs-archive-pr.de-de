---
title: Servereigenschaften (Seite „Verlauf“)|Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.logging.f1
ms.assetid: b338deab-4868-4951-9f22-0605add2fc95
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a04c27fd790a1ad5c4ba453b43af5983a6440e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619012"
---
# <a name="server-properties-logging-page"></a><span data-ttu-id="e0eda-102">Servereigenschaften (Seite Protokollierung)</span><span class="sxs-lookup"><span data-stu-id="e0eda-102">Server Properties (Logging Page)</span></span>
  <span data-ttu-id="e0eda-103">Verwenden Sie diese Seite, um Grenzwerte für die Berichtsausführungsdaten festzulegen, die von einem Berichtsserver aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="e0eda-103">Use this page to set limits on the report execution data that is collected by a report server.</span></span> <span data-ttu-id="e0eda-104">Die Ausführungsdaten werden intern in der Berichtsserverdatenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e0eda-104">Execution data is stored internally in the report server database.</span></span> <span data-ttu-id="e0eda-105">Sie können die Berichtsaktivität eines Berichtsservers, der im einheitlichen Modus oder im integrierten SharePoint-Modus ausgeführt wird, nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="e0eda-105">You can track report activity for report server that runs in native mode or SharePoint integrated mode.</span></span> <span data-ttu-id="e0eda-106">Ist der Berichtsserver Teil einer Bereitstellung für horizontales Skalieren, zeichnet das Berichtsausführungsprotokoll die Berichtsaktivität der gesamten Bereitstellung in einer einzelnen Protokolldatei auf.</span><span class="sxs-lookup"><span data-stu-id="e0eda-106">If the report server is part of a scale-out deployment, the report execution log maintains a record of all report activity for the entire deployment in a single log file.</span></span>  
  
 <span data-ttu-id="e0eda-107">Um diese Seite zu öffnen, starten [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Sie, stellen eine Verbindung mit einem Berichts Server her, klicken mit der rechten Maustaste auf den Namen des Berichts Servers und wählen **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e0eda-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="e0eda-108">Klicken Sie auf **Protokollierung** , um diese Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e0eda-108">Click **Logging** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0eda-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e0eda-109">Options</span></span>  
 <span data-ttu-id="e0eda-110">**Protokollierung der Berichtsausführung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="e0eda-110">**Enable report execution logging**</span></span>  
 <span data-ttu-id="e0eda-111">Klicken Sie auf diese Schaltfläche, um Informationen über die Berichtsaktivität zu erstellen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e0eda-111">Click to create and store information about report activity on the server.</span></span> <span data-ttu-id="e0eda-112">Ist diese Option aktiviert, verfolgt der Berichtsserver nach, welche Berichte verwendet werden, die Häufigkeit der Berichtsverarbeitung, der Typ des durchgeführten Berichtsvorgangs, das Ausgabeformat und wer den Bericht ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="e0eda-112">If this option is enabled, the report server will track which reports are used, the frequency of report processing, the type of report operation that was performed, the output format, and who ran the report.</span></span> <span data-ttu-id="e0eda-113">Weitere Informationen zu zusätzlichen Datenpunkten, die im Protokoll aufgezeichnet werden, finden Sie unter [Berichts Server-Ausführungs Protokoll und die ExecutionLog3-Sicht](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span><span class="sxs-lookup"><span data-stu-id="e0eda-113">For more information about additional data points that are captured in the log, see [Report Server Execution Log and the ExecutionLog3 View](../report-server/report-server-executionlog-and-the-executionlog3-view.md).</span></span>  
  
 <span data-ttu-id="e0eda-114">**Protokolleinträge entfernen, die älter sind als die folgende Anzahl von Tagen**</span><span class="sxs-lookup"><span data-stu-id="e0eda-114">**Remove log entries older than this number of days**</span></span>  
 <span data-ttu-id="e0eda-115">Geben Sie die Anzahl an Tagen an, nach denen die Protokolleinträge aus dem Berichtsausführungsprotokoll gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e0eda-115">Specify the number of days after which log entries will be trimmed from the report execution log.</span></span> <span data-ttu-id="e0eda-116">Der Standardwert ist 60 Tage.</span><span class="sxs-lookup"><span data-stu-id="e0eda-116">The default value is 60 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0eda-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0eda-117">See Also</span></span>  
 <span data-ttu-id="e0eda-118">[&#40;Management Studio Eigenschaften für Berichts Server festlegen&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="e0eda-118">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="e0eda-119">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="e0eda-119">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="e0eda-120">[Reporting Services-Protokolldateien und Quellen](../report-server/reporting-services-log-files-and-sources.md) </span><span class="sxs-lookup"><span data-stu-id="e0eda-120">[Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md) </span></span>  
 <span data-ttu-id="e0eda-121">[Berichts Server in Management Studio F1-Hilfe](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e0eda-121">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="e0eda-122">Berichtsserverausführungsprotokoll und die ExecutionLog3-Ansicht</span><span class="sxs-lookup"><span data-stu-id="e0eda-122">Report Server Execution Log and the ExecutionLog3 View</span></span>](../report-server/report-server-executionlog-and-the-executionlog3-view.md)  
  
  
