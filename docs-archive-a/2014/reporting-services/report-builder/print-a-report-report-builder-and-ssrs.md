---
title: Drucken eines Berichts (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b96936c9-c387-41a9-8c19-6eb325769ffd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe029019cdf9739153256db399cfa1426d3ba632
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615830"
---
# <a name="print-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d0aeb-102">Drucken eines Berichts (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d0aeb-102">Print a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d0aeb-103">Nach dem Speichern eines Berichts auf einem Berichtsserver können Sie diesen mit einem Browser, dem Berichts-Manager oder einer beliebigen Anwendung, die Sie zum Anzeigen eines exportierten Berichts verwenden, anzeigen und drucken.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-103">After you save a report to a report server, you can view and print the report from a browser, Report Manager, or any application that you use to view an exported report.</span></span> <span data-ttu-id="d0aeb-104">Vor dem Speichern eines Berichts können Sie ihn aus der Vorschau drucken.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-104">Before saving a report, you can print it when you preview it.</span></span>  
  
 <span data-ttu-id="d0aeb-105">Beim Drucken eines Berichts können Sie das zu verwendende Papierformat festlegen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-105">When you print a report, you can specify the size of the paper to use.</span></span> <span data-ttu-id="d0aeb-106">Durch das Papierformat wird die Anzahl der Seiten in einem Bericht festgelegt und welche Berichtsdaten jeweils auf eine Seite passen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-106">The size of the paper determines the number of pages in a report and which report data fits on each page.</span></span> <span data-ttu-id="d0aeb-107">Das Papierformat beeinflusst nur Berichte, die mit harten Seitenumbrüchen gerendert werden: PDF, Bild und Druck.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-107">Paper size affects only reports that are rendered with hard page-break renders: PDF, Image, and Print.</span></span> <span data-ttu-id="d0aeb-108">Die Festlegung des Papierformats hat keine Auswirkungen auf andere Renderer.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-108">Setting the paper size has no effect on other renderers.</span></span> <span data-ttu-id="d0aeb-109">Weitere Informationen finden Sie unter [Renderingverhalten &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d0aeb-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="d0aeb-110">Auf der Berichts-Viewer-Symbolleiste im Berichts-Manager oder in der Vorschau des Berichts-Generators können Sie einen Bericht in einen Renderer mit harten Seitenumbrüchen exportieren oder auf die Schaltfläche Drucken klicken, um eine Kopie des Berichts zu drucken.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-110">From the report viewer toolbar in Report Manager or in preview in Report Builder, you can export a report to a hard page-break renderer or click the Print button to print a copy of the report.</span></span> <span data-ttu-id="d0aeb-111">Möglicherweise müssen Sie das Papierformat oder andere Seiteneinrichtungseigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-111">You might need to set the paper size or other page setup properties.</span></span> <span data-ttu-id="d0aeb-112">Verwenden Sie das Dialogfeld **Berichtseigenschaften** , um Seiteneinrichtungseigenschaften zu ändern, z. B. das Papierformat.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-112">Use the **Report Properties** dialog box to change page setup properties, including paper size.</span></span>  
  
 <span data-ttu-id="d0aeb-113">Druckseitenränder können an zwei Stellen angegeben können: im Entwurfsmodus und im Ausführungsmodus.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-113">You can specify print page margins in two different locations: in design mode and in run mode.</span></span>  
  
-   <span data-ttu-id="d0aeb-114">**Entwurfsmodus.**</span><span class="sxs-lookup"><span data-stu-id="d0aeb-114">**Design mode.**</span></span> <span data-ttu-id="d0aeb-115">Wenn Sie Seitenränder im Entwurfsmodus festlegen, werden diese Einstellungen beim Speichern des Berichts in der Berichtsdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-115">When you set page margins in design mode, these settings are saved in the report definition when you save the report.</span></span>  
  
-   <span data-ttu-id="d0aeb-116">**Der Lauf Modus.**</span><span class="sxs-lookup"><span data-stu-id="d0aeb-116">**Run mode.**</span></span> <span data-ttu-id="d0aeb-117">Wenn Sie Seitenränder im Ausführungsmodus festlegen, werden diese Informationen nicht in der Berichtsdefinition gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-117">When you set page margins in run mode, this information is not saved in the report definition.</span></span> <span data-ttu-id="d0aeb-118">Wenn Sie den Bericht das nächste Mal ausdrucken, übernehmen Sie die Einstellungen aus der Berichtsdefinition, wenn Sie die Seitenränder nicht erneut angeben.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-118">The next time you print the report, you will get the settings from the report definition, unless you indicate your print margins again.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0aeb-119">Druckränder werden im Entwurfs- oder Ausführungsmodus nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-119">Print margins are not displayed in design or run modes.</span></span> <span data-ttu-id="d0aeb-120">Es gibt keine Beziehung zwischen dem Entwurfsoberflächenbereich und dem Druckbereich des Berichts.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-120">There is no relationship between the design surface area and the print area of your report.</span></span> <span data-ttu-id="d0aeb-121">Klicken Sie auf der Registerkarte **Ausführen** auf dem Menüband auf "Seitenlayout", um Druckränder im Ausführungsmodus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-121">To see print margins, in run mode, click Print Layout on the **Run** tab on the Ribbon.</span></span>  
  
 <span data-ttu-id="d0aeb-122">Weitere Informationen zur Berichtspaginierung finden Sie unter [Paginierung in Reporting Services (Berichts-Generator und SSRS)](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d0aeb-122">For more information about report paging, see [Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-print-a-report-in-report-builder"></a><span data-ttu-id="d0aeb-123">So drucken Sie einen Bericht im Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="d0aeb-123">To print a report in Report Builder</span></span>  
  
1.  <span data-ttu-id="d0aeb-124">Öffnen Sie einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-124">Open a report.</span></span>  
  
2.  <span data-ttu-id="d0aeb-125">Klicken Sie auf der Registerkarte Startseite auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-125">On the Home tab, click **Run**.</span></span>  
  
3.  <span data-ttu-id="d0aeb-126">(Optional) Klicken Sie auf **Seitenlayout** , um eine Druckvorschau des Berichts aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-126">(optional) Click **Print Layout** to see how the report will look when it is printed.</span></span>  
  
4.  <span data-ttu-id="d0aeb-127">(Optional) Klicken Sie auf **Seite einrichten** , um Papier, Ausrichtung und Ränder festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-127">(optional) Click **Page Setup** to set paper, orientation, and margins.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0aeb-128">Die Standardwerte für diese Einstellungen werden aus den Berichtseigenschaften übernommen, die in der Entwurfsansicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-128">The default values for these come from the report properties, which are set in Design view.</span></span> <span data-ttu-id="d0aeb-129">Die Werte, die Sie hier im Dialogfeld **Seite einrichten** festlegen, sind nur für diese Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-129">The values you set here in the **Page Setup** dialog box are for this session only.</span></span> <span data-ttu-id="d0aeb-130">Wenn Sie diesen Bericht schließen und erneut öffnen, werden wieder die Standardwerte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-130">When you close this report and reopen it, it will have the default values again.</span></span>  
  
5.  <span data-ttu-id="d0aeb-131">Klicken Sie auf **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-131">Click **Print**.</span></span>  
  
6.  <span data-ttu-id="d0aeb-132">Im Dialogfeld **Drucken** können Sie einen Drucker auswählen und sonstige Druckoptionen angeben.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-132">In the **Print** dialog box, select a printer and specify other printing options.</span></span>  
  
### <a name="to-print-a-report-from-a-web-browser-application"></a><span data-ttu-id="d0aeb-133">So drucken Sie einen Bericht von einem Webbrowser aus</span><span class="sxs-lookup"><span data-stu-id="d0aeb-133">To print a report from a Web browser application</span></span>  
  
1.  <span data-ttu-id="d0aeb-134">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d0aeb-134">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="d0aeb-135">Navigieren Sie im Berichts-Manager zu dem Bericht, den Sie drucken möchten.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-135">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="d0aeb-136">Öffnen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-136">Open the report.</span></span>  
  
3.  <span data-ttu-id="d0aeb-137">Klicken Sie auf der Symbolleiste oben im Bericht auf **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-137">On the toolbar at the top of the report, click **Print**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0aeb-138">Beim erstmaligen Drucken eines HTML-Berichts werden Sie vom Berichtsserver aufgefordert, ein ActiveX-Steuerelement zu installieren, das für das Drucken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-138">The first time you print an HTML report, the report server prompts you to install an ActiveX control used for printing.</span></span> <span data-ttu-id="d0aeb-139">Das Steuerelement muss installiert und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-139">You must install and configure the control to print.</span></span>  
  
4.  <span data-ttu-id="d0aeb-140">Wählen Sie im Dialogfeld **Drucker** einen Drucker aus, und klicken Sie dann auf **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-140">In the **Print** dialog box, select a printer, and then click **Prin**t.</span></span>  
  
### <a name="to-print-a-report-from-other-applications"></a><span data-ttu-id="d0aeb-141">So drucken Sie einen Bericht von anderen Anwendungen aus</span><span class="sxs-lookup"><span data-stu-id="d0aeb-141">To print a report from other applications</span></span>  
  
1.  <span data-ttu-id="d0aeb-142">Navigieren Sie im Berichts-Manager zu dem Bericht, den Sie drucken möchten.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-142">In Report Manager, navigate to the report that you want to print.</span></span> <span data-ttu-id="d0aeb-143">Öffnen Sie den Bericht.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-143">Open the report.</span></span>  
  
2.  <span data-ttu-id="d0aeb-144">Wählen Sie auf der Symbolleiste oben im Bericht ein Renderingformat aus, und klicken Sie auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-144">On the toolbar at the top of the report, select a rendering format, and then click **Export**.</span></span> <span data-ttu-id="d0aeb-145">Der Bericht wird in einer Viewer-Anwendung geöffnet, die dem Renderingformat entspricht.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-145">The report opens in a viewer application that corresponds to the rendering format.</span></span>  
  
     <span data-ttu-id="d0aeb-146">Wenn Sie z. B. PDF auswählen, wird der Bericht in Adobe Acrobat Reader geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-146">For example, if you select PDF, the report opens in Adobe Acrobat Reader.</span></span>  
  
3.  <span data-ttu-id="d0aeb-147">Klicken Sie in diesem Programm im Menü **Datei** auf **Drucken**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-147">On the **File** menu in that program, click **Print**.</span></span>  
  
### <a name="to-change-paper-size"></a><span data-ttu-id="d0aeb-148">So ändern Sie das Papierformat</span><span class="sxs-lookup"><span data-stu-id="d0aeb-148">To change paper size</span></span>  
  
1.  <span data-ttu-id="d0aeb-149">Klicken Sie mit der rechten Maustaste außerhalb des Berichtshauptteils, und klicken Sie auf **Berichtseigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-149">Right-click outside of the report body and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="d0aeb-150">Wählen Sie in **Seite einrichten**einen Wert aus der Liste **Papierformat** aus.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-150">In **Page Setup**, select a value from the **Paper Size** list.</span></span> <span data-ttu-id="d0aeb-151">Jede Option füllt die Eigenschaft **Breite** und die Eigenschaft **Höhe** aus.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-151">Each option populates the **Width** and **Height** properties.</span></span> <span data-ttu-id="d0aeb-152">Sie können auch ein benutzerdefiniertes Format angeben, indem Sie numerische Werte in den Feldern **Breite** und **Höhe** eingeben.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-152">You can also specify a custom size by typing numeric values in the **Width** and **Height** boxes.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0aeb-153">Die Standardeinheiten der Größenwerte hängen von den Gebietsschemaeinstellungen des Benutzers ab.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-153">Size values have a default unit based on the user's locale settings.</span></span> <span data-ttu-id="d0aeb-154">Geben Sie zum Festlegen einer anderen Einheit einen physischen Einheitenkennzeichner nach dem numerischen Wert ein, z. B. cm, mm, pt oder pc.</span><span class="sxs-lookup"><span data-stu-id="d0aeb-154">To designate a different unit, type a physical unit designator such as cm, mm, pt, or pc after the numeric value.</span></span>  
  
### <a name="to-set-page-margins-in-design-mode"></a><span data-ttu-id="d0aeb-155">So legen Sie Seitenränder im Entwurfsmodus fest</span><span class="sxs-lookup"><span data-stu-id="d0aeb-155">To set page margins in design mode</span></span>  
  
-   <span data-ttu-id="d0aeb-156">Klicken Sie mit der rechten Maustaste auf den blauen Bereich um die Entwurfsoberfläche, klicken Sie auf **Berichtseigenschaften**und danach auf die Seite **Seite einrichten** .</span><span class="sxs-lookup"><span data-stu-id="d0aeb-156">Right-click the blue area around the design surface, click **Report Properties**, and then click the **Page Setup** page.</span></span>  
  
### <a name="to-set-page-margins-in-run-mode"></a><span data-ttu-id="d0aeb-157">So legen Sie Seitenränder im Ausführungsmodus fest</span><span class="sxs-lookup"><span data-stu-id="d0aeb-157">To set page margins in run mode</span></span>  
  
-   <span data-ttu-id="d0aeb-158">Klicken Sie auf **Seite einrichten** auf der Registerkarte **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="d0aeb-158">Click **Page Setup** on the **Run** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0aeb-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0aeb-159">See Also</span></span>  
 <span data-ttu-id="d0aeb-160">[Drucken von Berichten &#40;Berichts-Generator und SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d0aeb-160">[Print Reports &#40;Report Builder and SSRS&#41;](print-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d0aeb-161">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d0aeb-161">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="d0aeb-162">[Berichtseigenschaften (Dialogfeld, Seite einrichten, Berichts-Generator)](../report-properties-dialog-box-page-setup-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="d0aeb-162">[Report Properties Dialog Box, Page Setup &#40;Report Builder&#41;](../report-properties-dialog-box-page-setup-report-builder.md) </span></span>  
 [<span data-ttu-id="d0aeb-163">Berichtsentwurfsansicht &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="d0aeb-163">Report Design View &#40;Report Builder&#41;</span></span>](report-design-view-report-builder.md)  
  
  
