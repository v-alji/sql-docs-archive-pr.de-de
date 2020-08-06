---
title: Erstellen einer Dokumentstruktur (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c200a97b-67f2-499f-8374-3ed1ebe3f33c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a9dad0f8e6ee1d9b9ada44fda0eec5908f27cfcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616440"
---
# <a name="create-a-document-map-report-builder-and-ssrs"></a><span data-ttu-id="8e5e7-102">Erstellen einer Dokumentstruktur (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="8e5e7-102">Create a Document Map (Report Builder and SSRS)</span></span>
  <span data-ttu-id="8e5e7-103">Eine Dokumentstruktur stellt einen Satz von Navigationslinks zu Berichtselementen in einem gerenderten Bericht bereit.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-103">A document map provides a set of navigational links to report items in a rendered report.</span></span> <span data-ttu-id="8e5e7-104">Wenn Sie einen Bericht anzeigen, der eine Dokumentstruktur enthält, wird neben dem Bericht ein Seitenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-104">When you view a report that includes a document map, a separate side pane appears next to the report.</span></span> <span data-ttu-id="8e5e7-105">Durch Klicken auf Links in der Dokumentstruktur kann der Benutzer zu bestimmten Seiten in einem Bericht springen, die ein bestimmten Element anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-105">A user can click links in the document map to jump to the report page that displays that item.</span></span> <span data-ttu-id="8e5e7-106">In diesem Bereich werden Berichtsabschnitte und Gruppen in Form einer Hierarchie aus Links angeordnet.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-106">Report sections and groups are arranged in a hierarchy of links.</span></span> <span data-ttu-id="8e5e7-107">Durch Klicken auf Elemente in der Dokumentstruktur wird der Bericht aktualisiert und der Bereich des Berichts angezeigt, der dem Element in der Dokumentstruktur entspricht.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-107">Clicking items in the document map refreshes the report and displays the area of the report that corresponds to the item in the document map.</span></span>  
  
 <span data-ttu-id="8e5e7-108">Zum Hinzufügen von Links zur Dokumentstruktur legen Sie die `DocumentMapLabel`-Eigenschaft des Berichtselements auf Text fest, den Sie erstellen möchten, oder auf einen Ausdruck, der zu dem Text ausgewertet wird, den Sie in der Dokumentstruktur anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-108">To add links to the document map, you set the `DocumentMapLabel` property of the report item to text that you create or to an expression that evaluates to the text that you want display in the document map.</span></span> <span data-ttu-id="8e5e7-109">Sie können der Dokumentstruktur auch die eindeutigen Werte für eine Tabelle oder eine Matrixgruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-109">You can also add the unique values for a table or matrix group to the document map.</span></span> <span data-ttu-id="8e5e7-110">Beispielsweise ist für eine auf Farbe basierende Gruppe jede einzelne Farbe ein Link zur Berichtsseite, die die Gruppeninstanz der jeweiligen Farbe anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-110">For example, for a group based on color, each unique color is a link to the report page that displays the group instance for that color.</span></span>  
  
 <span data-ttu-id="8e5e7-111">Sie können auch eine URL für einen Bericht erstellen, die die Anzeige der Dokumentstruktur überschreibt, sodass Sie den Bericht ohne Anzeigen der Dokumentstruktur ausführen können. Durch Klicken auf die Schaltfläche **Dokumentstruktur ein-/ausblenden** auf der Symbolleiste des Berichts-Viewers können Sie die Anzeige ein- bzw. ausblenden.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-111">You can also create a URL to a report that overrides the display of the document map, so that you can run the report without displaying the document map, and then click the **Show/Hide Document Map** button on the report viewer toolbar to toggle the display.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="document-maps-and-rendering-extensions"></a><a name="DocMapRenderExtensions"></a> <span data-ttu-id="8e5e7-112">Dokumentstrukturen und Renderingerweiterungen</span><span class="sxs-lookup"><span data-stu-id="8e5e7-112">Document Maps and Rendering Extensions</span></span>  
 <span data-ttu-id="8e5e7-113">Die Dokumentstruktur ist für die Verwendung in der HTML-Renderingerweiterung vorgesehen, z.B. in der Vorschau und im Berichts-Viewer.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-113">The document map is intended for use in the HTML rendering extension-for example, in Preview and the Report Viewer.</span></span> <span data-ttu-id="8e5e7-114">Andere Renderingerweiterungen verwenden andere Verfahren zum Darstellen einer Dokumentstruktur:</span><span class="sxs-lookup"><span data-stu-id="8e5e7-114">Other rendering extensions have different ways of articulating a document map:</span></span>  
  
-   <span data-ttu-id="8e5e7-115">PDF rendert eine Dokumentstruktur in Form des Lesezeichen-Bereichs.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-115">PDF renders a document map as the Bookmarks pane.</span></span>  
  
-   <span data-ttu-id="8e5e7-116">Excel rendert eine Dokumentstruktur in Form eines benannten Arbeitsblatts, das eine Hierarchie aus Links einschließt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-116">Excel renders a document map as a named worksheet that includes a hierarchy of links.</span></span> <span data-ttu-id="8e5e7-117">Berichtsbereiche werden in verschiedenen Arbeitsblättern gerendert, die zusammen mit der Dokumentstruktur in dieselbe Arbeitsmappe eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-117">Report sections are rendered in separate worksheets that are included with the document map in the same workbook.</span></span>  
  
-   <span data-ttu-id="8e5e7-118">Word schließt eine Dokumentstruktur als Inhaltsverzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-118">Word includes a document map as the table of contents.</span></span>  
  
-   <span data-ttu-id="8e5e7-119">Atom, TIFF, XML und CSV berücksichtigen Dokumentstrukturen nicht.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-119">Atom, TIFF, XML, and CSV ignore document maps.</span></span>  
  
 <span data-ttu-id="8e5e7-120">Weitere Informationen finden Sie unter [Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen (Berichts-Generator und SSRS)](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="8e5e7-120">For more information, see [Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](../report-builder/interactive-functionality-different-report-rendering-extensions.md).</span></span>  
  
##  <a name="AddRptItemToMap"></a>   
#### <a name="to-add-a-report-item-to-a-document-map"></a><span data-ttu-id="8e5e7-121">So fügen Sie einer Dokumentstruktur ein Berichtselement hinzu</span><span class="sxs-lookup"><span data-stu-id="8e5e7-121">To add a report item to a document map</span></span>  
  
1.  <span data-ttu-id="8e5e7-122">Wählen Sie das Berichtselement, wie Tabelle, Matrix oder Messgerät, das Sie der Dokumentstruktur hinzufügen möchten, in der Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-122">In Design view, select the report item such as a table, matrix, or gauge that you want to add to the document map.</span></span> <span data-ttu-id="8e5e7-123">Die Berichtselementeigenschaften werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-123">The report item properties appear in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e5e7-124">Klicken Sie auf eine Zelle, um die Zeilen- und Spaltenziehpunkte anzuzeigen, und klicken Sie dann auf den Eckziehpunt, wenn Sie einen Tablix-Datenbereich wählen möchten.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-124">To select a tablix data region, click in any cell to display the row and column handles, and then click the corner handle.</span></span>  
  
2.  <span data-ttu-id="8e5e7-125">Geben Sie im Eigenschaften Bereich den Text ein, der in der Dokumentstruktur in der-Eigenschaft angezeigt `DocumentMapLabel` werden soll, oder geben Sie einen Ausdruck ein, der zu einer Bezeichnung ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-125">In the Properties pane, type the text that you want to appear in the document map in the `DocumentMapLabel` property, or enter an expression that evaluates to a label.</span></span> <span data-ttu-id="8e5e7-126">Geben Sie beispielsweise **Umsatzdiagramm**ein.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-126">For example, type **Sales Chart**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8e5e7-127">Wenn der Eigenschaftenbereich nicht angezeigt wird, klicken Sie in der Registerkarte **Ansicht** in der Gruppe **Ein-/Ausblenden** auf die Option **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-127">If you do not see the Properties pane, on the **View** tab, in the **Show/Hide** group, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="8e5e7-128">Wiederholen Sie Schritt 1und 2 für jedes Berichtselement, das in der Dokumentstruktur angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-128">Repeat steps 1 and 2 for every report item that you want to appear in the document map.</span></span>  
  
4.  <span data-ttu-id="8e5e7-129">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-129">Click **Run**.</span></span> <span data-ttu-id="8e5e7-130">Der Bericht wird ausgeführt, und die Dokumentstruktur zeigt die Bezeichnungen an, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-130">The report runs and the document map displays the labels you created.</span></span> <span data-ttu-id="8e5e7-131">Klicken Sie auf einen beliebigen Link, um zur Berichtsseite zu wechseln, die dieses Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-131">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="AddUniqueValuesToMap"></a>   
#### <a name="to-add-unique-group-values-to-a-document-map"></a><span data-ttu-id="8e5e7-132">So fügen Sie einer Dokumentstruktur eindeutige Gruppenwerte hinzu</span><span class="sxs-lookup"><span data-stu-id="8e5e7-132">To add unique group values to a document map</span></span>  
  
1.  <span data-ttu-id="8e5e7-133">Wählen Sie in der Entwurfsansicht die Tabelle, Matrix oder Liste aus, die die Gruppe enthält, die in der Dokumentstruktur angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-133">In Design view, select the table, matrix, or list that contains the group that you want to display in the document map.</span></span> <span data-ttu-id="8e5e7-134">Im Gruppierungsbereich werden die Zeilen- und Spaltengruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-134">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="8e5e7-135">Klicken Sie im Bereich Zeilengruppen mit der rechten Maustaste auf die Gruppe, und klicken Sie anschließend auf **Gruppe bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-135">In the Row Groups pane, right-click the group, and then click **Edit Group**.</span></span> <span data-ttu-id="8e5e7-136">Die Seite **Allgemein** des Dialogfelds **Tablix-Gruppeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-136">The **General** page of the **Tablix Group Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="8e5e7-137">Klicken Sie auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-137">Click **Advanced**.</span></span>  
  
4.  <span data-ttu-id="8e5e7-138">Geben Sie im Listenfeld **Dokumentstruktur** einen Ausdruck ein, oder wählen Sie einen Ausdruck aus, der dem Gruppenausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-138">In the **Document map** list box, type or select an expression that matches the group expression.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8e5e7-139">Wiederholen Sie die Schritte 1-4 für jede Gruppe, die in der Dokumentstruktur angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-139">Repeat steps 1-4 for every group that you want to appear in the document map.</span></span>  
  
7.  <span data-ttu-id="8e5e7-140">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-140">Click **Run**.</span></span> <span data-ttu-id="8e5e7-141">Der Bericht wird ausgeführt, und die Dokumentstruktur zeigt die Gruppenwerte an.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-141">The report runs and the document map displays the group values.</span></span> <span data-ttu-id="8e5e7-142">Klicken Sie auf einen beliebigen Link, um zur Berichtsseite zu wechseln, die dieses Element enthält.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-142">Click any link to jump to the report page with that item.</span></span>  
  
 
  
##  <a name="HideMapWhenViewRpt"></a>   
#### <a name="to-hide-the-document-map-when-you-view-a-report"></a><span data-ttu-id="8e5e7-143">So blenden Sie die Dokumentstruktur aus, wenn Sie einen Bericht anzeigen</span><span class="sxs-lookup"><span data-stu-id="8e5e7-143">To hide the document map when you view a report</span></span>  
  
1.  <span data-ttu-id="8e5e7-144">Wechseln Sie im Berichts-Manager zu dem Bericht, der die Dokumentstruktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-144">In Report Manager, browse to the report that has the document map.</span></span>  
  
     <span data-ttu-id="8e5e7-145">Für die [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] -Beispielberichte gibt beispielsweise die folgende URL den Bericht mit dem Namen des Produktkatalogs an.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-145">For example, for the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample reports, the following URL specifies the report named Product Catalog.</span></span>  
  
    ```  
    http://localhost/Reports/Pages/Report.aspx?ItemPath=%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    ```  
  
2.  <span data-ttu-id="8e5e7-146">Kopieren Sie den Berichtspfad auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-146">Copy the report path on the server.</span></span> <span data-ttu-id="8e5e7-147">In dem Beispiel lautet der Berichtspfad `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-147">In the example, the report path is `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`.</span></span>  
  
3.  <span data-ttu-id="8e5e7-148">Erstellen Sie eine neue URL mit den folgenden drei Komponenten:</span><span class="sxs-lookup"><span data-stu-id="8e5e7-148">Create a new URL with the following three components:</span></span>  
  
    -   <span data-ttu-id="8e5e7-149">Dem Berichts-Viewer auf dem Berichtsserver: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span><span class="sxs-lookup"><span data-stu-id="8e5e7-149">The report viewer on the report server: `http://localhost/ReportServer/Pages/ReportViewer.aspx?`</span></span>  
  
    -   <span data-ttu-id="8e5e7-150">Dem Namen des Berichts, den Sie in Schritt 1 kopiert haben, z. B: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span><span class="sxs-lookup"><span data-stu-id="8e5e7-150">The name of the report you copied in step 1, for example: `%2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog`</span></span>  
  
    -   <span data-ttu-id="8e5e7-151">Den Geräteinformationsparametern, die das Ausblenden der Dokumentstruktur angeben: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span><span class="sxs-lookup"><span data-stu-id="8e5e7-151">The device information parameters that specify hiding the document map: `&rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False`</span></span>  
  
     <span data-ttu-id="8e5e7-152">Die folgende URL besteht aus diesen drei Komponenten, die in der Reihenfolge angefügt werden, in der sie aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-152">The following URL consists of these three components appended in the order they are listed.</span></span>  
  
    ```  
    http://localhost/ReportServer/Pages/ReportViewer.aspx?  
    %2fAdventureWorks2012+Sample+Reports%2fProduct+Catalog  
    &rs%3aCommand=Render&rc%3aFormat=HTML4.0&rc%3aDocMap=False  
    ```  
  
     <span data-ttu-id="8e5e7-153">Um diese URL zu verwenden, kopieren Sie sie, und entfernen Sie alle Zeilenumbrüche.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-153">To use this URL, copy it and remove all line breaks.</span></span>  
  
4.  <span data-ttu-id="8e5e7-154">Fügen Sie die URL in den Berichts-Manager ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-154">Paste the URL in Report Manager, and then press ENTER.</span></span> <span data-ttu-id="8e5e7-155">Der Bericht wird ausgeführt, und die Dokumentstruktur ist ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-155">The report runs, and the document map is hidden.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e5e7-156">Weitere Informationen zum Herunterladen von Beispielberichten finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Beispielberichte für Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="8e5e7-156">For more information about downloading sample reports, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
>   
>  <span data-ttu-id="8e5e7-157">Weitere Informationen finden Sie unter "URL-Zugriff" in der [Reporting Services-Dokumentation](https://go.microsoft.com/fwlink/?linkid=121312) in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e5e7-157">For more information, see "URL Access" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="8e5e7-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e5e7-158">See Also</span></span>  
 [<span data-ttu-id="8e5e7-159">Finding and Viewing Reports in Report Manager (Report Builder and SSRS) (Suchen und Anzeigen von Berichten in Berichts-Manager (Berichts-Generator und SSRS))</span><span class="sxs-lookup"><span data-stu-id="8e5e7-159">Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md)  
  
  
