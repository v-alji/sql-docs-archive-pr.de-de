---
title: Vorschauansicht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.previewview.f1
helpviewer_keywords:
- Preview view [Reporting Services]
ms.assetid: 108255d1-5be8-47c1-80f3-1f2a055e4d02
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1ff7c59c3ac5143d4f4103edea1a5ee309046547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700700"
---
# <a name="preview-view"></a><span data-ttu-id="8d080-102">Vorschauansicht</span><span class="sxs-lookup"><span data-stu-id="8d080-102">Preview View</span></span>
  <span data-ttu-id="8d080-103">Verwenden Sie die Ansicht **Vorschau** , um den gerenderten Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d080-103">Use **Preview** view to display the rendered report.</span></span> <span data-ttu-id="8d080-104">Wenn ein Bericht in der Vorschau angezeigt wird, führt der Berichts-Designer den Bericht lokal aus und zeigt ihn in der Vorschauansicht an.</span><span class="sxs-lookup"><span data-stu-id="8d080-104">When a report is previewed, Report Designer runs the report locally and displays it in the Preview view.</span></span> <span data-ttu-id="8d080-105">Der Bericht wird im Vorschaumodus vollständig verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8d080-105">In preview mode, the report is processed in full.</span></span> <span data-ttu-id="8d080-106">Wenn der Bericht eine komplexe Abfrage oder eine große Datenmenge enthält, kann das Generieren der Vorschau beim erstmaligen Anzeigen mehrere Minuten in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="8d080-106">If the report has a complex query or has a large amount of data, preview might take several minutes to complete the first time you view it.</span></span> <span data-ttu-id="8d080-107">Bei späteren Änderungen, die sich nur auf das Format des Berichts auswirken, wird die Vorschau mit zwischengespeicherten Daten generiert.</span><span class="sxs-lookup"><span data-stu-id="8d080-107">For subsequent changes that affect only the format of the report, preview uses cached data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8d080-108">Wenn [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] als RemoteApp ausgeführt wird, können Berichte in \*\*\*\* nicht in der Vorschau [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8d080-108">When [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] is run as a RemoteApp, reports cannot be displayed in **Preview** view in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8d080-109">RemoteApp-Programme sind Programme, auf die remote über Remotedesktop-Dienste zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="8d080-109">RemoteApp programs are programs that are accessed remotely through Remote Desktop Services.</span></span> <span data-ttu-id="8d080-110">Weitere Informationen finden Sie unter [schrittweise Anleitung für TS RemoteApp](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="8d080-110">For more information, see [TS RemoteApp Step-by-Step Guide](https://technet.microsoft.com/library/cc730673\(WS.10\).aspx).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d080-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8d080-111">Options</span></span>  
 <span data-ttu-id="8d080-112">Mithilfe der Symbolleiste können Sie Vorschaufunktionen verwalten.</span><span class="sxs-lookup"><span data-stu-id="8d080-112">Use the toolbar to manage preview functions.</span></span>  
  
 <span data-ttu-id="8d080-113">**Dokumentstruktur ein-/ausblenden**</span><span class="sxs-lookup"><span data-stu-id="8d080-113">**Show or Hide Document Map**</span></span>  
 <span data-ttu-id="8d080-114">Wählen Sie diese Option aus, um die Dokumentstruktur ein- oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="8d080-114">Choose this option to show or hide the document map if one exists.</span></span>  
  
 <span data-ttu-id="8d080-115">**Parameterbereich ein-/ausblenden**</span><span class="sxs-lookup"><span data-stu-id="8d080-115">**Show or Hide Parameter Area**</span></span>  
 <span data-ttu-id="8d080-116">Wählen Sie diese Option aus, um die Parameterfelder für Berichte mit Parametern ein- oder auszublenden.</span><span class="sxs-lookup"><span data-stu-id="8d080-116">Choose this option to show or hide the parameters boxes for reports with parameters.</span></span>  
  
 <span data-ttu-id="8d080-117">**Erste Seite**</span><span class="sxs-lookup"><span data-stu-id="8d080-117">**First Page**</span></span>  
 <span data-ttu-id="8d080-118">Wählen Sie diese Option aus, um zur ersten Seite des Berichts zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-118">Choose this option to go to the first page of the report.</span></span>  
  
 <span data-ttu-id="8d080-119">**Vorherige Seite**</span><span class="sxs-lookup"><span data-stu-id="8d080-119">**Previous Page**</span></span>  
 <span data-ttu-id="8d080-120">Wählen Sie diese Option aus, um zur vorherigen Seite des Berichts zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-120">Choose this option to go to the previous page of the report.</span></span>  
  
 <span data-ttu-id="8d080-121">**Aktuelle Seite**</span><span class="sxs-lookup"><span data-stu-id="8d080-121">**Current Page**</span></span>  
 <span data-ttu-id="8d080-122">Zeigt die aktuelle Seite des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="8d080-122">Displays the current page of the report.</span></span>  
  
 <span data-ttu-id="8d080-123">**Seiten gesamt**</span><span class="sxs-lookup"><span data-stu-id="8d080-123">**Total Pages**</span></span>  
 <span data-ttu-id="8d080-124">Zeigt die Gesamtzahl der Seiten des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="8d080-124">Displays the total number of pages in the report.</span></span>  
  
 <span data-ttu-id="8d080-125">**Nächste Seite**</span><span class="sxs-lookup"><span data-stu-id="8d080-125">**Next Page**</span></span>  
 <span data-ttu-id="8d080-126">Wählen Sie diese Option aus, um zur nächsten Seite des Berichts zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-126">Choose this option to go to the next page of the report.</span></span>  
  
 <span data-ttu-id="8d080-127">**Letzte Seite**</span><span class="sxs-lookup"><span data-stu-id="8d080-127">**Last Page**</span></span>  
 <span data-ttu-id="8d080-128">Wählen Sie diese Option aus, um zur letzten Seite des Berichts zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-128">Choose this option to go to the last page of the report.</span></span>  
  
 <span data-ttu-id="8d080-129">**Zurück zum übergeordneten Bericht**</span><span class="sxs-lookup"><span data-stu-id="8d080-129">**Back to Parent Report**</span></span>  
 <span data-ttu-id="8d080-130">Wählen Sie diese Option aus, um zum übergeordneten Bericht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-130">Choose this option to go to the parent report.</span></span> <span data-ttu-id="8d080-131">Diese Option wird zum Navigieren in Drillthroughberichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d080-131">This option is used to navigate drillthrough reports.</span></span>  
  
 <span data-ttu-id="8d080-132">**Rendern beenden**</span><span class="sxs-lookup"><span data-stu-id="8d080-132">**Stop Rendering**</span></span>  
 <span data-ttu-id="8d080-133">Wählen Sie diese Option aus, um das Rendern zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8d080-133">Choose this option to stop the rendering process.</span></span>  
  
 <span data-ttu-id="8d080-134">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="8d080-134">**Refresh**</span></span>  
 <span data-ttu-id="8d080-135">Wählen Sie diese Option aus, um den Datencache zu aktualisieren, und führen Sie den Bericht erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8d080-135">Choose this option to refresh the data cache and run the report again.</span></span>  
  
 <span data-ttu-id="8d080-136">**Drucken**</span><span class="sxs-lookup"><span data-stu-id="8d080-136">**Print**</span></span>  
 <span data-ttu-id="8d080-137">Wählen Sie diese Option aus, um den Bericht zu drucken.</span><span class="sxs-lookup"><span data-stu-id="8d080-137">Choose this option to print the report.</span></span>  
  
 <span data-ttu-id="8d080-138">**Drucklayout**</span><span class="sxs-lookup"><span data-stu-id="8d080-138">**Print Layout**</span></span>  
 <span data-ttu-id="8d080-139">Wählen Sie diese Option aus, um zwischen der Berichtsvorschau und der Anzeige des Berichts als gedruckte Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d080-139">Choose this option to toggle between the preview report and the view of the report as it will appear on the printed page.</span></span>  
  
 <span data-ttu-id="8d080-140">**Seite einrichten**</span><span class="sxs-lookup"><span data-stu-id="8d080-140">**Page Setup**</span></span>  
 <span data-ttu-id="8d080-141">Wählen Sie diese Option aus, um Seiten- und Druckeigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8d080-141">Choose this option to conveniently change page and print properties.</span></span> <span data-ttu-id="8d080-142">Verwenden Sie Seitenlayout, um Änderungen vor dem Drucken anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8d080-142">Use Print Layout to view changes before printing.</span></span>  
  
 <span data-ttu-id="8d080-143">**Export**</span><span class="sxs-lookup"><span data-stu-id="8d080-143">**Export**</span></span>  
 <span data-ttu-id="8d080-144">Wählen Sie diese Option aus, um den gerenderten Bericht in einem bestimmten Format zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="8d080-144">Choose this option to export the rendered report in a specific format.</span></span>  
  
 <span data-ttu-id="8d080-145">**Zoom**</span><span class="sxs-lookup"><span data-stu-id="8d080-145">**Zoom**</span></span>  
 <span data-ttu-id="8d080-146">Wählen Sie einen Zoomfaktor zum Verkleinern oder Vergrößern des Berichts aus.</span><span class="sxs-lookup"><span data-stu-id="8d080-146">Select a zoom factor to zoom in or out on the report.</span></span>  
  
 <span data-ttu-id="8d080-147">**Suchtext**</span><span class="sxs-lookup"><span data-stu-id="8d080-147">**Search Text**</span></span>  
 <span data-ttu-id="8d080-148">Geben Sie Text zum Suchen nach einer Übereinstimmung in dem Bericht ein.</span><span class="sxs-lookup"><span data-stu-id="8d080-148">Type text to search for a match within the report.</span></span> <span data-ttu-id="8d080-149">Das Verwenden von Suchoperatoren ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="8d080-149">You cannot use search operators.</span></span> <span data-ttu-id="8d080-150">Klicken Sie auf **Suchen** , um nach der ersten Instanz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8d080-150">Click **Find** to search for the first instance.</span></span>  
  
 <span data-ttu-id="8d080-151">**Sich**</span><span class="sxs-lookup"><span data-stu-id="8d080-151">**Find**</span></span>  
 <span data-ttu-id="8d080-152">Wählen Sie diese Option aus, um die Suche nach dem Suchtext in dem Bericht zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="8d080-152">Choose this option to begin searching the report for the search text.</span></span>  
  
 <span data-ttu-id="8d080-153">**Weitersuchen**</span><span class="sxs-lookup"><span data-stu-id="8d080-153">**Find Next**</span></span>  
 <span data-ttu-id="8d080-154">Wählen Sie diese Option aus, um nach der nächsten Instanz des Suchtexts zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8d080-154">Choose this option to search for the next instance of the search text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d080-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d080-155">See Also</span></span>  
 <span data-ttu-id="8d080-156">[Anzeigen einer Vorschau für Berichte](../reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="8d080-156">[Previewing Reports](../reports/previewing-reports.md) </span></span>  
 [<span data-ttu-id="8d080-157">Berichts-Designer (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="8d080-157">Report Designer F1 Help</span></span>](report-designer-f1-help.md)  
  
  
