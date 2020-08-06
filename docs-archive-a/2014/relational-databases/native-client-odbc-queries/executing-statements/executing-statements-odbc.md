---
title: Ausführen von Anweisungen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, statements
- statements [ODBC]
- ODBC applications, statements
- statements [ODBC], executing
ms.assetid: 063fc40d-ff81-490d-9c9b-2faefb729f37
author: rothja
ms.author: jroth
ms.openlocfilehash: 3066a09cb1f5e63105ca3ffe2441f19e4bbe0101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608611"
---
# <a name="executing-statements-odbc"></a><span data-ttu-id="5b00a-102">Ausführen von Anweisungen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5b00a-102">Executing Statements (ODBC)</span></span>
  <span data-ttu-id="5b00a-103">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber bietet eine Vielzahl von Möglichkeiten zum Ausführen von SQL-Anweisungen in einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Datenbank:</span><span class="sxs-lookup"><span data-stu-id="5b00a-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver offers a variety ways to execute SQL statements in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database:</span></span>  
  
-   <span data-ttu-id="5b00a-104">Direkte Ausführung</span><span class="sxs-lookup"><span data-stu-id="5b00a-104">Direct execution</span></span>  
  
-   <span data-ttu-id="5b00a-105">Vorbereitete Ausführung</span><span class="sxs-lookup"><span data-stu-id="5b00a-105">Prepared execution</span></span>  
  
 <span data-ttu-id="5b00a-106">Die direkte Ausführung umfasst die Verwendung einer Zeichenfolge, [!INCLUDE[tsql](../../../includes/tsql-md.md)] die eine-Anweisung enthält, und die Übermittlung mit der **SQLExecDirect** -Funktion zur Ausführung.</span><span class="sxs-lookup"><span data-stu-id="5b00a-106">Direct execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and submitting it for execution using the **SQLExecDirect** function.</span></span> <span data-ttu-id="5b00a-107">Die vorbereitete Ausführung erfordert die Bildung einer Zeichenfolge, die eine [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisung enthält, und die Ausführung dieser Anweisung in zwei Phasen.</span><span class="sxs-lookup"><span data-stu-id="5b00a-107">Prepared execution involves building a character string containing a [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement and then executing it in two stages.</span></span> <span data-ttu-id="5b00a-108">In der ersten Phase wird die [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360) verwendet, um den Ausführungsplan für die Anweisung im zu analysieren und zu kompilieren [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b00a-108">The first stage uses the [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) function to parse and compile the execution plan for the statement in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="5b00a-109">In der zweiten Phase wird die **SQLExecute** -Funktion verwendet, um den zuvor vorbereiteten Ausführungsplan auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5b00a-109">The second stage uses the **SQLExecute** function to execute the previously prepared execution plan.</span></span> <span data-ttu-id="5b00a-110">Dadurch wird bei jeder Ausführung der mit der Analyse und Kompilierung verbundene Aufwand reduziert.</span><span class="sxs-lookup"><span data-stu-id="5b00a-110">This saves the parsing and compiling overhead on each execution.</span></span> <span data-ttu-id="5b00a-111">Die vorbereitete Ausführung wird in Anwendungen häufig verwendet, um dieselbe parametrisierte SQL-Anweisung mehrfach auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5b00a-111">Prepared execution is commonly used by applications to repeatedly execute the same, parameterized SQL statement.</span></span>  
  
 <span data-ttu-id="5b00a-112">Sowohl bei der direkten als auch bei der vorbereiteten Ausführung können einzelne [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen oder Batches von SQL-Anweisungen ausgeführt oder gespeicherte Prozeduren aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5b00a-112">Both direct and prepared execution can execute a single [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement or a batch of SQL statements, or they can call a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b00a-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5b00a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="5b00a-114">Direkte Ausführung</span><span class="sxs-lookup"><span data-stu-id="5b00a-114">Direct Execution</span></span>](direct-execution.md)  
  
-   [<span data-ttu-id="5b00a-115">Vorbereitete Ausführung</span><span class="sxs-lookup"><span data-stu-id="5b00a-115">Prepared Execution</span></span>](prepared-execution.md)  
  
-   [<span data-ttu-id="5b00a-116">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5b00a-116">Procedures</span></span>](procedures.md)  
  
-   [<span data-ttu-id="5b00a-117">Batches von Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5b00a-117">Batches of Statements</span></span>](batches-of-statements.md)  
  
-   [<span data-ttu-id="5b00a-118">Effekte von ISO-Optionen</span><span class="sxs-lookup"><span data-stu-id="5b00a-118">Effects of ISO Options</span></span>](effects-of-iso-options.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b00a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b00a-119">See Also</span></span>  
 [<span data-ttu-id="5b00a-120">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="5b00a-120">Executing Queries &#40;ODBC&#41;</span></span>](../executing-queries-odbc.md)  
  
  
