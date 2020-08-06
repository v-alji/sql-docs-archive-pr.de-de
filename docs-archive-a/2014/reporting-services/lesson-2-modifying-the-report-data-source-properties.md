---
title: 'Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609727"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="8c90b-102">Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle</span><span class="sxs-lookup"><span data-stu-id="8c90b-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="8c90b-103">In dieser Lektion verwenden Sie den Berichts-Manager für die Auswahl eines Berichts, der an Empfänger übermittelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c90b-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="8c90b-104">Das datengesteuerte Abonnement, das Sie definieren, verteilt den im Tutorial **Erstellen eines einfachen Tabellenberichts &amp;#40;SSRS-Tutorial&amp;#41;** erstellten Bericht [Erstellen eines einfachen Tabellenberichts &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8c90b-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="8c90b-105">In den folgenden Schritten wird erläutert, wie Sie die Datenquellen-Verbindungsinformationen ändern, die vom Bericht zum Abrufen von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c90b-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="8c90b-106">Nur Berichte, die **gespeicherte Anmeldeinformationen** für das Zugreifen auf eine Berichtsdatenquelle verwenden, können über ein datengesteuertes Abonnement verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="8c90b-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="8c90b-107">Für die unbeaufsichtigte Berichtsverarbeitung sind gespeicherte Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c90b-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="8c90b-108">Sie ändern auch das Dataset und den Bericht, um einen Parameter zu verwenden, mit dem der Bericht nach `[Order]` gefiltert wird, damit das Abonnement verschiedene Instanzen des Berichts für bestimmte Aufträge und Renderingformate ausgeben kann.</span><span class="sxs-lookup"><span data-stu-id="8c90b-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="8c90b-109">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="8c90b-109">**In this topic:**</span></span>

-   [<span data-ttu-id="8c90b-110">So ändern Sie die Datenquelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c90b-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="8c90b-111">So ändern Sie den AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="8c90b-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="8c90b-112">So fügen Sie einen Berichtsparameter hinzu und veröffentlichen den Bericht erneut</span><span class="sxs-lookup"><span data-stu-id="8c90b-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="8c90b-113">So stellen Sie den Bericht erneut bereit</span><span class="sxs-lookup"><span data-stu-id="8c90b-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="8c90b-114">So ändern Sie die Datenquellen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c90b-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="8c90b-115">Starten Sie [Berichts-Manager &#40;SSRS im einheitlichen&#41;Modus](../../2014/reporting-services/report-manager-ssrs-native-mode.md) mit Administratorrechten, indem Sie z. b. mit der rechten Maustaste auf das Symbol für Internet Explorer und dann auf **als Administrator ausführen**klicken.</span><span class="sxs-lookup"><span data-stu-id="8c90b-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8c90b-116">Navigieren Sie zu dem Ordner, der den Bericht **Sales Orders** enthält, und klicken Sie im Kontextmenü des Berichts auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="8c90b-117">![Öffnen des Berichtskontextmenüs und Auswählen von "Verwalten"](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Öffnen des Berichtskontextmenüs und Auswählen von "Verwalten"")</span><span class="sxs-lookup"><span data-stu-id="8c90b-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="8c90b-118">Klicken Sie auf die Registerkarte **Datenquellen** .</span><span class="sxs-lookup"><span data-stu-id="8c90b-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="8c90b-119">Wählen Sie unter **Verbindungstyp**die Option **Microsoft SQL Server**aus.</span><span class="sxs-lookup"><span data-stu-id="8c90b-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="8c90b-120">Die benutzerdefinierte Datenquellenverbindungszeichenfolge lautet wie folgt (es wird vorausgesetzt, dass sich die Beispieldatenbank auf einem lokalen Datenbankserver befindet):</span><span class="sxs-lookup"><span data-stu-id="8c90b-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="8c90b-121">Klicken Sie auf **Anmeldeinformationen, die sicher im Berichtsserver gespeichert sind**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="8c90b-122">Geben Sie Ihren Benutzernamen (verwenden Sie das Format *domain\user*) und Ihr Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8c90b-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="8c90b-123">Wenn Sie über keine Zugriffsberechtigung für die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank verfügen, geben Sie eine gültige Anmeldung an.</span><span class="sxs-lookup"><span data-stu-id="8c90b-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="8c90b-124">Aktivieren Sie das Kontrollkästchen **Als Windows-Anmeldeinformationen verwenden, wenn eine Verbindung zur Datenquelle hergestellt wird**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="8c90b-125">Wenn Sie kein Domänenkonto verwenden (wenn Sie z. B. mit einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldung arbeiten), aktivieren Sie dieses Kontrollkästchen nicht.</span><span class="sxs-lookup"><span data-stu-id="8c90b-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="8c90b-126">Klicken Sie auf **Verbindung testen** , um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c90b-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="8c90b-127">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-127">Click **Apply**.</span></span>

11. <span data-ttu-id="8c90b-128">Zeigen Sie den Bericht an, um zu überprüfen, ob er mit den von Ihnen angegebenen Anmeldeinformationen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c90b-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="8c90b-129">Um den Bericht anzuzeigen, klicken Sie auf die Registerkarte **Ansicht** . Beachten Sie, dass nach dem Öffnen des Berichts ein Mitarbeiter Name ausgewählt werden muss. Klicken Sie dann auf die Schaltfläche **Bericht anzeigen** , um den Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c90b-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="8c90b-130">So ändern Sie das AdventureWorksDataSet</span><span class="sxs-lookup"><span data-stu-id="8c90b-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="8c90b-131">Öffnen Sie den Bericht "Sales Orders" in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c90b-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="8c90b-132">Klicken Sie mit der rechten Maustaste auf das Dataset `AdventureWorksDataset` und anschließend auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="8c90b-133">Fügen Sie die Anweisung `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` vor der Anweisung `Group By` hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c90b-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="8c90b-134">Die vollständige Abfragesyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8c90b-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="8c90b-135">Klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="8c90b-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="8c90b-136">So fügen Sie einen Berichts Parameter hinzu und veröffentlichen den Bericht erneut</span><span class="sxs-lookup"><span data-stu-id="8c90b-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="8c90b-137">Klicken Sie im **Berichtsdatenbereich** auf **Neu** und anschließend auf **Parameter...**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="8c90b-138">Geben Sie in **Name**den Namen `OrderNumber`ein.</span><span class="sxs-lookup"><span data-stu-id="8c90b-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="8c90b-139">Geben Sie in **Eingabeaufforderung**`OrderNumber`ein.</span><span class="sxs-lookup"><span data-stu-id="8c90b-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="8c90b-140">Wählen Sie **Leeren Wert zulassen ("")** aus.</span><span class="sxs-lookup"><span data-stu-id="8c90b-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="8c90b-141">Wählen Sie **NULL-Wert zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="8c90b-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="8c90b-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-142">Click **OK**.</span></span> <span data-ttu-id="8c90b-143">Dem **Berichtsdatenbereich** wird der Parameter hinzugefügt, und er entspricht der folgenden Abbildung:</span><span class="sxs-lookup"><span data-stu-id="8c90b-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="8c90b-144">![Der neue Parameter wird dem Berichtsdatenbereich hinzugefügt](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "Der neue Parameter wird dem Berichtsdatenbereich hinzugefügt")</span><span class="sxs-lookup"><span data-stu-id="8c90b-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="8c90b-145">Klicken Sie auf die Registerkarte **Vorschau** , um den Bericht auszuführen. Beachten Sie das Parametereingabefeld am oberen Rand des Berichts.</span><span class="sxs-lookup"><span data-stu-id="8c90b-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="8c90b-146">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="8c90b-146">You can either:</span></span>

    -   <span data-ttu-id="8c90b-147">Klicken Sie auf "Bericht anzeigen", um den vollständigen Bericht zu sehen, ohne einen Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c90b-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="8c90b-148">Deaktivieren Sie die Null-Option, und geben Sie eine Auftragsnummer ein, z. B. so71949, um nur die einen Auftrag im Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8c90b-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="8c90b-149">![Berichts-Viewer mit sichtbarem Parameterbereich](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Berichts-Viewer mit sichtbarem Parameterbereich")</span><span class="sxs-lookup"><span data-stu-id="8c90b-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="8c90b-150">Stellen Sie den Bericht erneut bereit, damit bei der Abonnementkonfiguration in der nächsten Lektion die in dieser Lektion vorgenommenen Änderungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c90b-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="8c90b-151">Weitere Informationen zu den Projekteigenschaften, die im Tabellentutorial verwendet werden, finden Sie im Abschnitt „So veröffentlichen Sie den Bericht auf dem Berichtsserver (Optional)“ in [Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="8c90b-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="8c90b-152">So stellen Sie den Bericht erneut bereit</span><span class="sxs-lookup"><span data-stu-id="8c90b-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="8c90b-153">Stellen Sie den Bericht erneut bereit, damit bei der Abonnementkonfiguration in der nächsten Lektion die in dieser Lektion vorgenommenen Änderungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c90b-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="8c90b-154">Weitere Informationen zu den Projekteigenschaften, die im Tabellentutorial verwendet werden, finden Sie im Abschnitt „So veröffentlichen Sie den Bericht auf dem Berichtsserver (Optional)“ in [Lektion 6: Hinzufügen von Gruppierungen und Gesamtwerten &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="8c90b-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="8c90b-155">Klicken Sie auf der Symbolleiste auf **Erstellen** , und klicken Sie dann auf **Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="8c90b-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c90b-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8c90b-156">Next Steps</span></span>
 <span data-ttu-id="8c90b-157">Sie haben damit erfolgreich den Bericht so konfiguriert, dass er beim Abrufen von Daten gespeicherte Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c90b-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="8c90b-158">Als Nächstes geben Sie das Abonnement mit den Seiten für datengesteuerte Abonnements im Berichts-Manager an.</span><span class="sxs-lookup"><span data-stu-id="8c90b-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="8c90b-159">Siehe [Lektion 3: Definieren eines datengesteuerten Abonnements](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="8c90b-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c90b-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c90b-160">See Also</span></span>
 <span data-ttu-id="8c90b-161">[Verwalten von Berichtsdaten Quellen](report-data/manage-report-data-sources.md) [Angeben von Anmelde Informationen und Verbindungsinformationen für Berichtsdaten Quellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Erstellen eines datengesteuerten Abonnements &#40;SSRS](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) -Lernprogramm&#41;[Erstellen eines einfachen Tabellen Berichts &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="8c90b-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


