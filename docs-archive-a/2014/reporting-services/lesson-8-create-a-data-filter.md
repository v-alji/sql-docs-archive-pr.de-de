---
title: 'Lektion 8: Erstellen eines Datenfilters | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609706"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="0e615-102">Lektion 8: Erstellen eines Datenfilters</span><span class="sxs-lookup"><span data-stu-id="0e615-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="0e615-103">Nachdem Sie im übergeordneten Bericht eine Drillthroughaktion hinzugefügt haben, erstellen Sie im nächsten Schritt einen Datenfilter für die Datentabelle, die Sie für den untergeordneten Bericht definiert haben.</span><span class="sxs-lookup"><span data-stu-id="0e615-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="0e615-104">Sie können für den Drillthroughbericht einen tabellenbasierten Filter **oder** einen Abfragefilter erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e615-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="0e615-105">Diese Lektion enthält Anweisungen zum Erstellen beider Filtertypen.</span><span class="sxs-lookup"><span data-stu-id="0e615-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="0e615-106">Tabellenbasierter Filter</span><span class="sxs-lookup"><span data-stu-id="0e615-106">Table-Based Filter</span></span>  
 <span data-ttu-id="0e615-107">Führen Sie folgende Aufgaben aus, um einen tabellenbasierten Filter zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0e615-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="0e615-108">Fügen Sie der Tablix im untergeordneten Bericht einen Filterausdruck hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e615-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="0e615-109">Erstellen Sie eine Funktion, mit der ungefilterte Daten aus der `PurchaseOrderDetail`-Tabelle ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="0e615-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="0e615-110">Fügen Sie einen Ereignishandler hinzu, durch den die `PurchaseOrderDetail`-DataTable an den untergeordneten Bericht gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="0e615-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="0e615-111">So fügen Sie der Tablix im untergeordneten Bericht einen Filterausdruck hinzu</span><span class="sxs-lookup"><span data-stu-id="0e615-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="0e615-112">Öffnen Sie den untergeordneten Bericht.</span><span class="sxs-lookup"><span data-stu-id="0e615-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="0e615-113">Wählen Sie im Tablix-Element eine Spaltenüberschrift aus, klicken Sie mit der rechten Maustaste auf die graue Zelle oberhalb der Spaltenüberschrift, und klicken Sie dann auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0e615-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="0e615-114">Klicken Sie auf die Seite **Filter** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0e615-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="0e615-115">Klicken Sie **Expression** im `ProductID` abgelegten Ausdruck auf aus der Dropdown Liste.</span><span class="sxs-lookup"><span data-stu-id="0e615-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="0e615-116">Dies ist die Spalte, auf die Sie den Filter anwenden.</span><span class="sxs-lookup"><span data-stu-id="0e615-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="0e615-117">Klicken Sie **=** in der Dropdown Liste **Operator** auf den Gleichheits Operator ().</span><span class="sxs-lookup"><span data-stu-id="0e615-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="0e615-118">Klicken Sie neben dem Feld **Wert** auf die Ausdrucks Schaltfläche, klicken Sie im Bereich **Kategorie** auf **Parameter** , und doppelklicken Sie dann `productid` auf den Bereich **Werte** .</span><span class="sxs-lookup"><span data-stu-id="0e615-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="0e615-119">Das Feld **Ausdruck festlegen für: Wert** sollte jetzt einen mit **=Parameters!productid.Value**vergleichbaren Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="0e615-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="0e615-120">Klicken Sie im Dialogfeld **Tablix-Eigenschaften** auf **OK** und ein zweites Mal auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="0e615-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="0e615-121">Speichern Sie die RDLC-Datei.</span><span class="sxs-lookup"><span data-stu-id="0e615-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="0e615-122">So erstellen Sie eine Funktion, durch die ungefilterte Daten aus der PurchaseOrderDetail-Tabelle ausgewählt werden</span><span class="sxs-lookup"><span data-stu-id="0e615-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="0e615-123">Erweitern Sie im Projektmappen-Explorer Default.aspx, und doppelklicken Sie dann auf Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="0e615-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="0e615-124">Erstellen Sie eine neue Funktion, die einen Parameter `productid` vom Typ Integer akzeptiert und ein- `datatable` Objekt zurückgibt, und führt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="0e615-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="0e615-125">Erstellt eine Instanz des Datasets, `DataSet2` das in Schritt 2 von [Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für](lesson-4-define-a-data-connection-and-data-table-for-child-report.md)den untergeordneten Bericht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e615-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="0e615-126">Herstellen einer Verbindung mit der SQL Server-Datenbank, um die in **Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für den untergeordneten Bericht**definierte Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e615-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="0e615-127">Die Abfrage gibt ungefilterte Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="0e615-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="0e615-128">Füllen der DataSet-Instanz mit den ungefilterten Daten, indem die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e615-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="0e615-129">Zurückgeben der `PurchaseOrderDetail`-DataTable.</span><span class="sxs-lookup"><span data-stu-id="0e615-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="0e615-130">Die Funktion sieht etwa wie folgt aus. (Sie dient nur zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="0e615-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="0e615-131">Sie können zum Abrufen der erforderlichen Daten für den untergeordneten Bericht ein beliebiges Muster verwenden.)</span><span class="sxs-lookup"><span data-stu-id="0e615-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="0e615-132">So fügen Sie einen Ereignishandler hinzu, durch den die PurchaseOrderDetail-DataTable an den untergeordneten Bericht gebunden wird</span><span class="sxs-lookup"><span data-stu-id="0e615-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="0e615-133">Öffnen Sie Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="0e615-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="0e615-134">Klicken Sie mit der rechten Maustaste auf das ReportViewer-Steuerelement, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0e615-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="0e615-135">Klicken Sie auf der Seite **Eigenschaften** auf das Symbol **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="0e615-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="0e615-136">Doppelklicken Sie auf das Ereignis **Drillthrough** .</span><span class="sxs-lookup"><span data-stu-id="0e615-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="0e615-137">Dadurch wird dem Code ein mit folgendem Block vergleichbarer Ereignishandlerabschnitt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e615-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="0e615-138">Vervollständigen Sie den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="0e615-138">Complete the event handler.</span></span> <span data-ttu-id="0e615-139">Er sollte folgende Funktionen umfassen.</span><span class="sxs-lookup"><span data-stu-id="0e615-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="0e615-140">Abrufen des Verweises des untergeordneten Berichtsobjekts aus dem *DrillthroughEventArgs* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0e615-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="0e615-141">Ruft die-Funktion auf.`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="0e615-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="0e615-142">Binden Sie die Datentabelle `PurchaseOrderDetail` an die entsprechende Datenquelle des Berichts.</span><span class="sxs-lookup"><span data-stu-id="0e615-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="0e615-143">Der vollständige Ereignishandlercode sollte dem folgenden ähnlich sein.</span><span class="sxs-lookup"><span data-stu-id="0e615-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="0e615-144">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="0e615-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="0e615-145">Abfragefilter</span><span class="sxs-lookup"><span data-stu-id="0e615-145">Query Filter</span></span>  
 <span data-ttu-id="0e615-146">Führen Sie folgende Aufgaben aus, um einen Abfragefilter zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0e615-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="0e615-147">Erstellen Sie eine Funktion, mit der gefilterte Daten aus der `PurchaseOrderDetail`-Tabelle ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="0e615-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="0e615-148">Fügen Sie einen Ereignishandler hinzu, durch den Parameterwerte abgerufen und die `PurchaseOrdeDetail`-DataTable an den untergeordneten Bericht gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="0e615-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="0e615-149">So erstellen Sie eine Funktion, durch die gefilterte Daten aus der PurchaseOrderDetail-Tabelle ausgewählt werden</span><span class="sxs-lookup"><span data-stu-id="0e615-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="0e615-150">Erweitern Sie im Projektmappen-Explorer Default.aspx, und doppelklicken Sie dann auf Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="0e615-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="0e615-151">Erstellen Sie eine neue Funktion, die den `productid`-Parameter vom Typ Integer akzeptiert, ein `datatable`-Objekt zurückgibt und folgende Schritte ausführt.</span><span class="sxs-lookup"><span data-stu-id="0e615-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="0e615-152">Erstellt eine Instanz des Datasets, `DataSet2` das in Schritt 2 von [Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für](lesson-4-define-a-data-connection-and-data-table-for-child-report.md)den untergeordneten Bericht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0e615-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="0e615-153">Herstellen einer Verbindung mit der SQL Server-Datenbank, um die in **Lektion 4: Definieren einer Datenverbindung und einer Datentabelle für den untergeordneten Bericht**definierte Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e615-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="0e615-154">Die Abfrage enthält den `productid`-Parameter, der gewährleistet, dass die zurückgegebenen Daten auf Grundlage der im übergeordneten Bericht ausgewählten `ProductID` gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="0e615-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="0e615-155">Füllen der DataSet-Instanz mit den gefilterten Daten, indem die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e615-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="0e615-156">Zurückgeben der `PurchaseOrderDetail`-DataTable.</span><span class="sxs-lookup"><span data-stu-id="0e615-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="0e615-157">Die Funktion sieht etwa wie folgt aus. (Sie dient nur zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="0e615-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="0e615-158">Sie können zum Abrufen der erforderlichen Daten für den untergeordneten Bericht ein beliebiges Muster verwenden.)</span><span class="sxs-lookup"><span data-stu-id="0e615-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="0e615-159">So fügen Sie einen Ereignishandler hinzu, durch den Parameterwerte abgerufen und die PurchaseOrderDetail-DataTable an den untergeordneten Bericht gebunden wird</span><span class="sxs-lookup"><span data-stu-id="0e615-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="0e615-160">Öffnen Sie Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="0e615-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="0e615-161">Klicken Sie mit der rechten Maustaste auf das Report Viewer-Steuerelement, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0e615-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0e615-162">Klicken Sie im Bereich **Eigenschaften** auf das Symbol **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="0e615-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="0e615-163">Doppelklicken Sie auf das Ereignis **Drillthrough** .</span><span class="sxs-lookup"><span data-stu-id="0e615-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="0e615-164">Dadurch wird dem Code ein mit Folgendem vergleichbarer Ereignishandlerabschnitt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0e615-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="0e615-165">Vervollständigen Sie den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="0e615-165">Complete the event handler.</span></span> <span data-ttu-id="0e615-166">Er sollte folgende Funktionen umfassen.</span><span class="sxs-lookup"><span data-stu-id="0e615-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="0e615-167">Abrufen des Verweises des untergeordneten Berichtsobjekts aus dem *DrillthroughEventArgs* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0e615-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="0e615-168">Abrufen der Parameterliste des untergeordneten Berichts aus dem abgerufenen untergeordneten Berichtsobjekt.</span><span class="sxs-lookup"><span data-stu-id="0e615-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="0e615-169">Durchlaufen der Parameterauflistung und Abrufen des aus dem übergeordneten Bericht übergebenen Werts für den `ProductID`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0e615-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="0e615-170">Aufrufen der `GetPurchaseOrderDetail`-Funktion und Übergeben des Werts für den `ProductID`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0e615-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="0e615-171">Binden der `PurchaseOrderDetail`-DataTable an die entsprechende Datenquelle des Berichts.</span><span class="sxs-lookup"><span data-stu-id="0e615-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="0e615-172">Der vollständige Ereignishandlercode sollte dem folgenden ähnlich sein.</span><span class="sxs-lookup"><span data-stu-id="0e615-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="0e615-173">Speichern Sie die Datei .</span><span class="sxs-lookup"><span data-stu-id="0e615-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="0e615-174">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="0e615-174">Next Task</span></span>  
 <span data-ttu-id="0e615-175">Sie haben erfolgreich einen Datenfilter für die Datentabelle erstellt, die Sie für den untergeordneten Bericht definiert haben.</span><span class="sxs-lookup"><span data-stu-id="0e615-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="0e615-176">Als Nächstes werden Sie die Websiteanwendung erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e615-176">Next, you will build and run the website application.</span></span>  
  
  
