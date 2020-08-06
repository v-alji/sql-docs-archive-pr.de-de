---
title: Hinzufügen von kaskadierenden Parametern zu einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 3a22eec3-57a7-478e-b6fc-102a9dbe0591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5419d448b2fa9526224e1bccd80d5c195e2763d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696409"
---
# <a name="add-cascading-parameters-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="aa961-102">Hinzufügen von kaskadierenden Parametern zu einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="aa961-102">Add Cascading Parameters to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="aa961-103">Kaskadierende Parameter ermöglichen das Verwalten großer Berichtsdatenmengen.</span><span class="sxs-lookup"><span data-stu-id="aa961-103">Cascading parameters provide a way of managing large amounts of report data.</span></span> <span data-ttu-id="aa961-104">Sie können einen Satz von abhängigen Parametern definieren, sodass die Liste der Werte für einen Parameter von dem Wert abhängt, der in einem anderen Parameter ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-104">You can define a set of related parameters so that the list of values for one parameter depends on the value chosen in another parameter.</span></span> <span data-ttu-id="aa961-105">Der erste Parameter ist beispielsweise unabhängig und stellt eine Liste von Produktkategorien dar.</span><span class="sxs-lookup"><span data-stu-id="aa961-105">For example, the first parameter is independent and might present a list of product categories.</span></span> <span data-ttu-id="aa961-106">Wenn der Benutzer eine Kategorie auswählt, hängt der zweite Parameter vom Wert des ersten Parameters ab.</span><span class="sxs-lookup"><span data-stu-id="aa961-106">When the user selects a category, the second parameter is dependent on the value of the first parameter.</span></span> <span data-ttu-id="aa961-107">Seine Werte werden mit einer Liste von Unterkategorien innerhalb der ausgewählten Kategorie aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aa961-107">Its values are updated with a list of subcategories within the chosen category.</span></span> <span data-ttu-id="aa961-108">Wenn der Benutzer den Bericht anzeigt, werden die Berichtsdaten mit den Parameterwerten für die Kategorie und die Unterkategorien gefiltert.</span><span class="sxs-lookup"><span data-stu-id="aa961-108">When the user views the report, the values for both the category and subcategory parameters are used to filter report data.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="aa961-109">Zum Erstellen von kaskadierenden Parametern definieren Sie zunächst die Datasetabfrage und binden einen Abfrageparameter für jeden benötigten kaskadierenden Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="aa961-109">To create cascading parameters, you define the dataset query first and include a query parameter for each cascading parameter that you need.</span></span> <span data-ttu-id="aa961-110">Außerdem müssen Sie ein separates Dataset für jeden kaskadierenden Parameter erstellen, um verfügbare Werte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="aa961-110">You must also create a separate dataset for each cascading parameter to provide available values.</span></span> <span data-ttu-id="aa961-111">Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter (Berichts-Generator und SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="aa961-111">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
 <span data-ttu-id="aa961-112">Die Reihenfolge ist für kaskadierende Parameter relevant, da die Datasetabfrage für einen Parameter weiter unten in der Liste einen Verweis auf jeden Parameter weiter oben in der Liste enthält.</span><span class="sxs-lookup"><span data-stu-id="aa961-112">Order is important for cascading parameters because the dataset query for a parameter later in the list includes a reference to each parameter that is earlier in the list.</span></span> <span data-ttu-id="aa961-113">Zur Laufzeit bestimmt die Reihenfolge der Parameter im Berichtsdatenbereich die Reihenfolge, in der Parameterabfragen im Bericht aufgeführt werden, und damit die Reihenfolge, in der Benutzer die einzelnen aufeinander folgenden Parameterwerte auswählen.</span><span class="sxs-lookup"><span data-stu-id="aa961-113">At run time, the order of the parameters in the Report Data pane determines the order in which the parameter queries appear in the report, and therefore, the order in which a user chooses each successive parameter value.</span></span>  
  
 <span data-ttu-id="aa961-114">Informationen zum Erstellen von kaskadierenden Parametern mit mehreren Werten und einschließlich der Funktion "Alle auswählen" finden Sie unter [Informationen zu einem mehrwertigen, kaskadierenden Parameter vom Typ &lt;legacyBold&gt;Alle auswählen&lt;/legacyBold&gt;](https://go.microsoft.com/fwlink/?LinkId=184757).</span><span class="sxs-lookup"><span data-stu-id="aa961-114">For information about creating cascading parameters with multiple values and including the Select All feature, see [How to have a Select All Multivalue Cascading Parameter](https://go.microsoft.com/fwlink/?LinkId=184757).</span></span>  
  
### <a name="to-create-the-main-dataset-with-a-query-that-includes-multiple-related-parameters"></a><span data-ttu-id="aa961-115">So erstellen Sie das Hauptdataset mit einer Abfrage, die mehrere abhängige Parameter enthält</span><span class="sxs-lookup"><span data-stu-id="aa961-115">To create the main dataset with a query that includes multiple related parameters</span></span>  
  
1.  <span data-ttu-id="aa961-116">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf eine Datenquelle, und klicken Sie anschließend auf **Dataset hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-116">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="aa961-117">Geben Sie unter **Name**den Namen des Datasets ein.</span><span class="sxs-lookup"><span data-stu-id="aa961-117">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="aa961-118">Wählen Sie in **Datenquelle**den Namen der Datenquelle aus, oder klicken Sie auf **Neu** , um eine Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa961-118">In **Data source**, choose the name of the data source or click **New** to create one.</span></span>  
  
4.  <span data-ttu-id="aa961-119">Wählen Sie in **Abfragetyp**den Abfragetyp für die ausgewählte Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="aa961-119">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="aa961-120">In diesem Thema wird angenommen, dass der Abfragetyp **Text** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-120">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="aa961-121">Geben Sie in **Abfrage**die Abfrage ein, mit der die Daten für diesen Bericht abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa961-121">In **Query**, type the query to use to retrieve data for this report.</span></span> <span data-ttu-id="aa961-122">Die Abfrage muss die folgenden Teile enthalten:</span><span class="sxs-lookup"><span data-stu-id="aa961-122">The query must include the following parts:</span></span>  
  
    1.  <span data-ttu-id="aa961-123">Eine Liste mit Datenquellenfeldern.</span><span class="sxs-lookup"><span data-stu-id="aa961-123">A list of data source fields.</span></span> <span data-ttu-id="aa961-124">In einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung gibt beispielsweise die SELECT-Anweisung eine Liste mit den Namen aller Datenbankspalten aus einer bestimmten Tabelle oder Sicht an.</span><span class="sxs-lookup"><span data-stu-id="aa961-124">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, the SELECT statement specifies a list of database column names from a given table or view.</span></span>  
  
    2.  <span data-ttu-id="aa961-125">Einen Abfrageparameter für jeden kaskadierenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="aa961-125">One query parameter for each cascading parameter.</span></span> <span data-ttu-id="aa961-126">Ein Abfrageparameter beschränkt die von der Datenquelle abgerufenen Daten, indem bestimmte Werte angegeben werden, die in die Abfrage eingebunden bzw. von dieser ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa961-126">A query parameter limits the data retrieved from the data source by specifying certain values to include or exclude from the query.</span></span> <span data-ttu-id="aa961-127">Typischerweise sind Abfrageparameter in einer Einschränkungsklausel in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="aa961-127">Typically, query parameters occur in a restriction clause in the query.</span></span> <span data-ttu-id="aa961-128">In einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -SELECT-Anweisung sind Abfrageparameter beispielsweise in der WHERE-Klausel enthalten.</span><span class="sxs-lookup"><span data-stu-id="aa961-128">For example, in a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement, query parameters occur in the WHERE clause.</span></span> <span data-ttu-id="aa961-129">Weitere Informationen finden Sie unter "Filtern von Zeilen mithilfe von WHERE und HAVING" in der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dokumentation in der [SQL Server-Onlinedokumentation](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="aa961-129">For more information, see "Filtering Rows by Using WHERE and HAVING" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
6.  <span data-ttu-id="aa961-130">Klicken Sie auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="aa961-130">Click **Run** (**!**).</span></span> <span data-ttu-id="aa961-131">Nachdem Sie die Abfrageparameter eingebunden und anschließend die Abfrage ausgeführt haben, werden automatisch Berichtsparameter erstellt, die den Abfrageparametern entsprechen.</span><span class="sxs-lookup"><span data-stu-id="aa961-131">After you include query parameters and then run the query, report parameters that correspond to the query parameters are automatically created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa961-132">Die Reihenfolge von Abfrageparametern beim erstmaligen Ausführen einer Abfrage bestimmt die Reihenfolge, in der sie im Bericht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa961-132">The order of query parameters the first time you run a query determines the order that they are created in the report.</span></span> <span data-ttu-id="aa961-133">Informationen zum Ändern der Reihenfolge finden Sie unter [Ändern der Reihenfolge von Berichtsparametern (Berichts-Generator und SSRS)](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="aa961-133">To change the order, see [Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="aa961-134">Anschließend erstellen Sie ein Dataset, das die Werte für den unabhängigen Parameter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-134">Next, you will create a dataset that provides the values for the independent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-an-independent-parameter"></a><span data-ttu-id="aa961-135">So erstellen Sie ein Dataset zum Bereitstellen von Werten für einen unabhängigen Parameter</span><span class="sxs-lookup"><span data-stu-id="aa961-135">To create a dataset to provide values for an independent parameter</span></span>  
  
1.  <span data-ttu-id="aa961-136">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf eine Datenquelle, und klicken Sie anschließend auf **Dataset hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-136">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="aa961-137">Geben Sie unter **Name**den Namen des Datasets ein.</span><span class="sxs-lookup"><span data-stu-id="aa961-137">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="aa961-138">Vergewissern Sie sich, dass der Name in **Datenquelle**dem Namen der Datenquelle entspricht, die in Schritt 1 ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-138">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="aa961-139">Wählen Sie in **Abfragetyp**den Abfragetyp für die ausgewählte Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="aa961-139">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="aa961-140">In diesem Thema wird angenommen, dass der Abfragetyp **Text** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-140">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="aa961-141">Geben Sie in **Abfrage**die Abfrage ein, mit der Werte für diesen Parameter abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa961-141">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="aa961-142">Abfragen für unabhängige Parameter enthalten normalerweise keine Abfrageparameter.</span><span class="sxs-lookup"><span data-stu-id="aa961-142">Queries for independent parameters typically do not contain query parameters.</span></span> <span data-ttu-id="aa961-143">Wenn Sie z. B. eine Abfrage für einen Parameter erstellen möchten, der alle Kategoriewerte bereitstellt, können Sie eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wie die Folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="aa961-143">For example, to create a query for a parameter that provides all category values, you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT <column name> FROM <table>  
    ```  
  
     <span data-ttu-id="aa961-144">Der SELECT DISTINCT-Befehl entfernt doppelte Werte aus dem Resultset, sodass Sie die einzelnen eindeutigen Werte aus der angegebenen Spalte in der angegebenen Tabelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="aa961-144">The SELECT DISTINCT command removes duplicate values from the result set so that you get each unique value from the specified column in the specified table.</span></span>  
  
     <span data-ttu-id="aa961-145">Klicken Sie auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="aa961-145">Click **Run** (**!**).</span></span> <span data-ttu-id="aa961-146">Im Resultset werden die Werte angezeigt, die für diesen ersten Parameter verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aa961-146">The result set shows the values that are available for this first parameter.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="aa961-147">Anschließend legen Sie die Eigenschaften des ersten Parameters fest, um mit diesem Dataset zur Laufzeit die verfügbaren Werte aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="aa961-147">Next, you will set the properties of the first parameter to use this dataset to populate its available values at run-time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="aa961-148">So legen Sie verfügbare Werte für einen Berichtsparameter fest</span><span class="sxs-lookup"><span data-stu-id="aa961-148">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="aa961-149">Klicken Sie im Berichtsdatenbereich im Ordner „Parameter“ mit der rechten Maustaste auf den ersten Parameter, und klicken Sie anschließend auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="aa961-149">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="aa961-150">Vergewissern Sie sich, dass in **Name**der korrekte Name des Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="aa961-150">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="aa961-151">Klicken Sie auf **Verfügbare Werte**.</span><span class="sxs-lookup"><span data-stu-id="aa961-151">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="aa961-152">Klicken Sie auf **Werte aus Abfrage abrufen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-152">Click **Get values from a query**.</span></span> <span data-ttu-id="aa961-153">Es werden drei Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aa961-153">Three fields appear.</span></span>  
  
5.  <span data-ttu-id="aa961-154">Klicken Sie in **Dataset**in der Dropdownliste auf den Namen des Datasets, das Sie in der vorherigen Prozedur erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="aa961-154">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="aa961-155">Klicken Sie im Feld **Wert** auf den Namen des Felds, das den Parameterwert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-155">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="aa961-156">Klicken Sie im Feld **Bezeichnung** auf den Namen des Felds, das die Parameterbezeichnung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-156">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="aa961-157">Nun erstellen Sie ein Dataset, das die Werte für einen abhängigen Parameter bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-157">Next, you will create a dataset that provides the values for a dependent parameter.</span></span>  
  
### <a name="to-create-a-dataset-to-provide-values-for-a-dependent-parameter"></a><span data-ttu-id="aa961-158">So erstellen Sie ein Dataset zum Bereitstellen von Werten für einen abhängigen Parameter</span><span class="sxs-lookup"><span data-stu-id="aa961-158">To create a dataset to provide values for a dependent parameter</span></span>  
  
1.  <span data-ttu-id="aa961-159">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf eine Datenquelle, und klicken Sie anschließend auf **Dataset hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-159">In the Report Data pane, right-click a data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="aa961-160">Geben Sie unter **Name**den Namen des Datasets ein.</span><span class="sxs-lookup"><span data-stu-id="aa961-160">In **Name**, type the name of the dataset.</span></span>  
  
3.  <span data-ttu-id="aa961-161">Vergewissern Sie sich, dass der Name in **Datenquelle**dem Namen der Datenquelle entspricht, die in Schritt 1 ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-161">In **Data source**, verify the name is the name of the data source you chose in step 1.</span></span>  
  
4.  <span data-ttu-id="aa961-162">Wählen Sie in **Abfragetyp**den Abfragetyp für die ausgewählte Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="aa961-162">In **Query type**, choose the type of query for the selected data source.</span></span> <span data-ttu-id="aa961-163">In diesem Thema wird angenommen, dass der Abfragetyp **Text** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-163">In this topic, query type **Text** is assumed.</span></span>  
  
5.  <span data-ttu-id="aa961-164">Geben Sie in **Abfrage**die Abfrage ein, mit der Werte für diesen Parameter abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa961-164">In **Query**, type the query to use to retrieve values for this parameter.</span></span> <span data-ttu-id="aa961-165">Abfragen für abhängige Parameter enthalten normalerweise Abfrageparameter für jeden Parameter, von dem der betreffende Parameter abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="aa961-165">Queries for dependent parameters typically include query parameters for each parameter that this parameter is dependent on.</span></span> <span data-ttu-id="aa961-166">Wenn Sie beispielsweise eine Abfrage für einen Parameter erstellen möchten, der alle Unterkategoriewerte (abhängiger Parameter) für eine Kategorie (unabhängiger Parameter) bereitstellt, können Sie eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung wie die Folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="aa961-166">For example, to create a query for a parameter that provides all subcategory (dependent parameter) values for a category (independent parameter), you might use a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement similar to the following:</span></span>  
  
    ```  
    SELECT DISTINCT Subcategory FROM <table>   
    WHERE (Category = @Category)  
    ```  
  
     <span data-ttu-id="aa961-167">In der WHERE-Klausel ist Category der Name eines Felds aus, \<table> und @Category ist ein Abfrage Parameter.</span><span class="sxs-lookup"><span data-stu-id="aa961-167">In the WHERE clause, Category is the name of a field from \<table> and @Category is a query parameter.</span></span> <span data-ttu-id="aa961-168">Diese Anweisung erstellt eine Liste von Unterkategorien für die in @Category angegebene Kategorie.</span><span class="sxs-lookup"><span data-stu-id="aa961-168">This statement produces a list of subcategories for the category specified in @Category.</span></span> <span data-ttu-id="aa961-169">Zur Laufzeit wird dieser Wert mit dem Wert ausgefüllt, der vom Benutzer für den Berichtsparameter mit demselben Namen ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="aa961-169">At run time, this value will be filled in with the value that the user chooses for the report parameter that has the same name.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="aa961-170">Anschließend legen Sie die Eigenschaften des zweiten Parameters fest, um mit diesem Dataset zur Laufzeit die verfügbaren Werte aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="aa961-170">Next, you will set the properties of the second parameter to use this dataset to populate its available values at run time.</span></span>  
  
### <a name="to-set-available-values-for-a-report-parameter"></a><span data-ttu-id="aa961-171">So legen Sie verfügbare Werte für einen Berichtsparameter fest</span><span class="sxs-lookup"><span data-stu-id="aa961-171">To set available values for a report parameter</span></span>  
  
1.  <span data-ttu-id="aa961-172">Klicken Sie im Berichtsdatenbereich im Ordner „Parameter“ mit der rechten Maustaste auf den ersten Parameter, und klicken Sie anschließend auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="aa961-172">In the Report Data pane, in the Parameters folder, right-click the first parameter, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="aa961-173">Vergewissern Sie sich, dass in **Name**der korrekte Name des Parameters angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="aa961-173">In **Name**, verify that the name of the parameter is correct.</span></span>  
  
3.  <span data-ttu-id="aa961-174">Klicken Sie auf **Verfügbare Werte**.</span><span class="sxs-lookup"><span data-stu-id="aa961-174">Click **Available Values**.</span></span>  
  
4.  <span data-ttu-id="aa961-175">Klicken Sie auf **Werte aus Abfrage abrufen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-175">Click **Get values from a query**.</span></span>  
  
5.  <span data-ttu-id="aa961-176">Klicken Sie in **Dataset**in der Dropdownliste auf den Namen des Datasets, das Sie in der vorherigen Prozedur erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="aa961-176">In **Dataset**, from the drop-down list, click the name of the dataset you created in the previous procedure.</span></span>  
  
6.  <span data-ttu-id="aa961-177">Klicken Sie im Feld **Wert** auf den Namen des Felds, das den Parameterwert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-177">In **Value** field, click the name of the field that provides the parameter value.</span></span>  
  
7.  <span data-ttu-id="aa961-178">Klicken Sie im Feld **Bezeichnung** auf den Namen des Felds, das die Parameterbezeichnung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa961-178">In **Label** field, click the name of the field that provides the parameter label.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-cascading-parameters"></a><span data-ttu-id="aa961-179">So testen Sie die kaskadierenden Parameter</span><span class="sxs-lookup"><span data-stu-id="aa961-179">To test the cascading parameters</span></span>  
  
1.  <span data-ttu-id="aa961-180">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-180">Click **Run**.</span></span>  
  
2.  <span data-ttu-id="aa961-181">Wählen Sie in der Dropdownliste für den ersten unabhängigen Parameter einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="aa961-181">From the drop-down list for the first, independent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="aa961-182">Der Berichtsprozessor führt die Datasetabfrage für den nächsten Parameter aus und übergibt den Wert, den Sie für den ersten Parameter ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="aa961-182">The report processor runs the dataset query for the next parameter and passes it the value you chose for the first parameter.</span></span> <span data-ttu-id="aa961-183">Die Dropdownliste für den zweiten Parameter wird mit den verfügbaren Werten gefüllt, die auf dem Wert des ersten Parameters beruhen.</span><span class="sxs-lookup"><span data-stu-id="aa961-183">The drop-down list for the second parameter is populated with the available values based on the first parameter value.</span></span>  
  
3.  <span data-ttu-id="aa961-184">Wählen Sie in der Dropdownliste für den zweiten, abhängigen Parameter einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="aa961-184">From the drop-down list for the second, dependent parameter, choose a value.</span></span>  
  
     <span data-ttu-id="aa961-185">Der Bericht wird nach dem Auswählen des letzten Parameters nicht automatisch ausgeführt, sodass Sie eine andere Auswahl vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="aa961-185">The report does not run automatically after you choose the last parameter so that you can change your choice.</span></span>  
  
4.  <span data-ttu-id="aa961-186">Klicken Sie auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="aa961-186">Click **View Report**.</span></span> <span data-ttu-id="aa961-187">Die Anzeige des Berichts wird mit den ausgewählten Parametern aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="aa961-187">The report updates the display based on the parameters you have chosen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa961-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa961-188">See Also</span></span>  
 <span data-ttu-id="aa961-189">[Hinzufügen, ändern oder Löschen eines Berichts Parameters &#40;Berichts-Generator und SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="aa961-189">[Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="aa961-190">[Berichts Parameter &#40;Berichts-Generator und Berichts-Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="aa961-190">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="aa961-191">[Tutorial: Hinzufügen eines Parameters zu einem Bericht &#40;Berichts-Generator&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="aa961-191">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="aa961-192">[Lernprogramme &#40;Berichts-Generator&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="aa961-192">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="aa961-193">[Hinzufügen von datasetfiltern, Datenbereichs Filtern und Gruppen Filtern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="aa961-193">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 [<span data-ttu-id="aa961-194">Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa961-194">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
