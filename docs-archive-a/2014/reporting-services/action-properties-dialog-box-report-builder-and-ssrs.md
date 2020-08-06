---
title: Aktions Eigenschaften (Dialog Feld) (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.action.f1
- "10413"
- "10504"
- sql12.rtp.rptdesigner.calculatedseriesproperties.action.f1
- sql12.rtp.rptdesigner.pictureproperties.action.f1
- sql12.rtp.rptdesigner.actionproperties.f1
- sql12.rtp.rptdesigner.charttitleproperties.action.f1
- "10133"
- "10052"
- "10147"
- sql12.rtp.rptdesigner.chartproperties.action.f1
- "10122"
- sql12.rtp.rptdesigner.serieslabelproperties.action.f1
- sql12.rtp.rptdesigner.textboxproperties.action.f1
- "10162"
- "10168"
- sql12.rtp.rptdesigner.textproperties.action.f1
- sql12.rtp.rptdesigner.placeholderproperties.action.f1
- "10250"
- "10129"
- "10244"
- sql12.rtp.rptdesigner.seriesproperties.action.f1
ms.assetid: 2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77b51af0763010676b95fcedb433ab963fc7fcdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619661"
---
# <a name="action-properties-dialog-box-report-builder-and-ssrs"></a><span data-ttu-id="cfcb0-102">Aktionseigenschaften (Dialogfeld) (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="cfcb0-102">Action Properties Dialog Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cfcb0-103">Das Dialogfeld **Aktion** kann verwendet werden, um Linkoptionen für Diagramme, Messgeräte und Kartenelemente zu aktivieren, die Links unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-103">The **Action** dialog box can be used to enable hyperlink options for a chart, gauge, and map elements that support links.</span></span> <span data-ttu-id="cfcb0-104">Definieren Sie eine Aktion, damit ein Benutzer auf den Bereicht klicken und einen Link mit einer URL, einem anderen Bericht auf demselben Berichtsserver oder auf einer SharePoint-Site, die in einen Berichtsserver integriert ist, oder mit einer anderen Stelle in demselben Bericht herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-104">Define an action so that a user can click on the report and link to a URL, to a different report on the same report server or on a SharePoint site that is integrated with a report server, or to a different location in the same report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cfcb0-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cfcb0-105">Options</span></span>  
 <span data-ttu-id="cfcb0-106">**Als Aktion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-106">**Enable as an action**</span></span>  
 <span data-ttu-id="cfcb0-107">Wählen Sie eine Option aus, um anzugeben, welche Aktion ausgeführt werden soll, wenn Benutzer auf das Element klicken.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-107">Select an option to indicate the action to perform when the user clicks the item.</span></span>  
  
 <span data-ttu-id="cfcb0-108">**None**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-108">**None**</span></span>  
 <span data-ttu-id="cfcb0-109">Wählen Sie diese Option aus, um anzugeben, dass für dieses Element keine Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-109">Choose this option to indicate that the item has no action.</span></span>  
  
 <span data-ttu-id="cfcb0-110">**Gehe zu Bericht**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-110">**Go to report**</span></span>  
 <span data-ttu-id="cfcb0-111">Wählen Sie diese Option aus, um einen Link zu einem Drillthroughbericht auf einem Berichtsserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-111">Choose this option to create a link to a drillthrough report that is located on a report server.</span></span> <span data-ttu-id="cfcb0-112">Bei Auswahl von **Gehe zu Bericht**werden folgende zusätzliche Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-112">The following additional options appear when you select **Go to report**.</span></span>  
  
 <span data-ttu-id="cfcb0-113">**Bericht angeben**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-113">**Specify a report**</span></span>  
 <span data-ttu-id="cfcb0-114">Geben Sie den Namen des Berichts ein, den Sie als Drillthroughbericht verwenden möchten, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-114">Type or select the name of the report that you want to use as a drillthrough report.</span></span> <span data-ttu-id="cfcb0-115">Drillthroughberichte müssen sich auf dem gleichen Berichtsserver wie dieser Bericht befinden.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-115">Drillthrough reports must be on the same report server as this report.</span></span>  
  
 <span data-ttu-id="cfcb0-116">Verwenden Sie für einen Bericht, der auf einem für den einheitlichen Modus konfigurierten Berichtsserver veröffentlicht wurde, einen vollständigen oder relativen Pfad ohne die Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-116">For a report published to a report server configured for native mode, use a full or relative path without the file name extension.</span></span> <span data-ttu-id="cfcb0-117">Falls sich der Bericht in demselben Ordner befindet wie der aktuelle Bericht, verwenden Sie nur den Namen des Berichts.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-117">If the report is in the same folder as the current report, use the name of the report only.</span></span> <span data-ttu-id="cfcb0-118">Falls sich der Bericht in einem anderen Ordner auf demselben Berichtsserver befindet, verwenden Sie einen relativen oder vollständigen Pfad.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-118">If the report is in a different folder on the same report server, use a relative path or a full path.</span></span> <span data-ttu-id="cfcb0-119">Ein relativer Pfad beginnt mit dem aktuellen Ordner und enthält dann weitere übergeordnete Ordner in der Ordnerhierarchie, beispielsweise ../Ordner2/Bericht1.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-119">A relative path starts from the current folder and moves up the folder hierarchy, for example, ../Folder2/Report1.</span></span> <span data-ttu-id="cfcb0-120">Ein vollständiger Pfad beginnt mit /, dem Basisordner.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-120">A full path starts from /, the Home folder.</span></span> <span data-ttu-id="cfcb0-121">Beispiel: /Berichte/Bericht1.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-121">For example, /Reports/Report1.</span></span>  
  
 <span data-ttu-id="cfcb0-122">Verwenden Sie für einen Bericht, der auf einem im integrierten SharePoint-Modus konfigurierten Berichtsserver veröffentlicht wurde, eine vollqualifizierte URL einschließlich der Dateinamenerweiterung (.rdl).</span><span class="sxs-lookup"><span data-stu-id="cfcb0-122">For a report published to a report server configured in SharePoint integrated mode, use a fully qualified URL including the file name extension (.rdl).</span></span> <span data-ttu-id="cfcb0-123">Beispielsweise http:// *\<SharePointservername>/\<site>* /Documents/Report1.RDL.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-123">For example, http://*\<SharePointservername>/\<site>*/Documents/Report1.rdl.</span></span> <span data-ttu-id="cfcb0-124">Relative Pfade werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-124">Relative paths are not supported.</span></span>  
  
 <span data-ttu-id="cfcb0-125">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in der [Dokumentation zu Report Builder](https://go.microsoft.com/fwlink/?LinkId=154494) auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-125">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md) in the [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="cfcb0-126">**Diese Parameter zum Ausführen des Berichts verwenden**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-126">**Use these parameters to run the report**</span></span>  
 <span data-ttu-id="cfcb0-127">Fügen Sie eine Liste von Parametern hinzu, die an den Drillthroughbericht übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-127">Add a list of parameters to pass to the drillthrough report.</span></span> <span data-ttu-id="cfcb0-128">Die Parameternamen müssen mit den für den Zielbericht definierten Parametern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-128">The parameter names must match the parameters defined for the target report.</span></span> <span data-ttu-id="cfcb0-129">Verwenden Sie die Schaltflächen **Hinzufügen** und **Löschen** , um Parameter hinzuzufügen oder zu löschen, und sortieren Sie die Liste der Parameter mithilfe des Aufwärts- und Abwärtspfeils.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-129">Use the **Add** and **Delete** buttons to add and remove parameters and use the up and down arrows to order the list of parameters.</span></span>  
  
 <span data-ttu-id="cfcb0-130">**Add**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-130">**Add**</span></span>  
 <span data-ttu-id="cfcb0-131">Fügen Sie einen neuen Parameter hinzu, der an den Drillthroughbericht übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-131">Add a new parameter to pass to the drillthrough report.</span></span>  
  
 <span data-ttu-id="cfcb0-132">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-132">**Delete**</span></span>  
 <span data-ttu-id="cfcb0-133">Löschen Sie einen Parameter für den Drillthroughbericht.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-133">Delete a parameter for the drillthrough report.</span></span>  
  
 <span data-ttu-id="cfcb0-134">**Pfeil nach oben**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-134">**Up arrow**</span></span>  
 <span data-ttu-id="cfcb0-135">Verschiebt den Parameter in der Liste nach oben.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-135">Move the parameter up in the list.</span></span>  
  
 <span data-ttu-id="cfcb0-136">**Pfeil nach unten**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-136">**Down arrow**</span></span>  
 <span data-ttu-id="cfcb0-137">Verschiebt den Parameter in der Liste nach unten.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-137">Move the parameter down in the list.</span></span>  
  
 <span data-ttu-id="cfcb0-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-138">**Name**</span></span>  
 <span data-ttu-id="cfcb0-139">Geben Sie den Namen eines im Drillthroughbericht definierten Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-139">Type text that is the name of a parameter defined in the drillthrough report.</span></span>  
  
 <span data-ttu-id="cfcb0-140">**Wert**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-140">**Value**</span></span>  
 <span data-ttu-id="cfcb0-141">Sie können einen Wert zur Übergabe für den benannten Parameter im Drillthroughbericht eingeben oder auswählen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-141">Type or select a value to pass for the named parameter in the drillthrough report.</span></span> <span data-ttu-id="cfcb0-142">Klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-142">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="cfcb0-143">**Auslassen**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-143">**Omit**</span></span>  
 <span data-ttu-id="cfcb0-144">Wählen Sie diese Option aus, um zu verhindern, dass der Parameter ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-144">Select to prevent the parameter from running.</span></span> <span data-ttu-id="cfcb0-145">Standardmäßig ist dieses Kontrollkästchen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-145">By default, this check box is cleared and not active.</span></span> <span data-ttu-id="cfcb0-146">Zum Aktivieren des Kontrollkästchens klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*) und geben entweder **true** ein oder erstellen einen Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-146">To select the check box, click the **Expression** (*fx*) button and either type **True** or create an expression.</span></span> <span data-ttu-id="cfcb0-147">Das Kontrollkästchen wird aktiviert, wenn Sie im Dialogfeld **Ausdruck** auf **OK** klicken.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-147">The check box is selected when you click **OK** in the **Expression** dialog box.</span></span>  
  
 <span data-ttu-id="cfcb0-148">**Gehe zu Lesezeichen**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-148">**Go to bookmark**</span></span>  
 <span data-ttu-id="cfcb0-149">Wählen Sie diese Option aus, um einen Link zu einem Lesezeichen im aktuellen Bericht zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-149">Choose this option to define a link to a bookmark in the current report.</span></span> <span data-ttu-id="cfcb0-150">Bei Auswahl von **Gehe zu Lesezeichen**wird die folgende zusätzliche Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-150">The following additional option appears when you select **Go to bookmark**.</span></span>  
  
 <span data-ttu-id="cfcb0-151">**Lesezeichen auswählen**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-151">**Select bookmark**</span></span>  
 <span data-ttu-id="cfcb0-152">Sie können die Lesezeichen-ID eingeben oder auswählen, zu der der Bericht springen soll, wenn Benutzer auf den Link klicken.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-152">Type or select the bookmark ID for the report to jump to when the user clicks the link.</span></span> <span data-ttu-id="cfcb0-153">Klicken Sie auf die Ausdrucks Schaltfläche (**FX**), um den Ausdruck zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-153">Click the Expression (**fx**) button to change the expression.</span></span> <span data-ttu-id="cfcb0-154">Bei der Lesezeichen-ID kann es sich entweder um eine statische ID oder einen Ausdruck handeln, der zu einer Lesezeichen-ID ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-154">The bookmark ID can be either a static ID or an expression that evaluates to a bookmark ID.</span></span> <span data-ttu-id="cfcb0-155">Der Ausdruck kann ein Feld mit einer Lesezeichen-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-155">The expression can include a field that contains a bookmark ID.</span></span>  
  
 <span data-ttu-id="cfcb0-156">Sie müssen zuerst die Lesezeicheneigenschaft eines Berichtselements festlegen, um einen Link zu einem Lesezeichen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-156">To link to a bookmark, you must first set the Bookmark property of a report item.</span></span> <span data-ttu-id="cfcb0-157">Wählen Sie ein Berichtselement, und geben Sie im Bereich Eigenschaften einen Wert oder einen Ausdruck für die Lesezeichen-ID ein, um die Lesezeicheneigenschaft festzulegen. Beispiel: SalesChart oder 5TopSales.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-157">To set the Bookmark property, select a report item, and in the Properties pane, type a value or expression for the bookmark ID; for example, SalesChart or 5TopSales.</span></span>  
  
 <span data-ttu-id="cfcb0-158">**Gehe zu URL**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-158">**Go to URL**</span></span>  
 <span data-ttu-id="cfcb0-159">Wählen Sie diese Option aus, um einen Link zu einer Webseite zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-159">Choose this option to define a link to a Web page.</span></span> <span data-ttu-id="cfcb0-160">Sie können die URL einer Webseite oder einen Ausdruck, der zur URL einer Webseite ausgewertet wird, eingeben oder auswählen.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-160">Type or select the URL of a Web page or an expression that evaluates to the URL of a Web page.</span></span> <span data-ttu-id="cfcb0-161">Klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*), um den Ausdruck zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-161">Click the **Expression** (*fx*) button to change the expression.</span></span> <span data-ttu-id="cfcb0-162">Der Ausdruck kann ein Feld mit einer URL enthalten.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-162">This expression can include a field that contains a URL.</span></span> <span data-ttu-id="cfcb0-163">Bei Auswahl von **Gehe zu URL**wird die folgende zusätzliche Option angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-163">The following additional option appears when you select **Go to URL**.</span></span>  
  
 <span data-ttu-id="cfcb0-164">**URL auswählen**</span><span class="sxs-lookup"><span data-stu-id="cfcb0-164">**Select URL**</span></span>  
 <span data-ttu-id="cfcb0-165">Geben Sie die URL des Elements ein.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-165">Type or enter the URL of the item.</span></span> <span data-ttu-id="cfcb0-166">Verwenden Sie für ein Element, das auf einem für den einheitlichen Modus konfigurierten Berichtsserver veröffentlicht wurde, einen vollständigen oder relativen Pfad.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-166">For an item published to a report server configured for native mode, use a full or relative path.</span></span> <span data-ttu-id="cfcb0-167">Beispielsweise http:// *\<servername>* /Images/image1.jpg.</span><span class="sxs-lookup"><span data-stu-id="cfcb0-167">For example, http://*\<servername>*/images/image1.jpg.</span></span> <span data-ttu-id="cfcb0-168">Verwenden Sie für ein Element, das auf einem im integrierten SharePoint-Modus konfigurierten Berichts Server veröffentlicht wurde, eine voll qualifizierte URL (z *\<SharePointservername>/\<site>* . b. http:///Documents/images/image1.jpg).</span><span class="sxs-lookup"><span data-stu-id="cfcb0-168">For an item published to a report server configured in SharePoint integrated mode, use a fully qualified URL (for example, http://*\<SharePointservername>/\<site>*/Documents/images/image1.jpg).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcb0-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfcb0-169">See Also</span></span>  
 <span data-ttu-id="cfcb0-170">[Diagramme &#40;Berichts-Generator und SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb0-170">[Charts &#40;Report Builder and SSRS&#41;](report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cfcb0-171">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb0-171">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="cfcb0-172">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb0-172">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="cfcb0-173">[Fügen Sie einen unter Bericht und Parameter &#40;Berichts-Generator und SSRS hinzu&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cfcb0-173">[Add a Subreport and Parameters &#40;Report Builder and SSRS&#41;](report-design/add-a-subreport-and-parameters-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cfcb0-174">Interaktive Sortierung, Dokumentstrukturen und Links &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cfcb0-174">Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;</span></span>](report-design/interactive-sort-document-maps-and-links-report-builder-and-ssrs.md)  
  
  
