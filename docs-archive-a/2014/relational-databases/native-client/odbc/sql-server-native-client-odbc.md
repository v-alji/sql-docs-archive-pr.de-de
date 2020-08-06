---
title: SQL Server Native Client (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718076"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="7465e-102">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7465e-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="7465e-103">ODBC ist eine Standarddefinition einer API (Application Programming Interface, Schnittstelle für Anwendungsprogrammierung), die für den Zugriff auf Daten in relationalen oder ISAM-Datenbanken (Indexed Sequential Access Method, indizierte sequenzielle Zugriffsmethode) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7465e-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7465e-104">unterstützt ODBC (über den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber) als eine der systemeigenen APIs für das Schreiben von C- und C++-Anwendungen, die mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="7465e-104">supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="7465e-105">-Programme, die mithilfe des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treibers geschrieben wurden, kommunizieren mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] über Funktionsaufrufe in C.</span><span class="sxs-lookup"><span data-stu-id="7465e-105">programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="7465e-106">Die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -spezifischen Versionen der ODBC-Funktionen werden im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber implementiert.</span><span class="sxs-lookup"><span data-stu-id="7465e-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="7465e-107">Der Treiber übergibt SQL-Anweisungen an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] und gibt die Ergebnisse der Anweisungen an die Anwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="7465e-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="7465e-108">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber entspricht der Spezifikation für Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="7465e-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="7465e-109">Der Treiber unterstützt Anwendungen, die mit früheren Versionen von ODBC gemäß ODBC 3.51-Spezifikation geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="7465e-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7465e-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7465e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="7465e-111">Datenquellennamen und 64-Bit-Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="7465e-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="7465e-112">Erstellen einer SQL Server Native Client-ODBC-Treiberanwendung</span><span class="sxs-lookup"><span data-stu-id="7465e-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="7465e-113">Kommunikation mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="7465e-114">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="7465e-115">Verarbeitungsergebnisse &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="7465e-116">Verwenden von Cursorn &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="7465e-117">Ausführen von Transaktionen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="7465e-118">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="7465e-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="7465e-119">Ausführen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7465e-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="7465e-120">Verwenden von Katalogfunktionen</span><span class="sxs-lookup"><span data-stu-id="7465e-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="7465e-121">Ausführen von Massen Kopier Vorgängen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="7465e-122">Verwalten von Text und Imagespalten</span><span class="sxs-lookup"><span data-stu-id="7465e-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="7465e-123">Leistungsprofilerstellung des ODBC-Treibers</span><span class="sxs-lookup"><span data-stu-id="7465e-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="7465e-124">Tabellenwert Parameter &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="7465e-125">Datums-und Uhrzeit Verbesserungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="7465e-126">Große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="7465e-127">FILESTREAM-Unterstützung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="7465e-128">Dienstprinzipalnamen (SPN) in Clientverbindungen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7465e-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="7465e-129">Unterstützung für sparsespalten &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7465e-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="7465e-130">SQL Server Native Client &#40;ODBC-&#41; Referenz</span><span class="sxs-lookup"><span data-stu-id="7465e-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="7465e-131">ODBC How-to Topics</span><span class="sxs-lookup"><span data-stu-id="7465e-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="7465e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7465e-132">See Also</span></span>  
 <span data-ttu-id="7465e-133">[SQL Server Native Client Programmierung](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="7465e-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="7465e-134">Installieren von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="7465e-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
