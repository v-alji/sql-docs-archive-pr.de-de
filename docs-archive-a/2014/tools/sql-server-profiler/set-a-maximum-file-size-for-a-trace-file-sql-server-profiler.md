---
title: Festlegen einer maximalen Dateigröße für eine Ablaufverfolgungsdatei (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- maximum file size for traces
- size [SQL Server], trace files
ms.assetid: e86dc4ce-5aa3-4c0d-acb5-c9e8871ed963
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa990c610f7aa8bf82690c8c201c6643eb712191
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720617"
---
# <a name="set-a-maximum-file-size-for-a-trace-file-sql-server-profiler"></a><span data-ttu-id="4c9d7-102">Festlegen einer maximalen Dateigröße für eine Ablaufverfolgungsdatei (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="4c9d7-102">Set a Maximum File Size for a Trace File (SQL Server Profiler)</span></span>
  <span data-ttu-id="4c9d7-103">Verwenden Sie die folgende Prozedur, um die maximale Dateigröße für eine Ablaufverfolgungsdatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-103">Use the following procedure to set the maximum file size for a trace file.</span></span>  
  
### <a name="to-set-a-maximum-file-size-for-a-trace-file"></a><span data-ttu-id="4c9d7-104">So legen Sie die maximale Dateigröße für eine Ablaufverfolgungsdatei fest</span><span class="sxs-lookup"><span data-stu-id="4c9d7-104">To set a maximum file size for a trace file</span></span>  
  
1.  <span data-ttu-id="4c9d7-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung zu einer Instanz von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-105">On the **File** menu, click **New Trace**, and then connect to an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="4c9d7-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c9d7-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="4c9d7-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="4c9d7-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="4c9d7-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="4c9d7-110">Geben Sie im Feld **Vorlagenname**eine Ablaufverfolgungsvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="4c9d7-111">Wählen Sie **In Datei speichern**aus, und geben Sie dann eine Datei zum Speichern der Ablaufverfolgungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-111">Select **Save to file**, and then specify a file to store the trace information.</span></span>  
  
5.  <span data-ttu-id="4c9d7-112">Aktivieren Sie das Kontrollkästchen **Maximale Dateigröße festlegen** , und geben Sie die maximale Dateigröße für die Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-112">In the **Set maximum file size** check box, specify a maximum file size for the trace.</span></span> <span data-ttu-id="4c9d7-113">Erreicht die Datei die maximale Größe, werden die Ablaufverfolgungsereignisse in dieser Datei nicht mehr aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-113">When the file size reaches this maximum, trace events are no longer recorded in this file.</span></span> <span data-ttu-id="4c9d7-114">Folgende Situation tritt ein, wenn Sie die Option **Dateirollover aktivieren** auswählen (dies ist standardmäßig ausgewählt):</span><span class="sxs-lookup"><span data-stu-id="4c9d7-114">If you select **Enable file rollover** (which is selected by default),the following occurs:</span></span>  
  
     <span data-ttu-id="4c9d7-115">Die Dateirolloveroption führt dazu, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die aktuelle Datei schließt und eine neue Datei erstellt, wenn die maximale Dateigröße erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-115">The file rollover option causes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to close the current file and create a new file when the maximum file size is reached.</span></span> <span data-ttu-id="4c9d7-116">Die neue Datei hat den gleichen Namen wie die vorige, sie wird jedoch zur Angabe der Abfolge um eine ganze Zahl ergänzt. Wenn z. B. der Name der ursprünglichen Ablaufverfolgungsdatei filename_1.trc lautet, lautet der Name der folgenden Ablaufverfolgungsdatei filename_2.trc usw.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-116">The new file has the same name as the previous file, but an integer is appended to the name to indicate its sequence; for example, if the original trace file is named filename_1.trc, the next trace file is filename_2.trc, and so on.</span></span> <span data-ttu-id="4c9d7-117">Wird der einer neuen Rolloverdatei zugewiesene Name bereits von einer vorhandenen Datei verwendet, wird die vorhandene Datei überschrieben, es sei denn, sie ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-117">If the name assigned to a new rollover file is already used by an existing file, the existing file is overwritten unless it is read-only.</span></span> <span data-ttu-id="4c9d7-118">Die Dateirolloveroption ist standardmäßig aktiviert, wenn Sie Ablaufverfolgungsdaten in einer Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-118">The file rollover option is enabled by default when you are saving trace data to a file.</span></span>  
  
     <span data-ttu-id="4c9d7-119">Bei aktivierter Dateirolloveroption wird die Ablaufverfolgung fortgesetzt, bis sie auf andere Weise beendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-119">With the file rollover option on, the trace continues until it is stopped by some other means.</span></span> <span data-ttu-id="4c9d7-120">Um die Ablaufverfolgung zu beenden, nachdem die Dateigrößenbeschränkung erreicht wurde, deaktivieren Sie die Dateirolloveroption.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-120">To stop the trace after you have reached the file size limit, disable the file rollover option.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c9d7-121">Durch das FAT32-Dateisystem wird die Größe von Dateien auf knapp 4 Gigabyte (GB) beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-121">The FAT32 file system limits files to slightly less than 4 gigabytes (GB).</span></span> <span data-ttu-id="4c9d7-122">Wenn diese Dateigröße erreicht wird, schlägt die Ablaufverfolgung mit dem Fehler "Nicht genügend Speicherplatz" fehl.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-122">When the trace file reaches that size, the trace fails with the error "Not enough disk space."</span></span> <span data-ttu-id="4c9d7-123">Verwenden Sie zum Erstellen größerer Dateien das NTFS-Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="4c9d7-123">To create larger files, use the NTFS file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9d7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c9d7-124">See Also</span></span>  
 [<span data-ttu-id="4c9d7-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4c9d7-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
