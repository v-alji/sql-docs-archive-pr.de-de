---
title: Anzeigen oder Ändern von Sammlungssatz-Zeitplänen (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.collectionsetprop.uploads.f1
- sql12.swb.dc.collectionsetprop.general.f1
- sql12.swb.dc.collectionsetprop.description.f1
helpviewer_keywords:
- collection sets [SQL Server], changing schedules
- schedules [SQL Server], changing collection set
- collection sets [SQL Server], viewing schedules
- schedules [SQL Server], viewing collection set
ms.assetid: 26336c98-78c5-414f-8d6a-574fc3af60c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2eb1acf0346b3e16bd1d54829abbc070e1d9d63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621009"
---
# <a name="view-or-change-collection-set-schedules-sql-server-management-studio"></a><span data-ttu-id="bd455-102">Anzeigen oder Ändern von Sammlungssatz-Zeitplänen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bd455-102">View or Change Collection Set Schedules (SQL Server Management Studio)</span></span>
  <span data-ttu-id="bd455-103">Sie können Zeitpläne für den Sammlungssatz mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="bd455-103">You can view or change collection set schedules by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="bd455-104">Der Auflistmodus (mit oder ohne Zwischenspeicherung) bestimmt, wie Sie Änderungen an einem Zeitplan vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="bd455-104">The collection mode, cached or non-cached, determines how you can make changes to a schedule.</span></span> <span data-ttu-id="bd455-105">Der Modus mit Zwischenspeicherung verwendet separate Zeitpläne für Sammlung und Hochladen.</span><span class="sxs-lookup"><span data-stu-id="bd455-105">Cached mode uses separate schedules for collection and upload.</span></span> <span data-ttu-id="bd455-106">Der Modus ohne Zwischenspeicherung verwendet für Sammlung und Hochladen denselben Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="bd455-106">Non-cached mode uses the same schedule for collection and upload.</span></span> <span data-ttu-id="bd455-107">Die einzelnen Systemdaten-Sammlungssätze weisen den folgenden Auflistmodustyp auf:</span><span class="sxs-lookup"><span data-stu-id="bd455-107">The type of collection mode for each of the System Datacollection sets is as follows:</span></span>  
  
-   <span data-ttu-id="bd455-108">Die**Datenträgerverwendung** verwendet den Auflistmodus ohne Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="bd455-108">**Disk Usage** uses non-cached collection mode.</span></span>  
  
-   <span data-ttu-id="bd455-109">Die**Abfragestatistik** verwendet den Auflistmodus mit Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="bd455-109">**Query Statistics** uses cached collection mode.</span></span>  
  
-   <span data-ttu-id="bd455-110">Die**Serveraktivität** verwendet den Auflistmodus mit Zwischenspeicherung.</span><span class="sxs-lookup"><span data-stu-id="bd455-110">**Server Activity** uses cached collection mode.</span></span>  
  
### <a name="to-view-collection-set-schedules"></a><span data-ttu-id="bd455-111">So zeigen Sie Sammlungssatz-Zeitpläne an</span><span class="sxs-lookup"><span data-stu-id="bd455-111">To view collection set schedules</span></span>  
  
1.  <span data-ttu-id="bd455-112">Erweitern Sie im Objekt-Explorer nacheinander die Knoten **Verwaltung** , **Datensammlung**und dann **Systemdaten-Sammlungssätze**.</span><span class="sxs-lookup"><span data-stu-id="bd455-112">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="bd455-113">Klicken Sie mit der rechten Maustaste auf einen Sammlungssatznamen, und klicken Sie anschließend auf **Eigenschaften** , um das Dialogfeld [Eigenschaften für Datensammlungssätze](#CollectionSet) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd455-113">Right-click a collection set name, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
### <a name="to-change-the-schedules-for-a-cached-mode-collection-set"></a><span data-ttu-id="bd455-114">So ändern Sie die Zeitpläne für einen Sammlungssatz im Modus mit Zwischenspeicherung</span><span class="sxs-lookup"><span data-stu-id="bd455-114">To change the schedules for a cached mode collection set</span></span>  
  
1.  <span data-ttu-id="bd455-115">Erweitern Sie im Objekt-Explorer nacheinander die Knoten **Verwaltung** , **Datensammlung**und dann **Systemdaten-Sammlungssätze**.</span><span class="sxs-lookup"><span data-stu-id="bd455-115">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="bd455-116">Klicken Sie mit der rechten Maustaste auf einen Sammlungssatz, der den Modus mit Zwischenspeicherung verwendet, beispielsweise **Abfragestatistik**, und klicken Sie dann auf **Eigenschaften** , um das Dialogfeld [Eigenschaften für Datensammlungssätze](#CollectionSet) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd455-116">Right-click a collection set that uses cached mode, such as **Query Statistics**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
3.  <span data-ttu-id="bd455-117">Sie können die Sammelhäufigkeit auf der Seite **Allgemein** ändern.</span><span class="sxs-lookup"><span data-stu-id="bd455-117">You can change the collection frequency on the **General** page.</span></span> <span data-ttu-id="bd455-118">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="bd455-118">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bd455-119">Doppelklicken Sie im Detailbereich auf die Zahl, die in der Tabelle **Sammelelemente** für die Spalte **Sammelhäufigkeit (Sek)** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bd455-119">In the details pane, double-click the number that is displayed for the **Collection Frequency (sec)** column in the **Collection items** table.</span></span>  
  
    2.  <span data-ttu-id="bd455-120">Erhöhen oder verringern Sie die Sammelhäufigkeit, indem Sie eine niedrigere oder eine höhere Zahl eingeben, und drücken Sie die EINGABETASTE, um den neuen Wert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bd455-120">To increase or decrease the collection frequency, type a lower or higher number, and then press ENTER to store the new value.</span></span>  
  
4.  <span data-ttu-id="bd455-121">Um den vorhandenen Uploadzeitplan für den Sammlungssatz zu ändern, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bd455-121">To change the existing upload schedule for the collection set, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="bd455-122">Klicken Sie auf die Seite **Uploads** .</span><span class="sxs-lookup"><span data-stu-id="bd455-122">Click the **Uploads** page.</span></span>  
  
    2.  <span data-ttu-id="bd455-123">Doppelklicken Sie im Detailbereich auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bd455-123">In the details pane, click **Pick**.</span></span>  
  
         <span data-ttu-id="bd455-124">Das Dialogfeld **Zeitplan für Auftrag auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bd455-124">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="bd455-125">Die verfügbaren Zeitpläne werden als Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd455-125">The available schedules appear as a table.</span></span>  
  
    3.  <span data-ttu-id="bd455-126">Klicken Sie auf die Zeile mit dem gewünschten Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="bd455-126">Click the row with the schedule that you want.</span></span> <span data-ttu-id="bd455-127">Um beispielsweise den Zeitplan in alle 5 Minuten zu ändern, klicken Sie auf die Zeile mit dem Zeitplannamen **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="bd455-127">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min.**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bd455-128">Sie können die Eigenschaften des ausgewählten Zeitplans anzeigen und bearbeiten, indem Sie auf **Eigenschaften** klicken, um das Dialogfeld **Eigenschaften des Auftragszeitplans** für diesen Zeitplan zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd455-128">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="bd455-129">In diesem Dialogfeld können Sie Zeitplaninformationen wie beispielsweise die Häufigkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="bd455-129">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
        >   
        >  <span data-ttu-id="bd455-130">Als Alternative zum Ändern eines vorhandenen Zeitplans können Sie einen neuen Uploadzeitplan erstellen. Klicken Sie dazu auf der Seite **Uploads** auf **Neu** .</span><span class="sxs-lookup"><span data-stu-id="bd455-130">As an alternative to modifying an existing schedule, you can create a new upload schedule by clicking **New** on the **Uploads** page.</span></span> <span data-ttu-id="bd455-131">Durch diese Aktion wird das Dialogfeld **Neuer Auftragszeitplan** geöffnet, das Sie verwenden können, um einen benutzerdefinierten Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd455-131">This action opens the **New Job Schedule** dialog box, which you can use to create a custom schedule.</span></span>  
  
    4.  <span data-ttu-id="bd455-132">Wenn Sie die Konfiguration des Zeitplans abgeschlossen haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd455-132">When you are finished configuring the schedule, click **OK**.</span></span>  
  
         <span data-ttu-id="bd455-133">Die vorgenommenen Änderungen werden auf der Seite **Uploads** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd455-133">The changes that you made appear on the **Uploads** page.</span></span>  
  
5.  <span data-ttu-id="bd455-134">Klicken Sie auf **OK** , um die Änderungen der Sammelhäufigkeit und des Uploadzeitplans zu speichern und um das Dialogfeld **Eigenschaften für Datensammlungssätze** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bd455-134">Click **OK** to save the changes to the collection frequency and the upload schedule, and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
### <a name="to-change-the-schedule-for-a-non-cached-mode-collection-set"></a><span data-ttu-id="bd455-135">So ändern Sie den Zeitplan für einen Sammlungssatz im Modus ohne Zwischenspeicherung</span><span class="sxs-lookup"><span data-stu-id="bd455-135">To change the schedule for a non-cached mode collection set</span></span>  
  
1.  <span data-ttu-id="bd455-136">Erweitern Sie im Objekt-Explorer nacheinander die Knoten **Verwaltung** , **Datensammlung**und dann **Systemdaten-Sammlungssätze**.</span><span class="sxs-lookup"><span data-stu-id="bd455-136">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="bd455-137">Klicken Sie mit der rechten Maustaste auf einen Sammlungssatz, der den Modus ohne Zwischenspeicherung verwendet, beispielsweise **Datenträgerverwendung**, und klicken Sie dann auf **Eigenschaften** , um das Dialogfeld [Eigenschaften für Datensammlungssätze](#CollectionSet) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd455-137">Right-click a collection set that uses non-cached mode, such as **Disk Usage**, and then click **Properties** to open the [Data Collection Set Properties](#CollectionSet) dialog box.</span></span>  
  
     <span data-ttu-id="bd455-138">Das Dialogfeld **Eigenschaften für Datensammlungssätze** zeigt eine Ansicht im Seitenformat mit den Eigenschaften für Sammlungssätze an.</span><span class="sxs-lookup"><span data-stu-id="bd455-138">The **Data Collection Set Properties** dialog box displays a paged view of the collection set properties.</span></span>  
  
3.  <span data-ttu-id="bd455-139">Klicken Sie auf **Auswählen**, um den Zeitplan für den Sammlungssatz festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bd455-139">To change the schedule for the collection set, click **Pick**.</span></span>  
  
     <span data-ttu-id="bd455-140">Das Dialogfeld **Zeitplan für Auftrag auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bd455-140">The **Pick Schedule for Job** dialog box opens.</span></span> <span data-ttu-id="bd455-141">Die verfügbaren Zeitpläne werden als Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd455-141">The available schedules are displayed as a table.</span></span>  
  
4.  <span data-ttu-id="bd455-142">Klicken Sie auf die Zeile mit dem gewünschten Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="bd455-142">Click the row with the schedule that you want.</span></span> <span data-ttu-id="bd455-143">Um beispielsweise den Zeitplan in alle 5 Minuten zu ändern, klicken Sie auf die Zeile mit dem Zeitplannamen **CollectorSchedule_Every_5min**.</span><span class="sxs-lookup"><span data-stu-id="bd455-143">For example, to change the schedule to every 5 minutes, click the row where the schedule name is **CollectorSchedule_Every_5min**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bd455-144">Sie können die Eigenschaften des ausgewählten Zeitplans anzeigen und bearbeiten, indem Sie auf **Eigenschaften** klicken, um das Dialogfeld **Eigenschaften des Auftragszeitplans** für diesen Zeitplan zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bd455-144">You can view and edit the properties for the selected schedule by clicking **Properties** to open the **Job Schedule Properties** dialog box for the schedule.</span></span> <span data-ttu-id="bd455-145">In diesem Dialogfeld können Sie Zeitplaninformationen wie beispielsweise die Häufigkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="bd455-145">You can use this dialog box to change schedule information, such as the frequency.</span></span>  
    >   
    >  <span data-ttu-id="bd455-146">Als Alternative zum Ändern eines vorhandenen Zeitplans können Sie einen neuen Sammlungs- und Uploadzeitplan erstellen. Klicken Sie dazu auf der Seite **Allgemein** auf **Neu** .</span><span class="sxs-lookup"><span data-stu-id="bd455-146">As an alternative to modifying an existing schedule, you can create a new collect and upload schedule by clicking **New** on the **General** page.</span></span> <span data-ttu-id="bd455-147">Mit dieser Aktion wird das Dialogfeld **Neuer Auftragszeitplan** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bd455-147">This action opens the **New Job Schedule** dialog box.</span></span>  
  
5.  <span data-ttu-id="bd455-148">Wenn Sie die Konfiguration des Zeitplans abgeschlossen haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd455-148">When you are finished configuring the schedule, click **OK**.</span></span>  
  
6.  <span data-ttu-id="bd455-149">Klicken Sie auf **OK** , um die Änderungen zu speichern und das Dialogfeld **Eigenschaften für Datensammlungssätze** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bd455-149">Click **OK** to save the changes and to close the **Data Collection Set Properties** dialog box.</span></span>  
  
####  <a name="data-collection-set-properties-dialog-box"></a><a name="CollectionSet"></a> <span data-ttu-id="bd455-150">Eigenschaften für Datensammlungssätze (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="bd455-150">Data Collection Set Properties Dialog Box</span></span>  
 <span data-ttu-id="bd455-151">**Seite Allgemein**</span><span class="sxs-lookup"><span data-stu-id="bd455-151">**General Page**</span></span>  
  
 <span data-ttu-id="bd455-152">Auf dieser Seite können Sie konfigurieren, wie Daten aufgelistet und hochgeladen werden. Zudem können Sie Zeitpläne und Aufbewahrungsdauern für Daten im Verwaltungs-Data Warehouse konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bd455-152">Use this page to configure how data is collected and uploaded, configure schedules, and configure data retention periods in the management data warehouse.</span></span> <span data-ttu-id="bd455-153">Darüber hinaus stehen auf dieser Seite Informationen zu Sammlungssätzen, z. B. Sammlertypen und Sammlungshäufigkeiten, sowie die für einen Sammlungssatz verwendeten Eingabeparameter zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd455-153">This page also provides information about collection sets, such as collector types and collection frequencies, as well as the input parameters that are used for a collection set.</span></span>  
  
 <span data-ttu-id="bd455-154">**Name**</span><span class="sxs-lookup"><span data-stu-id="bd455-154">**Name**</span></span>  
 <span data-ttu-id="bd455-155">Zeigt den Namen des Sammlungssatzes an, auf den diese Seite verweist.</span><span class="sxs-lookup"><span data-stu-id="bd455-155">Displays the name of the collection set that this page refers to.</span></span>  
  
 <span data-ttu-id="bd455-156">**Datensammlung und -upload**</span><span class="sxs-lookup"><span data-stu-id="bd455-156">**Data collection and upload**</span></span>  
 <span data-ttu-id="bd455-157">Gibt an, wie Daten aufgelistet und in das Verwaltungs-Data Warehouse hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="bd455-157">Specifies how data is collected and uploaded to the management data warehouse.</span></span> <span data-ttu-id="bd455-158">Wählen Sie eine der folgenden Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="bd455-158">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd455-159">**Nicht zwischengespeichert. Für Datensammlung und -upload wird derselbe Zeitplan verwendet.**</span><span class="sxs-lookup"><span data-stu-id="bd455-159">**Non-cached. Collection and data upload on the same schedule.**</span></span>|<span data-ttu-id="bd455-160">Wenn diese Option aktiviert ist, geben Sie einen der folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="bd455-160">When selected, specify one of the following:</span></span><br /><br /> <span data-ttu-id="bd455-161">**Bedarfsgesteuert**.</span><span class="sxs-lookup"><span data-stu-id="bd455-161">**On-demand**.</span></span> <span data-ttu-id="bd455-162">Daten werden nach Bedarf aufgelistet und hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="bd455-162">Data is collected and uploaded on demand.</span></span><br /><br /> <span data-ttu-id="bd455-163">**Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="bd455-163">**Schedule**.</span></span> <span data-ttu-id="bd455-164">Daten werden nach einem Zeitplan aufgelistet und hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="bd455-164">Data is collected and uploaded according to a schedule.</span></span> <span data-ttu-id="bd455-165">Klicken Sie auf **Auswählen** , um einen vordefinierten Zeitplan aus der Liste auszuwählen, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd455-165">Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>|  
|<span data-ttu-id="bd455-166">**Zwischengespeichert. Sammeln und Zwischenspeichern von Daten gemäß bestimmten Sammlungshäufigkeiten. Zwischengespeicherte Daten werden gemäß einem separaten Zeitplan hochgeladen.**</span><span class="sxs-lookup"><span data-stu-id="bd455-166">**Cached. Collect and cache data at a set of collection frequencies. Upload cached data on a separate schedule.**</span></span>|<span data-ttu-id="bd455-167">Daten werden gemäß bestimmten Sammlungshäufigkeiten aufgelistet und zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="bd455-167">Collect and cache data for a specified collection frequency.</span></span> <span data-ttu-id="bd455-168">Die aufgelisteten Daten werden gemäß einem separaten Zeitplan hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="bd455-168">Upload the collected data on a separate schedule.</span></span>|  
  
 <span data-ttu-id="bd455-169">**Sammelhäufigkeit (Sek)**</span><span class="sxs-lookup"><span data-stu-id="bd455-169">**Collection items**</span></span>  
 <span data-ttu-id="bd455-170">Zeigt die Sammelelemente im Sammlungssatz an.</span><span class="sxs-lookup"><span data-stu-id="bd455-170">Displays the collection items in the collection set.</span></span> <span data-ttu-id="bd455-171">Die folgenden Informationen werden für jedes Sammelelement bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="bd455-171">The following information is provided for each collection item:</span></span>  
  
-   <span data-ttu-id="bd455-172">**Name**</span><span class="sxs-lookup"><span data-stu-id="bd455-172">**Name**</span></span>  
  
-   <span data-ttu-id="bd455-173">**Sammlertyp**</span><span class="sxs-lookup"><span data-stu-id="bd455-173">**Collector Type**</span></span>  
  
-   <span data-ttu-id="bd455-174">**Sammlungshäufigkeit** (Sek).</span><span class="sxs-lookup"><span data-stu-id="bd455-174">**Collection Frequency** (secs).</span></span> <span data-ttu-id="bd455-175">Dieses Feld ist bearbeitbar, wenn **Datensammlung und -upload** als zwischengespeichert konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bd455-175">This field is editable if **Data collection and upload** is configured as cached.</span></span> <span data-ttu-id="bd455-176">Doppelklicken Sie auf diese Zelle, um die Sammlungshäufigkeit festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bd455-176">Double-click this cell to set the collection frequency.</span></span>  
  
 <span data-ttu-id="bd455-177">**Eingabeparameter**</span><span class="sxs-lookup"><span data-stu-id="bd455-177">**Input parameters**</span></span>  
 <span data-ttu-id="bd455-178">Zeigt die für den Sammlungssatz verwendeten Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="bd455-178">Displays the input parameters used for the collection set.</span></span>  
  
 <span data-ttu-id="bd455-179">**Ausführen als**</span><span class="sxs-lookup"><span data-stu-id="bd455-179">**Run as**</span></span>  
 <span data-ttu-id="bd455-180">Gibt das Konto an, das verwendet wird, um den Sammlungssatz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bd455-180">Specifies the account used to run the collection set.</span></span> <span data-ttu-id="bd455-181">Dies entspricht standardmäßig dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienstkonto.</span><span class="sxs-lookup"><span data-stu-id="bd455-181">By default this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Service Account.</span></span> <span data-ttu-id="bd455-182">Wenn Proxykonten definiert sind, enthält diese Liste die Namen der verfügbaren Proxykonten.</span><span class="sxs-lookup"><span data-stu-id="bd455-182">If proxy accounts are defined, this list includes the names of the available proxy accounts.</span></span>  
  
 <span data-ttu-id="bd455-183">**Festlegen, wie lang gesammelte Daten im Verwaltungs-Data Warehouse beibehalten werden**</span><span class="sxs-lookup"><span data-stu-id="bd455-183">**Set how long collected data will be retained in the management data warehouse.**</span></span>  
 <span data-ttu-id="bd455-184">Gibt an, wie lange aufgelistete Daten beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="bd455-184">Specifies how long collected data is retained.</span></span> <span data-ttu-id="bd455-185">Wählen Sie eine der folgenden Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="bd455-185">Pick one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd455-186">**Daten beibehalten für**</span><span class="sxs-lookup"><span data-stu-id="bd455-186">**Retain data for**</span></span>|<span data-ttu-id="bd455-187">Diese Option ist standardmäßig aktiviert, und die Standardbeibehaltungsdauer ist 14 Tage.</span><span class="sxs-lookup"><span data-stu-id="bd455-187">This option is selected by default, and the default retention period is 14 days.</span></span>|  
|<span data-ttu-id="bd455-188">**Daten unbegrenzt beibehalten**</span><span class="sxs-lookup"><span data-stu-id="bd455-188">**Retain data indefinitely**</span></span>|<span data-ttu-id="bd455-189">Daten können für unbegrenzte Zeit beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="bd455-189">There is no time limit on the length of time that data is retained.</span></span>|  
  
 <span data-ttu-id="bd455-190">**Uploads (Seite)**</span><span class="sxs-lookup"><span data-stu-id="bd455-190">**Uploads Page**</span></span>  
  
 <span data-ttu-id="bd455-191">Auf dieser Seite können Sie den Uploadzeitplan für Daten konfigurieren, die von diesem Sammlungssatz aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="bd455-191">Use this page to configure the upload schedule for data that is collected by this collection set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd455-192">Diese Registerkarte ist nur aktiviert, wenn die Option **Zwischengespeichert** für **Datensammlung und -upload**konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="bd455-192">This tab is only enabled if the **Cached** option is configured for **Data collection and upload**.</span></span>  
  
 <span data-ttu-id="bd455-193">**Server**</span><span class="sxs-lookup"><span data-stu-id="bd455-193">**Server**</span></span>  
 <span data-ttu-id="bd455-194">Zeigt den Namen des Servers an, der als Host für das Verwaltungs-Data Warehouse fungiert.</span><span class="sxs-lookup"><span data-stu-id="bd455-194">Displays the name of the server that hosts the management data warehouse.</span></span> <span data-ttu-id="bd455-195">Weitere Informationen finden Sie unter [Konfigurieren des Verwaltungs-Data Warehouses &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bd455-195">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="bd455-196">**Verwaltungs-Data Warehouse**</span><span class="sxs-lookup"><span data-stu-id="bd455-196">**Management data warehouse**</span></span>  
 <span data-ttu-id="bd455-197">Zeigt den Namen des Verwaltungs-Data Warehouses an.</span><span class="sxs-lookup"><span data-stu-id="bd455-197">Displays the name of the management data warehouse.</span></span> <span data-ttu-id="bd455-198">Weitere Informationen finden Sie unter [Konfigurieren des Verwaltungs-Data Warehouses &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="bd455-198">For more information, see [Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;](configure-the-management-data-warehouse-sql-server-management-studio.md).</span></span>  
  
 <span data-ttu-id="bd455-199">**Letzter Upload**</span><span class="sxs-lookup"><span data-stu-id="bd455-199">**Last upload**</span></span>  
 <span data-ttu-id="bd455-200">Zeigt Datums- und Uhrzeitinformationen zum letzten für den Sammlungssatz ausgeführten Upload an.</span><span class="sxs-lookup"><span data-stu-id="bd455-200">Displays date and time information for the last upload done for the collection set.</span></span>  
  
 <span data-ttu-id="bd455-201">**Uploadzeitplan**</span><span class="sxs-lookup"><span data-stu-id="bd455-201">**Upload schedule**</span></span>  
 <span data-ttu-id="bd455-202">Gibt den Uploadzeitplan für den Sammlungssatz an.</span><span class="sxs-lookup"><span data-stu-id="bd455-202">Specifies the upload schedule for the collection set.</span></span> <span data-ttu-id="bd455-203">Wenn diese Option aktiviert ist, klicken Sie auf **Auswählen** , um einen vordefinierten Zeitplan aus der Liste auszuwählen, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd455-203">If enabled, Click **Pick** to select from a predefined list of schedules, or click **New** to create a new schedule.</span></span>  
  
 <span data-ttu-id="bd455-204">**Beschreibung (Seite)**</span><span class="sxs-lookup"><span data-stu-id="bd455-204">**Description Page**</span></span>  
  
 <span data-ttu-id="bd455-205">Auf dieser Seite können Sie eine Beschreibung des Sammlungssatzes anzeigen, auf den diese Eigenschaftenseite verweist.</span><span class="sxs-lookup"><span data-stu-id="bd455-205">Use this page to view a description of the collection set that this properties page refers to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd455-206">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bd455-206">See Also</span></span>  
 <span data-ttu-id="bd455-207">[Verwalten von Datensammlungen](manage-data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="bd455-207">[Manage Data Collection](manage-data-collection.md) </span></span>  
 [<span data-ttu-id="bd455-208">Datensammlung</span><span class="sxs-lookup"><span data-stu-id="bd455-208">Data Collection</span></span>](data-collection.md)  
  
  
