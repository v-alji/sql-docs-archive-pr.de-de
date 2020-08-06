---
title: 'Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615256"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="dd9f6-102">Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="dd9f6-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="dd9f6-103">In diesem Lernprogramm erfahren Sie, wie Sie auf Grundlage von Beispielumsatzdaten einen einfachen Tabellenbericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="dd9f6-104">Die folgende Abbildung zeigt den Bericht, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="dd9f6-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="dd9f6-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="dd9f6-106">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="dd9f6-106">What You Will Learn</span></span>  
 <span data-ttu-id="dd9f6-107">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dd9f6-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="dd9f6-108">Erstellen eines neuen Berichts im Dialogfeld "Erste Schritte"</span><span class="sxs-lookup"><span data-stu-id="dd9f6-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="dd9f6-109">Angeben einer Datenverbindung im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="dd9f6-110">Erstellen einer Abfrage im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="dd9f6-111">Gruppieren von Daten im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="dd9f6-112">Hinzufügen von Teilergebnis- und Ergebniszeilen im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="dd9f6-113">Auswählen eines Formats im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="dd9f6-114">Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="dd9f6-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="dd9f6-115">Formatieren von Daten als Datum</span><span class="sxs-lookup"><span data-stu-id="dd9f6-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="dd9f6-116">Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="dd9f6-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="dd9f6-117">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="dd9f6-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="dd9f6-118">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="dd9f6-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="dd9f6-119">Exportieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="dd9f6-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="dd9f6-120">Ungefähre Dauer dieses Lernprogramms: 20 Minuten.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd9f6-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dd9f6-121">Requirements</span></span>  
 <span data-ttu-id="dd9f6-122">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="dd9f6-123">1. Erstellen eines neuen Berichts aus "Getting Started"</span><span class="sxs-lookup"><span data-stu-id="dd9f6-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="dd9f6-124">Erstellen Sie im Dialogfeld " **Getting Started** " einen Tabellen Bericht.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="dd9f6-125">Zwei Modi stehen zur Auswahl: Berichtsentwurf und Entwurf von freigegebenen Datasets.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="dd9f6-126">Im Berichtsentwurfsmodus legen Sie im Berichtsdatenbereich Daten und auf der Entwurfsoberfläche das Berichtslayout fest.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="dd9f6-127">Im Entwurfsmodus für freigegebene Datasets erstellen Sie Datasetabfragen, die für andere Benutzer freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="dd9f6-128">In diesem Lernprogramm verwenden Sie den Berichtsentwurfsmodus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="dd9f6-129">So erstellen Sie einen neuen Bericht</span><span class="sxs-lookup"><span data-stu-id="dd9f6-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="dd9f6-130">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft SQL Server 2012 Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="dd9f6-131">Das Dialogfeld **Erste Schritte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd9f6-132">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-133">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="dd9f6-134">Vergewissern Sie sich, dass im rechten Bereich **Tabellen- oder Matrix-Assistent** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="dd9f6-135">1a.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-135">1a.</span></span> <span data-ttu-id="dd9f6-136">Angeben einer Datenverbindung im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="dd9f6-137">Eine Datenverbindung enthält die Informationen zum Herstellen einer Verbindung mit einer externen Datenquelle, z. B. einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="dd9f6-138">Normalerweise erhalten Sie die Verbindungsinformationen und den zu verwendenden Anmeldeinformationstyp vom Datenquellenbesitzer.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="dd9f6-139">Sie können zum Angeben einer Datenverbindung eine freigegebene Datenquelle vom Berichtsserver verwenden oder eine eingebettete Datenquelle erstellen, die nur in diesem Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="dd9f6-140">In diesem Lernprogramm verwenden Sie eine eingebettete Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="dd9f6-141">Weitere Informationen zur Verwendung von freigegebenen Datenquellen finden Sie unter [Alternative Verfahren zum Herstellen einer Datenverbindung (Berichts-Generator)](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="dd9f6-142">So erstellen Sie eine eingebettete Datenquelle</span><span class="sxs-lookup"><span data-stu-id="dd9f6-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="dd9f6-143">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="dd9f6-144">Die Seite **Verbindung mit einer Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="dd9f6-145">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-145">Click **New**.</span></span> <span data-ttu-id="dd9f6-146">Das Dialogfeld **Datenquelleneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="dd9f6-147">Geben Sie im Feld **Name**den Namen **Product Sales** für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="dd9f6-148">Vergewissern Sie sich, dass unter **Verbindungstyp auswählen**die Option **Microsoft SQL Server** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="dd9f6-149">Geben Sie unter **Verbindungs Zeichenfolge**den folgenden Text *\<servername>* ein, wobei der Name einer Instanz von ist [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="dd9f6-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="dd9f6-150">Da Sie eine Abfrage verwenden, die die Daten enthält, anstatt die Daten aus einer Datenbank abzurufen, enthält die Verbindungszeichenfolge den Datenbanknamen nicht.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="dd9f6-151">Weitere Informationen finden Sie unter [Voraussetzungen für Lernprogramme &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="dd9f6-152">Klicken Sie auf **Anmeldeinformationen**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-152">Click **Credentials**.</span></span> <span data-ttu-id="dd9f6-153">Geben Sie die für den Zugriff auf die externe Datenquelle benötigten Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="dd9f6-154">Nun wird wieder die Seite **Verbindung mit einer Datenquelle auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="dd9f6-155">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="dd9f6-156">Die Meldung "Die Verbindung wurde erfolgreich hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="dd9f6-157">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="dd9f6-158">1B.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-158">1b.</span></span> <span data-ttu-id="dd9f6-159">Erstellen einer Abfrage im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="dd9f6-160">In einem Bericht können Sie ein freigegebenes Dataset mit einer vordefinierten Abfrage verwenden oder ein eingebettetes Dataset erstellen, das nur in Ihrem Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="dd9f6-161">In diesem Lernprogramm erstellen Sie ein eingebettetes Dataset.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd9f6-162">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="dd9f6-163">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-163">This makes the query quite long.</span></span> <span data-ttu-id="dd9f6-164">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="dd9f6-165">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="dd9f6-166">So erstellen Sie eine Abfrage</span><span class="sxs-lookup"><span data-stu-id="dd9f6-166">To create a query</span></span>  
  
1.  <span data-ttu-id="dd9f6-167">Auf der Seite **Abfrage entwerfen** ist der relationale Abfrage-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="dd9f6-168">Für dieses Lernprogramm verwenden Sie den textbasierten Abfrage-Designer.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="dd9f6-169">Klicken Sie auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-169">Click **Edit As Text**.</span></span> <span data-ttu-id="dd9f6-170">Der textbasierte Abfrage-Designer umfasst zwei Bereiche: den Abfragebereich und den Ergebnisbereich.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="dd9f6-171">Fügen Sie die folgende [!INCLUDE[tsql](../includes/tsql-md.md)] -Abfrage in das Feld **Abfrage** ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
  
    ```  
  
3.  <span data-ttu-id="dd9f6-172">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="dd9f6-173">Die Abfrage wird ausgeführt, und das Resultset für die Felder "SalesDate", "Subcategory", "Product", "Sales" und "Quantity" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="dd9f6-174">Die Spaltenüberschriften im Resultset basieren auf den Namen in der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="dd9f6-175">Im Dataset werden die Spaltennamen zu Feldnamen und werden im Bericht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="dd9f6-176">Nachdem Sie den Assistenten abgeschlossen haben, können Sie die Auflistung der Datasetfelder im Berichtsdatenbereich anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="dd9f6-177">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="dd9f6-178">1C.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-178">1c.</span></span> <span data-ttu-id="dd9f6-179">Gruppieren von Daten im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="dd9f6-180">Durch das Auswählen von Feldern für die Gruppierung entwerfen Sie eine Tabelle mit Zeilen und Spalten, in denen Detaildaten und aggregierte Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="dd9f6-181">So gruppieren Sie Daten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="dd9f6-182">Ziehen Sie auf der Seite **Felder anordnen** das Feld Product in **Werte**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-183">Ziehen Sie „Quantity“ in **Werte** , und platzieren Sie es unter „Product“.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="dd9f6-184">"Quantity" wird automatisch von der Sum-Funktion aggregiert, dem Standardaggregat für numerische Felder.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="dd9f6-185">Der Wert ist "[Sum(Quantity)]".</span><span class="sxs-lookup"><span data-stu-id="dd9f6-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="dd9f6-186">Sie können die Dropdownliste öffnen, um die anderen verfügbaren Aggregatfunktionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="dd9f6-187">Ändern Sie die Aggregatfunktion nicht.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="dd9f6-188">Ziehen Sie „Sales“ in **Werte** , und fügen Sie dieses Feld unter „[Sum(Quantity)]“ ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="dd9f6-189">"Sales" wird von der Sum-Funktion aggregiert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="dd9f6-190">Der Wert ist "[Sum(Sales)]".</span><span class="sxs-lookup"><span data-stu-id="dd9f6-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="dd9f6-191">In Schritt 1, 2 und 3 werden die Daten angegeben, die in der Tabelle angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="dd9f6-192">Ziehen Sie „SalesDate“ in **Zeilengruppen**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="dd9f6-193">Ziehen Sie „Subcategory“ in **Zeilengruppen** , und fügen Sie dieses Feld unter „SalesDate“ ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="dd9f6-194">Durch die Schritte 4 und 5 werden die Werte für die Felder zuerst nach Datum und dann nach Produktunterkategorie für dieses Datum geordnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="dd9f6-195">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="dd9f6-196">1D.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-196">1d.</span></span> <span data-ttu-id="dd9f6-197">Hinzufügen von Teilergebnis- und Ergebniszeilen im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="dd9f6-198">Nachdem Sie Gruppen erstellt haben, können Sie Zeilen hinzufügen und formatieren, in denen Aggregatwerte für die Felder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="dd9f6-199">Sie können auswählen, ob alle Daten angezeigt werden oder der Benutzer gruppierte Daten interaktiv erweitern und reduzieren kann.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="dd9f6-200">So fügen Sie Teilergebnisse und Summen hinzu</span><span class="sxs-lookup"><span data-stu-id="dd9f6-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="dd9f6-201">Vergewissern Sie sich, dass auf der Seite **Layout auswählen** unter **Optionen die Option** **Teil-und Gesamtsummen anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="dd9f6-202">Überprüfen Sie, ob **Als Block, Teilergebnis unterhalb** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="dd9f6-203">Im Vorschaubereich des Assistenten wird eine Tabelle mit fünf Zeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="dd9f6-204">Bei der Ausführung des Berichts wird jede Zeile wie folgt angezeigt:</span><span class="sxs-lookup"><span data-stu-id="dd9f6-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="dd9f6-205">Die erste Zeile wird einmal wiederholt, damit Spaltenüberschriften in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="dd9f6-206">Die zweite Zeile wird einmal für jedes Zeilenelement im Verkaufsauftrag wiederholt. In dieser Zeile werden Produktname, Bestellmenge und Zeilensumme angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="dd9f6-207">Die dritte Zeile wird einmal für jeden Verkaufsauftrag wiederholt. In dieser Zeile werden die Teilergebnisse für jeden Auftrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="dd9f6-208">Die vierte Zeile wird einmal für jedes Bestelldatum wiederholt. In ihr werden Zwischensummen pro Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="dd9f6-209">Die fünfte Zeile wird einmal wiederholt, damit Gesamtsummen in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="dd9f6-210">Deaktivieren Sie die Option **Gruppen erweitern/reduzieren**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="dd9f6-211">In diesem Lernprogramm enthält der erstellte Bericht keine Drilldownfunktion, mit der ein Benutzer eine übergeordnete Gruppenhierarchie einblenden kann, um untergeordnete Gruppenzeilen und Detailzeilen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="dd9f6-212">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="dd9f6-213">1E.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-213">1e.</span></span> <span data-ttu-id="dd9f6-214">Auswählen eines Formats im Tabellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="dd9f6-215">Ein Format dient zum Angeben eines Schriftschnitts, einer Farbpalette und einer Rahmenart.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="dd9f6-216">So geben Sie ein Tabellenformat an</span><span class="sxs-lookup"><span data-stu-id="dd9f6-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="dd9f6-217">Wählen Sie auf der Seite Format **auswählen** im Bereich Stile die Option Ozean aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="dd9f6-218">Im Vorschaubereich wird ein Beispiel für die Tabelle mit diesem Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="dd9f6-219">Sie können auf die anderen Formate klicken, um entsprechende Beispiele anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="dd9f6-220">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="dd9f6-221">Die Tabelle wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-221">The table is added to the design surface.</span></span> <span data-ttu-id="dd9f6-222">Die Tabelle enthält 5 Spalten und 5 Zeilen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="dd9f6-223">Im Bereich "Zeilengruppen" werden drei Zeilengruppen angezeigt: "SalesDate", "Subcategory" und "Details".</span><span class="sxs-lookup"><span data-stu-id="dd9f6-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="dd9f6-224">Detaildaten sind alle Daten, die von der Datasetabfrage abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="dd9f6-225">2. Formatieren von Daten als Währung</span><span class="sxs-lookup"><span data-stu-id="dd9f6-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="dd9f6-226">Die Zusammenfassungsdaten für das Feld "Sales" werden standardmäßig als eine Zahl im Standardzahlenformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="dd9f6-227">Formatieren Sie das Feld, um die Zahl als Währung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-227">Format it to display the number as currency.</span></span> <span data-ttu-id="dd9f6-228">Ändern Sie die Einstellung der Option **Platzhalterformate** , um formatierte Textfelder und Platzhaltertext als Beispielwerte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="dd9f6-229">So formatieren Sie ein Währungsfeld</span><span class="sxs-lookup"><span data-stu-id="dd9f6-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="dd9f6-230">Klicken Sie auf **Entwurf** , um zur Entwurfs Ansicht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="dd9f6-231">Klicken Sie auf die Zelle in der zweiten Zeile (unter der Zeile mit den Spaltenüberschriften) in der Spalte "Sales", und ziehen Sie den Mauszeiger nach unten, um alle Zellen auszuwählen, die `[Sum(Sales)]`enthalten.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="dd9f6-232">Klicken Sie auf der Registerkarte **Stamm** in der Gruppe **Zahl** auf die Schaltfläche **Währung** .</span><span class="sxs-lookup"><span data-stu-id="dd9f6-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="dd9f6-233">Die Zellen ändern sich, um die formatierte Währung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="dd9f6-234">Wenn Sie das Gebietsschema „Deutsch (Deutschland)“ verwenden, lautet der Standardbeispieltext [**12,345.00€**].</span><span class="sxs-lookup"><span data-stu-id="dd9f6-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="dd9f6-235">Wenn kein Beispiel Währungswert angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalter** Formate und dann auf **Beispiel Werte**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="dd9f6-236">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="dd9f6-237">Die Zusammenfassungswerte für "Sales" werden als Währung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="dd9f6-238">3. Formatieren von Daten als Datum</span><span class="sxs-lookup"><span data-stu-id="dd9f6-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="dd9f6-239">Im Feld "SalesDate" werden standardmäßig sowohl Datums- als auch Zeitangaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="dd9f6-240">Durch entsprechende Formatierung kann auch nur das Datum angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="dd9f6-241">So formatieren Sie ein Datumsfeld als Standardformat</span><span class="sxs-lookup"><span data-stu-id="dd9f6-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="dd9f6-242">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dd9f6-243">Klicken Sie auf die Zelle, die `[SalesDate]`enthält.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="dd9f6-244">Wählen Sie im Menüband auf der Registerkarte **Startseite** in der Gruppe **Zahl** in der Dropdown Liste **Datum**aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="dd9f6-245">In der Zelle wird das Beispieldatum **[31.01.2000]** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="dd9f6-246">Falls kein Beispieldatum angezeigt wird, klicken Sie in der Gruppe **Zahlen** auf **Platzhalterformate** und anschließend auf **Beispielwerte**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="dd9f6-247">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="dd9f6-248">Die "SalesDate"-Werte werden im Standarddatumsformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="dd9f6-249">So ändern Sie das Datumsformat in ein benutzerdefiniertes Format</span><span class="sxs-lookup"><span data-stu-id="dd9f6-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="dd9f6-250">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dd9f6-251">Klicken Sie auf die Zelle, die `[SalesDate]`enthält.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="dd9f6-252">Klicken Sie auf der Registerkarte **Startseite** in der Gruppe **Zahl** auf das Dialogfeld Start Programm.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="dd9f6-253">Das Startprogramm ist der kleine Pfeil in der rechten Ecke der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="dd9f6-254">Das Dialogfeld **Textfeldeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="dd9f6-255">Prüfen Sie im Bereich Kategorie, ob **Datum** gewählt ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="dd9f6-256">Wählen Sie im Bereich **Typ** die Option **31. Januar 2000**aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="dd9f6-257">Die Zelle zeigt das Beispieldatum an: **[31. Januar 2000]**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="dd9f6-258">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="dd9f6-259">Der "SalesDate"-Wert wird mit dem Namen des Monats anstelle der Zahl für den Monat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="dd9f6-260">4. Ändern der Spaltenbreite</span><span class="sxs-lookup"><span data-stu-id="dd9f6-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="dd9f6-261">Standardmäßig enthält jede Zelle in einer Tabelle ein Textfeld.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="dd9f6-262">Textfelder werden beim Rendern der Seite entsprechend dem anzuzeigenden Text vertikal erweitert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="dd9f6-263">Im gerenderten Bericht werden alle Zeilen auf die Höhe des größten gerenderten Textfelds in der Zeile vergrößert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="dd9f6-264">Die Höhe der Zeile auf der Entwurfsoberfläche hat keinen Einfluss auf die Höhe der Zeile im gerenderten Bericht.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="dd9f6-265">Um die Höhe der Zeilen zu reduzieren, vergrößern Sie die Spaltenbreite, sodass der erwartete Inhalt der Textfelder in der Spalte in einer Zeile untergebracht werden kann.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="dd9f6-266">So ändern Sie die Breite von Tabellenspalten</span><span class="sxs-lookup"><span data-stu-id="dd9f6-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="dd9f6-267">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dd9f6-268">Klicken Sie auf die Tabelle, damit die Spalten- und Zeilenhandles über und neben der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="dd9f6-269">Die grauen Balken oberhalb und neben der Tabelle stellen die Spalten- und Zeilenhandles dar.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="dd9f6-270">Zeigen Sie auf die Zeile zwischen Spaltenhandles, sodass sich der Cursor in einen Doppelpfeil ändert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="dd9f6-271">Ziehen Sie die Spalten auf die gewünschte Größe.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="dd9f6-272">Beispiel: Erweitern Sie die Spalte für Produkt, damit der Produktname auf einer Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="dd9f6-273">Klicken Sie auf **Ausführen** , um den Bericht in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="dd9f6-274">5. Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="dd9f6-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="dd9f6-275">Ein Berichtstitel wird oben im Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="dd9f6-276">Sie können den Berichtstitel in eine Berichtskopfzeile einfügen oder, wenn der Bericht keine Kopfzeile enthält, in einem Textfeld am oberen Rand des Berichtshauptteils.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="dd9f6-277">In diesem Lernprogramm verwenden Sie das Textfeld, das automatisch am oberen Rand des Berichtshauptteils platziert wird.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="dd9f6-278">Die Darstellung des Texts kann weiter verbessert werden, indem andere Schriftschnitte, Größen und Farben für Ausdrücke und einzelne Zeichen des Texts angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="dd9f6-279">Weitere Informationen finden Sie unter [Formatieren von Text in einem Textfeld (Berichts-Generator und SSRS)](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="dd9f6-280">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="dd9f6-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="dd9f6-281">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-282">Geben Sie **Product Sales**ein, und klicken Sie anschließend außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="dd9f6-283">Klicken Sie mit der rechten Maustaste auf das Textfeld, das **Product Sales** enthält, und klicken Sie auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="dd9f6-284">Klicken Sie im Dialogfeld **Textfeldeigenschaften** auf **Schriftart**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="dd9f6-285">Wählen Sie in der Liste **Schriftgrad** den Eintrag **18pt**aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="dd9f6-286">Wählen Sie in der Liste **Farbe** die Option **Kornblumenblau**aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="dd9f6-287">Wählen Sie **Fett**aus.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="dd9f6-288">6. Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="dd9f6-288">6. Save the Report</span></span>  
 <span data-ttu-id="dd9f6-289">Speichern Sie den Bericht auf einem Berichtsserver oder auf Ihrem Computer.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="dd9f6-290">Wenn Sie den Bericht nicht auf dem Berichtsserver speichern, ist eine Reihe von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionen nicht verfügbar, z. B. Berichtsteile und Unterberichte.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="dd9f6-291">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="dd9f6-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="dd9f6-292">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-293">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="dd9f6-294">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="dd9f6-295">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="dd9f6-296">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="dd9f6-297">Ersetzen Sie im Feld **Name**den Standardnamen durch **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="dd9f6-298">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="dd9f6-299">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-299">The report is saved to the report server.</span></span> <span data-ttu-id="dd9f6-300">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="dd9f6-301">So speichern Sie den Bericht auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="dd9f6-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="dd9f6-302">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-303">Klicken Sie auf **Desktop**, **Eigene Dokumente**oder **Computer**, und navigieren Sie zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="dd9f6-304">Ersetzen Sie im Feld **Name**den Standardnamen durch **Product Sales**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="dd9f6-305">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="dd9f6-306">7. Exportieren des Berichts</span><span class="sxs-lookup"><span data-stu-id="dd9f6-306">7. Export the Report</span></span>  
 <span data-ttu-id="dd9f6-307">Berichte können in verschiedene Formate exportiert werden, z. B. das Microsoft Excel- und CSV-Format.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="dd9f6-308">Weitere Informationen finden Sie unter [Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="dd9f6-309">In diesem Lernprogramm exportieren Sie den Bericht nach Excel, und Sie legen eine Eigenschaft für den Bericht fest, um einen benutzerdefinierten Namen für das Arbeitsmappenregister anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="dd9f6-310">So geben Sie den Namen des Arbeitsmappenregisters an</span><span class="sxs-lookup"><span data-stu-id="dd9f6-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="dd9f6-311">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="dd9f6-312">Klicken Sie an einer beliebigen Stelle außerhalb des Berichts.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="dd9f6-313">. Suchen Sie im Eigenschaften Bereich die initialpagename-Eigenschaft, und geben Sie **Product Sales Excel**ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dd9f6-314">Wenn der Bereich Eigenschaften nicht sichtbar ist, klicken Sie im Menüband auf die Registerkarte Ansicht, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="dd9f6-315">So exportieren Sie einen Bericht nach Excel</span><span class="sxs-lookup"><span data-stu-id="dd9f6-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="dd9f6-316">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="dd9f6-317">. Klicken Sie im Menüband auf **exportieren**, und klicken Sie dann auf **Excel**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="dd9f6-318">Das Dialogfeld **Speichern unter** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="dd9f6-319">Navigieren Sie zum Ordner **Dokumente** .</span><span class="sxs-lookup"><span data-stu-id="dd9f6-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="dd9f6-320">Geben Sie im Textfeld **Dateiname den Namen** **Product Sales Excel**ein.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="dd9f6-321">Vergewissern Sie sich, dass der Dateityp **Excel-Arbeitsmappe**ist.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="dd9f6-322">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="dd9f6-323">So zeigen Sie den Bericht in Excel an</span><span class="sxs-lookup"><span data-stu-id="dd9f6-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="dd9f6-324">Öffnen Sie den Ordner **Dokumente** , und doppelklicken Sie auf \*\*Product Sales #b0 \*\*.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="dd9f6-325">Überprüfen Sie, ob der Name des Arbeitsmappenregisters **Product Sales Excel**lautet.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dd9f6-326">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd9f6-326">Next Steps</span></span>  
 <span data-ttu-id="dd9f6-327">Damit ist die exemplarische Vorgehensweise für das Erstellen eines einfachen Tabellenberichts abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dd9f6-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="dd9f6-328">Weitere Informationen zu Tabellen finden Sie unter [Tabellen, Matrizen und Listen (Berichts-Generator und SSRS)](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="dd9f6-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd9f6-329">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd9f6-329">See Also</span></span>  
 <span data-ttu-id="dd9f6-330">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="dd9f6-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="dd9f6-331">Berichts-Generator in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="dd9f6-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
