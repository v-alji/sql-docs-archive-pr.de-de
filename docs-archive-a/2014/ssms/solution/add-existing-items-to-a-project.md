---
title: Hinzufügen vorhandener Elemente zu einem Projekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 084b3879-e96b-45a7-b421-6a4b0db2b92b
author: stevestein
ms.author: sstein
ms.openlocfilehash: cffa683bfa2a2c81c059d887231531f03d5c892b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622329"
---
# <a name="add-existing-items-to-a-project"></a><span data-ttu-id="4d7d6-102">Hinzufügen vorhandener Elemente zu einem Projekt</span><span class="sxs-lookup"><span data-stu-id="4d7d6-102">Add Existing Items to a Project</span></span>
  <span data-ttu-id="4d7d6-103">Sie können neue Elemente zu einem Projekt hinzufügen, um die Funktionalität der Anwendung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="4d7d6-104">Bei einem vorhandenen Element kann es sich um eine Abfrage oder eine beliebige Datei handeln.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-104">An existing item can be a query or a miscellaneous file.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4d7d6-105">hat zwei Projekttypen: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Skriptprojekt und Analysis Services-Skriptprojekt.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="4d7d6-106">Der Projekttyp bestimmt die Abfragedateien, die Sie zu einem Projekt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-106">The project type determines the query files that you can add to the project.</span></span> <span data-ttu-id="4d7d6-107">So können Sie beispielsweise eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage (eine Datei mit einer SQL-Erweiterung) zu einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Skriptprojekt hinzufügen, nicht jedoch zu einem Analysis Services-Skriptprojekt.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span> <span data-ttu-id="4d7d6-108">Informationen zum Zuordnen zusätzlicher Dateierweiterungen zu einem Projekttyp finden Sie unter [Zuordnen von Dateierweiterungen zu einem Code-Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4d7d6-108">To associate additional file extensions to a project type, see [Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md).</span></span>  
  
### <a name="to-add-an-existing-query-or-a-miscellaneous-file-to-a-project"></a><span data-ttu-id="4d7d6-109">So fügen Sie eine vorhandene Abfrage oder eine beliebige Datei zu einem Projekt hinzu</span><span class="sxs-lookup"><span data-stu-id="4d7d6-109">To add an existing query or a miscellaneous file to a project</span></span>  
  
1.  <span data-ttu-id="4d7d6-110">Wählen Sie im Projektmappen-Explorer ein Zielprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-110">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="4d7d6-111">Klicken Sie im Menü **Projekt** auf **Vorhandenes Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-111">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
     <span data-ttu-id="4d7d6-112">**Look in**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-112">**Look in**</span></span>  
     <span data-ttu-id="4d7d6-113">Suchen Sie in der Liste nach den Dateien oder Ordnern, die dem Projekt hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-113">Locate the files or folders to add to your project from this list.</span></span> <span data-ttu-id="4d7d6-114">Die Dateien von XML-Webdiensten und ASP.NET-Webanwendungen sind auf dem Webserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-114">For XML Web services and ASP.NET Web applications, the files are located on the Web server.</span></span>  
  
     <span data-ttu-id="4d7d6-115">**Desktop**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-115">**Desktop**</span></span>  
     <span data-ttu-id="4d7d6-116">Zeigt die Dateien und Ordner auf dem Desktop an.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-116">Displays the files and folders located on the desktop.</span></span>  
  
     <span data-ttu-id="4d7d6-117">**Eigene Projekte**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-117">**My Projects**</span></span>  
     <span data-ttu-id="4d7d6-118">Zeigt die Dateien und Ordner im Standardverzeichnis **Eigene Projekte** an.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-118">Displays the files and folders at the default **My Projects** location.</span></span>  
  
     <span data-ttu-id="4d7d6-119">**Arbeitsplatz**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-119">**My Computer**</span></span>  
     <span data-ttu-id="4d7d6-120">Zeigt den Inhalt des Ordners **Arbeitsplatz** an.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-120">Displays the contents of your **My Computer** folder.</span></span>  
  
     <span data-ttu-id="4d7d6-121">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-121">**File name**</span></span>  
     <span data-ttu-id="4d7d6-122">Mithilfe dieser Option können Sie die anzuzeigenden Dateien oder Ordner filtern.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-122">Use this option to filter the files and folders that are displayed.</span></span> <span data-ttu-id="4d7d6-123">Geben Sie den Dateinamen, nach dem gefiltert werden soll, vollständig oder teilweise ein. Als Platzhalter können Sie das Sternchen (`*`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-123">Enter the full or partial file name on which to filter; use an asterisk (`*`) as a wildcard.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d7d6-124">Navigieren Sie zu dem gewünschten Speicherort im Web oder Netzwerk, indem Sie die URL oder Netzwerkpfad in das Feld **Dateiname** eingeben.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-124">Navigate to Web and network locations by entering the URL or network path in the **File name** box.</span></span> <span data-ttu-id="4d7d6-125">Beispielsweise werden mit **http://mywebsite** alle Dateien angezeigt, die unter der Webadresse „mywebsite“ verfügbar sind, während mit **\\\myserver\myshare** alle Dateien aufgeführt werden, die im Ordner „myshare“ des Servers „myserver“ gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-125">For example, **http://mywebsite** displays the files available at the mywebsite Web location, and **\\\myserver\myshare** displays the files available at the myshare location on myserver.</span></span>  
  
     <span data-ttu-id="4d7d6-126">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-126">**Files of type**</span></span>  
     <span data-ttu-id="4d7d6-127">Mithilfe dieser Option können Sie Dateien nach der Dateierweiterung filtern.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-127">Use this option to filter files based on file extension.</span></span> <span data-ttu-id="4d7d6-128">Jedes Produkt listet Standardfilter für die am häufigsten verwendeten Dateitypen auf.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-128">Each product lists default filters of the most common file types.</span></span>  
  
     <span data-ttu-id="4d7d6-129">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-129">**Add**</span></span>  
     <span data-ttu-id="4d7d6-130">Mithilfe dieser Dropdown-Schaltfläche können Sie dem Projekt das Objekt hinzufügen und das Objekt mit dem entsprechenden Standard-Editor öffnen.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-130">Use this drop-down button to add the item to the project and open the item in its default editor.</span></span>  
  
    -   <span data-ttu-id="4d7d6-131">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-131">**Add**</span></span>  
  
         <span data-ttu-id="4d7d6-132">Kopiert ein vorhandenes Objekt in den Projektordner auf dem Datenträger und fügt das Objekt dem ausgewählten Projekt im Projektmappen-Explorer hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-132">Copies the existing item to your project folder on disk and adds the item under the selected project in Solution Explorer.</span></span> <span data-ttu-id="4d7d6-133">Die an diesem Objekt vorgenommenen Änderungen haben keine Auswirkungen auf das Objekt am ursprünglichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-133">Any changes made to the item are not reflected in the item at the original location.</span></span> <span data-ttu-id="4d7d6-134">Dies ist der Standardeditor für diesen Dateityp.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-134">This is the default editor for the file type.</span></span>  
  
    -   <span data-ttu-id="4d7d6-135">**Als Link hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="4d7d6-135">**Add As Link**</span></span>  
  
         <span data-ttu-id="4d7d6-136">Fügt dem Projekt die ausgewählte Datei hinzu und öffnet sie mit dem Standard-Editor für den Dateityp.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-136">Adds the selected file to the project and opens it with the default editor for the file type.</span></span> <span data-ttu-id="4d7d6-137">Mit dieser Option wird die ursprünglich ausgewählte Datei geöffnet. Die Datei wird nicht in den Projektordner kopiert.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-137">This option opens the originally selected file and does not copy the file to the project folder.</span></span>  
  
3.  <span data-ttu-id="4d7d6-138">Beim Hinzufügen von Abfragedateien werden Sie im Verbindungsdialogfeld aufgefordert, eine Verbindung für die Abfrage anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-138">If you are adding query files, the connection dialog will prompt you to specify a connection for the query.</span></span> <span data-ttu-id="4d7d6-139">Wenn Sie der Abfrage keine Verbindung zuordnen möchten, klicken Sie im Verbindungsdialogfeld auf **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="4d7d6-139">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the query.</span></span>  
  
4.  <span data-ttu-id="4d7d6-140">Die Datei wird dem Ordner **Abfragen** oder **Sonstige Dateien** des Projekts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d7d6-140">The file will be added to the **Queries** or **Miscellaneous Files** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7d6-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d7d6-141">See Also</span></span>  
 <span data-ttu-id="4d7d6-142">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="4d7d6-142">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="4d7d6-143">[Hinzufügen neuer Elemente zu einem Projekt](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="4d7d6-143">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="4d7d6-144">Entfernen oder Löschen eines Elements oder Projekts</span><span class="sxs-lookup"><span data-stu-id="4d7d6-144">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
