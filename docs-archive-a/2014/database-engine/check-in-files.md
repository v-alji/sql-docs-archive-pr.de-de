---
title: Einchecken von Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourceControl.CheckInDialog
helpviewer_keywords:
- checking in files
ms.assetid: 0657a387-8411-4406-bef9-d262a5bfa269
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 070c1dfa5dd057cf777980f7022752a97a4dc84c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619365"
---
# <a name="check-in-files"></a><span data-ttu-id="32288-102">Einchecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="32288-102">Check In Files</span></span>
  <span data-ttu-id="32288-103">Um von Ihnen geänderte quellcodeverwaltete Dateien für andere Benutzer verfügbar zu machen, müssen Sie die Dateien zunächst in die Quellcodeverwaltung einchecken.</span><span class="sxs-lookup"><span data-stu-id="32288-103">To make source-controlled files that you have modified available to other users, you must check the files into source control.</span></span> <span data-ttu-id="32288-104">Wenn Sie eine Datei einchecken, wird die von Ihnen eingecheckte Version in den Quellcodeverwaltungsanbieter geschrieben und als aktuelle Dateiversion festgelegt.</span><span class="sxs-lookup"><span data-stu-id="32288-104">When you check in a file, the version you check in is written to the source control provider and becomes the latest version of the file.</span></span>  
  
 <span data-ttu-id="32288-105">Sie können den Befehl **Einchecken** verwenden, um Dateien einzuchecken.</span><span class="sxs-lookup"><span data-stu-id="32288-105">You can use the **Check In** command to check in files.</span></span> <span data-ttu-id="32288-106">Wenn Sie mit diesem Befehl eine Projektmappe oder ein Projekt einchecken, werden auch alle Dateien eingecheckt, die sich in der Projektmappe bzw. im Projekt befinden.</span><span class="sxs-lookup"><span data-stu-id="32288-106">If you use this command to check in a solution or project, all the files in the solution or project are also checked in.</span></span> <span data-ttu-id="32288-107">Umgekehrt wird durch das Einchecken einer einzelnen Quellcodedatei nicht das Projekt bzw. die Projektmappe eingecheckt, zu der sie gehört.</span><span class="sxs-lookup"><span data-stu-id="32288-107">However, checking in an individual source code file does not result in the check-in of the project or solution to which it belongs.</span></span>  
  
### <a name="to-check-in-a-file"></a><span data-ttu-id="32288-108">So checken Sie eine Datei ein</span><span class="sxs-lookup"><span data-stu-id="32288-108">To check in a file</span></span>  
  
1.  <span data-ttu-id="32288-109">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf die Datei, die Sie einchecken möchten, und klicken Sie dann auf **Einchecken**.</span><span class="sxs-lookup"><span data-stu-id="32288-109">In Solution Explorer, right-click the file to check in, and then click **Check In**.</span></span>  
  
2.  <span data-ttu-id="32288-110">Wenn das **Eincheck** Dialogfeld angezeigt wird, wählen Sie die entsprechenden Optionen aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="32288-110">If the **Check In** dialog box appears, select the appropriate options, and then click **OK**.</span></span>  
  
     <span data-ttu-id="32288-111">**Ankunft**</span><span class="sxs-lookup"><span data-stu-id="32288-111">**Check In**</span></span>  
     <span data-ttu-id="32288-112">Checkt die ausgewählten Elemente ein.</span><span class="sxs-lookup"><span data-stu-id="32288-112">Check in all the selected items.</span></span>  
  
     <span data-ttu-id="32288-113">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="32288-113">**Columns**</span></span>  
     <span data-ttu-id="32288-114">Bestimmt die anzuzeigenden Spalten und die Reihenfolge, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="32288-114">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="32288-115">**Kommentare**</span><span class="sxs-lookup"><span data-stu-id="32288-115">**Comments**</span></span>  
     <span data-ttu-id="32288-116">Fügt einen Kommentar für den Eincheckvorgang hinzu.</span><span class="sxs-lookup"><span data-stu-id="32288-116">Add a comment to associate with the check-in operation.</span></span>  
  
     <span data-ttu-id="32288-117">**Dialogfeld "Einchecken" beim Einchecken von Elementen nicht anzeigen**</span><span class="sxs-lookup"><span data-stu-id="32288-117">**Don't show Check in dialog box when checking in items**</span></span>  
     <span data-ttu-id="32288-118">Unterdrückt die Anzeige des Dialogfelds bei Eincheckvorgängen.</span><span class="sxs-lookup"><span data-stu-id="32288-118">Suppress the dialog box during check-in operations.</span></span>  
  
     <span data-ttu-id="32288-119">**Flache Ansicht**</span><span class="sxs-lookup"><span data-stu-id="32288-119">**Flat View**</span></span>  
     <span data-ttu-id="32288-120">Zeigt die Dateien, die eingecheckt werden, als flache Listen unter der entsprechenden Verbindung mit der Quellcodeverwaltung an.</span><span class="sxs-lookup"><span data-stu-id="32288-120">Display the files you are checking in as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="32288-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="32288-121">**Name**</span></span>  
     <span data-ttu-id="32288-122">Zeigt die Namen der einzucheckenden Elemente an.</span><span class="sxs-lookup"><span data-stu-id="32288-122">Displays the names of the items to check in.</span></span> <span data-ttu-id="32288-123">Die Elemente werden mit einem aktivierten Kontrollkästchen neben dem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32288-123">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="32288-124">Wenn ein Element nicht eingecheckt werden soll, deaktivieren Sie das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="32288-124">If you do not want to check in a particular item, clear its check box.</span></span>  
  
     <span data-ttu-id="32288-125">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="32288-125">**Options**</span></span>  
     <span data-ttu-id="32288-126">Zeigt die für das Quellcodeverwaltungs-Plug-In spezifischen Eincheckoptionen an, wenn Sie auf den Pfeil rechts neben der Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="32288-126">Displays source control plug-in-specific check-in options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="32288-127">**Sort**</span><span class="sxs-lookup"><span data-stu-id="32288-127">**Sort**</span></span>  
     <span data-ttu-id="32288-128">Sortiert die Reihenfolge der Anzeigespalten.</span><span class="sxs-lookup"><span data-stu-id="32288-128">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="32288-129">**Strukturansicht**</span><span class="sxs-lookup"><span data-stu-id="32288-129">**Tree View**</span></span>  
     <span data-ttu-id="32288-130">Zeigt die Ordner- und Dateihierarchie für die eingecheckten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="32288-130">Display the folder and file hierarchy for the items you are checking in.</span></span>  
  
 <span data-ttu-id="32288-131">Wenn die Datei, die Sie eingecheckt haben, nicht zu einem freigegebenen ausgecheckten Element gehört, wird die Datei von der [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]-Umgebung unmittelbar eingecheckt.</span><span class="sxs-lookup"><span data-stu-id="32288-131">If the file you have checked in is not part of a shared checkout, the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment checks in the file immediately.</span></span> <span data-ttu-id="32288-132">Ist dies nicht der Fall, werden Sie unter Umständen aufgefordert, Ihre Version mit Versionen zusammenzuführen, die von anderen Benutzern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="32288-132">Otherwise, it may prompt you to merge your version with versions created by other users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32288-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32288-133">See Also</span></span>  
 <span data-ttu-id="32288-134">[Anzeigen einer Liste geänderter Dateien](../../2014/database-engine/view-a-list-of-modified-files.md) </span><span class="sxs-lookup"><span data-stu-id="32288-134">[View a List of Modified Files](../../2014/database-engine/view-a-list-of-modified-files.md) </span></span>  
 [<span data-ttu-id="32288-135">Verwalten von Eincheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="32288-135">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)  
  
  
