---
title: Geben Sie eine Version als neueste Version an | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608818"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="23f04-102">Angeben einer Version als letzte Version</span><span class="sxs-lookup"><span data-stu-id="23f04-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="23f04-103">Wenn Sie eine Datei in die Quellcodeverwaltung einchecken, wird die eingecheckte Version zur letzten Version. Benutzer, die die letzte Version auschecken oder abrufen, erhalten lokale Kopien des zuletzt eingecheckten Elements.</span><span class="sxs-lookup"><span data-stu-id="23f04-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="23f04-104">In einigen Situationen können Sie aber auch eine frühere Version eines Elements als letzte Version bestimmen.</span><span class="sxs-lookup"><span data-stu-id="23f04-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="23f04-105">Sie können z. B. eine Datei auschecken, die Datei ändern und sie anschließend einchecken.</span><span class="sxs-lookup"><span data-stu-id="23f04-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="23f04-106">Später beschließen Sie, die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="23f04-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="23f04-107">Da Sie das Element eingecheckt haben, können Sie das ursprüngliche Auschecken nicht rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="23f04-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="23f04-108">In diesem Fall können Sie die usprünglich ausgecheckte Version als letzte Version des Elements bestimmen.</span><span class="sxs-lookup"><span data-stu-id="23f04-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="23f04-109">Sie können die letzte Version folgendermaßen bestimmen:</span><span class="sxs-lookup"><span data-stu-id="23f04-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="23f04-110">**Anhenung einer Version**.</span><span class="sxs-lookup"><span data-stu-id="23f04-110">**Pinning a version**.</span></span> <span data-ttu-id="23f04-111">Wenn Sie eine Dateiversion festhalten, werden Versionen, die jünger als die festgehaltene Version sind, nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23f04-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="23f04-112">Außerdem können Sie das Festhalten einer Datei aufheben, die Sie zuvor festgehalten haben.</span><span class="sxs-lookup"><span data-stu-id="23f04-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="23f04-113">Dabei wird die zuletzt eingecheckte Version der Datei zur letzten Version.</span><span class="sxs-lookup"><span data-stu-id="23f04-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="23f04-114">Sie können aber keine festgehaltene Datei auschecken.</span><span class="sxs-lookup"><span data-stu-id="23f04-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="23f04-115">**Rollback zu einer bestimmten Version**.</span><span class="sxs-lookup"><span data-stu-id="23f04-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="23f04-116">Wenn Sie ein Rollback zu einer Version ausführen, werden alle aktuelleren Versionen aus der Quellcodeverwaltung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23f04-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="23f04-117">Sie können dann die letzte verbleibende Version auschecken.</span><span class="sxs-lookup"><span data-stu-id="23f04-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="23f04-118">So halten Sie eine Version fest</span><span class="sxs-lookup"><span data-stu-id="23f04-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="23f04-119">Öffnen Sie in die Projekt Mappe [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23f04-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="23f04-120">Wählen Sie im Projektmappen-Explorer die Datei aus, die Sie als letzte Version angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="23f04-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="23f04-121">Zeigen Sie im Menü **Datei** auf **Quell** Code Verwaltung, und klicken Sie auf **ViewHistory**.</span><span class="sxs-lookup"><span data-stu-id="23f04-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="23f04-122">Wählen Sie **History of** im \<file> Dialogfeld Verlauf die Version aus, die Sie als letztes angeben möchten, und klicken Sie auf **Pin**anheften.</span><span class="sxs-lookup"><span data-stu-id="23f04-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="23f04-123">Die von Ihnen ausgewählte Version wird mit einem entsprechenden Symbol als aktuelle Dateiversion gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="23f04-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="23f04-124">Wenn eine andere Version in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] geladen wurde, werden Sie aufgefordert, die Datei neu zu laden.</span><span class="sxs-lookup"><span data-stu-id="23f04-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="23f04-125">So führen Sie ein Rollback zu einer Version aus</span><span class="sxs-lookup"><span data-stu-id="23f04-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="23f04-126">Öffnen Sie in die Projekt Mappe [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23f04-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="23f04-127">Wählen Sie im Projektmappen-Explorer das Element aus, das Sie als letzte Version angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="23f04-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="23f04-128">Zeigen Sie im Menü **Datei** auf **Quell** Code Verwaltung, und klicken Sie auf **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="23f04-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="23f04-129">Klicken Sie im Dialogfeld Versions Verlaufs **Optionen** auf **OK** , um das Dialogfeld **Verlauf der Datei** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23f04-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="23f04-130">Wählen Sie im Feld **Verlauf der Datei** die Version aus, die Sie als neueste Version angeben möchten, und klicken Sie auf **Rollback**.</span><span class="sxs-lookup"><span data-stu-id="23f04-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="23f04-131">Eine Meldung wird angezeigt, in der Sie darüber benachrichtigt werden, dass alle Versionen nach der von Ihnen ausgewählten Version gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="23f04-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="23f04-132">Klicken Sie auf **Ja** , um ein Rollback zur ausgewählten Version auszuführen.</span><span class="sxs-lookup"><span data-stu-id="23f04-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f04-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23f04-133">See Also</span></span>  
 <span data-ttu-id="23f04-134">[Check-Ins verwalten](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="23f04-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="23f04-135">Einchecken von Dateien</span><span class="sxs-lookup"><span data-stu-id="23f04-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
