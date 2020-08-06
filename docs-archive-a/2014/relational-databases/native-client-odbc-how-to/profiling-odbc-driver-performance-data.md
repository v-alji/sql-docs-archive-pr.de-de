---
title: Leistungsdaten des Profil Treibers (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698162"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="276cc-102">Profilerstellung für Treiberleistungsdaten (ODBC)</span><span class="sxs-lookup"><span data-stu-id="276cc-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="276cc-103">In diesem Beispiel werden die für den ODBC-Treiber von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spezifischen Optionen zum Aufzeichnen von Leistungsstatistiken dargestellt.</span><span class="sxs-lookup"><span data-stu-id="276cc-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="276cc-104">Im Beispiel wird eine Datei erstellt: odbcperf.log. Dieses Beispiel zeigt die Erstellung einer Leistungsdaten-Protokolldatei und das Anzeigen von Leistungsdaten direkt aus der SQLPERF-Datenstruktur (die SQLPERF-Struktur ist in Odbcss.h definiert).</span><span class="sxs-lookup"><span data-stu-id="276cc-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="276cc-105">Dieses Beispiel wurde für ODBC, Version 3.0 oder höher, entwickelt.</span><span class="sxs-lookup"><span data-stu-id="276cc-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="276cc-106">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="276cc-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="276cc-107">Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="276cc-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="276cc-108">Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="276cc-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="276cc-109">Wenn Sie Anmelde Informationen beibehalten müssen, sollten Sie diese mit der [Win32-kryptografieapi](https://go.microsoft.com/fwlink/?LinkId=64532)verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="276cc-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="276cc-110">So protokollieren Sie Treiberleistungsdaten mit dem ODBC-Administrator</span><span class="sxs-lookup"><span data-stu-id="276cc-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="276cc-111">Öffnen Sie in der **Systemsteuerung**die Option **Verwaltung** , und doppelklicken Sie dann auf **Datenquellen (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="276cc-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="276cc-112">Alternativ können Sie odbcad32.exe aufrufen.</span><span class="sxs-lookup"><span data-stu-id="276cc-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="276cc-113">Klicken Sie auf die Registerkarte **Benutzer-DSN**, **System-DSN**oder **Datei-DSN** .</span><span class="sxs-lookup"><span data-stu-id="276cc-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="276cc-114">Klicken Sie auf die Datenquelle für die die Leistung protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="276cc-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="276cc-115">Klicken Sie auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="276cc-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="276cc-116">Navigieren Sie im Microsoft SQL Server Assistenten zum Konfigurieren von DSN zur Seite mit den **ODBC-Treiber Statistiken für die Protokolldatei**.</span><span class="sxs-lookup"><span data-stu-id="276cc-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="276cc-117">Wählen Sie **ODBC-Treiber Statistiken in der Protokolldatei protokollieren**aus.</span><span class="sxs-lookup"><span data-stu-id="276cc-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="276cc-118">Platzieren Sie im Feld den Namen der Datei, in der die Statistik protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="276cc-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="276cc-119">Klicken Sie optional auf **Durchsuchen** , um das Dateisystem nach dem Statistik Protokoll zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="276cc-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="276cc-120">So protokollieren Sie programmgesteuert Treiberleistungsdaten</span><span class="sxs-lookup"><span data-stu-id="276cc-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="276cc-121">Aufrufen von [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_DATA_LOG und dem vollständigen Pfad und Dateinamen der Leistungsdaten-Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="276cc-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="276cc-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="276cc-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="276cc-123">Aufrufen von [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_DATA und SQL_PERF_START, um mit dem Protokollieren von Leistungsdaten zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="276cc-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="276cc-124">Optional können Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_LOG_NOW und NULL aufrufen, um einen durch Tabstopps getrennten Datensatz mit Leistungsdaten in die Leistungsdaten-Protokolldatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="276cc-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="276cc-125">Dies kann mehrmals durchgeführt werden, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="276cc-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="276cc-126">Aufrufen von [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_DATA und SQL_PERF_STOP, um das Protokollieren von Leistungsdaten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="276cc-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="276cc-127">So ziehen Sie Treiberleistungsdaten in eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="276cc-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="276cc-128">Aufrufen von [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_DATA und SQL_PERF_START, um mit der Profilerstellung der Leistungsdaten zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="276cc-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="276cc-129">Aufrufen von [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) mit SQL_COPT_SS_PERF_DATA und der Adresse eines Zeigers auf eine SQLPERF-Struktur.</span><span class="sxs-lookup"><span data-stu-id="276cc-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="276cc-130">Mit den ersten Aufrufen wird der Zeiger auf die Adresse einer gültigen SQLPERF-Struktur festgelegt, die aktuelle Leistungsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="276cc-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="276cc-131">Der Treiber aktualisiert die Daten in der Leistungsstruktur nicht ständig.</span><span class="sxs-lookup"><span data-stu-id="276cc-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="276cc-132">Die Anwendung muss den Aufruf von [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) jederzeit wiederholen, wenn die Struktur mit aktuellen Leistungsdaten aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="276cc-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="276cc-133">Aufrufen von [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_DATA und SQL_PERF_STOP, um das Protokollieren von Leistungsdaten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="276cc-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="276cc-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="276cc-134">Example</span></span>  
 <span data-ttu-id="276cc-135">Sie benötigen eine ODBC-Datenquelle mit dem Namen AdventureWorks, deren Standarddatenbank die AdventureWorks-Beispieldatenbank ist.</span><span class="sxs-lookup"><span data-stu-id="276cc-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="276cc-136">(Sie können die AdventureWorks-Beispieldatenbank von der Startseite [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) herunterladen.) Diese Datenquelle muss auf dem ODBC-Treiber basieren, der vom Betriebssystem bereitgestellt wird (der Treiber Name ist "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="276cc-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="276cc-137">Wenn Sie dieses Beispiel als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.</span><span class="sxs-lookup"><span data-stu-id="276cc-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="276cc-138">In diesem Beispiel wird eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Standardinstanz des Computers hergestellt.</span><span class="sxs-lookup"><span data-stu-id="276cc-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="276cc-139">Ändern Sie zum Herstellen einer Verbindung mit einer benannten Instanz die Definition der ODBC-Datenquelle, um die Instanz im folgenden Format anzugeben: Server\benannteInstanz.</span><span class="sxs-lookup"><span data-stu-id="276cc-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="276cc-140">Standardmäßig wird [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] in einer benannten Instanz installiert.</span><span class="sxs-lookup"><span data-stu-id="276cc-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="276cc-141">Kompilieren Sie mit odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="276cc-141">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="276cc-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="276cc-142">See Also</span></span>  
 <span data-ttu-id="276cc-143">[Gewusst-wie-Themen zur Profilerstellung für ODBC-Treiber &#40;ODBC-&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="276cc-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="276cc-144">Leistungsprofilerstellung des ODBC-Treibers</span><span class="sxs-lookup"><span data-stu-id="276cc-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
