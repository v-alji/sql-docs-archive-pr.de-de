---
title: Editor für den Datenprofilerstellungs-Task (Seite „Allgemein“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619264"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="51137-102">Editor für den Datenprofilerstellungs-Task (Seite "Allgemein")</span><span class="sxs-lookup"><span data-stu-id="51137-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="51137-103">Verwenden Sie die Seite **Allgemein** im **Editor für den Datenprofilerstellungs-Task** , um die folgenden Optionen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="51137-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="51137-104">Geben Sie das Ziel für die Profilausgabe an.</span><span class="sxs-lookup"><span data-stu-id="51137-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="51137-105">Verwenden Sie die Standardeinstellungen, um den Task der Profilerstellung für eine einzelne Tabelle oder Sicht zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="51137-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="51137-106">Weitere Informationen zum Verwenden des Datenprofilerstellungs-Tasks finden Sie unter [Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="51137-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="51137-107">Weitere Informationen zum Verwenden des Datenprofil-Viewers zum Analysieren der Ausgabe des Datenprofilerstellungs-Tasks finden Sie unter [Datenprofil-Viewer](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="51137-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="51137-108">**So öffnen Sie die Seite 'Allgemein' des Editors für den Datenprofilerstellungs-Task**</span><span class="sxs-lookup"><span data-stu-id="51137-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="51137-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, das den Datenprofilerstellungs-Task enthält.</span><span class="sxs-lookup"><span data-stu-id="51137-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="51137-110">Doppelklicken Sie auf der Registerkarte **Ablaufsteuerung** auf den Datenprofilerstellungs-Task.</span><span class="sxs-lookup"><span data-stu-id="51137-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="51137-111">Klicken Sie im **Editor für den Datenprofilerstellungs-Task**auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="51137-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="51137-112">Datenprofilerstellungs-Optionen</span><span class="sxs-lookup"><span data-stu-id="51137-112">Data Profiling Options</span></span>  
 <span data-ttu-id="51137-113">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="51137-113">**Timeout**</span></span>  
 <span data-ttu-id="51137-114">Geben Sie die Anzahl der Sekunden an, nach der ein Timeout des Datenprofilerstellungs-Tasks erfolgt und die Taskausführung abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="51137-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="51137-115">Der Standardwert ist 0, d. h., es erfolgt kein Timeout.</span><span class="sxs-lookup"><span data-stu-id="51137-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="51137-116">Zieloptionen</span><span class="sxs-lookup"><span data-stu-id="51137-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="51137-117">Die Ausgabedatei enthält möglicherweise vertrauliche Daten über Ihre Datenbank und die darin enthaltenen Daten.</span><span class="sxs-lookup"><span data-stu-id="51137-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="51137-118">Vorschläge zur Verbesserung der Sicherheit dieser Datei finden Sie unter [Zugriff auf Dateien, die von Paketen verwendet werden](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="51137-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="51137-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="51137-119">**DestinationType**</span></span>  
 <span data-ttu-id="51137-120">Geben Sie an, ob die Datenprofilausgabe in einer Datei oder einer Variablen gespeichert werden soll:</span><span class="sxs-lookup"><span data-stu-id="51137-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="51137-121">value</span><span class="sxs-lookup"><span data-stu-id="51137-121">Value</span></span>|<span data-ttu-id="51137-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="51137-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="51137-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="51137-123">**FileConnection**</span></span>|<span data-ttu-id="51137-124">Speichert die Profilausgabe in einer Datei an dem in einem Dateiverbindungs-Manager angegebenen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="51137-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="51137-125">Hinweis: Sie geben mit der Option **Ziel** an, welcher Dateiverbindungs-Manager verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="51137-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="51137-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="51137-126">**Variable**</span></span>|<span data-ttu-id="51137-127">Speichert die Profilausgabe in einer Paketvariablen.</span><span class="sxs-lookup"><span data-stu-id="51137-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="51137-128">Hinweis: Sie geben mit der Option **Ziel** an, welche Paketvariable verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="51137-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="51137-129">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="51137-129">**Destination**</span></span>  
 <span data-ttu-id="51137-130">Geben Sie an, welcher Dateiverbindungs-Manager oder welche Paketvariable die Datenprofilausgabe enthält:</span><span class="sxs-lookup"><span data-stu-id="51137-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="51137-131">Wenn die **DestinationType** -Option auf **FileConnection**festgelegt wird, zeigt die Option **Ziel** die verfügbaren Dateiverbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="51137-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="51137-132">Wählen Sie einen dieser Verbindungs-Manager aus, oder wählen Sie \<New File connection> aus, um einen neuen Dateiverbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51137-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="51137-133">Wenn die **DestinationType** -Option auf **Variable**festgelegt wird, zeigt die Option **Ziel** die verfügbaren Paketvariablen in der Liste **Ziel** an.</span><span class="sxs-lookup"><span data-stu-id="51137-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="51137-134">Wählen Sie eine dieser Variablen aus, oder wählen Sie \<New Variable> aus, um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="51137-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="51137-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="51137-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="51137-136">Geben Sie an, ob die Ausgabedatei überschrieben werden soll, wenn sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="51137-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="51137-137">Der Standardwert ist **False**.</span><span class="sxs-lookup"><span data-stu-id="51137-137">The default value is **False**.</span></span> <span data-ttu-id="51137-138">Der Wert dieser Eigenschaft wird nur verwendet, wenn die DestinationType-Option auf FileConnection festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="51137-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="51137-139">Wenn die DestinationType-Option auf Variable festgelegt wird, überschreibt der Task immer den vorherigen Wert der Variablen.</span><span class="sxs-lookup"><span data-stu-id="51137-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="51137-140">Wenn Sie versuchen, den Datenprofilerstellungs-Task mehrmals auszuführen, ohne den Namen der Ausgabedatei zu ändern oder den Wert der **OverwriteDestination** -Eigenschaft in **True**zu ändern, schlägt der Task mit der Meldung fehl, dass die Ausgabedatei bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="51137-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="51137-141">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="51137-141">Other Options</span></span>  
 <span data-ttu-id="51137-142">**Schnellprofil**</span><span class="sxs-lookup"><span data-stu-id="51137-142">**Quick Profile**</span></span>  
 <span data-ttu-id="51137-143">Öffnet das **Schnellprofilformular für eine einzelne Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="51137-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="51137-144">Dieses Formular vereinfacht den Task der Profilerstellung für eine einzelne Tabelle oder Sicht anhand von Standardeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="51137-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="51137-145">Weitere Informationen finden Sie unter [Schnellprofilformular für eine einzelne Tabelle &#40;Datenprofilerstellungs-Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="51137-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="51137-146">**Profil-Viewer öffnen**</span><span class="sxs-lookup"><span data-stu-id="51137-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="51137-147">Öffnet den Datenprofil-Viewer.</span><span class="sxs-lookup"><span data-stu-id="51137-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="51137-148">Der eigenständige Datenprofil-Viewer zeigt die Datenprofilausgabe des Datenprofilerstellungs-Tasks an.</span><span class="sxs-lookup"><span data-stu-id="51137-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="51137-149">Sie können die Datenprofilausgabe anzeigen, nachdem Sie den Datenprofilerstellungs-Task innerhalb des [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakets ausgeführt und die Datenprofile berechnet haben.</span><span class="sxs-lookup"><span data-stu-id="51137-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51137-150">Sie können auch den Datenprofil-Viewer öffnen, indem Sie den DataProfileViewer.exe im Ordner „ *\<drive>* :\Programme (x86) | Programme\Microsoft SQL Server\110\DTS\Binn“ ausführen.</span><span class="sxs-lookup"><span data-stu-id="51137-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51137-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51137-151">See Also</span></span>  
 <span data-ttu-id="51137-152">[Schnellprofilformular für eine einzelne Tabelle &#40;Datenprofilerstellungs-Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="51137-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="51137-153">Editor für den Datenprofilerstellungs-Task &#40;Seite „Profilanforderungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="51137-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
