---
title: Hinzufügen, ändern oder Löschen von Standardwerten für einen Berichts Parameter (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10460"
- sql12.rtp.rptdesigner.reportparameters.defaultvalues.f1
- "10072"
ms.assetid: 6a87e069-b3a9-47b6-bcec-afcdd8aff65f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1d50fdbbe42a656ef839785c0968b36c8c829e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617761"
---
# <a name="add-change-or-delete-default-values-for-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="cff2c-102">Hinzufügen, Ändern oder Löschen von Standardwerten für einen Berichtsparameter (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="cff2c-102">Add, Change, or Delete Default Values for a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cff2c-103">Nachdem Sie einen Berichtsparameter erstellt haben, können Sie eine Liste mit Standardwerten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-103">After you create a report parameter, you can provide a list of default values.</span></span> <span data-ttu-id="cff2c-104">Wenn alle Parameter über einen gültigen Standardwert verfügen, wird der Bericht beim ersten Anzeigen bzw. bei der ersten Vorschau automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cff2c-104">If all parameters have a valid default value, the report runs automatically when you first view or preview it.</span></span>  
  
 <span data-ttu-id="cff2c-105">Berichtsparameter können einen Wert oder mehrere Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-105">Report parameters can represent one value or multiple values.</span></span> <span data-ttu-id="cff2c-106">Für einzelne Werte können Sie ein Literal oder einen Ausdruck bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-106">For single values, you can provide a literal or expression.</span></span> <span data-ttu-id="cff2c-107">Für mehrere Werte können Sie eine statische Liste oder eine Liste anhand eines Berichtsdatasets bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-107">For multiple values, you can provide a static list or a list from a report dataset.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="cff2c-108">Nachdem ein Bericht veröffentlicht wurde, können Sie die Standardwerte, die Sie im Bericht im Berichterstellungstool definieren, durch Festlegen von Parametereigenschaftswerten auf dem Berichtsserver überschreiben.</span><span class="sxs-lookup"><span data-stu-id="cff2c-108">After you publish a report, you can override the default values that you define in the report in the report authoring tool, by setting parameter property values on the report server.</span></span> <span data-ttu-id="cff2c-109">Sie können auch mehrere Gruppen von Standardparameterwerten bereitstellen, indem Sie verknüpfte Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-109">You can also provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="cff2c-110">Weitere Informationen finden Sie unter  [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span><span class="sxs-lookup"><span data-stu-id="cff2c-110">For more information, see  [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md)</span></span>  
  
### <a name="to-add-or-change-the-default-values-for-a-report-parameter"></a><span data-ttu-id="cff2c-111">So fügen Sie die Standardwerte für einen Berichtsparameter hinzu bzw. ändern diese</span><span class="sxs-lookup"><span data-stu-id="cff2c-111">To add or change the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="cff2c-112">Erweitern Sie im Berichtsdatenbereich den Knoten **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="cff2c-112">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="cff2c-113">Klicken Sie mit der rechten Maustaste auf den Parameter, und klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-113">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="cff2c-114">Das Dialogfeld **Berichtsparametereigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cff2c-114">The **Report Parameter Properties** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cff2c-115">Zum Anzeigen des Berichtsdatenbereichs klicken Sie im Menü **Ansicht** auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-115">If the Report Data pane is not visible, click **View** and then click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="cff2c-116">Klicken Sie auf **Standardwerte**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-116">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="cff2c-117">Wählen Sie eine Standardoption:</span><span class="sxs-lookup"><span data-stu-id="cff2c-117">Select a default option:</span></span>  
  
    -   <span data-ttu-id="cff2c-118">Klicken Sie auf **Werte angeben**, um manuell einen Wert oder eine Liste mit Werten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-118">To manually provide a value or list of values, click **Specify values**.</span></span> <span data-ttu-id="cff2c-119">Klicken Sie auf **Hinzufügen** , und geben Sie den Wert in das Textfeld **Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="cff2c-119">Click **Add** and then enter the value in the **Value** text box.</span></span> <span data-ttu-id="cff2c-120">Sie können einen Ausdruck für einen Wert schreiben.</span><span class="sxs-lookup"><span data-stu-id="cff2c-120">You can write an expression for a value.</span></span> <span data-ttu-id="cff2c-121">Der Datentyp muss mit dem Datentyp des Parameters übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-121">The data type must match the data type of the parameter.</span></span> <span data-ttu-id="cff2c-122">In einem Ausdruck für einen Parameter können keine Feldnamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cff2c-122">Field names cannot be used in an expression for a parameter.</span></span>  
  
         <span data-ttu-id="cff2c-123">Wiederholen Sie diesen Schritt bei Parametern mit mehreren Werten entsprechend der Anzahl der Werte, die Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="cff2c-123">For multivalue parameters, repeat this step for as many values as you want to provide.</span></span> <span data-ttu-id="cff2c-124">Die Reihenfolge der in dieser Liste angezeigten Elemente bestimmt die Reihenfolge, die Benutzer in der Dropdownliste sehen.</span><span class="sxs-lookup"><span data-stu-id="cff2c-124">The order of items you see in this list determines the order that the user sees them in the drop-down list.</span></span> <span data-ttu-id="cff2c-125">Wenn Sie die Position eines Elements in der Liste ändern möchten, klicken Sie auf das Textfeld **Wert** , um das Element auszuwählen. Bewegen Sie das Element dann mit den Nach-oben- und Nach-unten-Pfeilen in der Liste nach oben bzw. nach unten.</span><span class="sxs-lookup"><span data-stu-id="cff2c-125">To change the order of an item in the list, click the **Value** text box to select the item, and then use the up and down arrow buttons to move the item higher or lower in the list.</span></span>  
  
    -   <span data-ttu-id="cff2c-126">Klicken Sie auf **Werte aus Abfrage abrufen**, um den Namen eines vorhandenen Datasets bereitzustellen, mit dem die Werte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cff2c-126">To provide the name of an existing dataset that retrieves the values, click **Get values from a query**.</span></span> <span data-ttu-id="cff2c-127">Wählen Sie unter **Dataset**den Namen des Datasets aus.</span><span class="sxs-lookup"><span data-stu-id="cff2c-127">In **Dataset**, choose the name of the dataset.</span></span>  
  
         <span data-ttu-id="cff2c-128">Wählen Sie unter **Wertfeld**den Namen des Felds aus, das Parameterwerte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cff2c-128">In **Value field**, choose the name of the field that provides parameter values.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-remove-the-default-values-for-a-report-parameter"></a><span data-ttu-id="cff2c-129">So entfernen Sie die Standardwerte für einen Berichtsparameter</span><span class="sxs-lookup"><span data-stu-id="cff2c-129">To remove the default values for a report parameter</span></span>  
  
1.  <span data-ttu-id="cff2c-130">Erweitern Sie im Berichtsdatenbereich den Knoten **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="cff2c-130">In the Report Data pane, expand the **Parameters** node.</span></span> <span data-ttu-id="cff2c-131">Klicken Sie mit der rechten Maustaste auf den Parameter, und klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-131">Right-click the parameter and click **Edit**.</span></span> <span data-ttu-id="cff2c-132">Das Dialogfeld **Berichtsparametereigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cff2c-132">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="cff2c-133">Klicken Sie auf **Standardwerte**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-133">Click **Default Values**.</span></span>  
  
3.  <span data-ttu-id="cff2c-134">Klicken Sie unter **Wählen Sie eine der folgenden Optionen aus**auf **Kein Standardwert**.</span><span class="sxs-lookup"><span data-stu-id="cff2c-134">In **Select from one of the following options**, click **No default value**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cff2c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cff2c-135">See Also</span></span>  
 <span data-ttu-id="cff2c-136">[Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-136">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="cff2c-137">[Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-137">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cff2c-138">[Tutorial: Add a Parameter to Your Report (Report Builder) (Tutorial: Hinzufügen eines Parameters zu einem Bericht (Berichts-Generator))](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-138">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="cff2c-139">[Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-139">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="cff2c-140">[Parameters Collection References (Report Builder and SSRS) (Verweise auf Parameterauflistungen (Berichts-Generator und SSRS))](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-140">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 <span data-ttu-id="cff2c-141">[Ändern der Reihenfolge von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-141">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cff2c-142">[Hinzufügen, Ändern oder Löschen von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cff2c-142">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cff2c-143">Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cff2c-143">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
