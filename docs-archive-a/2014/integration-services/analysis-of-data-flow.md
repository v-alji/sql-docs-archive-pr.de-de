---
title: Analyse des Datenflusses | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5654cb30-cad2-470c-97b3-59cb331033e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 184b53d3e982cd80d7c9c0909538a751585ae21d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615528"
---
# <a name="analysis-of-data-flow"></a><span data-ttu-id="93e30-102">Analyse des Datenflusses</span><span class="sxs-lookup"><span data-stu-id="93e30-102">Analysis of Data Flow</span></span>
  <span data-ttu-id="93e30-103">Mithilfe der Daten Bank Sicht [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md) können Sie `SSISDB` den Datenfluss von Paketen analysieren.</span><span class="sxs-lookup"><span data-stu-id="93e30-103">You can use the [catalog.execution_data_statistics](../relational-databases/statistics/statistics.md)`SSISDB` database view to analyze the data flow of packages.</span></span> <span data-ttu-id="93e30-104">In dieser Sicht wird immer dann eine Zeile angezeigt, wenn eine Datenflusskomponente Daten an eine Downstreamkomponente sendet.</span><span class="sxs-lookup"><span data-stu-id="93e30-104">This view displays a row each time a data flow component sends data to a downstream component.</span></span> <span data-ttu-id="93e30-105">Anhand der Informationen können Sie ein tieferes Verständnis der Zeilen erhalten, die an jede Komponente gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="93e30-105">The information can be used to gain a deeper understanding of the rows that are sent to each component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93e30-106">Der Protokollierungsgrad muss auf **Ausführlich** festgelegt werden, um Informationen mit der catalog.execution_data_statistics-Sicht aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="93e30-106">The logging level must be set to **Verbose** in order to capture information with the catalog.execution_data_statistics view.</span></span>  
  
 <span data-ttu-id="93e30-107">Im folgenden Beispiel wird die Anzahl der Zeilen angezeigt, die zwischen Komponenten eines Pakets gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93e30-107">The following example displays the number of rows sent between components of a package.</span></span>  
  
```  
use SSISDB  
select package_name, task_name, source_component_name, destination_component_name, rows_sent  
from catalog.execution_data_statistics  
where execution_id = 132  
order by source_component_name, destination_component_name  
  
```  
  
 <span data-ttu-id="93e30-108">Im folgenden Beispiel wird die Anzahl der Zeilen pro Millisekunde berechnet, die von jeder Komponente für eine bestimmte Ausführung gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="93e30-108">The following example calculates the number of rows per millisecond sent by each component for a specific execution.</span></span> <span data-ttu-id="93e30-109">Die berechneten Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="93e30-109">The calculated values are:</span></span>  
  
-   <span data-ttu-id="93e30-110">**total_rows** : Die Summe aller von der Komponente gesendeten Zeilen</span><span class="sxs-lookup"><span data-stu-id="93e30-110">**total_rows** - the sum of all the rows sent by the component</span></span>  
  
-   <span data-ttu-id="93e30-111">**wall_clock_time_ms:** Die insgesamt verstrichene Ausführungszeit, in Millisekunden, für jede Komponente</span><span class="sxs-lookup"><span data-stu-id="93e30-111">**wall_clock_time_ms** - the total elapsed execution time, in milliseconds, for each component</span></span>  
  
-   <span data-ttu-id="93e30-112">**num_rows_per_millisecond:** Die Anzahl der pro Millisekunde von jeder Komponente gesendeten Zeilen</span><span class="sxs-lookup"><span data-stu-id="93e30-112">**num_rows_per_millisecond** - the number of rows per millisecond sent by each component</span></span>  
  
 <span data-ttu-id="93e30-113">Die- `HAVING` Klausel wird verwendet, um einen Fehler aufgrund einer Division durch 0 in den Berechnungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="93e30-113">The `HAVING` clause is used to prevent a divide-by-zero error in the calculations.</span></span>  
  
```  
use SSISDB  
select source_component_name, destination_component_name,  
    sum(rows_sent) as total_rows,  
    DATEDIFF(ms,min(created_time),max(created_time)) as wall_clock_time_ms,  
    ((0.0+sum(rows_sent)) / (datediff(ms,min(created_time),max(created_time)))) as [num_rows_per_millisecond]  
from [catalog].[execution_data_statistics]  
where execution_id = 132  
group by source_component_name, destination_component_name  
having (datediff(ms,min(created_time),max(created_time))) > 0  
order by source_component_name desc  
  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="93e30-114">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="93e30-114">Related Tasks</span></span>  
 [<span data-ttu-id="93e30-115">Debuggen des Datenflusses</span><span class="sxs-lookup"><span data-stu-id="93e30-115">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="93e30-116">Behandlung von Problemen mit Paketausführungstools</span><span class="sxs-lookup"><span data-stu-id="93e30-116">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
## <a name="see-also"></a><span data-ttu-id="93e30-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93e30-117">See Also</span></span>  
 [<span data-ttu-id="93e30-118">Daten in Datenflüssen</span><span class="sxs-lookup"><span data-stu-id="93e30-118">Data in Data Flows</span></span>](data-flow/data-in-data-flows.md)  
  
  
