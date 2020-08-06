---
title: Cluster-Assistent (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- clustering [data mining]
ms.assetid: 85b25625-a7ab-4960-9f9c-df22e8ecae37
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90500ae627bcafd1ca5ce17114dac9df9939691d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615686"
---
# <a name="cluster-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="31568-102">Cluster-Assistent (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="31568-102">Cluster Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="31568-103">![Cluster-Assistent (Data Mining-Menüband)](media/dmc-cluster.gif "Cluster-Assistent (Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="31568-103">![Cluster wizard in Data Mining ribbon](media/dmc-cluster.gif "Cluster wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="31568-104">Mit dem Cluster-Assistenten erstellen Sie ein Modell, das Gruppen von Zeilen erkennt, die über ähnliche Merkmale verfügen, und diese gruppiert, um den Abstand zwischen den Gruppen zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="31568-104">The Cluster wizard helps you build a model that detects rows that share similar characteristics and groups them to maximize the distance between groups.</span></span> <span data-ttu-id="31568-105">Dieser Assistent ist hilfreich beim Suchen von Mustern in sämtlichen Daten.</span><span class="sxs-lookup"><span data-stu-id="31568-105">This wizard is useful for finding patterns in all kinds of data.</span></span>  
  
 <span data-ttu-id="31568-106">Der Cluster-Assistent verwendet den Microsoft Clustering-Algorithmus und kann umfassend angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="31568-106">The Cluster wizard uses the Microsoft Clustering algorithm and can be extensively customized.</span></span> <span data-ttu-id="31568-107">Er kann für vorhandene Daten aus einer Excel-Tabelle, einem Excel-Bereich oder einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Abfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31568-107">It works on existing data from an Excel table, an Excel range, or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] query.</span></span> <span data-ttu-id="31568-108">Ähnliche Funktionen werden vom Tool " [Kategorien erkennen](detect-categories-table-analysis-tools-for-excel.md) " bereitgestellt, das in den Tabellenanalyse Tools für Excel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="31568-108">Similar functionality is provided by the [Detect Categories](detect-categories-table-analysis-tools-for-excel.md) tool, provided in the Table Analysis Tools for Excel.</span></span> <span data-ttu-id="31568-109">Das Tool Kategorien erkennen kann jedoch nicht angepasst werden und muss Daten in Excel-Tabellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="31568-109">However, the Detect Categories tool cannot be customized and must use data in Excel tables.</span></span>  
  
## <a name="using-the-cluster-wizard"></a><span data-ttu-id="31568-110">Verwenden des Cluster-Assistenten</span><span class="sxs-lookup"><span data-stu-id="31568-110">Using the Cluster Wizard</span></span>  
  
1.  <span data-ttu-id="31568-111">Klicken Sie im Menüband Data Mining auf **Cluster**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="31568-111">In the Data Mining ribbon, click **Cluster**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="31568-112">Wählen Sie auf der Seite **Quelldaten auswählen** eine Excel-Tabelle oder einen Excel-Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="31568-112">In the **Select Source Data** page, select an Excel table or range.</span></span> <span data-ttu-id="31568-113">Oder geben Sie eine externe Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="31568-113">Or specify and external data source.</span></span>  
  
     <span data-ttu-id="31568-114">Wenn Sie eine externe Datenquelle verwenden, können Sie benutzerdefinierte Sichten erstellen oder benutzerdefinierten Abfragetext einfügen und das Dataset als [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenquelle speichern.</span><span class="sxs-lookup"><span data-stu-id="31568-114">If you use an external data source, you can create custom views or paste in custom query text, and save the data set as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="31568-115">Auf der Seite **Clustering** können Sie die Art und Weise anpassen, in der das Modell erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="31568-115">On the **Clustering** page, you can customize the way the model is built.</span></span>  
  
    -   <span data-ttu-id="31568-116">Für die **Anzahl von Segmenten**können Sie den Assistenten anweisen, eine festgelegte Anzahl von Kategorien zu erstellen, oder die optimale Anzahl von Gruppierungen automatisch erkennen lassen.</span><span class="sxs-lookup"><span data-stu-id="31568-116">For **Number of segments**, you can tell the wizard to create a fixed number of categories, or let it automatically detect the optimum number of groupings.</span></span>  
  
    -   <span data-ttu-id="31568-117">Überprüfen Sie die Liste der Spalten in der Liste **Eingabe Spalten** , und deaktivieren Sie alle Spalten, die beim Erstellen von Mustern nicht nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="31568-117">Review the list of columns in the **Input columns** list, and deselect any columns that are not useful in creating patterns.</span></span> <span data-ttu-id="31568-118">Sie sollten Spalten ausschließen, die IDs, Kundennamen usw. enthalten.</span><span class="sxs-lookup"><span data-stu-id="31568-118">Columns you should exclude include ID numbers, customer names, and so on.</span></span>  
  
4.  <span data-ttu-id="31568-119">Klicken Sie optional auf **Parameter** , um die Algorithmusparameter zu ändern und das Verhalten des Clustering-Modells anzupassen.</span><span class="sxs-lookup"><span data-stu-id="31568-119">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="31568-120">Geben Sie auf der Seite **Daten in Trainings-und Testsätze aufteilen** an, wie viele Daten zum Testen aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31568-120">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="31568-121">Der Rest wird immer zum Trainieren des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="31568-121">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="31568-122">In der Standardeinstellung sind 30 % als Testdaten und 70 % als Trainingsdaten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31568-122">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="31568-123">Geben Sie auf der Seite **Fertig** stellen einen beschreibenden Namen für das DataSet und das Modell an, und legen Sie die folgenden Optionen fest, mit denen die Arbeit mit dem fertigen Modell gesteuert wird:</span><span class="sxs-lookup"><span data-stu-id="31568-123">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="31568-124">**Modell durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="31568-124">**Browse model**.</span></span> <span data-ttu-id="31568-125">Wenn diese Option ausgewählt ist, wird das Fenster **Durchsuchen** geöffnet, sobald der Assistent die Verarbeitung des Modells abgeschlossen hat, damit Sie die Ergebnisse untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="31568-125">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="31568-126">Der Inhalt des Viewers hängt vom Typ des erstellten Modells ab.</span><span class="sxs-lookup"><span data-stu-id="31568-126">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="31568-127">Weitere Informationen finden Sie unter durch [Suchen eines Clusteringmodells](browsing-a-clustering-model.md).</span><span class="sxs-lookup"><span data-stu-id="31568-127">For more information, see [Browsing a Clustering Model](browsing-a-clustering-model.md).</span></span>  
  
    -   <span data-ttu-id="31568-128">**Drillthrough aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="31568-128">**Enable drillthrough**.</span></span> <span data-ttu-id="31568-129">Wählen Sie diese Option aus, um die zugrunde liegenden Daten des fertigen Modells anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31568-129">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="31568-130">Diese Option ist nur verfügbar, wenn Sie ein Decision Tree-Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="31568-130">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="31568-131">**Temporäres Modell verwenden**.</span><span class="sxs-lookup"><span data-stu-id="31568-131">**Use temporary model**.</span></span> <span data-ttu-id="31568-132">Wenn Sie diese Option auswählen, wird das Modell nicht auf dem Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="31568-132">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="31568-133">Temporäre Modelle werden beim Schließen von Excel gelöscht.</span><span class="sxs-lookup"><span data-stu-id="31568-133">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-clustering-models"></a><span data-ttu-id="31568-134">Weitere Informationen zu Clustermodellen</span><span class="sxs-lookup"><span data-stu-id="31568-134">More about Clustering Models</span></span>  
 <span data-ttu-id="31568-135">Sie können den von diesem Assistenten verwendeten Clustering-Algorithmus ändern, indem Sie auf **erweitert** klicken und das Dialogfeld **Algorithmusparameter** verwenden.</span><span class="sxs-lookup"><span data-stu-id="31568-135">You can change the clustering algorithm used by this wizard by clicking **Advanced** and using the **Algorithm Parameters** dialog box.</span></span>  
  
 <span data-ttu-id="31568-136">Der Microsoft Clustering-Algorithmus stellt folgende Clustering-Methoden bereit:</span><span class="sxs-lookup"><span data-stu-id="31568-136">The Microsoft Clustering algorithm provides these clustering methods:</span></span>  
  
-   <span data-ttu-id="31568-137">K-Means – skalierbar oder nicht skalierbar</span><span class="sxs-lookup"><span data-stu-id="31568-137">K-means -  scalable or non-scaling.</span></span>  
  
-   <span data-ttu-id="31568-138">Expectation Maximization (EM) – skalierbar oder nicht skalierbar</span><span class="sxs-lookup"><span data-stu-id="31568-138">Expectation Maximization (EM) - scalable or non-scaling.</span></span>  
  
 <span data-ttu-id="31568-139">Mit dem Parameter CLUSTER_SEED können Sie den Anfangswert festlegen und sicherstellen, dass wiederholte Modelle, die dasselbe Dataset verwenden, die gleichen Ergebnisse liefern.</span><span class="sxs-lookup"><span data-stu-id="31568-139">You can also use the CLUSTER_SEED parameter to control the starting value and ensure that repeated models using the same data set have the same results.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="31568-140">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31568-140">Requirements</span></span>  
 <span data-ttu-id="31568-141">Zum Verwenden des Cluster-Assistenten muss eine Verbindung mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank bestehen.</span><span class="sxs-lookup"><span data-stu-id="31568-141">To use the Cluster wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="31568-142">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit Quelldaten &#40;Data Mining-Client für Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="31568-142">For more information, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31568-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31568-143">See Also</span></span>  
 <span data-ttu-id="31568-144">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="31568-144">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="31568-145">Erkennen von Kategorien &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="31568-145">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
  
