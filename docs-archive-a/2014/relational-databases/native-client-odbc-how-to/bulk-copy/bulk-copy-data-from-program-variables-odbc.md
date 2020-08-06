---
title: Massen Daten kopieren aus Programmvariablen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], program variables
- bulk copy [ODBC]
ms.assetid: 0c3f2d7c-4ff2-4887-adfd-1f488a27c21c
author: rothja
ms.author: jroth
ms.openlocfilehash: e6e1c5294611b280aea8e67963613971f2690c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725677"
---
# <a name="bulk-copy-data-from-program-variables-odbc"></a><span data-ttu-id="c2d9f-102">Massenkopieren von Daten aus Programmvariablen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c2d9f-102">Bulk Copy Data from Program Variables (ODBC)</span></span>
  <span data-ttu-id="c2d9f-103">In diesem Beispiel wird gezeigt, wie mit Massenkopierfunktionen unter Verwendung von `bcp_bind` und `bcp_sendrow` Daten aus Programmvariablen nach SQL Server massenkopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-103">This sample shows how to use bulk copy functions to bulk copy data from program variables to SQL Server using `bcp_bind` and `bcp_sendrow`.</span></span> <span data-ttu-id="c2d9f-104">(Zur Vereinfachung dieses Beispiels wurde der Fehlerprüfcode entfernt.)</span><span class="sxs-lookup"><span data-stu-id="c2d9f-104">(Error-checking code is removed to simplify this example.)</span></span>  
  
 <span data-ttu-id="c2d9f-105">Dieses Beispiel wurde für ODBC, Version 3.0 oder höher, entwickelt.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
 <span data-ttu-id="c2d9f-106">**Sicherheitshinweis** Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-106">**Security Note** When possible, use Windows Authentication.</span></span> <span data-ttu-id="c2d9f-107">Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="c2d9f-108">Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="c2d9f-109">Wenn Sie die Anmeldeinformationen persistent speichern müssen, sollten Sie sie mit der [Win32 Crypto-API](https://go.microsoft.com/fwlink/?LinkId=9504)verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-109">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
### <a name="to-use-bulk-copy-functions-directly-on-program-variables"></a><span data-ttu-id="c2d9f-110">So verwenden Sie Funktionen zum Massenkopieren direkt für Programmvariablen</span><span class="sxs-lookup"><span data-stu-id="c2d9f-110">To use bulk copy functions directly on program variables</span></span>  
  
1.  <span data-ttu-id="c2d9f-111">Ordnen Sie ein Umgebungshandle und ein Verbindungshandle zu.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-111">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="c2d9f-112">Legen Sie SQL_COPT_SS_BCP und SQL_BCP_ON fest, um Massenkopiervorgänge zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-112">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="c2d9f-113">Stellen Sie eine Verbindung mit SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-113">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="c2d9f-114">Rufen Sie [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) auf, um die folgenden Informationen festzulegen:</span><span class="sxs-lookup"><span data-stu-id="c2d9f-114">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="c2d9f-115">Name der Tabelle oder Sicht, aus der bzw. in die massenkopiert werden soll</span><span class="sxs-lookup"><span data-stu-id="c2d9f-115">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="c2d9f-116">Geben Sie NULL für den Namen der Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-116">Specify NULL for the name of the data file.</span></span>  
  
    -   <span data-ttu-id="c2d9f-117">Name einer Datendatei, in die Fehlermeldungen zum Massenkopiervorgang ausgegeben werden sollen (geben Sie NULL an, wenn keine Meldungsdatei erstellt werden soll)</span><span class="sxs-lookup"><span data-stu-id="c2d9f-117">The name of an data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="c2d9f-118">Die Kopierrichtung: DB_IN von der Anwendung in die Sicht oder Tabelle bzw. DB_OUT von der Tabelle oder Sicht in die Anwendung</span><span class="sxs-lookup"><span data-stu-id="c2d9f-118">The direction of the copy: DB_IN from the application to the view or table or DB_OUT to the application from the table or view.</span></span>  
  
5.  <span data-ttu-id="c2d9f-119">Rufen Sie [bcp_bind](../../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) für jede Spalte im Massenkopiervorgang auf, um die Spalte an eine Programmvariable zu binden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-119">Call [bcp_bind](../../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for each column in the bulk copy to bind the column to a program variable.</span></span>  
  
6.  <span data-ttu-id="c2d9f-120">Füllen Sie die Programmvariablen mit Daten, und rufen Sie [bcp_sendrow](../../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) auf, um eine Datenzeile zu senden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-120">Fill the program variables with data, and call [bcp_sendrow](../../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) to send a row of data.</span></span>  
  
7.  <span data-ttu-id="c2d9f-121">Nachdem mehrere Zeilen gesendet wurden, rufen Sie [bcp_batch](../../native-client-odbc-extensions-bulk-copy-functions/bcp-batch.md) auf, um einen Prüfpunkt für die bereits gesendeten Zeilen einzufügen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-121">After several rows have been sent, call [bcp_batch](../../native-client-odbc-extensions-bulk-copy-functions/bcp-batch.md) to checkpoint the rows already sent.</span></span> <span data-ttu-id="c2d9f-122">Es wird empfohlen, [bcp_batch](../../native-client-odbc-extensions-bulk-copy-functions/bcp-batch.md) mindestens einmal nach jeweils 1000 Zeilen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-122">It is good practice to call [bcp_batch](../../native-client-odbc-extensions-bulk-copy-functions/bcp-batch.md) at least once per 1000 rows.</span></span>  
  
8.  <span data-ttu-id="c2d9f-123">Nachdem alle Zeilen gesendet wurden, rufen Sie [bcp_done](../../native-client-odbc-extensions-bulk-copy-functions/bcp-done.md) auf, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-123">After all rows have been sent, call [bcp_done](../../native-client-odbc-extensions-bulk-copy-functions/bcp-done.md) to complete the operation.</span></span>  
  
 <span data-ttu-id="c2d9f-124">Position und Länge der Programmvariablen können während eines Massenkopiervorgangs durch Aufrufe von [bcp_colptr](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colptr.md) und [bcp_collen](../../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md)abgeändert werden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-124">You can vary the location and length of program variables during a bulk copy operation by calling [bcp_colptr](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colptr.md) and [bcp_collen](../../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md).</span></span> <span data-ttu-id="c2d9f-125">Verwenden Sie [bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) zum Festlegen verschiedener Massenkopieroptionen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-125">Use [bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) to set various bulk copy options.</span></span> <span data-ttu-id="c2d9f-126">Verwenden Sie [bcp_moretext](../../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) , `text` um `ntext` -,-und- `image` Daten in Segmenten an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-126">Use [bcp_moretext](../../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) to send `text`, `ntext`, and `image` data in segments to the server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d9f-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2d9f-127">Example</span></span>  
 <span data-ttu-id="c2d9f-128">Dieses Beispiel wird nicht auf IA64-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-128">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="c2d9f-129">Sie benötigen eine ODBC-Datenquelle mit dem Namen AdventureWorks, deren Standarddatenbank die AdventureWorks-Beispieldatenbank ist.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-129">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="c2d9f-130">(Sie können die AdventureWorks-Beispieldatenbank von der Startseite [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) herunterladen.) Diese Datenquelle muss auf dem ODBC-Treiber basieren, der vom Betriebssystem bereitgestellt wird (der Treiber Name ist "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="c2d9f-130">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="c2d9f-131">Wenn Sie dieses Beispiel als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-131">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="c2d9f-132">In diesem Beispiel wird eine Verbindung mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Standardinstanz des Computers hergestellt.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-132">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="c2d9f-133">Ändern Sie zum Herstellen einer Verbindung mit einer benannten Instanz die Definition der ODBC-Datenquelle, um die Instanz im folgenden Format anzugeben: Server\benannteInstanz.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-133">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="c2d9f-134">Standardmäßig wird [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] in einer benannten Instanz installiert.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-134">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="c2d9f-135">Führen Sie das erste Codelisting ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) aus, um im Beispiel verwendete Tabellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-135">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create tables that the sample will use.</span></span>  
  
 <span data-ttu-id="c2d9f-136">Kompilieren Sie das zweite Codelisting (C++) mit odbc32.lib und odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-136">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="c2d9f-137">Wenn Sie das Beispiel mit MSBuild.exe erstellt haben, kopieren Sie zuerst Bcpfmt.fmt und Bcpodbc.bcp aus dem Projektverzeichnis in das Verzeichnis mit der EXE-Datei, und rufen Sie dann die EXE-Datei auf.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-137">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="c2d9f-138">Führen Sie das dritte Codelisting ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) aus, um die im Beispiel verwendeten Tabellen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c2d9f-138">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the tables that the sample used.</span></span>  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPSource')  
     DROP TABLE BCPSource  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPTarget')  
     DROP TABLE BCPTarget  
GO  
  
CREATE TABLE BCPSource (cola int PRIMARY KEY, colb CHAR(10) NULL)  
INSERT INTO BCPSource (cola, colb) VALUES (1, 'aaa')  
INSERT INTO BCPSource (cola, colb) VALUES (2, 'bbb')  
CREATE TABLE BCPTarget (cola int PRIMARY KEY, colb CHAR(10) NULL)  
```  
  
```  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC, hdbc2 = SQL_NULL_HDBC;  
SQLHSTMT hstmt2 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt2 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt2);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (hdbc2 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc2);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc2);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // BCP variables.  
   char *terminator = "\0";  
  
   // bcp_done takes a different format return code because it returns number of rows bulk copied  
   // after the last bcp_batch call.  
   DBINT cRowsDone = 0;  
  
   // Set up separate return code for bcp_sendrow so it is not using the same retcode as SQLFetch.  
   RETCODE SendRet;  
  
   // Column variables.  cbCola and cbColb must be defined right before Cola and szColb because   
   // they are used as bulk copy indicator variables.  
   struct ColaData {  
      int cbCola;  
      SQLINTEGER Cola;  
   } ColaInst;  
  
   struct ColbData {  
      int cbColb;  
      SQLCHAR szColb[11];  
   } ColbInst;  
  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // sample uses Integrated Security, create the SQL Server DSN using Windows NT authentication  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "AdventureWorks..BCPTarget", NULL, NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Bind the program variables for the bulk copy.  
   retcode = bcp_bind(hdbc1, (BYTE *)&ColaInst.cbCola, 4, SQL_VARLEN_DATA, NULL, (INT)NULL, SQLINT4, 1);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_bind(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Could normally use strlen to calculate the bcp_bind cbTerm parameter, but this terminator   
   // is a null byte (\0), which gives strlen a value of 0. Explicitly give cbTerm a value of 1.  
   retcode = bcp_bind(hdbc1, (BYTE *)&ColbInst.cbColb, 4, 11, (UCHAR*)terminator, 1, SQLCHARACTER, 2);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_bind(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate second ODBC connection handle so bulk copy and cursor operations do not conflict.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc2);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc2, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate ODBC statement handle.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc2, &hstmt2);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hstmt2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
SQLLEN lDataLengthA;  
SQLLEN lDataLengthB;  
  
   // Bind the SELECT statement to the same program variables bound to the bulk copy operation.  
   retcode = SQLBindCol(hstmt2, 1, SQL_C_SLONG, &ColaInst.Cola, 0, &lDataLengthA);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLBindCol(hstmt2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLBindCol(hstmt2, 2, SQL_C_CHAR, &ColbInst.szColb, 11, &lDataLengthB);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLBindCol(hstmt2) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute SELECT statement to build a cursor containing data to be bulk copied to new table.  
   retcode = SQLExecDirect(hstmt2, (UCHAR*)"SELECT * FROM BCPSource", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
   // Go into a loop fetching rows from the cursor until each row is fetched. Because the   
   // bcp_bind calls and SQLBindCol calls each reference the same variables, each fetch fills   
   // the variables used by bcp_sendrow, so all you have to do to send the data to SQL Server is   
   // to call bcp_sendrow.  
   while ( (retcode = SQLFetch(hstmt2) ) != SQL_NO_DATA) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLFetch Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
  
      ColaInst.cbCola = (int)lDataLengthA;  
      ColbInst.cbColb = (int)lDataLengthB;  
  
     if ( (SendRet = bcp_sendrow(hdbc1) ) != SUCCEED ) {  
         printf("bcp_sendrow(hdbc1) Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Signal the end of the bulk copy operation.  
   cRowsDone = bcp_done(hdbc1);  
   if ( (cRowsDone == -1) ) {  
      printf("bcp_done(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied after last bcp_batch call = %d.\n", cRowsDone);  
  
   // Cleanup.  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt2);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLDisconnect(hdbc2);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc2);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPSource')  
     DROP TABLE BCPSource  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPTarget')  
     DROP TABLE BCPTarget  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2d9f-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2d9f-139">See Also</span></span>  
 <span data-ttu-id="c2d9f-140">[Massen kopieren mit dem SQL Server ODBC-Treiber &#40;ODBC-&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="c2d9f-140">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="c2d9f-141">Massenkopieren aus Programmvariablen</span><span class="sxs-lookup"><span data-stu-id="c2d9f-141">Bulk Copying from Program Variables</span></span>](../../native-client-odbc-bulk-copy-operations/bulk-copying-from-program-variables.md)  
  
  
