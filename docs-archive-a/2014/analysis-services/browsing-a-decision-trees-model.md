---
title: Durchsuchen eines Decision Trees-Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- tree viewer
- mining model, decision tree
- decision tree [data mining]
- dependency network
ms.assetid: 6b3dd1ae-caff-41c3-817b-802dc020ff88
author: minewiskan
ms.author: owend
ms.openlocfilehash: 809d2e494cfa7a6c4078acf95c2c70a0e68c188d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610318"
---
# <a name="browsing-a-decision-trees-model"></a><span data-ttu-id="1c3d8-102">Durchsuchen eines Entscheidungsstrukturmodells</span><span class="sxs-lookup"><span data-stu-id="1c3d8-102">Browsing a Decision Trees Model</span></span>
  <span data-ttu-id="1c3d8-103">Wenn Sie ein Klassifizierungs Modell mithilfe von **Durchsuchen**öffnen, wird das Modell in einem interaktiven Entscheidungsstruktur-Viewer angezeigt, der dem [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Viewer in ähnelt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1c3d8-103">When you open a classification model using **Browse**, the model is displayed in an interactive decision tree viewer, similar to the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="1c3d8-104">Im Viewer werden die Ergebnisse der Klassifizierung als Diagramm angezeigt. Darin sind die Kriterien hervorgehoben, die verschiedene Datengruppen voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-104">The viewer displays the results of classification as a graph that is designed to highlight the criteria that differentiate one group of data from another.</span></span> <span data-ttu-id="1c3d8-105">Sie können auch einen Drilldown auf einzelne Teilmengen der Struktur ausführen und die zugrunde liegenden Daten abrufen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-105">You can also drill down into individual subsets of the tree and retrieve the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="1c3d8-106">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="1c3d8-106">Explore the Model</span></span>  
 <span data-ttu-id="1c3d8-107">Modelle, die auf dem Decision Trees-Algorithmus basieren, verfügen über eine große Menge aufschlussreicher Informationen, die Sie untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-107">Models based on the Decision Trees algorithm have lots of interesting information to explore.</span></span> <span data-ttu-id="1c3d8-108">Das Fenster **Durchsuchen** enthält die folgenden Registerkarten und Bereiche, die Sie beim Erlernen der Muster und Vorhersagen von Ergebnissen mithilfe des Diagramms unterstützen:</span><span class="sxs-lookup"><span data-stu-id="1c3d8-108">The **Browse** window includes the following tabs and panes to help you learn the patterns and predict outcomes using the graph:</span></span>  
  
-   [<span data-ttu-id="1c3d8-109">Entscheidungsstruktur</span><span class="sxs-lookup"><span data-stu-id="1c3d8-109">Decision Tree</span></span>](#BKMK_DecisionTree)  
  
-   [<span data-ttu-id="1c3d8-110">Abhängigkeitsnetzwerk</span><span class="sxs-lookup"><span data-stu-id="1c3d8-110">Dependency Network</span></span>](#BKMK_DNetwork)  
  
 <span data-ttu-id="1c3d8-111">Um mit einem Entscheidungsstrukturmodell zu experimentieren, können Sie die Beispieldaten auf der Registerkarte Trainingsdaten (oder Quelldaten) der Beispieldaten-Arbeitsmappe verwenden und ein Entscheidungsstrukturmodell erstellen, für das "Bike Buyer" als vorhersagbares Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-111">To experiment with a decision trees model, you can use the sample data on the Training Data (or Source Data) tab of the sample data workbook, and build a decision tree model using Bike Buyer as the predictable attribute.</span></span>  
  
###  <a name="decision-tree"></a><a name="BKMK_DecisionTree"></a><span data-ttu-id="1c3d8-112">Entscheidungsstruktur</span><span class="sxs-lookup"><span data-stu-id="1c3d8-112">Decision Tree</span></span>  
 <span data-ttu-id="1c3d8-113">Mithilfe dieser Ansicht sind Sie in der Lage, die Faktoren, die zu einem Ergebnis führen, zu verstehen und zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-113">This view is intended to help you understand and explore the factors that lead to an outcome.</span></span>  
  
 <span data-ttu-id="1c3d8-114">Das Entscheidungsstrukturdiagramm kann wie folgt von links nach rechts ausgewertet werden:</span><span class="sxs-lookup"><span data-stu-id="1c3d8-114">The decision tree graph can be read from left to right as follows:</span></span>  
  
-   <span data-ttu-id="1c3d8-115">Die Rechtecke, die als *Knoten*bezeichnet werden, enthalten Teilmengen der Daten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-115">The rectangles, which are referred to as *nodes*, contain subsets of the data.</span></span> <span data-ttu-id="1c3d8-116">Die Beschriftung des Knotens gibt die Unterscheidungsmerkmale dieser Teilmenge an.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-116">The label on the node tells you the defining characteristics of that subset.</span></span>  
  
-   <span data-ttu-id="1c3d8-117">Der Knoten ganz links mit der Bezeichnung **all**stellt das vollständige DataSet dar.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-117">The leftmost node, labeled **All**, represents the complete data set.</span></span> <span data-ttu-id="1c3d8-118">Alle nachfolgenden Knoten stellen Teilmengen der Daten dar.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-118">All subsequent nodes represent subsets of the data.</span></span>  
  
-   <span data-ttu-id="1c3d8-119">Eine Entscheidungsstruktur enthält viele Teilungen oder Orte, an denen die Daten auf der Grundlage von Attributen in mehrere Sätze unter *teilt*werden.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-119">A decision tree contains many *splits*, or places where the data diverges into multiple sets based on attributes.</span></span>  
  
     <span data-ttu-id="1c3d8-120">In der ersten Unterteilung des Beispielmodells ist das Dataset beispielsweise in drei Altersgruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-120">For example, the first split in the sample model divides the dataset into three groups by age.</span></span>  
  
-   <span data-ttu-id="1c3d8-121">Die Teilung unmittelbar nach dem Knoten **alle** ist am wichtigsten, da Sie die primäre Bedingung anzeigt, die dieses DataSet dividiert.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-121">The split immediately after the **All** node is most important because it shows the primary condition that divides this dataset.</span></span>  
  
     <span data-ttu-id="1c3d8-122">Weitere Unterteilungen befinden sich rechts davon.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-122">Additional splits occur to the right.</span></span> <span data-ttu-id="1c3d8-123">Durch die Analyse der verschiedenen Struktursegmente können Sie verstehen, welche Attribute den größten Einfluss auf das Kaufverhalten haben.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-123">Thus, by analyzing different segments of the tree, you can learn which attributes had the most influence on purchasing behavior.</span></span>  
  
 <span data-ttu-id="1c3d8-124">![Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell](media/dm13-dec-tree-split-definition.gif "Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell")</span><span class="sxs-lookup"><span data-stu-id="1c3d8-124">![Dependency network graph for an association model](media/dm13-dec-tree-split-definition.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="1c3d8-125">Anhand dieser Informationen können Sie eine zielgruppenorientierte Marketingkampagne für Kunden entwickeln, die durch bestimmte Anreize zum Kauf motiviert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-125">Using this information, you might focus a marketing campaign on customers that might simply need encouragement to make a purchase.</span></span>  
  
##### <a name="explore-the-decision-tree"></a><span data-ttu-id="1c3d8-126">Untersuchen der Entscheidungsstruktur</span><span class="sxs-lookup"><span data-stu-id="1c3d8-126">Explore the decision tree</span></span>  
  
1.  <span data-ttu-id="1c3d8-127">Klicken Sie auf den Knoten **alle** , und sehen Sie sich die **Mining Legende**an.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-127">Click the **All** node, and look at the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="1c3d8-128">Darin finden Sie die genaue Anzahl der Fälle im Trainingsdataset sowie eine Aufschlüsselung der Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-128">It displays the exact count of cases in the training data set, as well as a breakdown of the outcomes.</span></span>  
  
     <span data-ttu-id="1c3d8-129">Sie können die gleichen Informationen in einer QuickInfo anzeigen, wenn Sie den Mauszeiger auf einen Knoten bewegen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-129">You can view the same information in a tooltip if you pause the mouse over a node.</span></span>  
  
2.  <span data-ttu-id="1c3d8-130">Klicken Sie auf das Plus- oder Minuszeichen neben den einzelnen Knoten, um die Struktur zu erweitern oder zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-130">Click the plus and minus signs next to each node to expand or collapse the tree.</span></span>  
  
     <span data-ttu-id="1c3d8-131">Sie können auch den Schieberegler **Ebene anzeigen** verwenden, um die Struktur zu vergrößern oder zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-131">You can also use the **Show Level** slider to expand or shrink the tree.</span></span>  
  
3.  <span data-ttu-id="1c3d8-132">Ist Ihnen aufgefallen, dass einige Knoten dunkler sind als andere?</span><span class="sxs-lookup"><span data-stu-id="1c3d8-132">Notice that some nodes are darker than others?</span></span>  
  
     <span data-ttu-id="1c3d8-133">Standardmäßig wird die Auffüllung als Schattierungs Variable verwendet, was **bedeutet, dass** die Intensität der Farbe Ihnen anzeigt, welche Knoten die meiste Unterstützung bieten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-133">By default, **Population** is used as the shading variable, which means that the intensity of the color shows you which nodes have the most support.</span></span>  
  
     <span data-ttu-id="1c3d8-134">Der äußerst linke Knoten, der das gesamte Dataset enthält, weist demnach die höchste Farbintensität auf.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-134">Therefore the leftmost node is darkest, because it contains the entire dataset.</span></span>  
  
4.  <span data-ttu-id="1c3d8-135">Ändern Sie den Wert für **Hintergrund** von **allen Fällen** in **Ja**.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-135">Change the value for **Background** from **All Cases** to **Yes**.</span></span>  
  
     <span data-ttu-id="1c3d8-136">![Ändern des Entscheidungsstrukturdiagramms zum Hervorheben der Käufer](media/dm13-dectreeshadedbuyer.gif "Ändern des Entscheidungsstrukturdiagramms zum Hervorheben der Käufer")</span><span class="sxs-lookup"><span data-stu-id="1c3d8-136">![changing decision tree graph to highlight buyers](media/dm13-dectreeshadedbuyer.gif "changing decision tree graph to highlight buyers")</span></span>  
  
5.  <span data-ttu-id="1c3d8-137">Jetzt erkennen Sie an der Intensität der Farbe, wie viele Kunden in jedem Knoten ein Fahrrad gekauft haben, also genau das Verhalten, das Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-137">Now the intensity of the color tells you how many customers in each node purchased a bike, which is the behavior you are interested in.</span></span>  
  
     <span data-ttu-id="1c3d8-138">Achten Sie auch auf die Farbbalken innerhalb jedes Knotens.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-138">Notice the colored bars within each node.</span></span> <span data-ttu-id="1c3d8-139">Dies ist ein Histogramm, das die Verteilung von Ergebnissen innerhalb dieser Teilmenge von Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-139">This is a histogram that shows the distribution of outcomes within this subset of data.</span></span> <span data-ttu-id="1c3d8-140">Beispielsweise zeigt die farbige Leiste in der Beispiel-Entscheidungsstruktur für Bike Buyer den Anteil der Kunden an, die Fahrräder gekauft haben (Ja-Werte), und diejenigen, die keine (keine Werte).</span><span class="sxs-lookup"><span data-stu-id="1c3d8-140">For example, in the sample Bike Buyer decision tree, the colored bar shows the proportion of customers who bought bikes (Yes values) vs. those who did not (No values).</span></span> <span data-ttu-id="1c3d8-141">Um die genauen Werte zu erhalten, können Sie auf den Knoten klicken und die **Mining Legende**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-141">To get the exact values, you can click the node and view the **Mining Legend**.</span></span>  
  
6.  <span data-ttu-id="1c3d8-142">Bei der Auswertung des Diagramms erkennen Sie, wie sich jede einzelne Teilmenge von Daten in kleinere Gruppen aufgliedert und welche Attribute am hilfreichsten sind, um ein Ergebnis vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-142">By following the graph, you can see how each subset of data is further decomposed into smaller groups, and which attributes are most useful in predicting an outcome.</span></span>  
  
     <span data-ttu-id="1c3d8-143">Allein die Intensität der Schattierung deutet bereits auf einige interessante Gruppierungen hin, die Sie anhand detaillierterer Daten vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-143">Just by looking at the intensity of the shading, you can focus on a couple groups of interest, and get more detailed data on them for comparison.</span></span> <span data-ttu-id="1c3d8-144">Diese Gruppen zeichnen sich durch eine relativ hohe Wahrscheinlichkeit aus, in Zukunft ein Fahrrad zu kaufen:</span><span class="sxs-lookup"><span data-stu-id="1c3d8-144">For example, these groups have a fairly high probability of buying bikes:</span></span>  
  
    -   <span data-ttu-id="1c3d8-145">Age >= 32 und \< 53 and Yearly Income > = 26000 und Children = 0</span><span class="sxs-lookup"><span data-stu-id="1c3d8-145">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children = 0</span></span>  
  
         <span data-ttu-id="1c3d8-146">Fälle gesamt: 1150</span><span class="sxs-lookup"><span data-stu-id="1c3d8-146">Total cases: 1150</span></span>  
  
         <span data-ttu-id="1c3d8-147">Bike Buyer-Wahrscheinlichkeit: 18%</span><span class="sxs-lookup"><span data-stu-id="1c3d8-147">Bike buyer probability: 18%</span></span>  
  
    -   <span data-ttu-id="1c3d8-148">Age >= 32 und \< 53 and Yearly Income > = 26000 und Children not = 0 und Familien Status = ' Single '</span><span class="sxs-lookup"><span data-stu-id="1c3d8-148">Age >= 32 and \< 53 and Yearly Income >= 26000 and Children not = 0 and Marital Status = 'Single'</span></span>  
  
         <span data-ttu-id="1c3d8-149">Fälle gesamt: 402</span><span class="sxs-lookup"><span data-stu-id="1c3d8-149">Total cases: 402</span></span>  
  
         <span data-ttu-id="1c3d8-150">Wahrscheinlichkeit eines Fahrradkaufs: 16 %</span><span class="sxs-lookup"><span data-stu-id="1c3d8-150">Bike buyer probability: 16%</span></span>  
  
7.  <span data-ttu-id="1c3d8-151">Ändern Sie den Wert für **Hintergrund** von **Ja** in **Nein** , und sehen Sie sich an, wie sich das Diagramm ändert.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-151">Change the value for **Background** from **Yes** to **No** and see how the graph changes.</span></span>  
  
     <span data-ttu-id="1c3d8-152">![Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell](media/dm13-dec-tree-background-no.gif "Abhängigkeitsnetzwerkdiagramm für ein Zuordnungsmodell")</span><span class="sxs-lookup"><span data-stu-id="1c3d8-152">![Dependency network graph for an association model](media/dm13-dec-tree-background-no.gif "Dependency network graph for an association model")</span></span>  
  
 <span data-ttu-id="1c3d8-153">**Tipps**</span><span class="sxs-lookup"><span data-stu-id="1c3d8-153">**Tips**</span></span>  
  
-   <span data-ttu-id="1c3d8-154">Wenn die Daten in mehrere Reihen aufgeteilt werden können, wird für jedes Dataset, das Sie modellieren möchten, ein anderes Modell erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-154">If your data can be divided into multiple series, a different model is built for each set of data that you want to model.</span></span>  
  
-   <span data-ttu-id="1c3d8-155">Im Beispiel Datenmodell gibt es nur ein vorhersagbares Ergebnis: Bike Buyer, aber angenommen, Sie hatten Informationen dazu, ob der Kunde einen Serviceplan gekauft hat und auch Vorhersagen wollte.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-155">In the sample data model, there is only one predictable outcome - Bike Buyer - but suppose you had information about whether the customer purchased a service plan and wanted to predict that as well.</span></span> <span data-ttu-id="1c3d8-156">In diesem Fall würden sich die Daten in einer separaten Spalte befinden und zwei vorhersagbare Attribute aus dem Modell enthalten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-156">In that case you would have that data in a separate column, and include two predictable attributes in the model.</span></span>  
  
     <span data-ttu-id="1c3d8-157">Klicken Sie in der oberen linken Ecke des Bereichs Entscheidungsstruktur auf die Option **Histogramm** , um die maximale Anzahl von Zuständen zu ändern, die in den Histogrammen in der Struktur vorkommen können.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-157">Click the **Histogram** option, in the upper left corner of the Decision Tree pane, to change the maximum number of states that can appear in the histograms in the tree.</span></span> <span data-ttu-id="1c3d8-158">Dies ist sinnvoll, wenn die vorhersagbaren Attribute viele Status haben.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-158">This is useful if the predictable attribute has many states.</span></span> <span data-ttu-id="1c3d8-159">Die Status werden von links nach rechts in einem Histogramm in Reihenfolge der Verwendungshäufigkeit angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-159">The states appear in a histogram in order of popularity from left to right.</span></span>  
  
-   <span data-ttu-id="1c3d8-160">Sie können auch die Optionen auf der Registerkarte **Entscheidungs** Struktur verwenden, um zu beeinflussen, wie die Struktur angezeigt wird, indem Sie Zoomen oder verkleinern oder die Größe des Diagramms anpassen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-160">You can also use the options on the **Decision Tree** tab to affect how the tree is displayed, by zooming in or out, or sizing the graph to fit the window.</span></span>  
  
-   <span data-ttu-id="1c3d8-161">Verwenden Sie die Option **Standarderweiterung** , um die Standardzahl der für alle Strukturen im Modell angezeigten Ebenen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-161">Use **Default Expansion** to set the default number of levels that are displayed for all trees in the model.</span></span>  
  
-   <span data-ttu-id="1c3d8-162">Wählen Sie **langen Namen anzeigen** aus, um den vollständigen Namen des Attributs einschließlich der Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-162">Select **Show long name** to display the full name of the attribute, including the data source.</span></span> <span data-ttu-id="1c3d8-163">Kurze Namen und lange Namen sind identisch, solange die Fälle aus derselben Datenquelle wie die Attribute für jeden Fall abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-163">Short names and long names are the same unless your cases are obtained from a different data source than the attributes for each case.</span></span>  
  
 [<span data-ttu-id="1c3d8-164">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="1c3d8-164">Back To Top</span></span>](#bkmk_Top)  
  
###  <a name="dependency-network"></a><a name="BKMK_DNetwork"></a><span data-ttu-id="1c3d8-165">Abhängigkeits Netzwerk</span><span class="sxs-lookup"><span data-stu-id="1c3d8-165">Dependency Network</span></span>  
 <span data-ttu-id="1c3d8-166">Die **Abhängigkeits Netzwerk** Ansicht zeigt die Verbindungen zwischen den Eingabe Attributen und den vorhersagbaren Attributen im Modell an.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-166">The **Dependency Network** view displays the connections between the input attributes and the predictable attributes in the model.</span></span>  
  
1.  <span data-ttu-id="1c3d8-167">Klicken und ziehen Sie den Schieberegler auf der linken Seite des Viewers.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-167">Click and drag the slider at the left of the viewer</span></span>  
  
     <span data-ttu-id="1c3d8-168">Befindet sich dieser auf der obersten Position, werden alle Verbindungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-168">At the top position, all connections are shown.</span></span> <span data-ttu-id="1c3d8-169">Wenn Sie den Schieberegler nach unten ziehen, werden nur die stärksten Verbindungslinien im Viewer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-169">When you drag the slider down, only the strongest links are shown in the viewer.</span></span>  
  
2.  <span data-ttu-id="1c3d8-170">Klicken Sie jetzt auf den Knoten Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-170">Now click the Bike Buyer node.</span></span>  
  
     <span data-ttu-id="1c3d8-171">![Abhängigkeitsnetzwerkansicht für Entscheidungsstrukturen](media/dm13-dectree-depnet.gif "Abhängigkeitsnetzwerkansicht für Entscheidungsstrukturen")</span><span class="sxs-lookup"><span data-stu-id="1c3d8-171">![Dependency network view for decision trees](media/dm13-dectree-depnet.gif "Dependency network view for decision trees")</span></span>  
  
     <span data-ttu-id="1c3d8-172">Wenn Sie einen Knoten auswählen, hebt der Viewer die Abhängigkeiten hervor, die knotenspezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-172">When you select a node, the viewer highlights the dependencies that are specific to the node.</span></span> <span data-ttu-id="1c3d8-173">In diesem Fall werden im Viewer die einzelnen Knoten hervorgehoben, mit denen sich das Ergebnis vorhersagen lässt.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-173">In this case, the viewer highlights each node that helps predict the outcome.</span></span>  
  
3.  <span data-ttu-id="1c3d8-174">Wenn der Viewer zahlreiche Knoten enthält, können Sie mithilfe der Schaltfläche **Knoten** suchen nach bestimmten Knoten suchen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-174">If the viewer contains many nodes, you can search for specific nodes by using the **Find Node** button.</span></span> <span data-ttu-id="1c3d8-175">Durch Klicken auf **Knoten finden** wird das Dialogfeld **Knoten finden** geöffnet, in dem Sie mit einem Filter nach bestimmten Knoten suchen und diese auswählen können.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-175">Clicking **Find Node** opens the **Find Node** dialog box, in which you can use a filter to search for and select specific nodes.</span></span>  
  
4.  <span data-ttu-id="1c3d8-176">Die Legende im unteren Bereich des Viewers verknüpft Farbcodes mit dem Abhängigkeitstyp im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-176">The legend at the bottom of the viewer links color codes to the type of dependency in the graph.</span></span> <span data-ttu-id="1c3d8-177">Wenn Sie einen vorhersagbaren Knoten auswählen, wird dieser z. B. türkis schattiert, und die Knoten, die den ausgewählten Knoten vorhersagen, orange.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-177">For example, when you select a predictable node, the predictable node is shaded turquoise, and the nodes that predict the selected node are shaded orange.</span></span>  
  
 [<span data-ttu-id="1c3d8-178">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="1c3d8-178">Back To Top</span></span>](#bkmk_Top)  
  
### <a name="drill-through-to-underlying-data"></a><span data-ttu-id="1c3d8-179">Ausführen eines Drillthroughs zu zugrunde liegenden Daten</span><span class="sxs-lookup"><span data-stu-id="1c3d8-179">Drill through to Underlying Data</span></span>  
 <span data-ttu-id="1c3d8-180">Mehrere Modelltypen unterstützen die Möglichkeit, einen *Drillthrough* vom Modell zu den zugrunde liegenden Falldaten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-180">Several types of models support the ability to *drill through* from the model to the underlying case data.</span></span> <span data-ttu-id="1c3d8-181">Dies kann sehr hilfreich sein, wenn Sie Kunden aus einem bestimmten Segment kontaktieren oder Daten für weiterführende Analysen extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-181">This can be very useful if you want to contact customers in a particular segment or pull out the data to perform further analysis.</span></span>  
  
##### <a name="get-case-data"></a><span data-ttu-id="1c3d8-182">Abrufen von Falldaten</span><span class="sxs-lookup"><span data-stu-id="1c3d8-182">Get case data</span></span>  
  
1.  <span data-ttu-id="1c3d8-183">Klicken Sie mit der rechten Maustaste auf den Strukturknoten, der die gewünschten Daten enthält, und wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="1c3d8-183">Right-click the node in the tree that contains the desired data and select one of these options:</span></span>  
  
    -   <span data-ttu-id="1c3d8-184">**Drillthrough des Modells**.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-184">**Drill Through Model**.</span></span> <span data-ttu-id="1c3d8-185">Durch diese Option werden die zum ausgewählten Knoten gehörenden Fälle abgerufen und in einer Excel-Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-185">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="1c3d8-186">Sie rufen nur die Datenspalten ab, die tatsächlich zur Modellerstellung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-186">You get back only the columns of data that were actually used in building the model.</span></span>  
  
    -   <span data-ttu-id="1c3d8-187">**Drillthrough für Struktur Spalten**.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-187">**Drill Through Structure Columns**.</span></span> <span data-ttu-id="1c3d8-188">Durch diese Option werden die zum ausgewählten Knoten gehörenden Fälle abgerufen und in einer Excel-Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-188">This option gets the cases that belong to the selected node, and saves them to a table in Excel.</span></span> <span data-ttu-id="1c3d8-189">Sie erhalten alle Informationen, die während der Erstellung in den zugrunde liegenden Daten verfügbar waren, auch wenn eine Spalte nicht im Modell verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-189">You get all information that was available in the underlying data when you built it, even of a column wasn't used in the model.</span></span> <span data-ttu-id="1c3d8-190">Möglicherweise haben Sie die Kundenadresse und die Postleitzahl ausgeschlossen, weil sie zu Analysezwecken nicht hilfreich sind; trotzdem wurden sie in der Struktur beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-190">For example, you might have excluded the customer address and zip code because those fields are not useful with analysis, but left them in the structure.</span></span>  
  
     <span data-ttu-id="1c3d8-191">Kehren Sie zu Excel zurück, um die Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-191">Return to Excel to view your data.</span></span> <span data-ttu-id="1c3d8-192">In der Anzeige Durchsuchen wird eine Abfrage ausgeführt, die Daten werden in einer Tabelle eines neuen Arbeitsblatts gespeichert und die Ergebnisse mit Beschriftungen versehen.</span><span class="sxs-lookup"><span data-stu-id="1c3d8-192">The Browse viewer runs a query, saves the data to a table in a new worksheet, and labels the results.</span></span>  
  
     <span data-ttu-id="1c3d8-193">![Drillthroughergebnisse werden in Excel gespeichert.](media/dm13-dectree-drillthroughresults.gif "Drillthroughergebnisse werden in Excel gespeichert.")</span><span class="sxs-lookup"><span data-stu-id="1c3d8-193">![results of drillthrough are saved to Excel](media/dm13-dectree-drillthroughresults.gif "results of drillthrough are saved to Excel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c3d8-194">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c3d8-194">See Also</span></span>  
 [<span data-ttu-id="1c3d8-195">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="1c3d8-195">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
