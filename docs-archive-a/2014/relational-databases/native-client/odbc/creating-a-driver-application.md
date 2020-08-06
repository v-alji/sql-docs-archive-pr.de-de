---
title: Erstellen einer SQL Server Native Client ODBC-Treiber Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722710"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="441ee-102">Erstellen einer SQL Server Native Client-ODBC-Treiberanwendung</span><span class="sxs-lookup"><span data-stu-id="441ee-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="441ee-103">Die ODBC-Architektur verfügt über vier Komponenten, die die folgenden Funktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="441ee-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="441ee-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="441ee-104">Component</span></span>|<span data-ttu-id="441ee-105">Funktion</span><span class="sxs-lookup"><span data-stu-id="441ee-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="441ee-106">Application</span><span class="sxs-lookup"><span data-stu-id="441ee-106">Application</span></span>|<span data-ttu-id="441ee-107">Ruft ODBC-Funktionen auf, um mit einer ODBC-Datenquelle zu kommunizieren, sendet SQL-Anweisungen und verarbeitet Resultsets.</span><span class="sxs-lookup"><span data-stu-id="441ee-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="441ee-108">Treiber-Manager</span><span class="sxs-lookup"><span data-stu-id="441ee-108">Driver Manager</span></span>|<span data-ttu-id="441ee-109">Verwaltet die Kommunikation zwischen einer Anwendung und allen von der Anwendung verwendeten ODBC-Treibern.</span><span class="sxs-lookup"><span data-stu-id="441ee-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="441ee-110">Treiber</span><span class="sxs-lookup"><span data-stu-id="441ee-110">Driver</span></span>|<span data-ttu-id="441ee-111">Verarbeitet alle ODBC-Funktionsaufrufe von der Anwendung, stellt eine Verbindung zu einer Datenquelle her, übergibt SQL-Anweisungen von der Anwendung an die Datenquelle und gibt Ergebnisse an die Anwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="441ee-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="441ee-112">Bei Bedarf übersetzt der Treiber ODBC SQL-Code von der Anwendung in den von der Datenquelle verwendeten systemeigenen SQL-Code.</span><span class="sxs-lookup"><span data-stu-id="441ee-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="441ee-113">Datenquelle</span><span class="sxs-lookup"><span data-stu-id="441ee-113">Data source</span></span>|<span data-ttu-id="441ee-114">Enthält alle Informationen, die ein Treiber für den Zugriff auf eine bestimmte Instanz der Daten in einem DBMS benötigt.</span><span class="sxs-lookup"><span data-stu-id="441ee-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="441ee-115">Eine Anwendung, die den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber für die Kommunikation mit einer Instanz von verwendet, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="441ee-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="441ee-116">Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="441ee-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="441ee-117">Senden von SQL-Anweisungen an die Datenquelle</span><span class="sxs-lookup"><span data-stu-id="441ee-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="441ee-118">Verarbeiten der Ergebnisse von Anweisungen von der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="441ee-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="441ee-119">Verarbeiten von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="441ee-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="441ee-120">Beenden der Verbindung mit der Datenquelle</span><span class="sxs-lookup"><span data-stu-id="441ee-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="441ee-121">Eine komplexere Anwendung, die für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber geschrieben wurde, kann auch die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="441ee-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="441ee-122">Verwenden von Cursorn, um die Position in einem Resultset zu bestimmen</span><span class="sxs-lookup"><span data-stu-id="441ee-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="441ee-123">Anforderung von Commit- oder Rollbackvorgängen zur Steuerung von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="441ee-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="441ee-124">Ausführen von verteilten Transaktionen, an denen zwei oder mehr Server beteiligt sind</span><span class="sxs-lookup"><span data-stu-id="441ee-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="441ee-125">Ausführen von gespeicherten Prozeduren auf dem Remoteserver</span><span class="sxs-lookup"><span data-stu-id="441ee-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="441ee-126">Aufrufen von Katalogfunktionen für die Abfrage der Attribute eines Resultsets</span><span class="sxs-lookup"><span data-stu-id="441ee-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="441ee-127">Ausführen von Massen Kopier Vorgängen</span><span class="sxs-lookup"><span data-stu-id="441ee-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="441ee-128">Verwalten von großen Daten Vorgängen (**varchar (max)**, **nvarchar (max)** und **varbinary (max)** -Spalten)</span><span class="sxs-lookup"><span data-stu-id="441ee-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="441ee-129">Verwenden einer Logik zum Wiederherstellen einer Verbindung, um bei der Konfiguration der Datenbankspiegelung ein Failover zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="441ee-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="441ee-130">Protokollieren von Leistungsdaten und Abfragen mit langer Ausführungszeit</span><span class="sxs-lookup"><span data-stu-id="441ee-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="441ee-131">Um ODBC-Funktionen aufrufen können, muss eine C- oder C++-Anwendung die Headerdateien sql.h, sqlext.h und sqltypes.h enthalten.</span><span class="sxs-lookup"><span data-stu-id="441ee-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="441ee-132">Um API-Funktionen des ODBC-Installationsprogramms aufrufen zu können, muss eine Anwendung die Headerdatei odbcinst.h enthalten.</span><span class="sxs-lookup"><span data-stu-id="441ee-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="441ee-133">Eine ODBC-Unicode-Anwendung muss die Headerdatei sqlucode.h enthalten.</span><span class="sxs-lookup"><span data-stu-id="441ee-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="441ee-134">ODBC-Anwendungen müssen mit der Datei odbc32.lib verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="441ee-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="441ee-135">ODBC-Anwendungen, die API-Funktionen des ODBC-Installationsprogramms aufrufen, müssen mit der Datei odbccp32.lib verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="441ee-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="441ee-136">Diese Dateien sind im Windows Platform SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="441ee-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="441ee-137">Viele ODBC-Treiber, einschließlich des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treibers, bieten Treiber spezifische ODBC-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="441ee-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="441ee-138">Um die Vorteile von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-treiberspezifischen Erweiterungen zu nutzen, sollte eine Anwendung die Header Datei sqlncli. h enthalten.</span><span class="sxs-lookup"><span data-stu-id="441ee-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="441ee-139">Diese Headerdatei enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="441ee-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-140">Native Client-ODBC-Treiber spezifische Verbindungs Attribute.</span><span class="sxs-lookup"><span data-stu-id="441ee-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-141">Native Client-ODBC-Treiber spezifische Anweisungs Attribute.</span><span class="sxs-lookup"><span data-stu-id="441ee-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-142">Native Client-ODBC-Treiber spezifische Spalten Attribute.</span><span class="sxs-lookup"><span data-stu-id="441ee-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-143">-spezifische Datentypen</span><span class="sxs-lookup"><span data-stu-id="441ee-143">-specific data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-144">-spezifische, benutzerdefinierte Datentypen</span><span class="sxs-lookup"><span data-stu-id="441ee-144">-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-145">Native Client-ODBC-Treiber spezifische [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) -Typen.</span><span class="sxs-lookup"><span data-stu-id="441ee-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="441ee-146">Diagnose Felder für Native Client-ODBC-Treiber.</span><span class="sxs-lookup"><span data-stu-id="441ee-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="441ee-147">Für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] spezifische, dynamische Diagnosefunktionscodes</span><span class="sxs-lookup"><span data-stu-id="441ee-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="441ee-148">C/C++-Definitionen für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-spezifische, systemeigene C-Datentypen (die zurückgegeben werden, wenn Spalten an den C-Datentyp SQL_C_BINARY gebunden werden).</span><span class="sxs-lookup"><span data-stu-id="441ee-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="441ee-149">Typdefinition für die SQLPERF-Datenstruktur</span><span class="sxs-lookup"><span data-stu-id="441ee-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="441ee-150">Massenkopiermakros und Prototypen zur Unterstützung von APIs für das Massenkopieren über eine ODBC-Verbindung</span><span class="sxs-lookup"><span data-stu-id="441ee-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="441ee-151">Aufrufen der API-Funktionen für verteilte Abfragemetadaten für Listen mit verknüpften Servern und den zugehörigen Katalogen</span><span class="sxs-lookup"><span data-stu-id="441ee-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="441ee-152">Jede C-oder C++-ODBC-Anwendung, die die Massen Kopierfunktion des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treibers verwendet, muss mit der Datei sqlncli11. lib verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="441ee-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="441ee-153">Anwendungen, die die API-Funktionen für verteilte Abfragemetadaten aufrufen, müssen ebenfalls mit der Datei sqlncli11.lib verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="441ee-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="441ee-154">Die Dateien sqlncli. h und sqlncli11. lib werden als Teil der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Entwicklertools verteilt.</span><span class="sxs-lookup"><span data-stu-id="441ee-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="441ee-155">Die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Verzeichnisse Include und Lib müssen sich wie im folgenden Beispiel in den Verzeichnissen INCLUDE und LIB des Compilers befinden:</span><span class="sxs-lookup"><span data-stu-id="441ee-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="441ee-156">Ob es erforderlich ist, dass bei der Anwendung mehrere ODBC-Aufrufe gleichzeitig ausstehen können, ist eine Entwurfsentscheidung, die früh im Prozess der Erstellung einer Anwendung getroffen werden muss.</span><span class="sxs-lookup"><span data-stu-id="441ee-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="441ee-157">Es gibt zwei Methoden zur Unterstützung mehrerer gleichzeitiger ODBC-Aufrufe, die in den verbleibenden Themen dieses Abschnitts beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="441ee-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="441ee-158">Weitere Informationen finden Sie in der [ODBC Programmer es Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="441ee-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="441ee-159">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="441ee-159">In This Section</span></span>  
  
-   [<span data-ttu-id="441ee-160">Asynchroner Modus und SQLCancel</span><span class="sxs-lookup"><span data-stu-id="441ee-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="441ee-161">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="441ee-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="441ee-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="441ee-162">See Also</span></span>  
 [<span data-ttu-id="441ee-163">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="441ee-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
