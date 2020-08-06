---
title: 'Schritt 1: Kopieren des Pakets aus Lektion 1 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f1616c2-2b4e-4010-be50-27d7b897403a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e117d82983bdaca8959fe7af8940d248ded97b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618109"
---
# <a name="step-1-copying-the-lesson-1-package"></a><span data-ttu-id="b82e7-102">Schritt 1: Kopieren des Pakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="b82e7-102">Step 1: Copying the Lesson 1 Package</span></span>
  <span data-ttu-id="b82e7-103">In dieser Aufgabe erstellen Sie eine Kopie des in Lektion 1 erstellten Pakets Lesson 1.dtsx.</span><span class="sxs-lookup"><span data-stu-id="b82e7-103">In this task, you will create a copy of the Lesson 1.dtsx package that you created in Lesson 1.</span></span> <span data-ttu-id="b82e7-104">Falls Sie Lektion 1 nicht abgeschlossen haben, können Sie stattdessen das vollständige Lektion 1-Paket, das im Tutorial des Projekts enthalten ist, hinzufügen und anschließend kopieren.</span><span class="sxs-lookup"><span data-stu-id="b82e7-104">If you did not complete Lesson 1, you can add the completed lesson 1 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="b82e7-105">Sie verwenden diese neue Kopie im gesamten Rest der Lektion 2.</span><span class="sxs-lookup"><span data-stu-id="b82e7-105">You will use this new copy throughout the rest of Lesson 2.</span></span>  
  
### <a name="to-create-the-lesson-2-package"></a><span data-ttu-id="b82e7-106">So erstellen Sie das Lektion 2-Paket</span><span class="sxs-lookup"><span data-stu-id="b82e7-106">To create the Lesson 2 package</span></span>  
  
1.  <span data-ttu-id="b82e7-107">Wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools noch nicht geöffnet ist, klicken Sie auf **Start**und zeigen Sie auf **Alle Programme**. Klicken Sie anschließend auf **Microsoft SQL Server 2012**und danach auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="b82e7-108">Klicken Sie im Menü **Datei** auf **Öffnen**, klicken Sie auf **Projekt/Projektmappe**, klicken Sie auf **SSIS Tutorial** , klicken Sie auf **Öffnen**, und doppelklicken Sie anschließend auf **SSIS Tutorial.sln**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-108">On the **File** menu, click **Open**, click **Project/Solution**, click the **SSIS Tutorial** folder and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="b82e7-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Lesson 1.dtsx**, und klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-109">In Solution Explorer, right-click **Lesson 1.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="b82e7-110">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="b82e7-111">Standardmäßig wird das kopierte Paket Lesson 2.dtsx genannt.</span><span class="sxs-lookup"><span data-stu-id="b82e7-111">By default, the copied package will be named Lesson 2.dtsx.</span></span>  
  
5.  <span data-ttu-id="b82e7-112">Doppelklicken Sie in Projektmappen-Explorer auf **Lektion 2. DTX** , um das Paket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b82e7-112">In Solution Explorer, double-click **Lesson 2.dtsx** to open the package</span></span>  
  
6.  <span data-ttu-id="b82e7-113">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Hintergrund der Entwurfsoberfläche **Ablaufsteuerung** , und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-113">Right-click anywhere in the background of the **Control Flow** design surface and click **Properties**.</span></span>  
  
7.  <span data-ttu-id="b82e7-114">Aktualisieren Sie im Eigenschaftenfenster die- `Name` Eigenschaft auf `Lesson 2` .</span><span class="sxs-lookup"><span data-stu-id="b82e7-114">In the Properties window, update the `Name` property to `Lesson 2`.</span></span>  
  
8.  <span data-ttu-id="b82e7-115">Klicken Sie in das Feld für die **ID** -Eigenschaft, klicken Sie auf den Dropdownpfeil und anschließend auf **\<Generate New ID>**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-115">Click the box for the **ID** property, click the dropdown arrow and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-1-package"></a><span data-ttu-id="b82e7-116">So fügen Sie das abgeschlossene Lektion 1-Paket hinzu</span><span class="sxs-lookup"><span data-stu-id="b82e7-116">To add the completed Lesson 1 package</span></span>  
  
1.  <span data-ttu-id="b82e7-117">Öffnen Sie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools und das SSIS-Lernprogrammprojekt.</span><span class="sxs-lookup"><span data-stu-id="b82e7-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="b82e7-118">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie auf **vorhandenes Paket hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="b82e7-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="b82e7-119">Wählen Sie im Dialogfeld **Kopie des vorhandenen Pakets hinzufügen** unter **Paketspeicherort**die Option **Dateisystem**aus.</span><span class="sxs-lookup"><span data-stu-id="b82e7-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="b82e7-120">Klicken Sie auf die Schaltfläche zum Durchsuchen **(…)**, navigieren Sie zu **Lesson 1.dtsx** auf Ihrem Computer, und klicken Sie anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b82e7-120">Click the browse **(...)** button, navigate to **Lesson 1.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="b82e7-121">Um alle Lektionspakete für dieses Lernprogramm herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="b82e7-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="b82e7-122">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="b82e7-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="b82e7-123">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="b82e7-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="b82e7-124">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="b82e7-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="b82e7-125">Kopieren Sie das Paket aus Lektion 1, und fügen Sie es wie in den Schritten 3 bis 8 der vorherigen Prozedur beschrieben ein.</span><span class="sxs-lookup"><span data-stu-id="b82e7-125">Copy and paste the Lesson 1 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b82e7-126">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b82e7-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b82e7-127">Schritt 2: Hinzufügen und Konfigurieren des Foreach-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="b82e7-127">Step 2: Adding and Configuring the Foreach Loop Container</span></span>](lesson-2-2-adding-and-configuring-the-foreach-loop-container.md)  
  
  
