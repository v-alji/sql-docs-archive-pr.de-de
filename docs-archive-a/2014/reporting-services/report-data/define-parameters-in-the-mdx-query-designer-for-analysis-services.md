---
title: Definieren von Parametern im MDX-Abfrage-Designer für Analysis Services (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726569"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="fb175-102">Definieren von Parametern im MDX-Abfrage-Designer für Analysis Services (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="fb175-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fb175-103">Um eine MDX-Abfrage von einer [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Datenquelle zu parametrisieren, müssen Sie der Abfrage einen Abfrageparameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb175-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="fb175-104">Im MDX-Abfrage-Designer können Sie im Entwurfsmodus und im Abfragemodus einen Abfrageparameter hinzufügen, indem Sie einen Filter angeben.</span><span class="sxs-lookup"><span data-stu-id="fb175-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="fb175-105">Nachdem Sie die Abfrage mit einem Abfrageparameter definiert haben, erstellt Reporting Services automatisch einen Berichtsparameter und ein Dataset für die Bereitstellung der Liste mit gültigen Werten.</span><span class="sxs-lookup"><span data-stu-id="fb175-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="fb175-106">Dies ermöglicht einem Benutzer, einen Wert anzugeben, der direkt an die Abfrage übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fb175-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="fb175-107">So definieren Sie in MDX im Entwurfsmodus einen Abfrageparameter</span><span class="sxs-lookup"><span data-stu-id="fb175-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="fb175-108">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf ein Dataset, das aus dem Datenquellentyp [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] erstellt wurde, und klicken Sie dann auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fb175-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="fb175-109">Der MDX-Abfrage-Designer wird im Entwurfsmodus geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fb175-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="fb175-110">Ziehen Sie eine Dimension in den Filterbereich, und legen Sie sie in der ersten Zelle in der Spalte **Dimension** ab.</span><span class="sxs-lookup"><span data-stu-id="fb175-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="fb175-111">Wählen Sie in der Spalte **Hierarchie** einen Wert aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="fb175-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="fb175-112">Wählen Sie in der Spalte **Operator** einen Operator für die Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="fb175-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="fb175-113">Wählen Sie in der Spalte **Filterausdruck** einzelne Werte aus der Dropdownliste aus, oder klicken Sie auf das Element **Alle** , um alle Werte auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fb175-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="fb175-114">Aktivieren Sie in der Spalte **Parameter** das Kontrollkästchen, um einen Berichtsparameter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb175-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="fb175-115">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fb175-115">Click **Run**.</span></span>

     <span data-ttu-id="fb175-116">Klicken Sie nach dem Ausführen der Abfrage auf der Symbolleiste auf **Entwurf** , um für die Ansicht der erstellten MDX-Abfrage in den Abfragemodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="fb175-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="fb175-117">Ändern Sie den Abfragetext im Abfragemodus nicht, falls Sie die Abfrage weiterhin im Entwurfsmodus entwickeln möchten.</span><span class="sxs-lookup"><span data-stu-id="fb175-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="fb175-118">Klicken Sie auf **Entwurf** , um zurück in den Entwurfsmodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="fb175-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="fb175-119">Erweitern Sie im Bereich Berichtsdatenbereich den Parameterknoten, um den Berichtsparameter anzuzeigen, der automatisch für den Filter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb175-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="fb175-120">Um das Dataset anzuzeigen, das verfügbare Werte für den Berichtsparameter enthält, klicken Sie mit der rechten Maustaste auf einen leeren Bereich im Berichtsdatenbereich, und klicken Sie dann auf **Ausgeblendete Datasets anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fb175-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="fb175-121">Der Berichtsdatenbereich zeigt alle Datasets im Bericht an.</span><span class="sxs-lookup"><span data-stu-id="fb175-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="fb175-122">So definieren Sie einen Abfrageparameter in MDX im Abfragemodus</span><span class="sxs-lookup"><span data-stu-id="fb175-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="fb175-123">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf ein Dataset, das aus dem Datenquellentyp [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] erstellt wurde, und klicken Sie dann auf **Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="fb175-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="fb175-124">Der MDX-Abfrage-Designer wird im Entwurfsmodus geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fb175-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="fb175-125">Klicken Sie auf der Symbolleiste auf **Entwurf** , um in den Abfragemodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="fb175-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="fb175-126">Klicken Sie auf der MDX-Abfrage-Designer-Symbolleiste auf **Abfrageparameter** (![Symbol für das Dialogfeld „Abfrageparameter“](../../analysis-services/media/iconqueryparameter.gif "Symbol für das Dialogfeld „Abfrageparameter“")).</span><span class="sxs-lookup"><span data-stu-id="fb175-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="fb175-127">Das Dialogfeld Abfrageparameter wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fb175-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="fb175-128">Klicken Sie in der Spalte **Parameter** auf **\<Enter Parameter>** , und geben Sie dann den Namen eines Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="fb175-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="fb175-129">Wählen Sie in der Spalte **Dimension** einen Wert aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="fb175-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="fb175-130">Wählen Sie in der Spalte **Hierarchie** einen Wert aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="fb175-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="fb175-131">Aktivieren Sie in der Spalte **Mehrere Werte** das Kontrollkästchen, um einen mehrwertigen Parameter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb175-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="fb175-132">Wählen Sie in der Spalte **Standard** entsprechend Ihrer Auswahl in Schritt 5 einzelne oder mehrere Werte aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="fb175-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="fb175-133">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fb175-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="fb175-134">Erweitern Sie im Bereich Berichtsdatenbereich den Parameterknoten, um den Berichtsparameter anzuzeigen, der automatisch für den Filter erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb175-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="fb175-135">Um das Dataset anzuzeigen, das verfügbare Werte für den Berichtsparameter enthält, klicken Sie mit der rechten Maustaste auf einen leeren Bereich im Berichtsdatenbereich, und klicken Sie dann auf **Ausgeblendete Datasets anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fb175-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="fb175-136">Der Berichtsdatenbereich zeigt alle Datasets im Bericht an.</span><span class="sxs-lookup"><span data-stu-id="fb175-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb175-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb175-137">See Also</span></span>
 <span data-ttu-id="fb175-138">[Analysis Services Verbindungstyp für MDX-&#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX-Abfrage-Designer-Benutzeroberfläche](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="fb175-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


