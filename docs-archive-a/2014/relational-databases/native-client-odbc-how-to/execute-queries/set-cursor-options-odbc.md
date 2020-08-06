---
title: Festlegen von Cursor Optionen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], options
ms.assetid: 0e72b48a-fc5a-4656-8cf5-39f57d8c1565
author: rothja
ms.author: jroth
ms.openlocfilehash: 877c2596c87ce50295a15912493661c6dd4e0305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723806"
---
# <a name="set-cursor-options-odbc"></a><span data-ttu-id="e8bdc-102">Festlegen von Cursoroptionen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e8bdc-102">Set Cursor Options (ODBC)</span></span>
  <span data-ttu-id="e8bdc-103">Um Cursor Optionen festzulegen, müssen Sie [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) aufrufen, um oder [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) festzulegen, um die Anweisungs Optionen zu erhalten, die das Cursor Verhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-103">To set cursor options, Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get the statement options that control cursor behavior.</span></span>  
  
|<span data-ttu-id="e8bdc-104">*Attribut*</span><span class="sxs-lookup"><span data-stu-id="e8bdc-104">*Attribute*</span></span>|<span data-ttu-id="e8bdc-105">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="e8bdc-105">Specifies</span></span>|  
|-----------------|---------------|  
|<span data-ttu-id="e8bdc-106">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="e8bdc-106">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="e8bdc-107">Cursortyp, der einen Vorwärtscursor, einen statischen, dynamischen oder keyset-gesteuerten Cursor bezeichnen kann</span><span class="sxs-lookup"><span data-stu-id="e8bdc-107">Cursor type of forward-only, static, dynamic, or keyset-driven</span></span>|  
|<span data-ttu-id="e8bdc-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="e8bdc-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="e8bdc-109">Option zur Steuerung der gleichzeitigen Ausführung, die Schreibschutz, Sperren, vollständige Parallelität mit Timestamps oder vollständige Parallelität mit Werten angeben kann</span><span class="sxs-lookup"><span data-stu-id="e8bdc-109">Concurrency control option of read-only, locking, optimistic using timestamps, or optimistic using values</span></span>|  
|<span data-ttu-id="e8bdc-110">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="e8bdc-110">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="e8bdc-111">Anzahl der Zeilen, die mit jedem Abrufvorgang abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="e8bdc-111">Number of rows retrieved in each fetch</span></span>|  
|<span data-ttu-id="e8bdc-112">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="e8bdc-112">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="e8bdc-113">Cursor, der Cursorupdates, die von anderen Verbindungen an Cursorzeilen vorgenommen wurden, anzeigt oder nicht anzeigt</span><span class="sxs-lookup"><span data-stu-id="e8bdc-113">Cursor that does or does not show updates to cursor rows made by other connections</span></span>|  
|<span data-ttu-id="e8bdc-114">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="e8bdc-114">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="e8bdc-115">Cursor, mit denen sowohl ein Vorwärts- als auch ein Rückwärtsbildlauf ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="e8bdc-115">Cursor that can be scrolled forward and backward</span></span>|  
  
 <span data-ttu-id="e8bdc-116">Bei Verwendung der Standardwerte dieser Attribute (forward-only, read-only, Rowsetgröße von 1) werden keine Servercursor verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-116">The default values for these attributes (forward-only, read-only, rowset size of 1) do not use server cursors.</span></span> <span data-ttu-id="e8bdc-117">Die Verwendung von Servercursorn setzt voraus, dass mindestens eines dieser Attribute auf einen anderen Wert als den Standardwert festgelegt wird und dass es sich bei der auszuführenden Anweisungen um eine einzelne SELECT-Anweisung oder eine gespeicherte Prozedur handelt, die eine einzelne SELECT-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-117">To use server cursors, at least one of these attributes must be set to a value other than the default, and the statement being executed must be a single SELECT statement or a stored procedure that contains a single SELECT statement.</span></span> <span data-ttu-id="e8bdc-118">Beim Einsatz von Servercursorn können in SELECT-Anweisungen keine Klauseln angegeben werden, die von den Servercursorn nicht unterstützt werden: COMPUTE, COMPUTE BY, FOR BROWSE und INTO.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-118">When using server cursors, SELECT statements cannot use clauses not supported by server cursors: COMPUTE, COMPUTE BY, FOR BROWSE, and INTO.</span></span>  
  
 <span data-ttu-id="e8bdc-119">Sie können den Typ des verwendeten Cursors entweder durch Festlegen von SQL_ATTR_CURSOR_TYPE und SQL_ATTR_CONCURRENCY oder durch Festlegen von SQL_ATTR_CURSOR_SENSITIVITY und SQL_ATTR_CURSOR_SCROLLABLE steuern.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-119">You can control the type of cursor used either by setting SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="e8bdc-120">Sie sollten die zwei Methoden zur Angabe des Cursorverhaltens nicht kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-120">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8bdc-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8bdc-121">Example</span></span>  
 <span data-ttu-id="e8bdc-122">Im folgenden Beispiel werden ein Anweisungshandle zugeordnet, ein dynamischer Cursortyp mit vollständiger Parallelität mit Zeilenversionsverwaltung festgelegt und anschließend eine SELECT-Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-122">The following sample allocates a statement handle, sets a dynamic cursor type with row versioning optimistic concurrency, and then executes a SELECT.</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_TYPE, (SQLPOINTER)SQL_CURSOR_DYNAMIC, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CONCURRENCY, SQLPOINTER)SQL_CONCUR_ROWVER, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, SELECT au_lname FROM authors", SQL_NTS);  
```  
  
## <a name="example"></a><span data-ttu-id="e8bdc-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8bdc-123">Example</span></span>  
 <span data-ttu-id="e8bdc-124">Im folgenden Beispiel werden ein Anweisungshandle zugeordnet, ein bildlauffähiger Sensitivcursor festgelegt und anschließend eine SELECT-Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8bdc-124">The following sample allocates a statement handle, sets a scrollable, sensitive cursor, and then executes a SELECT</span></span>  
  
```  
retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
  
// Set the cursor options and execute the statement.  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SCROLLABLE, SQLPOINTER)SQL_SCROLLABLE, SQL_IS_INTEGER);  
retcode = SQLSetStmtAttr(hstmt1, SQL_ATTR_CURSOR_SENSITIVITY, SQLPOINTER)SQL_INSENSITIVE, SQL_IS_INTEGER);  
retcode = SQLExecDirect(hstmt1, select au_lname from authors", SQL_NTS);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8bdc-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8bdc-125">See Also</span></span>  
 [<span data-ttu-id="e8bdc-126">Gewusst-wie-Themen zum Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="e8bdc-126">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
