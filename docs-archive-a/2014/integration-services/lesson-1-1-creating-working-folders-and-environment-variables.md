---
title: 'Schritt 1: Erstellen von Arbeitsordnern und Umgebungsvariablen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45091ba2-ea3d-4399-9814-489d812b42cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 63308d406e230538e5ca8b90dbb55bb802759bd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618147"
---
# <a name="step-1-creating-working-folders-and-environment-variables"></a><span data-ttu-id="71918-102">Schritt 1: Erstellen von Arbeitsordnern und Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="71918-102">Step 1: Creating Working Folders and Environment Variables</span></span>
  <span data-ttu-id="71918-103">In dieser Aufgabe erstellen Sie den Arbeitsordner (C:\DeploymentTutorial) und die neuen Systemumgebungsvariablen (`DataTransfer` und `LoadXMLData`), die in späteren Lernprogrammaufgaben verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71918-103">In this task, you will create the working folder (C:\DeploymentTutorial) and the new system environment variables (`DataTransfer` and `LoadXMLData`) that you will use in later tutorial tasks.</span></span>  
  
 <span data-ttu-id="71918-104">Der Arbeitsordner befindet sich im Stamm von Laufwerk C.</span><span class="sxs-lookup"><span data-stu-id="71918-104">The working folder is at the root of the C drive.</span></span> <span data-ttu-id="71918-105">Bei Bedarf können Sie ein anderes Laufwerk bzw. einen anderen Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="71918-105">If you must use a different drive or location, you can do that.</span></span> <span data-ttu-id="71918-106">Sie müssen sich diesen Speicherort jedoch notieren und immer dann verwenden, wenn im Lernprogramm auf den Speicherort des Arbeitsordners DeploymentTutorial verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71918-106">However, you need to note this location and then use it wherever the tutorial refers to the location of the DeploymentTutorial working folder.</span></span>  
  
 <span data-ttu-id="71918-107">In einer späteren Lektion stellen Sie Pakete bereit, die im Dateisystem in der sysssispackages-Tabelle der msdb-Datenbank von[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="71918-107">In a later lesson, you will deploy packages that are saved to the file system to the sysssispackages table in the msdb[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="71918-108">Idealerweise erfolgt die Bereitstellung der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete auf einem anderen Computer.</span><span class="sxs-lookup"><span data-stu-id="71918-108">Ideally you will deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to a different computer.</span></span> <span data-ttu-id="71918-109">Falls dies nicht möglich ist, können Sie dennoch viel von diesem Lernprogramm profitieren, indem Sie die Pakete auf einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf dem lokalen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71918-109">If that is not possible, you can still learn a lot from doing this tutorial by deploying the packages to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is on the local computer.</span></span> <span data-ttu-id="71918-110">Die Umgebungsvariablen, die auf dem lokalen Computer und dem Zielcomputer verwendet werden, weisen die gleichen Variablennamen auf, doch werden unterschiedliche Werte in den Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="71918-110">The environment variables that are used on the local and destination computers have the same variable names, but different values are stored in the variables.</span></span> <span data-ttu-id="71918-111">So verweist z. B. der Wert der `DataTransfer` -Umgebungsvariablen auf dem lokalen Computer auf den Ordner C:\DeploymentTutorial, während die `DataTransfer` -Umgebungsvariable auf dem Zielcomputer auf den Ordner C:\DeploymentTutorialInstall verweist.</span><span class="sxs-lookup"><span data-stu-id="71918-111">For example, on the local computer, the value of the environment variable `DataTransfer` references the C:\DeploymentTutorial folder, whereas on the target computer the environment variable `DataTransfer` references the C:\DeploymentTutorialInstall folder.</span></span>  
  
 <span data-ttu-id="71918-112">Wenn Sie eine Bereitstellung auf dem lokalen Computer planen, müssen Sie nur einen Satz von Umgebungsvariablen erstellen. Es ist jedoch erforderlich, den Wert der Umgebungsvariablen vor der lokalen Bereitstellung auf einen geeigneten Wert zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="71918-112">If you plan to deploy to the local computer, you need to create only one set of environment variables; however, you will need to update the value of the environment variables to an appropriate value before you do the local deployment.</span></span>  
  
 <span data-ttu-id="71918-113">Wenn Sie planen, die Pakete auf einem anderen Computer bereitzustellen, müssen Sie zwei Sätze von Umgebungsvariablen erstellen: einen Satz für den lokalen Computer und einen Satz für den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="71918-113">If you plan to deploy the packages to a different computer, you must create two sets of environment variables: one set for the local computer, and one set for the destination computer.</span></span> <span data-ttu-id="71918-114">Zum jetzigen Zeitpunkt können Sie nur die Variablen für den Quellcomputer erstellen. Die Variablen für den Zielcomputer müssen später erstellt werden. Sie können die Pakete jedoch erst auf dem Zielcomputer installieren, wenn sowohl der Ordner als auch die Umgebungsvariablen auf dem Zielcomputer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="71918-114">You can create only the variables for the source computer now, and create the variables for the destination computer later, but you must have both the folder and environment variables available on the destination computer before you can install the packages on that computer.</span></span>  
  
### <a name="to-create-the-local-working-folder"></a><span data-ttu-id="71918-115">So erstellen Sie den lokalen Arbeitsordner</span><span class="sxs-lookup"><span data-stu-id="71918-115">To create the local working folder</span></span>  
  
1.  <span data-ttu-id="71918-116">Klicken Sie mit der rechten Maustaste auf das Menü Start, und klicken Sie dann auf Suchen.</span><span class="sxs-lookup"><span data-stu-id="71918-116">Right-click the Start menu, and click Explore.</span></span>  
  
2.  <span data-ttu-id="71918-117">Klicken Sie auf **Lokaler Datenträger (C:)** .</span><span class="sxs-lookup"><span data-stu-id="71918-117">Click **Local Disk (C:)**.</span></span>  
  
3.  <span data-ttu-id="71918-118">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie anschließend auf **Ordner**.</span><span class="sxs-lookup"><span data-stu-id="71918-118">On the **File** menu, point to **New**, and then click **Folder**.</span></span>  
  
4.  <span data-ttu-id="71918-119">Benennen Sie den neuen Ordner in um `DeploymentTutorial` .</span><span class="sxs-lookup"><span data-stu-id="71918-119">Rename New Folder to `DeploymentTutorial`.</span></span>  
  
### <a name="to-create-local-environment-variables"></a><span data-ttu-id="71918-120">So erstellen Sie lokale Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="71918-120">To create local environment variables</span></span>  
  
1.  <span data-ttu-id="71918-121">Klicken Sie im Menü **Start** auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="71918-121">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="71918-122">Doppelklicken Sie in der Systemsteuerung auf **System**.</span><span class="sxs-lookup"><span data-stu-id="71918-122">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="71918-123">Klicken Sie im Dialogfeld **Systemeigenschaften** auf die Registerkarte **Erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="71918-123">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="71918-124">Klicken Sie im Dialogfeld **Umgebungsvariablen** im Bereich **Systemvariablen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="71918-124">In the **Environment Variables** dialog box, in the **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="71918-125">Geben Sie im Dialogfeld **neue System Variable** `DataTransfer` in das Feld **Variablenname** und `C:\DeploymentTutorial\datatransferconfig.dtsconfig` im Feld **Variablen Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="71918-125">In the **New System Variable** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorial\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="71918-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="71918-126">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="71918-127">Klicken Sie erneut auf **neu** , und geben Sie im Feld Variablen `LoadXMLData` **Name** und `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` im Feld **Variablen Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="71918-127">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorial\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="71918-128">Klicken Sie auf **OK** , um das Dialogfeld **Umgebungsvariablen** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="71918-128">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="71918-129">Klicken Sie auf **OK** , um das Dialogfeld **Systemeigenschaften** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="71918-129">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="71918-130">Führen Sie optional einen Neustart des Computers aus.</span><span class="sxs-lookup"><span data-stu-id="71918-130">Optionally, restart your computer.</span></span> <span data-ttu-id="71918-131">Wenn Sie den Computer nicht neu starten, wird der Name der neuen Variablen nicht im Paketkonfigurations-Assistenten angezeigt, kann jedoch verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71918-131">If you do not restart the computer, the name of the new variable will not be displayed in the Package Configuration Wizard, but you can still use it.</span></span>  
  
### <a name="to-create-destination-environment-variables"></a><span data-ttu-id="71918-132">So erstellen Sie Zielumgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="71918-132">To create destination environment variables</span></span>  
  
1.  <span data-ttu-id="71918-133">Klicken Sie im Menü **Start** auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="71918-133">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="71918-134">Doppelklicken Sie in der Systemsteuerung auf **System**.</span><span class="sxs-lookup"><span data-stu-id="71918-134">In Control Panel, double-click **System**.</span></span>  
  
3.  <span data-ttu-id="71918-135">Klicken Sie im Dialogfeld **Systemeigenschaften** auf die Registerkarte **Erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="71918-135">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="71918-136">Klicken Sie im Dialogfeld **Umgebungsvariablen** unter **Systemvariablen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="71918-136">In the **Environment Variables** dialog box, in **System variables** frame, click **New**.</span></span>  
  
5.  <span data-ttu-id="71918-137">Geben Sie im Dialogfeld **neue System Variablen** `DataTransfer` in das Feld **Variablenname** und `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` im Feld **Variablen Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="71918-137">In the **New System Variables** dialog box, type `DataTransfer` in the **Variable name** box, and `C:\DeploymentTutorialInstall\datatransferconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
6.  <span data-ttu-id="71918-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="71918-138">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="71918-139">Klicken Sie erneut auf **neu** , und geben Sie im Feld Variablen `LoadXMLData` **Name** und `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` im Feld **Variablen Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="71918-139">Click **New** again, and type `LoadXMLData` in the **Variable name** box, and `C:\DeploymentTutorialInstall\loadxmldataconfig.dtsconfig` in the **Variable value** box.</span></span>  
  
8.  <span data-ttu-id="71918-140">Klicken Sie auf **OK** , um das Dialogfeld **Umgebungsvariablen** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="71918-140">Click **OK** to exit the **Environment Variables** dialog box.</span></span>  
  
9. <span data-ttu-id="71918-141">Klicken Sie auf **OK** , um das Dialogfeld **Systemeigenschaften** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="71918-141">Click **OK** to exit the **System Properties** dialog box.\</span></span>  
  
10. <span data-ttu-id="71918-142">Führen Sie optional einen Neustart des Computers aus.</span><span class="sxs-lookup"><span data-stu-id="71918-142">Optionally, restart your computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="71918-143">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="71918-143">Next Task in Lesson</span></span>  
 [<span data-ttu-id="71918-144">Schritt 2: Erstellen des Bereitstellungsprojekts</span><span class="sxs-lookup"><span data-stu-id="71918-144">Step 2: Creating the Deployment Project</span></span>](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
<span data-ttu-id="71918-145">![Integration Services Symbol (klein)](media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="71918-145">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="71918-146">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="71918-146">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="71918-147">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="71918-147">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="71918-148">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="71918-148">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
