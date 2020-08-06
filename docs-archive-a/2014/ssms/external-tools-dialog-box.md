---
title: Externe Tools (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717269"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="aa570-102">Externe Tools (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="aa570-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="aa570-103">Mit dem Dialogfeld **Externe Tools** können Sie dem Menü **Extras** externe Tools hinzufügen, z. B. SQLCMD oder den Editor.</span><span class="sxs-lookup"><span data-stu-id="aa570-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="aa570-104">Durch das Hinzufügen von externen Tools können Sie auf einfache Weise andere Anwendungen starten, während Sie in der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Umgebung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aa570-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="aa570-105">Sie können beim Starten des Tools Argumente und ein Arbeitsverzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="aa570-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="aa570-106">Darüber hinaus kann im **Ausgabefenster** die Ausgabe einiger Tools angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aa570-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="aa570-107">Das Dialogfeld **Externe Tools** wird über das Menü **Extras** aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aa570-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa570-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="aa570-108">Options</span></span>  
 <span data-ttu-id="aa570-109">**Inhalt des Menüs**</span><span class="sxs-lookup"><span data-stu-id="aa570-109">**Menu contents**</span></span>  
 <span data-ttu-id="aa570-110">Führt die Titel der Elemente auf, die aktuell dem Menü **Extras** hinzugefügt sind.</span><span class="sxs-lookup"><span data-stu-id="aa570-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="aa570-111">Verwenden Sie die Schaltflächen **Nach oben** und **Nach unten** , um die Reihenfolge zu ändern, in der die Elemente im Menü angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="aa570-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="aa570-112">Verwenden Sie die Schaltfläche **Löschen** , um ein Element aus dem Menü zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="aa570-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="aa570-113">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="aa570-113">**Move Up**</span></span>  
 <span data-ttu-id="aa570-114">Verschiebt das ausgewählte Tool innerhalb der Liste der Tools im Menü **Extras** nach oben.</span><span class="sxs-lookup"><span data-stu-id="aa570-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="aa570-115">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="aa570-115">**Move Down**</span></span>  
 <span data-ttu-id="aa570-116">Verschiebt das ausgewählte Tool innerhalb der Liste der Tools im Menü **Extras** nach unten.</span><span class="sxs-lookup"><span data-stu-id="aa570-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="aa570-117">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="aa570-117">**Add**</span></span>  
 <span data-ttu-id="aa570-118">Löscht die Textfelder, sodass Sie ein neues Tool angeben können.</span><span class="sxs-lookup"><span data-stu-id="aa570-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="aa570-119">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="aa570-119">**Delete**</span></span>  
 <span data-ttu-id="aa570-120">Entfernt das Tool oder den Befehl aus der Liste **Menüinhalt** und aus dem Menü **Extras** .</span><span class="sxs-lookup"><span data-stu-id="aa570-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="aa570-121">**Titel**</span><span class="sxs-lookup"><span data-stu-id="aa570-121">**Title**</span></span>  
 <span data-ttu-id="aa570-122">Geben Sie den Namen des Tools oder Befehls ein, der im Untermenü **Externe Tools** des Menüs **Extras** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aa570-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="aa570-123">Fügen Sie vor einem Buchstaben im Namen des Tools ein kaufmännisches Und-Zeichen (&) ein, um diesen Buchstaben als Tastenkombination anzugeben.</span><span class="sxs-lookup"><span data-stu-id="aa570-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="aa570-124">Mit „&SQLCMD“ wird z. B. SQLCMD im Menü **Extras** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa570-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="aa570-125">**Befehl**</span><span class="sxs-lookup"><span data-stu-id="aa570-125">**Command**</span></span>  
 <span data-ttu-id="aa570-126">Gibt den Pfad zu der Datei an, die gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa570-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="aa570-127">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="aa570-127">**Arguments**</span></span>  
 <span data-ttu-id="aa570-128">Gibt die Variablen an, die an das Tool übergeben werden, wenn es im Menü aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="aa570-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="aa570-129">Argumente können Werte festlegen, die beim Starten an das Tool oder den Befehl übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa570-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="aa570-130">Ein Wert kann beispielsweise einen Dateinamen oder ein Verzeichnis angeben.</span><span class="sxs-lookup"><span data-stu-id="aa570-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="aa570-131">Mit der Schaltfläche mit dem Pfeil können Sie aus einer Liste mit vordefinierten Argumenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="aa570-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="aa570-132">Sie können mehrere Argumente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aa570-132">You can add more than one.</span></span> <span data-ttu-id="aa570-133">Eine vollständige Liste vordefinierter Argumente und ihrer Definitionen finden Sie unter [Arguments for External Tools](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aa570-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="aa570-134">Abhängig vom verwendeten Befehl oder Tool können Sie auch benutzerdefinierte Argumente eingeben, (wie z. B. Befehlszeilenoptionen).</span><span class="sxs-lookup"><span data-stu-id="aa570-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="aa570-135">**Ausgabefenster verwenden**</span><span class="sxs-lookup"><span data-stu-id="aa570-135">**Use Output window**</span></span>  
 <span data-ttu-id="aa570-136">Öffnet das Ausgabefenster in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , in dem die Ausgabe des derzeit ausgeführten Befehls angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aa570-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="aa570-137">Nicht alle Tools zeigen ihre Ausgabe in einem Format an, das im Ausgabefenster dargestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa570-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="aa570-138">Weitere Informationen finden Sie unter [Ausgabefenster](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="aa570-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="aa570-139">**Ausgabe als Unicode behandeln**</span><span class="sxs-lookup"><span data-stu-id="aa570-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="aa570-140">Interpretiert die Ausgabe als Unicode.</span><span class="sxs-lookup"><span data-stu-id="aa570-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="aa570-141">**Ausgangsverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="aa570-141">**Initial directory**</span></span>  
 <span data-ttu-id="aa570-142">Gibt das Arbeitsverzeichnis für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="aa570-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="aa570-143">Mit der Schaltfläche mit dem Pfeil können Sie Verzeichnisse auswählen.</span><span class="sxs-lookup"><span data-stu-id="aa570-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="aa570-144">Sie können mehrere Verzeichnisse auswählen.</span><span class="sxs-lookup"><span data-stu-id="aa570-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="aa570-145">**Zur Argumenteingabe auffordern**</span><span class="sxs-lookup"><span data-stu-id="aa570-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="aa570-146">Zeigt das Dialogfeld **Argumente** an, in dem Sie bei jedem Start des externen Tools Werte für die Argumente eingeben oder bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="aa570-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="aa570-147">**Beim Beenden schließen**</span><span class="sxs-lookup"><span data-stu-id="aa570-147">**Close on exit**</span></span>  
 <span data-ttu-id="aa570-148">Schließt das vom Fenster geöffnete Tool, wenn das Tool geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="aa570-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa570-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa570-149">Example</span></span>  
 <span data-ttu-id="aa570-150">Durch die Eingabe der folgenden Werte im Dialogfeld **Externe Tools** wird ein Menüelement mit der Bezeichnung "DAC" erstellt. Durch Auswählen des Elements wird eine Eingabeaufforderung geöffnet und das Hilfsprogramm **sqlcmd** mithilfe der dedizierten Administratorverbindung (Dedicated Administrator Connection, DAC) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="aa570-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="aa570-151">Feld</span><span class="sxs-lookup"><span data-stu-id="aa570-151">Box</span></span>|<span data-ttu-id="aa570-152">value</span><span class="sxs-lookup"><span data-stu-id="aa570-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="aa570-153">**Titel**</span><span class="sxs-lookup"><span data-stu-id="aa570-153">**Title**</span></span>|<span data-ttu-id="aa570-154">DAC</span><span class="sxs-lookup"><span data-stu-id="aa570-154">DAC</span></span>|  
|<span data-ttu-id="aa570-155">**Befehl**</span><span class="sxs-lookup"><span data-stu-id="aa570-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="aa570-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="aa570-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="aa570-157">**Argumente**</span><span class="sxs-lookup"><span data-stu-id="aa570-157">**Arguments**</span></span>|<span data-ttu-id="aa570-158">-A</span><span class="sxs-lookup"><span data-stu-id="aa570-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa570-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa570-159">See Also</span></span>  
 <span data-ttu-id="aa570-160">[Argumente für externe Tools](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="aa570-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="aa570-161">Allgemeine Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="aa570-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
