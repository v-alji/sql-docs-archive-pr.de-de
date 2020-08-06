---
title: Abrufen und Aktualisieren von Rowsets (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [ODBC]
ms.assetid: cf0eb3b4-8b72-49fc-a845-95edc360cf93
author: rothja
ms.author: jroth
ms.openlocfilehash: e09a3033e0883452ecd69b82c9375ed28c920da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607733"
---
# <a name="fetch-and-update-rowsets-odbc"></a><span data-ttu-id="8b355-102">Abfragen und Aktualisieren von Rowsets (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8b355-102">Fetch and Update Rowsets (ODBC)</span></span>
    
### <a name="to-fetch-and-update-rowsets"></a><span data-ttu-id="8b355-103">So können Sie Rowsets abfragen und aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8b355-103">To fetch and update rowsets</span></span>  
  
1.  <span data-ttu-id="8b355-104">Optional können Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) mit SQL_ROW_ARRAY_SIZE aufrufen, um die Anzahl der Zeilen (R) im Rowset zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8b355-104">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) with SQL_ROW_ARRAY_SIZE to change the number of rows (R) in the rowset.</span></span>  
  
2.  <span data-ttu-id="8b355-105">Rufen Sie [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) oder [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) auf, um ein Rowset abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8b355-105">Call [SQLFetch](https://go.microsoft.com/fwlink/?LinkId=58401) or [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md) to get a rowset.</span></span>  
  
3.  <span data-ttu-id="8b355-106">Bei der Verwendung von gebundenen Spalten verwenden Sie die Datenwerte und Datenlängen, die nun in den Puffern mit gebundenen Spalten für das Rowset verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8b355-106">If bound columns are used, use the data values and data lengths now available in the bound column buffers for the rowset.</span></span>  
  
     <span data-ttu-id="8b355-107">Bei der Verwendung von ungebundenen Spalten rufen Sie für jede Zeile [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) mit SQL_POSITION auf, um die Cursorposition festzulegen. Gehen Sie anschließend bei jeder ungebundenen Spalte wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8b355-107">If unbound columns are used, for each row call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) with SQL_POSITION to set the cursor position; then, for each unbound column:</span></span>  
  
    -   <span data-ttu-id="8b355-108">Rufen Sie [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) einmal oder mehrere Male auf, um die Daten für ungebundene Spalten nach der letzten gebundenen Spalte des Rowsets abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8b355-108">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) one or more times to get the data for unbound columns after the last bound column of the rowset.</span></span> <span data-ttu-id="8b355-109">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) muss in zunehmender Spaltenzahlfolge aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8b355-109">Calls to [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) should be in order of increasing column number.</span></span>  
  
    -   <span data-ttu-id="8b355-110">Rufen Sie [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) mehrere Male auf, um Daten aus einer text- oder image-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8b355-110">Call [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) multiple times to get data from a text or image column.</span></span>  
  
4.  <span data-ttu-id="8b355-111">Richten Sie alle Data-at-Execution-text- oder Data-at-Execution-image-Spalten ein.</span><span class="sxs-lookup"><span data-stu-id="8b355-111">Set up any data-at-execution text or image columns.</span></span>  
  
5.  <span data-ttu-id="8b355-112">Rufen Sie [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) oder [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) auf, um die Cursorposition festzulegen und Zeilen im Rowset zu aktualisieren, zu löschen oder hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8b355-112">Call [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) or [SQLBulkOperations](https://go.microsoft.com/fwlink/?LinkId=58398) to set the cursor position, refresh, update, delete, or add row(s) within the rowset.</span></span>  
  
     <span data-ttu-id="8b355-113">Data-at-Execution-text- oder Data-at-Execution-image-Spalten, die zum Aktualisieren oder Hinzufügen verwendet werden, müssen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8b355-113">If data-at-execution text or image columns are used for an update or add operation, handle them.</span></span>  
  
6.  <span data-ttu-id="8b355-114">Sie können eine positionierte UPDATE- oder DELETE-Anweisung ausführen und dabei den Cursornamen angeben (über [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)abrufbar) und für dieselbe Verbindung ein anderes Anweisungshandle verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b355-114">Optionally, execute a positioned UPDATE or DELETE statement, specifying the cursor name (available from [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md)) and using a different statement handle on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b355-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b355-115">See Also</span></span>  
 [<span data-ttu-id="8b355-116">Gewusst-wie-Themen zur Verwendung von Cursorn &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="8b355-116">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
