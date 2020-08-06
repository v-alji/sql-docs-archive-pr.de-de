---
title: Verwenden von Drillthrough für Strukturdaten (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a693979c-0564-4d6d-b35d-cbbc8f350469
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 49a1ced27150676def541548f47a90a3f847c8ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608122"
---
# <a name="using-drillthrough-on-structure-data-basic-data-mining-tutorial"></a><span data-ttu-id="bae2b-102">Verwenden von Drillthrough für Strukturdaten (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="bae2b-102">Using Drillthrough on Structure Data (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="bae2b-103">Im Rahmen einer Werbekampagne sendet [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] einen Prospekt an alle potenziellen Kunden im Alter von 34 bis 40 Jahren.</span><span class="sxs-lookup"><span data-stu-id="bae2b-103">As part of their advertising campaign, [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] is sending a mailer to potential customers in the 34-40 age demographic.</span></span> <span data-ttu-id="bae2b-104">Der gleiche Prospekt soll auf Wunsch der Marketingabteilung auch an Kunden gesendet werden, die vor mehr als fünf Jahren ein Fahrrad von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="bae2b-104">The marketing department has decided that they would also like to send the mailer to the customers who purchased bikes from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] more than five years ago.</span></span> <span data-ttu-id="bae2b-105">In dieser Lektion identifizieren Sie Kunden mit älteren Fahrrädern und rufen ihre Kontaktinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="bae2b-105">In this lesson you will identify customers with older bikes and retrieve their contact information.</span></span> <span data-ttu-id="bae2b-106">Diese Informationen sind nicht im Modell, sondern in der Struktur enthalten.</span><span class="sxs-lookup"><span data-stu-id="bae2b-106">This information is not included in the model, but is included in the structure.</span></span> <span data-ttu-id="bae2b-107">Stellen Sie zunächst sicher, dass die Drillthroughfunktion für die Struktur aktiviert ist, um die Kontaktinformationen abzurufen. Rufen Sie dann die Namen und Adressen der Kundenzielgruppe ab, indem Sie einen Drillthrough ausführen.</span><span class="sxs-lookup"><span data-stu-id="bae2b-107">To retrieve the contact information you will first ensure that drillthrough is enabled for the structure and then you will use drillthrough to reveal the names and addresses of the targeted customers.</span></span>  
  
### <a name="to-enable-drillthrough-on-a-mining-model"></a><span data-ttu-id="bae2b-108">So aktivieren Sie Drillthrough für ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="bae2b-108">To enable drillthrough on a mining model</span></span>  
  
1.  <span data-ttu-id="bae2b-109">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Data Mining-Designer auf der Registerkarte **Miningmodelle** mit der rechten Maustaste auf das **TM_Decision_Tree** -Modell, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="bae2b-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Mining Models** tab of Data Mining Designer, right-click the **TM_Decision_Tree** model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bae2b-110">Klicken Sie im Eigenschaftenfenster auf **AllowDrillthrough**, und wählen Sie **True**aus.</span><span class="sxs-lookup"><span data-stu-id="bae2b-110">In the Properties windows, click **AllowDrillthrough**, and select **True**.</span></span>  
  
3.  <span data-ttu-id="bae2b-111">Klicken Sie auf der Registerkarte **Miningmodelle**mit der rechten Maustaste auf das Modell, und wählen Sie Modell verarbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="bae2b-111">In the Mining Models tab, right-click the model, and select **Process Model**.</span></span>  
  
 <span data-ttu-id="bae2b-112">Weitere Informationen finden Sie unter [Drillthrough-Abfragen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="bae2b-112">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
### <a name="to-view-drillthrough-data-from-a-mining-model"></a><span data-ttu-id="bae2b-113">So zeigen Sie Drillthroughdaten von einem Miningmodell an</span><span class="sxs-lookup"><span data-stu-id="bae2b-113">To view drillthrough data from a mining model</span></span>  
  
1.  <span data-ttu-id="bae2b-114">Klicken Sie im Data Mining-Designer auf die Registerkarte **Miningmodell-Viewer** .</span><span class="sxs-lookup"><span data-stu-id="bae2b-114">In Data Mining Designer, click the **Mining Model Viewer** tab.</span></span>  
  
2.  <span data-ttu-id="bae2b-115">Wählen Sie das **TM_Decision_Tree** -Modell aus der Liste **Miningmodell** aus.</span><span class="sxs-lookup"><span data-stu-id="bae2b-115">Select the **TM_Decision_Tree** model from the **Mining Model** list.</span></span>  
  
3.  <span data-ttu-id="bae2b-116">Ändern Sie den Wert für **Background** in `1` .</span><span class="sxs-lookup"><span data-stu-id="bae2b-116">Change the **Background** value to `1`.</span></span> <span data-ttu-id="bae2b-117">Auf diese Weise zeigen Sie nur den Teil des Modells an, der sich auf Kunden bezieht, die Fahrräder gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="bae2b-117">By doing this, you show only the part of the model that is related to customer who bought bikes.</span></span>  
  
4.  <span data-ttu-id="bae2b-118">Wählen Sie den Microsoft Struktur-Viewer aus der Liste **Viewer** aus.</span><span class="sxs-lookup"><span data-stu-id="bae2b-118">Select the Microsoft Tree viewer from the **Viewer** list.</span></span> <span data-ttu-id="bae2b-119">Dadurch wird eine Aktualisierung des Viewers mit den neuen Filterbedingungen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="bae2b-119">This will force the viewer to refresh with the new filter conditions.</span></span> <span data-ttu-id="bae2b-120">Suchen Sie anschließend den Knoten **Age >= 34 und <41** , und klicken Sie mit der rechten Maustaste auf den Knoten.</span><span class="sxs-lookup"><span data-stu-id="bae2b-120">Then, locate the **Age >=34 and <41** node and right-click the node.</span></span>  
  
5.  <span data-ttu-id="bae2b-121">Wählen Sie **Drillthrough**und anschließend **Modell- und Strukturspalten** aus, um das Fenster **Drillthrough** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bae2b-121">Select **Drill Through**, and then select **Model and Structure Columns** to open the **Drill Through** window.</span></span>  
  
6.  <span data-ttu-id="bae2b-122">Führen Sie einen Bildlauf zur Spalte **Structure.Date First Purchase** durch, um die Kaufdaten für die älteren Fahrräder anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bae2b-122">Scroll to the **Structure.Date First Purchase** column to view the purchase dates for the older bikes.</span></span>  
  
7.  <span data-ttu-id="bae2b-123">Um die Daten in die Zwischenablage zu kopieren, klicken Sie mit der rechten Maustaste auf eine beliebige Zeile in der Tabelle, und wählen Sie **Alle kopieren**.</span><span class="sxs-lookup"><span data-stu-id="bae2b-123">To copy the data to the Clipboard, right-click any row in the table, and select **Copy All**.</span></span>  
  
 <span data-ttu-id="bae2b-124">Gratulation – Sie haben das Lernprogramm zu Data Mining-Grundlagen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bae2b-124">Congratulations, you have completed the basic data mining tutorial.</span></span> <span data-ttu-id="bae2b-125">Nachdem Sie sich mit der Verwendung der Data Mining-Tools vertraut gemacht haben, wird empfohlen, das Data Mining-Lernprogramm für Fortgeschrittene zu absolvieren. Darin wird das Erstellen von Modellen für Vorhersagen, Market Basket-Analysen und Sequenzcluster veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bae2b-125">Now that you are comfortable using the data mining tools, we recommend that you also complete the intermediate data mining tutorial, which demonstrates how to create models for forecasting, market basket analysis, and sequence clustering.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="bae2b-126">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="bae2b-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="bae2b-127">Erstellen von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="bae2b-127">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="bae2b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bae2b-128">See Also</span></span>  
 [<span data-ttu-id="bae2b-129">erstellt eine Vorhersage mithilfe des Generators für Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="bae2b-129">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
