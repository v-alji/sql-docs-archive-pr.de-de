---
title: Seite "Elemente verschieben" (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fc83b8d2-bc79-4b56-8970-34a1cbbcc176
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 98ff306caf634a5f0478e2eba03c2313b24be274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723581"
---
# <a name="move-items-page-report-manager"></a><span data-ttu-id="61d8d-102">Elemente verschieben (Seite, Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="61d8d-102">Move Items Page (Report Manager)</span></span>
  <span data-ttu-id="61d8d-103">Auf der Seite Elemente verschieben können Sie einen Bericht, Ordner oder ein anderes Element an einen neuen Speicherort auf dem Berichtsserver verschieben.</span><span class="sxs-lookup"><span data-stu-id="61d8d-103">Use the Move Items page to move a report, folder, or other item to a new location on the report server.</span></span> <span data-ttu-id="61d8d-104">Sie können den Pfad des neuen Speicherortes eingeben oder die Strukturansicht verwenden, um zu einem neuen Speicherort im Namespace des Berichtsservers zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="61d8d-104">You can type the path of the new location or use a tree view to browse to a new location in the report server namespace.</span></span> <span data-ttu-id="61d8d-105">Sie können nur die Elemente verschieben, für die Sie über die entsprechende Berechtigung verfügen und die auf dem aktuellen Berichtsserver gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="61d8d-105">You can only move items that you have permission to move and that are stored on the current report server.</span></span>  
  
 <span data-ttu-id="61d8d-106">Wenn Sie ein Element verschieben, auf das durch ein anderes Element verwiesen wird (z. B. eine freigegebene Datenquelle oder ein freigegebenes Modell, auf die oder das viele Berichte verweisen), wird der Pfad zu diesem Element automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="61d8d-106">When you move an item that is referenced by another item (for example, a shared data source or model that is referenced by many reports), the path information for that item is updated automatically.</span></span> <span data-ttu-id="61d8d-107">Durch das Verschieben einer freigegebenen Datenquelle wird die Datenquellenverbindung der Berichte und Modelle, die diese verwenden, nicht unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="61d8d-107">Moving a shared data source does not disrupt a data source connection to the reports and models that use it.</span></span> <span data-ttu-id="61d8d-108">Wenn Sie eine freigegebene Datenquelle oder ein freigegebenes Modell in einen Ordner verschieben, für den die Benutzer keine Berechtigung haben, können sie immer noch jeden Bericht ausführen, der auf diese Quelle oder dieses Modell verweist. Das Element ist jedoch in der Ordnerhierarchie für sie nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="61d8d-108">If you move a shared data source or model to a folder for which users do not have permission, they will still be able to run any report that references the data source or model, however the item will not be visible to them in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="61d8d-109">Geben Sie für **Speicherort**den vollständigen Pfad zum Ordner an, wobei Sie mit dem Namen des Stammordners beginnen.</span><span class="sxs-lookup"><span data-stu-id="61d8d-109">For **Location**, specify the full path to folder, beginning with the root folder name.</span></span> <span data-ttu-id="61d8d-110">Sie können den Pfadnamen eingeben oder die Strukturansicht verwenden, um zu dem gewünschten Ordner zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="61d8d-110">You can type the path name or use the tree view to navigate to the folder you want.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61d8d-111">Nicht alle Elemente können verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="61d8d-111">Not all items are movable.</span></span> <span data-ttu-id="61d8d-112">Reservierte Ordner wie Home, Meine Berichte und Benutzerordner können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="61d8d-112">You cannot move reserved folders such as Home, My Reports, or Users Folders.</span></span> <span data-ttu-id="61d8d-113">Der Berichtsverlauf oder Momentaufnahmen können ebenfalls nicht an andere Speicherorte verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="61d8d-113">You cannot move report history or snapshots to different locations.</span></span> <span data-ttu-id="61d8d-114">Verlauf und Momentaufnahmen werden immer zusammen mit dem Bericht gespeichert, auf dem sie basieren, und der Zugriff auf sie erfolgt ebenfalls über diesen Bericht.</span><span class="sxs-lookup"><span data-stu-id="61d8d-114">History and snapshots are always located with, and accessed through, the report on which they are based.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="61d8d-115">Navigation</span><span class="sxs-lookup"><span data-stu-id="61d8d-115">Navigation</span></span>  
 <span data-ttu-id="61d8d-116">Verwenden Sie folgende Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="61d8d-116">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-details-view"></a><span data-ttu-id="61d8d-117">So öffnen Sie die Seite "Elemente verschieben" auf der Seite "Inhalt" in der Detailansicht</span><span class="sxs-lookup"><span data-stu-id="61d8d-117">To open the Move Items page from the Contents page in Details View</span></span>  
  
1.  <span data-ttu-id="61d8d-118">Öffnen Sie den Berichts-Manager, und navigieren Sie zu dem Ordner mit dem zu verschiebenden Element.</span><span class="sxs-lookup"><span data-stu-id="61d8d-118">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="61d8d-119">Sie können auch Elemente von der Homepage des Berichts-Managers verschieben.</span><span class="sxs-lookup"><span data-stu-id="61d8d-119">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="61d8d-120">Klicken Sie auf der Symbolleiste auf **Detailansicht**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-120">In the toolbar, click **Details View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61d8d-121"> Wenn nur die **Kachelansicht**angezeigt wird, sind Sie bereits in der **Detailansicht**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-121">If you see only **Tiles View**, you are already in **Details View**.</span></span>  
  
3.  <span data-ttu-id="61d8d-122">Aktivieren Sie das Kontrollkästchen neben einem Element, und klicken Sie dann auf der Symbolleiste auf **Verschieben** .</span><span class="sxs-lookup"><span data-stu-id="61d8d-122">Select the box next to an item, and then click **Move** in the toolbar.</span></span> <span data-ttu-id="61d8d-123">Sie können mehr als ein Kontrollkästchen aktivieren, wenn Sie mehrere Elemente an den gleichen neuen Speicherort verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="61d8d-123">You can select more than one box if you want to move multiple items to the same new location.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-contents-page-in-tiles-view"></a><span data-ttu-id="61d8d-124">So öffnen Sie die Seite 'Elemente verschieben' auf der Seite 'Inhalt' in der Kachelansicht</span><span class="sxs-lookup"><span data-stu-id="61d8d-124">To open the Move Items page from the Contents page in Tiles View</span></span>  
  
1.  <span data-ttu-id="61d8d-125">Öffnen Sie den Berichts-Manager, und navigieren Sie zu dem Ordner mit dem zu verschiebenden Element.</span><span class="sxs-lookup"><span data-stu-id="61d8d-125">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="61d8d-126">Sie können auch Elemente von der Homepage des Berichts-Managers verschieben.</span><span class="sxs-lookup"><span data-stu-id="61d8d-126">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="61d8d-127">Klicken Sie auf der Symbolleiste auf **Kachelansicht**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-127">In the toolbar, click **Tiles View**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61d8d-128"> Wenn nur **Detailansicht**angezeigt wird, sind Sie bereits in der Kachelansicht\ \*\*\**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-128">If you see only **Details View**, you are already in **Tiles View**.</span></span>  
  
3.  <span data-ttu-id="61d8d-129">Zeigen Sie auf ein Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="61d8d-129">Hover over an item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="61d8d-130">Klicken Sie im Dropdownmenü auf **Verschieben**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-130">In the drop-down menu, click **Move**.</span></span>  
  
###### <a name="to-open-the-move-items-page-from-the-general-properties-page-of-an-item"></a><span data-ttu-id="61d8d-131">So öffnen Sie die Seite 'Elemente verschieben' von der Seite 'Allgemeine Eigenschaften' eines Elements</span><span class="sxs-lookup"><span data-stu-id="61d8d-131">To open the Move Items page from the General Properties page of an item</span></span>  
  
1.  <span data-ttu-id="61d8d-132">Öffnen Sie den Berichts-Manager, und navigieren Sie zu dem Ordner mit dem zu verschiebenden Element.</span><span class="sxs-lookup"><span data-stu-id="61d8d-132">Open Report Manager, and navigate to the folder that contains an item you want to move.</span></span> <span data-ttu-id="61d8d-133">Sie können auch Elemente von der Homepage des Berichts-Managers verschieben.</span><span class="sxs-lookup"><span data-stu-id="61d8d-133">You can also move items from the Report Manager Home page.</span></span>  
  
2.  <span data-ttu-id="61d8d-134">Zeigen Sie auf ein Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="61d8d-134">Hover over an item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="61d8d-135">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="61d8d-136">Dadurch wird die Seite Allgemeine Eigenschaften für ein Element geöffnet.</span><span class="sxs-lookup"><span data-stu-id="61d8d-136">This opens the General properties page for an item.</span></span>  
  
4.  <span data-ttu-id="61d8d-137">Klicken Sie auf der Elementsymbolleiste auf **Verschieben**.</span><span class="sxs-lookup"><span data-stu-id="61d8d-137">In the item toolbar, click **Move**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d8d-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61d8d-138">See Also</span></span>  
 <span data-ttu-id="61d8d-139">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="61d8d-139">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="61d8d-140">[Allgemeine Eigenschaften (Seite), Ordner &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61d8d-140">[General Properties Page, Folders &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-folders-report-manager.md) </span></span>  
 <span data-ttu-id="61d8d-141">[Allgemeine Eigenschaften (Seite), Berichte &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61d8d-141">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="61d8d-142">[Allgemeine Eigenschaften (Seite), Ressourcen &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61d8d-142">[General Properties Page, Resources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-resources-report-manager.md) </span></span>  
 <span data-ttu-id="61d8d-143">[Allgemeine Eigenschaften (Seite), freigegebene Datenquellen &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="61d8d-143">[General Properties Page, Shared Data Sources &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-shared-data-sources-report-manager.md) </span></span>  
 [<span data-ttu-id="61d8d-144">Berichts-Manager (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="61d8d-144">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
