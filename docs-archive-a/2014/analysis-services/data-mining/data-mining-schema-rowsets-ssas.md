---
title: Abfragen der Data Mining-Schemarowsets (Analysis Services-Data Mining) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620677"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="656fe-102">Abfragen der Data Mining-Schemarowsets (Analysis Services – Data Mining)</span><span class="sxs-lookup"><span data-stu-id="656fe-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="656fe-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]werden viele der bestehenden OLE DB Data Mining-Schemarowsets als Gruppe von Systemtabellen verfügbar gemacht, die Sie mit DMX (Data Mining Extensions)-Anweisungen abfragen können.</span><span class="sxs-lookup"><span data-stu-id="656fe-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="656fe-104">Durch das Erstellen von Queries für das Data Mining-Schemarowset können Sie die zur Verfügung stehenden Services identifizieren, Statusupdates für Ihre Modelle und Strukturen erhalten und Details über den Inhalt des Modells oder Parameter erfahren.</span><span class="sxs-lookup"><span data-stu-id="656fe-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="656fe-105">Eine Beschreibung des Data Mining-Schemarowsets finden Sie unter [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="656fe-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="656fe-106">Sie können auch das Data Mining-Schemarowset mithilfe von XMLA abfragen.</span><span class="sxs-lookup"><span data-stu-id="656fe-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="656fe-107">Weitere Informationen dazu, wie Sie dies in SQL Server Management Studio tun, finden Sie unter [Erstellen einer Data Mining-Abfrage mit XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="656fe-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="656fe-108">Liste der Data Mining-Schemarowsets</span><span class="sxs-lookup"><span data-stu-id="656fe-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="656fe-109">In der folgenden Tabelle werden die Data Mining-Schemarowsets, die möglicherweise zum Abfragen und Überwachen nützlich sind, aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="656fe-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="656fe-110">Rowsetname</span><span class="sxs-lookup"><span data-stu-id="656fe-110">Rowset name</span></span>|<span data-ttu-id="656fe-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="656fe-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="656fe-112">DMSCHEMA_MINING_MODELS-Rowset</span><span class="sxs-lookup"><span data-stu-id="656fe-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="656fe-113">Listet alle Miningmodelle im aktuellen Kontext auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="656fe-114">Beinhaltet Informationen wie das Erstellungsdatum, Parameter, die zur Erstellung des Modells verwendet wurden, und die Größe des Trainingsatzes.</span><span class="sxs-lookup"><span data-stu-id="656fe-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="656fe-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="656fe-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="656fe-116">Listet alle in Miningmodellen verwendeten Spalten im aktuellen Kontext auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="656fe-117">Zu den Informationen gehören das Zuordnen der Quellspalte der Miningstruktur, der Datentyp, die Genauigkeit und Vorhersagefunktionen, die mit der Spalte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="656fe-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="656fe-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="656fe-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="656fe-119">Listet alle Miningstrukturen im aktuellen Kontext auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="656fe-120">Hierzu gehören Informationen darüber, ob die Struktur Daten enthält, das Datum der letzten Verarbeitung der Struktur und gegebenenfalls die Definition des zurückgehaltenen Datasets.</span><span class="sxs-lookup"><span data-stu-id="656fe-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="656fe-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="656fe-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="656fe-122">Listet alle in Miningstrukturen verwendeten Spalten im aktuellen Kontext auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="656fe-123">Zu den Informationen gehören Inhaltstyp und Datentyp, NULL-Zulässigkeit und ob die Spalte geschachtelte Tabellendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="656fe-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="656fe-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="656fe-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="656fe-125">Listet alle Miningdienste oder Algorithmen, die auf dem angegebenen Server verfügbar sind, auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="656fe-126">Informationen enthalten unterstützte Modellierungsflags, Eingabetypen und unterstützte Datenquellentypen.</span><span class="sxs-lookup"><span data-stu-id="656fe-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="656fe-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="656fe-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="656fe-128">Listet alle Parameter für die Miningdienste, die auf der angegebenen Instanz verfügbar sind, auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="656fe-129">Die Informationen enthalten den Datentyp für jeden Parameter, die Standardwerte und die oberen und unteren Grenzen.</span><span class="sxs-lookup"><span data-stu-id="656fe-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="656fe-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="656fe-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="656fe-131">Gibt den Inhalt des Modells zurück, wenn das Modell verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="656fe-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="656fe-132">Weitere Informationen finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="656fe-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="656fe-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="656fe-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="656fe-134">Listet alle Datenbanken (Kataloge) in der aktuellen Instanz von Analysis Services auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="656fe-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="656fe-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="656fe-136">Listet alle Datenquellen in der aktuellen Instanz von Analysis Services auf.</span><span class="sxs-lookup"><span data-stu-id="656fe-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="656fe-137">Die Liste in der Tabelle ist nicht vollständig; es werden nur die Rowsets angezeigt, die für die Problembehandlung am wichtigsten sein könnten.</span><span class="sxs-lookup"><span data-stu-id="656fe-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="656fe-138">Beispiele</span><span class="sxs-lookup"><span data-stu-id="656fe-138">Examples</span></span>  
 <span data-ttu-id="656fe-139">Der folgende Abschnitt enthält einige Beispiele für Abfragen gegen die Data Mining-Schemarowsets.</span><span class="sxs-lookup"><span data-stu-id="656fe-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="656fe-140">Beispiel 1: Auflisten von Data Mining-Diensten</span><span class="sxs-lookup"><span data-stu-id="656fe-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="656fe-141">Die folgende Abfrage gibt eine Liste der Miningdienste zurück, die auf dem aktuellen Server zur Verfügung stehen, d. h. die aktivierten Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="656fe-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="656fe-142">Die für jeden Miningdienst bereitgestellten Spalten beinhalten die Modellierungsflags und Inhaltstypen, die von jedem Algorithmus verwendet werden können, die GUID für jeden Dienst und jegliche Vorhersagenbeschränkungen, die für jeden Dienst hinzugefügt worden sein könnten.</span><span class="sxs-lookup"><span data-stu-id="656fe-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="656fe-143">Beispiel 2: Auflisten von Miningmodellparametern</span><span class="sxs-lookup"><span data-stu-id="656fe-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="656fe-144">Das folgende Beispiel gibt die Parameter zurück, die verwendet wurden, um ein bestimmtes Miningmodell zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="656fe-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="656fe-145">Beispiel 3: Auflisten aller Rowsets</span><span class="sxs-lookup"><span data-stu-id="656fe-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="656fe-146">Im folgenden Beispiel wird eine umfassende Liste der Rowsets, die auf dem aktuellen Server verfügbar sind, zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="656fe-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="656fe-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="656fe-147">See Also</span></span>  
 [<span data-ttu-id="656fe-148">Konzepte zur Problembehandlung (Analysis Services &amp;ndash; Data Mining)</span><span class="sxs-lookup"><span data-stu-id="656fe-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
