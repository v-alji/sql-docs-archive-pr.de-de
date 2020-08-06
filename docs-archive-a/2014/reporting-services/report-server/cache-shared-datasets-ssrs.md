---
title: Zwischenspeichern von freigegebenen Datasets (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4acb1bbe-1c04-4979-b893-dc1b1c5039b6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5b08149b075ae3fd267baf2dad0ca342457958c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619613"
---
# <a name="cache-shared-datasets-ssrs"></a><span data-ttu-id="d9b79-102">Zwischenspeichern von freigegebenen Datasets (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9b79-102">Cache Shared Datasets (SSRS)</span></span>
  <span data-ttu-id="d9b79-103">Abfrageergebnisse für ein freigegebenes Dataset können in einen Cache kopiert werden, um konsistente Daten für mehrere Berichte bereitzustellen und die Antwortzeit für die Datasetabfrage zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="d9b79-103">Query results for a shared dataset can be copied to a cache to provide consistent data for multiple reports and to improve response time for the dataset query.</span></span> <span data-ttu-id="d9b79-104">Freigegebene Datasets können ähnlich wie Berichte so konfiguriert werden, dass sie bei der erstmaligen Verwendung oder nach einem angegebenen Zeitplan zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d9b79-104">Like reports, you can configure a shared dataset to be cached on first use or by specifying a schedule.</span></span>  
  
 <span data-ttu-id="d9b79-105">Ein freigegebenes Dataset kann in mehreren Berichten enthalten oder Teil einer Komponentendefinition sein.</span><span class="sxs-lookup"><span data-stu-id="d9b79-105">A shared dataset can be included in multiple reports or as part of component definitions.</span></span> <span data-ttu-id="d9b79-106">Indem Sie das freigegebene Dataset zwischenspeichern, stellen Sie für alle Berichte, die das Dataset verwenden, konsistente Daten bereit und reduzieren gleichzeitig die Anzahl der in der externen Datenquelle ausgeführten Datasetabfragen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-106">By caching the shared dataset, you provide a consistent set of data for all reports that use it, and also reduce the number of times that the dataset query runs against the external data source.</span></span>  
  
 <span data-ttu-id="d9b79-107">Die folgende Liste enthält Beispiele dafür, wann ein freigegebenes Dataset zwischengespeichert werden sollte:</span><span class="sxs-lookup"><span data-stu-id="d9b79-107">The following list provides examples of when to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="d9b79-108">Die Ausführung der Abfrage nimmt viel Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="d9b79-108">The query takes a substantial amount of time to run.</span></span>  
  
-   <span data-ttu-id="d9b79-109">Die Abfrage verwendet Parameter, die Anzahl der Parameterkombinationen ist jedoch meist klein.</span><span class="sxs-lookup"><span data-stu-id="d9b79-109">The query takes parameters, but most of the time, the number of parameter combinations is small.</span></span> <span data-ttu-id="d9b79-110">Durch jede Kombination werden zwischengespeicherte Abfrageergebnisse generiert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-110">Each combination creates cached query results.</span></span>  
  
-   <span data-ttu-id="d9b79-111">Die Abfrage wird täglich, wöchentlich oder monatlich zu festen Zeiten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b79-111">The query runs at predictable times of the day, week, or month.</span></span>  
  
-   <span data-ttu-id="d9b79-112">Die Abfrage wird in Reaktion auf einen Verweis auf ein freigegebenes Dataset in einem Bericht ausgeführt, der per E-Mail übermittelt wird, und es wird erwartet, dass eine große Anzahl von Personen in kurzer Zeit auf den Link klicken wird.</span><span class="sxs-lookup"><span data-stu-id="d9b79-112">The query runs as the result of a shared dataset reference in a report that is delivered via e-mail, where a large number of people are likely to click the link in a short span of time.</span></span>  
  
-   <span data-ttu-id="d9b79-113">Die folgende Liste enthält Beispiele dafür, wann ein freigegebenes Dataset nicht zwischengespeichert werden sollte:</span><span class="sxs-lookup"><span data-stu-id="d9b79-113">The following list provides examples of when not to cache a shared dataset:</span></span>  
  
-   <span data-ttu-id="d9b79-114">Die Abfrageergebnisse müssen immer die neuesten Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d9b79-114">The query results must always include the most recent data.</span></span>  
  
-   <span data-ttu-id="d9b79-115">Die Abfrage wird schnell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b79-115">The query runs quickly.</span></span>  
  
-   <span data-ttu-id="d9b79-116">Die Abfrage wird selten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9b79-116">The query runs infrequently.</span></span>  
  
-   <span data-ttu-id="d9b79-117">Die Abfrage verwendet Parameter, die Anzahl der Parameterkombinationen ist groß, und keine Kombination ist wahrscheinlicher als eine andere.</span><span class="sxs-lookup"><span data-stu-id="d9b79-117">The query takes parameters, the number of parameter combinations is large, and no combination is more likely than another.</span></span>  
  
-   <span data-ttu-id="d9b79-118">Für die Datenquelle, auf der das freigegebene Dataset basiert, werden Anmeldeinformationen angefordert oder integrierte Windows-Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9b79-118">The data source that the shared dataset is based on has Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="d9b79-119">Der Filter für das freigegebene Dataset oder die Abfrage enthält einen Ausdruck mit einem Verweis auf die globale User-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d9b79-119">The shared dataset filter or the query contains an expression with a reference to the global collection User.</span></span>  
  
 <span data-ttu-id="d9b79-120">Wenn ein Benutzer Berichtsparameterwerte auswählt, die sich von den Standardwerten unterscheiden, die für das zwischengespeicherte Resultset angegeben wurden, wird die Datasetabfrage aktiv ausgeführt, und die zwischengespeicherten Ergebnisse werden nicht für diese Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9b79-120">If a user chooses report parameter values that differ from the default values that are specified for the cached result set, the dataset query runs actively and the cached results are not used for that query.</span></span>  
  
## <a name="caching-shared-datasets"></a><span data-ttu-id="d9b79-121">Zwischenspeichern freigegebener Datasets</span><span class="sxs-lookup"><span data-stu-id="d9b79-121">Caching Shared Datasets</span></span>  
 <span data-ttu-id="d9b79-122">Um das Zwischenspeichern für ein freigegebenes Dataset zu aktivieren, müssen Sie die Cacheoption für das freigegebene Dataset auswählen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-122">To enable caching for a shared dataset, you must select the cache option on the shared dataset.</span></span> <span data-ttu-id="d9b79-123">Nachdem das Zwischenspeichern aktiviert wurde, werden die Abfrageergebnisse für ein freigegebenes Dataset bei der ersten Verwendung in den Cache kopiert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-123">After caching is enabled, the query results for a shared dataset are copied to the cache on first use.</span></span> <span data-ttu-id="d9b79-124">Wenn das freigegebene Dataset über Parameter verfügt, wird durch jede Parameterkombination ein neuer Eintrag im Cache erstellt.</span><span class="sxs-lookup"><span data-stu-id="d9b79-124">If the shared dataset has parameters, each combination of parameters creates a new entry in the cache.</span></span>  
  
 <span data-ttu-id="d9b79-125">Während die Abfrageergebnisse für eine bestimmte Parameterkombination im Cache enthalten sind, verwendet jeder Bericht, dessen Verarbeitung gestartet wird und der einen Verweis auf das freigegebene Dataset mit den jeweiligen Parameterwerten enthält, die zwischengespeicherten Daten.</span><span class="sxs-lookup"><span data-stu-id="d9b79-125">While the query results for a specific parameter combination are in the cache, each report that is launched for processing and that includes a reference to the shared dataset with those parameter values will use the cached data.</span></span>  
  
 <span data-ttu-id="d9b79-126">Sie können angeben, wie lange die Daten im Cache beibehalten werden, bevor sie ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="d9b79-126">You can specify how long to keep data in the cache before it expires.</span></span> <span data-ttu-id="d9b79-127">Weitere Informationen finden Sie unter [Zwischenspeichern (Seite), Freigegebene Datasets &#40;Berichts-Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d9b79-127">For more information, see [Caching Page, Shared Datasets &#40;Report Manager&#41;](../caching-page-shared-datasets-report-manager.md).</span></span>  
  
## <a name="preloading-the-cache"></a><span data-ttu-id="d9b79-128">Vorabladen des Caches</span><span class="sxs-lookup"><span data-stu-id="d9b79-128">Preloading the Cache</span></span>  
 <span data-ttu-id="d9b79-129">Sie können den Cache vorab laden, indem Sie einen Cacheaktualisierungsplan erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-129">You can preload the cache by creating a cache refresh plan.</span></span> <span data-ttu-id="d9b79-130">Mit einem Aktualisierungsplan können Sie unter Verwendung eines elementspezifischen Zeitplans oder eines freigegebenen Zeitplans angeben, wie oft der Cache aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9b79-130">With a refresh plan, you can specify how often to refresh the cache by using an item-specific schedule or a shared schedule.</span></span> <span data-ttu-id="d9b79-131">Damit nicht mehrere Cacheeinträge für das gleiche Element gespeichert werden, sollte der angegebene Zeitplan genügend Zeit zur Abfrageverarbeitung in der externen Datenquelle vorsehen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-131">To avoid multiple cache entries for the same item, the schedule that you specify should allow enough time for query processing on the external data source.</span></span> <span data-ttu-id="d9b79-132">Wenn die Abfrageausführung z. B. 20 Minuten benötigt, sollte der Aktualisierungszeitplan größer als 20 Minuten sein.</span><span class="sxs-lookup"><span data-stu-id="d9b79-132">For example, if the query takes 20 minutes to run, the refresh schedule should be greater than 20 minutes.</span></span> <span data-ttu-id="d9b79-133">Weitere Informationen finden Sie unter [Schedules](../subscriptions/schedules.md).</span><span class="sxs-lookup"><span data-stu-id="d9b79-133">For more information, see [Schedules](../subscriptions/schedules.md).</span></span>  
  
 <span data-ttu-id="d9b79-134">Beim Erstellen eines Cacheaktualisierungsplans für ein freigegebenes Dataset gelten die folgenden Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-134">To create a cache refresh plan for a shared dataset, the following conditions apply.</span></span>  
  
-   <span data-ttu-id="d9b79-135">Für das freigegebene Dataset muss das Zwischenspeichern aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="d9b79-135">The shared dataset must be enabled for caching.</span></span>  
  
-   <span data-ttu-id="d9b79-136">Von der freigegebenen Datenquelle, von der das freigegebene Dataset abhängig ist, dürfen keine Anmeldeinformationen angefordert bzw. integrierte Windows-Anmeldeinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b79-136">The shared data source that the shared dataset depends on cannot use Prompt or Windows Integrated credentials.</span></span>  
  
-   <span data-ttu-id="d9b79-137">Wenn das freigegebene Dataset über Parameter verfügt, müssen Sie statische Standardwerte für alle Parameter angeben, die nicht als schreibgeschützt gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="d9b79-137">If the shared dataset has parameters, you must specify static default values for each parameter that is not marked read-only.</span></span> <span data-ttu-id="d9b79-138">Schreibgeschützte Parameter verwenden immer den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-138">Read-only parameters will always use the default value.</span></span> <span data-ttu-id="d9b79-139">Um ein freigegebenes Dataset für mehrere Parameterkombinationen zwischenzuspeichern, müssen Sie einen separaten Cacheaktualisierungsplan für jede Kombination von Werten erstellen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-139">To cache a shared dataset for multiple combinations of parameters, you must create a separate cache refresh plan for each combination of values.</span></span> <span data-ttu-id="d9b79-140">Parameter können keine Verweise auf andere Datasets enthalten.</span><span class="sxs-lookup"><span data-stu-id="d9b79-140">Parameters cannot contain references to other datasets.</span></span>  
  
-   <span data-ttu-id="d9b79-141">Jeder Cacheaktualisierungsplan ist nur einem freigegebenen Dataset oder Bericht zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d9b79-141">Each cache refresh plan is associated with only one shared dataset or report.</span></span>  
  
-   <span data-ttu-id="d9b79-142">Sie benötigen die ReadPolicy-Berechtigung und UpdatePolicy-Berechtigung für das freigegebene Dataset.</span><span class="sxs-lookup"><span data-stu-id="d9b79-142">You must have ReadPolicy and UpdatePolicy permissions on the shared dataset.</span></span>  
  
 <span data-ttu-id="d9b79-143">Cacheaktualisierungspläne können sowohl auf freigegebene Datasets als auch auf Berichte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b79-143">Cache refresh plans apply to both shared datasets and reports.</span></span> <span data-ttu-id="d9b79-144">Weitere Informationen finden Sie unter [Optionen zur Cacheaktualisierung (Berichts-Manager)](../cache-refresh-options-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d9b79-144">For more information, see [Cache Refresh Options &#40;Report Manager&#41;](../cache-refresh-options-report-manager.md).</span></span>  
  
## <a name="conditions-that-cause-cache-expiration"></a><span data-ttu-id="d9b79-145">Bedingungen, die zum Ablaufen des Caches führen</span><span class="sxs-lookup"><span data-stu-id="d9b79-145">Conditions that Cause Cache Expiration</span></span>  
 <span data-ttu-id="d9b79-146">Die folgenden Bedingungen können bewirken, dass ein Cache für ein freigegebenes Dataset ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="d9b79-146">The following conditions can cause a shared dataset cache to become not valid.</span></span>  
  
-   <span data-ttu-id="d9b79-147">Eine Zeitplanbedingung läuft ab.</span><span class="sxs-lookup"><span data-stu-id="d9b79-147">A schedule condition expires.</span></span> <span data-ttu-id="d9b79-148">Das Timeout für den Cache oder die Ablaufzeit wird erreicht.</span><span class="sxs-lookup"><span data-stu-id="d9b79-148">The cache times out or the expiration time occurs.</span></span>  
  
-   <span data-ttu-id="d9b79-149">Ein freigegebener Zeitplan wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d9b79-149">A shared schedule is deleted.</span></span>  
  
-   <span data-ttu-id="d9b79-150">Änderungen an einem freigegebenen Zeitplan.</span><span class="sxs-lookup"><span data-stu-id="d9b79-150">Changes to a shared schedule.</span></span> <span data-ttu-id="d9b79-151">Freigegebene Zeitpläne können angehalten werden, was sich auch auf die Ablaufzeit eines Caches auswirkt.</span><span class="sxs-lookup"><span data-stu-id="d9b79-151">Shared schedules can be paused, which also affects when a cache expires.</span></span>  
  
-   <span data-ttu-id="d9b79-152">Die Abfragedefinition für das freigegebene Dataset wird geändert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-152">The query definition for the shared dataset changes.</span></span>  
  
-   <span data-ttu-id="d9b79-153">Die Anmeldeinformationen für die freigegebene Datenquelle, von der das freigegebene Dataset abhängig ist, werden geändert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-153">The credentials for the shared data source that the shared dataset depends on change.</span></span>  
  
-   <span data-ttu-id="d9b79-154">Die Cacheoptionen für das freigegebene Dataset werden geändert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-154">The cache options for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="d9b79-155">Die Standardwerte für schreibgeschützte Parameter für das freigegebene Dataset werden geändert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-155">The default values for read-only parameters for the shared dataset change.</span></span>  
  
-   <span data-ttu-id="d9b79-156">Die Filter, die Teil der Definition für das freigegebene Dataset sind, werden geändert.</span><span class="sxs-lookup"><span data-stu-id="d9b79-156">The filters that are part of the shared dataset definition change.</span></span>  
  
-   <span data-ttu-id="d9b79-157">Das freigegebene Dataset wird vom Berichtsserver gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d9b79-157">The shared dataset is deleted from the report server.</span></span> <span data-ttu-id="d9b79-158">Wenn ein freigegebenes Dataset gelöscht wird, werden zugeordnete zwischengespeicherte Kopien und Cacheaktualisierungspläne ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d9b79-158">When a shared dataset is deleted, associated cached copies and cache refresh plans are also deleted.</span></span>  
  
 <span data-ttu-id="d9b79-159">Aktualisierungen an Cacheaktualisierungsplänen für freigegebene Datasets haben keinen Einfluss auf Berichte, die bereits verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d9b79-159">Updates to cache refresh plans for shared datasets do not affect reports that are already being processed.</span></span> <span data-ttu-id="d9b79-160">Aktualisierungen an einem Cacheaktualisierungsplan wirken sich nur auf zukünftig gestartete Berichte aus, die auf das freigegebene Dataset verweisen.</span><span class="sxs-lookup"><span data-stu-id="d9b79-160">Updating a cache refresh plan affects only future launches of reports that reference the shared dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b79-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9b79-161">See Also</span></span>  
 [<span data-ttu-id="d9b79-162">Verwalten von freigegebenen Datasets</span><span class="sxs-lookup"><span data-stu-id="d9b79-162">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
