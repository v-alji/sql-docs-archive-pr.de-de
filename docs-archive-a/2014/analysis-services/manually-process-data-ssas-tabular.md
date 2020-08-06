---
title: Manuelles Verarbeiten von Daten (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620626"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="38c43-102">Manuelle Verarbeitung von Daten (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="38c43-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="38c43-103">In diesem Thema wird beschrieben, wie Arbeitsbereichsdaten in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]manuell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="38c43-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="38c43-104">Wenn Sie ein tabellarisches Modell erstellen, das externe Daten verwendet, können Sie die Daten mit dem Befehl Verarbeiten manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="38c43-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="38c43-105">Sie können eine einzelne Tabelle, alle Tabellen im Modell oder eine oder mehrere Partitionen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="38c43-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="38c43-106">Wenn Sie Daten verarbeiten, müssen Sie möglicherweise auch Daten neu berechnen.</span><span class="sxs-lookup"><span data-stu-id="38c43-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="38c43-107">Verarbeiten von Daten bedeutet, dass die aktuellen Daten aus den externen Quellen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="38c43-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="38c43-108">Neuberechnen bedeutet, dass das Ergebnis jeder Formel aktualisiert wird, die die Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="38c43-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="38c43-109">Abschnitte in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="38c43-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="38c43-110">Manuelle Verarbeitung von Daten</span><span class="sxs-lookup"><span data-stu-id="38c43-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="38c43-111">Status der Datenverarbeitung</span><span class="sxs-lookup"><span data-stu-id="38c43-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="38c43-112">Manuelles Verarbeiten von Daten</span><span class="sxs-lookup"><span data-stu-id="38c43-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="38c43-113">So verarbeiten Sie Daten für eine einzelne Tabelle oder alle Tabellen in einem Modell</span><span class="sxs-lookup"><span data-stu-id="38c43-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="38c43-114">Klicken Sie im Modell-Designer auf die Tabelle, die Sie verarbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="38c43-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="38c43-115">Wählen Sie das Menü **Modell** . Klicken Sie dann auf **Verarbeiten**und danach auf **Verarbeiten** oder **Alles verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="38c43-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="38c43-116">So verarbeiten Sie Daten für alle Tabellen, die dieselbe Verbindung verwenden</span><span class="sxs-lookup"><span data-stu-id="38c43-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="38c43-117">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]im Menü **Modell** auf **Vorhandene Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="38c43-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="38c43-118">Wählen Sie im Dialogfeld **Vorhandene Verbindungen** eine Verbindung aus, und klicken Sie dann auf **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="38c43-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="38c43-119">So verarbeiten Sie Daten für eine oder mehrere Partitionen</span><span class="sxs-lookup"><span data-stu-id="38c43-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="38c43-120">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]im Modell-Designer auf das Menü **Modell** . Navigieren Sie dann zu **Verarbeiten**, und klicken Sie anschließend auf **Partitionen verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="38c43-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="38c43-121">Wählen Sie im Dialogfeld **Partitionen verarbeiten** unter **Modus**einen der folgenden Verarbeitungsmodi aus:</span><span class="sxs-lookup"><span data-stu-id="38c43-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="38c43-122">Mode</span><span class="sxs-lookup"><span data-stu-id="38c43-122">Mode</span></span>|<span data-ttu-id="38c43-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38c43-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="38c43-124">**Standard verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="38c43-124">**Process Default**</span></span>|<span data-ttu-id="38c43-125">Erkennt den Verarbeitungsstatus eines Partitionsobjekts und führt die Verarbeitung durch, durch die nicht oder teilweise verarbeitete Partitionsobjekte in den Status "Vollständig verarbeitet" versetzt werden.</span><span class="sxs-lookup"><span data-stu-id="38c43-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="38c43-126">Daten für leere Tabellen und Partitionen werden geladen, Hierarchien, berechnete Spalten und Beziehungen werden erstellt oder neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="38c43-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="38c43-127">**Vollständig verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="38c43-127">**Process Full**</span></span>|<span data-ttu-id="38c43-128">Verarbeitet ein Partitionsobjekt und alle darin enthaltenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="38c43-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="38c43-129">Wenn die Verarbeitungsmethode "Vollständig verarbeiten" für ein bereits verarbeitetes Objekt ausgeführt wird, löscht [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] alle Daten im Objekt und verarbeitet anschließend das Objekt.</span><span class="sxs-lookup"><span data-stu-id="38c43-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="38c43-130">Diese Art der Verarbeitung ist erforderlich, wenn eine Änderung an der Objektstruktur vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="38c43-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="38c43-131">**Verarbeiten von Daten**</span><span class="sxs-lookup"><span data-stu-id="38c43-131">**Process Data**</span></span>|<span data-ttu-id="38c43-132">Lädt Daten in eine Partition oder Tabelle, ohne Hierarchien oder Beziehungen neu zu erstellen bzw. berechnete Spalten und Measures neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="38c43-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="38c43-133">**Löschung verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="38c43-133">**Process Clear**</span></span>|<span data-ttu-id="38c43-134">Entfernt alle Daten aus einer Partition.</span><span class="sxs-lookup"><span data-stu-id="38c43-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="38c43-135">**Hinzufügung verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="38c43-135">**Process Add**</span></span>|<span data-ttu-id="38c43-136">Aktualisiert die Partition inkrementell mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="38c43-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="38c43-137">Wählen Sie in der Liste der Partitionen die zu verarbeitende Partition aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="38c43-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a><span data-ttu-id="38c43-138">Status der Datenverarbeitung</span><span class="sxs-lookup"><span data-stu-id="38c43-138">Data Process Progress</span></span>  
 <span data-ttu-id="38c43-139">Im Dialogfeld **Status der Datenverarbeitung** können Sie die Verarbeitung von Daten überwachen, die Sie aus einer externen Quelle in das Modell importiert haben.</span><span class="sxs-lookup"><span data-stu-id="38c43-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="38c43-140">Um dieses Dialogfeld zu öffnen, klicken Sie auf das Menü **Modell** und anschließend auf **Partitionen verarbeiten**, **Tabelle verarbeiten** oder **Alles verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="38c43-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="38c43-141">**Status**</span><span class="sxs-lookup"><span data-stu-id="38c43-141">**Status**</span></span>  
 <span data-ttu-id="38c43-142">Gibt an, ob der Verarbeitungsvorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="38c43-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="38c43-143">**Details**</span><span class="sxs-lookup"><span data-stu-id="38c43-143">**Details**</span></span>  
 <span data-ttu-id="38c43-144">Listet die Tabellen und die Sichten, die importiert wurden, sowie die Anzahl von Zeilen auf, die importiert wurden, und stellt einen Link für einen Bericht zu Problemen bereit.</span><span class="sxs-lookup"><span data-stu-id="38c43-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="38c43-145">**Aktualisierung beenden**</span><span class="sxs-lookup"><span data-stu-id="38c43-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="38c43-146">Klicken Sie auf diese Option, um den Verarbeitungsvorgang anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="38c43-146">Click to halt the process operation.</span></span> <span data-ttu-id="38c43-147">Diese Option ist nützlich, wenn der Vorgang zu lange dauert oder wenn es zu viele Fehler gibt.</span><span class="sxs-lookup"><span data-stu-id="38c43-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c43-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38c43-148">See Also</span></span>  
 <span data-ttu-id="38c43-149">[Verarbeiten von Daten &#40;tabellarischen SSAS-&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="38c43-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="38c43-150">Problembehandlung von Verarbeitungsdaten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="38c43-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
