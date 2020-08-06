---
title: Erstellen eines freigegebenen Datasets oder eingebetteten Datasets (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696473"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="c0f57-102">Erstellen eines freigegebenen Datasets oder eingebetteten Datasets (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c0f57-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c0f57-103">Sie können ein eingebettetes Dataset zur Verwendung in einem einzelnen Bericht oder ein freigegebenes Dataset erstellen, das auf einem Berichtsserver gespeichert und von mehreren Berichten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0f57-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="c0f57-104">Damit Sie ein Dataset erstellen können, muss eine eingebettete oder freigegebene Datenquelle vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="c0f57-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="c0f57-105">Verwenden Sie Berichts-Generator für folgende Tasks:</span><span class="sxs-lookup"><span data-stu-id="c0f57-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="c0f57-106">Erstellen eines freigegebenen Datasets in der Datasetentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="c0f57-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="c0f57-107">Für freigegebene Datasets müssen veröffentlichte freigegebene Datenquellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0f57-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="c0f57-108">Erstellen eines eingebetteten Datasets in der Berichtsentwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="c0f57-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="c0f57-109">Speichern Sie das Dataset direkt auf dem Berichtsserver oder der SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="c0f57-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="c0f57-110">Verwenden Sie Berichts-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , um die folgenden Tasks auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c0f57-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="c0f57-111">Erstellen Sie im Projektmappen-Explorer ein freigegebenes Dataset.</span><span class="sxs-lookup"><span data-stu-id="c0f57-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="c0f57-112">Für freigegebene Datasets müssen Datenquellen aus dem Ordner Freigegebene Datenquellen im Projektmappen-Explorer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0f57-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="c0f57-113">Erstellen Sie im Berichtsdatenbereich ein eingebettetes Dataset.</span><span class="sxs-lookup"><span data-stu-id="c0f57-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="c0f57-114">Stellen Sie die freigegebenen Datasets und freigegebene Datenquelle mit dem Bericht optional bereit.</span><span class="sxs-lookup"><span data-stu-id="c0f57-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="c0f57-115">Verwenden Sie für jeden Elementtyp Projekteigenschaften, um Pfade zu Ordnern auf dem Berichtsserver oder einer SharePoint-Website anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0f57-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="c0f57-116">Weitere Informationen finden Sie unter [Erstellen von Berichten zu eingebetteten und freigegebenen Datasets &#40;Berichts-Generator und SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c0f57-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="c0f57-117">So öffnen Sie den Berichts-Generator und erstellen ein freigegebenes Dataset</span><span class="sxs-lookup"><span data-stu-id="c0f57-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="c0f57-118">So öffnen Sie den Berichts-Generator.</span><span class="sxs-lookup"><span data-stu-id="c0f57-118">Open Report Builder.</span></span> <span data-ttu-id="c0f57-119">Der Bereich **Neuer Bericht oder neues Dataset** wird geöffnet, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c0f57-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="c0f57-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="c0f57-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c0f57-121">Wenn der Bereich **Neuer Bericht oder neues Dataset** nicht angezeigt wird, klicken Sie in der Schaltfläche „Berichts-Generator“ auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="c0f57-122">Klicken Sie im linken Bereich unter **Dataset erstellen**auf **Freigegebenes Dataset**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="c0f57-123">Klicken Sie im rechten Bereich auf **Durchsuchen** , um eine freigegebene Datenquelle vom Berichtsserver auszuwählen, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="c0f57-124">Der mit der freigegebenen Datenquelle verknüpfte Abfrage-Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c0f57-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="c0f57-125">Geben Sie im Abfrage-Designer die Felder an, die in das Dataset einbezogen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="c0f57-126">Klicken Sie auf **Ausführen** (**!**), um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="c0f57-127">Klicken Sie in der Schaltfläche **Berichts-Generator** auf **Speichern** oder **Speichern unter** , um das freigegebene Dataset auf dem Berichtsserver zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c0f57-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="c0f57-128">Um den Berichts-Generator zu beenden, klicken Sie auf **Berichts-Generator**und dann auf **Berichts-Generator beenden**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="c0f57-129">Um mit Berichten zu arbeiten, klicken Sie auf **Berichts-Generator**und dann auf **Neu** oder **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="c0f57-130">So legen Sie Abfrageparameteroptionen fest</span><span class="sxs-lookup"><span data-stu-id="c0f57-130">To set query parameter options</span></span>

1.  <span data-ttu-id="c0f57-131">So öffnen Sie den Berichts-Generator.</span><span class="sxs-lookup"><span data-stu-id="c0f57-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="c0f57-132">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-132">Click **Open**.</span></span>

3.  <span data-ttu-id="c0f57-133">Wechseln Sie zum Berichtsserver, und wählen Sie den Ordner für die freigegebene Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="c0f57-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="c0f57-134">Klicken Sie unter **Elemente des Typs**in der Dropdownliste auf „Datasets (\*.rsd)“.</span><span class="sxs-lookup"><span data-stu-id="c0f57-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="c0f57-135">Wählen Sie das freigegebene Dataset aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="c0f57-136">Der verknüpfte Abfrage-Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c0f57-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="c0f57-137">Klicken Sie im Menüband auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="c0f57-138">Klicken Sie auf **Parameter**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-138">Click **Parameters**.</span></span> <span data-ttu-id="c0f57-139">Legen Sie auf dieser Seite als Standardwert eine Konstante oder einen Ausdruck fest, markieren Sie den Parameter als schreibgeschützt, auf NULL festlegbar oder mit **In Abfrage auslassen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="c0f57-140">Weitere Informationen finden Sie unter [Dataseteigenschaften &#40;Dialogfeld, Parameter, Berichts-Generator&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c0f57-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="c0f57-141">So erstellen Sie ein Dataset aus einer relationalen SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="c0f57-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="c0f57-142">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf den Namen der Datenquelle, und klicken Sie dann auf **Dataset hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c0f57-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="c0f57-143">Die Seite **Abfrage** des Dialogfelds **Dataseteigenschaften** wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="c0f57-144">Geben Sie im Textfeld **Name**einen Namen für das Dataset ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c0f57-145">Der Name des Datasets wird intern im Bericht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0f57-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="c0f57-146">Zur Verdeutlichung sollte der Name des Datasets die Daten beschreiben, die von der Abfrage zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0f57-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="c0f57-147">Wählen Sie aus der Liste **Datenquelle**eine vorhandene freigegebene Datenquelle aus, oder klicken Sie auf **Neu** , um eine neue eingebettete Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="c0f57-148">Wählen Sie einen **Abfragetyp** .</span><span class="sxs-lookup"><span data-stu-id="c0f57-148">Select a **Query type** option.</span></span> <span data-ttu-id="c0f57-149">Die verfügbaren Optionen sind vom Datenquellentyp abhängig.</span><span class="sxs-lookup"><span data-stu-id="c0f57-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="c0f57-150">Wählen Sie **Text** aus, um eine Abfrage zu schreiben, die die Abfragesprache der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0f57-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="c0f57-151">Wählen Sie **Table** aus, um alle Felder in einer relationalen Datenbanktabelle zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0f57-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="c0f57-152">Wählen Sie **Gespeicherte Prozedur** , um eine gespeicherte Prozedur nach Namen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="c0f57-153">Geben Sie in **Abfrage**die Abfrage, die gespeicherte Prozedur oder den Tabellennamen ein.</span><span class="sxs-lookup"><span data-stu-id="c0f57-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="c0f57-154">Oder klicken Sie auf **Abfrage-Designer** , um den grafischen oder textbasierten Abfrage-Designer zu öffnen, oder auf **Importieren** , um die Abfrage aus einem vorhandenen Bericht zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c0f57-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="c0f57-155">In einigen Fällen kann die von der Abfrage angegebene Feldauflistung nur durch Anwendung der Abfrage auf die Datenquelle ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="c0f57-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="c0f57-156">Eine gespeicherte Prozedur gibt möglicherweise im Resultset eine variable Feldauflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="c0f57-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="c0f57-157">Klicken Sie auf **Felder aktualisieren** , um die Abfrage auf die Datenquelle anzuwenden und die Feldnamen abzurufen, die erforderlich sind, um die Dataset-Feldauflistung im Berichtsdatenbereich aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="c0f57-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="c0f57-158">Die Feldauflistung wird unter dem Datasetknoten angezeigt, nachdem Sie das Dialogfeld **Dataseteigenschaften** geschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="c0f57-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="c0f57-159">Geben Sie in das Feld **Timeout**die Anzahl der Sekunden ein, die der Berichtsserver auf eine Antwort von der Datenbank warten soll.</span><span class="sxs-lookup"><span data-stu-id="c0f57-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="c0f57-160">Der Standardwert beträgt 0 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c0f57-160">The default value is 0 seconds.</span></span> <span data-ttu-id="c0f57-161">Bei diesem Wert gibt es keinen Timeout.</span><span class="sxs-lookup"><span data-stu-id="c0f57-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="c0f57-162">Das Dataset und seine Feldauflistung werden im Berichtsdatenbereich unter dem Datenquellenknoten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0f57-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0f57-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0f57-163">See Also</span></span>
 <span data-ttu-id="c0f57-164">[Berichte zu eingebetteten Datasets und freigegebenen Datasets &#40;Berichts-Generator und SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Datasetfeldauflistung &#40;Berichts-Generator und SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Abfrage-Designer](../query-designers-report-builder.md) &#40;Berichts-Generator&#41;[Hilfe für Dialog Felder, Bereiche und Assistenten](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) Berichts-Generator &#40;und SSRS Berichts-Generator [Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in&#41;](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [eingebetteten und freigegebenen Datasets](embedded-and-shared-datasets-report-builder-and-ssrs.md) [Hinzufügen](report-datasets-ssrs.md) Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="c0f57-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


