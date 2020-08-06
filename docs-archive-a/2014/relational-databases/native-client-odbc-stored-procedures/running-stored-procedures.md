---
title: Ausführen gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e5de6a9a13c95b417657a1d108403fa27abe34b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725626"
---
# <a name="running-stored-procedures"></a><span data-ttu-id="f85e6-102">Ausführen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f85e6-102">Running Stored Procedures</span></span>
  <span data-ttu-id="f85e6-103">Bei einer gespeicherten Prozedur handelt es sich um ein ausführbares Objekt, das in einer Datenbank gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f85e6-103">A stored procedure is an executable object stored in a database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f85e6-104">unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f85e6-104">supports:</span></span>  
  
-   <span data-ttu-id="f85e6-105">Gespeicherte Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="f85e6-105">Stored procedures:</span></span>  
  
     <span data-ttu-id="f85e6-106">Eine oder mehrere SQL-Anweisungen, die in eine einzelne ausführbare Prozedur vorkompiliert wurden</span><span class="sxs-lookup"><span data-stu-id="f85e6-106">One or more SQL statements precompiled into a single executable procedure.</span></span>  
  
-   <span data-ttu-id="f85e6-107">Erweiterte gespeicherte Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="f85e6-107">Extended stored procedures:</span></span>  
  
     <span data-ttu-id="f85e6-108">In die SQL Server Open Data Services-API für erweiterte gespeicherte Prozeduren geschriebene Dynamic Link Libraries (DLL) in C oder C++.</span><span class="sxs-lookup"><span data-stu-id="f85e6-108">C or C++ dynamic-link libraries (DLL) written to the SQL Server Open Data Services API for extended stored procedures.</span></span> <span data-ttu-id="f85e6-109">Die Open Data Services-API erweitert die Fähigkeiten gespeicherter Prozeduren, C- oder C++-Code zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="f85e6-109">The Open Data Services API extends the capabilities of stored procedures to include C or C++ code.</span></span>  
  
 <span data-ttu-id="f85e6-110">Wenn beim Ausführen von Anweisungen eine gespeicherte Prozedur in der Datenquelle aufgerufen wird (anstatt eine Anweisung direkt in der Clientanwendung auszuführen oder vorzubereiten), bietet das folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f85e6-110">When executing statements, calling a stored procedure on the data source (instead of directly executing or preparing a statement in the client application) can provide:</span></span>  
  
-   <span data-ttu-id="f85e6-111">Höhere Leistung</span><span class="sxs-lookup"><span data-stu-id="f85e6-111">Higher performance</span></span>  
  
     <span data-ttu-id="f85e6-112">SQL-Anweisungen werden analysiert und kompiliert, wenn Prozeduren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f85e6-112">SQL statements are parsed and compiled when procedures are created.</span></span> <span data-ttu-id="f85e6-113">Dieser Aufwand ist dann bei der Ausführung der Prozeduren nicht mehr nötig.</span><span class="sxs-lookup"><span data-stu-id="f85e6-113">This overhead is then saved when the procedures are executed.</span></span>  
  
-   <span data-ttu-id="f85e6-114">Geringere Netzwerkbelastung</span><span class="sxs-lookup"><span data-stu-id="f85e6-114">Reduced network overhead</span></span>  
  
     <span data-ttu-id="f85e6-115">Durch das Ausführen einer Prozedur statt Senden komplexer Abfragen über das Netzwerk wird der Netzwerkdatenverkehr reduziert.</span><span class="sxs-lookup"><span data-stu-id="f85e6-115">Executing a procedure instead of sending complex queries across the network can reduce network traffic.</span></span> <span data-ttu-id="f85e6-116">Wenn eine ODBC-Anwendung die ODBC-Syntax { CALL } zum Ausführen einer Prozedur verwendet, nimmt der ODBC-Treiber zusätzliche Optimierungen vor, die das Konvertieren von Parameterdaten überflüssig machen.</span><span class="sxs-lookup"><span data-stu-id="f85e6-116">If an ODBC application uses the ODBC { CALL } syntax to execute a stored procedure, the ODBC driver makes additional optimizations that eliminate the need to convert parameter data.</span></span>  
  
-   <span data-ttu-id="f85e6-117">Größere Konsistenz</span><span class="sxs-lookup"><span data-stu-id="f85e6-117">Greater consistency</span></span>  
  
     <span data-ttu-id="f85e6-118">Wenn die Regeln einer Organisation in einer zentralen Ressource implementiert sind, wie beispielsweise einer gespeicherten Prozedur, können Sie auf einmal codiert und getestet und Fehler behoben werden.</span><span class="sxs-lookup"><span data-stu-id="f85e6-118">If an organization's rules are implemented in a central resource, such as a stored procedure, they can be coded, tested, and debugged once.</span></span> <span data-ttu-id="f85e6-119">Programmierer können dann die getesteten gespeicherten Prozeduren verwenden, statt eigene Implementierungen entwickeln zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f85e6-119">Individual programmers can then use the tested stored procedures instead of developing their own implementations.</span></span>  
  
-   <span data-ttu-id="f85e6-120">Höhere Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="f85e6-120">Greater accuracy</span></span>  
  
     <span data-ttu-id="f85e6-121">Da gespeicherte Prozeduren in der Regel von erfahrenen Programmierern entwickelt werden, sind sie meist effizienter und weisen weniger Fehler auf als Code, der mehrmals von Programmierern unterschiedlicher Qualifikation entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="f85e6-121">Because stored procedures are usually developed by experienced programmers, they tend to be more efficient and have fewer errors than code developed multiple times by programmers of varying skill levels.</span></span>  
  
-   <span data-ttu-id="f85e6-122">Zusätzliche Funktionalität</span><span class="sxs-lookup"><span data-stu-id="f85e6-122">Added functionality</span></span>  
  
     <span data-ttu-id="f85e6-123">Erweiterte gespeicherte Prozeduren können C- und C++-Funktionen verwenden, die in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f85e6-123">Extended stored procedures can use C and C++ features not available in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
     <span data-ttu-id="f85e6-124">Ein Beispiel zum Abrufen einer gespeicherten Prozedur finden Sie unter Verarbeiten von [Rückgabe Codes und Ausgabeparametern &#40;ODBC-&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f85e6-124">For an example of how to call a stored procedure, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f85e6-125">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f85e6-125">In This Section</span></span>  
  
-   [<span data-ttu-id="f85e6-126">Aufrufen von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f85e6-126">Calling a Stored Procedure</span></span>](calling-a-stored-procedure.md)  
  
-   [<span data-ttu-id="f85e6-127">Batchverarbeitung von gespeicherten Prozeduraufrufen</span><span class="sxs-lookup"><span data-stu-id="f85e6-127">Batching Stored Procedure Calls</span></span>](batching-stored-procedure-calls.md)  
  
-   [<span data-ttu-id="f85e6-128">Verarbeiten von Ergebnissen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f85e6-128">Processing Stored Procedure Results</span></span>](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="f85e6-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f85e6-129">See Also</span></span>  
 <span data-ttu-id="f85e6-130">[SQL Server Native Client &#40;ODBC-&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="f85e6-130">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="f85e6-131">Gewusst-wie-Themen zur Ausführung gespeicherter Prozeduren &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="f85e6-131">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  
