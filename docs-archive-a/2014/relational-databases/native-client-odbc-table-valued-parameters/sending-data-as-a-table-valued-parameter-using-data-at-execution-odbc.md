---
title: Senden von Daten als Tabellenwert Parameter mit Data-at-Execution (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), sending data to a stored procedure one row at a time
ms.assetid: 361e6442-34de-4cac-bdbd-e05f04a21ce4
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3951ef93539e003b62397f370490c89c953a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724581"
---
# <a name="sending-data-as-a-table-valued-parameter-using-data-at-execution-odbc"></a><span data-ttu-id="8df2c-102">Senden von Daten als Tabellenwertparameter mit Data-at-Execution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8df2c-102">Sending Data as a Table-Valued Parameter Using Data-At-Execution (ODBC)</span></span>
  <span data-ttu-id="8df2c-103">Dies ähnelt der Vorgehensweise " [alles im Arbeitsspeicher](sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc.md) ", verwendet jedoch Data-at-Execution für den Tabellenwert Parameter.</span><span class="sxs-lookup"><span data-stu-id="8df2c-103">This is similar to the [All in Memory](sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc.md) procedure, but uses data-at-execution for the table-valued parameter.</span></span>  
  
 <span data-ttu-id="8df2c-104">Ein weiteres Beispiel zur Veranschaulichung von Tabellenwert Parametern finden Sie unter [Verwenden von Tabellenwert Parametern &#40;ODBC-&#41;](table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="8df2c-104">For another sample demonstrating table-valued parameters, see [Use Table-Valued Parameters &#40;ODBC&#41;](table-valued-parameters-odbc.md).</span></span>  
  
 <span data-ttu-id="8df2c-105">In diesem Beispiel gibt der Treiber, wenn SQLExecute oder SQLExecDirect aufgerufen wird, SQL_NEED_DATA zurück.</span><span class="sxs-lookup"><span data-stu-id="8df2c-105">In this example, when SQLExecute or SQLExecDirect is called, the driver returns SQL_NEED_DATA.</span></span> <span data-ttu-id="8df2c-106">Die Anwendung ruft dann SQLParamData wiederholt auf, bis der Treiber einen anderen Wert als SQL_NEED_DATA zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8df2c-106">The application then calls SQLParamData repeatedly until the driver returns a value other than SQL_NEED_DATA.</span></span> <span data-ttu-id="8df2c-107">Der Treiber gibt *ParameterValuePtr* zurück, um die Anwendung darüber zu informieren, für welchen Parameterdaten angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="8df2c-107">The driver returns *ParameterValuePtr* to inform the application which parameter it is requesting data for.</span></span> <span data-ttu-id="8df2c-108">Die Anwendung ruft SQLPutData auf, um Parameterdaten vor dem nächsten Aufruf von SQLParamData bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8df2c-108">The application calls SQLPutData to supply parameter data before the next call to SQLParamData.</span></span> <span data-ttu-id="8df2c-109">Bei einem Tabellenwert Parameter gibt der SQLPutData-Befehl an, wie viele Zeilen er für den Treiber vorbereitet hat (in diesem Beispiel immer 1).</span><span class="sxs-lookup"><span data-stu-id="8df2c-109">For a table-valued parameter, the call to SQLPutData indicates how many rows it has prepared for the driver (in this example, always 1).</span></span> <span data-ttu-id="8df2c-110">Wenn alle Zeilen des Tabellen Werts an den Treiber weitergegeben wurden, wird SQLPutData aufgerufen, um anzugeben, dass 0 Zeilen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8df2c-110">When all rows of the table-value have been passed to the driver, SQLPutData is called to indicate that 0 rows are available.</span></span>  
  
 <span data-ttu-id="8df2c-111">Es ist möglich, Data-at-Execution-Werte innerhalb von Zeilen eines Tabellenwerts zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8df2c-111">It is possible to use data-at-execution values within rows of a table-value.</span></span> <span data-ttu-id="8df2c-112">Der von SQLParamData zurückgegebene Wert informiert die Anwendung darüber, welchen Wert der Treiber erfordert.</span><span class="sxs-lookup"><span data-stu-id="8df2c-112">The value returned by SQLParamData informs the application which value the driver requires.</span></span> <span data-ttu-id="8df2c-113">Wie bei regulären Parameterwerten kann SQLPutData einmal oder mehrmals für einen Zeichen-oder binären Tabellenwert Spalten-Wert aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8df2c-113">As with regular parameter values, SQLPutData can be called one or more times for a character or binary table-value column value.</span></span> <span data-ttu-id="8df2c-114">Dies ermöglicht es einer Anwendung, große Werte schrittweise zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="8df2c-114">This allows an application to pass large values in pieces.</span></span>  
  
 <span data-ttu-id="8df2c-115">Wenn SQLPutData für einen Tabellenwert aufgerufen wird, wird *DataPtr* für die Anzahl der verfügbaren Zeilen verwendet (in diesem Beispiel immer 1).</span><span class="sxs-lookup"><span data-stu-id="8df2c-115">When SQLPutData is called for a table-value, *DataPtr* is used for the number of rows available (in this example, always 1).</span></span> <span data-ttu-id="8df2c-116">*StrLen_or_IndPtr* muss immer 0 sein.</span><span class="sxs-lookup"><span data-stu-id="8df2c-116">*StrLen_or_IndPtr* must always be 0.</span></span> <span data-ttu-id="8df2c-117">Wenn alle Zeilen des Tabellen Werts weitergegeben wurden, wird SQLPutData mit einem *DataPtr* -Wert von 0 aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8df2c-117">When all rows of the table-value have been passed, SQLPutData is called with a *DataPtr* value of 0.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="8df2c-118">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="8df2c-118">Prerequisite</span></span>  
 <span data-ttu-id="8df2c-119">In dieser Prozedur wird davon ausgegangen, dass der folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehl auf dem Server ausgeführt wurde:</span><span class="sxs-lookup"><span data-stu-id="8df2c-119">This procedure assumes that the following [!INCLUDE[tsql](../../includes/tsql-md.md)] has been executed on the server:</span></span>  
  
```  
create type TVParam as table(ProdCode integer, Qty integer)  
create procedure TVPOrderEntry(@CustCode varchar(5), @Items TVPParam,   
            @OrdNo integer output, @OrdDate datetime output)  
         as   
         set @OrdDate = GETDATE();  
         insert into TVPOrd (OrdDate, CustCode) values (@OrdDate, @CustCode) output OrdNo);   
         select @OrdNo = SCOPE_IDENTITY();   
         insert into TVPItem (OrdNo, ProdCode, Qty)  
select @OrdNo, @Items.ProdCode, @Items.Qty   
from @Items  
```  
  
## <a name="to-send-the-data"></a><span data-ttu-id="8df2c-120">So senden Sie Daten</span><span class="sxs-lookup"><span data-stu-id="8df2c-120">To Send the Data</span></span>  
  
1.  <span data-ttu-id="8df2c-121">Deklarieren Sie die Variablen für die SQL-Parameter.</span><span class="sxs-lookup"><span data-stu-id="8df2c-121">Declare the variables for the SQL parameters.</span></span> <span data-ttu-id="8df2c-122">Die Puffer für Tabellenwertparameter müssen in diesem Beispiel keine Arrays sein. In diesem Beispiel wird jeweils eine Zeile übergeben.</span><span class="sxs-lookup"><span data-stu-id="8df2c-122">The buffers for table-valued parameters do not have to be arrays in this example; the example passes one row at a time.</span></span>  
  
    ```  
    SQLRETURN r;  
  
    // Variables for SQL parameters:  
    SQLCHAR CustCode[6];  
    SQLCHAR *TVP = (SQLCHAR *) "TVPInParam";  
    SQLINTEGER ProdCode, Qty;  
    SQLINTEGER OrdNo;  
    char *OrdDate[23];  
    SQLCHAR *TVP = (SQLCHAR *) "TVParam";  
    SQLINTEGER ItemNo;  
    // Variables for indicator/length variables associated with parameters:  
    SQLLEN cbCustCode, cbTVP, cbProdCode, cbQty, cbOrdNo, cbOrdDate, cbItemNo;  
    // Token returned by SQLParamData to indicate which param data is needed for:  
    SQLPOINTER ParamId;  
    ```  
  
2.  <span data-ttu-id="8df2c-123">Binden Sie die Parameter.</span><span class="sxs-lookup"><span data-stu-id="8df2c-123">Bind the parameters.</span></span> <span data-ttu-id="8df2c-124">*ColumnSize* ist 1. Dies bedeutet, dass höchstens eine Zeile gleichzeitig übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="8df2c-124">*ColumnSize* is 1, meaning that at most one row is passed at a time.</span></span>  
  
    ```  
    // Bind parameters for call to TVPOrderEntryByRow.  
    r = SQLBindParameter(hstmt, 1, SQL_C_CHAR, SQL_PARAM_INPUT,SQL_VARCHAR, 5, 0, CustCode, sizeof(CustCode), &cbCustCode);  
  
    // 2 - Items TVP  
    r = SQLBindParameter(hstmt,   
        2,         // ParameterNumber  
        SQL_C_DEFAULT,   // InputOutputType  
        SQL_PARAM_INPUT,   // ValueType   
        SQL_SS_TABLE,   // Parametertype  
        1,         // ColumnSize: For a table-valued parameter this the row array size.  
        0,         // DecimalDigits: For a table-valued parameter this is always 0.   
        TVP,      // ParameterValuePtr: For a table-valued parameter this is the type name of the TVP,  
             //      and also a token returned by SQLParamData.  
        SQL_NTS,      // BufferLength: For a table-valued parameter this is the length of the type name or SQL_NTS.  
        &cbTVP);      // StrLen_or_IndPtr: For a table-valued parameter this is the number of rows input and output.  
  
    // 3 - OrdNo output  
    r = SQLBindParameter(hstmt, 3, SQL_PARAM_OUTPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &OrdNo,  
        sizeof(SQLINTEGER), &cbOrdNo);  
    // 4- OrdDate output  
    r = SQLBindParameter(hstmt, 4, SQL_PARAM_OUTPUT, SQL_C_CHAR, SQL_TYPE_TIMESTAMP, 23, 3, &OrdDate,  
        sizeof(OrdDate), &cbOrdDate);  
    ```  
  
3.  <span data-ttu-id="8df2c-125">Binden Sie die Spalten für den Tabellenwertparameter.</span><span class="sxs-lookup"><span data-stu-id="8df2c-125">Bind the columns for the table-valued parameter.</span></span>  
  
    ```  
    // Bind the table-valued parameter columns.  
    // First set focus on param 2  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 2, SQL_IS_INTEGER);  
  
    // ProdCode  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &ProdCode,  
        sizeof(SQLINTEGER), &cbProdCode);  
    // Qty  
    r = SQLBindParameter(hstmt, 2, SQL_PARAM_INPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &Qty,   
       sizeof(SQLINTEGER), &cbQty);  
  
    // Reset param focus  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 0, SQL_IS_INTEGER);  
    ```  
  
4.  <span data-ttu-id="8df2c-126">Initialisieren Sie die Parameter.</span><span class="sxs-lookup"><span data-stu-id="8df2c-126">Initialize the parameters.</span></span> <span data-ttu-id="8df2c-127">In diesem Beispiel wird die Größe des Tabellenwertparameters auf SQL_DATA_AT_EXEC statt auf eine Zeilenanzahl festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8df2c-127">This example sets the size of the table-valued parameter to SQL_DATA_AT_EXEC, rather than to a row count.</span></span>  
  
    ```  
    // Initialze the TVP for row streaming.  
    cbTVP = SQL_DATA_AT_EXEC;  
  
    // Populate non-data-at-exec parameters.  
    strcpy_s((char *) CustCode ,sizeof(CustCode), "CUST1"); cbCustCode = SQL_NTS;  
    ```  
  
5.  <span data-ttu-id="8df2c-128">Rufen Sie die Prozedur auf.</span><span class="sxs-lookup"><span data-stu-id="8df2c-128">Call the procedure.</span></span> <span data-ttu-id="8df2c-129">SQLExecDirect gibt SQL_NEED_DATA zurück, weil der Tabellenwert Parameter ein Data-at-Execution-Parameter ist.</span><span class="sxs-lookup"><span data-stu-id="8df2c-129">SQLExecDirect will return SQL_NEED_DATA because the table-valued parameter is a data-at-execution parameter.</span></span>  
  
    ```  
    // Call the procedure  
    r = SQLExecDirect(hstmt, (SQLCHAR *) "{call TVPOrderEntry(?, ?, ?, ?)}",SQL_NTS);  
    ```  
  
6.  <span data-ttu-id="8df2c-130">Geben Sie Data-at-Execution-Parameterdaten an.</span><span class="sxs-lookup"><span data-stu-id="8df2c-130">Supply data-at-execution parameter data.</span></span> <span data-ttu-id="8df2c-131">Wenn SQLParamData den *ParameterValuePtr* für einen Tabellenwert Parameter zurückgibt, muss die Anwendung die Spalten für die nächste Zeile oder Zeilen des Tabellen Werts vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="8df2c-131">When SQLParamData returns the *ParameterValuePtr* for a table-valued parameter, the application must prepare the columns for the next row or rows of the table-value.</span></span> <span data-ttu-id="8df2c-132">Anschließend ruft die Anwendung SQLPutData auf, wobei *DataPtr* auf die Anzahl der verfügbaren Zeilen (in diesem Beispiel 1) und *StrLen_or_IndPtr* auf 0 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8df2c-132">Then the application calls SQLPutData with *DataPtr* set to the number of rows available (in this example, 1) and *StrLen_or_IndPtr* set to 0.</span></span>  
  
    ```  
    // Check if parameter data is required, and get the first parameter ID token  
    if (r == SQL_NEED_DATA) {  
        r = SQLParamData(hstmt, &ParamId);  
    }  
  
    // Supply parameter row data.  
    int rowNum = 0;  
    while (r == SQL_NEED_DATA) {  
        if (ParamId == TVP) {  
       switch (rowNum) {  
           case 0: // Supply data for 1st row  
          // Populate input table-valued parameter row constituent columns.  
          ProdCode = 1215;   cbProdCode = sizeof(SQLINTEGER);   
          Qty = 5;      cbQty = sizeof(SQLINTEGER);  
          // Returning 1 for StrLenOrIndPtr indicates that a row is available.  
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 1);  
          rowNum++;  
          break;  
  
           case 1: // Supply data for the second row.  
          // Populate another table-valued parameter row as above.  
          ProdCode = 1017;   cbProdCode = sizeof(SQLINTEGER);   
          // This time supply Qty through SQLPutData.  
          Qty = 0;      cbQty = SQL_DATA_AT_EXEC;   
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 1);  
          rowNum++;  
          break;  
  
        default:  
          // Passing 0 in StrLenOrIndPtr indicates that no more table-valued parameter rows are available.  
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 0);  
          break;  
           }  
        }  
        else {  
           if (ParamId == &Qty) {  
          Qty = 2;  
          // For a character or binary parameter, SQLPutData could be called  
          // multiple times to pass the value in pieces.  
          SQLPutData(hstmt, &Qty, sizeof(SQLINTEGER));  
           }  
       }  
       // Signal that parameter data is available, and get the token for   
       // the next parameter.  
       r = SQLParamData(hstmt, &ParamId);  
        }  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="8df2c-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8df2c-133">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="8df2c-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8df2c-134">Description</span></span>  
 <span data-ttu-id="8df2c-135">Dieses Beispiel zeigt, dass Sie das Zeilen Streaming, eine Zeile pro SQLPutData-Befehl, mit ODBC TVP verwenden können, ähnlich wie bei der Verwendung von BCP.exe zum Laden von Daten in eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8df2c-135">This sample shows that you can use row streaming, one row per call to SQLPutData, with ODBC TVP, similar to how you might use BCP.exe to load data into a database.</span></span>  
  
 <span data-ttu-id="8df2c-136">Ändern Sie den Servernamen in der Verbindungszeichenfolge, bevor Sie das Beispiel erstellen.</span><span class="sxs-lookup"><span data-stu-id="8df2c-136">Before building the sample, change the server name in the connection string.</span></span>  
  
 <span data-ttu-id="8df2c-137">In diesem Beispiel wird die Standarddatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="8df2c-137">This sample uses the default database.</span></span> <span data-ttu-id="8df2c-138">Führen Sie vor dem Ausführen des Beispiels die folgenden Befehle in der ausgewählten Datenbank aus:</span><span class="sxs-lookup"><span data-stu-id="8df2c-138">Before running this sample, run the following commands in the database you will use:</span></span>  
  
```  
create table MCLOG (  
   biSeqNo bigint,   
   iSeries int,   
   bmRestData varbinary(max)  
)  
go  
  
-- Table type definition  
create type MCLOGType   
   as table(biSeqNo bigint, iSeries int, bmRestData varbinary(max) )  
go  
  
-- Insert procedure  
create procedure MCLOGInsert (@TableVariable MCLOGType READONLY)  
   as  
   insert into MCLog(biSeqNo,  iSeries, bmRestData)   
   select biSeqNo, iSeries, bmRestData from @TableVariable    
go  
```  
  
### <a name="code"></a><span data-ttu-id="8df2c-139">Code</span><span class="sxs-lookup"><span data-stu-id="8df2c-139">Code</span></span>  
  
```  
#define UNICODE  
#define _UNICODE  
#define _SQLNCLI_ODBC_  
  
#include <windows.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// link to sqlncli11.lib  
  
#define SUCCESS(x) ( \  
   !((x) & 0xFFFE) \  
   )  
  
#define CHKRC(stmt) { \  
   rc = (stmt); \  
   if (!SUCCESS(rc)) { \  
      _tprintf(_T(#stmt) _T(" failed with rc = %ld\r\n"), rc); \  
      goto EXIT; \  
   } \  
};  
  
void PrintError(SQLSMALLINT HandleType, SQLHANDLE Handle) {  
   RETCODE rc = SQL_SUCCESS;  
   SQLTCHAR szSqlState[6];  
   SQLTCHAR szMessage[1024];  
   SQLSMALLINT i = 1;  
   SQLSMALLINT msgLen = 0;  
   SQLINTEGER NativeError;  
  
   i = 1;  
   while ( (rc = SQLGetDiagRec(HandleType, Handle, i, szSqlState, &NativeError, szMessage, sizeof(szMessage)/sizeof(SQLTCHAR), &msgLen)) != SQL_NO_DATA) {  
      if (!SUCCESS(rc))  
         break;  
      szMessage[msgLen] = 0;  
      szSqlState[5] = 0;  
      _tprintf(_T("SQLState=%s, NativeError=%ld, Message=%s\r\n"), szSqlState, NativeError, szMessage);  
      i++;  
   }  
}  
  
int main() {  
   RETCODE rc = SQL_SUCCESS;  
   HENV henv = SQL_NULL_HENV;  
   HDBC hdbc = SQL_NULL_HDBC;  
   SQLHSTMT hstmt = SQL_NULL_HSTMT;  
   SQLTCHAR * pszConnection = _T("DRIVER={SQL Server Native Client 10.0};Server=your_servername;Trusted_Connection=Yes;");  
  
   // insert one TVP parameter  
   SQLTCHAR * pszInsertStmt = _T("{call MCLOGInsert(?)}");  
   SQLLEN cbParamLength;  
   SQLULEN cMaxRows = 3;  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HENV, &henv));  
   CHKRC(SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0));  
   CHKRC(SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc));  
   CHKRC(SQLSetConnectAttr(hdbc, SQL_ATTR_LOGIN_TIMEOUT,reinterpret_cast<SQLPOINTER>(60),SQL_IS_UINTEGER));  
   CHKRC(SQLDriverConnect(hdbc, NULL, pszConnection, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT));  
   CHKRC(SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt));  
   CHKRC(SQLPrepare(hstmt, pszInsertStmt, SQL_NTS));  
  
   // Bind the first parameter  
   CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)1, 0, &cbParamLength));  
   // If the stored procedure is executed as T-SQL ("exec sp_insert ?, ?"), you will supply the type name.  
   // CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)lpszTVPParamType, SQL_NTS, &cbParamLengths));  
  
   // bind TVP columns  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)1, SQL_IS_INTEGER));  
  
   // for each TVP column, you can define an array to send more than one row for each SQLPutData call.  
   LONGLONG llSeqNo;  
   SQLLEN cbSeqNo = sizeof(LONGLONG);  
   LONG lSeries;  
   SQLLEN cbSeries = sizeof(LONG);  
   BYTE rgbRestData[2048];  
   SQLLEN cbRestData = SQL_DATA_AT_EXEC;  
   SQLUSMALLINT iColumn = 1;  
  
   // Bind biSeqNo   
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SBIGINT, SQL_BIGINT, sizeof(LONGLONG), 0, (SQLPOINTER)&llSeqNo, sizeof(llSeqNo), &cbSeqNo));  
  
   // Bind iSeries   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SLONG, SQL_INTEGER, sizeof(LONG), 0, (SQLPOINTER)&lSeries, sizeof(lSeries), &cbSeries));  
  
   // Bind bmRestData   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_BINARY, SQL_VARBINARY, 0, 0, (SQLPOINTER)rgbRestData, 0, &cbRestData));  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)0, SQL_IS_INTEGER));  
  
   // Set cbParamLength to SQL_DATA_AT_EXEC to indicate the TVP parameter is bound as DAE.  
   cbParamLength = SQL_DATA_AT_EXEC;  
   rc = SQLExecute(hstmt);  
  
   if (rc == SQL_NEED_DATA) {  
      SQLPOINTER ptr = NULL;  
      SQLULEN cRows = 0;  
  
      rc = ::SQLParamData(hstmt, &ptr);  
  
      while (rc == SQL_NEED_DATA) {  
         if (ptr == (SQLPOINTER)1) {  
            // it is the TVP parameter  
            if (cRows == cMaxRows) {  
               // We finish sending the last row already.  
               CHKRC(::SQLPutData(hstmt, NULL, 0));  
            }  
            else {  
               // StrLen_or_IndPtr can be changed to SQL_DATA_AT_EXEC or to a byte length before sending  
               // the actual TVP rows. SQL_DATA_AT_EXEC means send DAE data.  
               llSeqNo = cRows;  
               cbSeqNo = sizeof(LONGLONG);   // send as bound TVP column  
               lSeries = cRows + 100;  
               cbSeries = sizeof(LONG);   // send as bound TVP column  
               cbRestData = SQL_DATA_AT_EXEC;   // send as DAE TVP column  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)1, 1));  
               cRows++;  
            }  
         }  
         else if (ptr == (SQLPOINTER)rgbRestData)  
            // varbinary(max) column.  Send data in parts.  
            for ( int i = 0 ; i < 3 ; i++ ) {  
               // Obtain the data in part from somewhere, here we just set all bytes to 'a'.  
               ::memset(rgbRestData, 'a', sizeof(rgbRestData));  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)rgbRestData, sizeof(rgbRestData)));  
            }  
         else   
            // handling other DAE parameters, but in our case, we don't have other DAE parameters.  
            goto EXIT;  
         rc = ::SQLParamData(hstmt, &ptr);  
      }  
   }  
  
   if (hstmt)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt);  
   if (hdbc) {  
      SQLDisconnect(hdbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc);  
   }  
   if (henv)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
  
EXIT:  
   if (!SUCCESS(rc)) {  
      if (hstmt)  
         PrintError(SQL_HANDLE_STMT, hstmt);  
      if (hdbc)  
         PrintError(SQL_HANDLE_DBC, hdbc);  
      if(henv)  
         PrintError(SQL_HANDLE_ENV, henv);  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="8df2c-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8df2c-140">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="8df2c-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8df2c-141">Description</span></span>  
 <span data-ttu-id="8df2c-142">Dieses Beispiel zeigt, dass Sie mit ODBC TVP Zeilen Streaming, mehrere Zeilen pro aufzurufenden SQLPutData-Vorgang verwenden können, ähnlich wie bei der Verwendung von BCP.exe zum Laden von Daten in eine Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8df2c-142">This sample shows that you can use row streaming, multiple rows per call to SQLPutData, with ODBC TVP, similar to how you might use BCP.exe to load data into a database.</span></span>  
  
 <span data-ttu-id="8df2c-143">Ändern Sie den Servernamen in der Verbindungszeichenfolge, bevor Sie das Beispiel erstellen.</span><span class="sxs-lookup"><span data-stu-id="8df2c-143">Before building the sample, change the server name in the connection string.</span></span>  
  
 <span data-ttu-id="8df2c-144">In diesem Beispiel wird die Standarddatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="8df2c-144">This sample uses the default database.</span></span> <span data-ttu-id="8df2c-145">Führen Sie vor dem Ausführen des Beispiels die folgenden Befehle in der ausgewählten Datenbank aus:</span><span class="sxs-lookup"><span data-stu-id="8df2c-145">Before running this sample, run the following commands in the database you will use:</span></span>  
  
```  
create table MCLOG (  
   biSeqNo bigint,   
   iSeries int,   
   bmRestData varbinary(max)  
)  
go  
  
-- Table type definition  
create type MCLOGType   
   as table(biSeqNo bigint, iSeries int, bmRestData varbinary(max) )  
go  
  
-- Insert procedure  
create procedure MCLOGInsert (@TableVariable MCLOGType READONLY)  
   as  
   insert into MCLog(biSeqNo,  iSeries, bmRestData)   
   select biSeqNo, iSeries, bmRestData from @TableVariable    
go  
```  
  
### <a name="code"></a><span data-ttu-id="8df2c-146">Code</span><span class="sxs-lookup"><span data-stu-id="8df2c-146">Code</span></span>  
  
```  
#define UNICODE  
#define _UNICODE  
#define _SQLNCLI_ODBC_  
  
#include <windows.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// link to sqlncli11.lib  
  
#define SUCCESS(x) ( \  
   !((x) & 0xFFFE) \  
   )  
  
#define CHKRC(stmt) { \  
   rc = (stmt); \  
   if (!SUCCESS(rc)) { \  
      _tprintf(_T(#stmt) _T(" failed with rc = %ld\r\n"), rc); \  
      goto EXIT; \  
   } \  
};  
  
void PrintError(SQLSMALLINT HandleType, SQLHANDLE Handle) {  
   RETCODE rc = SQL_SUCCESS;  
   SQLTCHAR szSqlState[6];  
   SQLTCHAR szMessage[1024];  
   SQLSMALLINT i = 1;  
   SQLSMALLINT msgLen = 0;  
   SQLINTEGER NativeError;  
  
   i = 1;  
   while ( (rc = SQLGetDiagRec(HandleType, Handle, i, szSqlState, &NativeError, szMessage, sizeof(szMessage)/sizeof(SQLTCHAR), &msgLen)) != SQL_NO_DATA) {  
      if (!SUCCESS(rc))  
         break;  
      szMessage[msgLen] = 0;  
      szSqlState[5] = 0;  
      _tprintf(_T("SQLState=%s, NativeError=%ld, Message=%s\r\n"), szSqlState, NativeError, szMessage);  
      i++;  
   }  
}  
  
int main() {  
   RETCODE rc = SQL_SUCCESS;  
   HENV henv = SQL_NULL_HENV;  
   HDBC hdbc = SQL_NULL_HDBC;  
   SQLHSTMT hstmt = SQL_NULL_HSTMT;  
   SQLTCHAR * pszConnection = _T("DRIVER={SQL Server Native Client 10.0};Server=MyServer;Trusted_Connection=Yes;");  
  
   // insert one TVP parameter  
   SQLTCHAR * pszInsertStmt = _T("{call MCLOGInsert(?)}");  
   SQLLEN cbParamLength;  
   SQLULEN cMaxRows = 9;  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HENV, &henv));  
   CHKRC(SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0));  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc));  
   CHKRC(SQLSetConnectAttr( hdbc, SQL_ATTR_LOGIN_TIMEOUT, reinterpret_cast<SQLPOINTER>(60), SQL_IS_UINTEGER));  
   CHKRC(SQLDriverConnect( hdbc, NULL, pszConnection, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT));   
   CHKRC(SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt));  
   CHKRC(SQLPrepare(hstmt, pszInsertStmt, SQL_NTS));  
  
   // Bind the first parameter  
   CHKRC(SQLBindParameter( hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)1, 0, &cbParamLength));  
  
   /*  
   // If the stored procedure is executed as T-SQL ("exec sp_insert ?, ?"), then, supply the type name.  
   CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)lpszTVPParamType, SQL_NTS, &cbParamLengths));  
   */  
  
   // bind TVP columns.  
   CHKRC(SQLSetStmtAttr( hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)1, SQL_IS_INTEGER));   
  
   // For the first and the second TVP columns (bigint, int), always send them as bound.   
   // For the third column varbinary(max), either send them as bound or DAE.  
   const size_t ARRAY_SIZE = 3;  
   LONGLONG llSeqNo[ARRAY_SIZE];  
   SQLLEN cbSeqNo[ARRAY_SIZE] = {sizeof(LONGLONG), sizeof(LONGLONG), sizeof(LONGLONG)};  
   LONG lSeries[ARRAY_SIZE];  
   SQLLEN cbSeries[ARRAY_SIZE] = {sizeof(LONG), sizeof(LONG), sizeof(LONG)};  
   BYTE rgbRestData[ARRAY_SIZE][2048];  
   SQLLEN cbRestData[ARRAY_SIZE] = {sizeof(rgbRestData[0]), sizeof(rgbRestData[0]), sizeof(rgbRestData[0])};  
   SQLUSMALLINT iColumn = 1;  
  
   // Bind biSeqNo   
   CHKRC(SQLBindParameter( hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SBIGINT, SQL_BIGINT, sizeof(LONGLONG), 0, (SQLPOINTER)&llSeqNo, sizeof(llSeqNo[0]), cbSeqNo));  
  
   // Bind iSeries   
   iColumn++;  
   CHKRC(SQLBindParameter( hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SLONG, SQL_INTEGER, sizeof(LONG), 0, (SQLPOINTER)&lSeries, sizeof(lSeries[0]), cbSeries));  
  
   // Bind bmRestData   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_BINARY, SQL_VARBINARY, 0, 0, (SQLPOINTER)rgbRestData, sizeof(rgbRestData[0]), cbRestData));  
  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)0, SQL_IS_INTEGER));  
  
   // Set cbParamLength to SQL_DATA_AT_EXEC to indicate the TVP parameter is bound as DAE.  
   cbParamLength = SQL_DATA_AT_EXEC;  
   rc = SQLExecute(hstmt);  
  
   if (rc == SQL_NEED_DATA) {  
      SQLPOINTER ptr = NULL;  
      SQLUINTEGER cRows = 0;  
  
      rc = ::SQLParamData(hstmt, &ptr);  
  
      while (rc == SQL_NEED_DATA) {  
         if (ptr == (SQLPOINTER)1) {  
            // it is the TVP parameter  
            if (cRows >= cMaxRows) {  
               // We finish sending the last row already.  
               CHKRC(::SQLPutData(hstmt, NULL, 0));  
            }  
            else {  
               // Obtaining row data from somewhere. In this case we will fill 3 rows.  
               for (size_t i = 0; i < ARRAY_SIZE; i++) {  
                  llSeqNo[i] = cRows + i + 1;  
                  lSeries[i] = llSeqNo[i] * 10;  
  
                  // Now fill the varbinary(max) column.  Assume that the even row can't be fit into   
                  // the buffer provided as send them as DAE.  
                  if (!((cRows + i) % 2)) {  
                     // SQL_DATA_AT_EXEC means send DAE data.  
                     cbRestData[i] = SQL_DATA_AT_EXEC;  
                  }  
                  else {  
                     // data can fit into the buffer, then copy the data to the buffer directly.  
                     cbRestData[i] = 100;  
                     ::memset(&rgbRestData[i], 'b', cbRestData[i]);  
                  }  
               }  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)1, ARRAY_SIZE));  
               cRows += ARRAY_SIZE;  
            }  
         }  
         else if ((SQLPOINTER)&rgbRestData[0] <= ptr && ptr <= (SQLPOINTER)&rgbRestData[ARRAY_SIZE-1]) {  
            // it is varbinary(max) column  
            // Send data in parts.  
            for (int i = 0; i < 3; i++) {  
               // Obtain the data in part from somewhere, here we just set all bytes to 'a'.  
               ::memset(ptr, 'a', sizeof(rgbRestData[0]));  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)ptr, sizeof(rgbRestData[0])));  
            }  
         }  
         else {  
            // handling other DAE parameters, but in our case, we don't have other DAE parameters.  
            goto EXIT;  
         }  
         rc = ::SQLParamData(hstmt, &ptr);  
      }  
   }  
  
EXIT:  
   if (!SUCCESS(rc)) {  
      if (hstmt)   
         PrintError(SQL_HANDLE_STMT, hstmt);  
      if (hdbc)  
         PrintError(SQL_HANDLE_DBC, hdbc);  
      if(henv)  
         PrintError(SQL_HANDLE_ENV, henv);  
   }  
  
   if (hstmt)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt);  
   if (hdbc) {  
      SQLDisconnect(hdbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc);  
   }  
   if (henv)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8df2c-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8df2c-147">See Also</span></span>  
 [<span data-ttu-id="8df2c-148">Programmierbeispiele für ODBC-Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="8df2c-148">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
  
  
