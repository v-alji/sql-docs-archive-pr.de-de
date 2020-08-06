---
title: Anzeigen der Protokolleinträge im Fenster "Protokollereignisse" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695794"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="b5f6b-102">Anzeigen der Protokolleinträge im Fenster „Protokollereignisse“</span><span class="sxs-lookup"><span data-stu-id="b5f6b-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="b5f6b-103">In diesem Verfahren wird das Ausführen eines Pakets und das Anzeigen der geschriebenen Protokolleinträge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="b5f6b-104">Sie können die Protokolleinträge in Echtzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-104">You can view the log entries in real time.</span></span> <span data-ttu-id="b5f6b-105">Die im Fenster **Protokollereignisse** geschriebenen Protokolleinträge können auch kopiert und für die spätere Analyse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="b5f6b-106">Dabei müssen die Protokolleinträge nicht in ein Protokoll geschrieben werden, um die Einträge in das Fenster **Protokollereignisse** zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="b5f6b-107">So zeigen Sie Protokolleinträge an</span><span class="sxs-lookup"><span data-stu-id="b5f6b-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="b5f6b-108">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b5f6b-109">Klicken Sie im Menü **SSIS** auf **Protokollereignisse**.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="b5f6b-110">Sie können das Fenster **Protokollereignisse** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.LogEvents einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="b5f6b-111">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="b5f6b-112">Sobald die Laufzeit feststellt, dass das Protokoll für Ereignisse und benutzerdefinierte Meldungen aktiviert wurde, werden die Protokolleinträge für die Ereignisse und Meldungen in das Fenster **Protokollereignisse** geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="b5f6b-113">Klicken Sie im Menü **Debuggen** auf die Option **Debuggen beenden**.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="b5f6b-114">Die Protokolleinträge sind so lange im Fenster **Protokollereignisse** verfügbar, bis Sie das Paket erneut ausführen, ein anderes Paket ausführen oder [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]schließen.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="b5f6b-115">Zeigen Sie die Protokolleinträge im Fenster **Protokollereignisse** an.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="b5f6b-116">Klicken Sie optional auf die zu kopierenden Protokolleinträge, klicken Sie auf die rechte Maustaste, und klicken dann Sie auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="b5f6b-117">Doppelklicken Sie optional auf einen Protokolleintrag, und zeigen Sie die Details eines einzelnen Protokolleintrags im Dialogfeld **Protokolleintrag** an.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="b5f6b-118">Klicken Sie im Dialogfeld **Protokolleintrag** auf die Nach-Oben- oder Nach-Unten-Taste, um den vorigen oder nächsten Protokolleintrag anzuzeigen, und klicken Sie zum Kopieren des Protokolleintrags auf das Kopiersymbol.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="b5f6b-119">Öffnen Sie einen Texteditor, um den Protokolleintrag in eine Textdatei einzufügen und zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b5f6b-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f6b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5f6b-120">See Also</span></span>  
 [<span data-ttu-id="b5f6b-121">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="b5f6b-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
