---
title: Erstellen von Paketen in SQL Server Data Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: bb3c085b-1458-49fa-8348-6a76b6e97ea6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 330e0271421dc620f7c4fad9c6944331ebe94881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616606"
---
# <a name="create-packages-in-sql-server-data-tools"></a><span data-ttu-id="47337-102">Erstellen von Paketen in SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="47337-102">Create Packages in SQL Server Data Tools</span></span>
  <span data-ttu-id="47337-103">Die Pakete, die Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] mit dem [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer erstellen, werden im Dateisystem gespeichert.</span><span class="sxs-lookup"><span data-stu-id="47337-103">The packages that you create in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer are saved to the file system.</span></span> <span data-ttu-id="47337-104">Zum Speichern eines Pakets in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oder im Paketspeicher müssen Sie eine Kopie des Pakets speichern.</span><span class="sxs-lookup"><span data-stu-id="47337-104">To save a package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store, you need to save a copy of the package.</span></span> <span data-ttu-id="47337-105">Weitere Informationen finden Sie unter [Erstellen einer Kopie eines Miningmodells](../../2014/integration-services/save-a-copy-of-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="47337-105">For more information, see [Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md).</span></span>  
  
 <span data-ttu-id="47337-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]können Sie mit einer der folgenden Methoden ein neues Paket erstellen:</span><span class="sxs-lookup"><span data-stu-id="47337-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can create a new package by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="47337-107">Verwenden der Paketvorlage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47337-107">Use the package template that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes.</span></span>  
  
-   <span data-ttu-id="47337-108">Verwenden einer benutzerdefinierten Vorlage</span><span class="sxs-lookup"><span data-stu-id="47337-108">Use a custom template</span></span>  
  
     <span data-ttu-id="47337-109">Sie müssen nur die als Vorlage zu verwendenden benutzerdefinierten Pakete zum Erstellen neuer Pakete in den DataTransformationItems-Ordner kopieren.</span><span class="sxs-lookup"><span data-stu-id="47337-109">To use custom packages as templates for creating new packages, you simply copy them to the DataTransformationItems folder.</span></span> <span data-ttu-id="47337-110">Dieser Ordner befindet sich standardmäßig unter C:\Programme\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span><span class="sxs-lookup"><span data-stu-id="47337-110">By default, this folder is in C:\Program Files\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\ProjectItems\DataTransformationProject.</span></span>  
  
-   <span data-ttu-id="47337-111">Kopieren Sei ein vorhandenes Paket.</span><span class="sxs-lookup"><span data-stu-id="47337-111">Copy an existing package.</span></span>  
  
     <span data-ttu-id="47337-112">Wenn vorhandene Pakete Funktionen enthalten, die Sie wiederverwenden möchten, können Sie die Ablaufsteuerung und die Datenflüsse des neuen Pakets schneller erstellen, indem Sie aus den anderen Paketen Objekte kopieren und diese im neuen Paket einfügen.</span><span class="sxs-lookup"><span data-stu-id="47337-112">If existing packages include functionality that you want to reuse, you can build the control flow and data flows in the new package more quickly by copying and pasting objects from other packages.</span></span> <span data-ttu-id="47337-113">Weitere Informationen zu Kopier- und Einfügevorgängen in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] finden Sie unter [Wiederverwenden von Paketobjekten](reuse-of-package-objects.md).</span><span class="sxs-lookup"><span data-stu-id="47337-113">For more information about using copy and paste in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects, see [Reuse of Package Objects](reuse-of-package-objects.md).</span></span>  
  
     <span data-ttu-id="47337-114">Beim Erstellen eines neuen Pakets durch Kopieren eines vorhandenen Pakets oder mithilfe eines benutzerdefinierten Pakets, welches als Vorlage dient, werden Name und GUID des vorhandenen Pakets ebenfalls kopiert.</span><span class="sxs-lookup"><span data-stu-id="47337-114">If you create a new package by copying an existing package or by using a custom package as a template, the name and the GUID of the existing package are copied as well.</span></span> <span data-ttu-id="47337-115">Sie sollten den Namen und GUID des neuen Pakets aktualisieren, um das neue Paket vom Paket, von dem es kopiert wurde, zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="47337-115">You should update the name and the GUID of the new package to help differentiate it from the package from which it was copied.</span></span> <span data-ttu-id="47337-116">Beispielsweise können bei Paketen mit demselben GUID die Pakete, zu denen die Protokolldaten gehören, schwieriger identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="47337-116">For example, if packages have the same GUID, it is more difficult to identify the package to which log data belongs.</span></span> <span data-ttu-id="47337-117">Sie können die GUID in der `ID`-Eigenschaft neu generieren und den Wert der `Name`-Eigenschaft mithilfe des Eigenschaftenfensters in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="47337-117">You can regenerate the GUID in the `ID` property and update the value of the `Name` property by using the Properties window in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="47337-118">Weitere Informationen finden Sie unter [Festlegen von Paketeigenschaften](set-package-properties.md) und [dtutil (Hilfsprogramm)](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="47337-118">For more information, see [Set Package Properties](set-package-properties.md) and [dtutil Utility](dtutil-utility.md).</span></span>  
  
-   <span data-ttu-id="47337-119">Verwenden Sie ein benutzerdefiniertes Paket, das Sie als Vorlage festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="47337-119">Use a custom package that you have designated as a template.</span></span>  
  
-   <span data-ttu-id="47337-120">Ausführen des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Import/Export-Assistenten</span><span class="sxs-lookup"><span data-stu-id="47337-120">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard</span></span>  
  
     <span data-ttu-id="47337-121">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Import/Export-Assistent erstellt ein vollständiges Paket für einen einfachen Import oder Export.</span><span class="sxs-lookup"><span data-stu-id="47337-121">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard creates a complete package for a simple import or export.</span></span> <span data-ttu-id="47337-122">Dieser Assistent konfiguriert die Verbindungen, die Quelle und das Ziel und fügt alle Datentransformationen hinzu, die Sie zum sofortigen Ausführen des Imports oder Exports benötigen.</span><span class="sxs-lookup"><span data-stu-id="47337-122">This wizard configures the connections, source, and destination, and adds any data transformations that are required to let you run the import or export immediately.</span></span> <span data-ttu-id="47337-123">Optional können Sie das Paket speichern, um es zu einem späteren Zeitpunkt auszuführen oder in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]zu verfeinern und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="47337-123">You can optionally save the package to run it again later, or to refine and enhance the package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="47337-124">Wenn Sie das Paket speichern, müssen Sie es jedoch zunächst einem vorhandenen [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt hinzufügen, bevor Sie das Paket ändern oder in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]ausführen können.</span><span class="sxs-lookup"><span data-stu-id="47337-124">However, if you save the package, you must add the package to an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project before you can change the package or run the package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="47337-125">Die folgenden Prozeduren beschreiben, wie Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] ein Paket erstellen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="47337-125">The following procedures describe how to create or delete a package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="47337-126">Unter [Erstellen eines Basispakets (SQL Server-Video)](https://go.microsoft.com/fwlink/?LinkId=131023)können Sie ein Video abspielen, in dem das Erstellen eines Basispakets mithilfe der Standardpaketvorlage veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="47337-126">For a video that demonstrates how to create a basic package using the default package template, see [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023).</span></span>  
  
### <a name="to-create-a-package-in-sql-server-data-tools-using-the-package-template"></a><span data-ttu-id="47337-127">So erstellen Sie ein Paket in SQL Server-Datentools mithilfe der Paketvorlage</span><span class="sxs-lookup"><span data-stu-id="47337-127">To create a package in SQL Server Data Tools using the Package Template</span></span>  
  
1.  <span data-ttu-id="47337-128">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, in dem Sie ein Paket erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="47337-128">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you want to create a package.</span></span>  
  
2.  <span data-ttu-id="47337-129">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Ordner **SSIS-Pakete** , und klicken Sie dann auf **Neues SSIS-Paket**.</span><span class="sxs-lookup"><span data-stu-id="47337-129">In Solution Explorer, right-click the **SSIS Packages** folder, and then click **New SSIS Package**.</span></span>  
  
3.  <span data-ttu-id="47337-130">Fügen Sie dem Paket optional Ablaufsteuerungen, Datenflusstasks und Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="47337-130">Optionally, add control flow, data flow tasks, and event handlers to the package.</span></span> <span data-ttu-id="47337-131">Weitere Informationen finden Sie unter [Ablaufsteuerung](control-flow/control-flow.md), [Datenfluss](data-flow/data-flow.md) und [Integration Services-Ereignishandler &#40;SSIS&#41;](integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="47337-131">For more information, see [Control Flow](control-flow/control-flow.md), [Data Flow](data-flow/data-flow.md), and [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md).</span></span>  
  
4.  <span data-ttu-id="47337-132">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das neue Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="47337-132">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47337-133">Es ist möglich, ein leeres Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="47337-133">You can save an empty package.</span></span>  
  
  