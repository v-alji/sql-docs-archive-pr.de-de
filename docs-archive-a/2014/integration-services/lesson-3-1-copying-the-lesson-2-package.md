---
title: 'Schritt 1: Kopieren des Pakets aus Lektion 2 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bd91402-4e37-41de-ab78-8ca5a1948a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39bfc965febc401bd66b1077388021b8ccf52aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700016"
---
# <a name="step-1-copying-the-lesson-2-package"></a><span data-ttu-id="add4b-102">Schritt 1: Kopieren des Pakets aus Lektion 2</span><span class="sxs-lookup"><span data-stu-id="add4b-102">Step 1: Copying the Lesson 2 Package</span></span>
  <span data-ttu-id="add4b-103">In dieser Aufgabe erstellen Sie eine Kopie des in Lektion 2 erstellten Pakets Lesson 2.dtsx.</span><span class="sxs-lookup"><span data-stu-id="add4b-103">In this task, you will create a copy of the Lesson 2.dtsx package that you created in Lesson 2.</span></span> <span data-ttu-id="add4b-104">Wahlweise können Sie dem Projekt auch das im Tutorial enthaltene abgeschlossene Paket aus Lektion 2 hinzufügen und anschließend von diesem Paket eine Kopie erstellen.</span><span class="sxs-lookup"><span data-stu-id="add4b-104">Alternatively, you can add the completed lesson 2 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="add4b-105">Sie verwenden diese neue Kopie im gesamten Rest der Lektion 3.</span><span class="sxs-lookup"><span data-stu-id="add4b-105">You will use this new copy throughout the rest of Lesson 3.</span></span>  
  
### <a name="to-create-the-lesson-3-package"></a><span data-ttu-id="add4b-106">So erstellen Sie das Lektion 3-Paket</span><span class="sxs-lookup"><span data-stu-id="add4b-106">To create the Lesson 3 package</span></span>  
  
1.  <span data-ttu-id="add4b-107">Wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools noch nicht geöffnet ist, klicken Sie auf **Start**und zeigen Sie auf **Alle Programme**. Klicken Sie anschließend auf **Microsoft SQL Server 2012**und danach auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="add4b-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="add4b-108">Klicken Sie im Menü **Datei** auf **Öffnen**, klicken Sie auf **Projekt/Projekt**Mappe, wählen Sie **SSIS Tutorial** aus, klicken Sie auf **Öffnen**, und doppelklicken Sie dann auf **SSIS Tutorial. sln**.</span><span class="sxs-lookup"><span data-stu-id="add4b-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="add4b-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Lesson 2.dtsx**und anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="add4b-109">In Solution Explorer, right-click **Lesson 2.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="add4b-110">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="add4b-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="add4b-111">Standardmäßig wird das kopierte Paket Lesson 3.dtsx genannt.</span><span class="sxs-lookup"><span data-stu-id="add4b-111">By default, the copied package is named Lesson 3.dtsx.</span></span>  
  
5.  <span data-ttu-id="add4b-112">Doppelklicken Sie in Projektmappen-Explorer auf **Lesson 3. DTX** , um das Paket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="add4b-112">In Solution Explorer, double-click **Lesson 3.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="add4b-113">Klicken Sie mit der rechten Maustaste an einer beliebigen Stelle im Hintergrund der Registerkarte **Ablaufsteuerung** , und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="add4b-113">Right-click anywhere in the background of the **Control Flow** tab and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="add4b-114">Aktualisieren Sie im Eigenschaftenfenster die- `Name` Eigenschaft auf `Lesson 3` .</span><span class="sxs-lookup"><span data-stu-id="add4b-114">In the Properties window, update the `Name` property to `Lesson 3`.</span></span>  
  
8.  <span data-ttu-id="add4b-115">Klicken Sie in das Feld für die **ID** -Eigenschaft, und klicken Sie anschließend in der Liste auf **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="add4b-115">Click the box for the **ID** property, and then in the list, click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson2-package"></a><span data-ttu-id="add4b-116">So fügen Sie das abgeschlossene Lesson2-Paket hinzu</span><span class="sxs-lookup"><span data-stu-id="add4b-116">To add the completed Lesson2 package</span></span>  
  
1.  <span data-ttu-id="add4b-117">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , und öffnen Sie das SSIS-Lernprogrammprojekt.</span><span class="sxs-lookup"><span data-stu-id="add4b-117">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="add4b-118">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie auf **vorhandenes Paket hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="add4b-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="add4b-119">Wählen Sie im Dialogfeld **Kopie des vorhandenen Pakets hinzufügen** unter **Paketspeicherort**die Option **Dateisystem**aus.</span><span class="sxs-lookup"><span data-stu-id="add4b-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="add4b-120">Klicken Sie auf die Schaltfläche zum Durchsuchen **(…)**, navigieren Sie zu **Lesson 2.dtsx** auf Ihrem Computer, und klicken Sie anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="add4b-120">Click the browse **(...)** button, navigate to **Lesson 2.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="add4b-121">Um alle Lektionspakete für dieses Lernprogramm herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="add4b-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="add4b-122">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="add4b-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="add4b-123">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="add4b-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="add4b-124">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="add4b-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="add4b-125">Kopieren Sie das Paket aus Lektion 3, und fügen Sie es wie in den Schritten 3 bis 8 der vorherigen Prozedur beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="add4b-125">Copy and paste the Lesson 3 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="add4b-126">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="add4b-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="add4b-127">Schritt 2: Hinzufügen und Konfigurieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="add4b-127">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
  
