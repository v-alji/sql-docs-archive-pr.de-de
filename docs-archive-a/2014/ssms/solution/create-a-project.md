---
title: Erstellen eines Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], creating
ms.assetid: 7897be19-365b-4b06-bcf0-8a669f67a673
author: stevestein
ms.author: sstein
ms.openlocfilehash: 269feee7225ceb09b1c2ed86419b19ec4001c1f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619521"
---
# <a name="create-a-project"></a><span data-ttu-id="f3b17-102">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="f3b17-102">Create a Project</span></span>
  <span data-ttu-id="f3b17-103">Sie können innerhalb einer vorhandenen Projektmappe ein oder mehrere Projekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3b17-103">You can create one or more projects within an existing solution.</span></span>  
  
### <a name="to-create-a-new-project-and-add-it-to-a-solution"></a><span data-ttu-id="f3b17-104">So erstellen Sie ein neues Projekt erstellen und fügen es zu einer Projektmappe hinzu</span><span class="sxs-lookup"><span data-stu-id="f3b17-104">To create a new project and add it to a solution</span></span>  
  
1.  <span data-ttu-id="f3b17-105">Wählen Sie die Projektmappe im Projektmappen-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="f3b17-105">In Solution Explorer, select the solution.</span></span>  
  
2.  <span data-ttu-id="f3b17-106">Zeigen Sie im Menü **Datei** auf **Hinzufügen**, und klicken Sie auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f3b17-106">On the **File** menu, point to **Add**, and click **New Project**.</span></span>  
  
3.  <span data-ttu-id="f3b17-107">Klicken Sie im Dialogfeld  **Neues Projekt** auf einen Projekttyp.</span><span class="sxs-lookup"><span data-stu-id="f3b17-107">In the  **New Project** dialog box, click a type of project.</span></span>  
  
     <span data-ttu-id="f3b17-108">**Vorlagen**</span><span class="sxs-lookup"><span data-stu-id="f3b17-108">**Templates**</span></span>  
     <span data-ttu-id="f3b17-109">Wählen Sie im Feld **Vorlagen** eine Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="f3b17-109">In the **Templates** box, select a template.</span></span> <span data-ttu-id="f3b17-110">Neben dem Feld **Vorlagen** wird eine kurze Beschreibung der ausgewählten Projektvorlage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f3b17-110">A brief description of the selected project template appears beneath the **Templates** box.</span></span>  
  
     <span data-ttu-id="f3b17-111">**Name**</span><span class="sxs-lookup"><span data-stu-id="f3b17-111">**Name**</span></span>  
     <span data-ttu-id="f3b17-112">Geben Sie den Namen des zu erstellenden Skriptprojekts ein.</span><span class="sxs-lookup"><span data-stu-id="f3b17-112">Enter the name of the script project you want to create.</span></span> <span data-ttu-id="f3b17-113">Ein Ordner mit demselben Namen wie das Projekt wird ebenfalls an dem Ort erstellt, der im Feld **Speicherort** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f3b17-113">A folder with the same name as the project is also created in the location displayed in the **Location** field.</span></span> <span data-ttu-id="f3b17-114">Für einige Projekte erstellt [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Quell- und andere unterstützende Dateien, die dem neuen Projektordner hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f3b17-114">For some projects, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates source and other supporting files and adds them to the new project folder.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f3b17-115">Bei einigen Projekttypen ist das Textfeld **Name** nicht verfügbar, weil der Name durch die Angabe des Speicherorts festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f3b17-115">For some project types, the **Name** text box is unavailable because specifying the location sets the name.</span></span> <span data-ttu-id="f3b17-116">Webanwendungen und Webdienste befinden sich beispielsweise auf einem Webserver und leiten ihren Namen aus dem virtuellen Verzeichnis ab, das auf diesem Server angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f3b17-116">For example, Web applications and Web services are located on a Web server and derive their name from the virtual directory specified on that server.</span></span>  
  
     <span data-ttu-id="f3b17-117">Folgende Zeichen dürfen nicht in den Namen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="f3b17-117">Names cannot contain the following characters:</span></span>  
  
    -   <span data-ttu-id="f3b17-118">Nummernzeichen (#)</span><span class="sxs-lookup"><span data-stu-id="f3b17-118">Pound (#)</span></span>  
  
    -   <span data-ttu-id="f3b17-119">Prozent (%)</span><span class="sxs-lookup"><span data-stu-id="f3b17-119">Percent (%)</span></span>  
  
    -   <span data-ttu-id="f3b17-120">Kaufmännisches Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="f3b17-120">Ampersand (&)</span></span>  
  
    -   <span data-ttu-id="f3b17-121">Sternchen (\*)</span><span class="sxs-lookup"><span data-stu-id="f3b17-121">Asterisk (\*)</span></span>  
  
    -   <span data-ttu-id="f3b17-122">Senkrechter Strich (|)</span><span class="sxs-lookup"><span data-stu-id="f3b17-122">Vertical bar (|)</span></span>  
  
    -   <span data-ttu-id="f3b17-123">Umgekehrter Schrägstrich (\\)</span><span class="sxs-lookup"><span data-stu-id="f3b17-123">Backslash (\\)</span></span>  
  
    -   <span data-ttu-id="f3b17-124">Doppelpunkt (:)</span><span class="sxs-lookup"><span data-stu-id="f3b17-124">Colon (:)</span></span>  
  
    -   <span data-ttu-id="f3b17-125">Anführungszeichen (")</span><span class="sxs-lookup"><span data-stu-id="f3b17-125">Quotation mark (")</span></span>  
  
    -   <span data-ttu-id="f3b17-126">Kleiner als (\<)</span><span class="sxs-lookup"><span data-stu-id="f3b17-126">Less than (\<)</span></span>  
  
    -   <span data-ttu-id="f3b17-127">Größer als (>)</span><span class="sxs-lookup"><span data-stu-id="f3b17-127">Greater than (>)</span></span>  
  
    -   <span data-ttu-id="f3b17-128">Fragezeichen (?)</span><span class="sxs-lookup"><span data-stu-id="f3b17-128">Question mark (?)</span></span>  
  
    -   <span data-ttu-id="f3b17-129">Schrägstrich (/)</span><span class="sxs-lookup"><span data-stu-id="f3b17-129">Forward slash (/)</span></span>  
  
    -   <span data-ttu-id="f3b17-130">Führende oder nachfolgende Leerzeichen (' ')</span><span class="sxs-lookup"><span data-stu-id="f3b17-130">Leading or trailing spaces (' ')</span></span>  
  
    -   <span data-ttu-id="f3b17-131">Namen, die für Microsoft Windows oder MS-DOS reserviert sind (z. B. „nul“, „aux“, „con“, „com1“, „lpt1“ usw.)</span><span class="sxs-lookup"><span data-stu-id="f3b17-131">Names reserved for Microsoft Windows or MS-DOS, such as ("nul", "aux", "con", "com1", "lpt1", and so on)</span></span>  
  
     <span data-ttu-id="f3b17-132">**Location**</span><span class="sxs-lookup"><span data-stu-id="f3b17-132">**Location**</span></span>  
     <span data-ttu-id="f3b17-133">Geben Sie hier den Speicherort ein, an dem das Projekt erstellt werden soll, oder wählen Sie einen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="f3b17-133">Enter the location where you want to create your project, or choose one from the list.</span></span>  
  
     <span data-ttu-id="f3b17-134">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="f3b17-134">**Browse**</span></span>  
     <span data-ttu-id="f3b17-135">Zeigt das Dialogfeld **Projektspeicherort** an, mit dem Sie zu einem neuen Verzeichnis navigieren können, in dem das Projekt gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3b17-135">Displays the **Project Location** dialog box, allowing you to navigate to a new directory in which to save the project.</span></span>  
  
     <span data-ttu-id="f3b17-136">**Lösung**</span><span class="sxs-lookup"><span data-stu-id="f3b17-136">**Solution**</span></span>  
     <span data-ttu-id="f3b17-137">Wählen Sie **Neue Projektmappe erstellen** aus, um eine Projektmappe im Projektmappen-Explorer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f3b17-137">Select **Create new Solution** to create a solution in Solution Explorer.</span></span> <span data-ttu-id="f3b17-138">Wählen Sie **Zu Projektmappe hinzufügen** , um das neue Projekt zur aktuell geöffneten Projektmappe im Projektmappen-Explorer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f3b17-138">Select **Add to Solution** to add the new project to the solution currently open in Solution Explorer.</span></span>  
  
     <span data-ttu-id="f3b17-139">**Projektmappenverzeichnis erstellen**</span><span class="sxs-lookup"><span data-stu-id="f3b17-139">**Create directory for Solution**</span></span>  
     <span data-ttu-id="f3b17-140">Wählen Sie diese Option aus, um das Textfeld **Projektmappenname** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3b17-140">Select to enable the **(Solution) Name** text box.</span></span> <span data-ttu-id="f3b17-141">Diese Option erstellt ein neues Verzeichnis mit dem gewählten Namen für das Projekt und die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="f3b17-141">This option creates a new directory of the name you choose for your project and solution.</span></span>  
  
     <span data-ttu-id="f3b17-142">**Projektmappenname**</span><span class="sxs-lookup"><span data-stu-id="f3b17-142">**Solution Name**</span></span>  
     <span data-ttu-id="f3b17-143">Geben Sie den Namen der neuen Projektmappe ein, in der das Projekt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3b17-143">Enter the name of the new solution in which you want your project to be created.</span></span> <span data-ttu-id="f3b17-144">Der Standardwert für dieses Feld ist derselbe Name, der im Feld **Name** eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="f3b17-144">By default, this field uses the same name as entered in the **Name** field.</span></span>  
  
     <span data-ttu-id="f3b17-145">**Hinweis** Um auf diese Option zugreifen zu können, müssen Sie die Kontrollkästchen **Neue Projektmappe erstellen** in der **Projektmappe** und **Projektmappenverzeichnis erstellen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f3b17-145">**Note** To access this option, you must select both the **Create New Solution** in the **Solution** and the **Create directory for Solution** check boxes.</span></span> <span data-ttu-id="f3b17-146">Einige Projektvorlagen unterstützen diese Option nicht (z. B. Webanwendungen).</span><span class="sxs-lookup"><span data-stu-id="f3b17-146">Some project templates do not support this option, such as Web applications.</span></span>  
  
     <span data-ttu-id="f3b17-147">**Zur Quellcodeverwaltung hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="f3b17-147">**Add to Source Control**</span></span>  
     <span data-ttu-id="f3b17-148">Wenn dieses Kontrollkästchen aktiviert ist, wird die Quellcodeverwaltungs-Anwendung gestartet, sobald Sie auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="f3b17-148">When this check box is selected, your source control application opens when you click **OK**.</span></span> <span data-ttu-id="f3b17-149">Geben Sie alle Daten ein, die von der Quellcodeverwaltungs-Anwendung angefordert werden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="f3b17-149">Complete any information required by your source control application to continue.</span></span> <span data-ttu-id="f3b17-150">Um diese Option verwenden zu können, muss eine Quellcodeverwaltungs-Clientanwendung installiert sein.</span><span class="sxs-lookup"><span data-stu-id="f3b17-150">You must have a source control client application installed to use this option.</span></span>  
  
4.  <span data-ttu-id="f3b17-151">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3b17-151">Click **OK**.</span></span>  
  
 <span data-ttu-id="f3b17-152">Für das Skriptprojekt können Sie einen Namen festlegen. Die Ordnernamen hingegen werden von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] festgelegt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f3b17-152">You can set a name for the script project, but the folder names are established by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and cannot be changed.</span></span> <span data-ttu-id="f3b17-153">Sie können die Laufwerk- und Pfadspezifikation für den gemeinsamen Ordnersatz mit dem Dialogfeld **Neues Projekt hinzufügen** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f3b17-153">You can configure the drive and path specification for the common set of folders by using the **Add New Project** dialog box.</span></span> <span data-ttu-id="f3b17-154">Klicken Sie mit der rechten Maustaste auf das Projektmappensymbol im **Projektmappen-Explorer**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f3b17-154">Right-click the solution icon in **Solution Explorer**, and then click **Add**.</span></span> <span data-ttu-id="f3b17-155">Der Standardspeicherort für Skriptprojektordner lautet: „C:\Dokumente und Einstellungen\\*Benutzername*\Eigene Dokumente\SQL Server Management Studio\Projects\\.</span><span class="sxs-lookup"><span data-stu-id="f3b17-155">The default location for script project folders is: C:\Documents and Settings\\*username*\My Documents\SQL Server Management Studio\Projects\\.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b17-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3b17-156">See Also</span></span>  
 <span data-ttu-id="f3b17-157">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-157">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="f3b17-158">[Vorhandenes Projekt zu einer Projekt Mappe hinzufügen](add-an-existing-project-to-a-solution.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-158">[Add an Existing Project to a Solution](add-an-existing-project-to-a-solution.md) </span></span>  
 <span data-ttu-id="f3b17-159">[Hinzufügen neuer Elemente zu einem Projekt](add-new-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-159">[Add New Items to a Project](add-new-items-to-a-project.md) </span></span>  
 <span data-ttu-id="f3b17-160">[Hinzufügen vorhandener Elemente zu einem Projekt](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-160">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 <span data-ttu-id="f3b17-161">[Ändern des Standard Speicher Orts für Projekte](change-the-default-location-for-projects.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-161">[Change the Default Location for Projects](change-the-default-location-for-projects.md) </span></span>  
 <span data-ttu-id="f3b17-162">[Entfernen oder Löschen eines Elements oder Projekts](remove-or-delete-an-item-or-project.md) </span><span class="sxs-lookup"><span data-stu-id="f3b17-162">[Remove or Delete an Item or Project](remove-or-delete-an-item-or-project.md) </span></span>  
 [<span data-ttu-id="f3b17-163">Löschen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="f3b17-163">Delete a Solution</span></span>](delete-a-solution.md)  
  
  
