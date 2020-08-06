---
title: Assistent zum Verwalten von Partitionen (F1-Hilfe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.managepartition.getstart.f1
- sql12.swb.managepartition.selectoutput.f1
- sql12.swb.managepartition.partitionaction.f1
- sql12.swb.managepartition.switchout.f1
- sql12.swb.managepartition.summary.f1
- sql12.swb.managepartition.createjob.f1
- sql12.swb.managepartition.stagingtable.f1
- sql12.swb.managepartition.progress.f1
- sql12.swb.managepartition.switchin.f1
- sql12.swb.managepartition.selectswitchtables.f1
helpviewer_keywords:
- wizards [SQL Server Management Studio] See Manage Partition Wizard
ms.assetid: e2478d26-dea4-428d-98c5-aad2d2a30da8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 09b3e774168e9a48a0a387c3474b29f96081d875
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696785"
---
# <a name="manage-partition-wizard-f1-help"></a><span data-ttu-id="c645a-102">Assistent zum Verwalten von Partitionen (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="c645a-102">Manage Partition Wizard F1 Help</span></span>
  <span data-ttu-id="c645a-103">Mit dem **Assistenten zum Verwalten von Partitionen** können Sie vorhandene partitionierte Tabellen durch Partitionswechsel oder Implementierung eines Szenarios mit gleitendem Fenster verwalten und ändern.</span><span class="sxs-lookup"><span data-stu-id="c645a-103">Use the **Manage Partition Wizard** to manage and modify existing partitioned tables through partition switching or the implementation of a sliding window scenario.</span></span> <span data-ttu-id="c645a-104">Dieser Assistent vereinfacht die Verwaltung von Partitionen und die Migration von Daten in die und aus den Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c645a-104">This wizard can ease the management of your partitions and simplify the regular migration of data in and out of your tables.</span></span>  
  
### <a name="to-start-the-manage-partition-wizard"></a><span data-ttu-id="c645a-105">So starten Sie den Assistenten zum Verwalten von Partitionen</span><span class="sxs-lookup"><span data-stu-id="c645a-105">To start the Manage Partition Wizard</span></span>  
  
-   <span data-ttu-id="c645a-106">Wählen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die Datenbank aus, klicken Sie mit der rechten Maustaste auf die Tabelle, für die Sie Partitionen erstellen möchten, zeigen Sie auf **Speicher**, und klicken Sie anschließend auf **Partition verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c645a-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the database, right-click the table on which you want to create partitions, point to **Storage**, and then click **Manage Partition**.</span></span>  
  
     <span data-ttu-id="c645a-107">`Note`Wenn **Partition verwalten** nicht verfügbar ist, haben Sie möglicherweise eine Tabelle ausgewählt, die keine Partitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="c645a-107">`Note` If **Manage Partition** is unavailable, you may have selected a table that does not contain partitions.</span></span> <span data-ttu-id="c645a-108">Klicken Sie im Untermenü **Speicher** auf **Partition erstellen** , und erstellen Sie mit dem **Assistenten zum Erstellen von Partitionen** Partitionen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c645a-108">Click **Create Partition** on the **Storage** submenu and use the **Create Partition Wizard** to create partitions in your table.</span></span>  
  
 <span data-ttu-id="c645a-109">Allgemeine Informationen zu Partitionen und Indizes finden Sie unter [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="c645a-109">For general information about partitions and indexes, see [Partitioned Tables and Indexes](partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="c645a-110">Dieser Abschnitt stellt die Informationen bereit, die zum Verwalten, Ändern und Implementieren von Partitionen mit dem **Assistenten zum Verwalten von Partitionen**erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c645a-110">This section provides the information that is required to manage, modify, and implement partitions using the **Manage Partition Wizard**.</span></span>  
  
##  <a name="in-this-section"></a><a name="Top"></a> <span data-ttu-id="c645a-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c645a-111">In This Section</span></span>  
 <span data-ttu-id="c645a-112">Die folgenden Abschnitte stellen Hilfe für die Seiten des **Assistenten zum Verwalten von Partitionen** bereit.</span><span class="sxs-lookup"><span data-stu-id="c645a-112">The following sections provide help on the pages of the **Manage Partition Wizard**.</span></span>  
  
 [<span data-ttu-id="c645a-113">Assistent zum Verwalten von Partitionen (Seite 'Partitionsaktion auswählen')</span><span class="sxs-lookup"><span data-stu-id="c645a-113">Manage Partition Wizard (Select Partition Action Page)</span></span>](#SelectPartitionAction)  
  
 [<span data-ttu-id="c645a-114">Assistent zum Verwalten von Partitionen (Seite "Einfügen")</span><span class="sxs-lookup"><span data-stu-id="c645a-114">Manage Partition Wizard (Switch In Page)</span></span>](#SwitchIn)  
  
 [<span data-ttu-id="c645a-115">Assistent zum Verwalten von Partitionen (Seite "Auslagern")</span><span class="sxs-lookup"><span data-stu-id="c645a-115">Manage Partition Wizard (Switch Out Page)</span></span>](#SwitchOut)  
  
 [<span data-ttu-id="c645a-116">Assistent zum Verwalten von Partitionen (Seite 'Stagingtabellenoptionen auswählen')</span><span class="sxs-lookup"><span data-stu-id="c645a-116">Manage Partition Wizard (Select Staging Table Options Page)</span></span>](#StagingTableOptions)  
  
 [<span data-ttu-id="c645a-117">Assistent zum Verwalten von Partitionen (Seite 'Ausgabeoption auswählen')</span><span class="sxs-lookup"><span data-stu-id="c645a-117">Manage Partition Wizard (Select Output Option Page)</span></span>](#OutputOption)  
  
 [<span data-ttu-id="c645a-118">Assistent zum Verwalten von Partitionen (Seite 'Neuer Auftragszeitplan')</span><span class="sxs-lookup"><span data-stu-id="c645a-118">Manage Partition Wizard (New Job Schedule Page)</span></span>](#NewJob)  
  
 [<span data-ttu-id="c645a-119">Assistent zum Verwalten von Partitionen (Seite 'Zusammenfassung')</span><span class="sxs-lookup"><span data-stu-id="c645a-119">Manage Partition Wizard (Summary Page)</span></span>](#Summary)  
  
 [<span data-ttu-id="c645a-120">Assistent zum Verwalten von Partitionen (Seite 'Status')</span><span class="sxs-lookup"><span data-stu-id="c645a-120">Manage Partition Wizard (Progress Page)</span></span>](#Progress)  
  
##  <a name="select-partition-action-page"></a><a name="SelectPartitionAction"></a> <span data-ttu-id="c645a-121">Partitionsaktion auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-121">Select Partition Action Page</span></span>  
 <span data-ttu-id="c645a-122">Auf der Seite **Partitionsaktion auswählen** können Sie die Aktion auswählen, die Sie für die Partition ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c645a-122">Use the **Select Partition Action** page to choose the action you want to perform on your partition.</span></span>  
  
### <a name="create-a-staging-table"></a><span data-ttu-id="c645a-123">Erstellen einer Stagingtabelle</span><span class="sxs-lookup"><span data-stu-id="c645a-123">Create a Staging Table</span></span>  
 <span data-ttu-id="c645a-124">Der Partitionswechsel ist ein gängiger Partitionstask, wenn Sie über eine partitionierte Tabelle verfügen, in die bzw. aus der Sie regelmäßig Daten migrieren. Beispiel: Sie verfügen über eine partitionierte Tabelle, in der aktuelle vierteljährliche Daten gespeichert sind, und müssen zum Ende jedes Quartals alte Daten auslagern und neue Daten einfügen.</span><span class="sxs-lookup"><span data-stu-id="c645a-124">Partition switching is a common partitioning task if you have a partitioned table that you migrate data into and out of on a regular basis; for example, you have a partitioned table that stores current quarterly data, and you must move in new data and archive older data at the end of each quarter.</span></span>  
  
 <span data-ttu-id="c645a-125">Mithilfe des Assistenten können Sie die Stagingtabelle mit der gleichen Partitionsspalte, Tabelle und Spaltenstruktur sowie Indizes entwerfen. Die neue Tabelle wird in der Dateigruppe gespeichert, in der sich auch die Quellpartition befindet.</span><span class="sxs-lookup"><span data-stu-id="c645a-125">The wizard designs the staging table with the same partitioning column, table and column structure, and indexes, and stores the new table in the filegroup where your source partition is located.</span></span>  
  
 <span data-ttu-id="c645a-126">Wählen Sie **Stagingtabelle für den Partitionswechsel erstellen**, um eine Stagingtabelle zum Einfügen und Auslagern von Partitionsdaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c645a-126">To create a staging table to switch in or switch out partition data, select **Create a staging table for partition switching**.</span></span>  
  
### <a name="sliding-window-scenario"></a><span data-ttu-id="c645a-127">Szenario mit gleitendem Fenster</span><span class="sxs-lookup"><span data-stu-id="c645a-127">Sliding Window Scenario</span></span>  
 <span data-ttu-id="c645a-128">Um die Partitionen in einem flexiblen Fenster zu verwalten, wählen Sie **Partitionierte Daten in einem Szenario mit gleitendem Fenster verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c645a-128">To manage your partitions in a sliding-window scenario, select **Manage partitioned data in a sliding window scenario**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c645a-129">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c645a-129">UI element list</span></span>  
 <span data-ttu-id="c645a-130">**Stagingtabelle für den Partitionswechsel erstellen**</span><span class="sxs-lookup"><span data-stu-id="c645a-130">**Create a staging table for partition switching**</span></span>  
 <span data-ttu-id="c645a-131">Erstellt eine Stagingtabelle für die Daten, die Sie aus der vorhandenen partitionierten Tabelle auslagern bzw. darin einfügen.</span><span class="sxs-lookup"><span data-stu-id="c645a-131">Creates a staging table for the data you are switching in or switching out of the existing partitioned table.</span></span>  
  
 <span data-ttu-id="c645a-132">**Partition auslagern**</span><span class="sxs-lookup"><span data-stu-id="c645a-132">**Switch out partition**</span></span>  
 <span data-ttu-id="c645a-133">Stellt Optionen beim Entfernen einer Partition aus der Tabelle bereit.</span><span class="sxs-lookup"><span data-stu-id="c645a-133">Provides options when removing a partition from the table.</span></span>  
  
 <span data-ttu-id="c645a-134">**Partition einfügen**</span><span class="sxs-lookup"><span data-stu-id="c645a-134">**Switch in partition**</span></span>  
 <span data-ttu-id="c645a-135">Stellt Optionen beim Hinzufügen einer Partition zur Tabelle bereit.</span><span class="sxs-lookup"><span data-stu-id="c645a-135">Provides options when adding a partition to the table.</span></span>  
  
 <span data-ttu-id="c645a-136">**Partitionierte Daten in einem Szenario mit gleitendem Fenster verwalten**</span><span class="sxs-lookup"><span data-stu-id="c645a-136">**Manage partitioned data in a sliding window scenario**</span></span>  
 <span data-ttu-id="c645a-137">Fügt eine leere Partition an die vorhandene Tabelle an, die zum Einfügen und Auslagern von Daten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c645a-137">Appends an empty partition to the existing table that can be used for switching in data.</span></span> <span data-ttu-id="c645a-138">Der Assistent unterstützt derzeit das Einfügen in die letzte Partition und das Auslagern aus der ersten Partition.</span><span class="sxs-lookup"><span data-stu-id="c645a-138">The wizard currently supports switching into the last partition and switching out the first partition.</span></span>  
  
 <span data-ttu-id="c645a-139">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-139">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-in-options-page"></a><a name="SwitchIn"></a> <span data-ttu-id="c645a-140">Partitionseinfügeoptionen auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-140">Select Partition Switching-In Options Page</span></span>  
 <span data-ttu-id="c645a-141">Auf der Seite **Partitionseinfügeoptionen auswählen** können Sie die Stagingtabelle erstellen, die Sie in die partitionierte Tabelle einfügen.</span><span class="sxs-lookup"><span data-stu-id="c645a-141">Use the **Select Partition Switching-In options** page to select the staging table you are switching into the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c645a-142">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c645a-142">UI element list</span></span>  
 <span data-ttu-id="c645a-143">**Alle Partitionen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="c645a-143">**Show All Partitions**</span></span>  
 <span data-ttu-id="c645a-144">Wählen Sie diese Option zum Anzeigen aller Partitionen aus, einschließlich der Partitionen, die sich gegenwärtig in der partitionierten Tabelle befinden.</span><span class="sxs-lookup"><span data-stu-id="c645a-144">Select to show all partitions, including the partitions currently in the partitioned table.</span></span>  
  
 <span data-ttu-id="c645a-145">**Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="c645a-145">**Partition grid**</span></span>  
 <span data-ttu-id="c645a-146">Zeigt den Partitionsnamen, **Linke Begrenzung**, **Rechte Begrenzung**, **Dateigruppe**und **Zeilenanzahl** der Partitionen an, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c645a-146">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="c645a-147">**Einzufügende Tabelle**</span><span class="sxs-lookup"><span data-stu-id="c645a-147">**Switch in table**</span></span>  
 <span data-ttu-id="c645a-148">Wählen Sie die Stagingtabelle aus, die die Partition enthält, die Sie der partitionierten Tabelle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c645a-148">Select the staging table that contains the partition that you want to add to your partitioned table.</span></span> <span data-ttu-id="c645a-149">Sie müssen diese Stagingtabelle erstellen, bevor Sie Partitionen mit dem Assistenten zum **Verwalten von Partitionen**einfügen können.</span><span class="sxs-lookup"><span data-stu-id="c645a-149">You must create this staging table before you switch-in partitions with the **Manage PartitionsWizard**.</span></span>  
  
 <span data-ttu-id="c645a-150">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-150">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-partition-switching-out-options-page"></a><a name="SwitchOut"></a> <span data-ttu-id="c645a-151">Partitionsauslagerungsoptionen auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-151">Select Partition Switching-Out Options Page</span></span>  
 <span data-ttu-id="c645a-152">Auf der Seite **Partitionsauslagerungsoptionen auswählen** können Sie die Partition und die Stagingtabelle für die partitionierten Daten auswählen, die aus der partitionierten Tabelle ausgelagert werden.</span><span class="sxs-lookup"><span data-stu-id="c645a-152">Use the **Select Partition Switching-Out options** page to select the partition and the staging table to hold the partitioned data that you are switching out of the partitioned table.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c645a-153">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c645a-153">UI element list</span></span>  
 <span data-ttu-id="c645a-154">**Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="c645a-154">**Partition grid**</span></span>  
 <span data-ttu-id="c645a-155">Zeigt den Partitionsnamen, **Linke Begrenzung**, **Rechte Begrenzung**, **Dateigruppe**und **Zeilenanzahl** der Partitionen an, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c645a-155">Displays the partition name, **Left boundary**, **Right boundary**, **Filegroup**, and **Row count** of the partitions you selected.</span></span>  
  
 <span data-ttu-id="c645a-156">**Tabelle auslagern**</span><span class="sxs-lookup"><span data-stu-id="c645a-156">**Switch out table**</span></span>  
 <span data-ttu-id="c645a-157">Wählen Sie eine neue oder vorhandene Tabelle aus, in die Sie die Daten auslagern.</span><span class="sxs-lookup"><span data-stu-id="c645a-157">Choose a new table or an existing table to switch-out your data to.</span></span>  
  
 <span data-ttu-id="c645a-158">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c645a-158">**New**</span></span>  
 <span data-ttu-id="c645a-159">Geben Sie einen Namen für die neue Stagingtabelle ein, die zum Auslagern der Partition aus der aktuellen Quelltabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c645a-159">Enter a new name for the staging table you want to use for the partition to switch out of the current source table.</span></span>  
  
 <span data-ttu-id="c645a-160">**Vorhanden**</span><span class="sxs-lookup"><span data-stu-id="c645a-160">**Existing**</span></span>  
 <span data-ttu-id="c645a-161">Wählen Sie die vorhandene Stagingtabelle aus, die zum Auslagern der Partition aus der aktuellen Quelltabelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c645a-161">Select an existing staging table you want to use for the partition you want to switch out of the current source table.</span></span> <span data-ttu-id="c645a-162">Wenn die vorhandene Tabelle Daten enthält, werden diese mit den Daten überschrieben, die Sie auslagern.</span><span class="sxs-lookup"><span data-stu-id="c645a-162">If the existing table contains data, this data will be overwritten with the data you are switching out.</span></span>  
  
 <span data-ttu-id="c645a-163">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-the-staging-table-options-page"></a><a name="StagingTableOptions"></a> <span data-ttu-id="c645a-164">Stagingtabellenoptionen auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-164">Select the Staging Table Options Page</span></span>  
 <span data-ttu-id="c645a-165">Auf der Seite **Stagingtabellenoptionen auswählen** können Sie die Stagingtabelle erstellen, die zum Verschieben der partitionierten Daten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c645a-165">Use the **Select the Staging Table Options** page to create the staging table you want to use for switching your partitioned data.</span></span>  
  
 <span data-ttu-id="c645a-166">Stagingtabellen müssen sich in der gleichen Dateigruppe der ausgewählten Partition befinden, in der sich auch die Quelltabelle befindet.</span><span class="sxs-lookup"><span data-stu-id="c645a-166">Staging tables must reside in the same filegroup of the selected partition where the source table is located.</span></span> <span data-ttu-id="c645a-167">Der Entwurf der Stagingtabelle muss dem der Quell- und der Zieltabelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c645a-167">The staging table must mirror the design of both the source table and the destination table.</span></span>  
  
 <span data-ttu-id="c645a-168">Sie können auch in der Stagingtabelle die gleichen Indizes erstellen, die in der Quellpartition vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c645a-168">You can also create the same indexes in the staging table that exist in the source partition.</span></span> <span data-ttu-id="c645a-169">Die Stagingtabelle enthält automatisch eine Einschränkung auf Grundlage der Elemente der Quellpartition.</span><span class="sxs-lookup"><span data-stu-id="c645a-169">The staging table automatically contains a constraint based on the elements of the source partition.</span></span> <span data-ttu-id="c645a-170">Diese Einschränkung wird i. d. R. aus dem Begrenzungswert der Quellpartition generiert.</span><span class="sxs-lookup"><span data-stu-id="c645a-170">This constraint is typically generated from the boundary value of the source partition.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c645a-171">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c645a-171">UI element list</span></span>  
 <span data-ttu-id="c645a-172">**Stagingtabellenname**</span><span class="sxs-lookup"><span data-stu-id="c645a-172">**Staging table name**</span></span>  
 <span data-ttu-id="c645a-173">Erstellen Sie einen Namen für die Stagingtabelle, oder übernehmen Sie den im Eingabefeld angezeigten Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="c645a-173">Create a name for the staging table or accept the default name displayed in the edit box.</span></span>  
  
 <span data-ttu-id="c645a-174">**Partition wechseln**</span><span class="sxs-lookup"><span data-stu-id="c645a-174">**Switch partition**</span></span>  
 <span data-ttu-id="c645a-175">Wählen Sie die Quellpartition aus, die Sie aus der aktuellen Tabelle auslagern möchten.</span><span class="sxs-lookup"><span data-stu-id="c645a-175">Select the source partition that you want to switch out of the current table.</span></span>  
  
 <span data-ttu-id="c645a-176">**Neuer Begrenzungswert**</span><span class="sxs-lookup"><span data-stu-id="c645a-176">**New boundary value**</span></span>  
 <span data-ttu-id="c645a-177">Wählen Sie den gewünschten Begrenzungswert für die Partition in der Stagingtabelle aus, oder geben Sie einen Begrenzungswert ein.</span><span class="sxs-lookup"><span data-stu-id="c645a-177">Select or enter the boundary value you want for the partition in the staging table.</span></span>  
  
 <span data-ttu-id="c645a-178">**Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="c645a-178">**Filegroup**</span></span>  
 <span data-ttu-id="c645a-179">Wählen Sie eine Dateigruppe für die neue Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c645a-179">Select a filegroup for the new table.</span></span>  
  
 <span data-ttu-id="c645a-180">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-180">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="select-output-option-page"></a><a name="OutputOption"></a> <span data-ttu-id="c645a-181">Ausgabeoption auswählen (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-181">Select Output Option Page</span></span>  
 <span data-ttu-id="c645a-182">Geben Sie auf der Seite **Ausgabeoption auswählen** an, wie Sie die Änderungen für Ihre Partitionen abschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="c645a-182">Use the **Select Output Option** page to specify how you want to complete the modifications to your partitions.</span></span>  
  
### <a name="create-script"></a><span data-ttu-id="c645a-183">Erstellen von Skripts</span><span class="sxs-lookup"><span data-stu-id="c645a-183">Create Script</span></span>  
 <span data-ttu-id="c645a-184">Bei Abschluss des Assistenten wird im Abfrage-Editor ein Skript zum Ändern der Partitionen in der Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="c645a-184">When the wizard finishes, it creates a script in Query Editor to modify partitions in the table.</span></span> <span data-ttu-id="c645a-185">Wählen Sie **Skript erstellen** aus, wenn Sie das Skript überprüfen möchten, und führen Sie das Skript dann manuell aus.</span><span class="sxs-lookup"><span data-stu-id="c645a-185">Select **Create Script** if you want to review the script, and then execute the script manually.</span></span>  
  
 <span data-ttu-id="c645a-186">**Skript in Datei schreiben**</span><span class="sxs-lookup"><span data-stu-id="c645a-186">**Script to file**</span></span>  
 <span data-ttu-id="c645a-187">Generiert das Skript in einer SQL-Datei.</span><span class="sxs-lookup"><span data-stu-id="c645a-187">Generate the script to a .sql file.</span></span> <span data-ttu-id="c645a-188">Geben Sie entweder **Unicode** oder **ANSI-Text**an.</span><span class="sxs-lookup"><span data-stu-id="c645a-188">Specify either **Unicode** or **ANSI text**.</span></span> <span data-ttu-id="c645a-189">Klicken Sie auf **Durchsuchen**, um einen Namen und einen Speicherort für die Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c645a-189">To specify a name and location for the file, click **Browse**.</span></span>  
  
 <span data-ttu-id="c645a-190">**Skript in Zwischenablage schreiben**</span><span class="sxs-lookup"><span data-stu-id="c645a-190">**Script to Clipboard**</span></span>  
 <span data-ttu-id="c645a-191">Speichert das Skript in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="c645a-191">Save the script to the Clipboard.</span></span>  
  
 <span data-ttu-id="c645a-192">**Skript in Fenster "Neue Abfrage" schreiben**</span><span class="sxs-lookup"><span data-stu-id="c645a-192">**Script to New Query Window**</span></span>  
 <span data-ttu-id="c645a-193">Generiert das Skript in einem Abfrage-Editor-Fenster.</span><span class="sxs-lookup"><span data-stu-id="c645a-193">Generate the script to a Query Editor window.</span></span> <span data-ttu-id="c645a-194">Wenn kein Editor-Fenster geöffnet ist, wird ein neues Editor-Fenster als Skriptziel geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c645a-194">If no editor window is open, a new editor window opens as the target for the script.</span></span>  
  
### <a name="run-immediately"></a><span data-ttu-id="c645a-195">Sofort ausführen</span><span class="sxs-lookup"><span data-stu-id="c645a-195">Run Immediately</span></span>  
 <span data-ttu-id="c645a-196">**Run immediately**</span><span class="sxs-lookup"><span data-stu-id="c645a-196">**Run immediately**</span></span>  
 <span data-ttu-id="c645a-197">Wenn Sie auf **Weiter** oder **Fertig stellen**klicken, schließt der Assistent die Änderungen an den Partitionen ab.</span><span class="sxs-lookup"><span data-stu-id="c645a-197">Have the wizard finish modifications to the partitions when you click **Next** or **Finish**.</span></span>  
  
### <a name="schedule"></a><span data-ttu-id="c645a-198">Zeitplan</span><span class="sxs-lookup"><span data-stu-id="c645a-198">Schedule</span></span>  
 <span data-ttu-id="c645a-199">Wählen Sie diese Option aus, um die Tabellenpartitionen zu einem geplanten Datum und einer geplanten Uhrzeit zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c645a-199">Select to modify the table partitions at a scheduled date and time.</span></span>  
  
 <span data-ttu-id="c645a-200">**Zeitplan ändern**</span><span class="sxs-lookup"><span data-stu-id="c645a-200">**Change schedule**</span></span>  
 <span data-ttu-id="c645a-201">Hiermit wird das Dialogfeld **Neuer Auftragszeitplan** geöffnet, in dem Sie die Eigenschaften des geplanten Auftrags auswählen, ändern oder anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c645a-201">Opens the **New Job Schedule** dialog box, where you can select, change, or view the properties of the scheduled job.</span></span>  
  
 <span data-ttu-id="c645a-202">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-202">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="new-job-schedule-page"></a><a name="NewJob"></a> <span data-ttu-id="c645a-203">Neuer Auftragszeitplan (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-203">New Job Schedule Page</span></span>  
 <span data-ttu-id="c645a-204">Verwenden Sie die Seite **Neuer Auftragszeitplan** , um die Eigenschaften des Zeitplans anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c645a-204">Use the **New Job Schedule** page to view and change the properties of the schedule.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c645a-205">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c645a-205">Options</span></span>  
 <span data-ttu-id="c645a-206">Wählen Sie den Typ des gewünschten Zeitplans für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="c645a-206">Select the type of schedule you want for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
 <span data-ttu-id="c645a-207">**Name**</span><span class="sxs-lookup"><span data-stu-id="c645a-207">**Name**</span></span>  
 <span data-ttu-id="c645a-208">Geben Sie einen neuen Namen für den Zeitplan ein.</span><span class="sxs-lookup"><span data-stu-id="c645a-208">Type a new name for the schedule.</span></span>  
  
 <span data-ttu-id="c645a-209">**Aufträge im Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="c645a-209">**Jobs in schedule**</span></span>  
 <span data-ttu-id="c645a-210">Zeigen Sie die vorhandenen Aufträge an, die den Zeitplan verwenden.</span><span class="sxs-lookup"><span data-stu-id="c645a-210">View the existing jobs that use the schedule.</span></span>  
  
 <span data-ttu-id="c645a-211">**Zeitplantyp**</span><span class="sxs-lookup"><span data-stu-id="c645a-211">**Schedule type**</span></span>  
 <span data-ttu-id="c645a-212">Wählen Sie den Zeitplantyp aus.</span><span class="sxs-lookup"><span data-stu-id="c645a-212">Select the type of schedule.</span></span>  
  
 <span data-ttu-id="c645a-213">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="c645a-213">**Enabled**</span></span>  
 <span data-ttu-id="c645a-214">Aktivieren oder deaktivieren Sie den Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="c645a-214">Enable or disable the schedule.</span></span>  
  
### <a name="recurring-schedule-types-options"></a><span data-ttu-id="c645a-215">Zeitplantypoptionen für wiederkehrende Aufträge</span><span class="sxs-lookup"><span data-stu-id="c645a-215">Recurring Schedule Types Options</span></span>  
 <span data-ttu-id="c645a-216">Wählen Sie die Häufigkeit des geplanten Auftrags aus.</span><span class="sxs-lookup"><span data-stu-id="c645a-216">Select the frequency of the scheduled job.</span></span>  
  
 <span data-ttu-id="c645a-217">**Tritt auf**</span><span class="sxs-lookup"><span data-stu-id="c645a-217">**Occurs**</span></span>  
 <span data-ttu-id="c645a-218">Wählen Sie das Intervall aus, nach dem der Zeitplan wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-218">Select the interval at which the schedule recurs.</span></span>  
  
 <span data-ttu-id="c645a-219">**Wiederholen alle**</span><span class="sxs-lookup"><span data-stu-id="c645a-219">**Recurs every**</span></span>  
 <span data-ttu-id="c645a-220">Wählen Sie die Anzahl der Tage oder Wochen aus, die zwischen der wiederholten Ausführung des Zeitplans liegen.</span><span class="sxs-lookup"><span data-stu-id="c645a-220">Select the number of days or weeks between recurrences of the schedule.</span></span> <span data-ttu-id="c645a-221">Bei monatlichen Zeitplänen ist diese Option nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-221">This option is not available for monthly schedules.</span></span>  
  
 <span data-ttu-id="c645a-222">**Montag**</span><span class="sxs-lookup"><span data-stu-id="c645a-222">**Monday**</span></span>  
 <span data-ttu-id="c645a-223">Legt fest, dass der Auftrag an einem Montag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-223">Set the job to occur on a Monday.</span></span> <span data-ttu-id="c645a-224">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-224">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-225">**Dienstag**</span><span class="sxs-lookup"><span data-stu-id="c645a-225">**Tuesday**</span></span>  
 <span data-ttu-id="c645a-226">Legt fest, dass der Auftrag an einem Dienstag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-226">Set the job to occur on a Tuesday.</span></span> <span data-ttu-id="c645a-227">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-227">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-228">**Mittwoch**</span><span class="sxs-lookup"><span data-stu-id="c645a-228">**Wednesday**</span></span>  
 <span data-ttu-id="c645a-229">Legt fest, dass der Auftrag an einem Mittwoch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-229">Set the job to occur on a Wednesday.</span></span> <span data-ttu-id="c645a-230">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-230">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-231">**Donnerstag**</span><span class="sxs-lookup"><span data-stu-id="c645a-231">**Thursday**</span></span>  
 <span data-ttu-id="c645a-232">Legt fest, dass der Auftrag an einem Donnerstag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c645a-232">Set the job to occur on a Thursday.</span></span> <span data-ttu-id="c645a-233">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-233">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-234">**Freitag**</span><span class="sxs-lookup"><span data-stu-id="c645a-234">**Friday**</span></span>  
 <span data-ttu-id="c645a-235">Legt fest, dass der Auftrag an einem Freitag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c645a-235">Set the job to occur on a Friday.</span></span> <span data-ttu-id="c645a-236">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-236">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-237">**Samstag**</span><span class="sxs-lookup"><span data-stu-id="c645a-237">**Saturday**</span></span>  
 <span data-ttu-id="c645a-238">Legt fest, dass der Auftrag an einem Samstag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c645a-238">Set the job to occur on a Saturday.</span></span> <span data-ttu-id="c645a-239">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-239">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-240">**Sonntag**</span><span class="sxs-lookup"><span data-stu-id="c645a-240">**Sunday**</span></span>  
 <span data-ttu-id="c645a-241">Legt fest, dass der Auftrag an einem Sonntag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c645a-241">Set the job to occur on a Sunday.</span></span> <span data-ttu-id="c645a-242">Nur bei wöchentlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-242">Only available for weekly schedules.</span></span>  
  
 <span data-ttu-id="c645a-243">**Day**</span><span class="sxs-lookup"><span data-stu-id="c645a-243">**Day**</span></span>  
 <span data-ttu-id="c645a-244">Wählen Sie den Tag des Monats aus, an dem der Zeitplan ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c645a-244">Select the day of the month the schedule occurs.</span></span> <span data-ttu-id="c645a-245">Nur bei monatlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-245">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="c645a-246">**alle**</span><span class="sxs-lookup"><span data-stu-id="c645a-246">**of every**</span></span>  
 <span data-ttu-id="c645a-247">Wählen Sie die Anzahl der Monate aus, die zwischen wiederholten Ausführungen des Zeitplans liegen sollen.</span><span class="sxs-lookup"><span data-stu-id="c645a-247">Select the number of months between occurrences of the schedule.</span></span> <span data-ttu-id="c645a-248">Nur bei monatlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-248">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="c645a-249">**Am**</span><span class="sxs-lookup"><span data-stu-id="c645a-249">**The**</span></span>  
 <span data-ttu-id="c645a-250">Geben Sie einen Zeitplan für den Wochentag einer bestimmten Woche des Monats an.</span><span class="sxs-lookup"><span data-stu-id="c645a-250">Specify a schedule for a specific day of the week on a specific week within the month.</span></span> <span data-ttu-id="c645a-251">Nur bei monatlichen Zeitplänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c645a-251">Only available for monthly schedules.</span></span>  
  
 <span data-ttu-id="c645a-252">**Einmalig um**</span><span class="sxs-lookup"><span data-stu-id="c645a-252">**Occurs once at**</span></span>  
 <span data-ttu-id="c645a-253">Legen Sie die Uhrzeit für einen täglich auszuführenden Auftrag fest.</span><span class="sxs-lookup"><span data-stu-id="c645a-253">Set the time for a job to occur daily.</span></span>  
  
 <span data-ttu-id="c645a-254">**Alle**</span><span class="sxs-lookup"><span data-stu-id="c645a-254">**Occurs every**</span></span>  
 <span data-ttu-id="c645a-255">Legt die Anzahl von Stunden und Minuten zwischen den Ausführungen fest.</span><span class="sxs-lookup"><span data-stu-id="c645a-255">Set the number of hours or minutes between occurrences.</span></span>  
  
 <span data-ttu-id="c645a-256">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="c645a-256">**Start date**</span></span>  
 <span data-ttu-id="c645a-257">Legt fest, ab welchem Datum dieser Zeitplan gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c645a-257">Set the date when this schedule will become effective.</span></span>  
  
 <span data-ttu-id="c645a-258">**Enddatum**</span><span class="sxs-lookup"><span data-stu-id="c645a-258">**End date**</span></span>  
 <span data-ttu-id="c645a-259">Legen Sie fest, ab welchem Datum der Zeitplan nicht mehr gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c645a-259">Set the date when the schedule will no longer be effective.</span></span>  
  
 <span data-ttu-id="c645a-260">**Kein Enddatum**</span><span class="sxs-lookup"><span data-stu-id="c645a-260">**No end date**</span></span>  
 <span data-ttu-id="c645a-261">Geben Sie an, dass der Zeitplan für unbestimmte Zeit gültig bleibt.</span><span class="sxs-lookup"><span data-stu-id="c645a-261">Specify that the schedule will remain effective indefinitely.</span></span>  
  
### <a name="one-time-schedule-types-options"></a><span data-ttu-id="c645a-262">Zeitplantypoptionen für einmalige Aufträge</span><span class="sxs-lookup"><span data-stu-id="c645a-262">One Time Schedule Types Options</span></span>  
 <span data-ttu-id="c645a-263">Wenn ein Zeitplan nur einmalig ausgeführt werden soll, müssen Sie ein Datum und eine Uhrzeit in der Zukunft auswählen.</span><span class="sxs-lookup"><span data-stu-id="c645a-263">If you schedule a job to run once, you must select a date and time in the future.</span></span>  
  
 <span data-ttu-id="c645a-264">**Date**</span><span class="sxs-lookup"><span data-stu-id="c645a-264">**Date**</span></span>  
 <span data-ttu-id="c645a-265">Wählen Sie das Datum aus, an dem der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-265">Select the date for the job to run.</span></span>  
  
 <span data-ttu-id="c645a-266">**Time**</span><span class="sxs-lookup"><span data-stu-id="c645a-266">**Time**</span></span>  
 <span data-ttu-id="c645a-267">Wählen Sie die Uhrzeit aus, zu der der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c645a-267">Select the time for the job to run.</span></span>  
  
 <span data-ttu-id="c645a-268">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-268">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="c645a-269">Seite "Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="c645a-269">Summary Page</span></span>  
 <span data-ttu-id="c645a-270">Mithilfe der Seite **Zusammenfassung** können Sie die Optionen überprüfen, die Sie auf den vorherigen Seiten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="c645a-270">Use the **Summary** page to review the options that you have selected on the previous pages.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c645a-271">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="c645a-271">UI element list</span></span>  
 <span data-ttu-id="c645a-272">**Überprüfen Sie Ihre Auswahl**</span><span class="sxs-lookup"><span data-stu-id="c645a-272">**Review your selections**</span></span>  
 <span data-ttu-id="c645a-273">Zeigt die auf den einzelnen Seiten des Assistenten getroffene Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="c645a-273">Displays the selections you have made for each page of the wizard.</span></span> <span data-ttu-id="c645a-274">Klicken Sie auf einen Knoten, um diesen zu erweitern und die ausgewählten Optionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c645a-274">Click a node to expand and view your previously selected options.</span></span>  
  
 <span data-ttu-id="c645a-275">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-275">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="c645a-276">Status (Seite)</span><span class="sxs-lookup"><span data-stu-id="c645a-276">Progress Page</span></span>  
 <span data-ttu-id="c645a-277">Auf der Seite **Status** können Sie Statusinformationen zu den Aktionen im **Assistenten zum Verwalten von Partitionen**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c645a-277">Use the **Progress** page to monitor status information about the actions of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="c645a-278">Je nach den im Assistenten ausgewählten Optionen enthält die Seite **Status** eine oder mehrere Aktionen.</span><span class="sxs-lookup"><span data-stu-id="c645a-278">Depending on the options that you selected in the wizard, the **Progress** page might contain one or more actions.</span></span> <span data-ttu-id="c645a-279">Im oberen Feld werden der Gesamtstatus des Assistenten und die Anzahl der empfangenen Status-, Fehler- und Warnmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c645a-279">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
### <a name="options"></a><span data-ttu-id="c645a-280">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c645a-280">Options</span></span>  
 <span data-ttu-id="c645a-281">**Details**</span><span class="sxs-lookup"><span data-stu-id="c645a-281">**Details**</span></span>  
 <span data-ttu-id="c645a-282">Stellt für jede vom Assistenten ausgeführte Aktion Informationen zur Aktion, zum Status und zu den zurückgegebenen Meldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="c645a-282">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
 <span data-ttu-id="c645a-283">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="c645a-283">**Action**</span></span>  
 <span data-ttu-id="c645a-284">Gibt den Typ und den Namen jeder Aktion an.</span><span class="sxs-lookup"><span data-stu-id="c645a-284">Specifies the type and name of each action.</span></span>  
  
 <span data-ttu-id="c645a-285">**Status**</span><span class="sxs-lookup"><span data-stu-id="c645a-285">**Status**</span></span>  
 <span data-ttu-id="c645a-286">Gibt an, ob für die Aktion des Assistenten insgesamt der Wert **Erfolg** oder der Wert **Fehler**zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c645a-286">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
 <span data-ttu-id="c645a-287">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="c645a-287">**Message**</span></span>  
 <span data-ttu-id="c645a-288">Stellt alle vom Prozess zurückgegebenen Fehler- oder Warnmeldungen bereit.</span><span class="sxs-lookup"><span data-stu-id="c645a-288">Provides any error or warning messages that are returned from the process.</span></span>  
  
 <span data-ttu-id="c645a-289">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="c645a-289">**Stop**</span></span>  
 <span data-ttu-id="c645a-290">Beendet die Aktion des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c645a-290">Stop the action of the wizard.</span></span>  
  
 <span data-ttu-id="c645a-291">**Report**</span><span class="sxs-lookup"><span data-stu-id="c645a-291">**Report**</span></span>  
 <span data-ttu-id="c645a-292">Dient zum Erstellen eines Berichts mit den Ergebnissen des **Assistenten zum Verwalten von Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="c645a-292">Create a report that contains the results of the **Manage Partition Wizard**.</span></span> <span data-ttu-id="c645a-293">Die Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="c645a-293">The options are:</span></span>  
  
-   <span data-ttu-id="c645a-294">**Bericht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="c645a-294">**View Report**</span></span>  
  
-   <span data-ttu-id="c645a-295">**Bericht in Datei speichern**</span><span class="sxs-lookup"><span data-stu-id="c645a-295">**Save Report to File**</span></span>  
  
-   <span data-ttu-id="c645a-296">**Bericht in Zwischenablage kopieren**</span><span class="sxs-lookup"><span data-stu-id="c645a-296">**Copy Report to Clipboard**</span></span>  
  
-   <span data-ttu-id="c645a-297">**Bericht als E-Mail senden**</span><span class="sxs-lookup"><span data-stu-id="c645a-297">**Send Report as Email**</span></span>  
  
 <span data-ttu-id="c645a-298">**Bericht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="c645a-298">**View Report**</span></span>  
 <span data-ttu-id="c645a-299">Öffnet das Dialogfeld **Bericht anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="c645a-299">Open the **View Report** dialog box.</span></span> <span data-ttu-id="c645a-300">Dieses Dialogfeld enthält einen Textbericht zum Status des **Assistenten zum Verwalten von Partitionen**.</span><span class="sxs-lookup"><span data-stu-id="c645a-300">This dialog box contains a text report of the progress of the **Manage Partition Wizard**.</span></span>  
  
 <span data-ttu-id="c645a-301">**Close**</span><span class="sxs-lookup"><span data-stu-id="c645a-301">**Close**</span></span>  
 <span data-ttu-id="c645a-302">Schließen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c645a-302">Close the wizard.</span></span>  
  
 <span data-ttu-id="c645a-303">![Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [In diesem Abschnitt](#Top)</span><span class="sxs-lookup"><span data-stu-id="c645a-303">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [In This Section](#Top)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c645a-304">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c645a-304">See Also</span></span>  
 [<span data-ttu-id="c645a-305">Partitionierte Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="c645a-305">Partitioned Tables and Indexes</span></span>](partitioned-tables-and-indexes.md)  
  
  
