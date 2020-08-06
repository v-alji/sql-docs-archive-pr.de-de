---
title: 'Lektion 2: Hinzufügen von Daten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615664"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="15eb6-102">Lektion 2: Hinzufügen von Daten</span><span class="sxs-lookup"><span data-stu-id="15eb6-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="15eb6-103">In dieser Lektion verwenden Sie den Tabellenimport-Assistenten in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , um eine Verbindung mit der AdventureWorksDW-Datenbank herzustellen, Daten auszuwählen und die Daten zu filtern und sie anschließend in den Modellarbeitsbereich zu importieren.</span><span class="sxs-lookup"><span data-stu-id="15eb6-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="15eb6-104">Mit dem Tabellenimport-Assistenten können Sie Daten aus einer Reihe verschiedener relationaler Quellen importieren: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata usw.</span><span class="sxs-lookup"><span data-stu-id="15eb6-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="15eb6-105">Die Schritte zum Importieren von Daten aus jeder dieser relationalen Quellen sind sehr ähnlich und mit dem unten beschriebenen Vorgang vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="15eb6-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="15eb6-106">Darüber hinaus können Daten mit einer gespeicherten Prozedur ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="15eb6-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="15eb6-107">Weitere Informationen zum Importieren von Daten und den verschiedenen Datenquellentypen, aus denen Importe möglich sind, finden Sie unter [Datenquellen &#40;SSAS – tabellarisch&#41;](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="15eb6-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="15eb6-108">Geschätzte Zeit zum Bearbeiten dieser Lektion: **20 Minuten**</span><span class="sxs-lookup"><span data-stu-id="15eb6-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="15eb6-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="15eb6-109">Prerequisites</span></span>  
 <span data-ttu-id="15eb6-110">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="15eb6-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="15eb6-111">Vor dem Ausführen der Aufgaben in dieser Lektion sollten Sie die vorherige Lektion abgeschlossen haben: [Lektion 1: Erstellen eines neuen tabellarischen Modellprojekts](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="15eb6-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="15eb6-112">Erstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="15eb6-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="15eb6-113">So erstellen Sie eine Verbindung mit der AdventureWorksDW2012-Datenbank</span><span class="sxs-lookup"><span data-stu-id="15eb6-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="15eb6-114">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und anschließend auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="15eb6-115">Dadurch wird der Tabellenimport-Assistent gestartet, der Sie durch das Herstellen einer Verbindung mit einer Datenquelle führt.</span><span class="sxs-lookup"><span data-stu-id="15eb6-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="15eb6-116">Wenn **Aus Datenquelle importieren** ausgegraut ist, doppelklicken Sie **Solution Explorer** auf **Model.bim** , um das Modell im Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="15eb6-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="15eb6-117">Klicken Sie im **Tabellenimport-Assistenten**unter **Relationale Datenbanken**auf **Microsoft SQL Server**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="15eb6-118">Geben Sie auf der Seite **mit einer Microsoft SQL Server Datenbank verbinden** in Anzeige **Name der Verbindung den Namen**ein `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="15eb6-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="15eb6-119">Geben Sie in **Servername**den Namen des Servers ein, auf dem Sie die AdventureWorksDW-Datenbank installiert haben.</span><span class="sxs-lookup"><span data-stu-id="15eb6-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="15eb6-120">Klicken Sie im Feld **Datenbankname** auf den NACH-UNTEN-PFEIL, und wählen Sie **AdventureWorksDW**und anschließend **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="15eb6-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="15eb6-121">Auf der Seite **Identitätswechselinformationen** müssen Sie die Anmeldeinformationen angeben, mit denen Analysis Services eine Verbindung mit der Datenquelle herstellt, wenn Daten importiert und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="15eb6-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="15eb6-122">Überprüfen Sie, ob **Bestimmter Windows-Benutzername und bestimmtes Kennwort** ausgewählt ist, geben Sie in den Feldern **Benutzername** und **Kennwort**Ihre Windows-Anmeldeinformationen ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15eb6-123">Die Verwendung eines Windows-Benutzerkontos und -Kennworts stellt die sicherste Methode für das Herstellen einer Verbindung mit einer Datenquelle dar.</span><span class="sxs-lookup"><span data-stu-id="15eb6-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="15eb6-124">Weitere Informationen finden Sie unter [Identitätswechsel &#40;SSAS – tabellarisch&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="15eb6-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="15eb6-125">Überprüfen Sie auf der Seite **Auswählen, wie die Daten importiert werden sollen** , ob die Option **Aus einer Liste von Tabellen und Sichten auswählen, um die zu importierenden Daten zu bestimmen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="15eb6-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="15eb6-126">Sie möchten in einer Liste von Tabellen und Sichten eine Auswahl treffen. Klicken Sie daher auf **Weiter** , um eine Liste aller Quelltabellen in der Quelldatenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="15eb6-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="15eb6-127">Aktivieren Sie auf der Seite **Tabellen und Sichten auswählen** das Kontrollkästchen für die folgenden Tabellen: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**und **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="15eb6-128">Die Tabellen im Modell sollten leicht verständliche Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="15eb6-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="15eb6-129">Klicken Sie auf die Zelle in der Spalte **Anzeigename** für **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="15eb6-130">Benennen Sie die Tabelle um, indem Sie "Dim" aus "DimCustomer" entfernen.</span><span class="sxs-lookup"><span data-stu-id="15eb6-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="15eb6-131">Benennen Sie die anderen Tabellen um:</span><span class="sxs-lookup"><span data-stu-id="15eb6-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="15eb6-132">Quellname</span><span class="sxs-lookup"><span data-stu-id="15eb6-132">Source name</span></span>|<span data-ttu-id="15eb6-133">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="15eb6-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="15eb6-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="15eb6-134">DimDate</span></span>|<span data-ttu-id="15eb6-135">Date</span><span class="sxs-lookup"><span data-stu-id="15eb6-135">Date</span></span>|  
    |<span data-ttu-id="15eb6-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="15eb6-136">DimGeography</span></span>|<span data-ttu-id="15eb6-137">Geografie</span><span class="sxs-lookup"><span data-stu-id="15eb6-137">Geography</span></span>|  
    |<span data-ttu-id="15eb6-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="15eb6-138">DimProduct</span></span>|<span data-ttu-id="15eb6-139">Produkt</span><span class="sxs-lookup"><span data-stu-id="15eb6-139">Product</span></span>|  
    |<span data-ttu-id="15eb6-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="15eb6-140">DimProductCategory</span></span>|<span data-ttu-id="15eb6-141">Produktkategorie</span><span class="sxs-lookup"><span data-stu-id="15eb6-141">Product Category</span></span>|  
    |<span data-ttu-id="15eb6-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="15eb6-142">DimProductSubcategory</span></span>|<span data-ttu-id="15eb6-143">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="15eb6-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="15eb6-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="15eb6-144">FactInternetSales</span></span>|<span data-ttu-id="15eb6-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="15eb6-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="15eb6-146">Klicken Sie**NICHT** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="15eb6-147">Da Sie jetzt eine Verbindung mit der Datenbank hergestellt, die zu importierenden Tabellen ausgewählt und den Tabellen Anzeigenamen zugewiesen haben, wechseln Sie zum nächsten Abschnitt mit der Überschrift [Filtern der Tabellendaten vor dem Importieren](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="15eb6-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="15eb6-148">Filtern der Tabellendaten</span><span class="sxs-lookup"><span data-stu-id="15eb6-148">Filter the Table Data</span></span>  
 <span data-ttu-id="15eb6-149">Die DimCustomer-Tabelle, die Sie aus der Datenbank importieren, enthält eine Teilmenge der Daten aus der ursprünglichen SQL Server Adventure Works-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="15eb6-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="15eb6-150">Einige der Spalten aus der DimCustomer-Tabelle werden herausgefiltert, die nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="15eb6-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="15eb6-151">Wenn möglich, möchten Sie nicht verwendete Daten herausfiltern, um vom Modell verwendeten Speicherplatz im Arbeitsspeicher zu sparen.</span><span class="sxs-lookup"><span data-stu-id="15eb6-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="15eb6-152">So filtern Sie die Tabellendaten vor dem Importieren</span><span class="sxs-lookup"><span data-stu-id="15eb6-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="15eb6-153">Wählen Sie die Zeile für die Tabelle **Customer** aus, und klicken Sie anschließend auf **Vorschau & Filter**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="15eb6-154">Das Fenster **Vorschau der ausgewählten Tabelle** wird geöffnet und enthält alle Spalten in der DimCustomer-Quelltabelle.</span><span class="sxs-lookup"><span data-stu-id="15eb6-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="15eb6-155">Deaktivieren Sie das Kontrollkästchen am Anfang der folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="15eb6-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="15eb6-156">Kunde</span><span class="sxs-lookup"><span data-stu-id="15eb6-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="15eb6-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="15eb6-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="15eb6-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="15eb6-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="15eb6-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="15eb6-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="15eb6-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="15eb6-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="15eb6-161">Da die Werte für diese Spalten nicht relevant für die Analyse von Internetverkäufen sind, müssen die Spalten nicht importiert werden.</span><span class="sxs-lookup"><span data-stu-id="15eb6-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="15eb6-162">Durch Entfernen von nicht benötigten Spalten wird das Modell kleiner.</span><span class="sxs-lookup"><span data-stu-id="15eb6-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="15eb6-163">Überprüfen Sie, ob alle anderen Spalten aktiviert sind, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="15eb6-164">Beachten Sie, dass die Wörter **angewendete Filter** nun in der Spalte **Filter Details** in der Zeile **Customer** angezeigt werden. Wenn Sie auf diesen Link klicken, sehen Sie eine Textbeschreibung der Filter, die Sie soeben angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="15eb6-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="15eb6-165">Filtern Sie die verbleibenden Tabellen, indem Sie die Kontrollkästchen für die folgenden Spalten in jeder Tabelle deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="15eb6-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="15eb6-166">Date</span><span class="sxs-lookup"><span data-stu-id="15eb6-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="15eb6-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="15eb6-167">**DateKey**</span></span>|  
    |<span data-ttu-id="15eb6-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="15eb6-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="15eb6-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="15eb6-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="15eb6-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="15eb6-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="15eb6-172">Geografie</span><span class="sxs-lookup"><span data-stu-id="15eb6-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="15eb6-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="15eb6-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="15eb6-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="15eb6-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="15eb6-176">Produkt</span><span class="sxs-lookup"><span data-stu-id="15eb6-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="15eb6-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="15eb6-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="15eb6-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="15eb6-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="15eb6-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="15eb6-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="15eb6-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="15eb6-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="15eb6-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="15eb6-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="15eb6-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="15eb6-187">Produktkategorie</span><span class="sxs-lookup"><span data-stu-id="15eb6-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="15eb6-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="15eb6-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="15eb6-190">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="15eb6-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="15eb6-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="15eb6-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="15eb6-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="15eb6-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="15eb6-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="15eb6-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="15eb6-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="15eb6-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="15eb6-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="15eb6-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="15eb6-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="15eb6-197">Nachdem Sie die nicht benötigten Daten in der Vorschau angezeigt und die herausgefiltert haben, können Sie die Daten importieren.</span><span class="sxs-lookup"><span data-stu-id="15eb6-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="15eb6-198">Wechseln Sie zum nächsten Abschnitt ( **Importieren der ausgewählten Tabellen- und Spaltendaten**).</span><span class="sxs-lookup"><span data-stu-id="15eb6-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="15eb6-199">Importieren der ausgewählten Tabellen und Spaltendaten</span><span class="sxs-lookup"><span data-stu-id="15eb6-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="15eb6-200">Sie können jetzt die ausgewählten Daten importieren.</span><span class="sxs-lookup"><span data-stu-id="15eb6-200">You can now import the selected data.</span></span> <span data-ttu-id="15eb6-201">Der Assistent importiert die Tabellendaten zusammen mit allen Beziehungen zwischen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="15eb6-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="15eb6-202">Neue Tabellen und Spalten werden im Modell mit den Anzeigenamen erstellt, die Sie angegeben haben, und gefilterte Daten werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="15eb6-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="15eb6-203">So importieren Sie die ausgewählten Tabellen und Spaltendaten</span><span class="sxs-lookup"><span data-stu-id="15eb6-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="15eb6-204">Überprüfen Sie Ihre Auswahl.</span><span class="sxs-lookup"><span data-stu-id="15eb6-204">Review your selections.</span></span> <span data-ttu-id="15eb6-205">Wenn alles in Ordnung ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="15eb6-206">Während des Datenimports zeigt der Assistent an, wie viele Zeilen abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="15eb6-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="15eb6-207">Wenn alle Daten importiert wurden, wird in einer Meldung angezeigt, dass der Import erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="15eb6-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="15eb6-208">Klicken Sie zum Anzeigen der Beziehungen, die automatisch zwischen den importierten Tabellen erstellt wurden, in der Zeile **Datenvorbereitung** auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="15eb6-209">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="15eb6-210">Der Assistent wird geschlossen, wohingegen der Modell-Designer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="15eb6-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="15eb6-211">Jede Tabelle wurde als neue Registerkarte im Modell-Designer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="15eb6-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="15eb6-212">Speichern des Modellprojekts</span><span class="sxs-lookup"><span data-stu-id="15eb6-212">Save the Model Project</span></span>  
 <span data-ttu-id="15eb6-213">Es ist wichtig, das Modellprojekt, häufig zu speichern.</span><span class="sxs-lookup"><span data-stu-id="15eb6-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="15eb6-214">So speichern Sie das Modellprojekt</span><span class="sxs-lookup"><span data-stu-id="15eb6-214">To save the model project</span></span>  
  
-   <span data-ttu-id="15eb6-215">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Datei** und anschließend auf **Alle speichern**.</span><span class="sxs-lookup"><span data-stu-id="15eb6-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="15eb6-216">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="15eb6-216">Next Step</span></span>  
 <span data-ttu-id="15eb6-217">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 3: Umbenennen von Spalten](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="15eb6-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
