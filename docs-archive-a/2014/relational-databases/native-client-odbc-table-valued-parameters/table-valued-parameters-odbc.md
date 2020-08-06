---
title: Tabellenwert Parameter (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608596"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="c6217-102">Tabellenwertparameter (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c6217-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="c6217-103">Die ODBC-Unterstützung für Tabellenwertparameter ermöglicht einer Clientanwendung die effizientere Versendung von parametrisierten Daten an einen Server, indem mehrere Zeilen über einen Aufruf an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6217-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="c6217-104">Informationen zu Tabellenwert Parametern auf dem Server finden Sie unter [Verwenden von Tabellenwert Parametern &#40;Datenbank-Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c6217-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="c6217-105">In ODBC gibt es zwei Methoden zum Versenden von Tabellenwertparametern an den Server:</span><span class="sxs-lookup"><span data-stu-id="c6217-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="c6217-106">Alle Tabellenwert Parameter-Daten können sich im Arbeitsspeicher befinden, wenn SQLExecDirect oder SQLExecute aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c6217-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="c6217-107">Wenn es mehrere Zeilen im Tabellenwert gibt, werden diese Daten in Arrays gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c6217-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="c6217-108">Eine Anwendung kann Daten bei der Ausführung für einen Tabellenwert Parameter angeben, wenn SQLExecDirect oder SQLExecute aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c6217-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="c6217-109">In diesem Fall können Datenzeilen für den Tabellenwertparameter in Batches oder einzeln bereitgestellt werden, um die Speicheranforderungen zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="c6217-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="c6217-110">Die erste Option aktiviert gespeicherte Prozeduren, um mehr Geschäftslogik zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="c6217-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="c6217-111">Beispielsweise könnte eine einzeln gespeicherte Prozedur eine gesamte Bestellungseingabetransaktion kapseln, wenn die Bestellartikel als Tabellenwertparameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c6217-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="c6217-112">Diese Option ist sehr effizient, da nur ein einzelner Roundtrip zum Server erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6217-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="c6217-113">Alternativ könnten Sie verschiedene Prozeduren verwenden, um die Bestellungskopfzeile und die Bestellartikel separat zu behandeln. In diesem Fall wäre jedoch weiterer Code und ein komplexerer Vertrag zwischen Client und Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c6217-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="c6217-114">Die zweite Methode stellt einen effizienten Mechanismus für Massenvorgänge mit sehr großen Datenmengen bereit.</span><span class="sxs-lookup"><span data-stu-id="c6217-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="c6217-115">Dies ermöglicht es einer Anwendung, Datenzeilen zum Server zu streamen, ohne sie zuvor alle im Arbeitsspeicher puffern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c6217-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="c6217-116">Beim Erstellen der Tabellenvariablen können Sie Einschränkungen und Primärschlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6217-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="c6217-117">Einschränkungen sind eine gute Möglichkeit, um sicherzustellen, dass die Daten in einer Tabelle bestimmte Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c6217-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c6217-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c6217-118">In This Section</span></span>  
 [<span data-ttu-id="c6217-119">Verwendungen von ODBC-Tabellenwertparametern</span><span class="sxs-lookup"><span data-stu-id="c6217-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="c6217-120">Beschreibt die wichtigsten Benutzerszenarien für Tabellenwertparameter und ODBC.</span><span class="sxs-lookup"><span data-stu-id="c6217-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="c6217-121">ODBC-SQL-Typ für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c6217-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="c6217-122">Beschreibt den SQL_SS_TABLE-Typ.</span><span class="sxs-lookup"><span data-stu-id="c6217-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="c6217-123">Dies ist ein neuer ODBC SQL-Typ, der Tabellenwertparameter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c6217-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="c6217-124">Deskriptorfelder für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c6217-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="c6217-125">Beschreibt Deskriptorfelder, die Tabellenwertparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6217-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="c6217-126">Deskriptorfelder für aus Tabellenwertparameter bestehenden Spalten</span><span class="sxs-lookup"><span data-stu-id="c6217-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="c6217-127">Beschreibt Deskriptorfelder, die eine Bedeutung für Tabellenwertparameter haben.</span><span class="sxs-lookup"><span data-stu-id="c6217-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="c6217-128">Diagnosedatensatz-Felder für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c6217-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="c6217-129">Beschreibt zwei Diagnosefelder, die Diagnosedatensätzen hinzugefügt wurden, um Tabellenwertparameter zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6217-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="c6217-130">Anweisungsattribute, die sich auf Tabellenwertparameter auswirken</span><span class="sxs-lookup"><span data-stu-id="c6217-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="c6217-131">Beschreibt ein neues Deskriptorheaderfeld, das die Adressierung von Tabellenwertparameter-Spalten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c6217-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="c6217-132">Bindung und Datenübertragung von Tabellenwertparametern und Spaltenwerten</span><span class="sxs-lookup"><span data-stu-id="c6217-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="c6217-133">Beschreibt die Parameterbindung und die Übergabe eines Tabellenwertparameters an den Server.</span><span class="sxs-lookup"><span data-stu-id="c6217-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="c6217-134">Tabellenwertparameter-Metadaten für vorbereitete Anweisungen</span><span class="sxs-lookup"><span data-stu-id="c6217-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="c6217-135">Beschreibt, wie eine Anwendung Metadaten für einen vorbereiteten Prozeduraufruf abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="c6217-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="c6217-136">Zusätzliche Tabellenwertparameter-Metadaten</span><span class="sxs-lookup"><span data-stu-id="c6217-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="c6217-137">Beschreibt, wie sqlprocedurecolrens, SQLTables und SQLColumns zum Abrufen von Metadaten für einen Tabellenwert Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6217-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="c6217-138">Tabellenwertparameter-Datenkonvertierung und andere Fehler und Warnungen</span><span class="sxs-lookup"><span data-stu-id="c6217-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="c6217-139">Beschreibt, wie Fehler in Tabellenwertparameter-Spaltenwerten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c6217-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="c6217-140">Versionsübergreifende Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="c6217-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="c6217-141">Beschreibt Konflikte, die auftreten können, wenn Tabellenwertparameter von einem Client oder Server mit einer niedrigeren Version als [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6217-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="c6217-142">Zusammenfassung der ODBC-Tabellenwertparameter-API</span><span class="sxs-lookup"><span data-stu-id="c6217-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="c6217-143">Listet die ODBC-Funktionen auf, die Tabellenwertparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c6217-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="c6217-144">Programmierbeispiele für ODBC-Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="c6217-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="c6217-145">Beschreibt die Durchführung der häufigsten Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="c6217-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6217-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6217-146">See Also</span></span>  
 <span data-ttu-id="c6217-147">[SQL Server Native Client &#40;ODBC-&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="c6217-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="c6217-148">Tabellenwert Parameter &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="c6217-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
