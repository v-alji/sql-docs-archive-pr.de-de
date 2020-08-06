---
title: Hinzufügen eines Protokolls für Datenfluss-Leistungsindikatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721681"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="c4fff-102">Hinzufügen eines Protokolls für Datenfluss-Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="c4fff-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="c4fff-103">In diesem Verfahren wird beschrieben, wie ein Protokoll für die von der Datenfluss-Engine bereitgestellten Leistungsindikatoren hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c4fff-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4fff-104">Wenn Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] auf einem Computer installieren, auf dem [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)]ausgeführt wird, und anschließend ein Upgrade des betreffenden Computers auf [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)]ausführen, werden beim Upgradeprozess die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Leistungsindikatoren vom Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="c4fff-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="c4fff-105">Zum Wiederherstellen der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Leistungsindikatoren auf dem Computer führen Sie Setup von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] im Reparaturmodus aus.</span><span class="sxs-lookup"><span data-stu-id="c4fff-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="c4fff-106">So fügen Sie die Protokollierung von Leistungsindikatoren hinzu</span><span class="sxs-lookup"><span data-stu-id="c4fff-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="c4fff-107">Wenn Sie die klassische Ansicht verwenden, klicken Sie in der **Systemsteuerung**auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="c4fff-108">Wenn Sie die Kategorieansicht verwenden, klicken Sie auf **Leistung und Wartung** und dann auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="c4fff-109">Klicken Sie auf **Leistung**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="c4fff-110">Erweitern Sie im Dialogfeld **Leistung** die Option **Leistungsdatenprotokolle und Warnungen**, klicken Sie mit der rechten Maustaste auf **Leistungsindikatorenprotokolle**, und klicken Sie dann auf **Neue Protokolleinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="c4fff-111">Geben Sie den Namen des Protokolls ein.</span><span class="sxs-lookup"><span data-stu-id="c4fff-111">Type the name of the log.</span></span> <span data-ttu-id="c4fff-112">Geben Sie z. B. **MeinProtokoll**ein.</span><span class="sxs-lookup"><span data-stu-id="c4fff-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="c4fff-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c4fff-114">Klicken Sie im Dialogfeld **MeinProtokoll** auf **Indikatoren hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="c4fff-115">Klicken Sie auf **Lokale Leistungsindikatoren verwenden** , um die Leistungsindikatoren auf dem lokalen Computer zu protokollieren. Oder klicken Sie auf **Leistungsindikatoren auswählen von:** , und wählen Sie dann einen Computer aus der Liste aus, um die Leistungsindikatoren auf dem angegebenen Computer zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="c4fff-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="c4fff-116">Wählen Sie im Dialogfeld **Indikatoren hinzufügen** die Option **SQLServer:SSIS-Pipeline** aus der Liste **Leistungsobjekt** aus.</span><span class="sxs-lookup"><span data-stu-id="c4fff-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="c4fff-117">Gehen Sie zur Auswahl von Leistungsindikatoren wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c4fff-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c4fff-118">Wählen Sie **Alle Indikatoren** , um alle Leistungsindikatoren zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="c4fff-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="c4fff-119">Wählen Sie **Indikatoren aus Liste auswählen** , und wählen Sie die zu verwendenden Leistungsindikatoren aus.</span><span class="sxs-lookup"><span data-stu-id="c4fff-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="c4fff-120">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="c4fff-121">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="c4fff-122">Prüfen Sie im Dialogfeld **MeinProtokoll** die Liste **Indikatoren** mit den protokollierten Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="c4fff-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="c4fff-123">Um weitere Indikatoren hinzuzufügen, wiederholen Sie die Schritte 5 bis 10.</span><span class="sxs-lookup"><span data-stu-id="c4fff-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="c4fff-124">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4fff-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4fff-125">Sie müssen den Dienst Leistungsprotokolle und Warnungen mithilfe eines lokalen Kontos oder eines Domänenkontos starten, das Mitglied der Administratorengruppe ist.</span><span class="sxs-lookup"><span data-stu-id="c4fff-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fff-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4fff-126">See Also</span></span>  
 <span data-ttu-id="c4fff-127">[Leistungsindikatoren](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="c4fff-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="c4fff-128">Anzeigen der Protokolleinträge im Fenster „Protokollereignisse“</span><span class="sxs-lookup"><span data-stu-id="c4fff-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
