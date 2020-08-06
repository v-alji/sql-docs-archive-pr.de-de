---
title: Massen Kopieren mithilfe einer Format Datei (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725678"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="fcd59-102">Massenkopieren mithilfe einer Formatdatei (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fcd59-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="fcd59-103">Dieses Beispiel zeigt, wie die ODBC-Funktion bcp_init mit einer Formatdatei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcd59-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="fcd59-104">So führen Sie einen Massenkopiervorgang mithilfe einer Formatdatei aus</span><span class="sxs-lookup"><span data-stu-id="fcd59-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="fcd59-105">Ordnen Sie ein Umgebungshandle und ein Verbindungshandle zu.</span><span class="sxs-lookup"><span data-stu-id="fcd59-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="fcd59-106">Legen Sie SQL_COPT_SS_BCP und SQL_BCP_ON fest, um Massenkopiervorgänge zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fcd59-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="fcd59-107">Herstellen einer Verbindung mit Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fcd59-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="fcd59-108">Rufen Sie [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) auf, um die folgenden Informationen festzulegen:</span><span class="sxs-lookup"><span data-stu-id="fcd59-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="fcd59-109">Name der Tabelle oder Sicht, aus der bzw. in die massenkopiert werden soll</span><span class="sxs-lookup"><span data-stu-id="fcd59-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="fcd59-110">Name der Datendatei, welche die in die Datenbank zu kopierenden Daten enthält bzw. in welche die Daten eingefügt werden sollen, die aus der Datenbank kopiert werden</span><span class="sxs-lookup"><span data-stu-id="fcd59-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="fcd59-111">Name der Datendatei, in die Fehlermeldungen zum Massenkopiervorgang ausgegeben werden sollen (geben Sie NULL an, wenn keine Meldungsdatei erstellt werden soll)</span><span class="sxs-lookup"><span data-stu-id="fcd59-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="fcd59-112">Kopierrichtung: DB_IN, wenn Daten aus der Datei in die Tabelle oder Sicht kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="fcd59-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="fcd59-113">Rufen Sie [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) auf, um eine Formatdatei zu lesen, welche die vom Massenkopiervorgang verwendete Datendatei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="fcd59-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="fcd59-114">Rufen Sie [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) auf, um den Massenkopiervorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fcd59-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcd59-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcd59-115">Example</span></span>  
 <span data-ttu-id="fcd59-116">Dieses Beispiel wird nicht auf IA64-basierten Systemen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fcd59-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="fcd59-117">Sie benötigen eine ODBC-Datenquelle mit dem Namen AdventureWorks, deren Standarddatenbank die AdventureWorks-Beispieldatenbank ist.</span><span class="sxs-lookup"><span data-stu-id="fcd59-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="fcd59-118">(Sie können die AdventureWorks-Beispieldatenbank von der Startseite [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) herunterladen.) Diese Datenquelle muss auf dem ODBC-Treiber basieren, der vom Betriebssystem bereitgestellt wird (der Treiber Name ist "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="fcd59-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="fcd59-119">Wenn Sie dieses Beispiel als 32-Bit-Anwendung entwickeln und unter einem 64-Bit-Betriebssystem ausführen, müssen Sie die ODBC-Datenquelle mit dem ODBC-Administrator in %windir%\SysWOW64\odbcad32.exe erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcd59-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="fcd59-120">In diesem Beispiel wird eine Verbindung mit der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Standardinstanz des Computers hergestellt.</span><span class="sxs-lookup"><span data-stu-id="fcd59-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="fcd59-121">Ändern Sie zum Herstellen einer Verbindung mit einer benannten Instanz die Definition der ODBC-Datenquelle, um die Instanz im folgenden Format anzugeben: Server\benannteInstanz.</span><span class="sxs-lookup"><span data-stu-id="fcd59-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="fcd59-122">Standardmäßig wird [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] in einer benannten Instanz installiert.</span><span class="sxs-lookup"><span data-stu-id="fcd59-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="fcd59-123">Führen Sie das erste Codelisting ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) aus, um die im Beispiel verwendete Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcd59-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="fcd59-124">Kopieren Sie das zweite Codelisting, und fügen Sie es in eine Datei mit dem Namen Bcpfmt.fmt ein.</span><span class="sxs-lookup"><span data-stu-id="fcd59-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="fcd59-125">Jede Spalte in der Tabelle wird durch ein Tabstoppzeichen getrennt.</span><span class="sxs-lookup"><span data-stu-id="fcd59-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="fcd59-126">Kopieren Sie das dritte Codelisting, und fügen Sie es in eine Datei mit dem Namen Bcpodbc.bcp ein.</span><span class="sxs-lookup"><span data-stu-id="fcd59-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="fcd59-127">Jedem Wagenrücklauf in der Datei ist ein Tabstoppzeichen vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="fcd59-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="fcd59-128">Kompilieren Sie das vierte Codelisting (C++) mit odbc32.lib und odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="fcd59-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="fcd59-129">Wenn Sie das Beispiel mit MSBuild.exe erstellt haben, kopieren Sie zuerst Bcpfmt.fmt und Bcpodbc.bcp aus dem Projektverzeichnis in das Verzeichnis mit der EXE-Datei, und rufen Sie dann die EXE-Datei auf.</span><span class="sxs-lookup"><span data-stu-id="fcd59-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="fcd59-130">Führen Sie das fünfte Codelisting ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) aus, um die im Beispiel verwendete Tabelle zu löschen.</span><span class="sxs-lookup"><span data-stu-id="fcd59-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
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
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcd59-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcd59-131">See Also</span></span>  
 <span data-ttu-id="fcd59-132">[Massen kopieren mit dem SQL Server ODBC-Treiber &#40;ODBC-&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="fcd59-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="fcd59-133">Verwenden von Datendateien und Formatdateien</span><span class="sxs-lookup"><span data-stu-id="fcd59-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
