---
title: Hinzufügen, Bearbeiten und Aktualisieren von Feldern im Berichtsdatenbereich (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608338"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="a94f3-102">Hinzufügen, Bearbeiten und Aktualisieren von Feldern im Berichtsdatenbereich (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="a94f3-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a94f3-103">Datasetfelder sind die integrierte Auflistung von Feldnamen, die die Daten darstellen, die zurückgegeben werden, wenn eine Datasetabfrage in einer externen Datenquelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a94f3-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="a94f3-104">Bei einem eingebetteten Dataset sind Datasetfelder die Felder, die erstellt werden, nachdem Sie die Erstellung einer Abfrage abgeschlossen und den Bereich Abfrage-Designer geschlossen haben, und von Ihnen erstellte Felder berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="a94f3-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="a94f3-105">Bei einem freigegebenen Dataset entsprechen die Datasetfelder den Feldern aus der freigegebenen Datasetdefinition, die dem Bericht hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a94f3-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="a94f3-106">Obwohl die Abfrage vom freigegebenen Dataset auf dem Berichtsserver bei jeder Ausführung des Berichts verwendet wird, ist die Liste der Datasetfelder im Bericht statisch.</span><span class="sxs-lookup"><span data-stu-id="a94f3-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="a94f3-107">Aktualisieren Sie mit der Option **Felder Aktualisieren** die Liste der Felder im Bericht, damit Sie mit der aktuellen Liste der Felder der freigegebenen Datasetabfrage übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a94f3-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="a94f3-108">Die Aktualisierung der Feldliste wirkt sich nicht auf die berechneten Felder aus, die Sie im Bericht definieren.</span><span class="sxs-lookup"><span data-stu-id="a94f3-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="a94f3-109">So fügen Sie ein Abfragefeld hinzu</span><span class="sxs-lookup"><span data-stu-id="a94f3-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="a94f3-110">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Dataset, und klicken Sie anschließend auf **Abfragefeld hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a94f3-111">Zum Anzeigen des Berichtsdatenbereichs klicken Sie im Menü **Ansicht** auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="a94f3-112">Klicken Sie auf der Seite **Felder** des Dialogfelds **Dataseteigenschaften** auf **Hinzufügen**und dann auf **Abfragefeld**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="a94f3-113">Unten im Raster wird eine neue Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a94f3-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="a94f3-114">Geben Sie einen Namen für das neue Feld im Textfeld **Feldname** ein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a94f3-115">Namen müssen innerhalb des Datasets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="a94f3-116">Geben Sie im Textfeld **Feldquelle** den Namen eines vorhandenen Felds in der Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="a94f3-117">So fügen Sie ein berechnetes Feld hinzu</span><span class="sxs-lookup"><span data-stu-id="a94f3-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="a94f3-118">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Dataset, und klicken Sie anschließend auf **Berechnetes Feld hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="a94f3-119">Klicken Sie auf der Seite **Felder** des Dialogfelds **Dataseteigenschaften** auf **Hinzufügen**und dann auf **Berechnetes Feld**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="a94f3-120">Unten im Raster wird eine neue Zeile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a94f3-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="a94f3-121">Geben Sie einen Namen für das neue Feld im Textfeld **Feldname** ein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a94f3-122">Namen müssen innerhalb des Datasets eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="a94f3-123">Geben Sie den Ausdruck für das neue Feld im Textfeld **Feldquelle** ein.</span><span class="sxs-lookup"><span data-stu-id="a94f3-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="a94f3-124">Klicken Sie auf die Ausdrucksschaltfläche (**fx**), um einen Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a94f3-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a94f3-125">Der Ausdruck für ein berechnetes Feld darf keine Aggregate oder Verweise auf Berichtselemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="a94f3-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="a94f3-126">So bearbeiten Sie ein Abfragefeld oder ein Datasetfeld</span><span class="sxs-lookup"><span data-stu-id="a94f3-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="a94f3-127">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Feld, und klicken Sie anschließend auf **Feldeigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="a94f3-128">Klicken Sie auf der Seite **Felder** des Dialogfelds **Dataseteigenschaften** auf ein bereits vorhandenes Feld, um die Zeile auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a94f3-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="a94f3-129">Ändern Sie den Namen des Felds oder den Wert des Felds.</span><span class="sxs-lookup"><span data-stu-id="a94f3-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="a94f3-130">So löschen Sie ein Abfragefeld oder ein berechnetes Feld</span><span class="sxs-lookup"><span data-stu-id="a94f3-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="a94f3-131">Erweitern Sie im Berichtsdatenbereich das Dataset, um die Feldauflistung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a94f3-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="a94f3-132">Klicken Sie mit der rechten Maustaste auf das Feld, das Sie entfernen möchten, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="a94f3-133">So aktualisieren Sie die Feldauflistung im Berichtsdatenbereich für ein freigegebenes Dataset</span><span class="sxs-lookup"><span data-stu-id="a94f3-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="a94f3-134">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf das Dataset, und klicken Sie anschließend auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="a94f3-135">Klicken Sie auf **Felder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="a94f3-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="a94f3-136">Die Abfrage des freigegebenen Datasets wird auf dem Berichtsserver ausgeführt und gibt die aktuelle Feldauflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="a94f3-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94f3-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a94f3-137">See Also</span></span>  
 <span data-ttu-id="a94f3-138">[Datasetfeld-Sammlung &#40;Berichts-Generator und SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a94f3-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a94f3-139">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a94f3-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="a94f3-140">[Erstellen von Berichten zu eingebetteten und freigegebenen Datasets &#40;Berichts-Generator und SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a94f3-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a94f3-141">[Abfrage-Designer in Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="a94f3-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="a94f3-142">Abfrage-Designer &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="a94f3-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
