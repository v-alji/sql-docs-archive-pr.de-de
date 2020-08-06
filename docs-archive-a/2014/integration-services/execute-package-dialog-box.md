---
title: Dialog Feld "Paket ausführen" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageexecute.f1
- sql12.ssis.ssms.executepackage.f1
ms.assetid: 4f7a806d-4867-4d1f-bc65-b00c1caee7b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b60381054c781cd59f0a9d434710663b72d616c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618798"
---
# <a name="execute-package-dialog-box"></a><span data-ttu-id="f89c5-102">Execute Package Dialog Box</span><span class="sxs-lookup"><span data-stu-id="f89c5-102">Execute Package Dialog Box</span></span>
  <span data-ttu-id="f89c5-103">Mit dem Dialogfeld **Paket ausführen** können Sie ein Paket auszuführen, das auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f89c5-103">Use the **Execute Package** dialog box to run a package that is stored on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="f89c5-104">Ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket kann Parameter enthalten, die auf in Umgebungsvariablen gespeicherte Werte verweisen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-104">An [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package may contain parameters that values stored in environment variables.</span></span> <span data-ttu-id="f89c5-105">Vor dem Ausführen eines solchen Pakets müssen Sie angeben, mit welcher Umgebung die Werte für die Umgebungsvariablen bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-105">Before executing such a package, you must specify which environment will be used to provide the environment variable values.</span></span> <span data-ttu-id="f89c5-106">Ein Projekt kann mehrere Umgebungen enthalten, aber nur eine Umgebung kann zum Binden von Umgebungsvariablenwerten bei der Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f89c5-106">A project may contain multiple environments, but only one environment can be used for binding environment variable values at the time of execution.</span></span> <span data-ttu-id="f89c5-107">Wenn keine Umgebungsvariablen im Paket verwendet werden, ist auch keine Umgebung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f89c5-107">If no environment variables are used in the package, an environment is not required.</span></span>  
  
 <span data-ttu-id="f89c5-108">Was möchten Sie tun?</span><span class="sxs-lookup"><span data-stu-id="f89c5-108">What do you want to do?</span></span>  
  
-   [<span data-ttu-id="f89c5-109">Öffnen des Dialogfelds "Paket ausführen"</span><span class="sxs-lookup"><span data-stu-id="f89c5-109">Open the Execute Package dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="f89c5-110">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="f89c5-110">Set the Options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="f89c5-111">Festlegen der Optionen auf der Registerkarte "Parameter"</span><span class="sxs-lookup"><span data-stu-id="f89c5-111">Set the Options on the Parameters tab</span></span>](#parameters)  
  
-   [<span data-ttu-id="f89c5-112">Festlegen der Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="f89c5-112">Set the Options on the Connection Managers tab</span></span>](#connection)  
  
-   [<span data-ttu-id="f89c5-113">Festlegen der Optionen auf der Registerkarte "Erweitert"</span><span class="sxs-lookup"><span data-stu-id="f89c5-113">Set the Options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="f89c5-114">Erstellen der Optionen im Dialogfeld Paket ausführen</span><span class="sxs-lookup"><span data-stu-id="f89c5-114">Scripting the Options in the Execute Package Dialog Box</span></span>](#script)  
  
##  <a name="open-the-execute-package-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="f89c5-115">Öffnen des Dialogfelds "Paket ausführen"</span><span class="sxs-lookup"><span data-stu-id="f89c5-115">Open the Execute Package dialog box</span></span>  
  
1.  <span data-ttu-id="f89c5-116">Stellen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]eine Verbindung zum [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server her.</span><span class="sxs-lookup"><span data-stu-id="f89c5-116">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="f89c5-117">Sie stellen eine Verbindung mit der [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]-Instanz her, die die SSISDB-Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="f89c5-117">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="f89c5-118">Erweitern Sie im Objekt-Explorer die Struktur, um den Knoten **Integration Services-Kataloge** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-118">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="f89c5-119">Erweitern Sie den **SSISDB** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="f89c5-119">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="f89c5-120">Erweitern Sie den Ordner, der das auszuführende Paket enthält.</span><span class="sxs-lookup"><span data-stu-id="f89c5-120">Expand the folder that contains the package you want to run.</span></span>  
  
5.  <span data-ttu-id="f89c5-121">Klicken Sie mit der rechten Maustaste auf das Paket, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f89c5-121">Right-click the package, and then click **Execute**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="f89c5-122">Festlegen der Optionen auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="f89c5-122">Set the Options on the General page</span></span>  
 <span data-ttu-id="f89c5-123">Wählen Sie **Umgebung** aus, um die Umgebung anzugeben, die für das ausgeführte Paket angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f89c5-123">Select **Environment** to specify the environment that is applied with the package is run.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-tab"></a><a name="parameters"></a> <span data-ttu-id="f89c5-124">Festlegen der Optionen auf der Registerkarte "Parameter"</span><span class="sxs-lookup"><span data-stu-id="f89c5-124">Set the Options on the Parameters tab</span></span>  
 <span data-ttu-id="f89c5-125">Verwenden Sie die Registerkarte **Parameter** , um die Parameterwerte zu ändern, die bei der Ausführung des Pakets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f89c5-125">Use the **Parameters** tab to modify the parameter values that are used when the package runs.</span></span>  
  
##  <a name="set-the-options-on-the-connection-managers-tab"></a><a name="connection"></a> <span data-ttu-id="f89c5-126">Festlegen der Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="f89c5-126">Set the Options on the Connection Managers tab</span></span>  
 <span data-ttu-id="f89c5-127">Verwenden Sie die Registerkarte "Verbindungs-Manager", um die Eigenschaften des jeweiligen Paketverbindungs-Managers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-127">Use the Connection Managers tab to set the properties of the package connection manager(s).</span></span>  
  
##  <a name="set-the-options-on-the-advanced-tab"></a><a name="advanced"></a> <span data-ttu-id="f89c5-128">Festlegen der Optionen auf der Registerkarte "Erweitert"</span><span class="sxs-lookup"><span data-stu-id="f89c5-128">Set the Options on the Advanced tab</span></span>  
 <span data-ttu-id="f89c5-129">Verwenden Sie die Registerkarte "Erweitert", um Eigenschaften und andere Paketeinstellungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f89c5-129">Use the Advanced tab to manage properties and other package settings.</span></span>  
  
 <span data-ttu-id="f89c5-130">**Hinzufügen**, **Bearbeiten**, **Entfernen**</span><span class="sxs-lookup"><span data-stu-id="f89c5-130">**Add**, **Edit**, **Remove**</span></span>  
 <span data-ttu-id="f89c5-131">Klicken Sie auf die entsprechende Option, um eine Eigenschaft hinzuzufügen, zu bearbeiten oder zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-131">Click to add, edit, or remove a property.</span></span>  
  
 <span data-ttu-id="f89c5-132">**Protokolliergrad**</span><span class="sxs-lookup"><span data-stu-id="f89c5-132">**Logging level**</span></span>  
 <span data-ttu-id="f89c5-133">Wählen Sie den Protokolliergrad für die Paketausführung aus.</span><span class="sxs-lookup"><span data-stu-id="f89c5-133">Select the logging level for the package execution.</span></span> <span data-ttu-id="f89c5-134">Weitere Informationen finden Sie unter [catalog.set_execution_parameter_value &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f89c5-134">For more information, see [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database).</span></span>  
  
 <span data-ttu-id="f89c5-135">**Speichern bei Fehlern**</span><span class="sxs-lookup"><span data-stu-id="f89c5-135">**Dump on errors**</span></span>  
 <span data-ttu-id="f89c5-136">Geben Sie an, ob eine Dumpdatei erstellt wird, wenn Fehler während der Paketausführung auftreten.</span><span class="sxs-lookup"><span data-stu-id="f89c5-136">Specify whether a dump file is created when errors occur during the package execution.</span></span> <span data-ttu-id="f89c5-137">Weitere Informationen finden Sie unter [Generieren von Dumpdateien für die Paketausführung](troubleshooting/generating-dump-files-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="f89c5-137">For more information, see [Generating Dump Files for Package Execution](troubleshooting/generating-dump-files-for-package-execution.md).</span></span>  
  
 <span data-ttu-id="f89c5-138">**32-Bit-Laufzeit**</span><span class="sxs-lookup"><span data-stu-id="f89c5-138">**32-bit runtime**</span></span>  
 <span data-ttu-id="f89c5-139">Geben Sie an, dass das Paket auf einem 32-Bit-System ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f89c5-139">Specify that the package will execute on a 32-bit system.</span></span>  
  
##  <a name="scripting-the-options-in-the-execute-package-dialog-box"></a><a name="script"></a> <span data-ttu-id="f89c5-140">Erstellen der Optionen im Dialogfeld Paket ausführen</span><span class="sxs-lookup"><span data-stu-id="f89c5-140">Scripting the Options in the Execute Package Dialog Box</span></span>  
 <span data-ttu-id="f89c5-141">Im Dialogfeld **Paket ausführen** können Sie auch die Schaltfläche **Skript** verwenden, um Code für [!INCLUDE[tsql](../includes/tsql-md.md)] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f89c5-141">While you are in the **Execute Package** dialog box, you can also use the **Script** button on the toolbar to write [!INCLUDE[tsql](../includes/tsql-md.md)] code for you.</span></span> <span data-ttu-id="f89c5-142">Mit dem generierten Skript werden die gespeicherten Prozeduren für [catalog.start_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) mit den gleichen Optionen ausgeführt, die im Dialogfeld **Paket ausführen** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="f89c5-142">The generated script calls the stored procedures [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) with the same options that you have selected in the **Execute Package** dialog box.</span></span> <span data-ttu-id="f89c5-143">Das Skript wird in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]in einem neuen Skriptfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f89c5-143">The script appears in a new script window in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
  
