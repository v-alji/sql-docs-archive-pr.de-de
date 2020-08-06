---
title: Konfigurieren von Editoren
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7c7a8ef-f561-4258-a7b6-c445dba69f87
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e94cdbcd310814081e146e3fd0dbe75260d1240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701001"
---
# <a name="configure-editors-sql-server-management-studio"></a><span data-ttu-id="eb420-102">Konfigurieren von Editoren (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eb420-102">Configure Editors (SQL Server Management Studio)</span></span>
  <span data-ttu-id="eb420-103">Sie können die Operation der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Editoren anpassen, indem Sie die Optionen für jeden Editor konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb420-103">You can customize the operation of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editors by configuring the options for each editor.</span></span>  
  
## <a name="settng-editor-options"></a><span data-ttu-id="eb420-104">Settng-Editor-Optionen</span><span class="sxs-lookup"><span data-stu-id="eb420-104">Settng Editor Options</span></span>  
 <span data-ttu-id="eb420-105">Sie können die meisten Editoroptionen einrichten, indem Sie im Menü **Extras** den Eintrag **Optionen…** auswählen und so das Dialogfeld **Optionen** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb420-105">Most of the editor options are set by using the **Tools** menu and selecting **Options...** to display an **Options** dialog.</span></span> <span data-ttu-id="eb420-106">Öffnen Sie im Dialogfeld **Optionen** den Knoten **Text-Editor** im linken Bereich, um die Optionen für Code- und Textbearbeitung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eb420-106">In the **Options** dialog, open the **Text Editor** node in the left pane to set code and text editing options.</span></span> <span data-ttu-id="eb420-107">Die Knoten unter Text-Editor gelten für bestimmte Editoren:</span><span class="sxs-lookup"><span data-stu-id="eb420-107">The nodes under Text Editor apply to specific editors:</span></span>  
  
1.  <span data-ttu-id="eb420-108">**Alle Sprachen**: Mit diesem Knoten festgelegte Optionen gelten für alle [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]-Editoren.</span><span class="sxs-lookup"><span data-stu-id="eb420-108">**All Languages** - options set using this node apply to all of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] editors.</span></span> <span data-ttu-id="eb420-109">Sie können diese Einstellungen mithilfe der anderen Knoten überschreiben, um für einen bestimmten Editor andere Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eb420-109">You can override these settings by using the other nodes to set different options for a specific editor.</span></span>  
  
2.  <span data-ttu-id="eb420-110">**Nur-Text**: Mit diesem Knoten festgelegte Optionen gelten für MDX-, DMX- und Text-Editoren.</span><span class="sxs-lookup"><span data-stu-id="eb420-110">**Plain Text** - options set using this node apply to the MDX, DMX, and text editors.</span></span>  
  
3.  <span data-ttu-id="eb420-111">**Transact-SQL**: Mit diesem Knoten festgelegte Optionen gelten für den Datenbank-Engine-Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="eb420-111">**Transact-SQL** - options set using this node apply to the Database Engine Query Editor.</span></span>  
  
4.  <span data-ttu-id="eb420-112">**XML**: Mit diesem Knoten festgelegte Optionen gelten für den XML for Analysis-Editor.</span><span class="sxs-lookup"><span data-stu-id="eb420-112">**XML** - options set using this node apply to the XML for Analysis editor.</span></span>  
  
 <span data-ttu-id="eb420-113">Öffnen Sie die Knoten **Abfrageausführung** oder **Abfrageergebnisse** , um die Ausführung von Abfragen und die Anzeige der Ergebnisse anzupassen.</span><span class="sxs-lookup"><span data-stu-id="eb420-113">Open the **Query Execution** or **Query Results** nodes to customize the execution of queries and how the results are displayed.</span></span>  
  
## <a name="editor-configuration-tasks"></a><span data-ttu-id="eb420-114">Editorkonfigurationstasks</span><span class="sxs-lookup"><span data-stu-id="eb420-114">Editor Configuration Tasks</span></span>  
  
|<span data-ttu-id="eb420-115">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="eb420-115">Task Description</span></span>|<span data-ttu-id="eb420-116">Thema</span><span class="sxs-lookup"><span data-stu-id="eb420-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="eb420-117">Beschreibt das Vorgehen für die Festlegung, dass ein Editor durch Doppelklicken auf eine Datei mit einer angegebenen Erweiterung in Windows-Explorer geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eb420-117">Describes how to specify that an editor be opened by double-clicking on a file with a specified extension in Windows Explorer.</span></span>|[<span data-ttu-id="eb420-118">Zuordnen von Dateierweiterungen zu einem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="eb420-118">Associate File Extensions to a Code Editor</span></span>](associate-file-extensions-to-a-code-editor.md)|  
|<span data-ttu-id="eb420-119">Beschreibt die Anpassung von Schriftarten für eine bessere Lesbarkeit von Code und Text.</span><span class="sxs-lookup"><span data-stu-id="eb420-119">Describes how to customize fonts to make code and text more readable.</span></span>|[<span data-ttu-id="eb420-120">Ändern von Schriftfarbe, Schriftgrad und Schriftschnitt</span><span class="sxs-lookup"><span data-stu-id="eb420-120">Change Font Color, Size, and Style</span></span>](change-font-color-size-and-style.md)|  
|<span data-ttu-id="eb420-121">Beschreibt das Vorgehen zur Anzeige von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eb420-121">Describes how to view properties.</span></span>|[<span data-ttu-id="eb420-122">Verwenden des Eigenschaftenfensters in Management Studio</span><span class="sxs-lookup"><span data-stu-id="eb420-122">Use the Properties Window in Management Studio</span></span>](use-the-properties-window-in-management-studio.md)|  
|<span data-ttu-id="eb420-123">Speicherort der F1-Hilfeseiten zu den Dialogfeldern für Editoroptionen.</span><span class="sxs-lookup"><span data-stu-id="eb420-123">Location of the F1 help pages for the editor options dialogs.</span></span>|[<span data-ttu-id="eb420-124">Abfrageoptionen (Seiten; F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="eb420-124">Query Options Pages F1 Help</span></span>](../../database-engine/query-options-pages-f1-help.md)|  
  
  
