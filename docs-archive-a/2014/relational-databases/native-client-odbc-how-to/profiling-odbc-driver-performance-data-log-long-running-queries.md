---
title: Protokollieren von Abfragen mit langer Ausführungszeit (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- queries [ODBC]
ms.assetid: b9c1ddce-1dd9-409d-a414-8b544d616273
author: rothja
ms.author: jroth
ms.openlocfilehash: f73dbf6fe8fc4b3dfbbbc0012d14a58614b218dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724598"
---
# <a name="log-long-running-queries-odbc"></a><span data-ttu-id="9fff4-102">Protokollieren von Abfragen mit langer Ausführungszeit (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9fff4-102">Log Long-Running Queries (ODBC)</span></span>
  <span data-ttu-id="9fff4-103">Dieses Beispiel zeigt die ODBC-treiberspezifischen Optionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zum Protokollieren von Abfragen mit langer Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="9fff4-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to log long-running queries.</span></span> <span data-ttu-id="9fff4-104">Bei der Ausführung des Beispiels wird die Datei Odbcqry.log erstellt, die eine Liste von Abfragen enthält, deren Ausführung ein von der Anwendung festgelegtes Intervall überschreitet.</span><span class="sxs-lookup"><span data-stu-id="9fff4-104">When run, this sample creates Odbcqry.log, which contains a list of queries whose execution exceeds an interval set by the application.</span></span> <span data-ttu-id="9fff4-105">Dieses Beispiel wird nicht auf IA64-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9fff4-105">This sample is not supported on IA64.</span></span> <span data-ttu-id="9fff4-106">Dieses Beispiel wurde für ODBC, Version 3.0 oder höher, entwickelt.</span><span class="sxs-lookup"><span data-stu-id="9fff4-106">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9fff4-107">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9fff4-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="9fff4-108">Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="9fff4-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="9fff4-109">Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9fff4-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="9fff4-110">Wenn Sie Anmelde Informationen beibehalten müssen, sollten Sie diese mit der [Win32-kryptografieapi](https://go.microsoft.com/fwlink/?LinkId=64532)verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="9fff4-110">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-long-running-queries-using-odbc-administrator"></a><span data-ttu-id="9fff4-111">So protokollieren Sie Abfragen mit langer Ausführungszeit mithilfe des ODBC-Administrators</span><span class="sxs-lookup"><span data-stu-id="9fff4-111">To log long-running queries using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="9fff4-112">Öffnen Sie in der **Systemsteuerung**die Option **Verwaltung** , und doppelklicken Sie dann auf **Datenquellen (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-112">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="9fff4-113">(Stattdessen können Sie auch odbcad32.exe über die Eingabeaufforderung ausführen.)</span><span class="sxs-lookup"><span data-stu-id="9fff4-113">(Alternatively, you can run odbcad32.exe from the command prompt.)</span></span>  
  
2.  <span data-ttu-id="9fff4-114">Klicken Sie auf die Registerkarte **Benutzer-DSN**, **System-DSN**oder **Datei-DSN** .</span><span class="sxs-lookup"><span data-stu-id="9fff4-114">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="9fff4-115">Klicken Sie auf die Datenquelle, für die die Protokollierung der Abfragen mit langer Ausführungszeit ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fff4-115">Click the data source for which to log long-running queries.</span></span>  
  
4.  <span data-ttu-id="9fff4-116">Klicken Sie auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-116">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="9fff4-117">Navigieren Sie im Microsoft SQL Server-Assistenten zum Konfigurieren von DSN zur Seite mit der Option **Abfragen mit langer Ausführungszeit in der Protokolldatei speichern**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-117">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Save long-running queries to the log file**.</span></span>  
  
6.  <span data-ttu-id="9fff4-118">Wählen Sie **Abfragen mit langer Ausführungszeit in der Protokolldatei speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="9fff4-118">Select **Save long-running queries to the log file**.</span></span> <span data-ttu-id="9fff4-119">Platzieren Sie im Feld den Namen der Datei, in der die Abfragen mit langer Ausführungszeit protokolliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9fff4-119">In the box, place the name of the file where the long-running queries should be logged.</span></span> <span data-ttu-id="9fff4-120">Klicken Sie optional auf **Durchsuchen** , um im Dateisystem nach dem Abfrageprotokoll zu suchen.</span><span class="sxs-lookup"><span data-stu-id="9fff4-120">Optionally, click **Browse** to browse the file system for the query log.</span></span>  
  
7.  <span data-ttu-id="9fff4-121">Legen Sie im Feld **Lange Abfragezeit (Millisekunden)** ein Abfragetimeoutintervall in Millisekunden fest.</span><span class="sxs-lookup"><span data-stu-id="9fff4-121">Set a query time-out interval, in milliseconds, in the **Long query time (milliseconds)** box.</span></span>  
  
### <a name="to-log-long-running-queries-data-programmatically"></a><span data-ttu-id="9fff4-122">So protokollieren Sie Abfragen mit langer Ausführungszeit programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="9fff4-122">To log long-running queries data programmatically</span></span>  
  
1.  <span data-ttu-id="9fff4-123">Rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_QUERY_LOG und dem vollständigen Pfad und dem Dateinamen der Protokolldatei für Abfragen mit langer Ausführungszeit auf.</span><span class="sxs-lookup"><span data-stu-id="9fff4-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_LOG and the full path and file name of the long-running query log file.</span></span> <span data-ttu-id="9fff4-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9fff4-124">For example:</span></span>  
  
    ```  
    C:\\Odbcqry.log  
    ```  
  
2.  <span data-ttu-id="9fff4-125">Rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_QUERY_INTERVAL und Festlegung auf das Timeoutintervall in Millisekunden auf.</span><span class="sxs-lookup"><span data-stu-id="9fff4-125">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_INTERVAL and set to the time-out interval, in milliseconds.</span></span>  
  
3.  <span data-ttu-id="9fff4-126">Rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_QUERY und SQL_PERF_START auf, um das Protokollieren von Abfragen mit langer Ausführungszeit zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="9fff4-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_START to start logging long-running queries.</span></span>  
  
4.  <span data-ttu-id="9fff4-127">Rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_COPT_SS_PERF_QUERY und SQL_PERF_STOP auf, um das Protokollieren von Abfragen mit langer Ausführungszeit zu beenden.</span><span class="sxs-lookup"><span data-stu-id="9fff4-127">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_STOP to stop logging long-running queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fff4-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9fff4-128">Example</span></span>  
 <span data-ttu-id="9fff4-129">Sie benötigen eine ODBC-Datenquelle mit dem Namen AdventureWorks, deren Standarddatenbank die AdventureWorks-Beispieldatenbank ist.</span><span class="sxs-lookup"><span data-stu-id="9fff4-129">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="9fff4-130">(Sie können die AdventureWorks-Beispieldatenbank von der Startseite [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) herunterladen.) Diese Datenquelle muss auf dem ODBC-Treiber basieren, der vom Betriebssystem bereitgestellt wird (der Treiber Name ist "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="9fff4-130">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="9fff4-131">Wenn Sie dieses Beispiel als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.</span><span class="sxs-lookup"><span data-stu-id="9fff4-131">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="9fff4-132">In diesem Beispiel wird eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Standardinstanz des Computers hergestellt.</span><span class="sxs-lookup"><span data-stu-id="9fff4-132">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="9fff4-133">Ändern Sie zum Herstellen einer Verbindung mit einer benannten Instanz die Definition der ODBC-Datenquelle, um die Instanz im folgenden Format anzugeben: Server\benannteInstanz.</span><span class="sxs-lookup"><span data-stu-id="9fff4-133">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="9fff4-134">Standardmäßig wird [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] in einer benannten Instanz installiert.</span><span class="sxs-lookup"><span data-stu-id="9fff4-134">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="9fff4-135">Kompilieren Sie mit odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="9fff4-135">Compile with odbc32.lib.</span></span>  
  
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
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // sample uses Integrated Security, create SQL Server DSN using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log long-running queries, including the file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_LOG, &"odbcqry.log", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the long-running query interval (in milliseconds).  Note that for version 2.50 and 2.65  
   // drivers, this value is specified in seconds, not milliseconds.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_INTERVAL, (SQLPOINTER)3000, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the long-running query log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle then execute commands.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
           return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fff4-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fff4-136">See Also</span></span>  
 [<span data-ttu-id="9fff4-137">Gewusst-wie-Themen zur Profilerstellung für ODBC-Treiber &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="9fff4-137">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
  
