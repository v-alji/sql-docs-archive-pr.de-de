---
title: Erstellen einer Abfrage im relationalen Abfrage-Designer (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 28b25861-f3b4-4c3e-a9b0-03d6e4cfea26
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 555d72c4d3bca8677d04fdc4160639f004d6bbe9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723513"
---
# <a name="build-a-query-in-the-relational-query-designer-report-builder-and-ssrs"></a><span data-ttu-id="30c44-102">Erstellen einer Abfrage im relationalen Abfrage-Designer (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="30c44-102">Build a Query in the Relational Query Designer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="30c44-103">Ein Abfrage-Designer unterstützt Sie beim Festlegen der Daten, die für ein Berichtsdataset aus einer externen Datenquelle abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30c44-103">A query designer helps you specify which data to retrieve from an external data source for a report dataset.</span></span> <span data-ttu-id="30c44-104">Sie verwenden einen Abfrage-Designer, wenn Sie in einem Assistenten eine Abfrage oder eine Datasetabfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="30c44-104">You use a query designer when you build a query in a wizard or create a dataset query.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="30c44-105">Ein Dataset basiert auf einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="30c44-105">A dataset is based on a data source.</span></span> <span data-ttu-id="30c44-106">Der Typ der Datenquelle und die Erstellungsumgebung bestimmen, welcher Abfrage-Designer geöffnet wird, wenn Sie die Datasetabfrage definieren.</span><span class="sxs-lookup"><span data-stu-id="30c44-106">The type of data source and the authoring environment determines which query designer opens when you define the dataset query.</span></span> <span data-ttu-id="30c44-107">Die Funktionen eines Abfrage-Designers variieren abhängig von der zu Grunde liegenden Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="30c44-107">Query designer features vary based on the underlying data source.</span></span> <span data-ttu-id="30c44-108">Weitere Informationen zu Datenschichten finden Sie unter [Datenverbindungen, Datenquellen und Verbindungs](../data-connections-data-sources-and-connection-strings-in-report-builder.md) Zeichenfolgen in Berichts-Generator oder [Datenverbindungen, Datenquellen und Verbindungs](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)Zeichenfolgen in Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="30c44-108">For more information about data layers, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) or [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md).</span></span>  
  
 <span data-ttu-id="30c44-109">Ein Abfrage-Designer kann für die folgenden Aufgaben verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="30c44-109">You can use a query designer for the following tasks:</span></span>  
  
-   <span data-ttu-id="30c44-110">Durchsuchen der Metadaten für mehrere Schemas in der externen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="30c44-110">Explore the metadata for multiple schemas on the external data source</span></span>  
  
-   <span data-ttu-id="30c44-111">Festlegen der für das Dataset abzurufenden Felder</span><span class="sxs-lookup"><span data-stu-id="30c44-111">Specify fields to retrieve for the dataset</span></span>  
  
-   <span data-ttu-id="30c44-112">Festlegen von Beziehungen zwischen zwei Objekten, z. B. Tabellen</span><span class="sxs-lookup"><span data-stu-id="30c44-112">Specify relationships between two objects such as tables</span></span>  
  
-   <span data-ttu-id="30c44-113">Festlegen von Filtern, um die Daten vor dem Abruf als Berichtsdaten einzuschränken</span><span class="sxs-lookup"><span data-stu-id="30c44-113">Specify filters to restrict the data before it is retrieved as report data</span></span>  
  
-   <span data-ttu-id="30c44-114">Angeben, ob Parameter erstellt werden</span><span class="sxs-lookup"><span data-stu-id="30c44-114">Indicate whether to create parameters</span></span>  
  
-   <span data-ttu-id="30c44-115">Angeben von Aggregaten, um Berechnungen für die externe Datenquelle durchzuführen</span><span class="sxs-lookup"><span data-stu-id="30c44-115">Specify aggregates to perform calculations on the external data source</span></span>  
  
 <span data-ttu-id="30c44-116">Nach dem Öffnen eines Abfrage-Designers unterscheidet sich die Vorgehensweise zum Erstellen einer Abfrage für ein eingebettetes Dataset nicht von der für ein freigegebenes Dataset.</span><span class="sxs-lookup"><span data-stu-id="30c44-116">After you open a query designer, you build a query in the same way for either an embedded dataset or a shared dataset.</span></span> <span data-ttu-id="30c44-117">In den folgenden Verfahren wird eine Abfrage für ein eingebettetes Dataset verwendet.</span><span class="sxs-lookup"><span data-stu-id="30c44-117">The following procedures use an embedded dataset query.</span></span>  
  
 <span data-ttu-id="30c44-118">Weitere Informationen finden Sie unter [Benutzeroberfläche des relationalen Abfrage-Designers (Berichts-Generator)](relational-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="30c44-118">For more information, see [Relational Query Designer User Interface &#40;Report Builder&#41;](relational-query-designer-user-interface-report-builder.md).</span></span>  
  
### <a name="to-build-a-query-for-an-embedded-dataset-in-report-design-view"></a><span data-ttu-id="30c44-119">So erstellen Sie in der Berichtsentwurfssicht eine Abfrage für ein eingebettetes Dataset</span><span class="sxs-lookup"><span data-stu-id="30c44-119">To build a query for an embedded dataset in Report Design View</span></span>  
  
1.  <span data-ttu-id="30c44-120">Öffnen Sie den Abfrage-Designer.</span><span class="sxs-lookup"><span data-stu-id="30c44-120">Open the query designer.</span></span> <span data-ttu-id="30c44-121">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Dataset, und klicken Sie anschließend auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="30c44-121">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
     <span data-ttu-id="30c44-122">Der mit der Datenquelle verknüpfte Abfrage-Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="30c44-122">The query designer that is associated with the data source opens.</span></span>  
  
2.  <span data-ttu-id="30c44-123">Erweitern Sie im Bereich "Datenbanksicht" die Ordner, die eine hierarchische Ansicht von Datenbankschemaobjekten wie Tabellen, Sichten und gespeicherte Prozeduren enthalten.</span><span class="sxs-lookup"><span data-stu-id="30c44-123">In the Database view pane, expand the folders that display a hierarchical view of database schema objects such as tables, views, and stored procedures.</span></span> <span data-ttu-id="30c44-124">Klicken Sie auf das Auswahlfeld, um alle Felder für ein Objekt auszuwählen, oder erweitern Sie den Knoten, um einzelne Felder auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="30c44-124">Click the select box to select all fields for an object or expand the node to select individual fields.</span></span>  
  
     <span data-ttu-id="30c44-125">Die im Bereich "Datenbanksicht" ausgewählten Felder werden im Bereich **Felder auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30c44-125">As you select fields from the Database view pane, the **Select fields** pane displays your selections.</span></span>  
  
     <span data-ttu-id="30c44-126">Wenn Sie Felder aus mehreren verknüpften Datenbanktabellen auswählen, können Sie im Bereich "Beziehungen" die Tabellenbeziehungen anzeigen, die im Datenbankschema erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="30c44-126">If you select fields from more than one related database table, use the Relationships pane to view the table relationships that were detected from the database schema.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="30c44-127">Die Liste der Datasetfelder wird im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30c44-127">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-specify-limits-for-a-query"></a><span data-ttu-id="30c44-128">So geben Sie Grenzen für eine Abfrage an</span><span class="sxs-lookup"><span data-stu-id="30c44-128">To specify limits for a query</span></span>  
  
1.  <span data-ttu-id="30c44-129">Vergewissern Sie sich im relationalen Abfrage-Designer, dass Sie Felder ausgewählt haben und die Felder im Bereich **Ausgewählte Felder** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="30c44-129">In the relational query designer, verify that you have fields selected and that the fields appear in the **Selected fields** pane.</span></span>  
  
2.  <span data-ttu-id="30c44-130">Klicken Sie auf der Symbolleiste des Bereichs "Angewendete Filter" auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="30c44-130">In the Applied filters pane toolbar, click **Add Filter**.</span></span> <span data-ttu-id="30c44-131">Es wird ein neuer Zeilenfilter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30c44-131">A new filter row appears.</span></span>  
  
3.  <span data-ttu-id="30c44-132">Klicken Sie in das Feld **Feldname**, um die Dropdownliste der Felder anzuzeigen, und klicken Sie anschließend auf den Namen des Felds, nach dem Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="30c44-132">In **Field name**, click to display the drop-down list of fields, and then click the name of the field that you want to filter by.</span></span> <span data-ttu-id="30c44-133">Wenn Sie nach der Menge filtern möchten, klicken Sie z. B. auf das Feld, das die Anzahl von Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="30c44-133">For example, to filter by quantity, click the field that contains the number of items.</span></span>  
  
4.  <span data-ttu-id="30c44-134">Klicken Sie in das Feld **Operator**, um die Dropdownliste der Operatoren anzuzeigen, und wählen Sie anschließend den im Filter zu verwendenden Vergleichsoperator aus.</span><span class="sxs-lookup"><span data-stu-id="30c44-134">In **Operator**, click to display the drop-down list of operators, and then select the comparison operator to use in the filter.</span></span>  
  
5.  <span data-ttu-id="30c44-135">Geben Sie im Feld **Wert**den Wert ein, nach dem Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="30c44-135">In **Value**, type the value that you want to filter by.</span></span> <span data-ttu-id="30c44-136">Wenn Sie z. B. nach Mengen größer 100 filtern möchten, geben Sie 100 ein.</span><span class="sxs-lookup"><span data-stu-id="30c44-136">For example, to filter on quantity greater than 100, type 100.</span></span>  
  
6.  <span data-ttu-id="30c44-137">Wählen Sie die Parameteroption in dieser Zeile aus, um einen Datasetparameter zu erstellen. Dadurch können Benutzer einen Filterwert angeben.</span><span class="sxs-lookup"><span data-stu-id="30c44-137">Select the parameter option in this row to create a dataset parameter to enable a user to specify a filter value.</span></span> <span data-ttu-id="30c44-138">Es wird automatisch ein Berichtsparameter erstellt, der dem Datasetparameter entspricht.</span><span class="sxs-lookup"><span data-stu-id="30c44-138">A report parameter that matches the dataset parameter is automatically created.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="30c44-139">Die Liste der Datasetfelder wird im Berichtsdatenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30c44-139">The list of dataset fields appears in the Report Data pane.</span></span>  
  
### <a name="to-view-a-query-result-set"></a><span data-ttu-id="30c44-140">So zeigen Sie ein Abfrageresultset an</span><span class="sxs-lookup"><span data-stu-id="30c44-140">To view a query result set</span></span>  
  
1.  <span data-ttu-id="30c44-141">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Abfrage ausführen (!)** .</span><span class="sxs-lookup"><span data-stu-id="30c44-141">On the query designer toolbar, click **Run Query (!)**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30c44-142">Der Abfrage-Designer verwendet Entwurfszeitanmeldeinformationen, um die Abfrage auszuführen und das Resultset abzurufen.</span><span class="sxs-lookup"><span data-stu-id="30c44-142">The query designer uses design time credentials to run the query and retrieve the result set.</span></span> <span data-ttu-id="30c44-143">Weitere Informationen finden Sie unter [Angeben von Anmeldeinformationen im Berichts-Generator](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="30c44-143">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="30c44-144">Die Abfrage wird für die Datenquelle ausgeführt, und die zurückgegebenen Beispieldaten werden im Bereich "Abfrageergebnisse" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30c44-144">The query runs on the data source and returns example data in the Query results pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c44-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30c44-145">See Also</span></span>  
 <span data-ttu-id="30c44-146">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-146">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="30c44-147">[Hinzufügen von Daten aus externen Datenquellen (SSRS)](add-data-from-external-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-147">[Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="30c44-148">[Abfrage-Designer &#40;Berichts-Generator&#41;](../query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-148">[Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) </span></span>  
 <span data-ttu-id="30c44-149">[Erstellen eines freigegebenen Datasets oder eingebetteten Datasets &#40;Berichts-Generator und SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-149">[Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="30c44-150">[Berichtsentwurfsansicht &#40;Berichts-Generator&#41;](../report-builder/report-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-150">[Report Design View &#40;Report Builder&#41;](../report-builder/report-design-view-report-builder.md) </span></span>  
 <span data-ttu-id="30c44-151">[Freigegebene Datasetentwurfsansicht &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="30c44-151">[Shared Dataset Design View &#40;Report Builder&#41;](../report-builder/shared-dataset-design-view-report-builder.md) </span></span>  
 [<span data-ttu-id="30c44-152">Abfrage-Designer in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="30c44-152">Reporting Services Query Designers</span></span>](../reporting-services-query-designers.md)  
  
  
