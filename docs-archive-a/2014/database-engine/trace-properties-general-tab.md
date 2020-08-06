---
title: Ablauf Verfolgungs Eigenschaften (Registerkarte "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724897"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="ef11a-102">Ablaufverfolgungseigenschaften (Registerkarte Allgemein)</span><span class="sxs-lookup"><span data-stu-id="ef11a-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="ef11a-103">Mithilfe der Registerkarte **Allgemein** im Dialogfeld **Ablaufverfolgungseigenschaften** können Sie die Eigenschaften einer Ablaufverfolgung anzeigen und festlegen.</span><span class="sxs-lookup"><span data-stu-id="ef11a-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef11a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ef11a-104">Options</span></span>  
 <span data-ttu-id="ef11a-105">**Ablaufverfolgungsname**</span><span class="sxs-lookup"><span data-stu-id="ef11a-105">**Trace name**</span></span>  
 <span data-ttu-id="ef11a-106">Gibt den Namen der Ablaufverfolgung an.</span><span class="sxs-lookup"><span data-stu-id="ef11a-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="ef11a-107">**Name des Ablaufverfolgungsanbieters**</span><span class="sxs-lookup"><span data-stu-id="ef11a-107">**Trace provider name**</span></span>  
 <span data-ttu-id="ef11a-108">Zeigt den Namen der Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an, für die die Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="ef11a-109">Dieses Feld wird automatisch mit dem Namen des Servers ausgefüllt, den Sie bei der Verbindung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ef11a-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="ef11a-110">Um den Namen des Ablaufverfolgungsanbieters zu ändern, klicken Sie auf **Abbrechen** , um das Dialogfeld zu schließen, und starten Sie eine neue Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="ef11a-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="ef11a-111">**Typ des Ablaufverfolgungsanbieters**</span><span class="sxs-lookup"><span data-stu-id="ef11a-111">**Trace provider type**</span></span>  
 <span data-ttu-id="ef11a-112">Zeigt den Servertyp an, der die Ablaufverfolgung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ef11a-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="ef11a-113">Das Feld **Typ des Ablaufverfolgungsanbieters** wird automatisch mithilfe der Datei mit den Ablaufverfolgungsdefinitionen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ef11a-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="ef11a-114">Sie können diesen Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ef11a-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="ef11a-115">**version**</span><span class="sxs-lookup"><span data-stu-id="ef11a-115">**version**</span></span>  
 <span data-ttu-id="ef11a-116">Zeigt die Version des Servers an, der die Ablaufverfolgung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ef11a-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="ef11a-117">Das Feld **Version** wird automatisch mithilfe der Datei mit den Ablaufverfolgungsdefinitionen ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ef11a-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="ef11a-118">Sie können diesen Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ef11a-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="ef11a-119">**Verwenden der Vorlage**</span><span class="sxs-lookup"><span data-stu-id="ef11a-119">**Use the template**</span></span>  
 <span data-ttu-id="ef11a-120">Wählt eine Vorlage aus dem Vorlagenverzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="ef11a-120">Select a template from the template directory.</span></span> <span data-ttu-id="ef11a-121">Das Verzeichnis enthält die Standardvorlagen und alle benutzerdefinierten Vorlagen, die für den aktuellen Typ des Ablaufverfolgungsanbieters erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef11a-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="ef11a-122">**In Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="ef11a-122">**Save to file**</span></span>  
 <span data-ttu-id="ef11a-123">Zeichnet die Ablaufverfolgungsdaten in einer TRC-Datei auf.</span><span class="sxs-lookup"><span data-stu-id="ef11a-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="ef11a-124">Das Speichern von Ablaufverfolgungsdaten ist für die spätere Überprüfung und Analyse nützlich.</span><span class="sxs-lookup"><span data-stu-id="ef11a-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="ef11a-125">**Maximale Dateigröße festlegen (MB)**</span><span class="sxs-lookup"><span data-stu-id="ef11a-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="ef11a-126">Wenn Sie die Ablaufverfolgungsdaten in einer Datei speichern, müssen Sie die maximale Größe der Ablaufverfolgungsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ef11a-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="ef11a-127">Der Standardwert ist 5 MB.</span><span class="sxs-lookup"><span data-stu-id="ef11a-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="ef11a-128">Die maximale Größe ist nur durch das Dateisystem (NTFS, FAT) begrenzt, in dem die Datei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="ef11a-129">\<Graphic>**Speichern** unter</span><span class="sxs-lookup"><span data-stu-id="ef11a-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="ef11a-130">Nachdem Sie die Option zum Speichern ausgewählt haben, können Sie dieses Symbol verwenden, um den Dateinamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ef11a-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="ef11a-131">**Dateirollover aktivieren**</span><span class="sxs-lookup"><span data-stu-id="ef11a-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="ef11a-132">Wählen Sie diese Option, um das Erstellen zusätzlicher Dateien für Ablaufverfolgungsdaten zu ermöglichen, wenn die maximale Dateigröße erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="ef11a-133">Jeder neue Dateiname besteht aus dem ursprünglichen Namen der TRC-Datei mit einer aufsteigenden Nummer.</span><span class="sxs-lookup"><span data-stu-id="ef11a-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="ef11a-134">Wenn z. B. für die Datei **NewTrace.trc** die maximale Dateigröße erreicht ist, wird sie geschlossen und eine neue Datei mit dem Namen **NewTrace_1.trc**geöffnet, gefolgt von der Datei **NewTrace_2.trc**usw.</span><span class="sxs-lookup"><span data-stu-id="ef11a-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="ef11a-135">Der Dateirollover wird standardmäßig aktiviert, wenn Sie eine Ablaufverfolgung in eine Datei speichern.</span><span class="sxs-lookup"><span data-stu-id="ef11a-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="ef11a-136">**Ablaufverfolgungsdaten von Serverprozessen**</span><span class="sxs-lookup"><span data-stu-id="ef11a-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="ef11a-137">Gibt an, dass der Server, der die Ablaufverfolgung ausführt, die Ablaufverfolgungsdaten verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="ef11a-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="ef11a-138">Mit dieser Option kann der Verarbeitungsaufwand reduziert werden, der durch die Ablaufverfolgung verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="ef11a-139">Ist sie aktiviert, werden keine Ereignisse ausgelassen, auch nicht unter Belastungsbedingungen.</span><span class="sxs-lookup"><span data-stu-id="ef11a-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="ef11a-140">Ist dieses Kontrollkästchen deaktiviert, übernimmt SQL Server Profiler die Verarbeitung. In diesem Fall besteht die Möglichkeit, dass einige Ereignisse bei hoher Belastung nicht verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11a-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="ef11a-141">**In Tabelle speichern**</span><span class="sxs-lookup"><span data-stu-id="ef11a-141">**Save to table**</span></span>  
 <span data-ttu-id="ef11a-142">Zeichnet die Ablaufverfolgungsdaten in einer Datenbanktabelle auf.</span><span class="sxs-lookup"><span data-stu-id="ef11a-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="ef11a-143">Das Speichern von Ablaufverfolgungsdaten ist für die spätere Überprüfung und Analyse nützlich.</span><span class="sxs-lookup"><span data-stu-id="ef11a-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="ef11a-144">Durch das Speichern von Ablaufverfolgungsdaten in einer Tabelle kann es jedoch zu einem hohen Verarbeitungsaufwand auf dem Server kommen, auf dem die Ablaufverfolgung gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="ef11a-145">Vermeiden Sie daher wenn möglich, die Ablaufverfolgungstabelle auf demselben Server zu speichern, für den die Ablaufverfolgung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ef11a-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="ef11a-146">\<Graphic>**Ziel Tabelle**</span><span class="sxs-lookup"><span data-stu-id="ef11a-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="ef11a-147">Wenn Sie die Option zum Speichern der Ablaufverfolgungsdaten in einer Datenbanktabelle ausgewählt haben, können Sie auf dieses Symbol klicken, um den Tabellennamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ef11a-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="ef11a-148">**Maximale Zeilenzahl festlegen (in Tausend)**</span><span class="sxs-lookup"><span data-stu-id="ef11a-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="ef11a-149">Gibt die Höchstanzahl der Zeilen an, in denen Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef11a-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="ef11a-150">Die Standardeinstellung ist 1000 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="ef11a-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="ef11a-151">**Beendigungszeit für Ablaufverfolgung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="ef11a-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="ef11a-152">Legt das Datum und die Uhrzeit für das Ende und das Schließen der Ablaufverfolgung fest.</span><span class="sxs-lookup"><span data-stu-id="ef11a-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef11a-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef11a-153">See Also</span></span>  
 [<span data-ttu-id="ef11a-154">Erstellen einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="ef11a-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
