---
title: 'Schritt 1: Kopieren des Pakets aus Lektion 5 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a25fcc13-987e-4f3d-8f0c-76f7e6e59920
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b30ec927084548a2371f22d857d5302e5dc84c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622782"
---
# <a name="step-1-copying-the-lesson-5-package"></a><span data-ttu-id="9bb63-102">Schritt 1: Kopieren des Pakets aus Lektion 5</span><span class="sxs-lookup"><span data-stu-id="9bb63-102">Step 1: Copying the Lesson 5 Package</span></span>
  <span data-ttu-id="9bb63-103">In dieser Aufgabe erstellen Sie eine Kopie des in Lektion 5 erstellten Pakets Lesson 5.dtsx.</span><span class="sxs-lookup"><span data-stu-id="9bb63-103">In this task, you will create a copy of the Lesson 5.dtsx package that you created in Lesson 5.</span></span> <span data-ttu-id="9bb63-104">Wahlweise können Sie dem Projekt auch das im Lernprogramm enthaltene abgeschlossene Paket aus Lektion 5 hinzufügen und dann von diesem Paket eine Kopie erstellen.</span><span class="sxs-lookup"><span data-stu-id="9bb63-104">Alternatively, you can add the completed lesson 5 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="9bb63-105">Sie verwenden diese neue Kopie im gesamten Rest der Lektion 6.</span><span class="sxs-lookup"><span data-stu-id="9bb63-105">You will use this new copy throughout the rest of Lesson 6.</span></span>  
  
### <a name="to-copy-the-lesson-5-package"></a><span data-ttu-id="9bb63-106">So kopieren Sie das Lektion 5-Paket aus</span><span class="sxs-lookup"><span data-stu-id="9bb63-106">To copy the Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="9bb63-107">Wenn SQL Server Data Tools noch nicht geöffnet sind, klicken Sie auf Start, zeigen auf Alle Programme und auf Microsoft SQL Server 2012 und klicken dann auf SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="9bb63-107">If SQL Server Data Tools is not already open, click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Server Data Tools.</span></span>  
  
2.  <span data-ttu-id="9bb63-108">Klicken Sie im Menü Datei auf Öffnen, klicken Sie auf Projekt/Projektmappe, wählen Sie SSIS Tutorial aus, klicken Sie auf Öffnen, und doppelklicken Sie dann auf SSIS Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="9bb63-108">On the File menu, click Open, click Project/Solution, select SSIS Tutorial and click Open, and then double-click SSIS Tutorial.sln.</span></span>  
  
3.  <span data-ttu-id="9bb63-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf Lesson 5.dtsx, und klicken Sie dann auf Kopieren.</span><span class="sxs-lookup"><span data-stu-id="9bb63-109">In Solution Explorer, right-click Lesson 5.dtsx, and then click Copy.</span></span>  
  
4.  <span data-ttu-id="9bb63-110">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf SSIS Packages, und klicken Sie dann auf Einfügen.</span><span class="sxs-lookup"><span data-stu-id="9bb63-110">In Solution Explorer, right-click SSIS Packages, and then click Paste.</span></span>  
  
     <span data-ttu-id="9bb63-111">Standardmäßig wird das kopierte Paket Lesson 6.dtsx genannt.</span><span class="sxs-lookup"><span data-stu-id="9bb63-111">By default, the copied package is named Lesson 6.dtsx.</span></span>  
  
5.  <span data-ttu-id="9bb63-112">Doppelklicken Sie im Projektmappen-Explorer auf Lesson 6.dtsx, um das Paket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9bb63-112">In the Solution Explorer, double-click Lesson 6.dtsx to open the package.</span></span>  
  
6.  <span data-ttu-id="9bb63-113">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Hintergrund der Registerkarte Ablaufsteuerung, und klicken Sie dann auf Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9bb63-113">Right-click anywhere in the background of the Control Flow tab then click Properties.</span></span>  
  
7.  <span data-ttu-id="9bb63-114">Aktualisieren Sie im Eigenschaftenfenster die Name-Eigenschaft in Lesson 6.</span><span class="sxs-lookup"><span data-stu-id="9bb63-114">In the Properties window, update the Name property to Lesson 6.</span></span>  
  
8.  <span data-ttu-id="9bb63-115">Klicken Sie in das Feld für die ID-Eigenschaft, auf den Dropdownpfeil und anschließend auf \<Generate New ID>.</span><span class="sxs-lookup"><span data-stu-id="9bb63-115">Click the box for the ID property, then click the dropdown arrow, and then click \<Generate New ID>.</span></span>  
  
### <a name="to-add-the-completed-lesson-5-package"></a><span data-ttu-id="9bb63-116">So fügen Sie das abgeschlossene Lektion 5-Paket hinzu</span><span class="sxs-lookup"><span data-stu-id="9bb63-116">To add the completed Lesson 5 package</span></span>  
  
1.  <span data-ttu-id="9bb63-117">Öffnen Sie SQL Server Data Tools und das SSIS-Lernprogrammprojekt.</span><span class="sxs-lookup"><span data-stu-id="9bb63-117">Open SQL Server Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="9bb63-118">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf SSIS-Pakete, und klicken Sie auf Vorhandenes Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bb63-118">In Solution Explorer, right-click SSIS Packages, and click Add Existing Package.</span></span>  
  
3.  <span data-ttu-id="9bb63-119">Wählen Sie im Dialogfeld Kopie des vorhandenen Pakets hinzufügen unter Paketspeicherort die Option Dateisystem aus.</span><span class="sxs-lookup"><span data-stu-id="9bb63-119">In the Add Copy of Existing Package dialog box, in Package location, select File system.</span></span>  
  
4.  <span data-ttu-id="9bb63-120">Klicken Sie auf die Schaltfläche zum Durchsuchen (…), navigieren Sie auf dem Computer zu „Lesson 5.dtsx“, und klicken Sie anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="9bb63-120">Click the browse (...) button, Lesson 5.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="9bb63-121">Um alle Lektionspakete für dieses Lernprogramm herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="9bb63-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="9bb63-122">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="9bb63-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="9bb63-123">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="9bb63-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="9bb63-124">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="9bb63-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="9bb63-125">Kopieren Sie das Paket aus Lektion 5, und fügen Sie es wie in den Schritten 3 bis 8 der vorherigen Prozedur beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="9bb63-125">Copy and paste the Lesson 5 package as described in steps 3-8 in the previous procedure.</span></span>  
  
     <span data-ttu-id="9bb63-126">Wenn die Projektmappe nach dem Kopieren des Lektion 5-Pakets noch Pakete aus vorherigen Lektionen enthält, klicken Sie mit der rechten Maustaste auf die einzelnen Pakete aus Lektion 1 bis 5 und klicken dann auf Aus Projekt ausschließen.</span><span class="sxs-lookup"><span data-stu-id="9bb63-126">After copying the Lesson 5 package, if you currently have the packages from the previous lessons in your solution, right-click each package from lessons 1-5 and click Exclude From Project.</span></span> <span data-ttu-id="9bb63-127">Anschließend sollte nur noch Lesson 6.dtsx in der Projektmappe enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9bb63-127">When done you should have only Lesson 6.dtsx in your solution.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9bb63-128">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="9bb63-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9bb63-129">Schritt 2: Konvertieren des Projekts in das Projektbereitstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="9bb63-129">Step 2: Converting the Project to the Project Deployment Model</span></span>](lesson-6-2-converting-the-project-to-the-project-deployment-model.md)  
  
  
