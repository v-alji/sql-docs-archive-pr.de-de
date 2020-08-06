---
title: Erstellen, Löschen oder Ändern eines Ordners (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619585"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="11208-102">Erstellen, Löschen oder Ändern eines Ordners (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="11208-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="11208-103">Sie können Ordner erstellen, um die auf einem Berichtsserver zu veröffentlichenden Elemente zu organisieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="11208-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="11208-104">Mit der Erstellung von Ordnern können Benutzer relevante Berichte leichter finden.</span><span class="sxs-lookup"><span data-stu-id="11208-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="11208-105">Für Inhalts-Manager stellen Ordner ein Framework für die Anwendung von Berechtigungen dar.</span><span class="sxs-lookup"><span data-stu-id="11208-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="11208-106">Sie können Rollenzuweisungen für bestimmte Ordner erstellen, um den Zugriff auf Berichte einzuschränken, die sich aktuell in der Entwicklung befinden oder die nur bestimmten Personen zugänglich gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="11208-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="11208-107">So erstellen Sie einen Ordner</span><span class="sxs-lookup"><span data-stu-id="11208-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="11208-108">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="11208-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="11208-109">Wählen Sie im Berichts-Manager den Ordner Home, und klicken Sie auf **Neuer Ordner**.</span><span class="sxs-lookup"><span data-stu-id="11208-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="11208-110">Sie können einen Ordner auch unter einem vorhandenen Ordner erstellen. Navigieren Sie auf der Seite **Inhalt** zu diesem Ordner, und klicken Sie darauf, um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11208-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="11208-111">Klicken Sie dann auf **Neuer Ordner**.</span><span class="sxs-lookup"><span data-stu-id="11208-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="11208-112">Die Seite **Neuer Ordner** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="11208-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="11208-113">Geben Sie einen Ordnernamen ein.</span><span class="sxs-lookup"><span data-stu-id="11208-113">Type a folder name.</span></span> <span data-ttu-id="11208-114">Ein Ordnername kann Leerzeichen enthalten, jedoch keine reservierten Zeichen, die für die URL-Codierung verwendet werden: ; ?</span><span class="sxs-lookup"><span data-stu-id="11208-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="11208-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="11208-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="11208-116">Sie können keine Reihe von Ordnernamen eingeben, um mehrere Ordner gleichzeitig zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11208-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="11208-117">Geben Sie optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="11208-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="11208-118">Wählen Sie **In Listenansicht ausblenden** aus, wenn Sie den Ordner nicht in der Standardansicht der Seite **Inhalt** anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="11208-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="11208-119">Der Ordner wird Benutzern nur dann angezeigt, wenn sie auf der Seite **Inhalt** auf **Details anzeigen** klicken.</span><span class="sxs-lookup"><span data-stu-id="11208-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="11208-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="11208-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="11208-121">So löschen Sie einen Ordner</span><span class="sxs-lookup"><span data-stu-id="11208-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="11208-122">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und suchen Sie das zu ändernde Element.</span><span class="sxs-lookup"><span data-stu-id="11208-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="11208-123">Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="11208-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="11208-124">Klicken Sie im Dropdownmenü auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="11208-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="11208-125">So ändern oder löschen Sie einen Ordner</span><span class="sxs-lookup"><span data-stu-id="11208-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="11208-126">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und suchen Sie das zu ändernde Element.</span><span class="sxs-lookup"><span data-stu-id="11208-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="11208-127">Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="11208-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="11208-128">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="11208-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="11208-129">Die Seite Allgemeine Eigenschaften wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="11208-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="11208-130">Klicken Sie auf **Verschieben**, um den Speicherort des Ordners zu ändern.</span><span class="sxs-lookup"><span data-stu-id="11208-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="11208-131">Geben Sie den Speicherort des Zielordners ein, oder wählen Sie den Zielordner aus der Struktur aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="11208-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="11208-132">Sie können die Ordnereigenschaften auch folgendermaßen ändern:</span><span class="sxs-lookup"><span data-stu-id="11208-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="11208-133">Geben Sie einen Namen oder eine Beschreibung ein, um den angezeigten Text über den Ordner zu ändern.</span><span class="sxs-lookup"><span data-stu-id="11208-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="11208-134">Um den Ordner in der Standardansicht auf der Seite **Inhalt** anzuzeigen, deaktivieren Sie die Option **In Listenansicht ausblenden**.</span><span class="sxs-lookup"><span data-stu-id="11208-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="11208-135">Sie können den Ordner und seinen Inhalt auch entfernen, indem Sie auf **Löschen**klicken.</span><span class="sxs-lookup"><span data-stu-id="11208-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="11208-136">Klicken Sie auf **Apply** (Übernehmen), um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="11208-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11208-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11208-137">See Also</span></span>  
 <span data-ttu-id="11208-138">[Die Seite "neuer Ordner" &#40;Berichts-Manager&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="11208-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="11208-139">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="11208-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="11208-140">Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="11208-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
