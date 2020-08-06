---
title: Anzeigen einer Liste geänderter Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckinWindow
helpviewer_keywords:
- listing modified files
- modified files list [SQL Server]
- checking in files
ms.assetid: 1b053719-8500-4300-a169-fffca5801dd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a2899ab9889908089d17b3c929e7bf4b2dfe2185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620504"
---
# <a name="view-a-list-of-modified-files"></a><span data-ttu-id="710c4-102">Anzeigen einer Liste geänderter Dateien</span><span class="sxs-lookup"><span data-stu-id="710c4-102">View a List of Modified Files</span></span>
  <span data-ttu-id="710c4-103">Sie können das Fenster **anstehende Eincheck** Vorgänge verwenden, um jederzeit eine Liste der ausgecheckten Dateien in der aktuellen Projekt Mappe anzuzeigen und diese Dateien mit einem Klick auf die Schaltfläche einzuchecken.</span><span class="sxs-lookup"><span data-stu-id="710c4-103">You can use the **Pending Checkins** window to display at all times a list of the checked-out files in the current solution, and to check in these files with a single button click.</span></span>  
  
### <a name="to-view-a-list-of-modified-files"></a><span data-ttu-id="710c4-104">So zeigen Sie eine Liste geänderter Dateien an</span><span class="sxs-lookup"><span data-stu-id="710c4-104">To view a list of modified files</span></span>  
  
1.  <span data-ttu-id="710c4-105">Klicken Sie im Menü **Ansicht** auf **anstehende Eincheck**Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="710c4-105">On the **View** menu, click **Pending Checkins**.</span></span>  
  
2.  <span data-ttu-id="710c4-106">Klicken Sie auf **Einchecken**, um die ausgewählten Dateien einzuchecken.</span><span class="sxs-lookup"><span data-stu-id="710c4-106">To check in the selected files, click **Check In**.</span></span> <span data-ttu-id="710c4-107">Alternativ können Sie das Fenster **anstehende Eincheck** Vorgänge auf der rechten Seite der Umgebung andocken, [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] damit Sie die Dateien einchecken können, wenn die Arbeit abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="710c4-107">Alternatively, you can dock the **Pending Checkins** window on the right side of the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment so that you can check in the files when you are finished working.</span></span>  
  
     <span data-ttu-id="710c4-108">**Ankunft**</span><span class="sxs-lookup"><span data-stu-id="710c4-108">**Check In**</span></span>  
     <span data-ttu-id="710c4-109">Checkt die Projektmappe ein.</span><span class="sxs-lookup"><span data-stu-id="710c4-109">Checks in the solution.</span></span>  
  
     <span data-ttu-id="710c4-110">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="710c4-110">**Comments**</span></span>  
     <span data-ttu-id="710c4-111">Ordnet dem ausstehenden Eincheckvorgang einen Nur-Text-Kommentar zu.</span><span class="sxs-lookup"><span data-stu-id="710c4-111">Associates a plain text comment with the pending check in.</span></span> <span data-ttu-id="710c4-112">Für jede Version eines Projekts wird ein Kommentar erstellt und zugeordnet und in der Datenbank für die Quellcodeverwaltung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="710c4-112">A comment is created and associated with each version of a project, and stored in the source control database.</span></span>  
  
     <span data-ttu-id="710c4-113">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="710c4-113">**Options**</span></span>  
     <span data-ttu-id="710c4-114">Gibt die Aktionen an, die die Quell Code Verwaltung durchführen soll, wenn Sie auf die Schaltfläche **Einchecken** klicken.</span><span class="sxs-lookup"><span data-stu-id="710c4-114">Specifies the actions that source control should take when you click the **Check In** button.</span></span>  
  
    -   <span data-ttu-id="710c4-115">**Alle ausgecheckt lassen**</span><span class="sxs-lookup"><span data-stu-id="710c4-115">**Keep All Checked Out**</span></span>  
  
         <span data-ttu-id="710c4-116">Gibt an, dass Ihre Änderungen in den Quellcodeverwaltungsanbieter geschrieben werden, die Dateien aber weiterhin ausgecheckt bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="710c4-116">Specifies that your changes should be written to the source control provider but that the files should remain checked out.</span></span>  
  
     <span data-ttu-id="710c4-117">**Sort**</span><span class="sxs-lookup"><span data-stu-id="710c4-117">**Sort**</span></span>  
     <span data-ttu-id="710c4-118">Gibt die Sortierreihenfolge für die Spalten an, die in der Elementliste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="710c4-118">Specifies the sort order for the columns displayed in the Items list.</span></span>  
  
     <span data-ttu-id="710c4-119">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="710c4-119">**Columns**</span></span>  
     <span data-ttu-id="710c4-120">Zeigt eine Liste der Spalten an, die Sie der Elementliste des Fensters hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="710c4-120">Displays a list of the columns you can add to the window's Items list.</span></span>  
  
     <span data-ttu-id="710c4-121">**Strukturansicht**</span><span class="sxs-lookup"><span data-stu-id="710c4-121">**Tree View**</span></span>  
     <span data-ttu-id="710c4-122">Zeigt die Ordner- und Dateihierarchie für die Projektmappe bzw. das Projekt an, dass Sie einchecken.</span><span class="sxs-lookup"><span data-stu-id="710c4-122">Displays the folder and file hierarchy for the solution or project you are checking in.</span></span>  
  
     <span data-ttu-id="710c4-123">**Flache Ansicht**</span><span class="sxs-lookup"><span data-stu-id="710c4-123">**Flat View**</span></span>  
     <span data-ttu-id="710c4-124">Zeigt die Dateien, die Sie einchecken, als flache Listen unter ihrer Quell Code Verwaltungs Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="710c4-124">Displays the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="710c4-125">**Versionsvergleich**</span><span class="sxs-lookup"><span data-stu-id="710c4-125">**Compare Versions**</span></span>  
     <span data-ttu-id="710c4-126">Öffnet das Dialogfeld mit den **unterschiedlichen Optionen** für Visual SourceSafe, das eine ausgewählte Datei im Entwicklungs Umgebungs Projekt mit einer beliebigen anderen ausgewählten Datei vergleicht und ggf. die Unterschiede anzeigt.</span><span class="sxs-lookup"><span data-stu-id="710c4-126">Opens the Visual SourceSafe **Difference Options** dialog box, which compares a selected file in your development environment project to any other selected file and shows you the differences, if any.</span></span>  
  
     <span data-ttu-id="710c4-127">**Rückgängig: Auschecken**</span><span class="sxs-lookup"><span data-stu-id="710c4-127">**Undo checkout**</span></span>  
     <span data-ttu-id="710c4-128">Kehrt das Auschecken aller im Fenster **ausstehende Eincheck** Vorgänge ausgewählten Elemente um.</span><span class="sxs-lookup"><span data-stu-id="710c4-128">Reverses the checkout of all items selected in the **Pending Checkins** window.</span></span>  
  
     <span data-ttu-id="710c4-129">**Name**</span><span class="sxs-lookup"><span data-stu-id="710c4-129">**Name**</span></span>  
     <span data-ttu-id="710c4-130">Zeigt eine Liste der für den Eincheckvorgang verfügbaren Elemente an.</span><span class="sxs-lookup"><span data-stu-id="710c4-130">Displays a list of the items available for check in.</span></span> <span data-ttu-id="710c4-131">Das Kontrollkästchen neben den Elementen ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="710c4-131">Items appear with the check box next to them selected.</span></span> <span data-ttu-id="710c4-132">Wenn Sie ein bestimmtes Element nicht einchecken möchten, deaktivieren Sie das Kontrollkästchen daneben.</span><span class="sxs-lookup"><span data-stu-id="710c4-132">If you do not want to check in a particular item, clear the check box next to it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710c4-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="710c4-133">See Also</span></span>  
 <span data-ttu-id="710c4-134">[Check-Ins verwalten](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="710c4-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="710c4-135">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="710c4-135">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
