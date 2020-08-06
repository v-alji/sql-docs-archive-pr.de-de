---
title: Batch Verarbeitung (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608903"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="51b40-102">Batchverarbeitung (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="51b40-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="51b40-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]können Sie den Batch-Befehl verwenden, um mehrere Verarbeitungsbefehle in einer einzelnen Anforderung an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="51b40-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="51b40-104">Bei der Batchverarbeitung können Sie steuern, welche Objekte verarbeitet werden sollen und in welcher Reihenfolge dies geschehen soll.</span><span class="sxs-lookup"><span data-stu-id="51b40-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="51b40-105">Außerdem kann ein Batch als eine Reihe von eigenständigen Aufträgen ausgeführt werden oder als Transaktion, in der ein Fehler bei einem Vorgang ein Rollback der Änderungen des gesamten Batches zur Folge hat.</span><span class="sxs-lookup"><span data-stu-id="51b40-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="51b40-106">Die Batchverarbeitung gewährleistet eine maximale Datenverfügbarkeit, da sich die Zeit, die zum Ausführen von Commits für Änderungen benötigt wird, verringert.</span><span class="sxs-lookup"><span data-stu-id="51b40-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="51b40-107">Wenn Sie eine vollständige Verarbeitung einer Dimension vornehmen, werden Partitionen, die diese Dimension verwenden, als nicht verarbeitet markiert.</span><span class="sxs-lookup"><span data-stu-id="51b40-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="51b40-108">Infolgedessen sind Cubes, die die nicht verarbeiteten Partitionen verwenden, nicht zum Durchsuchen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="51b40-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="51b40-109">Mit einem Batchverarbeitungsauftrag können Sie dieses Problem beheben, indem Sie die Dimensionen zusammen mit den betroffenen Partitionen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="51b40-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="51b40-110">Indem Sie den Batchverarbeitungsauftrag als Transaktion ausführen, stellen Sie sicher, dass alle in der Transaktion enthaltenen Objekte für Abfragen verfügbar bleiben, bis die Verarbeitung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="51b40-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="51b40-111">Während die Transaktion das Commit für die Änderungen durchführt, werden die betroffenen Objekte gesperrt und sind daher vorübergehend nicht verfügbar. Die Zeit, die insgesamt zum Ausführen des Commits für die Änderungen benötigt wird, liegt jedoch unter der Zeit, die zum Verarbeiten jedes einzelnen Objekts benötigt würde.</span><span class="sxs-lookup"><span data-stu-id="51b40-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="51b40-112">Die Verfahren in diesem Thema zeigen die Schritte, die zur vollständigen Verarbeitung von Dimensionen und Partitionen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="51b40-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="51b40-113">Für die Batchverarbeitung sind auch andere Verarbeitungsoptionen verfügbar, wie z. B. die inkrementelle Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="51b40-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="51b40-114">Damit diese Verfahren ordnungsgemäß ausgeführt werden können, sollten Sie eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank verwenden, die mindestens zwei Dimensionen und eine Partition enthält.</span><span class="sxs-lookup"><span data-stu-id="51b40-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="51b40-115">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="51b40-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="51b40-116">Batchverarbeitung in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="51b40-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="51b40-117">Batchverarbeitung mithilfe von XMLA in Management Studio</span><span class="sxs-lookup"><span data-stu-id="51b40-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a><span data-ttu-id="51b40-118">Batch Verarbeitung in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="51b40-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="51b40-119">Bevor Objekte in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]verarbeitet werden können, muss das Projekt, in dem sie enthalten sind, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="51b40-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="51b40-120">Weitere Informationen finden Sie unter [Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="51b40-121">Öffnen Sie [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51b40-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="51b40-122">Öffnen Sie ein Projekt, das bereits bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="51b40-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="51b40-123">Erweitern Sie im Projektmappen-Explorer den Ordner **Dimensionen** unter dem bereitgestellten Projekt.</span><span class="sxs-lookup"><span data-stu-id="51b40-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="51b40-124">Halten Sie die STRG-Taste gedrückt, und klicken Sie auf jede der Dimensionen im Ordner **Dimensionen** .</span><span class="sxs-lookup"><span data-stu-id="51b40-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="51b40-125">Klicken Sie mit der rechten Maustaste auf die ausgewählten Dimensionen, und klicken Sie dann auf **Verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="51b40-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="51b40-126">Halten Sie die STRG-Taste gedrückt, und klicken Sie auf jede der in der Liste **Objektliste**aufgeführten Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="51b40-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="51b40-127">Klicken Sie mit der rechten Maustaste auf die ausgewählten Dimensionen, und wählen Sie **Vollständig verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="51b40-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="51b40-128">Klicken Sie auf **Einstellungen ändern**, um den Batchverarbeitungsauftrag anzupassen.</span><span class="sxs-lookup"><span data-stu-id="51b40-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="51b40-129">Wählen Sie unter **Verarbeitungsoptionen**die folgenden Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="51b40-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="51b40-130">Legen Sie für**Verarbeitungsreihenfolge** die Option **Sequenziell**und für **Transaktionsmodus** die Option **Eine Transaktion**fest.</span><span class="sxs-lookup"><span data-stu-id="51b40-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="51b40-131">Legen Sie für**Rückschreibetabellenoption** die Option **Vorhandene verwenden**fest.</span><span class="sxs-lookup"><span data-stu-id="51b40-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="51b40-132">Aktivieren Sie unter **Betroffene Objekte**das Kontrollkästchen **Betroffene Objekte verarbeiten** .</span><span class="sxs-lookup"><span data-stu-id="51b40-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="51b40-133">Klicken Sie auf die Registerkarte **Dimensions Schlüsselfehler** . Überprüfen Sie, ob **Standardfehler Konfiguration verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="51b40-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="51b40-134">Klicken Sie auf **OK** , um das Fenster **Einstellungen ändern** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51b40-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="51b40-135">Klicken Sie im Fenster **Objekte verarbeiten** auf **Ausführen** , um mit dem Verarbeitungsauftrag zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="51b40-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="51b40-136">Klicken Sie auf **Schließen** , sobald das Meldungsfeld **Status**die Meldung **Die Verarbeitung wurde erfolgreich ausgeführt**anzeigt.</span><span class="sxs-lookup"><span data-stu-id="51b40-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="51b40-137">Klicken Sie im Fenster **Objekte verarbeiten** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="51b40-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="51b40-138">Batch Verarbeitung mithilfe von XMLA in Management Studio</span><span class="sxs-lookup"><span data-stu-id="51b40-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="51b40-139">Sie können ein XMLA-Skript erstellen, das Batchverarbeitung ausführt.</span><span class="sxs-lookup"><span data-stu-id="51b40-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="51b40-140">Starten Sie, indem Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] für jedes Objekt ein XMLA-Skript generieren, und kombinieren Sie sie dann in eine einzelne XMLA-Abfrage, die Sie interaktiv oder in einem geplanten Task ausführen.</span><span class="sxs-lookup"><span data-stu-id="51b40-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="51b40-141">Schrittanleitungen finden Sie unter **Beispiel 2** in [Planen von administrativen Tasks in SSAS mithilfe von SQL Server-Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="51b40-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b40-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51b40-142">See Also</span></span>  
 [<span data-ttu-id="51b40-143">Verarbeitung von mehrdimensionalen Modellobjekten</span><span class="sxs-lookup"><span data-stu-id="51b40-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
