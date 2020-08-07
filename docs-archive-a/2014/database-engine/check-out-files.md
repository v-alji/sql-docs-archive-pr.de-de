---
title: Auschecken von Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- Visual Studio.SourceControl.CheckOutDialog
helpviewer_keywords:
- checking out files
ms.assetid: cc033727-51bb-4b58-a12b-8977ce61ff56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 151f554742bd6c381b27b58155d3f0e40e9eeb0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619364"
---
# <a name="check-out-files"></a><span data-ttu-id="eb07e-102">Auschecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="eb07e-102">Check Out Files</span></span>
  <span data-ttu-id="eb07e-103">Sie müssen eine Datei auschecken, bevor Sie sie bearbeiten können, es sei denn, Sie haben die [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Umgebung so konfiguriert, dass eingecheckte Dateien bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="eb07e-103">Unless you have configured the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment to permit checked-in files to be edited, you must check out a file before you can modify it.</span></span> <span data-ttu-id="eb07e-104">Beim Auschecken einer Datei wird eine Kopie der Dateiversion auf den lokalen Datenträger kopiert, und der Schreibschutz der Datei wird entfernt.</span><span class="sxs-lookup"><span data-stu-id="eb07e-104">When you check out a file, a copy of the file version is copied to your local disk, and the read-only attribute of the file is removed.</span></span>  
  
 <span data-ttu-id="eb07e-105">Sie können Dateien entweder exklusiv oder im Modus für gemeinsame Nutzung auschecken.</span><span class="sxs-lookup"><span data-stu-id="eb07e-105">You can check files out either exclusively or in shared mode.</span></span> <span data-ttu-id="eb07e-106">Wenn Sie eine Datei exklusiv auschecken, kann sie von einem anderen Benutzer erst dann ausgecheckt werden, nachdem Sie sie wieder eingecheckt haben.</span><span class="sxs-lookup"><span data-stu-id="eb07e-106">When you check out a file exclusively, no other user can check out the file until you check it in.</span></span> <span data-ttu-id="eb07e-107">Wenn Sie eine Datei im Modus für gemeinsame Nutzung auschecken, können andere Benutzer die Datei auschecken und ändern. Wenn Sie die Datei einchecken, müssen Sie die von Ihnen ausgecheckte Version möglicherweise mit den Versionen zusammenführen, die von anderen Benutzern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="eb07e-107">When you check out a file in shared mode, other users can check out and modify the file, and when you check it in, you may need to merge the version you have checked out with the versions created by other users.</span></span>  
  
 <span data-ttu-id="eb07e-108">Verwenden Sie den Befehl **Auschecken** , um Projekte und Dateien der Quell Code Verwaltung auszuchecken.</span><span class="sxs-lookup"><span data-stu-id="eb07e-108">Use the **Check Out** command to check out source-controlled projects and files.</span></span> <span data-ttu-id="eb07e-109">Wenn Sie mit diesem Befehl eine Projekt Mappe oder ein Projekt Auschecken, werden auch alle Dateien in der Projekt Mappe oder im Projekt ausgecheckt. Das Auschecken einer einzelnen Quell Code Datei führt jedoch nicht dazu, dass das Projekt oder die Projekt Mappe, zu der es gehört, ausgecheckt wird.</span><span class="sxs-lookup"><span data-stu-id="eb07e-109">If you use this command to check out a solution or project, all the files in the solution or project are also checked out. However, checking out an individual source code file does not result in the check out of the project or solution to which it belongs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb07e-110">Wenn die [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe-Datenbank für Ihr Projekt so konfiguriert ist, dass mehrere Auscheck Vorgänge zulässig sind, und Sie eine Datei exklusiv auschecken möchten, müssen Sie im Dialogfeld **Erweiterte auscheckungs Optionen** die Option **mehrere Auschecken zulassen** deaktivieren, bevor Sie die Datei Auschecken.</span><span class="sxs-lookup"><span data-stu-id="eb07e-110">If the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database for your project is configured to allow multiple checkouts, and you want to check out a file exclusively, you must clear the **Allow multiple checkouts** option in the **Advanced Check Out Options** dialog box before checking out the file.</span></span> <span data-ttu-id="eb07e-111">Damit diese Einstellung wirksam wird, müssen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] neu starten.</span><span class="sxs-lookup"><span data-stu-id="eb07e-111">You must restart the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for this setting to take effect.</span></span>  
  
### <a name="to-check-out-a-file"></a><span data-ttu-id="eb07e-112">So checken Sie eine Datei aus</span><span class="sxs-lookup"><span data-stu-id="eb07e-112">To check out a file</span></span>  
  
1.  <span data-ttu-id="eb07e-113">Wählen Sie das Projekt oder die Datei im Projektmappen-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="eb07e-113">In Solution Explorer, select the project or file.</span></span>  
  
2.  <span data-ttu-id="eb07e-114">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **Auschecken zum Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eb07e-114">On the **File** menu, point to **Source Control**, and then click **Check Out for Edit**.</span></span>  
  
3.  <span data-ttu-id="eb07e-115">Wenn das Dialogfeld **Auschecken zum Bearbeiten** angezeigt wird, wählen Sie die gewünschten Elemente aus, und klicken Sie auf **Auschecken**. Wenn Sie die Umgebung so konfiguriert haben, [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] dass das Dialogfeld " **Auschecken** " nicht angezeigt wird, werden die Elemente, die in Projektmappen-Explorer ausgewählt wurden, sowie alle untergeordneten Elemente sofort ausgecheckt.</span><span class="sxs-lookup"><span data-stu-id="eb07e-115">If the **Check Out for Edit** dialog box is displayed, select the items you want, and click **Check Out**. If you have configured the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment not to display the **Check Out** dialog box, the items selected in Solution Explorer and any children they might have are checked out immediately.</span></span>  
  
     <span data-ttu-id="eb07e-116">**Abreise**</span><span class="sxs-lookup"><span data-stu-id="eb07e-116">**Check Out**</span></span>  
     <span data-ttu-id="eb07e-117">Die ausgewählten Elemente werden ausgecheckt.</span><span class="sxs-lookup"><span data-stu-id="eb07e-117">Check out all the selected items.</span></span>  
  
     <span data-ttu-id="eb07e-118">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="eb07e-118">**Columns**</span></span>  
     <span data-ttu-id="eb07e-119">Bestimmt die anzuzeigenden Spalten und die Reihenfolge, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb07e-119">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="eb07e-120">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="eb07e-120">**Comments**</span></span>  
     <span data-ttu-id="eb07e-121">Hier können Sie einen Kommentar für den Auscheckvorgang eingeben.</span><span class="sxs-lookup"><span data-stu-id="eb07e-121">Specify a comment to associate with the checkout operation.</span></span>  
  
     <span data-ttu-id="eb07e-122">**Dialogfeld "Auschecken" beim Auschecken von Elementen nicht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="eb07e-122">**Don't Show Check Out dialog box when checking out items**</span></span>  
     <span data-ttu-id="eb07e-123">Unterdrückt die Anzeige des Dialogfelds während Auscheckvorgängen.</span><span class="sxs-lookup"><span data-stu-id="eb07e-123">Suppress the dialog box during checkout operations.</span></span>  
  
     <span data-ttu-id="eb07e-124">**Flache Ansicht**</span><span class="sxs-lookup"><span data-stu-id="eb07e-124">**Flat View**</span></span>  
     <span data-ttu-id="eb07e-125">Zeigt die Elemente, die ausgecheckt werden, als flache Listen unter der entsprechenden Verbindung mit der Quellcodeverwaltung an.</span><span class="sxs-lookup"><span data-stu-id="eb07e-125">Display the items you are checking out as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="eb07e-126">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="eb07e-126">**Edit**</span></span>  
     <span data-ttu-id="eb07e-127">Ändern Sie ein Element, ohne es auszuchecken. Die Schaltfläche **Bearbeiten** wird nur angezeigt, wenn Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] für die Unterstützung der Bearbeitung von eingecheckten Dateien konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="eb07e-127">Modify an item without checking it out. The **Edit** button appears only if you have [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] configured to support the editing of checked-in files.</span></span>  
  
     <span data-ttu-id="eb07e-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="eb07e-128">**Name**</span></span>  
     <span data-ttu-id="eb07e-129">Zeigt die Namen der Elemente an, die für das Auschecken verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eb07e-129">Displays the names of the items available for checkout.</span></span> <span data-ttu-id="eb07e-130">Die ausgewählten Elemente werden mit einem Kontrollkästchen neben dem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb07e-130">Items that are selected appear with check boxes next to them.</span></span> <span data-ttu-id="eb07e-131">Wenn ein Element nicht ausgecheckt werden soll, deaktivieren Sie das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="eb07e-131">If you do not want to check out a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="eb07e-132">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="eb07e-132">**Options**</span></span>  
     <span data-ttu-id="eb07e-133">Zeigt die für das Quellcodeverwaltungs-Plug-In spezifischen Optionen zum Auschecken an, wenn Sie auf den Pfeil rechts neben der Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="eb07e-133">Displays source control plug-in-specific checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="eb07e-134">**Sort**</span><span class="sxs-lookup"><span data-stu-id="eb07e-134">**Sort**</span></span>  
     <span data-ttu-id="eb07e-135">Sortiert die Reihenfolge der angezeigten Spalten.</span><span class="sxs-lookup"><span data-stu-id="eb07e-135">Sort the order of the displayed columns.</span></span>  
  
     <span data-ttu-id="eb07e-136">**Strukturansicht**</span><span class="sxs-lookup"><span data-stu-id="eb07e-136">**Tree View**</span></span>  
     <span data-ttu-id="eb07e-137">Zeigt die Ordner- und Dateihierarchie für das Element an, das ausgecheckt wird.</span><span class="sxs-lookup"><span data-stu-id="eb07e-137">Display the folder and file hierarchy for the item you are checking out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb07e-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb07e-138">See Also</span></span>  
 <span data-ttu-id="eb07e-139">[Eingecheckte Dateien bearbeiten](../../2014/database-engine/edit-checked-in-files.md) </span><span class="sxs-lookup"><span data-stu-id="eb07e-139">[Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md) </span></span>  
 <span data-ttu-id="eb07e-140">[Dateien beim Bearbeiten automatisch Auschecken](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span><span class="sxs-lookup"><span data-stu-id="eb07e-140">[Automatically Check Out Files Upon Edit](../../2014/database-engine/automatically-check-out-files-upon-edit.md) </span></span>  
 <span data-ttu-id="eb07e-141">[Rückgängigmachen](../../2014/database-engine/undo-checkouts.md) </span><span class="sxs-lookup"><span data-stu-id="eb07e-141">[Undo Checkouts](../../2014/database-engine/undo-checkouts.md) </span></span>  
 [<span data-ttu-id="eb07e-142">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="eb07e-142">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
