---
title: Hinzufügen einer Datenquellen Sicht für Vorhersagen (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2665040a-1291-4064-ba01-f458637dda57
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 9424988efa6a9856f4ef0d558992fc90ac303861
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720545"
---
# <a name="adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial"></a><span data-ttu-id="5f8b3-102">Hinzufügen einer Datenquellensicht für die Planungserstellung (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="5f8b3-102">Adding a Data Source View for Forecasting (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="5f8b3-103">In dieser Aufgabe fügen Sie eine neue Datenquellensicht für das Planungserstellungsszenario hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-103">In this task, you add a data source view that will be used for the forecasting scenario.</span></span> <span data-ttu-id="5f8b3-104">Vorhersagemodelle erfordern eine Spalte in den Daten, die zur Identifizierung von Schritten in einer Zeitreihe verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-104">A forecasting model requires that the data contains a column that can be used to identify steps in a time series.</span></span> <span data-ttu-id="5f8b3-105">Wenn Sie mehrere Datenreihen analysieren möchten, müssen alle Reihen mit dem gleichen Datums- oder Zeitschritt enden.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-105">If you plan to analyze multiple series of data, all series must end on the same date or time step.</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="5f8b3-106">So fügen Sie eine Datenquellensicht hinzu</span><span class="sxs-lookup"><span data-stu-id="5f8b3-106">To add a data source view</span></span>  
  
1.  <span data-ttu-id="5f8b3-107">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **Datenquellen Sichten**, und wählen Sie dann **neue Datenquellen Sicht**aus.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-107">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="5f8b3-108">Klicken Sie auf der Seite **Willkommen beim Datenquellensicht-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-108">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="5f8b3-109">Wählen Sie auf der Seite **Datenquelle auswählen** unter **relationale Datenquellen**die [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-109">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source.</span></span> <span data-ttu-id="5f8b3-110">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-110">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f8b3-111">Wenn Sie nicht über diese Datenquelle verfügen, finden Sie die Schritte zum Erstellen der Datenquelle im Lernprogramm zu [Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5f8b3-111">If you do not have this data source, you can find the steps to create the data source in the [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
4.  <span data-ttu-id="5f8b3-112">Wählen Sie auf der Seite **Tabellen und Sichten auswählen** die Tabelle vTimeSeries (dbo) aus, und klicken Sie dann auf den Pfeil nach rechts, um Sie der Datenquellen Sicht hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-112">On the **Select Tables and Views** page, select the table, vTimeSeries (dbo), and then click the right arrow to add it to the data source view.</span></span>  
  
5.  <span data-ttu-id="5f8b3-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="5f8b3-114">Auf der Seite **Assistenten abschließen** wird die Datenquellen Sicht standardmäßig benannt [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5f8b3-114">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="5f8b3-115">Ändern Sie den Namen in **SalesByRegion**, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-115">Change the name to **SalesByRegion**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="5f8b3-116">Der Datenquellen Sicht-Designer wird geöffnet, und die Datenquellen Sicht **SalesByRegion** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-116">Data Source View Designer opens and the **SalesByRegion** data source view appears.</span></span>  
  
## <a name="working-with-the-data-source-view"></a><span data-ttu-id="5f8b3-117">Arbeiten mit der Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="5f8b3-117">Working with the Data Source View</span></span>  
 <span data-ttu-id="5f8b3-118">Nachdem Sie die Datenquellensicht erstellt haben, können Sie die Daten wie folgt untersuchen:</span><span class="sxs-lookup"><span data-stu-id="5f8b3-118">After you have created the data source view, you can explore the data in the following ways:</span></span>  
  
-   <span data-ttu-id="5f8b3-119">Klicken Sie im Designer mit der rechten Maustaste auf die vTimeSeries-Tabelle, und wählen Sie **Daten durchsuchen** aus, um die ausgewählte Tabelle in einem Raster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-119">Right-click the table vTimeSeries in the designer, and select **Explore Data** to open the selected table in a grid.</span></span>  
  
-   <span data-ttu-id="5f8b3-120">Klicken Sie auf **samplingoptionen** , und ändern Sie dann mithilfe des Dialog Felds **Optionen** zum Durchsuchen der Stichprobenentnahme</span><span class="sxs-lookup"><span data-stu-id="5f8b3-120">Click **Sampling options** and then use the **Data Exploration Options** dialog box to change the sampling method.</span></span> <span data-ttu-id="5f8b3-121">Klicken Sie auf **Aktualisieren** , um Daten in der Tabelle mithilfe der neuen Options Einstellungen zu laden.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-121">Click **Refresh** to load data in the table using the new option settings.</span></span> <span data-ttu-id="5f8b3-122">Beispielsweise können Sie die Anzahl der Zeilen angeben, die im Beispiel ausgegeben werden sollen, oder die ersten n Zeilen auswählen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-122">For example, you could specify the number of rows to output in the sample, or choose the top n rows.</span></span>  
  
-   <span data-ttu-id="5f8b3-123">Klicken Sie mit der rechten Maustaste auf die Tabelle vTimeSeries, und wählen Sie **Eigenschaften** aus, um der Tabelle einen neuen Namen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-123">Right-click the table vTimeSeries and select **Properties** to assign a new name to the table.</span></span> <span data-ttu-id="5f8b3-124">Sie können auch einzelne Spalten aus der Datenquellensicht auswählen und die Spalteneigenschaften ändern.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-124">You can also select individual columns from the data source view, and the modify the column properties.</span></span>  
  
-   <span data-ttu-id="5f8b3-125">Klicken Sie im Entwurfsbereich der Datenquellensicht auf eine beliebige Stelle, um eine neue Abfrage zu erstellen und ihr einen Namen zuzuweisen, Beziehungen zwischen Tabellen zu erstellen oder das Layout des Entwurfsbereichs zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-125">Click anywhere in the data source view design area to create a new query and assign a name to it, to create relationships between tables, or to change the layout of the design area.</span></span>  
  
-   <span data-ttu-id="5f8b3-126">Klicken Sie mit der rechten Maustaste auf eine Tabelle, und wählen Sie **neue benannte Berechnung** , um abgeleitete Spalten einschließlich Aggregationen zu erstellen</span><span class="sxs-lookup"><span data-stu-id="5f8b3-126">Right-click a table and select **New Named Calculation** to create derived columns, including aggregations.</span></span> <span data-ttu-id="5f8b3-127">Sie können auch neue Tabellen und Sichten aus der Datenquelle dieser Sicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-127">You can also add new tables and views from the data source in this view.</span></span>  
  
 <span data-ttu-id="5f8b3-128">In der nächsten Aufgabe untersuchen Sie die Zeitreihendaten und stellen fest, welche Spalte sich am besten für die Verwendung als Zeitreihenbezeichner verwenden lässt.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-128">In the next task, you will explore the time series data and determine the best column to use as the time series identifier.</span></span> <span data-ttu-id="5f8b3-129">Außerdem erfahren Sie, wie unvollständige Zeitreihendaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5f8b3-129">You will also learn how to handle gaps in time series data.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5f8b3-130">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="5f8b3-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5f8b3-131">Grundlegendes zu den Anforderungen für ein Zeitreihen Modell &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="5f8b3-131">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f8b3-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f8b3-132">See Also</span></span>  
 [<span data-ttu-id="5f8b3-133">Microsoft Time Series-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="5f8b3-133">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
