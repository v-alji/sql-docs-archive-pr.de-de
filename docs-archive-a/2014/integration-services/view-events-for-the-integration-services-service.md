---
title: Anzeigen von Ereignissen für den Integration Services-Dienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621054"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="34468-102">Anzeigen von Ereignissen für den Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="34468-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="34468-103">Es gibt zwei Tools, in denen Sie Ereignisse für den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst anzeigen können:</span><span class="sxs-lookup"><span data-stu-id="34468-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="34468-104">Das Dialogfeld **Protokolldatei-Viewer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34468-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="34468-105">Das Dialogfeld **Protokolldatei-Viewer** enthält Optionen zum Exportieren, Filtern und Durchsuchen des Protokolls.</span><span class="sxs-lookup"><span data-stu-id="34468-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="34468-106">Weitere Informationen zu den Optionen im Dialogfeld **Protokolldatei-Viewer**finden Sie unter [Protokolldatei-Viewer (F1-Hilfe)](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="34468-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="34468-107">Die Windows-Ereignisanzeige.</span><span class="sxs-lookup"><span data-stu-id="34468-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="34468-108">Eine Beschreibung der vom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst protokollierten Ereignisse finden Sie unter [Ereignisprotokollierung durch den Integration Services-Dienst](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="34468-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="34468-109">So zeigen Sie Dienstereignisse für Integration Services in SQL Server Management Studio an</span><span class="sxs-lookup"><span data-stu-id="34468-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="34468-110">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34468-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="34468-111">Klicken Sie im Menü **Datei** auf **Objekt-Explorer verbinden**.</span><span class="sxs-lookup"><span data-stu-id="34468-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="34468-112">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Servertyp aus, wählen Sie den Server aus, mit dem die Verbindung hergestellt werden soll, oder suchen Sie ihn, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="34468-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="34468-113">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , und klicken Sie anschließend auf **Protokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="34468-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="34468-114">Wählen Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] SQL Server Integration Services **aus, um die**-Ereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="34468-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="34468-115">Die Option **NT-Ereignisse** ist automatisch ausgewählt und wird durch die Option **SQL Server Integration Services** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34468-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="34468-116">So zeigen Sie Dienstereignisse für Integration Services in der Windows-Ereignisanzeige an</span><span class="sxs-lookup"><span data-stu-id="34468-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="34468-117">Wenn Sie die klassische Ansicht verwenden, klicken Sie in der **Systemsteuerung**auf **Verwaltung**. Wenn Sie die Kategorieansicht verwenden, klicken Sie auf **Leistung und Wartung** und dann auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="34468-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="34468-118">Klicken Sie auf **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="34468-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="34468-119">Klicken Sie im Dialogfeld **Ereignisanzeige** auf **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="34468-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="34468-120">Suchen Sie im **Anwendungs** -Snap-In einen Eintrag in der Spalte **Quelle** , die den Wert **SQLISService**enthält. Klicken Sie mit der rechten Maustaste auf den Eintrag und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="34468-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="34468-121">Klicken Sie wahlweise auf den Nach-Oben- oder Nach-Unten-Pfeil, um das vorherige oder nächste Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="34468-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="34468-122">Klicken Sie wahlweise auf das Symbol "In Zwischenablage speichern", um die Ereignisinformationen zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="34468-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="34468-123">Zeigen Sie die Ereignisdaten in Byte oder Wörtern an.</span><span class="sxs-lookup"><span data-stu-id="34468-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="34468-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34468-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="34468-125">Klicken Sie im Menü **Datei** auf **Beenden** , um das Dialogfeld **Ereignisanzeige** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="34468-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34468-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34468-126">See Also</span></span>  
 <span data-ttu-id="34468-127">[Verwalten des Integration Services Dienstanbieter](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="34468-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="34468-128">Hinzufügen eines Protokolls für Datenfluss-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="34468-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
