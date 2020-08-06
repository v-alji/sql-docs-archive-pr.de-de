---
title: Bewährte Vorgehensweisen für den Aufruf von systemintern kompilierten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f39fc1c7-cfec-4a95-97f6-6b95954694bb
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d07d0e290d1fbd9b324235e64734a399bf7801d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609205"
---
# <a name="best-practices-for-calling-natively-compiled-stored-procedures"></a><span data-ttu-id="05991-102">Bewährte Vorgehensweisen für den Aufruf von systemintern kompilierten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="05991-102">Best Practices for Calling Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="05991-103">Für systemintern kompilierte gespeicherte Prozeduren gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="05991-103">Natively compiled stored procedures are:</span></span>  
  
-   <span data-ttu-id="05991-104">Sie werden üblicherweise in leistungskritischen Anwendungskomponenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="05991-104">Used typically in performance-critical parts of an application.</span></span>  
  
-   <span data-ttu-id="05991-105">Sie werden häufig ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="05991-105">Frequently executed.</span></span>  
  
-   <span data-ttu-id="05991-106">Sie zeichnen sich erwartungsgemäß durch eine sehr schnelle Ausführung aus.</span><span class="sxs-lookup"><span data-stu-id="05991-106">Expected to be very fast.</span></span>  
  
 <span data-ttu-id="05991-107">Der Leistungsvorteil bei Verwendung einer systemintern kompilierten gespeicherten Prozedur nimmt mit der Anzahl der Zeilen und dem Umfang der Logik zu, die von der Prozedur verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="05991-107">The performance benefit of using a natively compiled stored procedure increases with the number of rows and the amount of logic that is processed by the procedure.</span></span> <span data-ttu-id="05991-108">Beispielsweise lässt sich die Leistung einer systemintern kompilierten gespeicherten Prozedur durch eine oder mehrere der folgenden Maßnahmen verbessern:</span><span class="sxs-lookup"><span data-stu-id="05991-108">For example, a natively compiled stored procedure will exhibit better performance if it uses one or more of the following:</span></span>  
  
-   <span data-ttu-id="05991-109">Aggregation:</span><span class="sxs-lookup"><span data-stu-id="05991-109">Aggregation.</span></span>  
  
-   <span data-ttu-id="05991-110">Joins geschachtelter Schleifen.</span><span class="sxs-lookup"><span data-stu-id="05991-110">Nested-loops joins.</span></span>  
  
-   <span data-ttu-id="05991-111">Auswahl-, Einfüge-, Update- und Löschvorgänge mit mehreren Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="05991-111">Multi-statement select, insert, update, and delete operations.</span></span>  
  
-   <span data-ttu-id="05991-112">Komplexe Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="05991-112">Complex expressions.</span></span>  
  
-   <span data-ttu-id="05991-113">Prozedurale Logik, wie Bedingungsanweisungen und Schleifen.</span><span class="sxs-lookup"><span data-stu-id="05991-113">Procedural logic, such as conditional statements and loops.</span></span>  
  
 <span data-ttu-id="05991-114">Wenn Sie nur eine einzelne Zeile verarbeiten müssen, bietet eine systemintern kompilierte gespeicherte Prozedur u. U. keinen Leistungsvorteil.</span><span class="sxs-lookup"><span data-stu-id="05991-114">If you need to process only a single row, using a natively compiled stored procedure may not provide a performance benefit.</span></span>  
  
 <span data-ttu-id="05991-115">So vermeiden Sie, dass der Server Parameternamen zuordnen und Typen konvertieren muss:</span><span class="sxs-lookup"><span data-stu-id="05991-115">To avoid the server having to map parameter names and convert types:</span></span>  
  
-   <span data-ttu-id="05991-116">Gleichen Sie die Typen der an die Prozedur übergebenen Parameter mit den Typen in der Prozedurdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="05991-116">Match the types of the parameters passed to the procedure with the types in the procedure definition.</span></span>  
  
-   <span data-ttu-id="05991-117">Verwenden Sie Ordnungszahlparameter (namenlos), wenn Sie systemintern kompilierte gespeicherte Prozeduren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="05991-117">Use ordinal (nameless) parameters when calling natively compiled stored procedures.</span></span> <span data-ttu-id="05991-118">Verwenden Sie für die effizienteste Ausführung keine benannten Parameter.</span><span class="sxs-lookup"><span data-stu-id="05991-118">For the most efficient execution, do not use named parameters.</span></span>  
  
 <span data-ttu-id="05991-119">Die Verwendung von (ineffizienten) benannten Parametern mit systemintern kompilierten gespeicherten Prozeduren kann über das XEvent `hekaton_slow_parameter_passing`, mit `reason=named_parameters`, erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="05991-119">Use of (inefficient) named parameters with natively compiled stored procedures can be detected through the XEvent `hekaton_slow_parameter_passing`, with `reason=named_parameters`.</span></span>  
  
 <span data-ttu-id="05991-120">Auf ähnliche Weise können Sie die Verwendung von nicht übereinstimmenden Typen über dasselbe XEvent `hekaton_slow_parameter_passing`, mit `reason=parameter_conversion`, erkennen.</span><span class="sxs-lookup"><span data-stu-id="05991-120">Similarly, you can detect use of mismatched types through the same XEvent `hekaton_slow_parameter_passing`, with `reason=parameter_conversion`.</span></span>  
  
 <span data-ttu-id="05991-121">Da Sie bei der Verwendung speicheroptimierter Tabellen (in vielen Fällen) Wiederholungslogik implementieren und bestimmte Funktionseinschränkungen umgehen müssen, können Sie eine von einem Wrapper interpretierte gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur erstellen.</span><span class="sxs-lookup"><span data-stu-id="05991-121">Because you will need to implement retry logic when using memory-optimized tables (in many scenarios), and because you will need to work around certain feature limitations, you may want to create a wrapper interpreted [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure.</span></span> <span data-ttu-id="05991-122">Ein Beispiel finden Sie unter [Richtlinien für Wiederholungs Logik für Transaktionen in Speicher optimierten Tabellen](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="05991-122">For an example, see [Guidelines for Retry Logic for Transactions on Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05991-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05991-123">See Also</span></span>  
 [<span data-ttu-id="05991-124">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="05991-124">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
