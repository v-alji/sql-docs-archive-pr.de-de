---
title: 'Tutorial: Erstellen von Drillthrough- und Hauptberichten (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722434"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="60339-102">Lernprogramm: Erstellen von Drillthrough- und Hauptberichten (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="60339-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="60339-103">In diesem Lernprogramm erfahren Sie, wie Sie zwei Berichtsarten erstellen: einen Drillthroughbericht und einen Hauptbericht.</span><span class="sxs-lookup"><span data-stu-id="60339-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="60339-104">Die in diesen Berichten verwendeten Beispielvertriebsdaten werden aus einem Analysis Services-Cube abgerufen.</span><span class="sxs-lookup"><span data-stu-id="60339-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="60339-105">Die folgende Abbildung zeigt die Berichte, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="60339-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="60339-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="60339-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="60339-107">Die folgende Abbildung zeigt, wie der Feldwert, Games und Toys, im Hauptbericht im Titel des Drillthrough-Berichts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="60339-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="60339-108">Die Daten im Drillthroughbericht beziehen sich auf die Produktkategorie "Games and Toys".</span><span class="sxs-lookup"><span data-stu-id="60339-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="60339-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="60339-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="60339-110">Lernziele</span><span class="sxs-lookup"><span data-stu-id="60339-110">What You Will Learn</span></span>  
 <span data-ttu-id="60339-111">**Im Drillthroughbericht lernen Sie Folgendes:**</span><span class="sxs-lookup"><span data-stu-id="60339-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="60339-112">Erstellen eines Drillthrough-Matrixberichts und eines Datasets mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="60339-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="60339-113">Angeben einer Datenverbindung</span><span class="sxs-lookup"><span data-stu-id="60339-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="60339-114">Erstellen einer MDX-Abfrage</span><span class="sxs-lookup"><span data-stu-id="60339-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="60339-115">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="60339-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="60339-116">Hinzufügen von Teilergebnissen und Summen</span><span class="sxs-lookup"><span data-stu-id="60339-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="60339-117">Stil auswählen</span><span class="sxs-lookup"><span data-stu-id="60339-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="60339-118">Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="60339-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="60339-119">Hinzufügen von Spalten zum Anzeigen von Umsatz Werten in Sparklines</span><span class="sxs-lookup"><span data-stu-id="60339-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="60339-120">Hinzufügen des Berichtstitels mit dem Namen der Produktkategorie</span><span class="sxs-lookup"><span data-stu-id="60339-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="60339-121">Aktualisieren von Parametereigenschaften</span><span class="sxs-lookup"><span data-stu-id="60339-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="60339-122">Speichern des Berichts in einer SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="60339-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="60339-123">**Im Hauptbericht lernen Sie Folgendes:**</span><span class="sxs-lookup"><span data-stu-id="60339-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="60339-124">Erstellen des Hauptmatrixberichts und des Datasets mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="60339-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="60339-125">Angeben einer Datenverbindung</span><span class="sxs-lookup"><span data-stu-id="60339-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="60339-126">Erstellen einer MDX-Abfrage</span><span class="sxs-lookup"><span data-stu-id="60339-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="60339-127">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="60339-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="60339-128">Hinzufügen von Teilergebnissen und Summen</span><span class="sxs-lookup"><span data-stu-id="60339-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="60339-129">Stil auswählen</span><span class="sxs-lookup"><span data-stu-id="60339-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="60339-130">Entfernen der Gesamtergebniszeile</span><span class="sxs-lookup"><span data-stu-id="60339-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="60339-131">Konfigurieren der Textfeldaktion für den Drillthrough</span><span class="sxs-lookup"><span data-stu-id="60339-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="60339-132">Ersetzen von numerischen Werten durch Indikatoren</span><span class="sxs-lookup"><span data-stu-id="60339-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="60339-133">Aktualisieren von Parametereigenschaften</span><span class="sxs-lookup"><span data-stu-id="60339-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="60339-134">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="60339-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="60339-135">Speichern des Berichts in einer SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="60339-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="60339-136">Ausführen des Haupt- und Drillthroughberichts</span><span class="sxs-lookup"><span data-stu-id="60339-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="60339-137">Geschätzte Zeit zum Bearbeiten dieses Lernprogramms: 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="60339-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60339-138">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="60339-138">Requirements</span></span>  
 <span data-ttu-id="60339-139">Dieses Lernprogramm erfordert Zugriff auf den Contoso Sales-Cube.</span><span class="sxs-lookup"><span data-stu-id="60339-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="60339-140">Diese Anforderung gilt sowohl für den Drillthrough- als auch für den Hauptbericht.</span><span class="sxs-lookup"><span data-stu-id="60339-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="60339-141">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="60339-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="60339-142">1. Erstellen eines Drillthrough-Berichts mithilfe des Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="60339-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="60339-143">Erstellen Sie im Dialogfeld Erste Schritte mit dem **Tabellen- oder Matrix-Assistenten**einen Matrixbericht.</span><span class="sxs-lookup"><span data-stu-id="60339-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="60339-144">Im Assistenten stehen zwei Modi zur Auswahl: Berichtsentwurf und Entwurf von freigegebenen Datasets.</span><span class="sxs-lookup"><span data-stu-id="60339-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="60339-145">In diesem Lernprogramm verwenden Sie den Berichtsentwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="60339-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="60339-146">So erstellen Sie einen neuen Bericht</span><span class="sxs-lookup"><span data-stu-id="60339-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="60339-147">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="60339-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="60339-148">Das Dialogfeld **Erste Schritte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="60339-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="60339-149">Wenn Sie nicht angezeigt wird, klicken Sie auf der Schaltfläche **Berichts-Generator** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="60339-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="60339-150">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="60339-151">Vergewissern Sie sich, dass im rechten Bereich **Tabellen- oder Matrix-Assistent** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="60339-152">1a.</span><span class="sxs-lookup"><span data-stu-id="60339-152">1a.</span></span> <span data-ttu-id="60339-153">Angeben einer Datenverbindung</span><span class="sxs-lookup"><span data-stu-id="60339-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="60339-154">Eine Datenverbindung enthält die erforderlichen Informationen zum Herstellen einer Verbindung mit einer externen Datenquelle, z. B. einem Analysis Services-Cube oder einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="60339-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="60339-155">Sie können zum Angeben einer Datenverbindung eine freigegebene Datenquelle vom Berichtsserver verwenden oder eine eingebettete Datenquelle erstellen, die nur in diesem Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60339-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="60339-156">In diesem Lernprogramm verwenden Sie eine eingebettete Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="60339-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="60339-157">Weitere Informationen zur Verwendung von freigegebenen Datenquellen finden Sie unter [Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="60339-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="60339-158">So erstellen Sie eine eingebettete Datenquelle</span><span class="sxs-lookup"><span data-stu-id="60339-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="60339-159">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="60339-160">Die Seite **Verbindung mit einer Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="60339-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="60339-161">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="60339-161">Click **New**.</span></span> <span data-ttu-id="60339-162">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="60339-163">Geben Sie im Feld **Name**als Name für die Datenquelle **Online and Reseller Sales Detail** ein.</span><span class="sxs-lookup"><span data-stu-id="60339-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="60339-164">Wählen Sie unter **Verbindungstyp auswählen**die Option **Microsoft SQL Server Analysis Services**aus, und klicken Sie anschließend auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="60339-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="60339-165">Vergewissern Sie sich, dass unter **Datenquelle**die Option **Microsoft SQL Server Analysis Services (AdomdClient)** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="60339-166">Geben Sie unter **Servername**den Namen eines Servers ein, auf dem eine Instanz von Analysis Services installiert ist.</span><span class="sxs-lookup"><span data-stu-id="60339-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="60339-167">Wählen Sie unter **Datenbanknamen eingeben oder auswählen**den Contoso-Cube aus.</span><span class="sxs-lookup"><span data-stu-id="60339-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="60339-168">Überprüfen Sie, ob die **Verbindungszeichenfolge** die folgende Syntax enthält:</span><span class="sxs-lookup"><span data-stu-id="60339-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="60339-169">Der `<servername>` ist der Name der Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , auf der Analysis Services installiert sind.</span><span class="sxs-lookup"><span data-stu-id="60339-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="60339-170">Klicken Sie auf **Anmeldeinformationstyp**.</span><span class="sxs-lookup"><span data-stu-id="60339-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-171">Abhängig davon, wie die Berechtigungen für die Datenquelle konfiguriert sind, müssen Sie u. U. die standardmäßigen Authentifizierungsoptionen ändern.</span><span class="sxs-lookup"><span data-stu-id="60339-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="60339-172">Weitere Informationen finden Sie unter [Sicherheit &#40;Berichts-Generator&#41;](report-builder/security-report-builder.md)erstellen.</span><span class="sxs-lookup"><span data-stu-id="60339-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="60339-173">Die Seite **Verbindung mit einer Datenquelle auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="60339-174">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="60339-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="60339-175">Die **erfolgreich erstellte Nachrichten Verbindung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="60339-176">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="60339-177">1B.</span><span class="sxs-lookup"><span data-stu-id="60339-177">1b.</span></span> <span data-ttu-id="60339-178">Erstellen einer MDX-Abfrage</span><span class="sxs-lookup"><span data-stu-id="60339-178">Create an MDX Query</span></span>  
 <span data-ttu-id="60339-179">In einem Bericht können Sie ein freigegebenes Dataset mit einer vordefinierten Abfrage verwenden oder ein eingebettetes Dataset erstellen, das nur in Ihrem Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60339-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="60339-180">In diesem Lernprogramm erstellen Sie ein eingebettetes Dataset.</span><span class="sxs-lookup"><span data-stu-id="60339-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="60339-181">So erstellen Sie Abfragefilter</span><span class="sxs-lookup"><span data-stu-id="60339-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="60339-182">Klicken Sie auf der Seite **Abfrage entwerfen** im Bereich Metadaten auf die Schaltfläche **(...)**.</span><span class="sxs-lookup"><span data-stu-id="60339-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="60339-183">Klicken Sie im Dialogfeld **Cubeauswahl** auf „Sales“ und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="60339-184">Wenn Sie die MDX-Abfrage nicht manuell erstellen möchten, klicken Sie auf das Symbol ![In den Entwurfsmodus wechseln](media/rsqdicon-designmode.gif "Wechselt in den Entwurfsmodus"), wechseln Sie im Abfrage-Designer zum Abfragemodus, fügen Sie die abgeschlossene MDX in den Abfrage-Designer ein, und fahren Sie anschließend mit Schritt 6 unter [So erstellen Sie das Dataset](#DSkip) fort.</span><span class="sxs-lookup"><span data-stu-id="60339-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="60339-185">Erweitern Sie im Bereich Measuregruppe den Eintrag „Channel“, und ziehen Sie anschließend „Channel Name“ in die Spalte **Hierarchie** im Filterbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="60339-186">Der Dimensionsname, Channel, wird automatisch zur Spalte **Dimension** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="60339-187">Nehmen Sie keine Änderungen an den Spalten **Dimension** oder **Operator** vor.</span><span class="sxs-lookup"><span data-stu-id="60339-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="60339-188">Klicken Sie zum Öffnen der Liste **Filterausdruck** auf den Abwärtspfeil in der Spalte **Filterausdruck** .</span><span class="sxs-lookup"><span data-stu-id="60339-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="60339-189">Erweitern Sie in der Filterausdruckliste den Eintrag **All Channel**, klicken Sie auf **Online**, auf **Reseller**und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-190">Die Abfrage enthält nun einen Filter, um nur die folgenden Vertriebswege einzuschließen: Online und Wiederverkäufer.</span><span class="sxs-lookup"><span data-stu-id="60339-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="60339-191">Erweitern Sie die Dimension „Sales Territory“, und ziehen Sie anschließend „Sales Territory Group“ in die Spalte **Hierarchie** unter **Channel Name**.</span><span class="sxs-lookup"><span data-stu-id="60339-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="60339-192">Öffnen Sie die Liste **Filterausdruck** , erweitern Sie **All Sales Territory**, klicken Sie auf **North America**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-193">Die Abfrage enthält nun einen Filter, um nur den Vertrieb in Nordamerika einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="60339-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="60339-194">Erweitern Sie im Bereich „Measure Group“ den Eintrag „Date“, und ziehen Sie anschließend „Calendar Year“ in die Spalte **Hierarchie** im Filterbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="60339-195">Der Dimensionsname, Date, wird automatisch zur Spalte **Dimension** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="60339-196">Nehmen Sie keine Änderungen an den Spalten **Dimension** oder **Operator** vor.</span><span class="sxs-lookup"><span data-stu-id="60339-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="60339-197">Klicken Sie zum Öffnen der Liste **Filterausdruck** auf den Abwärtspfeil in der Spalte **Filterausdruck** .</span><span class="sxs-lookup"><span data-stu-id="60339-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="60339-198">Erweitern Sie in der Filterausdruckliste den Eintrag **All Date**, klicken Sie auf **Year 2009**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-199">Die Abfrage enthält nun einen Filter, um nur das Kalenderjahr 2009 einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="60339-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="60339-200">So erstellen Sie den Parameter</span><span class="sxs-lookup"><span data-stu-id="60339-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="60339-201">Erweitern Sie die Dimension „Product“, und ziehen Sie anschließend das Element „Product Category Name“ in die Spalte **Hierarchie** unter **Calendar Year**.</span><span class="sxs-lookup"><span data-stu-id="60339-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="60339-202">Öffnen Sie die Liste **Filterausdruck** , klicken Sie auf **All Products**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="60339-203">Klicken Sie auf das Kontrollkästchen **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="60339-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="60339-204">Die Abfrage enthält nun den Parameter „ProductProductCategoryName“.</span><span class="sxs-lookup"><span data-stu-id="60339-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-205">Der Parameter enthält die Namen von Produktkategorien.</span><span class="sxs-lookup"><span data-stu-id="60339-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="60339-206">Wenn Sie im Hauptbericht auf den Namen einer Produktkategorie klicken, wird dieser Name durch Verwendung dieses Parameters an den Drillthroughbericht übergeben.</span><span class="sxs-lookup"><span data-stu-id="60339-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="60339-207">So erstellen Sie das DataSet</span><span class="sxs-lookup"><span data-stu-id="60339-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="60339-208">Ziehen Sie „Channel Name“ aus der Dimension „Channel“ in den Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="60339-209">Ziehen Sie „Product Category Name“ aus der Dimension „Product“ in den Datenbereich, und legen Sie es rechts neben „Channel Name“ ab.</span><span class="sxs-lookup"><span data-stu-id="60339-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="60339-210">Ziehen Sie „Product Subcategory Name“ aus der Dimension „Product“ in den Datenbereich, und legen Sie es rechts neben „Product Category Name“ ab.</span><span class="sxs-lookup"><span data-stu-id="60339-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="60339-211">Erweitern Sie im Bereich „Metadaten“ zuerst den Eintrag **Measure**und anschließend „Sales“.</span><span class="sxs-lookup"><span data-stu-id="60339-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="60339-212">Ziehen Sie das Measure „Sales Amount“ in den Datenbereich, und legen Sie es rechts neben „Product Subcategory Name“ ab.</span><span class="sxs-lookup"><span data-stu-id="60339-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="60339-213">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **ausführen (!)**.</span><span class="sxs-lookup"><span data-stu-id="60339-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="60339-214">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="60339-215">1C.</span><span class="sxs-lookup"><span data-stu-id="60339-215">1c.</span></span> <span data-ttu-id="60339-216">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="60339-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="60339-217">Durch das Auswählen von Feldern für die Datengruppierung entwerfen Sie eine Matrix mit Zeilen und Spalten, in denen Detaildaten und aggregierte Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60339-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="60339-218">So gruppieren Sie Daten</span><span class="sxs-lookup"><span data-stu-id="60339-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="60339-219">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-220">Ziehen Sie „Product_Subcategory_Name“ auf der Seite **Felder anordnen** in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="60339-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-221">Die Leerzeichen in den Namen werden durch Unterstriche ersetzt (_).</span><span class="sxs-lookup"><span data-stu-id="60339-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="60339-222">Beispiel: Product Category Name wird zu Product_Category_Name.</span><span class="sxs-lookup"><span data-stu-id="60339-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="60339-223">Ziehen Sie Channel_Name in **Spaltengruppen**.</span><span class="sxs-lookup"><span data-stu-id="60339-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="60339-224">Ziehen Sie Sales_Amount in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="60339-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="60339-225">Sales_Amount wird automatisch von der Sum-Funktion aggregiert, dem Standardaggregat für numerische Felder.</span><span class="sxs-lookup"><span data-stu-id="60339-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="60339-226">Der Wert ist `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="60339-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="60339-227">Öffnen Sie die Dropdownliste, um die anderen verfügbaren Aggregatfunktionen anzuzeigen (ändern Sie die Aggregatfunktion nicht).</span><span class="sxs-lookup"><span data-stu-id="60339-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="60339-228">Ziehen Sie Sales_Return_Amount in **Werte**, und fügen Sie dieses Feld unter `[Sum(Sales_Amount)]`ein.</span><span class="sxs-lookup"><span data-stu-id="60339-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="60339-229">In Schritt 4 und 5 werden die Daten angegeben, die in der Matrix angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60339-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="60339-230">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="60339-231">1D.</span><span class="sxs-lookup"><span data-stu-id="60339-231">1d.</span></span> <span data-ttu-id="60339-232">Hinzufügen von Teilergebnissen und Summen</span><span class="sxs-lookup"><span data-stu-id="60339-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="60339-233">Nachdem Sie Gruppen erstellt haben, können Sie Zeilen hinzufügen und formatieren, in denen Aggregatwerte für die Felder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60339-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="60339-234">Sie können auch auswählen, ob alle Daten angezeigt werden oder der Benutzer gruppierte Daten interaktiv erweitern und reduzieren kann.</span><span class="sxs-lookup"><span data-stu-id="60339-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="60339-235">So fügen Sie Teilergebnisse und Summen hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="60339-236">Vergewissern Sie sich, dass auf der Seite **Layout auswählen** unter **Optionen die Option** **Teil-und Gesamtsummen anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="60339-237">Im Vorschaubereich des Assistenten wird eine Matrix mit vier Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="60339-238">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="60339-239">1E.</span><span class="sxs-lookup"><span data-stu-id="60339-239">1e.</span></span> <span data-ttu-id="60339-240">Auswählen eines Formats</span><span class="sxs-lookup"><span data-stu-id="60339-240">Choose a Style</span></span>  
 <span data-ttu-id="60339-241">Ein Format dient zum Angeben eines Schriftschnitts, einer Farbpalette und einer Rahmenart.</span><span class="sxs-lookup"><span data-stu-id="60339-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="60339-242">So geben Sie ein Format an</span><span class="sxs-lookup"><span data-stu-id="60339-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="60339-243">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile die Option Slate aus.</span><span class="sxs-lookup"><span data-stu-id="60339-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="60339-244">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="60339-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="60339-245">Die Tabelle wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="60339-246">Klicken Sie auf **Ausführen (!)**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="60339-247">2. Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="60339-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="60339-248">Übernehmen Sie die Währungsformatierung für die Sales Amount-Felder im Drillthroughbericht.</span><span class="sxs-lookup"><span data-stu-id="60339-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="60339-249">So formatieren Sie Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="60339-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="60339-250">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-251">Um mehrere Zellen in einem Schritt auszuwählen und zu formatieren, drücken Sie die STRG-TASTE, und wählen Sie dann die Zellen aus, die die numerischen Vertriebsdaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="60339-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="60339-252">Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** auf **Währung**.</span><span class="sxs-lookup"><span data-stu-id="60339-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="60339-253">3. Hinzufügen von Spalten zum Anzeigen von Umsatz Werten in Sparklines</span><span class="sxs-lookup"><span data-stu-id="60339-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="60339-254">Statt Umsätze und Umsatzrenditen als Währungswerte anzuzeigen, zeigt der Bericht die Werte in einer Sparkline an.</span><span class="sxs-lookup"><span data-stu-id="60339-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="60339-255">So fügen Sie Sparklines zu Spalten hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="60339-256">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-257">Klicken Sie in der Gesamtergebnisgruppe der Matrix mit der rechten Maustaste auf die Spalte **Sales Amount** , zeigen Sie auf **Spalte einfügen**, und klicken Sie anschließend auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="60339-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="60339-258">Rechts von **Sales Amount**wird eine leere Spalte eingefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="60339-259">Klicken Sie im Menüband auf **Rechteck**und anschließend auf die leere Zelle rechts von der Zelle `[Sum(Sales_Amount)]` in der Zeilengruppe [Product_Subcategory].</span><span class="sxs-lookup"><span data-stu-id="60339-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="60339-260">Klicken Sie im Menüband auf das Symbol **Sparkline** und anschließend auf die Zelle, in der das Rechteck hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="60339-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="60339-261">Vergewissern Sie sich, dass im Dialogfeld **Sparklinetyp auswählen** der Typ **Spalte** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="60339-262">Klicken Sie mit der rechten Maustaste auf die Sparkline.</span><span class="sxs-lookup"><span data-stu-id="60339-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="60339-263">Klicken Sie im Bereich Diagrammdaten auf das Symbol **Feld hinzufügen** und anschließend auf Sales_Amount.</span><span class="sxs-lookup"><span data-stu-id="60339-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="60339-264">Klicken Sie mit der rechten Maustaste auf die Spalte `Sales_Return_Amount` , und fügen Sie dann rechts davon eine Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="60339-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="60339-265">Wiederholen Sie die Schritte 2 bis 6.</span><span class="sxs-lookup"><span data-stu-id="60339-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="60339-266">Klicken Sie mit der rechten Maustaste auf die Sparkline.</span><span class="sxs-lookup"><span data-stu-id="60339-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="60339-267">Klicken Sie im Bereich Diagrammdaten auf das Symbol **Feld hinzufügen** und anschließend auf Sales_Return_Amount.</span><span class="sxs-lookup"><span data-stu-id="60339-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="60339-268">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="60339-269">4. Hinzufügen des Berichts Titels mit dem Namen der Produktkategorie</span><span class="sxs-lookup"><span data-stu-id="60339-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="60339-270">Ein Berichtstitel wird oben im Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="60339-271">Sie können den Berichtstitel in eine Berichtskopfzeile einfügen oder, wenn der Bericht keine Kopfzeile enthält, in einem Textfeld am oberen Rand des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="60339-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="60339-272">In diesem Lernprogramm verwenden Sie das Textfeld, das automatisch am oberen Rand des Berichtshauptteils platziert wird.</span><span class="sxs-lookup"><span data-stu-id="60339-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="60339-273">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="60339-274">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-275">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="60339-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="60339-276">Geben Sie **Sales and Returns for Category:** ein.</span><span class="sxs-lookup"><span data-stu-id="60339-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="60339-277">Klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Platzhalter erstellen**.</span><span class="sxs-lookup"><span data-stu-id="60339-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="60339-278">Klicken Sie auf die Schaltfläche **(fx)** rechts neben der Liste **Wert** .</span><span class="sxs-lookup"><span data-stu-id="60339-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="60339-279">Klicken Sie im Dialogfeld **Ausdruck** im Bereich Kategorie auf **Dataset**und anschließend der Liste **Werte** auf `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="60339-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="60339-280">Das Feld **Ausdruck** enthält den folgenden Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="60339-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="60339-281">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="60339-282">Der Berichtstitel enthält den Namen der ersten Produktkategorie.</span><span class="sxs-lookup"><span data-stu-id="60339-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="60339-283">Später, nachdem Sie diesen Bericht als Drillthroughbericht ausgeführt haben, ändert sich der Name der Produktkategorie dynamisch entsprechend dem Namen der Produktkategorie, auf die im Hauptbericht geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="60339-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="60339-284">5. Aktualisieren von Parameter Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="60339-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="60339-285">Standardmäßig sind Parameter sichtbar, was für diesen Bericht ungeeignet ist.</span><span class="sxs-lookup"><span data-stu-id="60339-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="60339-286">Sie werden die Parametereigenschaften für den Drillthroughbericht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60339-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="60339-287">So blenden Sie einen Parameter aus</span><span class="sxs-lookup"><span data-stu-id="60339-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="60339-288">Erweitern Sie im Berichtsdatenbereich den Eintrag **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="60339-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="60339-289">Klicken Sie mit der rechten Maustaste auf \@ProductProductCategoryName und dann auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="60339-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-290">Das Zeichen \@ neben dem Namen zeigt an, dass es sich um einen Parameter handelt.</span><span class="sxs-lookup"><span data-stu-id="60339-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="60339-291">Klicken Sie auf der Registerkarte **Allgemein** auf **Ausgeblendet**.</span><span class="sxs-lookup"><span data-stu-id="60339-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="60339-292">Geben Sie im Feld **Eingabeaufforderung** den Text **Product Category**ein.</span><span class="sxs-lookup"><span data-stu-id="60339-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-293">Da der Parameter verborgen ist, wird diese Eingabeaufforderung nie verwendet.</span><span class="sxs-lookup"><span data-stu-id="60339-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="60339-294">Klicken Sie optional auf **Verfügbare Werte** und **Standardwerte** , und überprüfen Sie die dort enthaltenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="60339-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="60339-295">Ändern Sie keine Optionen auf diesen Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="60339-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="60339-296">6. Speichern des Berichts in einer SharePoint-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="60339-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="60339-297">Sie können den Bericht in einer SharePoint-Bibliothek, auf einem Berichtsserver oder auf dem Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="60339-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="60339-298">Wenn Sie den Bericht auf dem Computer speichern, ist eine Reihe von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen nicht verfügbar, z. B. Berichtsteile und Unterberichte.</span><span class="sxs-lookup"><span data-stu-id="60339-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="60339-299">In diesem Lernprogramm speichern Sie den Bericht in der SharePoint-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="60339-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="60339-300">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="60339-300">To save the report</span></span>  
  
1.  <span data-ttu-id="60339-301">Klicken Sie über die Schaltfläche Berichts-Generator auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="60339-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="60339-302">Das Dialogfeld **Als Bericht speichern** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="60339-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-303">Wenn Sie einen Bericht erneut speichern, wird er automatisch am vorherigen Speicherort erneut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="60339-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="60339-304">Verwenden Sie die Option **Speichern unter** , um den Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="60339-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="60339-305">Um eine Liste der zuletzt verwendeten Berichtsserver und SharePoint-Websites anzuzeigen, klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="60339-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="60339-306">Wählen Sie den Namen der SharePoint-Website aus, für die Sie Berechtigungen zum Speichern von Berichten haben, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="60339-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="60339-307">Die URL der SharePoint-Bibliothek hat folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="60339-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="60339-308">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="60339-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="60339-309">Unter**Letzte Sites und Server** werden die Bibliotheken auf der SharePoint-Website aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="60339-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="60339-310">Navigieren Sie zu der Bibliothek, in der Sie den Bericht speichern werden.</span><span class="sxs-lookup"><span data-stu-id="60339-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="60339-311">Ersetzen Sie im Feld **Name** den Standardnamen durch **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="60339-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="60339-312">Sie werden den Hauptbericht am selben Speicherort speichern.</span><span class="sxs-lookup"><span data-stu-id="60339-312">You will save the main report to the same location.</span></span> <span data-ttu-id="60339-313">Wenn Sie den Hauptbericht und die Drillthroughberichte an unterschiedlichen Speicherorten oder Bibliotheken speichern möchten, müssen Sie den Pfad der Aktion **Gehe zu Bericht** im Hauptbericht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="60339-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="60339-314">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="60339-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="60339-315">1. Erstellen eines neuen Berichts mit dem Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="60339-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="60339-316">Erstellen Sie im Dialogfeld **Erste Schritte** mit dem **Tabellen- oder Matrix-Assistenten**einen Matrixbericht.</span><span class="sxs-lookup"><span data-stu-id="60339-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="60339-317">So erstellen Sie einen neuen Bericht</span><span class="sxs-lookup"><span data-stu-id="60339-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="60339-318">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="60339-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="60339-319">Überprüfen Sie im Dialogfeld **Erste Schritte** , dass **Neuer Bericht** ausgewählt ist, und klicken Sie anschließend auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="60339-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="60339-320">1a.</span><span class="sxs-lookup"><span data-stu-id="60339-320">1a.</span></span> <span data-ttu-id="60339-321">Angeben einer Datenverbindung</span><span class="sxs-lookup"><span data-stu-id="60339-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="60339-322">Sie werden dem Hauptbericht eine eingebettete Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="60339-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="60339-323">So erstellen Sie eine eingebettete Datenquelle</span><span class="sxs-lookup"><span data-stu-id="60339-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="60339-324">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="60339-325">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="60339-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="60339-326">Geben Sie im Feld **Name**als Name für die Datenquelle **Online and Reseller Sales Main** ein.</span><span class="sxs-lookup"><span data-stu-id="60339-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="60339-327">Wählen Sie unter **Verbindungstyp auswählen**die Option **Microsoft SQL Server Analysis Services**aus, und klicken Sie anschließend auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="60339-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="60339-328">Vergewissern Sie sich, dass unter **Datenquelle**die Option **Microsoft SQL Server Analysis Services (AdomdClient)** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="60339-329">Geben Sie unter **Server Name**den Namen eines Servers ein, auf dem eine Instanz von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="60339-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="60339-330">Wählen Sie unter **Datenbanknamen eingeben oder auswählen**den Contoso-Cube aus.</span><span class="sxs-lookup"><span data-stu-id="60339-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="60339-331">Überprüfen Sie, dass die **Verbindungszeichenfolge** die folgende Syntax enthält:</span><span class="sxs-lookup"><span data-stu-id="60339-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="60339-332">Klicken Sie auf **Anmeldeinformationstyp**.</span><span class="sxs-lookup"><span data-stu-id="60339-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="60339-333">Abhängig davon, wie die Berechtigungen für die Datenquelle konfiguriert sind, müssen Sie u. U. die Standardauthentifizierung ändern.</span><span class="sxs-lookup"><span data-stu-id="60339-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="60339-334">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="60339-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="60339-335">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="60339-336">1B.</span><span class="sxs-lookup"><span data-stu-id="60339-336">1b.</span></span> <span data-ttu-id="60339-337">Erstellen einer MDX-Abfrage</span><span class="sxs-lookup"><span data-stu-id="60339-337">Create an MDX Query</span></span>  
 <span data-ttu-id="60339-338">Erstellen Sie als Nächstes ein eingebettetes Dataset.</span><span class="sxs-lookup"><span data-stu-id="60339-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="60339-339">Hierzu erstellen Sie mit dem Abfrage-Designer Filter, Parameter und berechnete Elemente sowie das Dataset selbst.</span><span class="sxs-lookup"><span data-stu-id="60339-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="60339-340">So erstellen Sie Abfragefilter</span><span class="sxs-lookup"><span data-stu-id="60339-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="60339-341">Klicken Sie auf der Seite **Abfrage entwerfen** im Bereich Metadaten auf die Schaltfläche mit den Auslassungs Punkten **(...)**.</span><span class="sxs-lookup"><span data-stu-id="60339-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="60339-342">Klicken Sie im Dialogfeld **Cubeauswahl** auf „Sales“ und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="60339-343">Wenn Sie die MDX-Abfrage nicht manuell erstellen möchten, klicken Sie auf das Symbol ![In den Entwurfsmodus wechseln](media/rsqdicon-designmode.gif "Wechselt in den Entwurfsmodus"), wechseln Sie im Abfrage-Designer zum Abfragemodus, fügen Sie die abgeschlossene MDX in den Abfrage-Designer ein, und fahren Sie anschließend mit Schritt 5 unter [So erstellen Sie das Dataset](#MSkip) fort.</span><span class="sxs-lookup"><span data-stu-id="60339-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="60339-344">Erweitern Sie im Bereich Measuregruppe den Eintrag „Channel“, und ziehen Sie anschließend „Channel Name“ in die Spalte **Hierarchie** im Filterbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="60339-345">Der Dimensionsname, Channel, wird automatisch zur Spalte **Dimension** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="60339-346">Nehmen Sie keine Änderungen an den Spalten **Dimension** oder **Operator** vor.</span><span class="sxs-lookup"><span data-stu-id="60339-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="60339-347">Klicken Sie zum Öffnen der Liste **Filterausdruck** auf den Abwärtspfeil in der Spalte **Filterausdruck** .</span><span class="sxs-lookup"><span data-stu-id="60339-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="60339-348">Erweitern Sie in der Filterausdruckliste den Eintrag **All Channel**, klicken Sie auf **Online** und **Reseller**und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-349">Die Abfrage enthält nun einen Filter, um nur die folgenden Vertriebswege einzuschließen: Online und Wiederverkäufer.</span><span class="sxs-lookup"><span data-stu-id="60339-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="60339-350">Erweitern Sie die Dimension Sales Territory, und ziehen Sie dann Sales Territory Group in die Spalte **Hierarchie** unter **Channel Name**.</span><span class="sxs-lookup"><span data-stu-id="60339-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="60339-351">Öffnen Sie die Liste **Filterausdruck** , erweitern Sie **All Sales Territory**, klicken Sie auf **North America**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-352">Die Abfrage enthält nun einen Filter, um nur den Vertrieb in Nordamerika einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="60339-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="60339-353">Erweitern Sie im Bereich Measure Group den Eintrag „Date“, und ziehen Sie anschließend „Calendar Year“ in die Spalte **Hierarchie** im Filterbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="60339-354">Der Dimensionsname, Date, wird automatisch zur Spalte **Dimension** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60339-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="60339-355">Nehmen Sie keine Änderungen an den Spalten **Dimension** oder **Operator** vor.</span><span class="sxs-lookup"><span data-stu-id="60339-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="60339-356">Klicken Sie zum Öffnen der Liste **Filterausdruck** auf den Abwärtspfeil in der Spalte **Filterausdruck** .</span><span class="sxs-lookup"><span data-stu-id="60339-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="60339-357">Erweitern Sie in der Filterausdruckliste den Eintrag **All Date**, klicken Sie auf **Year 2009**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-358">Die Abfrage enthält nun einen Filter, um nur das Kalenderjahr 2009 einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="60339-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="60339-359">So erstellen Sie den Parameter</span><span class="sxs-lookup"><span data-stu-id="60339-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="60339-360">Erweitern Sie die Dimension „Product“, und ziehen Sie anschließend das Element „Product Category Name“ in die Spalte **Hierarchie** unter **Sales Territory Group**.</span><span class="sxs-lookup"><span data-stu-id="60339-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="60339-361">Öffnen Sie die Liste **Filterausdruck** , klicken Sie auf **All Products**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="60339-362">Klicken Sie auf das Kontrollkästchen **Parameter** .</span><span class="sxs-lookup"><span data-stu-id="60339-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="60339-363">Die Abfrage enthält nun den Parameter „ProductProductCategoryName“.</span><span class="sxs-lookup"><span data-stu-id="60339-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="60339-364">So erstellen Sie berechnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60339-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="60339-365">Platzieren Sie den Cursor innerhalb des Bereichs Berechnete Elemente, klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="60339-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="60339-366">Erweitern Sie im Metadatenbereich **Measures** , und erweitern Sie dann Sales.</span><span class="sxs-lookup"><span data-stu-id="60339-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="60339-367">Ziehen Sie das Measure „Sales Quantity“ in das Feld **Ausdruck** , geben Sie das Subtraktionszeichen (-) ein, und ziehen Sie anschließend das Measure „Sales Return Quantity“ in das Feld **Ausdruck** ; platzieren Sie es hinter dem Subtraktionszeichen (-).</span><span class="sxs-lookup"><span data-stu-id="60339-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="60339-368">Im folgenden Code wird der Ausdruck gezeigt:</span><span class="sxs-lookup"><span data-stu-id="60339-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="60339-369">Geben Sie im Feld „Name“ die Zeichenfolge **Net QTY**ein, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="60339-370">Im Bereich Berechnete Elemente wird das berechnete Element **Net QTY** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="60339-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="60339-371">Klicken Sie mit der rechten Maustaste auf **Berechnete Elemente**, und klicken Sie anschließend auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="60339-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="60339-372">Erweitern Sie im Bereich Metadaten zuerst den Eintrag **Measures**und anschließend „Sales“.</span><span class="sxs-lookup"><span data-stu-id="60339-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="60339-373">Ziehen Sie das Measure „Sales Amount“ in das Feld **Ausdruck** , geben Sie das Subtraktionszeichen (-) ein, und ziehen Sie anschließend das Measure „Sales Return Amount“ in das Feld **Ausdruck** ; platzieren Sie es hinter dem Subtraktionszeichen (-).</span><span class="sxs-lookup"><span data-stu-id="60339-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="60339-374">Im folgenden Code wird der Ausdruck gezeigt:</span><span class="sxs-lookup"><span data-stu-id="60339-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="60339-375">Geben Sie im Feld **Name** den Text  **Net Sales**ein, und klicken Sie anschließend auf **OK**. Im Bereich Berechnete Elemente wird das berechnete Element **Net Sales** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="60339-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="60339-376">So erstellen Sie das DataSet</span><span class="sxs-lookup"><span data-stu-id="60339-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="60339-377">Ziehen Sie „Channel Name“ aus der Dimension „Channel“ in den Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="60339-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="60339-378">Ziehen Sie „Product Category Name“ aus der Dimension „Product“ in den Datenbereich, und legen Sie es rechts neben „Channel Name“ ab.</span><span class="sxs-lookup"><span data-stu-id="60339-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="60339-379">Ziehen Sie aus **Berechnete Elemente**das Element `Net QTY` in den Datenbereich, und legen Sie es rechts neben „Product Category Name“ ab.</span><span class="sxs-lookup"><span data-stu-id="60339-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="60339-380">Ziehen Sie aus Berechnete Elemente das Element „Net Sales“ in den Datenbereich, und legen Sie es rechts neben `Net QTY`ab.</span><span class="sxs-lookup"><span data-stu-id="60339-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="60339-381">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **ausführen (!)**.</span><span class="sxs-lookup"><span data-stu-id="60339-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="60339-382">Überprüfen Sie das Abfrageresultset.</span><span class="sxs-lookup"><span data-stu-id="60339-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="60339-383">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="60339-384">1C.</span><span class="sxs-lookup"><span data-stu-id="60339-384">1c.</span></span> <span data-ttu-id="60339-385">Gruppieren von Daten</span><span class="sxs-lookup"><span data-stu-id="60339-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="60339-386">Durch das Auswählen von Feldern für die Datengruppierung entwerfen Sie eine Matrix mit Zeilen und Spalten, in denen Detaildaten und aggregierte Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="60339-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="60339-387">So gruppieren Sie Daten</span><span class="sxs-lookup"><span data-stu-id="60339-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="60339-388">Ziehen Sie Product_Category_Name auf der Seite **Felder anordnen** in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="60339-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="60339-389">Ziehen Sie Channel_Name in **Spaltengruppen**.</span><span class="sxs-lookup"><span data-stu-id="60339-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="60339-390">Ziehen Sie `Net_QTY` zu **Werte**.</span><span class="sxs-lookup"><span data-stu-id="60339-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="60339-391">`Net_QTY` wird automatisch von der Sum-Funktion aggregiert, dem Standardaggregat für numerische Felder.</span><span class="sxs-lookup"><span data-stu-id="60339-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="60339-392">Der Wert ist `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="60339-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="60339-393">Wenn Sie die anderen verfügbaren Aggregatfunktionen anzeigen möchten, können Sie die Dropdownliste öffnen.</span><span class="sxs-lookup"><span data-stu-id="60339-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="60339-394">Ändern Sie die Aggregatfunktion nicht.</span><span class="sxs-lookup"><span data-stu-id="60339-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="60339-395">Ziehen Sie `Net_Sales_Return` in **Werte** , und platzieren Sie es unter `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="60339-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="60339-396">In Schritt 3 und 4 werden die Daten angegeben, die in der Matrix angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60339-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="60339-397">1D.</span><span class="sxs-lookup"><span data-stu-id="60339-397">1d.</span></span> <span data-ttu-id="60339-398">Hinzufügen von Teilergebnissen und Summen</span><span class="sxs-lookup"><span data-stu-id="60339-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="60339-399">Sie können in Berichten Teil- und Gesamtergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="60339-400">Die Daten im Hauptbericht zeigen einen Indikator an; Sie werden die Gesamtsumme nach Abschluss des Assistenten entfernen.</span><span class="sxs-lookup"><span data-stu-id="60339-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="60339-401">So fügen Sie Teilergebnisse und Gesamtsummen hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="60339-402">Vergewissern Sie sich, dass auf der Seite **Layout auswählen** unter **Optionen die Option** **Teil-und Gesamtsummen anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="60339-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="60339-403">Im Vorschaubereich des Assistenten wird eine Matrix mit vier Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="60339-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="60339-404">Wenn Sie den Bericht ausführen, wird jede Zeile folgendermaßen angezeigt: Die erste Zeile ist die Spaltengruppe, die zweite Zeile enthält die Spaltenüberschriften, die dritte Zeile enthält die Produktkategoriedaten (`[Sum(Net_ QTY)]` und `[Sum(Net_Sales)]`), und die vierte Zeile enthält die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="60339-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="60339-405">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="60339-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="60339-406">1E.</span><span class="sxs-lookup"><span data-stu-id="60339-406">1e.</span></span> <span data-ttu-id="60339-407">Auswählen eines Formats</span><span class="sxs-lookup"><span data-stu-id="60339-407">Choose a Style</span></span>  
 <span data-ttu-id="60339-408">Wenden Sie auf den Bericht das Format "Schiefer" an.</span><span class="sxs-lookup"><span data-stu-id="60339-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="60339-409">Dies ist das gleiche Format, das auch beim Drillthroughbericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60339-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="60339-410">So geben Sie ein Format an</span><span class="sxs-lookup"><span data-stu-id="60339-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="60339-411">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile die Option Slate aus.</span><span class="sxs-lookup"><span data-stu-id="60339-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="60339-412">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="60339-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="60339-413">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="60339-414">2. Entfernen der Gesamt Ergebniszeile</span><span class="sxs-lookup"><span data-stu-id="60339-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="60339-415">Die Datenwerte werden als Indikatorzustände angezeigt, einschließlich der Spaltengruppenergebnisse.</span><span class="sxs-lookup"><span data-stu-id="60339-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="60339-416">Entfernen Sie die Zeile, in der das Gesamtergebnis angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="60339-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="60339-417">So entfernen Sie die Gesamtergebniszeile</span><span class="sxs-lookup"><span data-stu-id="60339-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="60339-418">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-419">Klicken Sie auf die Ergebniszeile (die letzte Zeile in der Matrix), klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Zeilen löschen**.</span><span class="sxs-lookup"><span data-stu-id="60339-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="60339-420">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="60339-421">3. Konfigurieren der Text Feld Aktion für Drillthrough</span><span class="sxs-lookup"><span data-stu-id="60339-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="60339-422">Um den Drillthrough zu aktivieren, geben Sie eine Aktion für ein Textfeld im Hauptbericht an.</span><span class="sxs-lookup"><span data-stu-id="60339-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="60339-423">So aktivieren Sie eine Aktion</span><span class="sxs-lookup"><span data-stu-id="60339-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="60339-424">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-425">Klicken Sie mit der rechten Maustaste auf die Zelle, die Product_Category_Name enthält, und klicken Sie anschließend auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="60339-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="60339-426">Klicken Sie auf die Registerkarte **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="60339-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="60339-427">Wählen Sie **Gehe zu Bericht aus.**</span><span class="sxs-lookup"><span data-stu-id="60339-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="60339-428">Klicken Sie unter **Bericht angeben**auf **Durchsuchen**, und suchen Sie anschließend den Drillthroughbericht mit der Bezeichnung ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="60339-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="60339-429">Wenn Sie einen Parameter zur Ausführung des Drillthroughberichts hinzufügen möchten, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="60339-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="60339-430">Wählen Sie in der Liste **Name** den Eintrag ProductProductCategoryName aus.</span><span class="sxs-lookup"><span data-stu-id="60339-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="60339-431">Geben Sie in **Wert** Folgendes ein: `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="60339-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="60339-432">Product_Category_Name ist ein Feld im Dataset.</span><span class="sxs-lookup"><span data-stu-id="60339-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="60339-433">Sie müssen die Eigenschaft `UniqueName` einschließen, da für die Drillthroughaktion ein eindeutiger Wert erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="60339-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="60339-434">So formatieren Sie das Drillthroughfeld</span><span class="sxs-lookup"><span data-stu-id="60339-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="60339-435">Klicken Sie mit der rechten Maustaste auf die Zelle, die `Product_Category_Name`enthält, und klicken Sie anschließend auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="60339-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="60339-436">Klicken Sie auf die Registerkarte **Schriftart** .</span><span class="sxs-lookup"><span data-stu-id="60339-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="60339-437">Wählen Sie in der Liste **Effekte** die Option **Unterstrichen**aus.</span><span class="sxs-lookup"><span data-stu-id="60339-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="60339-438">Wählen Sie in der Liste **Farbe** die Option **Blau**aus.</span><span class="sxs-lookup"><span data-stu-id="60339-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="60339-439">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="60339-440">Die Produktkategorienamen weisen das übliche Linkformat (blau und unterstrichen) auf.</span><span class="sxs-lookup"><span data-stu-id="60339-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="60339-441">4. Ersetzen von numerischen Werten durch Indikatoren</span><span class="sxs-lookup"><span data-stu-id="60339-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="60339-442">Verwenden Sie Indikatoren, um den Status von Mengen und Umsätzen für Online- und Wiederverkäuferkanäle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="60339-443">So fügen Sie einen Indikator für Netto-QTY-Werte hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="60339-444">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-445">Klicken Sie im Menüband auf das Symbol **Rechteck** , und klicken Sie anschließend in die Zelle `[Sum(Net QTY)]` in der Zeilengruppe `[Product_Category_Name]` in der Spaltengruppe `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="60339-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="60339-446">Klicken Sie auf dem Menüband auf das Symbol **Indikator** , und klicken Sie anschließend in das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="60339-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="60339-447">Das Dialogfeld **Indikatortyp auswählen** wird geöffnet. Der Indikator **Direktional** ist vorausgewählt.</span><span class="sxs-lookup"><span data-stu-id="60339-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="60339-448">Klicken Sie auf den Typ **3 Zeichen** und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="60339-449">Klicken Sie mit der rechten Maustaste auf den Indikator, und klicken Sie im Bereich Messgerätdaten auf den Pfeil nach unten neben **(Keine Angabe)**.</span><span class="sxs-lookup"><span data-stu-id="60339-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="60339-450">Wählen Sie `Net_QTY`aus.</span><span class="sxs-lookup"><span data-stu-id="60339-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="60339-451">Wiederholen Sie die Schritte 2 bis 5 für die Zelle `[Sum(Net QTY)]` in der Zeilengruppe `[Product_Category_Name]` innerhalb von **Gesamt**.</span><span class="sxs-lookup"><span data-stu-id="60339-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="60339-452">So fügen Sie einen Indikator für Nettoumsatzwerte hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="60339-453">Klicken Sie im Menüband auf das Symbol **Rechteck** und anschließend in die Zelle `[Sum(Net_Sales)]` in der Zeilengruppe `[Product_Category_Name]` in der Spaltengruppe `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="60339-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="60339-454">Klicken Sie auf dem Menüband auf das Symbol **Indikator** , und klicken Sie anschließend in das Rechteck.</span><span class="sxs-lookup"><span data-stu-id="60339-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="60339-455">Klicken Sie auf den Typ **3 Zeichen** und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="60339-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="60339-456">Klicken Sie mit der rechten Maustaste auf den Indikator, und klicken Sie im Bereich Messgerätdaten auf den Pfeil nach unten neben **(Keine Angabe)**.</span><span class="sxs-lookup"><span data-stu-id="60339-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="60339-457">Wählen Sie `Net_Sales`aus.</span><span class="sxs-lookup"><span data-stu-id="60339-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="60339-458">Wiederholen Sie die Schritte 1 bis 4 für die Zelle `[Sum(Net_Sales)]` in der Zeilengruppe `[Product_Category_Name]` innerhalb von **Gesamt**.</span><span class="sxs-lookup"><span data-stu-id="60339-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="60339-459">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="60339-460">5. Aktualisieren von Parameter Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="60339-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="60339-461">Standardmäßig werden Parameter angezeigt, was für diesen Bericht nicht angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="60339-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="60339-462">Sie werden die Parametereigenschaften aktualisieren, um den Parameter zu einem internen Parameter zu machen.</span><span class="sxs-lookup"><span data-stu-id="60339-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="60339-463">So machen Sie den Parameter zu einem internen Parameter</span><span class="sxs-lookup"><span data-stu-id="60339-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="60339-464">Erweitern Sie im Berichtsdatenbereich den Eintrag **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="60339-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="60339-465">Klicken Sie mit der rechten Maustaste auf `@ProductProductCategoryName,` , und klicken Sie anschließend auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="60339-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="60339-466">Klicken Sie auf der Registerkarte **Allgemein** auf **Intern**.</span><span class="sxs-lookup"><span data-stu-id="60339-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="60339-467">Klicken Sie optional auf die Registerkarten **Verfügbare Werte** und **Standardwerte** , und überprüfen Sie die dort enthaltenen Optionen.</span><span class="sxs-lookup"><span data-stu-id="60339-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="60339-468">Ändern Sie keine Optionen auf diesen Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="60339-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="60339-469">6. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="60339-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="60339-470">Hinzufügen eines Titels zum Hauptbericht</span><span class="sxs-lookup"><span data-stu-id="60339-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="60339-471">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="60339-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="60339-472">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="60339-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="60339-473">Geben Sie **2009 Product Category Sales: Online and Reseller Category:** ein.</span><span class="sxs-lookup"><span data-stu-id="60339-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="60339-474">Wählen Sie den eingegebenen Text aus.</span><span class="sxs-lookup"><span data-stu-id="60339-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="60339-475">Wählen Sie auf der Registerkarte **Stamm** des Menübands in der Gruppe Schriftart die Schriftart **Times New Roman** , die Größe **16 pt** und die Schriftschnitte **Fett** und **Kursiv** aus.</span><span class="sxs-lookup"><span data-stu-id="60339-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="60339-476">Klicken Sie auf **Ausführen**, um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="60339-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="60339-477">7. speichern Sie den Hauptbericht in einer SharePoint-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="60339-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="60339-478">Speichern Sie den Hauptbericht in einer SharePoint-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="60339-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="60339-479">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="60339-479">To save the report</span></span>  
  
1.  <span data-ttu-id="60339-480">Klicken Sie auf **Entwurf**, um zur Entwurfsansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="60339-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="60339-481">Klicken Sie über die Schaltfläche Berichts-Generator auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="60339-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="60339-482">Wenn Sie eine Liste der zuletzt verwendeten Berichtsserver und SharePoint-Websites anzeigen möchten, klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="60339-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="60339-483">Wählen Sie den Namen der SharePoint-Website aus, für die Sie Berechtigungen zum Speichern von Berichten haben, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="60339-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="60339-484">Die URL der SharePoint-Bibliothek hat folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="60339-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="60339-485">Navigieren Sie zu der Bibliothek, in der Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="60339-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="60339-486">Ersetzen Sie unter **Name**den Standardnamen durch **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="60339-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="60339-487">Speichern Sie den Hauptbericht an demselben Speicherort, an dem Sie den Drillthroughbericht gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="60339-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="60339-488">Wenn Sie den Hauptbericht und die Drillthroughberichte an unterschiedlichen Speicherorten oder Bibliotheken speichern möchten, überprüfen Sie, dass die Aktion **Gehe zu Bericht** im Hauptbericht auf den korrekten Speicherort des Drillthroughberichts verweist.</span><span class="sxs-lookup"><span data-stu-id="60339-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="60339-489">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="60339-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="60339-490">8. Ausführen der Berichte "Main" und "Drillthrough"</span><span class="sxs-lookup"><span data-stu-id="60339-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="60339-491">Führen Sie den Hauptbericht aus, und klicken Sie dann auf Werte in der Produktkategoriespalte, um den Drillthroughbericht auszuführen.</span><span class="sxs-lookup"><span data-stu-id="60339-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="60339-492">So führen Sie die Berichte aus</span><span class="sxs-lookup"><span data-stu-id="60339-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="60339-493">Öffnen Sie die SharePoint-Bibliothek, in der die Berichte gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="60339-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="60339-494">Doppelklicken Sie auf ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="60339-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="60339-495">Der Bericht wird ausgeführt und zeigt Verkaufsinformationen zur Produktkategorie an.</span><span class="sxs-lookup"><span data-stu-id="60339-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="60339-496">Klicken Sie auf den Link **Games and Toys** in der Spalte, die Produktkategorienamen enthält.</span><span class="sxs-lookup"><span data-stu-id="60339-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="60339-497">Der Drillthroughbericht wird ausgeführt und zeigt nur die Werte für die Produktkategorie Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="60339-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="60339-498">Um zum Hauptbericht zurückzukehren, klicken Sie auf die Schaltfläche Zurück in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="60339-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="60339-499">Sie können sich auch andere Produktkategorien ansehen, indem Sie auf deren Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="60339-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60339-500">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60339-500">See Also</span></span>  
 [<span data-ttu-id="60339-501">Lernprogramme &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="60339-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
