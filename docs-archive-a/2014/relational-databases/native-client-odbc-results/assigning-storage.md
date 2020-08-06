---
title: Zuweisen von Speicher | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- column-wise binding [ODBC]
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLBindCol function
- storing data [ODBC]
- result sets [ODBC], storage
- SQL Server Native Client ODBC driver, data storage
- row-wise binding
- binding result sets [SQL Server Native Client]
- array binding
ms.assetid: 11c81955-5300-495f-925f-9256f2587b58
author: rothja
ms.author: jroth
ms.openlocfilehash: ada18c91493d91b36ced51bf84c32513a0c5f5df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620317"
---
# <a name="assigning-storage"></a><span data-ttu-id="18bed-102">Zuweisen von Speicher</span><span class="sxs-lookup"><span data-stu-id="18bed-102">Assigning Storage</span></span>
  <span data-ttu-id="18bed-103">Eine Anwendung kann vor oder nach der Ausführung einer SQL-Anweisung Speicher für Ergebnisse zuweisen.</span><span class="sxs-lookup"><span data-stu-id="18bed-103">An application can assign storage for results before or after it executes a SQL statement.</span></span> <span data-ttu-id="18bed-104">Wenn eine Anwendung die SQL-Anweisung zum ersten Mal vorbereitet oder ausführt, kann sie Informationen zum Resultset einholen, bevor sie Speicher für die Ergebnisse zuweist.</span><span class="sxs-lookup"><span data-stu-id="18bed-104">If an application prepares or executes the SQL statement first, it can inquire about the result set before it assigns storage for results.</span></span> <span data-ttu-id="18bed-105">Wenn das Resultset beispielsweise unbekannt ist, muss die Anwendung die Anzahl der Spalten abrufen, bevor sie diesen Speicher zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="18bed-105">For example, if the result set is unknown, the application must retrieve the number of columns before it can assign storage for them.</span></span>  
  
 <span data-ttu-id="18bed-106">Um Speicher für eine Datenspalte zuzuordnen, ruft eine Anwendung [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)auf und übergibt Sie:</span><span class="sxs-lookup"><span data-stu-id="18bed-106">To associate storage for a column of data, an application calls [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)and passes it:</span></span>  
  
-   <span data-ttu-id="18bed-107">Den Datentyp, in den die Daten konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18bed-107">The data type to which the data is to be converted.</span></span>  
  
-   <span data-ttu-id="18bed-108">Die Adresse eines Ausgabepuffers für die Daten.</span><span class="sxs-lookup"><span data-stu-id="18bed-108">The address of an output buffer for the data.</span></span>  
  
     <span data-ttu-id="18bed-109">Die Anwendung muss Speicher für diesen Puffer zuweisen, und der Puffer muss so groß sein, dass die Daten in dem Format, in das sie konvertiert werden sollen, darin Platz finden.</span><span class="sxs-lookup"><span data-stu-id="18bed-109">The application must allocate this buffer, and it must be large enough to hold the data in the form to which it is converted.</span></span>  
  
-   <span data-ttu-id="18bed-110">Die Länge des Ausgabepuffers.</span><span class="sxs-lookup"><span data-stu-id="18bed-110">The length of the output buffer.</span></span>  
  
     <span data-ttu-id="18bed-111">Dieser Wert wird ignoriert, wenn die zurückgegebenen Daten über eine feste Breite in C verfügen, z. B. eine ganze Zahl, reelle Zahl oder Datumsstruktur.</span><span class="sxs-lookup"><span data-stu-id="18bed-111">This value is ignored if the returned data has a fixed width in C, such as an integer, real number, or date structure.</span></span>  
  
-   <span data-ttu-id="18bed-112">Die Adresse eines Speicherpuffers, in den die Anzahl von Bytes verfügbarer Daten zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="18bed-112">The address of a storage buffer in which to return the number of bytes of available data.</span></span>  
  
 <span data-ttu-id="18bed-113">Eine Anwendung kann auch Resultsetspalten an Arrays von Programmvariablen binden, um das Abrufen von Resultsetzeilen in Blöcken zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="18bed-113">An application can also bind result set columns to arrays of program variables to support fetching result set rows in blocks.</span></span> <span data-ttu-id="18bed-114">Es gibt zwei verschiedene Arten der Arraybindung:</span><span class="sxs-lookup"><span data-stu-id="18bed-114">There are two different types of array binding:</span></span>  
  
-   <span data-ttu-id="18bed-115">Die spaltenweise Bindung ist fertig gestellt, wenn jede Spalte an sein eigenes Array von Variablen gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="18bed-115">Column-wise binding is finished when each column is bound to its own array of variables.</span></span>  
  
     <span data-ttu-id="18bed-116">Die spaltenweise Bindung wird angegeben, indem [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) aufgerufen wird, wobei *Attribute* auf SQL_ATTR_ROW_BIND_TYPE und *ValuePtr* auf SQL_BIND_BY_COLUMN festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18bed-116">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to SQL_BIND_BY_COLUMN.</span></span> <span data-ttu-id="18bed-117">Alle Arrays müssen über die gleiche Anzahl von Elementen verfügen.</span><span class="sxs-lookup"><span data-stu-id="18bed-117">All the arrays must have the same number of elements.</span></span>  
  
-   <span data-ttu-id="18bed-118">Die zeilenweise Bindung ist fertig gestellt, wenn alle Parameter in der SQL-Anweisung als Einheit an ein Array von Strukturen gebunden wurden, die die einzelnen Variablen für die Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="18bed-118">Row-wise binding is finished when all the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>  
  
     <span data-ttu-id="18bed-119">Die zeilenweise Bindung wird angegeben, indem **SQLSetStmtAttr** aufgerufen wird, wobei *Attribute* auf SQL_ATTR_ROW_BIND_TYPE festgelegt ist und *ValuePtr* auf die Größe der Struktur festgelegt ist, die die Variablen enthält, die die Resultsetspalten empfangen.</span><span class="sxs-lookup"><span data-stu-id="18bed-119">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_ROW_BIND_TYPE and *ValuePtr* set to the size of the structure holding the variables that will receive the result set columns.</span></span>  
  
 <span data-ttu-id="18bed-120">Die Anwendung legt zudem SQL_ATTR_ROW_ARRAY_SIZE auf die Anzahl der Elemente im Spalten- oder Zeilenarray sowie SQL_ATTR_ROW_STATUS_PTR und SQL_ATTR_ROWS_FETCHED_PTR fest.</span><span class="sxs-lookup"><span data-stu-id="18bed-120">The application also sets SQL_ATTR_ROW_ARRAY_SIZE to the number of elements in the column or row arrays and sets SQL_ATTR_ROW_STATUS_PTR and SQL_ATTR_ROWS_FETCHED_PTR.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bed-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18bed-121">See Also</span></span>  
 [<span data-ttu-id="18bed-122">Verarbeitungsergebnisse &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="18bed-122">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
