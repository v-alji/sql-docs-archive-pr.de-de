---
title: 'Gewusst wie: Debuggen von benutzerdefinierten Assemblys | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services], debugging
- debugging custom assemblies [Reporting Services]
- troubleshooting [Reporting Services], custom assemblies
ms.assetid: 3a3215b3-548c-4474-81ba-3a98dd3912bf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b5f9f5a4595d59cce98da4f753422cd07529926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717533"
---
# <a name="how-to-debug-custom-assemblies"></a><span data-ttu-id="a9fc2-102">Gewusst wie: Debuggen von benutzerdefinierten Assemblys</span><span class="sxs-lookup"><span data-stu-id="a9fc2-102">How to: Debug Custom Assemblies</span></span>
  <span data-ttu-id="a9fc2-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Bietet mehrere Debuggingtools, mit denen Sie den benutzerdefinierten Assemblycode analysieren und Fehler darin suchen können.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your custom assembly code and locate errors in it.</span></span> <span data-ttu-id="a9fc2-104">Welches Tool dafür am besten geeignet ist, hängt von Ihrer Zielsetzung ab.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-104">The best tool to use will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="a9fc2-105">In diesem Beispiel wird [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-105">This example uses [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span>  
  
 <span data-ttu-id="a9fc2-106">Am besten können Sie benutzerdefinierte Assemblys für [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] entwerfen, entwickeln und testen, wenn Sie eine Projektmappe erstellen, die sowohl Ihre Testberichte als auch Ihre benutzerdefinierte Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-106">The recommended way to design, develop, and test custom assemblies for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is to create a solution that contains both your test reports and your custom assembly.</span></span>  
  
### <a name="to-debug-assemblies-using-a-single-instance-of-visual-studio"></a><span data-ttu-id="a9fc2-107">So debuggen Sie Assemblys mithilfe einer Instanz von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9fc2-107">To debug assemblies using a single instance of Visual Studio</span></span>  
  
1.  <span data-ttu-id="a9fc2-108">So legen Sie ein neues Berichtsmodellprojekt mithilfe von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-108">Create a new report project using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
     <span data-ttu-id="a9fc2-109">Während Sie ein Berichtsprojekt erstellen, wird von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] auch eine Projektmappe für das Projekt angelegt.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-109">At the time you create a report project, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] also creates a solution to contain it.</span></span>  
  
2.  <span data-ttu-id="a9fc2-110">Fügen Sie der vorhandenen Projektmappe ein neues Klassenbibliotheksprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-110">Add a new Class Library project to the existing solution.</span></span> <span data-ttu-id="a9fc2-111">Stellen Sie sicher, dass das Berichtsprojekt als Startprojekt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-111">Make sure that the report project is set as the startup project.</span></span> <span data-ttu-id="a9fc2-112">Weitere Informationen hierzu finden Sie in Ihrer [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-112">For more information about how to accomplish this, see your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
3.  <span data-ttu-id="a9fc2-113">Wählen Sie die Projektmappe im Projektmappen-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-113">In Solution Explorer, select the solution.</span></span>  
  
4.  <span data-ttu-id="a9fc2-114">Klicken Sie im Menü **Ansicht** auf die Option **Eigenschaftenseiten**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-114">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="a9fc2-115">Das Dialogfeld **Eigenschaftenseiten** der Projektmappe wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-115">The **Solution Property Pages** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="a9fc2-116">Wenn nötig, öffnen Sie im linken Bereich **Allgemeine Eigenschaften**, und klicken Sie auf **Projektabhängigkeiten**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-116">In the left pane, expand **Common Properties** if necessary, and click **Project Dependencies**.</span></span> <span data-ttu-id="a9fc2-117">Wählen Sie das Berichtsprojekt aus der Dropdownliste **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-117">Select the report project from the **Project** drop-down list.</span></span> <span data-ttu-id="a9fc2-118">Wählen Sie das Assemblyprojekt in der Liste der **Abhängigkeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-118">Select your assembly project in the **Depends On** list.</span></span>  
  
6.  <span data-ttu-id="a9fc2-119">Klicken Sie auf **OK**, um die Änderungen zu speichern, und schließen Sie das Dialogfeld **Eigenschaftenseiten**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-119">Click **OK** to save the changes, and close the **Property Pages** dialog.</span></span>  
  
7.  <span data-ttu-id="a9fc2-120">Wählen Sie im Projektmappen-Explorer Ihr benutzerdefiniertes Assemblyprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-120">In Solution Explorer, select your custom assembly project.</span></span>  
  
8.  <span data-ttu-id="a9fc2-121">Klicken Sie im Menü **Ansicht** auf die Option **Eigenschaftenseiten**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-121">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="a9fc2-122">Das Dialogfeld der **Eigenschaftenseite des Projekts** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-122">The **Project Property Pages** dialog box opens.</span></span>  
  
9. <span data-ttu-id="a9fc2-123">Klicken Sie in einem C#-Projekt auf die Registerkarte **Erstellen** und in einem [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]-Projekt auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-123">Click the **Build** tab if you're in a C# project or the **Compile** tab if you're in a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] project.</span></span>  
  
10. <span data-ttu-id="a9fc2-124">Geben Sie auf der Seite **Build** / **Compile (buildkompilierung** ) den Pfad zum Berichts-Designer Ordner ein.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-124">On the **Build**/**Compile** page, enter the path to the Report Designer folder.</span></span> <span data-ttu-id="a9fc2-125">Standardmäßig ist dies C:\Programme\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) im Textfeld **Ausgabepfad**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-125">By default, this is C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) in the **Output Path** text box.</span></span> <span data-ttu-id="a9fc2-126">Damit wird eine aktualisierte Version der benutzerdefinierten Assembly erstellt und direkt im Berichts-Designer bereitgestellt, bevor der Bericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-126">This builds and deploys an updated version of your custom assembly directly to Report Designer before your report is executed.</span></span>  
  
11. <span data-ttu-id="a9fc2-127">Wenn Sie den Bericht entworfen und die benutzerdefinierte Assembly entwickelt haben, legen Sie die Breakpoints im Code der benutzerdefinierten Assembly fest.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-127">Once you have designed your report and developed your custom assembly, set breakpoints in your custom assembly code.</span></span>  
  
12. <span data-ttu-id="a9fc2-128">Führen Sie den Bericht unter dem **DebugLocal**-Modus aus, indem Sie die F5-TASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-128">Run the report under **DebugLocal** mode by pressing the F5 key.</span></span> <span data-ttu-id="a9fc2-129">Wenn der Bericht in der Popup-Vorschau ausgeführt wird, sucht der Debugger alle Breakpoints, die dem ausführbaren Code in Ihrer Assembly entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-129">When the report executes in the pop-up preview window, the debugger hits any breakpoints that correspond to executable code in your assembly.</span></span> <span data-ttu-id="a9fc2-130">Verwenden Sie F11, um den Code der benutzerdefinierten Assembly schrittweise zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-130">Use F11 to step through your custom assembly code.</span></span>  
  
### <a name="to-debug-assemblies-using-two-instances-of-visual-studio"></a><span data-ttu-id="a9fc2-131">So debuggen Sie Assemblys mithilfe von zwei Instanzen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a9fc2-131">To debug assemblies using two instances of Visual Studio</span></span>  
  
1.  <span data-ttu-id="a9fc2-132">Starten Sie [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], und öffnen Sie das Projekt der benutzerdefinierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-132">Start [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and open your custom assembly project.</span></span>  
  
2.  <span data-ttu-id="a9fc2-133">Erstellen Sie das Projekt, und stellen Sie die benutzerdefinierte Assembly und die dazugehörige PDB-Datei im Berichts-Designer bereit.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-133">Build the project, and deploy your custom assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="a9fc2-134">Weitere Informationen zur Bereitstellung finden Sie unter [Deploying a Custom Assembly (Bereitstellen einer benutzerdefinierten Assembly)](deploying-a-custom-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="a9fc2-134">For more information about deployment, see [Deploying a Custom Assembly](deploying-a-custom-assembly.md).</span></span>  
  
3.  <span data-ttu-id="a9fc2-135">Öffnen Sie ein Berichtsprojekt, das Ihre benutzerdefinierte Assembly verwendet, ohne den Code der benutzerdefinierten Assembly in einer anderen Instanz von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-135">Open up a report project that uses your custom assembly while leaving your custom assembly code open in a separate instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="a9fc2-136">Wechseln Sie zur [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]-Instanz, die das Projekt für die benutzerdefinierte Assembly enthält, und legen Sie einige Breakpoints im Code fest.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-136">Navigate to the instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] that contains your custom assembly project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="a9fc2-137">Während das Projekt der benutzerdefinierten Assembly noch immer das aktive Fenster ist, klicken Sie im Menü **Debuggen** auf **An den Prozess anhängen**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-137">With the custom assembly project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="a9fc2-138">Das Dialogfeld **An den Prozess anhängen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-138">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="a9fc2-139">Wählen Sie aus der Liste der Prozesse den Prozess „devenv.exe“ aus, der dem Berichtsprojekt entspricht, und klicken Sie auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-139">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="a9fc2-140">Definieren Sie die Ausdrücke, die Sie im Bericht aus der benutzerdefinierten Assembly verwenden möchten, und entwerfen Sie Ihren Bericht.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-140">Define the expressions that you will use in your report from your custom assembly and design your report.</span></span>  
  
8.  <span data-ttu-id="a9fc2-141">Wenn Sie den Bericht entworfen haben, klicken Sie auf die Registerkarte **Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-141">When you are finished designing your report, click the **Preview** tab.</span></span>  
  
     <span data-ttu-id="a9fc2-142">Der Bericht wird ausgeführt, und der Code der benutzerdefinierten Assembly sollte an den vordefinierten Breakpoints unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-142">The report executes, and the custom assembly code should break at your predefined break points.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9fc2-143">Bei Verwendung der Registerkarte **Vorschau** werden keine Codeberechtigungen für die Assembly erzwungen.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-143">Using the **Preview** tab does not enforce code permissions for the assembly.</span></span> <span data-ttu-id="a9fc2-144">Sie können einen vollständigen Test, der alle Fehler der Codezugriffssicherheit enthält, durchführen, indem Sie das Berichtsprojekt unter der Konfigurationseinstellung **DebugLocal** starten.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-144">For a complete test, which includes any code access security errors, start the report project under the **DebugLocal** configuration setting.</span></span>  
  
9. <span data-ttu-id="a9fc2-145">Gehen Sie den Code schrittweise mit der F11-Taste durch.</span><span class="sxs-lookup"><span data-stu-id="a9fc2-145">Step through your code using the F11 key.</span></span> <span data-ttu-id="a9fc2-146">Weitere Informationen zum Debuggen mithilfe von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9fc2-146">For more information about debugging using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fc2-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9fc2-147">See Also</span></span>  
 [<span data-ttu-id="a9fc2-148">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="a9fc2-148">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
