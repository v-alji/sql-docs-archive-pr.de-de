---
title: Auswählen eines Genauigkeits Diagramm Typs und Festlegen von Diagramm Optionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616852"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="eac8d-102">Auswählen eines Genauigkeitsdiagrammtyps Festlegen von Diagrammoptionen</span><span class="sxs-lookup"><span data-stu-id="eac8d-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="eac8d-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]bietet mehrere Methoden zum Bestimmen der Gültigkeit der Mining Modelle.</span><span class="sxs-lookup"><span data-stu-id="eac8d-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="eac8d-104">Der Typ des Genauigkeitsdiagramms, das Sie für jedes Modell oder jede Struktur erstellen können, hängt von diesen Faktoren ab:</span><span class="sxs-lookup"><span data-stu-id="eac8d-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="eac8d-105">Dem Algorithmustyp, der verwendet wurde, um das Modell zu erstellen</span><span class="sxs-lookup"><span data-stu-id="eac8d-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="eac8d-106">Dem Datentyp des vorhersagbaren Attributs</span><span class="sxs-lookup"><span data-stu-id="eac8d-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="eac8d-107">Der Anzahl der zu messenden vorhersagbaren Attribute</span><span class="sxs-lookup"><span data-stu-id="eac8d-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="eac8d-108">In diesem Thema findet sich eine Übersicht über die verschiedenen Genauigkeitsdiagramme.</span><span class="sxs-lookup"><span data-stu-id="eac8d-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="eac8d-109">**Hinweis** Diagramme und ihre Definitionen werden nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="eac8d-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="eac8d-110">Wenn Sie das Fenster schließen, das ein Diagramm enthält, müssen Sie das Diagramm erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="eac8d-111">Genauigkeitsdiagrammtypen</span><span class="sxs-lookup"><span data-stu-id="eac8d-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="eac8d-112">Abhängig vom ausgewählten Diagrammtyp können Sie weitere Optionen konfigurieren, um das Diagramm zu durchsuchen oder das Diagramm in die Zwischenablage zu kopieren und mit den Daten in Excel zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="eac8d-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="eac8d-113">Prognosegütediagramm</span><span class="sxs-lookup"><span data-stu-id="eac8d-113">Lift chart</span></span>  
 <span data-ttu-id="eac8d-114">Nachdem Sie die Optionen für das Modell konfiguriert und die Daten getestet haben, klicken Sie auf die Registerkarte **Prognosegütediagramm** , um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="eac8d-115">Sie können das Diagramm auch in die Zwischenablage kopieren oder Details einzelner Trendlinien oder Datenpunkte in der Mininglegende anzeigen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="eac8d-116">Gewinndiagramm</span><span class="sxs-lookup"><span data-stu-id="eac8d-116">Profit Chart</span></span>  
 <span data-ttu-id="eac8d-117">Nachdem Sie die Optionen für das Modell und die Testdaten konfiguriert haben, klicken Sie auf die Registerkarte **Prognosegütediagramm** , wählen Sie **Gewinndiagramm** in der Liste **Diagrammtyp** aus, um die Optionen für das Gewinndiagramm festzulegen, und klicken Sie anschließend auf **OK** , um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="eac8d-118">Sie können das Dialogfeld **Gewinndiagrammeinstellungen** beliebig oft verwenden, um verschiedene Kostenoptionen auszuprobieren und das Diagramm erneut anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="eac8d-119">Die Mininglegende enthält ausführliche Informationen über den geschätzten Gewinn für jedes Modell.</span><span class="sxs-lookup"><span data-stu-id="eac8d-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="eac8d-120">Sie können auch das Diagramm und den Inhalt der Mininglegende in die Zwischenablage kopieren, um in Excel damit zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="eac8d-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="eac8d-121">Punktdiagramm</span><span class="sxs-lookup"><span data-stu-id="eac8d-121">Scatter Plot</span></span>  
 <span data-ttu-id="eac8d-122">Wenn Sie den entsprechenden Modelltyp ausgewählt haben, ist bei Klicken auf die Registerkarte **Prognosegütediagramm** als Diagrammtyp automatisch **Punktdiagramm** festgelegt, und ein Punktdiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eac8d-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="eac8d-123">Eine weitere Konfiguration ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="eac8d-123">No further configuration is possible.</span></span> <span data-ttu-id="eac8d-124">Sie können das Diagramm auch in die Zwischenablage kopieren und als Grafik in Excel oder in eine andere Anwendung einfügen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="eac8d-125">Klassifikationsmatrix</span><span class="sxs-lookup"><span data-stu-id="eac8d-125">Classification Matrix</span></span>  
 <span data-ttu-id="eac8d-126">Für eine Klassifikationsmatrix wählen Sie auf der Registerkarte **Eingabeauswahl** die Modelle und Testdaten aus und klicken anschließend auf die Registerkarte **Klassifikationsmatrix** , um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eac8d-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="eac8d-127">Der Inhalt einer Klassifikationsmatrix ist bei allen Modelltypen gleich und kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="eac8d-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="eac8d-128">Sie können die Daten im Diagramm in die Zwischenablage kopieren, um sie in Excel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="eac8d-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="eac8d-129">Bericht für die übergreifende Überprüfung</span><span class="sxs-lookup"><span data-stu-id="eac8d-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="eac8d-130">Um einen Kreuzvalidierungsbericht zu erstellen, wählen Sie zunächst eine Miningstruktur oder ein Miningmodell im Projektmappen-Explorer aus. Klicken Sie anschließend auf die Registerkarte **Kreuzvalidierung** , konfigurieren Sie alle relevanten Optionen, und klicken Sie dann auf **Ergebnisse abrufen** , um den Bericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="eac8d-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="eac8d-131">Eine weitere Konfiguration ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="eac8d-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="eac8d-132">Das Format des Kreuzvalidierungsberichts ist bei allen Modelltypen gleich und kann nicht konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="eac8d-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="eac8d-133">Der Inhalt des Berichts ist jedoch abhängig vom analysierten Modelltyp und vom Datentyp des vorhersagbaren Attributs unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="eac8d-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="eac8d-134">Sie können die Ergebnisse des Berichts auch in die Zwischenablage kopieren, um in Excel mit den Daten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="eac8d-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
