---
title: Verschieben oder Löschen eines Elements (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- moving items
- items [Reporting Services], moving
ms.assetid: 980a66c7-a18b-4af7-8954-45726fa517d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a61ad56ea9e20e7fdf38d5acf05529b685ee896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695285"
---
# <a name="move-or-delete-an-item-report-manager"></a><span data-ttu-id="d723f-102">Verschieben oder Löschen eines Elements (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="d723f-102">Move or Delete an Item (Report Manager)</span></span>
  <span data-ttu-id="d723f-103">Berichte und berichtsbezogene Elemente, die Sie auf einem Berichtsserver veröffentlichen, werden in Ordnern gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d723f-103">Reports and report-related items that you publish to a report server are stored in folders.</span></span> <span data-ttu-id="d723f-104">Sie können Elemente in einen anderen Ordner verschieben. Verweise auf diese Elemente werden automatisch vom Berichtsserver verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d723f-104">You can move items to a different folder and references to those items are maintained automatically by the report server.</span></span> <span data-ttu-id="d723f-105">Bevor Sie ein Element löschen, ist zu überprüfen, ob Elemente davon abhängen.</span><span class="sxs-lookup"><span data-stu-id="d723f-105">Before you delete an item, consider whether other items depend on it.</span></span>  
  
## <a name="move-an-item"></a><span data-ttu-id="d723f-106">Verschieben eines Elements</span><span class="sxs-lookup"><span data-stu-id="d723f-106">Move an Item</span></span>  
 <span data-ttu-id="d723f-107">Sie können Berichtsserverelemente an andere Speicherorte in der Ordnerhierarchie des Berichtsservers verschieben.</span><span class="sxs-lookup"><span data-stu-id="d723f-107">You can move report server items to different folder locations in the report server folder hierarchy.</span></span> <span data-ttu-id="d723f-108">Beim Verschieben eines Elements werden auch alle zugehörigen Eigenschaften (einschließlich Sicherheitseinstellungen) an den neuen Speicherort verschoben.</span><span class="sxs-lookup"><span data-stu-id="d723f-108">When you move an item, all properties (including security settings) move with the item to the new location.</span></span> <span data-ttu-id="d723f-109">Wenn Sie einen Ordner verschieben, werden gleichzeitig alle in diesem Ordner enthaltenen Elemente verschoben.</span><span class="sxs-lookup"><span data-stu-id="d723f-109">When you move a folder, all the items in the folder move with it.</span></span>  
  
 <span data-ttu-id="d723f-110">Im Berichts-Manager werden die verschiebbaren Elemente in der Ordnerhierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d723f-110">In Report Manager, the items that you can move are indicated in the folder hierarchy.</span></span> <span data-ttu-id="d723f-111">In der folgenden Tabelle sind die Symbole für die verschiedenen verschiebbaren Elemente dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d723f-111">The following table shows the icon for each movable item.</span></span>  
  
|<span data-ttu-id="d723f-112">Symbol</span><span class="sxs-lookup"><span data-stu-id="d723f-112">Icon</span></span>|<span data-ttu-id="d723f-113">Verschiebbares Element</span><span class="sxs-lookup"><span data-stu-id="d723f-113">Moveable item</span></span>|  
|----------|-------------------|  
|<span data-ttu-id="d723f-114">![Report icon](../media/hlp-16doc.gif "Berichtssymbol")</span><span class="sxs-lookup"><span data-stu-id="d723f-114">![Report icon](../media/hlp-16doc.gif "Report icon")</span></span>|<span data-ttu-id="d723f-115">Bericht</span><span class="sxs-lookup"><span data-stu-id="d723f-115">Report</span></span>|  
|<span data-ttu-id="d723f-116">![Symbol für einen verknüpften Bericht](../media/hlp-16linked.gif "Symbol für einen verknüpften Bericht")</span><span class="sxs-lookup"><span data-stu-id="d723f-116">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>|<span data-ttu-id="d723f-117">Verknüpfter Bericht</span><span class="sxs-lookup"><span data-stu-id="d723f-117">Linked report</span></span>|  
|<span data-ttu-id="d723f-118">![Ordnersymbol](../media/hlp-16folder.gif "Ordnersymbol")</span><span class="sxs-lookup"><span data-stu-id="d723f-118">![Folder icon](../media/hlp-16folder.gif "Folder icon")</span></span>|<span data-ttu-id="d723f-119">Ordner</span><span class="sxs-lookup"><span data-stu-id="d723f-119">Folder</span></span>|  
|<span data-ttu-id="d723f-120">![allgemeines Ressourcensymbol](../media/hlp-16file.gif "allgemeines Ressourcensymbol")</span><span class="sxs-lookup"><span data-stu-id="d723f-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon")</span></span>|<span data-ttu-id="d723f-121">Allgemeine Ressource</span><span class="sxs-lookup"><span data-stu-id="d723f-121">Generic resource</span></span>|  
|<span data-ttu-id="d723f-122">![Shared data source icon](../media/hlp-16datasource.png "Symbol für freigegebene Datenquelle")</span><span class="sxs-lookup"><span data-stu-id="d723f-122">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>|<span data-ttu-id="d723f-123">Freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d723f-123">Shared data source</span></span>|  
||<span data-ttu-id="d723f-124">Freigegebenes Dataset</span><span class="sxs-lookup"><span data-stu-id="d723f-124">Shared dataset</span></span>|  
  
 <span data-ttu-id="d723f-125">Nicht alle Elemente, mit denen Sie arbeiten, können verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d723f-125">Not all items that you work with can be moved.</span></span> <span data-ttu-id="d723f-126">Elemente, die einem Bericht zugeordnet sind, z. B. Abonnements oder ein Berichtsverlauf, können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d723f-126">You cannot move items that are associated with a report, such as subscriptions or report history.</span></span> <span data-ttu-id="d723f-127">Diese Elemente werden mit den zugehörigen Berichten verschoben.</span><span class="sxs-lookup"><span data-stu-id="d723f-127">Those items move with their associated reports.</span></span> <span data-ttu-id="d723f-128">Auch Elemente wie freigegebene Zeitpläne, die außerhalb der Ordnerhierarchie vorhanden sind, können nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d723f-128">Similarly, you cannot move items, such as shared schedules, that exist outside of the folder hierarchy.</span></span> <span data-ttu-id="d723f-129">Sie können ohne die entsprechende Berechtigung keine Elemente verschieben.</span><span class="sxs-lookup"><span data-stu-id="d723f-129">You cannot move items if you lack permission to do so.</span></span> <span data-ttu-id="d723f-130">Die Berechtigung zum Verschieben eines Elements wird erteilt, wenn folgende Tasks in Ihrer Rollenzuweisung für das entsprechende Element ausgewählt sind: "Berichte verwalten", "Modelle verwalten", "Ordner verwalten" und "Datenquellen verwalten".</span><span class="sxs-lookup"><span data-stu-id="d723f-130">Permission to move an item is conveyed when the following tasks are selected in your role assignment for the item in question: "Manage reports," "Manage models", "Manage folders," and "Manage data sources."</span></span>  
  
#### <a name="to-move-an-item-from-within-the-contents-page"></a><span data-ttu-id="d723f-131">So verschieben Sie ein Element auf der Inhaltsseite</span><span class="sxs-lookup"><span data-stu-id="d723f-131">To move an item from within the Contents page</span></span>  
  
1.  <span data-ttu-id="d723f-132">Start [Berichts-Manager &#40;SSRS im einheitlichen Modus&#41;].. /Report-Manager-SSRS-Native-Mode.MD).</span><span class="sxs-lookup"><span data-stu-id="d723f-132">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="d723f-133">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und suchen Sie das zu verschiebende Element.</span><span class="sxs-lookup"><span data-stu-id="d723f-133">In Report Manager, navigate to the **Contents** page, and locate the item that you want to move.</span></span>  
  
3.  <span data-ttu-id="d723f-134">Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="d723f-134">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="d723f-135">Klicken Sie im Dropdownmenü auf **Verschieben**.</span><span class="sxs-lookup"><span data-stu-id="d723f-135">In the drop-down menu, click **Move**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="d723f-136">Geben Sie für **Speicherort**den Ordner an, in den Sie das Element verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="d723f-136">For **Location**, specify the folder you want to move the item to.</span></span> <span data-ttu-id="d723f-137">Sie können den vollqualifizierten Ordnernamen eingeben oder die Strukturansicht verwenden, um zum gewünschten Ordner zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="d723f-137">You can type the fully qualified folder name or use the tree control to navigate to the folder.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="d723f-138">Alternativ können Sie zum zu verschiebenden Objekt navigieren, auf **Eigenschaften**klicken, und anschließend oben auf der Seite auf **Verschieben** klicken.</span><span class="sxs-lookup"><span data-stu-id="d723f-138">Alternatively, you can navigate to the object you want to move, click **Properties**, and then click **Move** at the top of the page.</span></span>  
  
## <a name="delete-an-item"></a><span data-ttu-id="d723f-139">Löschen eines Elements</span><span class="sxs-lookup"><span data-stu-id="d723f-139">Delete an item</span></span>  
 <span data-ttu-id="d723f-140">Bevor Sie ein Element löschen, ist zu prüfen, ob es von anderen Elementen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d723f-140">Before you delete an item, determine if it is used by other items.</span></span> <span data-ttu-id="d723f-141">Wenn Sie beispielsweise eine freigegebene Datenquelle löschen, werden Berichte und Modelle, die diese Datenquelle verwenden, nicht mehr ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d723f-141">For example, if you delete a shared data source, reports and models that use that data source will no longer run.</span></span> <span data-ttu-id="d723f-142">Beim Löschen eines Berichts werden auch Abonnements und der Berichtsverlauf, die mit diesem Bericht verknüpft sind, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d723f-142">If you delete a report, subscriptions and report history associated with that report are also deleted.</span></span> <span data-ttu-id="d723f-143">Um abhängige Elemente für ein Element zu suchen, finden Sie weitere Informationen unter [Seite "abhängige Elemente" &#40;Berichts-Manager&#41;]. /Dependent-Items-Page-Report-Manager.MD).</span><span class="sxs-lookup"><span data-stu-id="d723f-143">To find dependent items for an item, see [Dependent Items Page &#40;Report Manager&#41;]../dependent-items-page-report-manager.md).</span></span>  
  
#### <a name="to-delete-a-report-or-item"></a><span data-ttu-id="d723f-144">So löschen Sie einen Bericht oder ein Element</span><span class="sxs-lookup"><span data-stu-id="d723f-144">To delete a report or item</span></span>  
  
1.  <span data-ttu-id="d723f-145">Start [Berichts-Manager &#40;SSRS im einheitlichen Modus&#41;].. /Report-Manager-SSRS-Native-Mode.MD).</span><span class="sxs-lookup"><span data-stu-id="d723f-145">Start [Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="d723f-146">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und suchen Sie das zu löschende Element.</span><span class="sxs-lookup"><span data-stu-id="d723f-146">In Report Manager, navigate to the **Contents** page, and locate the item that you want to delete.</span></span>  
  
3.  <span data-ttu-id="d723f-147">Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="d723f-147">Hover over the item, and click the drop-down arrow.</span></span>  
  
4.  <span data-ttu-id="d723f-148">Klicken Sie im Dropdownmenü auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d723f-148">In the drop-down menu, click **Delete**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d723f-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d723f-149">See Also</span></span>  
 <span data-ttu-id="d723f-150">[Inhaltsseite &#40;Berichts-Manager&#41;].. /Contents-Page-Report-Manager.MD)</span><span class="sxs-lookup"><span data-stu-id="d723f-150">[Contents Page &#40;Report Manager&#41;]../contents-page-report-manager.md)</span></span>   
 [<span data-ttu-id="d723f-151">Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS )</span><span class="sxs-lookup"><span data-stu-id="d723f-151">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
