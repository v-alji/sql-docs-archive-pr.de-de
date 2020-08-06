---
title: Hinzufügen einer Drillthroughaktion für einen Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615805"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="2175d-102">Hinzufügen einer Drillthroughaktion für einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="2175d-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2175d-103">Der Bericht, der geöffnet wird, wenn Sie auf den Link im Hauptbericht klicken, wird als *Drillthroughbericht*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2175d-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="2175d-104">Der Drillthrough-Link ermöglicht einen Drillthrough-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="2175d-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="2175d-105">Drillthroughberichte müssen auf demselben Berichtsserver wie der Hauptbericht veröffentlicht werden, können aber in anderen Ordnern abgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2175d-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="2175d-106">Sie können jedem Element einen Drillthroughlink hinzufügen, das über eine Eigenschaft **Aktion** verfügt, z. B. ein Textfeld, ein Bild oder Datenpunkte in einem Diagramm.</span><span class="sxs-lookup"><span data-stu-id="2175d-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="2175d-107">Sie müssen zuerst den Drillthroughbericht erstellen, mit dem der Hauptbericht verknüpft wird, um einem Bericht einen Drillthroughlink hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2175d-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="2175d-108">Ein Drillthroughbericht enthält im Allgemeinen Details zu einem im ursprünglichen Zusammenfassungsbericht enthaltenen Element und enthält oft Parameter, mit denen der Drillthroughbericht basierend auf Parametern, die vom Hauptbericht übergeben werden, gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="2175d-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="2175d-109">Weitere Informationen zum Erstellen des Drillthroughberichts finden Sie unter [Drillthroughberichte (Berichts-Generator und SSRS)](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2175d-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="2175d-110">So fügen Sie eine Drillthroughaktion hinzu</span><span class="sxs-lookup"><span data-stu-id="2175d-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="2175d-111">Klicken Sie in der Entwurfsansicht mit der rechten Maustaste auf das Textfeld, Bild oder Diagramm, dem Sie einen Link hinzufügen möchten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2175d-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="2175d-112">Klicken Sie im Dialogfeld **Eigenschaften** des Elements auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="2175d-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="2175d-113">Wählen Sie **Gehe zu Bericht**.</span><span class="sxs-lookup"><span data-stu-id="2175d-113">Select **Go to report**.</span></span> <span data-ttu-id="2175d-114">Im Dialogfeld für diese Option werden zusätzliche Abschnitte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2175d-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="2175d-115">Klicken Sie unter **Bericht angeben**auf **Durchsuchen** , um nach dem Namen des gewünschten Berichts zu suchen, oder geben Sie den Namen ein.</span><span class="sxs-lookup"><span data-stu-id="2175d-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="2175d-116">Alternativ können Sie auf die Ausdrucksschaltfläche (**fx**) klicken, um einen Ausdruck für den Berichtsnamen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2175d-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="2175d-117">Das Format des Pfads zum Drillthroughbericht unterscheidet sich beim einheitlichen und integrierten SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="2175d-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="2175d-118">Wenn Sie den Bericht über "Durchsuchen" auswählen, wird der Pfad im richtigen Format angegeben.</span><span class="sxs-lookup"><span data-stu-id="2175d-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="2175d-119">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2175d-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="2175d-120">Wenn Sie Parameter für den Drillthroughbericht angeben müssen, führen Sie den nächsten Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="2175d-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="2175d-121">Klicken Sie in **Diese Parameter zum Ausführen des Berichts verwenden**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2175d-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="2175d-122">Dem Parameterraster wird eine neue Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2175d-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="2175d-123">Klicken Sie im Textfeld **Name** auf die Dropdownliste, oder geben Sie den Namen des Berichtsparameters im Drillthroughbericht ein.</span><span class="sxs-lookup"><span data-stu-id="2175d-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2175d-124">Die Namen in der Parameterliste müssen mit den erwarteten Parametern im Zielbericht genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2175d-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="2175d-125">Beispiel: Die Schreibweise von Parameternamen muss übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2175d-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="2175d-126">Falls die Namen nicht übereinstimmen oder ein erwarteter Parameter nicht aufgeführt ist, ergibt der Drillthroughbericht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="2175d-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="2175d-127">Geben Sie den Wert, der an den Parameter im Drillthroughbericht übergeben werden soll, in das Feld **Wert**ein bzw. wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="2175d-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2175d-128">Werte können einen Ausdruck enthalten, der zu einem an den Berichtsparameter zu übergebenden Wert ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2175d-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="2175d-129">Die Ausdrücke in der Werteliste beinhalten die Feldliste für den aktuellen Bericht.</span><span class="sxs-lookup"><span data-stu-id="2175d-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="2175d-130">Informationen zum Ausblenden von Parametern in Berichten finden Sie unter [Hinzufügen, Ändern oder Löschen von Berichtsparametern (Berichts-Generator und SSRS)](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2175d-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="2175d-131">(Optional) Bei Textfeldern ist es hilfreich, die Farbe und den Effekt des Texts zu ändern, um zu verdeutlichen, dass es sich um einen Link handelt. Verwenden Sie dazu die Registerkarte **Home** auf dem Menüband.</span><span class="sxs-lookup"><span data-stu-id="2175d-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="2175d-132">Führen Sie den Bericht aus, und klicken Sie auf das Berichtselement, für das Sie den Link festgelegt haben, um den Link zu testen.</span><span class="sxs-lookup"><span data-stu-id="2175d-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2175d-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2175d-133">See Also</span></span>  
 <span data-ttu-id="2175d-134">[Aktionseigenschaften (Dialogfeld) &#40;Berichts-Generator und SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2175d-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2175d-135">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2175d-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2175d-136">Anzeigen von QuickInfos für eine Reihe &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2175d-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
