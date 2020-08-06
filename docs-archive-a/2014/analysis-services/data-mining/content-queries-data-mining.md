---
title: Inhalts Abfragen (Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c4f4a5a8-a230-4222-bece-9d563501f65f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44b162c34f5f505462a713205d8434484473afa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622963"
---
# <a name="content-queries-data-mining"></a><span data-ttu-id="e6ac4-102">Inhaltsabfragen (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="e6ac4-102">Content Queries (Data Mining)</span></span>
  <span data-ttu-id="e6ac4-103">Eine Inhaltsabfrage stellt eine Möglichkeit dar, Informationen über interne Statistiken und die Struktur des Miningmodells zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-103">A content query is a way of extracting information about the internal statistics and structure of the mining model.</span></span> <span data-ttu-id="e6ac4-104">Mitunter enthält eine Inhaltsabfrage Details, die im Viewer nicht unmittelbar verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-104">Sometimes a content query can provide details that are not readily available in the viewer.</span></span> <span data-ttu-id="e6ac4-105">Sie können auch die Ergebnisse einer Inhaltsabfrage verwenden, um Informationen programmgesteuert zu anderen Verwendungszwecken zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-105">You can also use the results of a content query to extract information programmatically for other uses.</span></span>  
  
 <span data-ttu-id="e6ac4-106">Dieser Abschnitt enthält allgemeine Informationen über die Art der Informationen, die Sie mit einer Inhaltsabfrage abrufen können, sowie die allgemeine DMX-Syntax für Inhaltsabfragen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-106">This section provides general information about the types of information that you can retrieve by using a content query, and the general DMX syntax for content queries.</span></span>  
  
 [<span data-ttu-id="e6ac4-107">Grundlegende Inhaltsabfragen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-107">Basic Content Queries</span></span>](#bkmk_ContentQuery)  
  
-   [<span data-ttu-id="e6ac4-108">Abfragen für Struktur-und Falldaten</span><span class="sxs-lookup"><span data-stu-id="e6ac4-108">Queries on Structure and Case Data</span></span>](#bkmk_Structure)  
  
-   [<span data-ttu-id="e6ac4-109">Abfragen für Modellmuster</span><span class="sxs-lookup"><span data-stu-id="e6ac4-109">Queries on Model Patterns</span></span>](#bkmk_Patterns)  
  
 [<span data-ttu-id="e6ac4-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e6ac4-110">Examples</span></span>](#bkmk_Examples)  
  
-   [<span data-ttu-id="e6ac4-111">Inhaltsabfrage für ein Zuordnungsmodell</span><span class="sxs-lookup"><span data-stu-id="e6ac4-111">Content Query on an Association Model</span></span>](#bkmk_Assoc)  
  
-   [<span data-ttu-id="e6ac4-112">Inhaltsabfrage für ein Entscheidungsstrukturmodell</span><span class="sxs-lookup"><span data-stu-id="e6ac4-112">Content Query on a Decision Trees Model</span></span>](#bkmk_DecTree)  
  
 [<span data-ttu-id="e6ac4-113">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-113">Working with the Query Results</span></span>](#bkmk_Results)  
  
##  <a name="basic-content-queries"></a><a name="bkmk_ContentQuery"></a><span data-ttu-id="e6ac4-114">Grundlegende Inhalts Abfragen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-114">Basic Content Queries</span></span>  
 <span data-ttu-id="e6ac4-115">Sie können Inhaltsabfragen mit dem Generator für Vorhersageabfragen erstellen, die in SQL Server Management Studio enthaltenen Vorlagen für DMX-Inhaltsabfragen verwenden oder Abfragen direkt in DMX schreiben.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-115">You can create content queries by using the Prediction Query Builder, use the DMX content query templates that are provided in SQL Server Management Studio, or write queries directly in DMX.</span></span> <span data-ttu-id="e6ac4-116">Anders als bei Vorhersageabfragen müssen keine externen Daten verknüpft werden, sodass Inhaltsabfragen leicht zu schreiben sind.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-116">Unlike prediction queries you do not need to join external data, so content queries are easy to write.</span></span>  
  
 <span data-ttu-id="e6ac4-117">Dieser Abschnitt bietet eine Übersicht über die Typen von Inhaltsabfragen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-117">This section provides an overview of the types of content queries you can create.</span></span>  
  
-   <span data-ttu-id="e6ac4-118">Abfragen der Miningstruktur oder der Falldaten liefern eine ausführliche Ansicht der Daten, die für das Training verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-118">Queries on the mining structure or case data let you view the detailed data that was used for training.</span></span>  
  
-   <span data-ttu-id="e6ac4-119">Abfragen des Modells können Muster, Attributlisten, Formeln usw. zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-119">Queries on the model can return patterns, lists of attributes, formulas, and so forth.</span></span>  
  
###  <a name="queries-on-structure-and-case-data"></a><a name="bkmk_Structure"></a> <span data-ttu-id="e6ac4-120">Abfragen für Struktur- und Falldaten</span><span class="sxs-lookup"><span data-stu-id="e6ac4-120">Queries on Structure and Case Data</span></span>  
 <span data-ttu-id="e6ac4-121">DMX unterstützt Abfragen für zwischengespeicherte Daten, die zum Erstellen von Miningstrukturen und -modellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-121">DMX supports queries on the cached data that is used to build mining structures and models.</span></span> <span data-ttu-id="e6ac4-122">Dieser Cache wird standardmäßig beim Definieren der Miningstruktur erstellt und beim Verarbeiten der Struktur oder des Modells aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-122">By default, this cache is created when you define the mining structure, and is populated when you process the structure or model.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e6ac4-123">Der Cache kann nicht gelöscht werden, falls Daten in Trainings- und Testsätze unterteilt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-123">This cache cannot be cleared or deleted if you need to separate data into training and testing sets.</span></span> <span data-ttu-id="e6ac4-124">Wenn der Cache gelöscht wird, können Sie keine Falldaten abfragen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-124">If the cache is cleared, you cannot query the case data.</span></span>  
  
 <span data-ttu-id="e6ac4-125">In den folgenden Beispielen werden allgemeine Schemas zum Erstellen von Abfragen für Falldaten oder Daten in der Miningstruktur erläutert:</span><span class="sxs-lookup"><span data-stu-id="e6ac4-125">The following examples show the common patterns for creating queries on the case data, or queries on the data in the mining structure:</span></span>  
  
 <span data-ttu-id="e6ac4-126">**Abrufen aller Fälle für ein Modell**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-126">**Get all the cases for a model**</span></span>  
 `SELECT FROM <model>.CASES`  
  
 <span data-ttu-id="e6ac4-127">Verwenden Sie diese Anweisung, um angegebene Spalten aus den zum Erstellen eines Modells verwendeten Falldaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-127">Use this statement to retrieve specified columns from the case data used to build a model.</span></span> <span data-ttu-id="e6ac4-128">Sie müssen über Drillthroughberechtigungen für das Modell verfügen, um diese Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-128">You must have drillthrough permissions on the model to run this query.</span></span>  
  
 <span data-ttu-id="e6ac4-129">**Anzeigen aller Daten, die in der Struktur enthalten sind**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-129">**View all the data that is included in the structure**</span></span>  
 `SELECT FROM <structure>.CASES`  
  
 <span data-ttu-id="e6ac4-130">Verwenden Sie diese Anweisung, um alle in der Struktur enthaltenen Daten anzuzeigen, einschließlich Spalten, die nicht in einem bestimmten Miningmodell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-130">Use this statement to view all the data that is included in the structure, including columns that are not included in a particular mining model.</span></span> <span data-ttu-id="e6ac4-131">Sie müssen über Drillthroughberechtigungen für das Modell sowie für die Struktur verfügen, um Daten aus der Miningstruktur abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-131">You must have drillthrough permissions on the model, as well as on the structure, to retrieve data from the mining structure.</span></span>  
  
 <span data-ttu-id="e6ac4-132">**Abrufen des Wertebereichs**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-132">**Get range of values**</span></span>  
 `SELECT DISTINCT RangeMin(<column>), RangeMax(<column>) FROM <model>`  
  
 <span data-ttu-id="e6ac4-133">Verwenden Sie diese Anweisung, um den minimalen, maximalen und Mittelwert einer kontinuierlichen Spalte oder der Buckets einer DISCRETIZED-Spalte zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-133">Use this statement to find the minimum value, maximum value, and mean of a continuous column, or of the buckets of a DISCRETIZED column.</span></span>  
  
 <span data-ttu-id="e6ac4-134">**Abrufen unterschiedlicher Werte**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-134">**Get distinct values**</span></span>  
 `SELECT DISTINCT <column>FROM <model>`  
  
 <span data-ttu-id="e6ac4-135">Verwenden Sie diese Anweisung, um alle Werte einer DISCRETE-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-135">Use this statement to retrieve all the values of a DISCRETE column.</span></span>  <span data-ttu-id="e6ac4-136">Verwenden Sie diese Anweisung nicht für DISCRETIZED-Spalten. Verwenden Sie stattdessen die `RangeMin`-Funktion und die `RangeMax`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-136">Do not use this statement for DISCRETIZED columns; use the `RangeMin` and `RangeMax` functions instead.</span></span>  
  
 <span data-ttu-id="e6ac4-137">**Suchen der Fälle, die zum Trainieren eines Modells oder einer Struktur verwendet wurden**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-137">**Find the cases that were used to train a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTrainingCase()`  
  
 <span data-ttu-id="e6ac4-138">Verwenden Sie diese Anweisung, um das vollständige Dataset abzurufen, das zum Trainieren eines Modells verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-138">Use this statement to get the complete set of data that was used in a training a model.</span></span>  
  
 <span data-ttu-id="e6ac4-139">**Suchen der Fälle, die zum Testen eines Modells oder einer Struktur verwendet werden**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-139">**Find the cases that are used for testing a model or structure**</span></span>  
 `SELECT  FROM <mining structure.CASES WHERE IsTestingCase()`  
  
 <span data-ttu-id="e6ac4-140">Verwenden Sie diese Anweisung, um die Daten abzurufen, die zum Testen von Miningmodellen reserviert wurden, die sich auf eine bestimmte Struktur beziehen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-140">Use this statement to get the data that has been set aside for testing mining models related to a specific structure.</span></span>  
  
 <span data-ttu-id="e6ac4-141">**Drillthroughs von einem bestimmten Modellmuster zu zugrunde liegenden Falldaten**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-141">**Drillthrough from a specific model pattern to underlying case data**</span></span>  
 `SELECT FROM <model>.CASESWHERE IsTrainingCase() AND IsInNode(<node>)`  
  
 <span data-ttu-id="e6ac4-142">Verwenden Sie diese Anweisung, um ausführliche Falldaten von einem trainierten Modell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-142">Use this statement to retrieve detailed case data from a trained model.</span></span> <span data-ttu-id="e6ac4-143">Sie müssen einen bestimmten Knoten angeben: Beispielsweise benötigen Sie die Knoten-ID des Clusters, der spezifischen Verzweigung der Entscheidungsstruktur usw. Außerdem müssen Sie über Drillthroughberechtigungen für das Modell verfügen, um diese Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-143">You must specify a specific node: for example, you must know the node ID of the cluster, the specific branch of the decision tree, etc. Moreover, you must have drillthrough permissions on the model to run this query.</span></span>  
  
###  <a name="queries-on-model-patterns-statistics-and-attributes"></a><a name="bkmk_Patterns"></a><span data-ttu-id="e6ac4-144">Abfragen für Modell Muster, Statistiken und Attribute</span><span class="sxs-lookup"><span data-stu-id="e6ac4-144">Queries on Model Patterns, Statistics, and Attributes</span></span>  
 <span data-ttu-id="e6ac4-145">Der Inhalt eines Data Mining-Modells ist für viele Zwecke nützlich.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-145">The content of a data mining model is useful for many purposes.</span></span> <span data-ttu-id="e6ac4-146">Eine Modellinhaltsabfrage bietet folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e6ac4-146">With a model content query, you can:</span></span>  
  
-   <span data-ttu-id="e6ac4-147">Extrahieren von Formeln oder Wahrscheinlichkeiten, um eigene Berechnungen anzustellen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-147">Extract formulas or probabilities for making your own calculations.</span></span>  
  
-   <span data-ttu-id="e6ac4-148">Abrufen der Regeln, die in einem Zuordnungsmodell verwendet werden, um eine Vorhersage zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-148">For an association model, retrieve the rules that are used to generate a prediction.</span></span>  
  
-   <span data-ttu-id="e6ac4-149">Abrufen der Beschreibungen bestimmter Regeln, um die Regeln in einer benutzerdefinierten Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-149">Retrieve the descriptions of specific rules so that you can use the rules in a custom application.</span></span>  
  
-   <span data-ttu-id="e6ac4-150">Anzeigen der von einem Zeitreihenmodell erkannten gleitenden Durchschnitte.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-150">View the moving averages detected by a time series model.</span></span>  
  
-   <span data-ttu-id="e6ac4-151">Abrufen der Regressionsformel für ein Segment der Trendlinie.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-151">Obtain the regression formula for some segment of the trend line.</span></span>  
  
-   <span data-ttu-id="e6ac4-152">Abrufen aussagekräftiger Informationen zu Kunden, die als Teil eines bestimmten Clusters identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-152">Retrieve actionable information about customers identified as being part of a specific cluster.</span></span>  
  
 <span data-ttu-id="e6ac4-153">In den folgenden Beispielen werden einige allgemeine Schemas zum Erstellen von Abfragen für den Modellinhalt veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e6ac4-153">The following examples show some of the common patterns for creating queries on the model content:</span></span>  
  
 <span data-ttu-id="e6ac4-154">**Abrufen von Mustern vom Modell**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-154">**Get patterns from the model**</span></span>  
 `SELECT FROM <model>.CONTENT`  
  
 <span data-ttu-id="e6ac4-155">Verwenden Sie diese Anweisung, um ausführliche Informationen zu bestimmten Knoten im Modell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-155">Use this statement to retrieve detailed information about specific nodes in the model.</span></span> <span data-ttu-id="e6ac4-156">Abhängig vom Algorithmustyp kann der Knoten Regeln und Formeln, unterstützende Daten und statistische Varianzdaten usw. enthalten.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-156">Depending on the algorithm type, the node can contain rules and formulas, support and variance statistics, and so forth.</span></span>  
  
 <span data-ttu-id="e6ac4-157">**Abrufen der in einem trainierten Modell verwendeten Attribute**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-157">**Retrieve attributes used in a trained model**</span></span>  
 `CALL System.GetModelAttributes(<model>)`  
  
 <span data-ttu-id="e6ac4-158">Verwenden Sie diese gespeicherte Prozedur, um die Liste der Attribute abzurufen, die von einem Modell verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-158">Use this stored procedure to retrieve the list of attributes that were used by a model.</span></span> <span data-ttu-id="e6ac4-159">Diese Informationen sind beispielsweise hilfreich, um die Attribute zu bestimmen, die aufgrund der Funktionsauswahl ausgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-159">This information is useful for determining attributes that were eliminated as a result of feature selection, for example.</span></span>  
  
 <span data-ttu-id="e6ac4-160">**Abrufen des in einer Data Mining-Dimension gespeicherten Inhalts**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-160">**Retrieve content stored in a data mining dimension**</span></span>  
 `SELECT FROM <model>.DIMENSIONCONTENT`  
  
 <span data-ttu-id="e6ac4-161">Verwenden Sie diese Anweisung, um die Daten aus einer Data Mining-Dimension abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-161">Use this statement to retrieve the data from a data mining dimension.</span></span>  
  
 <span data-ttu-id="e6ac4-162">Dieser Abfragetyp dient hauptsächlich zur internen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-162">This query type is principally for internal use.</span></span> <span data-ttu-id="e6ac4-163">Allerdings wird diese Funktionalität nicht von allen Algorithmen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-163">However, not all algorithms support this functionality.</span></span> <span data-ttu-id="e6ac4-164">Die Unterstützung wird von einem Flag im MINING_SERVICES-Schemarowset angegeben.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-164">Support is indicated by a flag in the MINING_SERVICES schema rowset.</span></span>  
  
 <span data-ttu-id="e6ac4-165">Wenn Sie einen eigenen Plug-In-Algorithmus entwickeln, könnten Sie diese Anweisung verwenden, um den Inhalt des Modells zu Testzwecken zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-165">If you develop your own plug-in algorithm, you might use this statement to verify the content of your model for testing.</span></span>  
  
 <span data-ttu-id="e6ac4-166">**Abrufen der PMML-Darstellung eines Modells**</span><span class="sxs-lookup"><span data-stu-id="e6ac4-166">**Get the PMML representation of a model**</span></span>  
 `SELECT * FROM <model>.PMML`  
  
 <span data-ttu-id="e6ac4-167">Ruft ein XML-Dokument ab, das das Modell im PMML-Format darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-167">Gets an XML document that represents the model in PMML format.</span></span> <span data-ttu-id="e6ac4-168">Nicht alle Modelltypen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-168">Not all model types are supported.</span></span>  
  
##  <a name="examples"></a><a name="bkmk_Examples"></a> <span data-ttu-id="e6ac4-169">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e6ac4-169">Examples</span></span>  
 <span data-ttu-id="e6ac4-170">Obwohl bestimmte Modellinhalte bei allen Algorithmen standardmäßig vorhanden sind, hängt der Inhalt des Modells stark vom Algorithmus ab, mit dem das Modell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-170">Although some model content is standard across algorithms, some parts of the content vary greatly depending on the algorithm that you used to build the model.</span></span> <span data-ttu-id="e6ac4-171">Beim Erstellen einer Inhaltsabfrage müssen Sie daher wissen, welche Informationen im Modell für ein spezifisches Modell am aussagekräftigsten sind.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-171">Therefore, when you create a content query, you must understand what information in the model is most useful to your specific model.</span></span>  
  
 <span data-ttu-id="e6ac4-172">In diesem Abschnitt werden einige Beispiele bereitgestellt, die veranschaulichen, wie sich die Auswahl des Algorithmus auf die Art von Informationen auswirkt, die im Modell gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-172">A few examples are provided in this section to illustrate how the choice of algorithm affects the kind of information that is stored in the model.</span></span> <span data-ttu-id="e6ac4-173">Weitere Informationen zu den Miningmodellinhalten und zu den spezifischen Inhalten der einzelnen Modelltypen finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="e6ac4-173">For more information about mining model content, and the content that is specific to each model type, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
###  <a name="example-1-content-query-on-an-association-model"></a><a name="bkmk_Assoc"></a> <span data-ttu-id="e6ac4-174">Beispiel 1: Inhaltsabfrage eines Zuordnungsmodells</span><span class="sxs-lookup"><span data-stu-id="e6ac4-174">Example 1: Content Query on an Association Model</span></span>  
 <span data-ttu-id="e6ac4-175">Die Anweisung `SELECT FROM <model>.CONTENT`gibt unterschiedliche Informationen zurück, je nachdem, welcher Modelltyp abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-175">The statement, `SELECT FROM <model>.CONTENT`, returns different kinds of information, depending on the type of model you are querying.</span></span> <span data-ttu-id="e6ac4-176">Bei einem Zuordnungsmodell ist eine der wichtigsten Informationen der *Knotentyp*.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-176">For an association model, a key piece of information is the *node type*.</span></span> <span data-ttu-id="e6ac4-177">Knoten sind wie Container für Informationen im Modellinhalt.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-177">Nodes are like containers for information in the model content.</span></span> <span data-ttu-id="e6ac4-178">In einem Zuordnungsmodell haben Knoten, die Regeln repräsentieren, den NODE_TYPE-Wert 8, während Knoten, die Itemsets darstellen, den NODE_TYPE-Wert 7 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-178">In an association model, nodes that represent rules have a NODE_TYPE value of 8, whereas nodes that represent itemsets have a NODE_TYPE value of 7.</span></span>  
  
 <span data-ttu-id="e6ac4-179">Die folgende Abfrage gibt daher die obersten 10 Itemsets geordnet nach Unterstützung (Standardreihenfolge) zurück.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-179">Thus, the following query returns the top 10 itemsets, ranked by support (the default ordering).</span></span>  
  
```  
SELECT TOP 10 NODE_DESCRIPTION, NODE_PROBABILITY, SUPPORT  
FROM <model>.CONTENT WHERE NODE_TYPE = 7  
```  
  
 <span data-ttu-id="e6ac4-180">Die folgende Abfrage baut auf diesen Informationen auf.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-180">The following query builds on this information.</span></span> <span data-ttu-id="e6ac4-181">Die Abfrage gibt drei Spalten zurück: die ID des Knotens, die komplette Regel und das Produkt auf der rechten Seite des Itemsets, d. h. das Produkt, das vorhergesagt wird, dass es mit einigen anderen Produkten als Teil eines Itemsets verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-181">The query returns three columns: the ID of the node, the complete rule, and the product on the right-hand side of the itemset-that is, the product that is predicted to be associated with some other products as part of an itemset.</span></span>  
  
```  
SELECT FLATTENED NODE_UNIQUE_NAME, NODE_DESCRIPTION,  
     (SELECT RIGHT(ATTRIBUTE_NAME, (LEN(ATTRIBUTE_NAME)-LEN('Association model name')))   
FROM NODE_DISTRIBUTION  
WHERE LEN(ATTRIBUTE_NAME)>2  
)   
AS RightSideProduct  
FROM [<Association model name>].CONTENT  
WHERE NODE_TYPE = 8   
ORDER BY NODE_SUPPORT DESC  
```  
  
 <span data-ttu-id="e6ac4-182">Das FLATTENED-Schlüsselwort gibt an, dass das geschachtelte Rowset in eine vereinfachte Tabelle konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-182">The FLATTENED keyword indicates that the nested rowset should be converted into a flattened table.</span></span> <span data-ttu-id="e6ac4-183">Das Attribut, das das Produkt auf der rechten Seite der Regel darstellt, ist in der NODE_DISTRIBUTION-Tabelle enthalten. Daher rufen wir nur die Zeile ab, die einen Attributnamen enthält. Dazu wird die Anforderung hinzugefügt, dass die Länge größer als zwei sein muss.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-183">The attribute that represents the product on the right-hand side of the rule is contained in the NODE_DISTRIBUTION table; therefore, we retrieve only the row that contains an attribute name, by adding a requirement that the length be greater than 2.</span></span>  
  
 <span data-ttu-id="e6ac4-184">Eine einfache Zeichenfolgenfunktion wird verwendet, um den Namen des Modells aus der dritten Spalte zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-184">A simple string function is used to remove the name of the model from the third column.</span></span> <span data-ttu-id="e6ac4-185">(Üblicherweise wird den Werten geschachtelter Spalten der Modellname als Präfix vorangestellt.)</span><span class="sxs-lookup"><span data-stu-id="e6ac4-185">(Usually the model name is prefixed to the values of nested columns.)</span></span>  
  
 <span data-ttu-id="e6ac4-186">Die WHERE-Klausel gibt an, dass der NODE_TYPE-Wert 8 betragen sollte, um nur Regeln abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-186">The WHERE clause specifies that the value of NODE_TYPE should be 8, to retrieve only rules.</span></span>  
  
 <span data-ttu-id="e6ac4-187">Weitere Beispiele finden Sie unter [Beispiele für Zuordnungsmodellabfragen](association-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e6ac4-187">For more examples, see [Association Model Query Examples](association-model-query-examples.md).</span></span>  
  
###  <a name="example-2-content-query-on-a-decision-trees-model"></a><a name="bkmk_DecTree"></a> <span data-ttu-id="e6ac4-188">Beispiel 2: Inhaltsabfrage für ein Entscheidungsstrukturmodell</span><span class="sxs-lookup"><span data-stu-id="e6ac4-188">Example 2: Content Query on a Decision Trees Model</span></span>  
 <span data-ttu-id="e6ac4-189">Ein Entscheidungsstrukturmodell kann für Vorhersagen und Klassifizierungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-189">A decision tree model can be used for prediction as well as for classification.</span></span>  <span data-ttu-id="e6ac4-190">In diesem Beispiel wird davon ausgegangen, dass Sie mithilfe des Modells ein Ergebnis vorhersagen, aber gleichzeitig ermitteln möchten, welche Faktoren oder Regeln verwendet werden können, um das Ergebnis zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-190">This example assumes that you are using the model to predict an outcome, but you also want to find out which factors or rules can be used to classify the outcome.</span></span>  
  
 <span data-ttu-id="e6ac4-191">In einem Entscheidungsstrukturmodell werden Knoten verwendet, um sowohl Strukturen als auch Blattknoten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-191">In a decision tree model, nodes are used to represent both trees and leaf nodes.</span></span> <span data-ttu-id="e6ac4-192">Die Beschriftung jedes Knotens enthält die Beschreibung des Pfads zum Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-192">The caption for each node contains the description of the path to the outcome.</span></span> <span data-ttu-id="e6ac4-193">Um den Pfad zu einem bestimmten Ergebnis nachzuverfolgen, müssen Sie daher den Knoten identifizieren, der das Ergebnis enthält, und die Details für diesen Knoten abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-193">Therefore, to trace the path for any particular outcome, you need to identify the node that contains it, and get the details for that node.</span></span>  
  
 <span data-ttu-id="e6ac4-194">In der Vorhersageabfrage fügen Sie die Vorhersagefunktion [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx) hinzu, um die ID verwandten Knotens abzurufen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6ac4-194">In your prediction query, you add the prediction function [PredictNodeId &#40;DMX&#41;](/sql/dmx/predictnodeid-dmx), to get the ID of the related node, as shown in the following example:</span></span>  
  
```  
SELECT  Predict([Bike Buyer]), PredictNodeID([Bike Buyer])   
FROM [<decision tree model name>]  
PREDICTION JOIN   
<input rowset>   
```  
  
 <span data-ttu-id="e6ac4-195">Sobald Sie die ID des Knotens, der das Ergebnis enthält, ermittelt haben, können Sie die Regel oder den Pfad abrufen, der die Vorhersage erklärt. Erstellen Sie dazu eine Inhaltsabfrage, die NODE_CAPTION beinhaltet, wie im Folgenden gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e6ac4-195">Once you have the ID of the node that contains the outcome, you can retrieve the rule or path that explains the prediction by creating a content query that includes the NODE_CAPTION, as follows:</span></span>  
  
```  
SELECT NODE_CAPTION  
FROM [<decision tree model name>]   
WHERE NODE_UNIQUE_NAME= '<node id>'  
```  
  
 <span data-ttu-id="e6ac4-196">Weitere Beispiele finden Sie unter [Beispiele für Entscheidungsstruktur-Modellabfragen](decision-trees-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e6ac4-196">For more examples, see [Decision Trees Model Query Examples](decision-trees-model-query-examples.md).</span></span>  
  
##  <a name="working-with-the-query-results"></a><a name="bkmk_Results"></a><span data-ttu-id="e6ac4-197">Arbeiten mit den Abfrage Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-197">Working with the Query Results</span></span>  
 <span data-ttu-id="e6ac4-198">Wie in den Beispielen veranschaulicht, werden von Inhaltsabfragen am häufigsten Tabellenrowsets zurückgegeben, sie können jedoch auch Informationen aus geschachtelten Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-198">As the examples demonstrate, content queries mostly return tabular rowsets, but can also include information from nested columns.</span></span> <span data-ttu-id="e6ac4-199">Sie können das zurückgegebene Rowset zwar vereinfachen, dadurch könnte die Bearbeitung der Ergebnisse jedoch komplexer werden.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-199">You can flatten the rowset that is returned, but this can make working with results more complex.</span></span> <span data-ttu-id="e6ac4-200">Besonders der Inhalt des NODE_DISTRIBUTION-Knotens ist geschachtelt, enthält aber viele interessante Informationen zum Modell.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-200">The content of the NODE_DISTRIBUTION node in particular is nested, but contains much interesting information about the model.</span></span>  
  
 <span data-ttu-id="e6ac4-201">Weitere Informationen zum Arbeiten mit hierarchischen Rowsets finden Sie in der OLEDB-Spezifikation von MSDN.</span><span class="sxs-lookup"><span data-stu-id="e6ac4-201">For more information about how to work with hierarchical rowsets, see the OLEDB specification on MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ac4-202">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-202">See Also</span></span>  
 <span data-ttu-id="e6ac4-203">[Grundlegendes zur DMX-SELECT-Anweisung](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="e6ac4-203">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 [<span data-ttu-id="e6ac4-204">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="e6ac4-204">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
