---
title: Ausführen von Abfragen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC applications, executing queries
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
- SQL Server Native Client ODBC driver, queries
- queries [ODBC]
ms.assetid: d935bcba-8ce6-4159-8395-6c86431602ad
author: rothja
ms.author: jroth
ms.openlocfilehash: adc51186803148056401f58f1207d3e9a7abf9c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608617"
---
# <a name="executing-queries-odbc"></a><span data-ttu-id="dc411-102">Ausführen von Abfragen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="dc411-102">Executing Queries (ODBC)</span></span>
  <span data-ttu-id="dc411-103">Nachdem eine ODBC-Anwendung ein Verbindungshandle initialisiert und eine Verbindung zu einer Datenquelle hergestellt hat, weist sie dem Verbindungshandle ein oder mehrere Anweisungshandles zu.</span><span class="sxs-lookup"><span data-stu-id="dc411-103">After an ODBC application initializes a connection handle and connects with a data source, it allocates one or more statement handles on the connection handle.</span></span> <span data-ttu-id="dc411-104">Die Anwendung kann dann- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Anweisungen für das Anweisungs Handle ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc411-104">The application can then execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statements on the statement handle.</span></span> <span data-ttu-id="dc411-105">Die übliche Reihenfolge bei der Ausführung einer SQL-Anweisung ist:</span><span class="sxs-lookup"><span data-stu-id="dc411-105">The general sequence of events in executing an SQL statement is:</span></span>  
  
1.  <span data-ttu-id="dc411-106">Festlegen aller erforderlichen Anweisungsattribute.</span><span class="sxs-lookup"><span data-stu-id="dc411-106">Set any required statement attributes.</span></span>  
  
2.  <span data-ttu-id="dc411-107">Erstellen der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dc411-107">Construct the statement.</span></span>  
  
3.  <span data-ttu-id="dc411-108">Ausführen der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dc411-108">Execute the statement.</span></span>  
  
4.  <span data-ttu-id="dc411-109">Abrufen der Resultsets.</span><span class="sxs-lookup"><span data-stu-id="dc411-109">Retrieve any result sets.</span></span>  
  
 <span data-ttu-id="dc411-110">Erst nachdem eine Anwendung alle Zeilen in sämtlichen von der SQL-Anweisung zurückgegebenen Resultsets abgerufen hat, kann sie eine weitere Abfrage über dasselbe Anweisungshandle ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc411-110">After an application retrieves all the rows in all of the result sets returned by the SQL statement, it can execute another query on the same statement handle.</span></span> <span data-ttu-id="dc411-111">Wenn eine Anwendung ermittelt, dass es nicht erforderlich ist, alle Zeilen in einem bestimmten Resultset abzurufen, kann Sie den Rest des Resultsets durch Aufrufen von [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) oder [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md)abbrechen.</span><span class="sxs-lookup"><span data-stu-id="dc411-111">If an application determines that it is not required to retrieve all the rows in a particular result set, it can cancel the rest of the result set by calling either [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
 <span data-ttu-id="dc411-112">Wenn Sie in einer ODBC-Anwendung dieselbe SQL-Anweisung mehrfach mit unterschiedlichen Daten ausführen müssen, verwenden Sie bei der Erstellung der SQL-Anweisung eine Parametermarkierung in Form eines Fragezeichens (?):</span><span class="sxs-lookup"><span data-stu-id="dc411-112">If, in an ODBC application, you must execute the same SQL statement multiple times with different data, use a parameter marker denoted by a question mark (?) in the construction of an SQL statement:</span></span>  
  
```  
INSERT INTO MyTable VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="dc411-113">Jede Parameter Markierung kann dann durch Aufrufen von [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md)an eine Programm Variable gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="dc411-113">Each parameter marker can then be bound to a program variable by calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md).</span></span>  
  
 <span data-ttu-id="dc411-114">Nachdem alle SQL-Anweisungen ausgeführt und ihre Resultsets verarbeitet wurden, gibt die Anwendung das Anweisungshandle frei.</span><span class="sxs-lookup"><span data-stu-id="dc411-114">After all SQL statements execute and their result sets process, the application frees the statement handle.</span></span>  
  
 <span data-ttu-id="dc411-115">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt mehrere Anweisungs Handles pro Verbindungs Handle.</span><span class="sxs-lookup"><span data-stu-id="dc411-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports multiple statement handles per connection handle.</span></span> <span data-ttu-id="dc411-116">Transaktionen werden auf Verbindungsebene verwaltet, d. h. alle über sämtliche Anweisungshandles auf einem einzelnen Verbindungshandle ausgeführten Aufgaben werden als Bestandteil derselben Transaktion verwaltet.</span><span class="sxs-lookup"><span data-stu-id="dc411-116">Transactions are managed at the connection level, so that all work performed on all statement handles on a single connection handle are managed as part of the same transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc411-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dc411-117">In This Section</span></span>  
  
-   [<span data-ttu-id="dc411-118">Zuordnen eines Anweisungshandles</span><span class="sxs-lookup"><span data-stu-id="dc411-118">Allocating a Statement Handle</span></span>](allocating-a-statement-handle.md)  
  
-   [<span data-ttu-id="dc411-119">Erstellen einer SQL-Anweisung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="dc411-119">Constructing an SQL Statement &#40;ODBC&#41;</span></span>](constructing-an-sql-statement-odbc.md)  
  
-   [<span data-ttu-id="dc411-120">Erstellen von SQL-Anweisungen für Cursor</span><span class="sxs-lookup"><span data-stu-id="dc411-120">Constructing SQL Statements for Cursors</span></span>](constructing-sql-statements-for-cursors.md)  
  
-   [<span data-ttu-id="dc411-121">Verwenden von Anweisungsparametern</span><span class="sxs-lookup"><span data-stu-id="dc411-121">Using Statement Parameters</span></span>](using-statement-parameters.md)  
  
-   [<span data-ttu-id="dc411-122">Ausführen von Anweisungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="dc411-122">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements/executing-statements-odbc.md)  
  
-   [<span data-ttu-id="dc411-123">Freigeben eines Anweisungshandles</span><span class="sxs-lookup"><span data-stu-id="dc411-123">Freeing a Statement Handle</span></span>](freeing-a-statement-handle.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc411-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc411-124">See Also</span></span>  
 [<span data-ttu-id="dc411-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="dc411-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
