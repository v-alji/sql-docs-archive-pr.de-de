---
title: Verarbeiten von Tabellen Modell Partitionen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6c498d2b-22d6-4661-bc21-2ee708336c8b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 496874707bd4030a98b1794fe7513d1d857390ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696114"
---
# <a name="process-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="01c51-102">Verarbeiten von Tabellenmodellpartitionen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="01c51-102">Process Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="01c51-103">Durch Partitionen wird eine Tabelle logisch unterteilt.</span><span class="sxs-lookup"><span data-stu-id="01c51-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="01c51-104">Jede Partition kann unabhängig von anderen Partitionen verarbeitet (aktualisiert) werden.</span><span class="sxs-lookup"><span data-stu-id="01c51-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="01c51-105">In den Tasks in diesem Thema wird beschrieben, wie Partitionen in einer Modelldatenbank mithilfe des Dialogfelds **Partition(en) verarbeiten** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="01c51-105">The tasks in this topic describe how to process partitions in a model database by using the **Process Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
###  <a name="to-process-a-partition"></a><a name="bkmk_create_new"></a> <span data-ttu-id="01c51-106">So verarbeiten Sie eine Partition</span><span class="sxs-lookup"><span data-stu-id="01c51-106">To process a partition</span></span>  
  
1.  <span data-ttu-id="01c51-107">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]mit der rechten Maustaste auf die Tabelle, die die zu verarbeitenden Partitionen enthält, und klicken Sie anschließend auf **Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="01c51-107">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on the table that has the partitions you want to process, and then click **Partitions**.</span></span>  
  
2.  <span data-ttu-id="01c51-108">Klicken Sie im Dialogfeld **Partitionen** unter **Partitionen**auf die Schaltfläche Verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01c51-108">In the **Partitions** dialog box, in **Partitions**, click on the Process button.</span></span>  
  
3.  <span data-ttu-id="01c51-109">Wählen Sie im Dialogfeld **Partition (en) verarbeiten** im Listenfeld **Modus** einen der folgenden Verarbeitungsmodi aus:</span><span class="sxs-lookup"><span data-stu-id="01c51-109">In the **Process Partition(s)** dialog box, in the **Mode** listbox, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="01c51-110">Mode</span><span class="sxs-lookup"><span data-stu-id="01c51-110">Mode</span></span>|<span data-ttu-id="01c51-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="01c51-111">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="01c51-112">**Standard verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="01c51-112">**Process Default**</span></span>|<span data-ttu-id="01c51-113">Erkennt den Verarbeitungsstatus eines Partitionsobjekts und führt die Verarbeitung durch, durch die nicht oder teilweise verarbeitete Partitionsobjekte in den Status "Vollständig verarbeitet" versetzt werden.</span><span class="sxs-lookup"><span data-stu-id="01c51-113">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="01c51-114">Daten für leere Tabellen und Partitionen werden geladen, Hierarchien, berechnete Spalten und Beziehungen werden erstellt oder neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="01c51-114">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="01c51-115">**Vollständig verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="01c51-115">**Process Full**</span></span>|<span data-ttu-id="01c51-116">Verarbeitet ein Partitionsobjekt und alle darin enthaltenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="01c51-116">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="01c51-117">Wenn die Verarbeitungsmethode "Vollständig verarbeiten" für ein bereits verarbeitetes Objekt ausgeführt wird, löscht [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] alle Daten im Objekt und verarbeitet anschließend das Objekt.</span><span class="sxs-lookup"><span data-stu-id="01c51-117">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="01c51-118">Diese Art der Verarbeitung ist erforderlich, wenn eine Änderung an der Objektstruktur vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="01c51-118">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="01c51-119">**Verarbeiten von Daten**</span><span class="sxs-lookup"><span data-stu-id="01c51-119">**Process Data**</span></span>|<span data-ttu-id="01c51-120">Lädt Daten in eine Partition oder Tabelle, ohne Hierarchien oder Beziehungen neu zu erstellen bzw. berechnete Spalten und Measures neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="01c51-120">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="01c51-121">**Löschung verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="01c51-121">**Process Clear**</span></span>|<span data-ttu-id="01c51-122">Entfernt alle Daten aus einer Partition.</span><span class="sxs-lookup"><span data-stu-id="01c51-122">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="01c51-123">**Hinzufügung verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="01c51-123">**Process Add**</span></span>|<span data-ttu-id="01c51-124">Aktualisiert die Partition inkrementell mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="01c51-124">Incrementally update partition with new data.</span></span>|  
  
4.  <span data-ttu-id="01c51-125">Wählen Sie in der Spalte der Kontrollkästchen unter **Verarbeiten** die Partitionen aus, die im ausgewählten Modus verarbeitet werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="01c51-125">In the **Process** checkbox column, select the partitions you want to process with the selected mode, and then click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c51-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01c51-126">See Also</span></span>  
 <span data-ttu-id="01c51-127">[Tabellarische Modell Partitionen &#40;tabellarischen SSAS-&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="01c51-127">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="01c51-128">Erstellen und Verwalten von Tabellenmodellpartitionen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="01c51-128">Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](create-and-manage-tabular-model-partitions-ssas-tabular.md)  
  
  
