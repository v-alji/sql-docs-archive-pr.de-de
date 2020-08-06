---
title: 'Schritt 1: Kopieren des Pakets aus Lektion 4 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8aa7d690-4649-4c0a-ac6f-9504637ee426
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1140c0e7d26f11f79e18d42143c1ed084c4ff144
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622214"
---
# <a name="step-1-copying-the-lesson-4-package"></a><span data-ttu-id="977b2-102">Schritt 1: Kopieren des Pakets aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="977b2-102">Step 1: Copying the Lesson 4 Package</span></span>
  <span data-ttu-id="977b2-103">In dieser Aufgabe erstellen Sie eine Kopie des in Lektion 4 erstellten Pakets namens „Lesson 4.dtsx“.</span><span class="sxs-lookup"><span data-stu-id="977b2-103">In this task, you will create a copy of the Lesson 4.dtsx package that you created in Lesson 4.</span></span> <span data-ttu-id="977b2-104">Alternativ können Sie dem Projekt auch das im Tutorial enthaltene, abgeschlossene Paket aus Lektion 4 hinzufügen und anschließend eine Kopie dieses Pakets erstellen.</span><span class="sxs-lookup"><span data-stu-id="977b2-104">Alternatively, you can add the completed lesson 4 package that is included with the tutorial to the project, and then copy it instead.</span></span> <span data-ttu-id="977b2-105">Sie werden diese neue Kopie in der gesamten Lektion 5 verwenden.</span><span class="sxs-lookup"><span data-stu-id="977b2-105">You will use this new copy throughout the rest of Lesson 5.</span></span>  
  
### <a name="to-copy-the-lesson-4-package"></a><span data-ttu-id="977b2-106">So kopieren Sie das Paket aus Lektion 4</span><span class="sxs-lookup"><span data-stu-id="977b2-106">To copy the Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="977b2-107">Wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools noch nicht geöffnet ist, klicken Sie auf **Start**und zeigen Sie auf **Alle Programme**. Klicken Sie anschließend auf **Microsoft SQL Server 2012**und danach auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="977b2-107">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools is not already open, click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2012**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="977b2-108">Klicken Sie im Menü **Datei** auf **Öffnen**, klicken Sie auf **Projekt/Projekt**Mappe, wählen Sie **SSIS Tutorial** aus, klicken Sie auf **Öffnen**, und doppelklicken Sie dann auf **SSIS Tutorial. sln**.</span><span class="sxs-lookup"><span data-stu-id="977b2-108">On the **File** menu, click **Open**, click **Project/Solution**, select **SSIS Tutorial** and click **Open**, and then double-click **SSIS Tutorial.sln**.</span></span>  
  
3.  <span data-ttu-id="977b2-109">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Lesson 4.dtsx**, und klicken Sie anschließend auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="977b2-109">In Solution Explorer, right-click **Lesson 4.dtsx**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="977b2-110">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="977b2-110">In Solution Explorer, right-click **SSIS Packages**, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="977b2-111">Standardmäßig wird das kopierte Paket „Lesson 5.dtsx“ benannt.</span><span class="sxs-lookup"><span data-stu-id="977b2-111">By default, the copied package is named Lesson 5.dtsx.</span></span>  
  
5.  <span data-ttu-id="977b2-112">Doppelklicken Sie im Projektmappen-Explorer auf **Lesson 5.dtsx** , um das Paket zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="977b2-112">In the Solution Explorer, double-click **Lesson 5.dtsx** to open the package.</span></span>  
  
6.  <span data-ttu-id="977b2-113">Klicken Sie mit der rechten Maustaste auf eine beliebige Stelle im Hintergrund der Registerkarte **Ablauf Steuerung** und dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="977b2-113">Right-click anywhere in the background of the **Control Flow** tab then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="977b2-114">Aktualisieren Sie im Eigenschaftenfenster die- `Name` Eigenschaft auf `Lesson 5` .</span><span class="sxs-lookup"><span data-stu-id="977b2-114">In the Properties window, update the `Name` property to `Lesson 5`.</span></span>  
  
8.  <span data-ttu-id="977b2-115">Aktivieren Sie das Kontrollkästchen für die **ID** -Eigenschaft, klicken Sie auf den Dropdown Pfeil, und klicken Sie dann auf **\<Generate New ID>** .</span><span class="sxs-lookup"><span data-stu-id="977b2-115">Click the box for the **ID** property, then click the dropdown arrow, and then click **\<Generate New ID>**.</span></span>  
  
### <a name="to-add-the-completed-lesson-4-package"></a><span data-ttu-id="977b2-116">So fügen Sie das abgeschlossene Paket aus Lektion 4 hinzu</span><span class="sxs-lookup"><span data-stu-id="977b2-116">To add the completed Lesson 4 package</span></span>  
  
1.  <span data-ttu-id="977b2-117">Öffnen Sie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools und das SSIS-Lernprogrammprojekt.</span><span class="sxs-lookup"><span data-stu-id="977b2-117">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Data Tools and open the SSIS Tutorial project.</span></span>  
  
2.  <span data-ttu-id="977b2-118">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **SSIS-Pakete**, und klicken Sie auf **vorhandenes Paket hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="977b2-118">In Solution Explorer, right-click **SSIS Packages**, and click **Add Existing Package**.</span></span>  
  
3.  <span data-ttu-id="977b2-119">Wählen Sie im Dialogfeld **Kopie des vorhandenen Pakets hinzufügen** unter **Paketspeicherort**die Option **Dateisystem**aus.</span><span class="sxs-lookup"><span data-stu-id="977b2-119">In the **Add Copy of Existing Package** dialog box, in **Package location**, select **File system**.</span></span>  
  
4.  <span data-ttu-id="977b2-120">Klicken Sie auf die Schaltfläche zum Durchsuchen **(…)**, navigieren Sie zu **Lesson 4.dtsx** auf Ihrem Computer, und klicken Sie anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="977b2-120">Click the browse **(...)** button, navigate to **Lesson 4.dtsx** on your machine, and then click **Open**.</span></span>  
  
     <span data-ttu-id="977b2-121">Um alle Lektionspakete für dieses Lernprogramm herunterzuladen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="977b2-121">To download all of the lesson packages for this tutorial, do the following.</span></span>  
  
    1.  <span data-ttu-id="977b2-122">Klicken Sie [hier](https://go.microsoft.com/fwlink/?LinkId=275027), um zur Seite Integration Services Product Samples zu gelangen</span><span class="sxs-lookup"><span data-stu-id="977b2-122">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="977b2-123">Klicken Sie auf die Registerkarte **DOWNLOADS** .</span><span class="sxs-lookup"><span data-stu-id="977b2-123">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="977b2-124">Klicken Sie auf die Datei SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip.</span><span class="sxs-lookup"><span data-stu-id="977b2-124">Click the SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
5.  <span data-ttu-id="977b2-125">Kopieren Sie das Paket aus Lektion 4, und fügen Sie es gemäß den Schritten 3 bis 8 der vorherigen Prozedur ein.</span><span class="sxs-lookup"><span data-stu-id="977b2-125">Copy and paste the Lesson 4 package as described in steps 3-8 in the previous procedure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="977b2-126">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="977b2-126">Next Task in Lesson</span></span>  
 [<span data-ttu-id="977b2-127">Schritt 2: Aktivieren und Konfigurieren von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="977b2-127">Step 2: Enabling and Configuring Package Configurations</span></span>](lesson-5-2-enabling-and-configuring-package-configurations.md)  
  
  
