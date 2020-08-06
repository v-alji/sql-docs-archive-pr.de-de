---
title: Erstellen von SQL-Anweisungen für Cursor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], statement construction
- ODBC applications, cursors
- SQL Server Native Client ODBC driver, statements
- statements [ODBC], constructing
- ODBC applications, statements
- statements [ODBC], cursors
ms.assetid: 134003fd-9c93-4f5c-a988-045990933b80
author: rothja
ms.author: jroth
ms.openlocfilehash: b0fe0831b97c13c5d20067386f4e9d8c97ee19ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608619"
---
# <a name="constructing-sql-statements-for-cursors"></a><span data-ttu-id="eda53-102">Erstellen von SQL-Anweisungen für Cursor</span><span class="sxs-lookup"><span data-stu-id="eda53-102">Constructing SQL Statements for Cursors</span></span>
  <span data-ttu-id="eda53-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber verwendet Server Cursor, um die in der ODBC-Spezifikation definierte Cursor Funktion zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="eda53-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses server cursors to implement the cursor functionality defined in the ODBC specification.</span></span> <span data-ttu-id="eda53-104">Eine ODBC-Anwendung steuert das Cursor Verhalten, indem [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) verwendet wird, um unterschiedliche Anweisungs Attribute festzulegen.</span><span class="sxs-lookup"><span data-stu-id="eda53-104">An ODBC application controls the cursor behavior by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) to set different statement attributes.</span></span> <span data-ttu-id="eda53-105">Nachfolgend sind die Attribute und ihre Standardwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eda53-105">These are the attributes and their defaults.</span></span>  
  
|<span data-ttu-id="eda53-106">attribute</span><span class="sxs-lookup"><span data-stu-id="eda53-106">Attribute</span></span>|<span data-ttu-id="eda53-107">Standard</span><span class="sxs-lookup"><span data-stu-id="eda53-107">Default</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="eda53-108">SQL_ATTR_CONCURRENCY</span><span class="sxs-lookup"><span data-stu-id="eda53-108">SQL_ATTR_CONCURRENCY</span></span>|<span data-ttu-id="eda53-109">SQL_CONCUR_READ_ONLY</span><span class="sxs-lookup"><span data-stu-id="eda53-109">SQL_CONCUR_READ_ONLY</span></span>|  
|<span data-ttu-id="eda53-110">SQL_ATTR_CURSOR_TYPE</span><span class="sxs-lookup"><span data-stu-id="eda53-110">SQL_ATTR_CURSOR_TYPE</span></span>|<span data-ttu-id="eda53-111">SQL_CURSOR_FORWARD_ONLY</span><span class="sxs-lookup"><span data-stu-id="eda53-111">SQL_CURSOR_FORWARD_ONLY</span></span>|  
|<span data-ttu-id="eda53-112">SQL_ATTR_CURSOR_SCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="eda53-112">SQL_ATTR_CURSOR_SCROLLABLE</span></span>|<span data-ttu-id="eda53-113">SQL_NONSCROLLABLE</span><span class="sxs-lookup"><span data-stu-id="eda53-113">SQL_NONSCROLLABLE</span></span>|  
|<span data-ttu-id="eda53-114">SQL_ATTR_CURSOR_SENSITIVITY</span><span class="sxs-lookup"><span data-stu-id="eda53-114">SQL_ATTR_CURSOR_SENSITIVITY</span></span>|<span data-ttu-id="eda53-115">SQL_UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="eda53-115">SQL_UNSPECIFIED</span></span>|  
|<span data-ttu-id="eda53-116">SQL_ATTR_ROW_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="eda53-116">SQL_ATTR_ROW_ARRAY_SIZE</span></span>|<span data-ttu-id="eda53-117">1</span><span class="sxs-lookup"><span data-stu-id="eda53-117">1</span></span>|  
  
 <span data-ttu-id="eda53-118">Wenn diese Optionen zum Zeitpunkt der Ausführung einer SQL-Anweisung auf ihre Standardwerte festgelegt sind, verwendet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber keinen Server Cursor zur Implementierung des Resultsets. stattdessen wird ein Standardresultset verwendet.</span><span class="sxs-lookup"><span data-stu-id="eda53-118">When these options are set to their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not use a server cursor to implement the result set; instead, it uses a default result set.</span></span> <span data-ttu-id="eda53-119">Wenn eine dieser Optionen zum Zeitpunkt der Ausführung einer SQL-Anweisung aus ihren Standardeinstellungen geändert wird, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versucht der Native Client ODBC-Treiber, das Resultset mithilfe eines Server Cursors zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="eda53-119">If any of these options are changed from their defaults at the time an SQL statement is executed, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver attempts to use a server cursor to implement the result set.</span></span>  
  
 <span data-ttu-id="eda53-120">Standardresultsets unterstützen alle [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="eda53-120">Default result sets support all of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="eda53-121">Es gibt keine Einschränkungen hinsichtlich der Arten von SQL-Anweisungen, die bei Verwendung eines Standardresultsets ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="eda53-121">There are no restrictions on the types of SQL statements that can be executed when using a default result set.</span></span>  
  
 <span data-ttu-id="eda53-122">Nicht alle [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen werden von Servercursorn unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eda53-122">Server cursors do not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="eda53-123">Servercursor unterstützen keine SQL-Anweisungen, die mehrere Resultsets generieren.</span><span class="sxs-lookup"><span data-stu-id="eda53-123">Server cursors do not support any SQL statement that generates multiple result sets.</span></span>  
  
 <span data-ttu-id="eda53-124">Die folgenden Typen von Anweisungen werden von Serversursorn nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="eda53-124">The following types of statements are not supported by server cursors:</span></span>  
  
-   <span data-ttu-id="eda53-125">Batches</span><span class="sxs-lookup"><span data-stu-id="eda53-125">Batches</span></span>  
  
     <span data-ttu-id="eda53-126">Aus zwei oder mehr einzelnen SQL SELECT-Anweisungen erstellte SQL-Anweisungen, Beispiel.:</span><span class="sxs-lookup"><span data-stu-id="eda53-126">SQL statements built from two or more individual SQL SELECT statements, for example:</span></span>  
  
    ```  
    SELECT * FROM Authors; SELECT * FROM Titles  
    ```  
  
-   <span data-ttu-id="eda53-127">Gespeicherte Prozeduren mit mehreren SELECT-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="eda53-127">Stored procedures with multiple SELECT statements</span></span>  
  
     <span data-ttu-id="eda53-128">SQL-Anweisungen, die eine gespeicherte Prozedur ausführen, die mehr als eine SELECT-Anweisung enthält</span><span class="sxs-lookup"><span data-stu-id="eda53-128">SQL statements that execute a stored procedure containing more than one SELECT statement.</span></span> <span data-ttu-id="eda53-129">Hierzu gehören auch SELECT-Anweisungen, mit denen Parameter- oder Variablenwerte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eda53-129">This includes SELECT statements that fill parameters or variables.</span></span>  
  
-   <span data-ttu-id="eda53-130">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="eda53-130">Keywords</span></span>  
  
     <span data-ttu-id="eda53-131">SQL-Anweisungen, die die Schlüsselwörter FOR BROWSE oder INTO enthalten.</span><span class="sxs-lookup"><span data-stu-id="eda53-131">SQL statements containing the keywords FOR BROWSE, or INTO.</span></span>  
  
 <span data-ttu-id="eda53-132">Wenn in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine SQL-Anweisung ausgeführt wird, die eine dieser Bedingungen erfüllt, dann wird der Servercursor implizit in ein Standardresultset konvertiert.</span><span class="sxs-lookup"><span data-stu-id="eda53-132">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if an SQL statement that matches any of these conditions is executed with a server cursor, the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="eda53-133">Nachdem **SQLExecDirect** oder **SQLExecute** SQL_SUCCESS_WITH_INFO zurückgegeben hat, werden die Cursor Attribute auf ihre Standardeinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="eda53-133">After **SQLExecDirect** or **SQLExecute** returns SQL_SUCCESS_WITH_INFO, the cursor attributes will be set back to their default settings.</span></span>  
  
 <span data-ttu-id="eda53-134">SQL-Anweisungen, die nicht in die oben genannten Kategorien passen, können mit beliebigen Anweisungsattributeinstelllungen ausgeführt werden. Sie funktionieren sowohl mit einem Standardresultset als auch einem Servercursor gleich gut.</span><span class="sxs-lookup"><span data-stu-id="eda53-134">SQL statements that do not fit the categories above can be executed with any statement attribute settings; they work equally well with either a default result set or a server cursor.</span></span>  
  
## <a name="errors"></a><span data-ttu-id="eda53-135">Errors</span><span class="sxs-lookup"><span data-stu-id="eda53-135">Errors</span></span>  
 <span data-ttu-id="eda53-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 und höher führt der Versuch, eine Anweisung auszuführen, die mehrere Resultsets erzeugt, zur Ausgabe von SQL_SUCCESS_WITH INFO und der folgenden Meldung:</span><span class="sxs-lookup"><span data-stu-id="eda53-136">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 and later, an attempt to execute a statement that produces multiple result sets generates SQL_SUCCESS_WITH INFO and the following message:</span></span>  
  
```  
SqlState: 01S02"  
pfNative: 0  
szErrorMsgString: "[Microsoft][SQL Server Native Client][SQL Server]  
               Cursor type changed."  
```  
  
 <span data-ttu-id="eda53-137">ODBC-Anwendungen, die diese Nachricht empfangen, können [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) aufrufen, um die aktuellen Cursor Einstellungen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="eda53-137">ODBC applications receiving this message can call [SQLGetStmtAttr](../native-client-odbc-api/sqlgetstmtattr.md) to determine the current cursor settings.</span></span>  
  
 <span data-ttu-id="eda53-138">Der Versuch, bei Verwendung von Servercursorn eine Prozedur mit mehreren SELECT-Anweisungen auszuführen, erzeugt folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="eda53-138">An attempt to execute a procedure with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16937  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               A server cursor is not allowed on a stored procedure  
               with more than one SELECT statement in it. Use a  
               default result set or client cursor.  
```  
  
 <span data-ttu-id="eda53-139">Der Versuch, bei Verwendung von Servercursorn einen Batch mit mehreren SELECT-Anweisungen auszuführen, erzeugt folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="eda53-139">An attempt to execute a batch with multiple SELECT statements when using server cursors generates the following error:</span></span>  
  
```  
SqlState: 42000  
pfNative: 16938  
szErrorMsgString: [Microsoft][SQL Server Native Client][SQL Server]  
               sp_cursoropen. The statement parameter can only  
               be a single SELECT statement or a single stored   
               procedure.  
```  
  
 <span data-ttu-id="eda53-140">ODBC-Anwendungen, die diese Fehler erhalten, müssen alle Cursoranweisungsattribute auf die jeweilige Standardeinstellung zurücksetzen, bevor sie die Anweisung auszuführen versuchen.</span><span class="sxs-lookup"><span data-stu-id="eda53-140">ODBC applications receiving these errors must reset all the cursor statement attributes to their defaults before attempting to execute the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda53-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eda53-141">See Also</span></span>  
 [<span data-ttu-id="eda53-142">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="eda53-142">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
