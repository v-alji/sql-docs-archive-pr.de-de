---
title: 'Schritt 1: Kopieren des Pakets aus Lektion 3 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0d053786-5203-43f3-a613-27a8dd2bc44a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fde3bd907e8a55b1ac9a164b2960268189b19392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617177"
---
# <a name="step-1-copying-the-lesson-3-package"></a><span data-ttu-id="e4bbe-102">Schritt 1: Kopieren des Pakets aus Lektion 3</span><span class="sxs-lookup"><span data-stu-id="e4bbe-102">Step 1: Copying the Lesson 3 Package</span></span>
  <span data-ttu-id="e4bbe-103">In dieser Aufgabe erstellen Sie eine Kopie des in Lektion 3 erstellten Pakets Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-103">In this task, you will create a copy of the Lesson 3.dtsx package that you created in Lesson 3.</span></span> <span data-ttu-id="e4bbe-104">Wenn Sie Lektion 3 nicht abgeschlossen haben, können Sie stattdessen das vollständige Lektion 3-Paket, das im Lernprogramm des Projekts enthalten ist, hinzufügen und dann kopieren.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-104">Alternatively, if you did not complete lesson 3, you can add the completed lesson 3 package that is included with the tutorial to the project, and then make a copy of it to work with.</span></span> <span data-ttu-id="e4bbe-105">Sie verwenden diese neue Kopie im gesamten Rest der Lektion 4.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-105">You will use this new copy throughout the rest of Lesson 4.</span></span>  
  
### <a name="to-create-the-lesson-4-package"></a><span data-ttu-id="e4bbe-106">So erstellen Sie das Lektion 4-Paket</span><span class="sxs-lookup"><span data-stu-id="e4bbe-106">To create the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="e4bbe-107">Wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools noch nicht geöffnet ist, klicken Sie auf **Start**und zeigen Sie auf **Alle Programme**. Klicken Sie auf **Microsoft SQL Server**und anschließend auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="e4bbe-108">Klicken Sie im Menü **Datei** auf **Öffnen**, klicken Sie auf **Projekt/Projekt**Mappe, wählen Sie **SSIS Tutorial** aus, klicken Sie auf **Öffnen**, und doppelklicken Sie dann auf **SSIS Tutorial. sln**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="e4bbe-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Lesson 3.dtsx**, und klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-109">In Solution Explorer, right-click **Lesson 3.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="e4bbe-110">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="e4bbe-111">Standardmäßig wird das kopierte Paket Lesson 4.dtsx genannt.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-111">By default, the copied package is named Lesson 4.dtsx.</span></span>  
  
5.  <span data-ttu-id="e4bbe-112">Doppelklicken Sie in Projektmappen-Explorer auf **Lektion 4. DTX** , um das Paket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-112">In Solution Explorer, double-click **Lesson 4.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="e4bbe-113">Klicken Sie mit der rechten Maustaste an einer beliebigen Stelle im Hintergrund der Registerkarte **Ablaufsteuerung** , und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="e4bbe-114">Aktualisieren Sie im Eigenschaftenfenster die- `Name` Eigenschaft auf `Lesson 4` .</span><span class="sxs-lookup"><span data-stu-id="e4bbe-114">In the Properties window, update the `Name` property to `Lesson 4`.</span></span>  
  
8.  <span data-ttu-id="e4bbe-115">Klicken Sie in das Feld für die **ID** -Eigenschaft, und klicken Sie anschließend in der Liste auf **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-3-package"></a><span data-ttu-id="e4bbe-116">So fügen Sie das abgeschlossene Lektion 3-Paket hinzu</span><span class="sxs-lookup"><span data-stu-id="e4bbe-116">To add the completed Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="e4bbe-117">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , und öffnen Sie das SSIS-Lernprogrammprojekt.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="e4bbe-118">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie auf **vorhandenes Paket hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="e4bbe-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="e4bbe-119">Wählen Sie im Dialogfeld **Kopie des vorhandenen Pakets hinzufügen** unter **Paketspeicherort**die Option **Dateisystem**aus.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="e4bbe-120">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , navigieren Sie zu Lesson 3. DTX auf Ihrem Computer, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-120">Click the browse **(...)** button, navigate to Lesson 3.dtsx on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="e4bbe-121">Um alle Lektionspakete für dieses Lernprogramm herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="e4bbe-122">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="e4bbe-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="e4bbe-123">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="e4bbe-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="e4bbe-124">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="e4bbe-125">Kopieren Sie das Paket aus Lektion 3, und fügen Sie es wie in den Schritten 3 bis 8 der vorherigen Prozedur beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="e4bbe-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e4bbe-126">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="e4bbe-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e4bbe-127">Schritt 2: Erstellen einer beschädigten Datei</span><span class="sxs-lookup"><span data-stu-id="e4bbe-127">Step 2: Creating a Corrupted File</span></span>](lesson-4-2-creating-a-corrupted-file.md)  
  
  
