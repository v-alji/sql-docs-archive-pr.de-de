---
title: 'Tutorial: Einführung in Ausdrücke | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722426"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="23461-102">Lernprogramm: Einführung in Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="23461-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="23461-103">Mit Ausdrücken können Sie leistungsfähige und flexible Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="23461-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="23461-104">In diesem Lernprogramm erfahren Sie, wie Sie Ausdrücke mit allgemeinen Funktionen und Operatoren erstellen und implementieren.</span><span class="sxs-lookup"><span data-stu-id="23461-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="23461-105">Verwenden Sie das Dialogfeld **Ausdruck** , um Ausdrücke zu schreiben, die namens Werte verketten, Werte in einem separaten Dataset suchen, verschiedene Bilder auf der Grundlage von Feldwerten anzeigen usw.</span><span class="sxs-lookup"><span data-stu-id="23461-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="23461-106">Der Bericht ist ein Balkenbericht mit abwechselnden Zeilenfarben (Weiß und eine beliebige andere Farbe).</span><span class="sxs-lookup"><span data-stu-id="23461-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="23461-107">Der Bericht enthält einen Parameter zur Auswahl der Farbe für alle Zeilen, die nicht weiß dargestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="23461-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="23461-108">Die folgende Abbildung zeigt einen Bericht, der mit dem Bericht vergleichbar ist, den Sie erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="23461-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="23461-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="23461-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="23461-110">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="23461-110">What You Will Learn</span></span>  
 <span data-ttu-id="23461-111">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="23461-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="23461-112">Erstellen eines Tabellenberichts und eines Datasets mit dem Tabellen- oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="23461-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="23461-113">Aktualisieren der Standardnamen der Datenquelle und des Datensets</span><span class="sxs-lookup"><span data-stu-id="23461-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="23461-114">Anzeigen des Vornamens, des Anfangsbuchstabens des zweiten Vornamens und des Nachnamens</span><span class="sxs-lookup"><span data-stu-id="23461-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="23461-115">Verwenden von Bildern für die Anzeige des Geschlechts</span><span class="sxs-lookup"><span data-stu-id="23461-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="23461-116">Suchen des CountryRegion-Namens</span><span class="sxs-lookup"><span data-stu-id="23461-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="23461-117">Ermitteln der vergangenen Tage seit dem letzten Kauf</span><span class="sxs-lookup"><span data-stu-id="23461-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="23461-118">Verwenden eines Indikators zur Anzeige des Umsatzvergleichs</span><span class="sxs-lookup"><span data-stu-id="23461-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="23461-119">Erstellen des Berichts als "grüner Balken Bericht"</span><span class="sxs-lookup"><span data-stu-id="23461-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="23461-120">Weitere optionale Schritte</span><span class="sxs-lookup"><span data-stu-id="23461-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="23461-121">Formatieren der Datumsspalte</span><span class="sxs-lookup"><span data-stu-id="23461-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="23461-122">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="23461-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="23461-123">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="23461-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="23461-124">Geschätzte Zeit zum Bearbeiten dieses Lernprogramms: 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="23461-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23461-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23461-125">Requirements</span></span>  
 <span data-ttu-id="23461-126">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="23461-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="23461-127">1. Erstellen eines Tabellen Berichts und eines Datasets mit dem Tabellen-oder Matrix-Assistenten</span><span class="sxs-lookup"><span data-stu-id="23461-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="23461-128">Erstellen Sie einen Tabellenbericht, eine Datenquelle und ein Dataset.</span><span class="sxs-lookup"><span data-stu-id="23461-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="23461-129">Für den Entwurf der Tabelle werden nur einige wenige Felder verwendet.</span><span class="sxs-lookup"><span data-stu-id="23461-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="23461-130">Nach Fertigstellung des Assistenten werden Sie manuell Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="23461-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="23461-131">Mit dem Assistenten können Sie die Tabelle einfach gestalten und formatieren.</span><span class="sxs-lookup"><span data-stu-id="23461-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23461-132">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="23461-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="23461-133">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="23461-133">This makes the query quite long.</span></span> <span data-ttu-id="23461-134">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="23461-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="23461-135">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="23461-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23461-136">In diesem Lernprogramm werden die Schritte für den Assistenten in einem Verfahren zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="23461-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="23461-137">Im ersten Tutorial dieser Reihe erhalten Sie detaillierte Anweisungen zum Navigieren zu einem Berichtsserver, zum Auswählen einer Datenquelle sowie zum Erstellen eines Datasets: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="23461-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="23461-138">So erstellen Sie einen neuen Tabellenbericht</span><span class="sxs-lookup"><span data-stu-id="23461-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="23461-139">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, klicken Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="23461-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="23461-140">Das Dialogfeld " **Getting Started** " wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23461-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23461-141">Wenn das Dialogfeld " **Getting Started** " nicht angezeigt wird, klicken Sie auf der Schaltfläche " **Berichts-Generator** " auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="23461-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23461-142">Wenn Sie die ClickOnce-Version von Berichts-Generator bevorzugen, öffnen Sie Berichts-Manager, und klicken Sie auf **Berichts-Generator**, oder wechseln Sie zu einer SharePoint-Website, auf der Reporting Services Inhaltstypen wie Berichte aktiviert sind, und klicken Sie im Menü **Neues Dokument** auf der Registerkarte **Dokumente** einer freigegebenen Dokumentbibliothek auf **Berichts-Generator Bericht** .</span><span class="sxs-lookup"><span data-stu-id="23461-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="23461-143">Vergewissern Sie sich, dass im linken Bereich **Neuer Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="23461-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="23461-144">Klicken Sie im rechten Bereich auf **Tabellen- oder Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="23461-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="23461-145">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**.</span><span class="sxs-lookup"><span data-stu-id="23461-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="23461-146">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23461-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="23461-147">Wählen Sie auf der Seite **Verbindung mit einer Datenquelle auswählen** eine Datenquelle vom Typ **SQL Server**aus.</span><span class="sxs-lookup"><span data-stu-id="23461-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="23461-148">Wählen Sie in der Liste eine Datenquelle aus, oder navigieren Sie zum Berichtsserver, um eine Datenquelle auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="23461-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="23461-149">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23461-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="23461-150">Klicken Sie auf der Seite **Abfrage entwerfen** auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="23461-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="23461-151">Fügen Sie die folgende Abfrage in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="23461-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="23461-152">Die Abfrage spezifiziert Spaltennamen mit Geburtsname, Vorname, Nachname, Bundesland oder Kanton, Bezeichner für Land bzw. Region, Geschlecht sowie Käufe des laufenden Jahrs.</span><span class="sxs-lookup"><span data-stu-id="23461-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="23461-153">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="23461-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="23461-154">Das Resultset umfasst 20 Zeilen mit Daten und umfasst folgenden Spalten: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase und LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="23461-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="23461-155">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23461-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="23461-156">Ziehen Sie auf der Seite **Felder anordnen** die folgenden Felder in der angegebenen Reihenfolge aus der Liste **Verfügbare Felder** in die Liste **Werte** .</span><span class="sxs-lookup"><span data-stu-id="23461-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="23461-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="23461-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="23461-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="23461-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="23461-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="23461-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="23461-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="23461-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="23461-161">Da CountryRegionID und YTDPurchase numerische Daten enthalten, wird die SUM-Aggregatfunktion standardmäßig auf diese Felder angewendet.</span><span class="sxs-lookup"><span data-stu-id="23461-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23461-162">Die Felder FirstName und LastName werden nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="23461-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="23461-163">Sie werden in einem späteren Schritt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="23461-164">Klicken Sie in der Liste **Werte** mit der rechten Maustaste, `CountryRegionID` und klicken Sie auf die Option **Sum** .</span><span class="sxs-lookup"><span data-stu-id="23461-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="23461-165">Sum wird nicht länger auf CountryRegionID angewendet.</span><span class="sxs-lookup"><span data-stu-id="23461-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="23461-166">Klicken Sie in der Liste **Werte** mit der rechten Maustaste auf **YTDPurchase** und klicken Sie anschließend auf die Option **Sum** .</span><span class="sxs-lookup"><span data-stu-id="23461-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="23461-167">Sum wird nicht länger auf YTDPurchase angewendet.</span><span class="sxs-lookup"><span data-stu-id="23461-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="23461-168">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23461-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="23461-169">Klicken Sie auf der Seite **Layout auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="23461-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="23461-170">Klicken Sie auf der Seite Format **auswählen** auf **Slate**, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="23461-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="23461-171">2. Aktualisieren der Standardnamen der Datenquelle und des Datasets</span><span class="sxs-lookup"><span data-stu-id="23461-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="23461-172">So aktualisieren Sie den Standardnamen der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="23461-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="23461-173">Erweitern Sie im Bereich „Berichtsdaten“ den Eintrag **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="23461-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="23461-174">Klicken Sie mit der rechten Maustaste auf **DataSource1** und anschließend auf **Datenquelleneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="23461-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="23461-175">Geben Sie im Feld **Name** Folgendes ein: **Datenquelle_für_Ausdrücke**</span><span class="sxs-lookup"><span data-stu-id="23461-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="23461-176">So aktualisieren Sie den Standardnamen des Datasets</span><span class="sxs-lookup"><span data-stu-id="23461-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="23461-177">Erweitern Sie im Bereich „Berichtsdaten“ den Eintrag **Datasets**.</span><span class="sxs-lookup"><span data-stu-id="23461-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="23461-178">Klicken Sie mit der rechten Maustaste auf **DataSet1** und anschließend auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="23461-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="23461-179">Geben Sie im Feld **Name** Folgendes ein: **Ausdrücke**</span><span class="sxs-lookup"><span data-stu-id="23461-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="23461-180">3. Anzeigen von Vorname, ursprünglicher Name und Nachname</span><span class="sxs-lookup"><span data-stu-id="23461-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="23461-181">Verwenden Sie die **Left**-Funktion und den **Concatenate (Verketten)** (**&**)-Operator in einem Ausdruck, um einen Namen mit den Anfangsbuchstaben des zweiten Vornamens und dem Nachnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23461-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="23461-182">Sie können den Ausdruck Schritt für Schritt erstellen oder diesen Teil der Prozedur überspringen und den Ausdruck aus dem Tutorial in das Dialogfeld **Ausdruck** kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="23461-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="23461-183">So fügen Sie die Spalte "Name" hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="23461-184">Klicken Sie mit der rechten Maustaste auf die Spalte **StateProvince** , zeigen Sie auf **Spalte einfügen**und klicken Sie auf **Links**.</span><span class="sxs-lookup"><span data-stu-id="23461-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="23461-185">Links von der Spalte **StateProvince** wird eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="23461-186">Klicken Sie auf den Titel der neuen Spalte und geben Sie **Name** ein</span><span class="sxs-lookup"><span data-stu-id="23461-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="23461-187">Klicken Sie mit der rechten Maustaste in die Datenzelle der Spalte **Name** und klicken Sie auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="23461-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="23461-188">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**und klicken Sie anschließend auf **Text**.</span><span class="sxs-lookup"><span data-stu-id="23461-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="23461-189">Doppelklicken Sie in der Liste **Element** auf **Left**.</span><span class="sxs-lookup"><span data-stu-id="23461-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="23461-190">Die Funktion **Left** wird dem Ausdruck hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="23461-191">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="23461-192">Doppelklicken Sie in der Liste **Werte** auf **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="23461-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="23461-193">Geben Sie **, 1)** ein</span><span class="sxs-lookup"><span data-stu-id="23461-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="23461-194">Der Ausdruck extrahiert ein Zeichen aus dem Wert **FirstName** , beginnend von links.</span><span class="sxs-lookup"><span data-stu-id="23461-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="23461-195">Geben Sie **& "" ein &**</span><span class="sxs-lookup"><span data-stu-id="23461-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="23461-196">Doppelklicken Sie in der Liste **Werte** auf **LastName**.</span><span class="sxs-lookup"><span data-stu-id="23461-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="23461-197">Der vollständige Ausdruck lautet wie folgt: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="23461-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="23461-198">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23461-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="23461-199">4. Verwenden von Bildern zum Anzeigen von Geschlecht</span><span class="sxs-lookup"><span data-stu-id="23461-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="23461-200">Verwenden Sie Bilder, um das Geschlecht einer Person anzuzeigen, und weisen Sie für den Fall unbekannter Werte ein drittes Bild zu.</span><span class="sxs-lookup"><span data-stu-id="23461-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="23461-201">Sie fügen dem Bericht drei versteckte Bilder und eine neue Spalte für die Bildanzeige hinzu. Sie legen dann fest, welches Bild auf Grundlage des Werts im Feld "Geschlecht" in der Spalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="23461-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="23461-202">Um eine Farbe auf die Tabellenzelle anzuwenden, die das Bild enthält, wenn Sie aus dem Bericht einen Balkenbericht machen, fügen Sie zuerst ein Rechteck hinzu und dann das Bild in das Rechteck ein.</span><span class="sxs-lookup"><span data-stu-id="23461-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="23461-203">Sie benötigen das Rechteck, da Sie einem Rechteck eine Hintergrundfarbe zuordnen können, nicht aber einem Bild.</span><span class="sxs-lookup"><span data-stu-id="23461-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="23461-204">Das Lernprogramm verwendet Bilder, die mit Windows ausgeliefert werden, Sie können aber auch jedes beliebige andere Bild verwenden.</span><span class="sxs-lookup"><span data-stu-id="23461-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="23461-205">Sie verwenden eingebettete Bilder, die nicht auf Ihrem Computer oder dem Berichtsserver installiert sein müssen.</span><span class="sxs-lookup"><span data-stu-id="23461-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="23461-206">So fügen Sie dem Berichtstext Bilder hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="23461-207">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-208">Klicken Sie auf der Registerkarte **Einfügen** des Menübands auf **Bild** und anschließend auf den Berichtstext unterhalb der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="23461-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="23461-209">Das Dialogfeld **Bildeigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23461-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="23461-210">Klicken Sie auf **Importieren**, und navigieren Sie zu C:\Benutzer\Öffentlich\Öffentliche Bilder\Beispielbilder.</span><span class="sxs-lookup"><span data-stu-id="23461-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="23461-211">Klicken Sie auf „Pinguine.JPG“ und anschließend auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="23461-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="23461-212">Klicken Sie im Dialogfeld **Bildeigenschaften** auf **Sichtbarkeit** und anschließend auf **Ausblenden**.</span><span class="sxs-lookup"><span data-stu-id="23461-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="23461-213">Wiederholen Sie die Schritte 2 bis 5, diesmal aber mit dem Bild "Koala.JPG".</span><span class="sxs-lookup"><span data-stu-id="23461-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="23461-214">Wiederholen Sie die Schritte 2 bis 5, diesmal aber mit dem Bild "Tulpen.JPG".</span><span class="sxs-lookup"><span data-stu-id="23461-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="23461-215">So fügen Sie die Spalte "Geschlecht" hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="23461-216">Klicken Sie mit der rechten Maustaste auf die Spalte **Name**, zeigen Sie auf **Spalte einfügen** und klicken Sie anschließend auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="23461-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="23461-217">Rechts von der Spalte **Name** wird eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="23461-218">Klicken Sie auf den Titel der neuen Spalte und geben Sie **Geschlecht** ein</span><span class="sxs-lookup"><span data-stu-id="23461-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="23461-219">So fügen Sie ein Rechteck hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="23461-220">Klicken Sie auf der Registerkarte **Einfügen** im Menüband auf **Rechteck** und anschließend in die Datenzelle der Spalte **Geschlecht**.</span><span class="sxs-lookup"><span data-stu-id="23461-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="23461-221">Der Zelle wird ein Rechteck hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="23461-222">So fügen Sie dem Rechteck ein Bild hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="23461-223">Klicken Sie mit der rechten Maustaste auf das Rechteck, zeigen Sie auf **Einsetzen** und klicken Sie anschließend auf **Bild**.</span><span class="sxs-lookup"><span data-stu-id="23461-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="23461-224">Klicken Sie im Dialogfeld **Bildeigenschaften** auf den Nach unten-Pfeil neben **Dieses Bild verwenden** und wählen Sie eines der hinzugefügten Bilder aus, z.B. „Pinguine.JPG“.</span><span class="sxs-lookup"><span data-stu-id="23461-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="23461-225">So verwenden Sie Bilder für die Anzeige des Geschlechts</span><span class="sxs-lookup"><span data-stu-id="23461-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="23461-226">Klicken Sie mit der rechten Maustaste auf das Bild in der Datenzelle in der Spalte **Geschlecht** und anschließend auf **Bildeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="23461-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="23461-227">Klicken Sie im Dialogfeld **Bildeigenschaften** auf die Ausdrucksschaltfläche **fx** neben dem Textfeld **Dieses Bild verwenden**.</span><span class="sxs-lookup"><span data-stu-id="23461-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="23461-228">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen** und klicken Sie auf **Programmfluss**.</span><span class="sxs-lookup"><span data-stu-id="23461-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="23461-229">Doppelklicken Sie in der Liste **Element** auf **Switch**.</span><span class="sxs-lookup"><span data-stu-id="23461-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="23461-230">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="23461-231">Doppelklicken Sie in der Liste **Werte** auf **Geschlecht**.</span><span class="sxs-lookup"><span data-stu-id="23461-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="23461-232">Geben Sie **="Männlich", "Koala",** ein</span><span class="sxs-lookup"><span data-stu-id="23461-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="23461-233">Doppelklicken Sie in der Liste **Werte** auf **Geschlecht**.</span><span class="sxs-lookup"><span data-stu-id="23461-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="23461-234">Geben Sie **="Weiblich", "Pinguine",** ein</span><span class="sxs-lookup"><span data-stu-id="23461-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="23461-235">Doppelklicken Sie in der Liste **Werte** auf **Geschlecht**.</span><span class="sxs-lookup"><span data-stu-id="23461-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="23461-236">Geben Sie **="Unbekannt", "Tulpen")** ein</span><span class="sxs-lookup"><span data-stu-id="23461-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="23461-237">Der vollständige Ausdruck lautet wie folgt: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="23461-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="23461-238">Klicken Sie auf **OK**, um das Dialogfeld **Bildeigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="23461-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="23461-239">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23461-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="23461-240">5. Suchen Sie den CountryRegion-Namen.</span><span class="sxs-lookup"><span data-stu-id="23461-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="23461-241">Erstellen Sie das CountryRegion-Dataset, und verwenden Sie die **Lookup**-Funktion, um den Namen des Lands/der Region anstelle des Bezeichners des Lands/der Region anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23461-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="23461-242">So erstellen Sie das CountryRegion-Dataset</span><span class="sxs-lookup"><span data-stu-id="23461-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="23461-243">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-244">Klicken Sie im Berichtsdaten Bereich auf **neu** , und klicken Sie dann auf **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="23461-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="23461-245">Klicken Sie auf **Ein in den eigenen Bericht eingebettetes Dataset verwenden**.</span><span class="sxs-lookup"><span data-stu-id="23461-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="23461-246">Wählen Sie in der Liste **Datenquelle** die Option „Datenquelle_für_Ausdrücke“.</span><span class="sxs-lookup"><span data-stu-id="23461-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="23461-247">Geben Sie im Feld **Name** Folgendes ein: **CountryRegion**</span><span class="sxs-lookup"><span data-stu-id="23461-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="23461-248">Überprüfen Sie, ob der Abfragetyp **Text** ausgewählt ist und klicken Sie auf **Abfrage-Designer**.</span><span class="sxs-lookup"><span data-stu-id="23461-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="23461-249">Klicken Sie auf **Als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="23461-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="23461-250">Kopieren Sie die folgende Abfrage, und fügen Sie sie in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="23461-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="23461-251">Klicken Sie auf **Ausführen** (**!**), um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="23461-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="23461-252">Abfrage-Ergebnisse sind die Land/Region-Bezeichner und -Namen.</span><span class="sxs-lookup"><span data-stu-id="23461-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="23461-253">Klicken Sie auf **OK** , um das Dialogfeld **Dataseteigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="23461-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="23461-254">So schlagen Sie Werte im CountryRegion-Dataset nach</span><span class="sxs-lookup"><span data-stu-id="23461-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="23461-255">Klicken Sie auf den Spaltentitel **Country Region ID** und löschen Sie den Text „ID“.</span><span class="sxs-lookup"><span data-stu-id="23461-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="23461-256">Klicken Sie mit der rechten Maustaste in die Datenzelle der Spalte **Country Region** und klicken Sie auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="23461-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="23461-257">Löschen Sie den Ausdruck bis auf das Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="23461-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="23461-258">Der verbleibende Ausdruck lautet: `=`</span><span class="sxs-lookup"><span data-stu-id="23461-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="23461-259">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**, und klicken Sie anschließend auf **Sonstiges**.</span><span class="sxs-lookup"><span data-stu-id="23461-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="23461-260">Doppelklicken Sie in der Liste **Element** auf **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="23461-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="23461-261">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="23461-262">Doppelklicken Sie in der Liste **Werte** auf `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="23461-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="23461-263">Wenn der Cursor nicht bereits unmittelbar nach `CountryRegionID.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="23461-264">Löschen Sie die rechte Klammer und geben Sie anschließend **,Fields!ID.value, Fields!CountryRegion.value, „CountryRegion“)** ein</span><span class="sxs-lookup"><span data-stu-id="23461-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="23461-265">Der vollständige Ausdruck lautet wie folgt: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="23461-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="23461-266">Die Syntax der **Lookup**-Funktion spezifiziert eine Suche zwischen CountryRegionID und ID im CountryRegion-Dataset, die den CountryRegion-Wert zurückgibt, der sich ebenfalls im CountryRegion-Dataset befindet.</span><span class="sxs-lookup"><span data-stu-id="23461-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="23461-267">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23461-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="23461-268">6. Anzahl der Tage seit dem letzten Kauf</span><span class="sxs-lookup"><span data-stu-id="23461-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="23461-269">Fügen Sie eine Spalte hinzu, und verwenden Sie anschließend die **Now** -Funktion oder die `ExecutionTime` integrierte globale Variable, um die Anzahl der Tage seit dem letzten Einkauf einer Person zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="23461-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="23461-270">So fügen Sie die Spalte "Vor (n) Tagen)" hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="23461-271">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-272">Klicken Sie mit der rechten Maustaste auf **Last Purchase** , zeigen Sie auf **Spalte einfügen**und klicken Sie auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="23461-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="23461-273">Rechts von der Spalte **Letzter Kauf** wird eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="23461-274">Geben Sie in der Spaltenüberschrift **Vor (n) Tagen**ein</span><span class="sxs-lookup"><span data-stu-id="23461-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="23461-275">Klicken Sie mit der rechten Maustaste in die Datenzelle der Spalte **Vor (n) Tagen** und klicken Sie auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="23461-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="23461-276">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**, und klicken Sie anschließend auf **Datum & Uhrzeit**.</span><span class="sxs-lookup"><span data-stu-id="23461-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="23461-277">Doppelklicken Sie in der Liste **Elemente** auf **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="23461-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="23461-278">Wenn der Cursor nicht bereits unmittelbar nach `DateDiff(` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="23461-279">Geben Sie **„d“,** ein.</span><span class="sxs-lookup"><span data-stu-id="23461-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="23461-280">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="23461-281">Doppelklicken Sie in der Liste **Werte** auf **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="23461-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="23461-282">Wenn der Cursor nicht bereits unmittelbar nach `Fields!LastPurchase.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="23461-283">Geben Sie ein **,**</span><span class="sxs-lookup"><span data-stu-id="23461-283">Type **,**</span></span>  
  
13. <span data-ttu-id="23461-284">Klicken Sie in der Liste **Kategorie** erneut auf **Datum & Uhrzeit**.</span><span class="sxs-lookup"><span data-stu-id="23461-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="23461-285">Doppelklicken Sie in der Liste **Element** auf **Now**.</span><span class="sxs-lookup"><span data-stu-id="23461-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="23461-286">In Produktionsberichten dürfen Sie nicht die **Now** -Funktion in Ausdrücken verwenden, die beim Rendern des Berichts mehrmals ausgewertet werden (z.B. in den Detailzeilen eines Berichts).</span><span class="sxs-lookup"><span data-stu-id="23461-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="23461-287">Der Wert von **Now** ändert sich von Zeile zu Zeile, und die verschiedenen Werte wirken sich auf die Auswertungsergebnisse der Ausdrücke aus, was zu inkonsistenten Resultaten führt.</span><span class="sxs-lookup"><span data-stu-id="23461-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="23461-288">Sie müssen stattdessen die globale Variable `ExecutionTime` verwenden, die von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="23461-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="23461-289">Wenn der Cursor nicht bereits unmittelbar nach `Now(` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="23461-290">Löschen Sie die linke Klammer, und geben Sie **)** ein</span><span class="sxs-lookup"><span data-stu-id="23461-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="23461-291">Der vollständige Ausdruck lautet wie folgt: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="23461-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="23461-292">7. Verwenden eines Indikators zur Anzeige des Umsatz Vergleichs</span><span class="sxs-lookup"><span data-stu-id="23461-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="23461-293">Fügen Sie eine neue Spalte hinzu, und verwenden Sie einen Indikator, um anzuzeigen, ob die Käufe im laufenden Jahr oberhalb oder unterhalb des durchschnittlichen YTD-Einkäufen liegen.</span><span class="sxs-lookup"><span data-stu-id="23461-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="23461-294">Die Funktion **Round** entfernt die Dezimalstellen aus den Werten.</span><span class="sxs-lookup"><span data-stu-id="23461-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="23461-295">Für die Konfiguration des Indikators und seiner Zustände sind mehrere Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23461-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="23461-296">Wenn Sie möchten, können Sie im Verfahren "so konfigurieren Sie den Indikator" fortfahren und die fertigen Ausdrücke aus diesem Tutorial in das Dialogfeld **Ausdruck** kopieren bzw. einfügen.</span><span class="sxs-lookup"><span data-stu-id="23461-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="23461-297">So fügen Sie die Spalte "+/- durchschnittl. Käufe" hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="23461-298">Klicken Sie mit der rechten Maustaste auf **YTD Purchase** , zeigen Sie auf **Spalte einfügen**und klicken Sie auf **Rechts**.</span><span class="sxs-lookup"><span data-stu-id="23461-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="23461-299">Rechts von der Spalte **YTD Purchase** wird eine neue Spalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23461-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="23461-300">Klicken Sie auf den Titel der Spalte und geben Sie **+/- durchschnittl. Käufe** ein</span><span class="sxs-lookup"><span data-stu-id="23461-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="23461-301">So fügen Sie einen Indikator hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="23461-302">Klicken Sie auf der Registerkarte **Einfügen** im Menüband auf **Indikator** und anschließend in die Datenzelle der Spalte **+/- durchschnittl. Käufe**.</span><span class="sxs-lookup"><span data-stu-id="23461-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="23461-303">Das Dialogfeld **Indikatortyp auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="23461-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="23461-304">Klicken Sie in der Gruppe **Direktional** der Symbolsätze auf den Satz mit den drei grauen Pfeilen.</span><span class="sxs-lookup"><span data-stu-id="23461-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="23461-305">So konfigurieren Sie den Indikator</span><span class="sxs-lookup"><span data-stu-id="23461-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="23461-306">Klicken Sie mit der rechten Maustaste auf den Indikator, anschließend auf **Indikatoreigenschaften**und schließlich auf **Wert und Status**.</span><span class="sxs-lookup"><span data-stu-id="23461-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="23461-307">Klicken Sie auf die Ausdrucksschaltfläche **fx** neben dem Textfeld **Wert** .</span><span class="sxs-lookup"><span data-stu-id="23461-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="23461-308">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**, und klicken Sie anschließend auf **Mathematisch**.</span><span class="sxs-lookup"><span data-stu-id="23461-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="23461-309">Doppelklicken Sie in der Liste **Element** auf **Round**.</span><span class="sxs-lookup"><span data-stu-id="23461-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="23461-310">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="23461-311">Doppelklicken Sie in der Liste **Werte** auf **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="23461-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="23461-312">Wenn der Cursor nicht bereits unmittelbar nach `Fields!YTDPurchase.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="23461-313">Sorte**-**</span><span class="sxs-lookup"><span data-stu-id="23461-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="23461-314">Erweitern Sie die **Allgemeinen Funktionen** erneut und klicken Sie auf **Aggregat**.</span><span class="sxs-lookup"><span data-stu-id="23461-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="23461-315">Doppelklicken Sie in der Liste **Element** auf **Avg**.</span><span class="sxs-lookup"><span data-stu-id="23461-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="23461-316">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="23461-317">Doppelklicken Sie in der Liste **Werte** auf **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="23461-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="23461-318">Wenn der Cursor nicht bereits unmittelbar nach `Fields!YTDPurchase.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="23461-319">Geben Sie **, "Expressions"))** ein</span><span class="sxs-lookup"><span data-stu-id="23461-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="23461-320">Der vollständige Ausdruck lautet wie folgt: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="23461-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="23461-321">Wählen Sie als **Maßeinheit für Status\*\*\*\*Numerisch**aus.</span><span class="sxs-lookup"><span data-stu-id="23461-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="23461-322">Klicken Sie in der Reihe mit dem Pfeil nach unten auf die Schaltfläche **fx** rechts neben dem Textfeld für den **Start** -Wert.</span><span class="sxs-lookup"><span data-stu-id="23461-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="23461-323">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**, und klicken Sie anschließend auf **Mathematisch**.</span><span class="sxs-lookup"><span data-stu-id="23461-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="23461-324">Doppelklicken Sie in der Liste **Element** auf **Round**.</span><span class="sxs-lookup"><span data-stu-id="23461-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="23461-325">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="23461-326">Doppelklicken Sie in der Liste **Werte** auf **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="23461-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="23461-327">Wenn der Cursor nicht bereits unmittelbar nach `Fields!YTDPurchase.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="23461-328">Sorte**-**</span><span class="sxs-lookup"><span data-stu-id="23461-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="23461-329">Erweitern Sie die **Allgemeinen Funktionen** erneut und klicken Sie auf **Aggregat**.</span><span class="sxs-lookup"><span data-stu-id="23461-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="23461-330">Doppelklicken Sie in der Liste **Element** auf **Avg**.</span><span class="sxs-lookup"><span data-stu-id="23461-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="23461-331">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="23461-332">Doppelklicken Sie in der Liste **Werte** auf **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="23461-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="23461-333">Wenn der Cursor nicht bereits unmittelbar nach `Fields!YTDPurchase.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="23461-334">Geben Sie **, "Expressions")) < 0** ein</span><span class="sxs-lookup"><span data-stu-id="23461-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="23461-335">Der vollständige Ausdruck lautet wie folgt: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="23461-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="23461-336">Geben Sie im Textfeld **Ende** den Wert **0**ein</span><span class="sxs-lookup"><span data-stu-id="23461-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="23461-337">Klicken Sie auf die Zeile mit dem horizontalen Pfeil, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="23461-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="23461-338">Geben Sie in der Zeile mit dem nach oben zeigenden Pfeil im Feld **Start** den Wert **0**ein</span><span class="sxs-lookup"><span data-stu-id="23461-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="23461-339">Klicken Sie auf die Schaltfläche **fx** rechts neben dem Textfeld für den **Ende** -Wert.</span><span class="sxs-lookup"><span data-stu-id="23461-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="23461-340">Erstellen Sie im Dialogfeld **Ausdruck** den Ausdruck:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="23461-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="23461-341">Klicken Sie auf **OK** , um das Dialogfeld **Indikatoreigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="23461-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="23461-342">Klicken Sie auf **Ausführen** , um eine Vorschau des Berichts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="23461-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="23461-343">8. machen Sie den Bericht zu einem "grünen Balken Bericht".</span><span class="sxs-lookup"><span data-stu-id="23461-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="23461-344">Verwenden Sie einen Parameter, um die Farbe zu bestimmen, die abwechselnd auf die Zeilen im Bericht angewendet wird, um einen Balkenbericht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23461-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="23461-345">So fügen Sie einen Parameter hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="23461-346">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-347">Klicken Sie im Bereich **Berichtsdaten** mit der rechten Maustaste auf **Parameter** und anschließend auf **Parameter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23461-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="23461-348">Das Dialogfeld **Berichtsparametereigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="23461-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="23461-349">Geben Sie in die **Eingabeaufforderung\*\*\*\*Farbe auswählen**ein</span><span class="sxs-lookup"><span data-stu-id="23461-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="23461-350">Geben Sie in **Name\*\*\*\*Spaltenfarbe**ein</span><span class="sxs-lookup"><span data-stu-id="23461-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="23461-351">Klicken Sie im linken Bereich auf **Verfügbare Werte**.</span><span class="sxs-lookup"><span data-stu-id="23461-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="23461-352">Klicken Sie auf **Werte angeben**.</span><span class="sxs-lookup"><span data-stu-id="23461-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="23461-353">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23461-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="23461-354">Geben Sie im Feld **Bezeichnung** Folgendes ein: **Gelb**</span><span class="sxs-lookup"><span data-stu-id="23461-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="23461-355">Geben Sie im Feld **Wert** Folgendes ein: **Gelb**</span><span class="sxs-lookup"><span data-stu-id="23461-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="23461-356">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23461-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="23461-357">Geben Sie im Feld **Bezeichnung** Folgendes ein: **Grün**</span><span class="sxs-lookup"><span data-stu-id="23461-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="23461-358">Geben Sie im Feld **Wert** Folgendes ein: **Blassgrün**</span><span class="sxs-lookup"><span data-stu-id="23461-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="23461-359">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23461-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="23461-360">Geben Sie im Feld **Bezeichnung** Folgendes ein: **Blau**</span><span class="sxs-lookup"><span data-stu-id="23461-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="23461-361">Geben Sie im Feld **Wert** Folgendes ein: **Hellblau**</span><span class="sxs-lookup"><span data-stu-id="23461-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="23461-362">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="23461-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="23461-363">Geben Sie im Feld **Bezeichnung** Folgendes ein: **Rosa**</span><span class="sxs-lookup"><span data-stu-id="23461-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="23461-364">Geben Sie im Feld **Wert** Folgendes ein: **Rosa**</span><span class="sxs-lookup"><span data-stu-id="23461-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="23461-365">So wenden Sie abwechselnde Farben auf Detailzeilen an</span><span class="sxs-lookup"><span data-stu-id="23461-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="23461-366">Klicken Sie auf die Registerkarte **Ansicht** auf dem Menüband und überprüfen Sie, ob **Eigenschaften** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="23461-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="23461-367">Klicken Sie mit der rechten Maustaste in die Datenzelle der Spalte **Name** und drücken Sie die UMSCHALTTASTE.</span><span class="sxs-lookup"><span data-stu-id="23461-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="23461-368">Klicken Sie nacheinander auf die anderen Zellen in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="23461-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="23461-369">Klicken Sie im Bereich „Eigenschaften“ auf **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="23461-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="23461-370">Wenn die Eigenschaften im Eigenschaftenbereich nach Kategorie angezeigt werden, finden Sie **BackgroundColor** in der Kategorie **Ausfüllen**.</span><span class="sxs-lookup"><span data-stu-id="23461-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="23461-371">Klicken Sie auf den Pfeil nach unten und anschließend auf **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="23461-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="23461-372">Erweitern Sie im Dialogfeld **Ausdruck** die Option **Allgemeine Funktionen**, und klicken Sie anschließend auf **Programmfluss**.</span><span class="sxs-lookup"><span data-stu-id="23461-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="23461-373">Doppelklicken Sie in der Liste **Element** auf **IIf**.</span><span class="sxs-lookup"><span data-stu-id="23461-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="23461-374">Erweitern Sie die **Allgemeinen Funktionen** und klicken Sie auf **Aggregat**.</span><span class="sxs-lookup"><span data-stu-id="23461-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="23461-375">Doppelklicken Sie in der Liste **Element** auf **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="23461-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="23461-376">Doppelklicken Sie in der Liste **Kategorie** auf **Felder (Ausdrücke)**.</span><span class="sxs-lookup"><span data-stu-id="23461-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="23461-377">Doppelklicken Sie in der Liste **Werte** auf **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="23461-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="23461-378">Wenn der Cursor nicht bereits unmittelbar nach `Fields!FirstName.Value` platziert ist, korrigieren Sie das und geben Sie **,** ein</span><span class="sxs-lookup"><span data-stu-id="23461-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="23461-379">Erweitern Sie die **Allgemeinen Funktionen** und klicken Sie auf **Aggregat**.</span><span class="sxs-lookup"><span data-stu-id="23461-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="23461-380">Doppelklicken Sie in der Liste **Element** auf **Count**.</span><span class="sxs-lookup"><span data-stu-id="23461-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="23461-381">Wenn der Cursor nicht bereits unmittelbar nach `Count(` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="23461-382">Löschen Sie die linke Klammer, und geben Sie **, "Ausdrücke")** ein.</span><span class="sxs-lookup"><span data-stu-id="23461-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="23461-383">"Ausdrücke" ist der Name des Datasets, das zum Zählen der Datenzeilen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="23461-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="23461-384">Erweitern Sie **Operatoren** und klicken Sie auf **Arithmetisch**.</span><span class="sxs-lookup"><span data-stu-id="23461-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="23461-385">Doppelklicken Sie in der Liste **Element** auf **Mod**.</span><span class="sxs-lookup"><span data-stu-id="23461-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="23461-386">Wenn der Cursor nicht bereits unmittelbar nach `Mod` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="23461-387">Geben Sie **2 =0,** ein</span><span class="sxs-lookup"><span data-stu-id="23461-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="23461-388">Stellen Sie sicher, dass vor der Zahl 2 ein Leerzeichen steht.</span><span class="sxs-lookup"><span data-stu-id="23461-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="23461-389">Klicken Sie auf **Parameter** und doppelklicken Sie in der Liste **Werte** auf **Spaltenfarbe**.</span><span class="sxs-lookup"><span data-stu-id="23461-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="23461-390">Wenn der Cursor nicht bereits unmittelbar nach `Parameters!RowColor.Value` platziert ist, korrigieren Sie das.</span><span class="sxs-lookup"><span data-stu-id="23461-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="23461-391">Geben Sie **, "White")** ein.</span><span class="sxs-lookup"><span data-stu-id="23461-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="23461-392">Der vollständige Ausdruck lautet wie folgt: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="23461-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="23461-393">Führen Sie den Bericht aus</span><span class="sxs-lookup"><span data-stu-id="23461-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="23461-394">Wenn Sie sich nicht auf der Registerkarte **Stamm** befinden, klicken Sie auf **Stamm**, um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-395">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="23461-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="23461-396">Wählen Sie in der Dropdownliste **Farbe auswählen** die Farbe für diejenigen Balken im Bericht aus, die nicht weiß sein sollen.</span><span class="sxs-lookup"><span data-stu-id="23461-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="23461-397">Klicken Sie auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="23461-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="23461-398">Der Bericht wird gerendert und die abwechselnden Zeilen weisen den gewünschten Hintergrund auf.</span><span class="sxs-lookup"><span data-stu-id="23461-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="23461-399">optionale Formatieren der Datums Spalte</span><span class="sxs-lookup"><span data-stu-id="23461-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="23461-400">Formatieren Sie die Spalte **Last Purchase**, die Datumsangaben enthält.</span><span class="sxs-lookup"><span data-stu-id="23461-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="23461-401">So formatieren Sie die Datumsspalte</span><span class="sxs-lookup"><span data-stu-id="23461-401">To format date column</span></span>  
  
1.  <span data-ttu-id="23461-402">Klicken Sie auf **Entwurf** , um zur Entwurfsansicht zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="23461-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="23461-403">Klicken Sie mit der rechten Maustaste in die Datenzelle der Spalte **Last Purchase** und klicken Sie anschließend auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="23461-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="23461-404">Klicken Sie im Dialogfeld **Textfeldeigenschaften** auf **Zahl**, dann auf **Datum** und anschließend auf den Typ **\*31.01.2000**.</span><span class="sxs-lookup"><span data-stu-id="23461-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="23461-405">optionale Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="23461-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="23461-406">Hinzufügen eines Titels zu einem Bericht</span><span class="sxs-lookup"><span data-stu-id="23461-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="23461-407">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="23461-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="23461-408">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="23461-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="23461-409">Geben Sie **Umsatzvergleich – Zusammenfassung** ein, und klicken Sie anschließend auf eine Stelle außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="23461-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="23461-410">Klicken Sie mit der rechten Maustaste auf das Textfeld, das **Umsatzvergleich - Zusammenfassung** enthält und klicken Sie auf **Textfeldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="23461-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="23461-411">Klicken Sie im Dialogfeld **Textfeldeigenschaften** auf **Schriftart**.</span><span class="sxs-lookup"><span data-stu-id="23461-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="23461-412">Wählen Sie in der Liste **Schriftgrad** den Eintrag **18pt**aus.</span><span class="sxs-lookup"><span data-stu-id="23461-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="23461-413">Wählen Sie in der Liste **Farbe** die Option **Grau** aus.</span><span class="sxs-lookup"><span data-stu-id="23461-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="23461-414">Wählen Sie **Fett** und **Kursiv**.</span><span class="sxs-lookup"><span data-stu-id="23461-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="23461-415">optionale Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="23461-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="23461-416">Sie können Berichte auf einem Berichtsserver, in einer SharePoint-Bibliothek oder auf dem Computer speichern.</span><span class="sxs-lookup"><span data-stu-id="23461-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="23461-417">Weitere Informationen finden Sie unter [Speichern von Berichten &#40;Berichts-Generator&#41;](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="23461-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="23461-418">Speichern Sie in diesem Lernprogramm den Bericht auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="23461-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="23461-419">Wenn Sie keinen Zugriff auf einen Berichtsserver besitzen, speichern Sie den Bericht auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="23461-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="23461-420">So speichern Sie den Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="23461-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="23461-421">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="23461-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="23461-422">Klicken Sie auf **Letzte Sites und Server**.</span><span class="sxs-lookup"><span data-stu-id="23461-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="23461-423">Wählen Sie den Namen des Berichtsservers aus, auf dem Sie zum Speichern von Berichten berechtigt sind, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="23461-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="23461-424">Die Meldung "Verbindung mit Berichtsserver wird hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23461-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="23461-425">Nachdem die Verbindung hergestellt wurde, sehen Sie den Inhalt des Berichtsordners, den der Berichtsserveradministrator als Standardspeicherort für Berichte angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="23461-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="23461-426">Ersetzen Sie in **Name** den Standardnamen durch **Umsatzvergleich – Zusammenfassung**.</span><span class="sxs-lookup"><span data-stu-id="23461-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="23461-427">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23461-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="23461-428">Der Bericht wird auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="23461-428">The report is saved to the report server.</span></span> <span data-ttu-id="23461-429">Der Name des Berichtsservers, mit dem Sie verbunden sind, wird in der Statusleiste unten im Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23461-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="23461-430">So speichern Sie den Bericht auf Ihrem Computer</span><span class="sxs-lookup"><span data-stu-id="23461-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="23461-431">Klicken Sie auf die Schaltfläche **Berichts-Generator** und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="23461-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="23461-432">Klicken Sie auf **Desktop**, **Meine Dokumente**oder **Arbeitsplatz**, und navigieren Sie anschließend zu dem Ordner, in dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="23461-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="23461-433">Ersetzen Sie in **Name** den Standardnamen durch **Umsatzvergleich – Zusammenfassung**.</span><span class="sxs-lookup"><span data-stu-id="23461-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="23461-434">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="23461-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23461-435">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23461-435">See Also</span></span>  
 <span data-ttu-id="23461-436">[Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23461-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23461-437">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23461-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23461-438">[Indikatoren &#40;Berichts-Generator und SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23461-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23461-439">[Bilder, Text Felder, Rechtecke und Linien &#40;Berichts-Generator und SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23461-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="23461-440">[Tabellen &#40;Berichts-Generator und SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="23461-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="23461-441">Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="23461-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
