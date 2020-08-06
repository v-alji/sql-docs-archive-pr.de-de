---
title: Hinzufügen, Ändern oder Löschen von Berichtsparametern (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617767"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="40609-102">Hinzufügen, Ändern oder Löschen von Berichtsparametern (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="40609-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="40609-103">Mithilfe von Berichtsparametern können Sie Berichtsdaten auswählen, eine Verbindung zwischen verwandten Berichten herstellen und die Berichtspräsentation anpassen.</span><span class="sxs-lookup"><span data-stu-id="40609-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="40609-104">Sie können einen Standardwert und eine Liste mit verfügbaren Werten bereitstellen, und die Benutzer können dann eine Auswahl treffen.</span><span class="sxs-lookup"><span data-stu-id="40609-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="40609-105">Nachdem ein Bericht veröffentlicht wurde, können Sie die Standardwerte, die verfügbaren Werte und andere Berichtsparametereigenschaften auf dem Berichtsserver ändern.</span><span class="sxs-lookup"><span data-stu-id="40609-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="40609-106">Sie können mehrere Gruppen mit Standardparameterwerten bereitstellen, indem Sie verknüpfte Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="40609-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="40609-107">Weitere Informationen finden Sie unter "Festlegen von Parametereigenschaften für einen publizierten Bericht" in der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dokumentation in der [SQL Server-Onlinedokumentation](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="40609-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="40609-108">So können Sie einen Berichtsparameter hinzufügen oder bearbeiten</span><span class="sxs-lookup"><span data-stu-id="40609-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="40609-109">Klicken Sie im Bereich **Berichtsdaten** mit der rechten Maustaste auf den Knoten **Parameter** , und klicken Sie dann auf **Parameter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="40609-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="40609-110">Das Dialogfeld **Berichtsparametereigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="40609-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="40609-111">Geben Sie unter **Name**einen Namen für den Parameter ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="40609-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="40609-112">Geben Sie unter **Eingabeaufforderung**den Text ein, der neben dem Parametertextfeld angezeigt wird, wenn der Bericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40609-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="40609-113">Wählen Sie unter **Datentyp**den Datentyp für den Parameterwert aus.</span><span class="sxs-lookup"><span data-stu-id="40609-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="40609-114">Falls der Parameter einen leeren Wert enthalten darf, wählen Sie **Leeren Wert zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="40609-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="40609-115">Falls der Parameter einen Nullwert enthalten darf, wählen Sie **NULL-Wert zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="40609-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="40609-116">Falls für einen Parameter mehrere Werte ausgewählt werden dürfen, aktivieren Sie die Option **Mehrere Werte zulassen**.</span><span class="sxs-lookup"><span data-stu-id="40609-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="40609-117">Legen Sie die Sichtbarkeit fest.</span><span class="sxs-lookup"><span data-stu-id="40609-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="40609-118">Wenn der Parameter oben im Bericht auf der Symbolleiste angezeigt werden soll, wählen Sie **Sichtbar**aus.</span><span class="sxs-lookup"><span data-stu-id="40609-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="40609-119">Um den Parameter auszublenden und nicht auf der Symbolleiste anzuzeigen, wählen Sie **Ausgeblendet**aus.</span><span class="sxs-lookup"><span data-stu-id="40609-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="40609-120">Um den Parameter auszublenden und zu verhindern, dass er nach Veröffentlichung des Berichts auf dem Berichtsserver geändert wird, wählen Sie die Option **Intern**aus.</span><span class="sxs-lookup"><span data-stu-id="40609-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="40609-121">Der Berichtsparameter kann dann nur in der Berichtsdefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="40609-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="40609-122">Bei dieser Option müssen Sie einen Standardwert festlegen oder NULL-Werte für den Parameter zulassen.</span><span class="sxs-lookup"><span data-stu-id="40609-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="40609-123">So löschen Sie einen Berichtsparameter</span><span class="sxs-lookup"><span data-stu-id="40609-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="40609-124">Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="40609-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="40609-125">Klicken Sie mit der rechten Maustaste auf den Berichtsparameter, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="40609-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40609-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40609-126">See Also</span></span>  
 <span data-ttu-id="40609-127">[Hinzufügen, ändern oder Löschen von verfügbaren Werten für einen Berichts Parameter &#40;Berichts-Generator und SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="40609-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="40609-128">[Hinzufügen, ändern oder Löschen von Standardwerten für einen Berichts Parameter &#40;Berichts-Generator und SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="40609-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="40609-129">[Ändern der Reihenfolge von Berichts Parametern &#40;Berichts-Generator und SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40609-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40609-130">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="40609-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="40609-131">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="40609-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="40609-132">[Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="40609-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="40609-133">[Tutorial: Hinzufügen eines Parameters zu einem Bericht &#40;Berichts-Generator&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="40609-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="40609-134">[Lernprogramme &#40;Berichts-Generator&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="40609-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="40609-135">[Hinzufügen von datasetfiltern, Datenbereichs Filtern und Gruppen Filtern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="40609-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="40609-136">[Die Parameter Sammlung verweist auf &#40;Berichts-Generator und SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="40609-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="40609-137">Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht</span><span class="sxs-lookup"><span data-stu-id="40609-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
