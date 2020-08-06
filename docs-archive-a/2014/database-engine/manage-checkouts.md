---
title: Verwalten von Auscheck Vorgängen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- source controls [SQL Server Management Studio], checkouts
- checkouts [SQL Server Management Studio]
- checking out files
ms.assetid: ddd4adba-d432-4005-9cb2-bb9ee3163d8e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cdfa25cdc27e707d4be705e66b215130c9d70ce1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622817"
---
# <a name="manage-checkouts"></a><span data-ttu-id="36f7e-102">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="36f7e-102">Manage Checkouts</span></span>
  <span data-ttu-id="36f7e-103">Nachdem eine Datei der Quellcodeverwaltung hinzugefügt wurde, müssen Sie die Datei auschecken, bevor Sie sie ändern können.</span><span class="sxs-lookup"><span data-stu-id="36f7e-103">After a file has been added to source control, you must check out the file before you can modify it.</span></span> <span data-ttu-id="36f7e-104">Beim Auschecken einer Datei aus der Quellcodeverwaltung erstellt der Quellcodeverwaltungsanbieter auf dem lokalen Datenträger eine Kopie der letzten Version und entfernt den Schreibschutz der Datei.</span><span class="sxs-lookup"><span data-stu-id="36f7e-104">When you check a file out of source control, the source control provider creates a copy of the latest version on your local disk and removes the read-only attribute of the file.</span></span> <span data-ttu-id="36f7e-105">In bestimmten Situationen müssen Sie möglicherweise eine Datei bearbeiten, ohne sie auszuchecken.</span><span class="sxs-lookup"><span data-stu-id="36f7e-105">In some circumstances you might need to edit a file without checking out the file.</span></span> <span data-ttu-id="36f7e-106">Weitere Informationen zum Bearbeiten einer Datei, ohne die Datei auszuchecken, finden Sie unter [Edit Check-in Files](../../2014/database-engine/edit-checked-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="36f7e-106">For more information about editing a file without checking the file out, see [Edit Checked-In Files](../../2014/database-engine/edit-checked-in-files.md).</span></span>  
  
 <span data-ttu-id="36f7e-107">Mit können Sie [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Dateien manuell oder automatisch auschecken.</span><span class="sxs-lookup"><span data-stu-id="36f7e-107">You can use [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out files manually or automatically.</span></span> <span data-ttu-id="36f7e-108">Sie checken Dateien manuell aus, indem Sie die Projekt Mappe öffnen, die die Dateien in der [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Umgebung enthält, und klicken Sie dann auf den Befehl **Auschecken** .</span><span class="sxs-lookup"><span data-stu-id="36f7e-108">You check out files manually by opening the solution that contains the files in the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment, and then clicking the **Check Out** command.</span></span> <span data-ttu-id="36f7e-109">Sie können Dateien automatisch auschecken, wenn Sie die [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]-Umgebung entsprechend konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="36f7e-109">You can check out files automatically if you configure the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to do so.</span></span>  
  
 <span data-ttu-id="36f7e-110">Abhängig von den Optionen, die der Administrator für den Quellcodeverwaltungsanbieter festlegt, können Sie Dateien zudem im Modus für exklusive oder gemeinsame Nutzung auschecken.</span><span class="sxs-lookup"><span data-stu-id="36f7e-110">Depending on the options that your administrator sets on your source control provider, you can also check out files in exclusive or shared mode.</span></span> <span data-ttu-id="36f7e-111">Wenn Sie eine Datei exklusiv auschecken, können nur Sie diese Datei bearbeiten. Ein anderer Benutzer kann die Datei erst dann auschecken, nachdem Sie sie wieder eingecheckt haben.</span><span class="sxs-lookup"><span data-stu-id="36f7e-111">When you check out a file exclusively, only you can modify it, and no other user can check out the file until you check it in.</span></span> <span data-ttu-id="36f7e-112">Wenn Sie eine Datei im freigegebenen Modus auschecken, kann sie von beliebig vielen Benutzern gleichzeitig ausgecheckt werden.</span><span class="sxs-lookup"><span data-stu-id="36f7e-112">When you check out a file in shared mode, any number of users can check out the same file.</span></span> <span data-ttu-id="36f7e-113">Da jeder Benutzer die Datei eincheckt, versucht der Quellcodeverwaltungsanbieter, die Datei mit der letzten Serverversion der Datei zusammenzuführen.</span><span class="sxs-lookup"><span data-stu-id="36f7e-113">As each user checks in the file, the source control provider attempts to merge the file with the latest server version of the file.</span></span> <span data-ttu-id="36f7e-114">Wenn Konflikte zwischen der eingecheckten Version und der letzten Version auftreten, wird der Benutzer vom Quellcodeverwaltungsanbieter aufgefordert, die Konflikte zu lösen.</span><span class="sxs-lookup"><span data-stu-id="36f7e-114">If conflicts arise between the version that is being checked in and the latest version, the source control provider prompts the user to resolve the conflicts.</span></span>  
  
 <span data-ttu-id="36f7e-115">In der folgenden Tabelle werden die Themen in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36f7e-115">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="36f7e-116">Thema</span><span class="sxs-lookup"><span data-stu-id="36f7e-116">Topic</span></span>|<span data-ttu-id="36f7e-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="36f7e-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="36f7e-118">Auschecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="36f7e-118">Check Out Files</span></span>](../../2014/database-engine/check-out-files.md)|<span data-ttu-id="36f7e-119">Enthält Anweisungen zum Auschecken von Dateien, damit Sie sie ändern können.</span><span class="sxs-lookup"><span data-stu-id="36f7e-119">Provides instructions on how to check out a file so you can modify it.</span></span>|  
|[<span data-ttu-id="36f7e-120">Rückgängigmachen von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="36f7e-120">Undo Checkouts</span></span>](../../2014/database-engine/undo-checkouts.md)|<span data-ttu-id="36f7e-121">Erläutert, wie Sie ein vorhandenes Auschecken abbrechen können.</span><span class="sxs-lookup"><span data-stu-id="36f7e-121">Explains how to cancel an existing checkout.</span></span>|  
|[<span data-ttu-id="36f7e-122">Automatisches Auschecken von Dateien beim Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="36f7e-122">Automatically Check Out Files Upon Edit</span></span>](../../2014/database-engine/automatically-check-out-files-upon-edit.md)|<span data-ttu-id="36f7e-123">Beschreibt, wie Sie die Quellcodeverwaltung konfigurieren können, damit Dateien beim Beginnen der Bearbeitung ausgecheckt werden.</span><span class="sxs-lookup"><span data-stu-id="36f7e-123">Explains how to configure source control to check out a file when you start to edit it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36f7e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36f7e-124">See Also</span></span>  
 <span data-ttu-id="36f7e-125">[Check-Ins verwalten](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="36f7e-125">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="36f7e-126">Bearbeiten eingecheckter Dateien</span><span class="sxs-lookup"><span data-stu-id="36f7e-126">Edit Checked-In Files</span></span>](../../2014/database-engine/edit-checked-in-files.md)  
  
  
