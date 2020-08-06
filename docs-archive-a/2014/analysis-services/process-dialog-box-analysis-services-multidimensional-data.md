---
title: Verarbeiten (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725041"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="66156-102">Dialogfeld 'Verarbeiten' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="66156-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="66156-103">Mithilfe des Dialogfelds **Verarbeiten** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] und [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekte verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="66156-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="66156-104">Das Dialogfeld **Verarbeiten** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie folgendermaßen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="66156-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="66156-105">Klicken Sie in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Projektmappen-Explorer **mit der rechten Maustaste auf ein Projekt, einen Cube, eine Dimension oder eine Miningstruktur von** , und wählen Sie **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="66156-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="66156-106">Wählen Sie auf der Symbolleiste auf jeder Seite von **Cube-Designer** und **Dimensions-Designer**oder auf den Seiten **Miningstruktur**und **Miningmodelle** von **Modell-Designer für Data Mining** die Option **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="66156-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="66156-107">Klicken Sie auf der Seite **Miningmodelle** von **Modell-Designer für Data Mining** mit der rechten Maustaste auf ein Miningmodell, und wählen Sie **Miningstruktur und alle Modelle verarbeiten** oder **Modell verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="66156-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="66156-108">Das Dialogfeld **Verarbeiten** von **SQL Server Management Studio** können Sie folgendermaßen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="66156-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="66156-109">Klicken Sie in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Objekt-Explorer **mit der rechten Maustaste auf eine Datenbank, einen Cube, eine Measuregruppe, eine Partition, eine Dimension, eine Miningstruktur oder ein Miningmodell von** , und wählen Sie **Verarbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="66156-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="66156-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="66156-110">Options</span></span>  
 <span data-ttu-id="66156-111">**Objektliste**</span><span class="sxs-lookup"><span data-stu-id="66156-111">**Object list**</span></span>  
 <span data-ttu-id="66156-112">Wählen Sie die zu verarbeitenden [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekte und die anzuwendenden Verarbeitungsoptionen und -einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="66156-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="66156-113">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="66156-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="66156-114">**Objektnamen**</span><span class="sxs-lookup"><span data-stu-id="66156-114">**Object Name**</span></span>  
 <span data-ttu-id="66156-115">Zeigt den Namen des zu verarbeitenden Objekts an.</span><span class="sxs-lookup"><span data-stu-id="66156-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="66156-116">Das Symbol links vom Namen gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="66156-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="66156-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="66156-117">**Type**</span></span>  
 <span data-ttu-id="66156-118">Zeigt den Typ des zu verarbeitenden Objekts an.</span><span class="sxs-lookup"><span data-stu-id="66156-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="66156-119">**Verarbeitungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="66156-119">**Process Options**</span></span>  
 <span data-ttu-id="66156-120">Wählen Sie den auszuführenden Verarbeitungstyp für das ausgewählte Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="66156-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="66156-121">Weitere Informationen zu verfügbaren Verarbeitungsoptionen finden Sie unter Verarbeitung von mehr [dimensionalen Modell Objekten](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="66156-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="66156-122">**Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="66156-122">**Settings**</span></span>  
 <span data-ttu-id="66156-123">Zeigt den Link **Konfigurieren** an, wenn Sie für Cubes, Measuregruppen oder Partitionen unter **Verarbeitungsoptionen** die Option **Inkrementell verarbeiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="66156-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="66156-124">Klicken Sie auf **Konfigurieren** , um das Dialogfeld **Inkrementelles Update** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="66156-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="66156-125">Weitere Informationen zum Dialogfeld **Inkrementelles Update** finden Sie unter [Inkrementelles Update &#40;Dialogfeld, Analysis Services – Mehrdimensionale Daten&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="66156-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="66156-126">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="66156-126">**Remove**</span></span>  
 <span data-ttu-id="66156-127">Klicken Sie auf diese Option, um die ausgewählten Elemente aus **Objektliste**zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="66156-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="66156-128">**Auswirkungsanalyse**</span><span class="sxs-lookup"><span data-stu-id="66156-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="66156-129">Klicken Sie auf diese Option, um das Dialogfeld **Auswirkungsanalyse** zu öffnen und die Objekte anzuzeigen, die von dem Verarbeitungstask betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="66156-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="66156-130">Weitere Informationen zum Dialogfeld **Auswirkungsanalyse** finden Sie unter [Auswirkungsanalyse &#40;Dialogfeld, Analysis Services – Mehrdimensionale Daten&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="66156-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66156-131">Diese Option ist deaktiviert, wenn im Dialogfeld **Einstellungen ändern** die Option **Betroffene Objekte** verarbeiten ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="66156-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="66156-132">**Einstellungen ändern**</span><span class="sxs-lookup"><span data-stu-id="66156-132">**Change Settings**</span></span>  
 <span data-ttu-id="66156-133">Klicken Sie auf diese Option, um das Dialogfeld **Einstellungen ändern** zu öffnen und die Einstellungen zu ändern, die die Verarbeitung der ausgewählten Objekte bestimmen, einschließlich der Batchverarbeitungseinstellungen, Rückschreibeeinstellungen und Einstellungen für Dimensionsschlüsselfehler.</span><span class="sxs-lookup"><span data-stu-id="66156-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="66156-134">Weitere Informationen zum Dialogfeld **Einstellungen ändern** finden Sie unter [Einstellungen ändern &#40;Dialogfeld, Analysis Services – Mehrdimensionale Daten&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="66156-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="66156-135">**Ausführen**</span><span class="sxs-lookup"><span data-stu-id="66156-135">**Run**</span></span>  
 <span data-ttu-id="66156-136">Klicken Sie auf diese Option, um die Objekte zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="66156-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66156-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66156-137">See Also</span></span>  
 <span data-ttu-id="66156-138">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="66156-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="66156-139">Dialog Feld ' Verarbeitungs Status ' &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="66156-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
