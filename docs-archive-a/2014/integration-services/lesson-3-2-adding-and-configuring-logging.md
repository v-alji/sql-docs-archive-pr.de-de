---
title: 'Schritt 2: Hinzufügen und Konfigurieren der Protokollierung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700011"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="edf44-102">Schritt 2: Hinzufügen und Konfigurieren der Protokollierung</span><span class="sxs-lookup"><span data-stu-id="edf44-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="edf44-103">In dieser Aufgabe aktivieren Sie die Protokollierung für den Datenfluss im Paket Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="edf44-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="edf44-104">Sie konfigurieren dann einen Protokollanbieter für Textdateien, um die Ereignisse PipelineExecutionPlan und PipelineExecuteTrees zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="edf44-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="edf44-105">Der Protokollanbieter für Textdateien erstellt Protokolle, die auf einfache Weise angezeigt werden können und portabel sind.</span><span class="sxs-lookup"><span data-stu-id="edf44-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="edf44-106">Die Einfachheit dieser Protokolldateien ist besonders während der grundlegenden Testphase eines Pakets nützlich.</span><span class="sxs-lookup"><span data-stu-id="edf44-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="edf44-107">Sie können die Protokolleinträge auch im Fenster Protokollereignisse des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers anzeigen.</span><span class="sxs-lookup"><span data-stu-id="edf44-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="edf44-108">So fügen Sie die Protokollierung zum Paket hinzu</span><span class="sxs-lookup"><span data-stu-id="edf44-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="edf44-109">Klicken Sie im Menü **SSIS** auf **Protokollierung**.</span><span class="sxs-lookup"><span data-stu-id="edf44-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="edf44-110">Stellen Sie im Dialogfeld **SSIS-Protokolle konfigurieren** im **Container** -Bereich sicher, dass das oberste Objekt, das das Paket aus Lektion 3 darstellt, ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="edf44-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="edf44-111">Wählen Sie auf der Registerkarte **Anbieter und Protokolle** im Feld **Anbietertyp** die Option **SSIS-Protokollanbieter für Textdateien**aus, und klicken Sie anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="edf44-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="edf44-112">Integration Services fügt dem Paket einen neuen Protokoll Anbieter für Textdateien mit dem Standardnamen **SSIS-Protokoll Anbieter für Text Dateien**hinzu.</span><span class="sxs-lookup"><span data-stu-id="edf44-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="edf44-113">Sie können jetzt den neuen Protokollanbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="edf44-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="edf44-114">Geben Sie in der Spalte **Name den Namen** ein `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="edf44-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="edf44-115">Ändern Sie optional **Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="edf44-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="edf44-116">Klicken Sie in der Spalte **Konfiguration** auf **\<New Connection>** , um das Ziel anzugeben, wohin die Protokollinformationen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="edf44-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="edf44-117">Wählen Sie im Dialogfeld **Dateiverbindungs-Manager-Editor** für **Verwendungstyp**die Option **Datei erstellen**aus, und klicken Sie anschließend auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="edf44-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="edf44-118">Standardmäßig wird vom Dialogfeld **Dateien auswählen** der Projektordner geöffnet, aber Sie können Protokollinformationen an beliebiger Stelle speichern.</span><span class="sxs-lookup"><span data-stu-id="edf44-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="edf44-119">Geben Sie im Dialogfeld **Datei auswählen** im Feld **Dateiname den Namen** ein `TutorialLog.log` , und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="edf44-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="edf44-120">Klicken Sie auf **OK** , um das Dialogfeld **Dateiverbindungs-Manager-Editor** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="edf44-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="edf44-121">Erweitern Sie im **Container** -Bereich alle Knoten der Paketcontainerhierarchie, und deaktivieren Sie anschließend alle Kontrollkästchen, einschließlich des Kontrollkästchens für **Extract Sample Currency Data** .</span><span class="sxs-lookup"><span data-stu-id="edf44-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="edf44-122">Aktivieren Sie jetzt das Kontrollkästchen für **Extract Sample Currency Data** , um nur die Ereignisse für diesen Knoten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="edf44-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="edf44-123">Wenn der Status des Kontrollkästchens **Extract Sample Currency Data** abgeblendet anstatt ausgewählt ist, verwendet der Task die Protokolleinstellungen des übergeordneten Containers. In diesem Fall können Sie die taskspezifischen Protokollereignisse nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="edf44-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="edf44-124">Wählen Sie auf der Registerkarte **Details** in der Spalte **Ereignisse** die Ereignisse **PipelineExecutionPlan** und **PipelineExecutionTrees** aus.</span><span class="sxs-lookup"><span data-stu-id="edf44-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="edf44-125">Klicken Sie auf **Erweitert** , um die Details zu überprüfen, die vom Protokollanbieter für jedes Ereignis in das Protokoll geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="edf44-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="edf44-126">Standardmäßig werden alle Informationskategorien für die Ereignisse ausgewählt, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="edf44-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="edf44-127">Klicken Sie auf **Standard** , um die Informationskategorien auszublenden.</span><span class="sxs-lookup"><span data-stu-id="edf44-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="edf44-128">Wählen Sie auf der Registerkarte **Anbieter und Protokolle** in der Spalte **Name den Namen** aus `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="edf44-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="edf44-129">Nach dem Erstellen eines Protokollanbieters für Ihr Paket können Sie diesen optional deaktivieren, um die Protokollierung zeitweise zu deaktivieren, ohne dass Sie einen Protokollanbieter löschen und dann erneut erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="edf44-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="edf44-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="edf44-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="edf44-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="edf44-131">Next Steps</span></span>  
 [<span data-ttu-id="edf44-132">Schritt 3: Testen des Tutorialpakets aus Lektion 3</span><span class="sxs-lookup"><span data-stu-id="edf44-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
