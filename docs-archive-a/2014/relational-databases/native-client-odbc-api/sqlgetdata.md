---
title: SQLGetData | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607745"
---
# <a name="sqlgetdata"></a><span data-ttu-id="ed64f-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="ed64f-102">SQLGetData</span></span>
  <span data-ttu-id="ed64f-103">**SQLGetData** wird zum Abrufen von Resultsetdaten ohne Bindungs Spaltenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed64f-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="ed64f-104">**SQLGetData** kann in derselben Spalte nacheinander aufgerufen werden, um große Datenmengen aus einer Spalte mit einem Datentyp vom Typ **Text**, **ntext**oder **Image** abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ed64f-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="ed64f-105">Es wird nicht vorausgesetzt, dass eine Anwendung Variablen binden muss, um Resultsetdaten abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="ed64f-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="ed64f-106">Die Daten einer beliebigen Spalte können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von **SQLGetData**vom ODBC-Treiber von Native Client abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed64f-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="ed64f-107">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt nicht die Verwendung von **SQLGetData** , um Daten in der Reihenfolge der Zufalls Spalten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ed64f-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="ed64f-108">Alle ungebundenen Spalten, die mit **SQLGetData** verarbeitet werden, müssen höhere Spalten ordinale aufweisen als die gebundenen Spalten im Resultset.</span><span class="sxs-lookup"><span data-stu-id="ed64f-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="ed64f-109">Die Anwendung muss die Daten vom niedrigsten nicht gebundenen ordinalen Spaltenwert zum höchsten Spaltenwert verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed64f-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="ed64f-110">Der Versuch, Daten aus einer Spalte mit einer niedrigeren Ordnungszahl abzurufen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed64f-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="ed64f-111">Wenn die Anwendung Servercursor zur Ausgabe von Resultsetzeilen verwendet, kann die Anwendung erneut die aktuelle Zeile abrufen und dann den Wert einer Spalte abrufen.</span><span class="sxs-lookup"><span data-stu-id="ed64f-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="ed64f-112">Wenn eine-Anweisung für den standardmäßigen schreibgeschützten Vorwärts Cursor ausgeführt wird, müssen Sie die-Anweisung erneut ausführen, um **SQLGetData**zu sichern.</span><span class="sxs-lookup"><span data-stu-id="ed64f-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="ed64f-113">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber meldet genau die Länge von **Text**-, **ntext**-und **Image** -Daten, die mithilfe von **SQLGetData**abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="ed64f-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="ed64f-114">Die Anwendung kann die *StrLen_or_IndPtr* Parameter Rückgabe nutzen, um lange Daten schnell abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ed64f-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed64f-115">Bei Typen mit großen Werten werden *StrLen_or_IndPtr* bei der Daten abkürzen SQL_NO_TOTAL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ed64f-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="ed64f-116">SQLGetData-Unterstützung für verbesserte Funktionen für Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ed64f-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="ed64f-117">Ergebnis Spaltenwerte von Datums-/Uhrzeittypen werden wie in [Konvertierungen von SQL in C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md)beschrieben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ed64f-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="ed64f-118">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="ed64f-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="ed64f-119">SQLGetData-Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="ed64f-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="ed64f-120">**SQLGetData** unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="ed64f-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="ed64f-121">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="ed64f-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed64f-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed64f-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed64f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed64f-123">See Also</span></span>  
 <span data-ttu-id="ed64f-124">[SQLGetData-Funktion](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="ed64f-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="ed64f-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="ed64f-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
