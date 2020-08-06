---
title: 'Optionen (Text-Editor: Registerkarte "Editor" und Status Leiste) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.editorcontextsettings
- VS.ToolsOptionsPages.Text_Editor.EditorTabAndStatusBar
ms.assetid: e4815678-7885-4631-878f-c6a2b857ee05
author: rothja
ms.author: jroth
ms.openlocfilehash: 920b7d48b5f7a2472a521af21c8217b1adba486a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621173"
---
# <a name="options-text-editor-editor-tab-and-status-bar-page"></a><span data-ttu-id="5ddd0-102">Optionen (Text-Editor: Registerkarte "Editor" und Statusleiste)</span><span class="sxs-lookup"><span data-stu-id="5ddd0-102">Options (Text Editor: Editor Tab and Status Bar Page)</span></span>
  <span data-ttu-id="5ddd0-103">Auf der Seite **Registerkarte "Editor" und Statusleiste** können Sie die von den [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] -Abfrage-Editoren angezeigten Informationen anpassen.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-103">The **Editor Tab and Status Bar Page** lets you customize the information displayed by the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Query Editors.</span></span> <span data-ttu-id="5ddd0-104">Sie können die Ebene der Informationen angeben, die auf der Registerkarte und der Statusleiste des Abfrage-Editor-Fensters angezeigt werden, sowie festlegen, ob die Statusleiste im Editor-Fenster oben oder unten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-104">You can specify the level of information displayed in the tab and status bar of the Query Editor window, and whether the status bar appears at the top or bottom of the editor window.</span></span>  
  
## <a name="option-settings-by-editor"></a><span data-ttu-id="5ddd0-105">Optionseinstellungen nach Editor</span><span class="sxs-lookup"><span data-stu-id="5ddd0-105">Option Settings by Editor</span></span>  
 <span data-ttu-id="5ddd0-106">Die Editorregisterkarte und die Statusleiste sind in allen [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] -Editoren verfügbar, bieten jedoch unterschiedliche Grade an Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-106">The editor tab and the status bar are available in all of the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, but have different levels of functionality.</span></span>  
  
 <span data-ttu-id="5ddd0-107">Der Abfrage-Editor der Datenbank-Engine kann eine Verbindung mit einer Servergruppe herstellen. In diesem Fall werden Verbindungen für alle Instanzen in der Servergruppe geöffnet, und eine Abfrage kann über alle Verbindungen gleichzeitig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-107">The Database Engine Query Editor can connect to a server group, in which case it opens connections to all the instances in the Server Group and can simultaneously run the same query on each connection.</span></span> <span data-ttu-id="5ddd0-108">In diesem Dialogfeld können Sie festlegen, dass die Statusleiste bei einer Verbindung mit mehreren Instanzen andere Farben aufweist als bei einer Verbindung mit nur einer Instanz. Zum Ändern der Multiserver-Ergebnisoptionen verwenden Sie die Seite [Optionen (Abfrageergebnisse/SQL Server/Für mehrere Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md).</span><span class="sxs-lookup"><span data-stu-id="5ddd0-108">You can use this dialog to specify that the status bar has different colors when connected to multiple instances rather than one instance.To change the multi-server results options, use the [Options (Query Results/SQL Server/Multi-Server)](../../2014/database-engine/options-query-results-sql-server-multi-server.md) page.</span></span>  
  
## <a name="status-bar-content"></a><span data-ttu-id="5ddd0-109">Inhalt der Statusleiste</span><span class="sxs-lookup"><span data-stu-id="5ddd0-109">Status Bar Content</span></span>  
 <span data-ttu-id="5ddd0-110">Gibt die Informationen an, die in der Statusleiste des Abfrage-Editors angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-110">Specifies the information that appears in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="5ddd0-111">**Ausführungszeit anzeigen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-111">**Display execution time**</span></span>  
 <span data-ttu-id="5ddd0-112">Schließt die Skriptausführungszeit ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-112">Includes the script execution time.</span></span> <span data-ttu-id="5ddd0-113">Die Einstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ddd0-113">The settings are as follows:</span></span>  
  
 <span data-ttu-id="5ddd0-114">**None**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-114">**None**</span></span>  
 <span data-ttu-id="5ddd0-115">Die Statusleiste zeigt keine Zeitinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-115">The status bar displays no time information.</span></span>  
  
 <span data-ttu-id="5ddd0-116">**ENDE**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-116">**End**</span></span>  
 <span data-ttu-id="5ddd0-117">Auf der Statusleiste wird während der Skriptausführung die aktuelle Uhrzeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-117">The status bar displays the current time of day while the script is running.</span></span> <span data-ttu-id="5ddd0-118">Bei Abschluss des Skripts wird die Uhrzeit angezeigt, zu der das Skript abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-118">When the script completes, the display shows the time of day that the script completed.</span></span>  
  
 <span data-ttu-id="5ddd0-119">**Verstrichene**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-119">**Elapsed**</span></span>  
 <span data-ttu-id="5ddd0-120">Auf der Statusleiste wird die Zeit angezeigt, die das Skript bereits ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-120">The status bar displays the length of time that the script has been running.</span></span> <span data-ttu-id="5ddd0-121">Bei Abschluss des Skripts wird die Zeit angezeigt, die zum Ausführen des Skripts benötigt wurde.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-121">When the script completes, the display shows how much time was taken to run the script.</span></span>  
  
 <span data-ttu-id="5ddd0-122">**Datenbanknamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-122">**Include database name**</span></span>  
 <span data-ttu-id="5ddd0-123">Schließt den Namen der aktuellen Datenbank für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-123">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="5ddd0-124">Wenn der Abfrage-Editor zuerst geöffnet wird, ist dies die Standarddatenbank für die Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-124">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="5ddd0-125">Der Datenbankkontext kann später mit der USE-Anweisung von Transact-SQL geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-125">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="5ddd0-126">**Anmeldenamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-126">**Include login name**</span></span>  
 <span data-ttu-id="5ddd0-127">Schließt den Anmeldenamen ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-127">Includes the login name.</span></span>  
  
 <span data-ttu-id="5ddd0-128">**Zeilenanzahl einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-128">**Include row count**</span></span>  
 <span data-ttu-id="5ddd0-129">Schließt die Anzahl der Zeilen ein, die vom derzeit ausgeführten Skript verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-129">Includes a count of the rows that have been processed by the script that is currently executing.</span></span>  
  
 <span data-ttu-id="5ddd0-130">**Servernamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-130">**Include server name**</span></span>  
 <span data-ttu-id="5ddd0-131">Schließt den Servernamen ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-131">Includes the server name.</span></span> <span data-ttu-id="5ddd0-132">Bei lokalen Verbindungen ist dies der Instanzname.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-132">For local connections, this is the instance name.</span></span> <span data-ttu-id="5ddd0-133">Bei Remoteverbindungen ist dies der Remotecomputername und Instanzname.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-133">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="status-bar-layout-and-colors"></a><span data-ttu-id="5ddd0-134">Layout und Farben der Statusleiste</span><span class="sxs-lookup"><span data-stu-id="5ddd0-134">Status Bar Layout and Colors</span></span>  
 <span data-ttu-id="5ddd0-135">Gibt die Farben für Elemente in der Statusleiste des Abfrage-Editors an.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-135">Specifies the colors for items in the Query Editor status bar.</span></span>  
  
 <span data-ttu-id="5ddd0-136">**Verbindungen gruppieren**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-136">**Group connections**</span></span>  
 <span data-ttu-id="5ddd0-137">Gibt die Farbe der Statusleiste an, wenn der Abfrage-Editor mehr als eine Verbindung aufweist.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-137">Set the color of the status bar when the Query Editor has more than one connection.</span></span>  
  
 <span data-ttu-id="5ddd0-138">**Einzelne Serververbindungen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-138">**Single server connections**</span></span>  
 <span data-ttu-id="5ddd0-139">Gibt die Farbe der Statusleiste an, wenn der Abfrage-Editor eine einzelne Verbindung aufweist.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-139">Set the color of the status bar when the Query Editor has one connection.</span></span>  
  
 <span data-ttu-id="5ddd0-140">**Speicherort der Statusleiste**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-140">**Status bar location**</span></span>  
 <span data-ttu-id="5ddd0-141">Gibt die Position der Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-141">Specifies the location of the status bar.</span></span> <span data-ttu-id="5ddd0-142">Die Einstellungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ddd0-142">The settings are as follows:</span></span>  
  
 <span data-ttu-id="5ddd0-143">**Top**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-143">**Top**</span></span>  
 <span data-ttu-id="5ddd0-144">Die Statusleiste wird am oberen Rand des Abfrage-Editor-Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-144">The status bar appears at the top of the Query Editor window.</span></span>  
  
 <span data-ttu-id="5ddd0-145">**Unten**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-145">**Bottom**</span></span>  
 <span data-ttu-id="5ddd0-146">Die Statusleiste wird am unteren Rand des Abfrage-Editor-Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-146">The status bar appears at the bottom of the Query Editor window.</span></span>  
  
## <a name="tab-text"></a><span data-ttu-id="5ddd0-147">Registerkartentext</span><span class="sxs-lookup"><span data-stu-id="5ddd0-147">Tab Text</span></span>  
 <span data-ttu-id="5ddd0-148">Gibt den Text an, der in der Registerkarte am oberen Rand eines Abfrage-Editor-Fensters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-148">Specifies the text that appears in the tab at the top of a Query Editor window.</span></span> <span data-ttu-id="5ddd0-149">Wenn der Text für die Anzeige zu lang ist, können Sie die vollständige Zeichenfolge in einer QuickInfo anzeigen, die angezeigt wird, wenn Sie den Mauszeiger über die Registerkarte führen.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-149">If the text is too long to display, you can view the full string in a tooltip that is displayed if you hover over the tab.</span></span>  
  
 <span data-ttu-id="5ddd0-150">**Datenbanknamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-150">**Include database name**</span></span>  
 <span data-ttu-id="5ddd0-151">Schließt den Namen der aktuellen Datenbank für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-151">Includes the name of the current database for the connection.</span></span> <span data-ttu-id="5ddd0-152">Wenn der Abfrage-Editor zuerst geöffnet wird, ist dies die Standarddatenbank für die Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-152">When the query editor is first opened, this is the default database for the login.</span></span> <span data-ttu-id="5ddd0-153">Der Datenbankkontext kann später mit der USE-Anweisung von Transact-SQL geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-153">The database context can later be changed by using the Transact-SQL USE statement.</span></span>  
  
 <span data-ttu-id="5ddd0-154">**Dateinamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-154">**Include file name**</span></span>  
 <span data-ttu-id="5ddd0-155">Schließt den Namen der Datei ein, in der das Skript gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-155">Includes the name of the file where the script is stored.</span></span>  
  
 <span data-ttu-id="5ddd0-156">**Ordner einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-156">**Include folder name**</span></span>  
 <span data-ttu-id="5ddd0-157">Schließt den Pfad des Ordners ein, in dem die Skriptdatei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-157">Includes the path of the folder where the script file is stored.</span></span>  
  
 <span data-ttu-id="5ddd0-158">**Anmeldenamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-158">**Include login name**</span></span>  
 <span data-ttu-id="5ddd0-159">Schließt den Anmeldenamen ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-159">Includes the login name.</span></span>  
  
 <span data-ttu-id="5ddd0-160">**Servernamen einschließen**</span><span class="sxs-lookup"><span data-stu-id="5ddd0-160">**Include server name**</span></span>  
 <span data-ttu-id="5ddd0-161">Schließt den Servernamen ein.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-161">Includes the server name.</span></span> <span data-ttu-id="5ddd0-162">Bei lokalen Verbindungen ist dies der Instanzname.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-162">For local connections, this is the instance name.</span></span> <span data-ttu-id="5ddd0-163">Bei Remoteverbindungen ist dies der Remotecomputername und Instanzname.</span><span class="sxs-lookup"><span data-stu-id="5ddd0-163">For remote connections, this is the remote computer name and instance name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ddd0-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ddd0-164">See Also</span></span>  
 <span data-ttu-id="5ddd0-165">[Optionen &#40;Umgebung: Seite "Schriftarten und Farben"&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span><span class="sxs-lookup"><span data-stu-id="5ddd0-165">[Options &#40;Environment: Fonts and Colors Page&#41;](../ssms/menu-help/options-environment-fonts-and-colors-page.md) </span></span>  
 [<span data-ttu-id="5ddd0-166">Farbcodierung im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="5ddd0-166">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
  
  
