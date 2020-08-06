---
title: Validieren von Modellen und Verwenden von Modellen für die Vorhersage (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616205"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="434ea-102">Überprüfen von Modellen und Verwenden von Modellen für Vorhersagen (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="434ea-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="434ea-103">Das Testen und Überprüfen des Modells ist ein wichtiger Schritt im Data Mining-Prozess.</span><span class="sxs-lookup"><span data-stu-id="434ea-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="434ea-104">Sie müssen wissen, welche Leistung Ihre Miningmodelle mit echten Daten erzielen, bevor Sie die Modelle in Ihrer Produktionsumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="434ea-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="434ea-105">Die Data Mining-Add-Ins bieten Tools, die Sie beim Testen erstellter Modelle und beim Erstellen von Vorhersagen und Empfehlungen auf Grundlage der Modelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="434ea-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="434ea-106">Genauigkeitsdiagramm</span><span class="sxs-lookup"><span data-stu-id="434ea-106">Accuracy Chart</span></span>  
 <span data-ttu-id="434ea-107">Der **Genauigkeits Diagramm** -Assistent unterstützt Sie beim Erstellen einer Vorhersage Abfrage und beim Bewerten der Leistung eines Data Mining Modells durch Erstellen eines Prognose Prognose-oder Punkt Diagramm.</span><span class="sxs-lookup"><span data-stu-id="434ea-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="434ea-108">Das Prognosegütediagramm hilft bei der Unterscheidung fast identischer Modelle in einer Struktur, sodass Sie feststellen können, von welchem Modell die besten Vorhersagen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="434ea-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="434ea-109">Genauigkeits Diagramm &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="434ea-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="434ea-110">Klassifikationsmatrix</span><span class="sxs-lookup"><span data-stu-id="434ea-110">Classification Matrix</span></span>  
 <span data-ttu-id="434ea-111">Der **Klassifikations Matrix** -Assistent unterstützt Sie beim Erstellen einer Vorhersage Abfrage zur Bewertung der Leistung eines Klassifizierungs Modells.</span><span class="sxs-lookup"><span data-stu-id="434ea-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="434ea-112">Als Ausgabe erhalten Sie ein Diagramm, in dem sowohl genaue als auch ungenaue Vorhersagen zusammengefasst sind, die mit dem Modell getroffen wurden.</span><span class="sxs-lookup"><span data-stu-id="434ea-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="434ea-113">Die Matrix ist ein wichtiges Tool, da sie nicht nur die Häufigkeit anzeigt, mit der ein Wert von einem Modell richtig vorhergesagt worden ist, sondern auch, welche Werte vom Modell am häufigsten falsch vorhergesagt wurden.</span><span class="sxs-lookup"><span data-stu-id="434ea-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="434ea-114">Klassifizierungs Matrix &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="434ea-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="434ea-115">Gewinndiagramm</span><span class="sxs-lookup"><span data-stu-id="434ea-115">Profit Chart</span></span>  
 <span data-ttu-id="434ea-116">Mit dem **Gewinn Diagramm** -Assistenten können Sie die Vorteile der Verwendung eines Data Mining Modells abwägen und die Kosten für falsch positive und falsche Negative Werte bewerten.</span><span class="sxs-lookup"><span data-stu-id="434ea-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="434ea-117">Dieser Diagrammtyp misst die Vorhersagegenauigkeit des Modells und schließt dabei die angegebenen Stückkosten und Gesamtkosten ein.</span><span class="sxs-lookup"><span data-stu-id="434ea-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="434ea-118">[Gewinn Diagramm &#40;SQL Server Data Mining-Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="434ea-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="434ea-119">Kreuzvalidierung</span><span class="sxs-lookup"><span data-stu-id="434ea-119">Cross-Validation</span></span>  
 <span data-ttu-id="434ea-120">Die Kreuzvalidierung gilt in der Data Mining-Community als bewährte Methode zum Bewerten der Gültigkeit eines Datasets und der Genauigkeit eines Miningmodells, das auf diesem Dataset beruht.</span><span class="sxs-lookup"><span data-stu-id="434ea-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="434ea-121">Dabei wird ein Dataset in Teilsets unterteilt, und anschließend werden iterativ Modelle für die einzelnen Teilsets erstellt, trainiert und getestet.</span><span class="sxs-lookup"><span data-stu-id="434ea-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="434ea-122">Mithilfe des **Kreuz Validierungs-** Assistenten können Sie die Anzahl der Aufteilungen angeben, nach denen die Daten aufgeteilt werden, und dann einen Kreuz Validierungsbericht bereitstellen, in dem die Unterschiede zwischen diesen quer Abschnitten statistisch beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="434ea-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="434ea-123">Auf dieser Grundlage können Sie ermitteln, ob das Modell für alle Trainingsdaten geeignet ist oder ob es für eine bestimmte Teilmenge verfälschte Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="434ea-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="434ea-124">&#40;SQL Server Data Mining-Add-ins&#41;der Kreuz Validierung</span><span class="sxs-lookup"><span data-stu-id="434ea-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="434ea-125">Abfrage-Assistent</span><span class="sxs-lookup"><span data-stu-id="434ea-125">Query Wizard</span></span>  
 <span data-ttu-id="434ea-126">Der **Abfrage** -Assistent ist ein interaktives Tool, das Sie beim Erstellen einer Vorhersage Abfrage unterstützt.</span><span class="sxs-lookup"><span data-stu-id="434ea-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="434ea-127">Über Abfragen generieren Sie Empfehlungen, Vorhersagen usw.</span><span class="sxs-lookup"><span data-stu-id="434ea-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="434ea-128">Wählen Sie im **Abfrage** -Assistenten ein Modell aus, und geben Sie dann Eingabedaten entweder als einzelne Werte oder aus einer Tabelle oder einem Bereich an, und der Assistent unterstützt Sie bei der Auswahl der auszulegenden Spalten.</span><span class="sxs-lookup"><span data-stu-id="434ea-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="434ea-129">Sie können der Abfrage auch Funktionen hinzufügen, um Wahrscheinlichkeitsergebnisse und andere nützliche Statistiken zu generieren.</span><span class="sxs-lookup"><span data-stu-id="434ea-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="434ea-130">Abfrage &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="434ea-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="434ea-131">Erweiterter Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="434ea-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="434ea-132">Der **Erweiterte Abfrage-Editor** ist ein interaktiver Satz von Dialogfeldern, mit denen Sie alle Arten von DMX-Anweisungen erstellen können, von der Ausführung benutzerdefinierter Abfragen bis hin zum Erstellen und trainieren neuer Modelle, zum Löschen von Modellen oder zum Erstellen neuer Datasets.</span><span class="sxs-lookup"><span data-stu-id="434ea-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="434ea-133">Erweiterter Data Mining-Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="434ea-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="434ea-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="434ea-134">See Also</span></span>  
 <span data-ttu-id="434ea-135">[Durchsuchen und Bereinigen von Daten](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="434ea-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="434ea-136">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="434ea-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="434ea-137">Bereitstellen und Skalieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="434ea-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
