---
title: Debugging gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- debugging stored procedures [Analysis Services]
- stored procedures [Analysis Services], debugging
ms.assetid: 34f51b85-02b3-40dd-bf93-375a9e522385
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4f5971fe611f06a413ca48b2bc91237a8c87ee8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700431"
---
# <a name="debugging-stored-procedures"></a><span data-ttu-id="8853f-102">Debuggen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="8853f-102">Debugging Stored Procedures</span></span>
  <span data-ttu-id="8853f-103">Gespeicherte [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Prozeduren sind eigentlich CLR- oder COM-Bibliotheken (normalerweise DLLs), die in C# (oder in einer anderen CLR- oder COM-Sprache) geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="8853f-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stored procedures are actually CLR or COM libraries (normally DLLs) that are written in C# (or any other CLR or COM language).</span></span> <span data-ttu-id="8853f-104">Das Debuggen einer gespeicherten Prozedur entspricht also im Wesentlichen dem Debuggen jeder anderen Anwendung in der Debugumgebung von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8853f-104">Therefore, debugging a stored procedure is much like debugging any other application in the Visual Studio debugging environment.</span></span> <span data-ttu-id="8853f-105">Sie debuggen gespeicherte Prozeduren in der Visual Studio-Entwicklungsumgebung mithilfe integrierter Debugfunktionen.</span><span class="sxs-lookup"><span data-stu-id="8853f-105">You debug stored procedures in the Visual Studio development environment using the integrated debugging functions.</span></span> <span data-ttu-id="8853f-106">Mit diesen können Sie an Prozedurspeicherorten stoppen, Speicher inspizieren und Werte registrieren, Variablen ändern, den Nachrichtenverkehr beobachten und einen genauen Blick auf das Funktionieren des Codes werfen.</span><span class="sxs-lookup"><span data-stu-id="8853f-106">These allow you to stop at procedure locations, inspect memory and register values, change variables, observe message traffic and get a close look at how your code works.</span></span>  
  
### <a name="to-debug-a-stored-procedure"></a><span data-ttu-id="8853f-107">So debuggen Sie eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="8853f-107">To debug a stored procedure</span></span>  
  
1.  <span data-ttu-id="8853f-108">Öffnen Sie das zum Erstellen der DLL verwendete Projekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8853f-108">Open the project used to create the DLL in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="8853f-109">Erstellen Sie Breakpoints in der Methode oder Funktion entsprechend der zu debuggenden Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8853f-109">Create breakpoints in the method or function corresponding to the procedure you want to debug.</span></span>  
  
3.  <span data-ttu-id="8853f-110">Verwenden Sie Visual Studio, um einen Debugbuild einer DLL für gespeicherte Prozeduren zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8853f-110">Use Visual Studio to create a debug build of a stored procedure DLL.</span></span>  
  
4.  <span data-ttu-id="8853f-111">Stellen Sie die DLL auf dem Server bereit.</span><span class="sxs-lookup"><span data-stu-id="8853f-111">Deploy the DLL to the server.</span></span> <span data-ttu-id="8853f-112">Weitere Informationen zum Bereitstellen der dll auf dem Server finden Sie unter [Erstellen von gespeicherten Prozeduren](creating-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8853f-112">For more information about deploying the DLL to the server, see [Creating Stored Procedures](creating-stored-procedures.md).</span></span>  
  
5.  <span data-ttu-id="8853f-113">Sie benötigen eine Anwendung, um die zu testende gespeicherte Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8853f-113">You need an application that calls the stored procedure that you want to test.</span></span> <span data-ttu-id="8853f-114">Wenn Sie keine solche zur Verfügung haben, können Sie mit dem MDX-Abfrage-Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine MDX-Abfrage erstellen, um die zu testende gespeicherte Prozedur aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="8853f-114">If you do not have one ready, you can use the MDX Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create an MDX query that calls the stored procedure that you want to test.</span></span>  
  
6.  <span data-ttu-id="8853f-115">Hängen Sie in Visual Studio den Debugger an den [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Prozess (Msmdsrv.exe) an.</span><span class="sxs-lookup"><span data-stu-id="8853f-115">In Visual Studio, attach to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process (Msmdsrv.exe).</span></span>  
  
    1.  <span data-ttu-id="8853f-116">Wählen Sie im Menü **Debuggen** die Option **attatch toprocess**.</span><span class="sxs-lookup"><span data-stu-id="8853f-116">From the **Debug** menu, choose **Attatch toProcess**.</span></span>  
  
    2.  <span data-ttu-id="8853f-117">Wählen Sie im Dialogfeld " **attatch toprocess** " die Option **Prozesse aller Benutzer anzeigen aus**.</span><span class="sxs-lookup"><span data-stu-id="8853f-117">In the **Attatch toProcess** dialog box, select **Show processes from all users**.</span></span>  
  
    3.  <span data-ttu-id="8853f-118">Klicken Sie in der Liste **Verfügbare Prozesse** in der Spalte **verarbeiten** auf **Msmdsrv.exe**.</span><span class="sxs-lookup"><span data-stu-id="8853f-118">In the **Available Processes** list, in the **Process** column, click **Msmdsrv.exe**.</span></span> <span data-ttu-id="8853f-119">Werden auf dem Server mehrere Instanzen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ausgeführt, müssen Sie den Prozess mithilfe der ID der Instanz, die Sie verwenden wollen, identifizieren.</span><span class="sxs-lookup"><span data-stu-id="8853f-119">If there is more than one instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] running on the server, you need to identify the process by the ID of the instance you want to use.</span></span>  
  
    4.  <span data-ttu-id="8853f-120">Stellen Sie sicher, dass im Textfeld **Anfügen an** der entsprechende Programmtyp ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8853f-120">In the **Attach to** text box, make sure that the appropriate program type is selected.</span></span> <span data-ttu-id="8853f-121">Klicken Sie für eine CLR-DLL auf **auswählen**, klicken Sie dann auf **Diese Codetypen debuggen**, klicken Sie auf **verwaltet**und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8853f-121">For a CLR DLL, click **Select**, then click **Debug these code types**, then click **Managed**, then click **OK**.</span></span> <span data-ttu-id="8853f-122">Klicken Sie für eine com-dll auf **auswählen**, klicken Sie dann auf **Diese Codetypen debuggen** **, klicken Sie auf System**eigen und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8853f-122">For a COM DLL, click **Select**, then click **Debug these code types**, then click **Native**, then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="8853f-123">Klicken Sie auf **Anfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="8853f-123">Click **Attach**.</span></span>  
  
7.  <span data-ttu-id="8853f-124">Rufen Sie in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] das Programm oder MDX-Skript zum Aufrufen der gespeicherten Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="8853f-124">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], invoke the program or MDX script that calls the stored procedure.</span></span> <span data-ttu-id="8853f-125">Der Debugger bricht um, wenn er eine Zeile mit einem Breakpoint erreicht.</span><span class="sxs-lookup"><span data-stu-id="8853f-125">The debugger breaks when it reaches a line containing a breakpoint.</span></span> <span data-ttu-id="8853f-126">Sie können Variablen im Überwachungsfenster auswerten, Lokale anzeigen und den Code schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="8853f-126">You can evaluate variables in the watch window, view locals, and step through the code.</span></span>  
  
 <span data-ttu-id="8853f-127">Wenn Sie beim Debuggen einer Bibliothek Probleme haben, stellen Sie sicher, dass die entsprechende Programmdatenbankdatei (PDB-Datei) an den Bereitstellungsspeicherort auf dem Server kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8853f-127">If you have problems debugging a library, make sure that the corresponding program database (PDB) file was copied to the deployment location on the server.</span></span> <span data-ttu-id="8853f-128">Wurde diese Datei bei der Registrierung oder Bereitstellung nicht kopiert, müssen Sie sie manuell an denselben Speicherort wie die DLL kopieren.</span><span class="sxs-lookup"><span data-stu-id="8853f-128">If this file was not copied during registration or deployment, you must copy it manually to the same location as the DLL.</span></span> <span data-ttu-id="8853f-129">Bei systemeigenem Code (COM-DLL) ist die PDB-Datei im Unterverzeichnis \Debug gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8853f-129">For native code (COM DLL), the PDB file resides in the \debug subdirectory.</span></span> <span data-ttu-id="8853f-130">Bei verwaltetem Code (CLR-DLL) ist sie im Unterverzeichnis \WINDEBUG gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8853f-130">For managed code (CLR DLL), it resides in the \WINDEBUG subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8853f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8853f-131">See Also</span></span>  
 <span data-ttu-id="8853f-132">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="8853f-132">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="8853f-133">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="8853f-133">Defining Stored Procedures</span></span>](defining-stored-procedures.md)  
  
  
