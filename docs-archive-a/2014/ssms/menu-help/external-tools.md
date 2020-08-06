---
title: Externe Tools | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- External Tools dialog box
ms.assetid: d7dae88f-0781-4162-96cd-d3a3a4d82035
author: stevestein
ms.author: sstein
ms.openlocfilehash: a39cd0d139e81c02a7d2a58fae4e74221be7f78e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700568"
---
# <a name="external-tools"></a><span data-ttu-id="d6c85-102">Externe Tools</span><span class="sxs-lookup"><span data-stu-id="d6c85-102">External Tools</span></span>
  <span data-ttu-id="d6c85-103">Verwenden Sie dieses Dialogfeld, um dem Menü **Extras** externe Tools hinzuzufügen, z. B. SQL Server-Konfigurations-Manager oder Editor.</span><span class="sxs-lookup"><span data-stu-id="d6c85-103">Use this dialog box to add external tools, such as SQL Server Configuration Manager or Notepad, to the **Tools** menu.</span></span> <span data-ttu-id="d6c85-104">Durch das Hinzufügen externer Tools erleichtern Sie das Starten anderer Anwendungen während der Arbeit mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6c85-104">Adding external tools allows you to easily launch other applications while working in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d6c85-105">Sie können beim Starten des Tools Argumente und ein Arbeitsverzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="d6c85-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="d6c85-106">Zusätzlich können die Ausgaben einiger Tools im Ausgabefenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6c85-106">In addition, the outputs from some tools can be displayed in the Output window.</span></span> <span data-ttu-id="d6c85-107">Das Dialogfeld **Externe Tools** wird über das Menü **Extras** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6c85-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d6c85-108">Options</span></span>  
 <span data-ttu-id="d6c85-109">**Menüinhalt**</span><span class="sxs-lookup"><span data-stu-id="d6c85-109">**Menu Contents**</span></span>  
 <span data-ttu-id="d6c85-110">Führt die Titel der Elemente auf, die aktuell dem Menü **Extras** hinzugefügt sind.</span><span class="sxs-lookup"><span data-stu-id="d6c85-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="d6c85-111">Verwenden Sie die Schaltflächen **Nach oben** und **Nach unten** , um die Reihenfolge zu ändern, in der die Elemente im Menü angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6c85-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="d6c85-112">Verwenden Sie die Schaltfläche **Löschen** , um ein Element aus dem Menü zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="d6c85-113">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="d6c85-113">**Move Up**</span></span>  
 <span data-ttu-id="d6c85-114">Verschiebt das ausgewählte Tool innerhalb der Liste der Tools im Menü **Extras** nach oben.</span><span class="sxs-lookup"><span data-stu-id="d6c85-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="d6c85-115">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="d6c85-115">**Move Down**</span></span>  
 <span data-ttu-id="d6c85-116">Verschiebt das ausgewählte Tool innerhalb der Liste der Tools im Menü **Extras** nach unten.</span><span class="sxs-lookup"><span data-stu-id="d6c85-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="d6c85-117">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="d6c85-117">**Add**</span></span>  
 <span data-ttu-id="d6c85-118">Löscht die Textfelder, sodass Sie ein neues Tool angeben können.</span><span class="sxs-lookup"><span data-stu-id="d6c85-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="d6c85-119">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="d6c85-119">**Delete**</span></span>  
 <span data-ttu-id="d6c85-120">Entfernt das Tool oder den Befehl aus der Liste **Menüinhalt** und aus dem Menü **Extras** .</span><span class="sxs-lookup"><span data-stu-id="d6c85-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="d6c85-121">**Titel**</span><span class="sxs-lookup"><span data-stu-id="d6c85-121">**Title**</span></span>  
 <span data-ttu-id="d6c85-122">Der Name des Tools oder Befehls, der im Untermenü **Externe Tools** des Menüs **Extras** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d6c85-122">The name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="d6c85-123">Setzen Sie ein kaufmännisches Und-Zeichen vor einen Buchstaben im Namen des Tools, um diesen Buchstaben als Zugriffstaste für das Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6c85-123">Place an ampersand before a letter in the name of the tool to use that letter as an accelerator key for the tool.</span></span> <span data-ttu-id="d6c85-124">Der Eintrag `&Spy++` würde beispielsweise als **Spy++** im Menü **Extras** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6c85-124">For example, `&Spy++` would display **Spy++** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="d6c85-125">**Befehl**</span><span class="sxs-lookup"><span data-stu-id="d6c85-125">**Command**</span></span>  
 <span data-ttu-id="d6c85-126">Gibt den Pfad zu der Datei mit der Endung EXE, COM, PIF, BAT, CMD oder einer anderen Datei an, die gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6c85-126">Specify the path to the .exe, .com, .pif, .bat, .cmd, or other file that you intend to launch.</span></span> <span data-ttu-id="d6c85-127">Die Ausgabe von `.bat`-, `.com`- und anderen Dateien kann im Ausgabefenster angezeigt werden, wenn Sie das Kontrollkästchen **Ausgabefenster verwenden** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6c85-127">The output from `.bat`, `.com`, and other files can be viewed in the Output window if you select the **Use output window** check box.</span></span>  
  
 <span data-ttu-id="d6c85-128">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="d6c85-128">**Arguments**</span></span>  
 <span data-ttu-id="d6c85-129">Gibt die Variablen an, die an das Tool übergeben werden, wenn es im Menü aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d6c85-129">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="d6c85-130">Argumente können Werte festlegen, die beim Starten an das Tool oder den Befehl übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="d6c85-130">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="d6c85-131">Ein Wert kann beispielsweise einen Dateinamen oder ein Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="d6c85-131">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="d6c85-132">Verwenden Sie die **Pfeil** Schaltfläche, um aus einer Liste vordefinierter Argumente eines auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-132">Use the **Arrow** button to select from a list of predefined arguments.</span></span> <span data-ttu-id="d6c85-133">Sie können mehrere Argumente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-133">You can add more than one.</span></span> <span data-ttu-id="d6c85-134">Eine vollständige Liste vordefinierter Argumente und ihrer Definitionen finden Sie unter [Arguments for External Tools](external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d6c85-134">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](external-tools.md).</span></span> <span data-ttu-id="d6c85-135">Außerdem können Sie benutzerdefinierte Argumente (z. B. Befehlszeilenoptionen) eingeben, je nach verwendetem Befehl bzw. Tool.</span><span class="sxs-lookup"><span data-stu-id="d6c85-135">You can also enter custom arguments (command-prompt switches, for example), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="d6c85-136">**Ausgangsverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="d6c85-136">**Initial directory**</span></span>  
 <span data-ttu-id="d6c85-137">Gibt das Arbeitsverzeichnis für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="d6c85-137">Specify the working directory of the tool.</span></span> <span data-ttu-id="d6c85-138">Verwenden Sie die **Pfeil** -Schaltfläche, um die Verzeichnisse auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-138">Use the **Arrow** button to select directories.</span></span> <span data-ttu-id="d6c85-139">Sie können mehrere Verzeichnisse auswählen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-139">You can select more than one.</span></span>  
  
 <span data-ttu-id="d6c85-140">**Use output Window**</span><span class="sxs-lookup"><span data-stu-id="d6c85-140">**Use output Window**</span></span>  
 <span data-ttu-id="d6c85-141">Gibt an, ob die Ergebnisse des Tools im Ausgabefenster angezeigt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d6c85-141">Specify whether or not results from the tool are displayed in the Output window.</span></span> <span data-ttu-id="d6c85-142">Diese Option ist nur für Dateien verfügbar, die normalerweise eine Ausgabe im Befehlszeilenfenster anzeigen (z. B. BAT- und COM-Dateien).</span><span class="sxs-lookup"><span data-stu-id="d6c85-142">This option is only available for files, such as .bat and .com files, that normally display output in the command prompt window.</span></span> <span data-ttu-id="d6c85-143">Ist sie aktiviert, vereinfacht diese Option die Fensterverwaltung beim Verfolgen der Fortschritte eines Tools.</span><span class="sxs-lookup"><span data-stu-id="d6c85-143">When enabled, this option eases window management when you are following the progress of a tool.</span></span>  
  
 <span data-ttu-id="d6c85-144">**Zur Argumenteingabe auffordern**</span><span class="sxs-lookup"><span data-stu-id="d6c85-144">**Prompt for arguments**</span></span>  
 <span data-ttu-id="d6c85-145">Zeigt das Dialogfeld **Argumente** an, mit dem Sie Werte für die Argumente jedes Mal eingeben oder bearbeiten können, wenn Sie das externe Tool starten.</span><span class="sxs-lookup"><span data-stu-id="d6c85-145">Display the **Arguments** dialog box to enable you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="d6c85-146">**Ausgabe als Unicode behandeln**</span><span class="sxs-lookup"><span data-stu-id="d6c85-146">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="d6c85-147">Ermöglicht dem Ausgabefenster die Annahme von Unicode.</span><span class="sxs-lookup"><span data-stu-id="d6c85-147">Allow the Output window to accept Unicode.</span></span>  
  
 <span data-ttu-id="d6c85-148">**Nach Beenden schließen**</span><span class="sxs-lookup"><span data-stu-id="d6c85-148">**Close On Exit**</span></span>  
 <span data-ttu-id="d6c85-149">Schließt das vom Fenster geöffnete Tool, wenn das Tool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d6c85-149">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6c85-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6c85-150">Example</span></span>  
  
#### <a name="to-add-sql-server-configuration-manager-to-the-tools-menu"></a><span data-ttu-id="d6c85-151">So fügen Sie „SQL Server-Konfigurations-Manager“ dem Menü „Extras“ hinzu</span><span class="sxs-lookup"><span data-stu-id="d6c85-151">To add SQL Server Configuration Manager to the Tools menu</span></span>  
  
1.  <span data-ttu-id="d6c85-152">Klicken Sie im Menü **Extras** auf **Externe Tools**.</span><span class="sxs-lookup"><span data-stu-id="d6c85-152">On the **Tools** menu, click **External Tools**.</span></span>  
  
2.  <span data-ttu-id="d6c85-153">Geben Sie in das Feld **Titel** den Titel **SQL Server-Konfigurations-Manager**ein.</span><span class="sxs-lookup"><span data-stu-id="d6c85-153">In the **Title** box, type **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="d6c85-154">Geben Sie im Feld **Befehl** den Pfad zur [!INCLUDE[msCoName](../../includes/msconame-md.md)] ausführbaren Datei der Verwaltungskonsole ein, z. b.`C:\WINNT\system32\mmc.exe`</span><span class="sxs-lookup"><span data-stu-id="d6c85-154">In the **Command** box, type the path to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console executable, such as `C:\WINNT\system32\mmc.exe`</span></span>  
  
4.  <span data-ttu-id="d6c85-155">Geben Sie im Feld **Argumente** den Pfad zur MSC-Datei ein, z. b.`"C:\WINNT\system32\SQLServerManager.msc"`</span><span class="sxs-lookup"><span data-stu-id="d6c85-155">In the **Arguments** box, type the path to the .msc file, such as `"C:\WINNT\system32\SQLServerManager.msc"`</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6c85-156">Zeigen Sie die Eigenschaften der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Verknüpfung im **Startmenü** an, um den Speicherort der Dateien auf dem Computer zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d6c85-156">View the properties of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] shortcut on the **Start** menu to confirm the location of the files on your computer.</span></span>  
