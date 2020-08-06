---
title: Abrufen gespeicherter Prozeduren (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], calling
ms.assetid: 31176be8-d40e-4f93-8d44-a46e804a3e2d
author: rothja
ms.author: jroth
ms.openlocfilehash: d98d623dbbb4701bb59c95df502d0063d528d0d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617936"
---
# <a name="call-stored-procedures-odbc"></a><span data-ttu-id="f1c99-102">Aufrufen von gespeicherten Prozeduren (ODBC)</span><span class="sxs-lookup"><span data-stu-id="f1c99-102">Call Stored Procedures (ODBC)</span></span>
  <span data-ttu-id="f1c99-103">Wenn eine SQL-Anweisung eine gespeicherte Prozedur mithilfe der ODBC-Aufruf-Escape-Klausel aufruft, sendet der Microsoft SQL Server Treiber die Prozedur mit dem RPC-Mechanismus (remote gespeicherte Prozedur Aufruf) an SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1c99-103">When a SQL statement calls a stored procedure using the ODBC CALL escape clause, the Microsoft SQL Server driver sends the procedure to SQL Server using the remote stored procedure call (RPC) mechanism.</span></span> <span data-ttu-id="f1c99-104">RPC-Anforderungen umgehen größtenteils das Analysieren der Anwendungen und die Parameterverarbeitung in SQL Server und sind schneller als die Transact-SQL EXECUTE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f1c99-104">RPC requests bypass much of the statement parsing and parameter processing in SQL Server and are faster than using the Transact-SQL EXECUTE statement.</span></span>  
  
 <span data-ttu-id="f1c99-105">Eine Beispielanwendung, die diese Funktion veranschaulicht, finden Sie unter [Verarbeiten von Rückgabe Codes und Ausgabeparametern &#40;ODBC-&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f1c99-105">For a sample application that demonstrates this feature, see [Process Return Codes and Output Parameters &#40;ODBC&#41;](running-stored-procedures-process-return-codes-and-output-parameters.md).</span></span>  
  
### <a name="to-run-a-procedure-as-an-rpc"></a><span data-ttu-id="f1c99-106">So führen Sie eine Prozedur als RPC aus</span><span class="sxs-lookup"><span data-stu-id="f1c99-106">To run a procedure as an RPC</span></span>  
  
1.  <span data-ttu-id="f1c99-107">Erstellen Sie eine SQL-Anweisung, die die ODBC-Escapesequenz verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1c99-107">Construct a SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="f1c99-108">Die Anweisung verwendet Parametermarkierungen für jeden Eingabe-, Eingabe/Ausgabe- und Ausgabeparameter sowie für den Prozedurrückgabewert (falls zutreffend):</span><span class="sxs-lookup"><span data-stu-id="f1c99-108">The statement uses parameter markers for each input, input/output, and output parameter, and for the procedure return value (if any):</span></span>  
  
    ```  
    {? = CALL procname (?,?)}  
    ```  
  
2.  <span data-ttu-id="f1c99-109">Rufen Sie [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) für jeden Eingabe-, Eingabe/Ausgabe- und Ausgabeparameter sowie für den Prozedurrückgabewert (sofern vorhanden) auf.</span><span class="sxs-lookup"><span data-stu-id="f1c99-109">Call [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) for each input, input/output, and output parameter, and for the procedure return value (if any).</span></span>  
  
3.  <span data-ttu-id="f1c99-110">Führen Sie die Anweisung mit [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399)aus.</span><span class="sxs-lookup"><span data-stu-id="f1c99-110">Execute the statement with [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1c99-111">Wenn eine Anwendung eine Prozedur mit der Transact-SQL EXECUTE-Syntax (statt mit der ODBC CALL-Escapesequenz) übermittelt, gibt der SQL Server ODBC-Treiber den Prozeduraufruf an SQL Server als SQL-Anweisung statt als RPC weiter.</span><span class="sxs-lookup"><span data-stu-id="f1c99-111">If an application submits a procedure using the Transact-SQL EXECUTE syntax (as opposed to the ODBC CALL escape sequence), the SQL Server ODBC driver passes the procedure call to SQL Server as a SQL statement rather than as an RPC.</span></span> <span data-ttu-id="f1c99-112">Darüber hinaus werden Ausgabeparameter nicht zurückgegeben, wenn die Transact SQL EXECUTE-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1c99-112">Also, output parameters are not returned if the Transact-SQL EXECUTE statement is used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c99-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1c99-113">See Also</span></span>  
 <span data-ttu-id="f1c99-114">[Gewusst-wie-Themen zur Ausführung gespeicherter Prozeduren &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="f1c99-114">[Running Stored Procedures How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md) </span></span>  
 <span data-ttu-id="f1c99-115">[Batch Verarbeitung von gespeicherten Prozedur aufrufen](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span><span class="sxs-lookup"><span data-stu-id="f1c99-115">[Batching Stored Procedure Calls](../native-client-odbc-stored-procedures/batching-stored-procedure-calls.md) </span></span>  
 <span data-ttu-id="f1c99-116">[Gespeicherte Prozeduren](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f1c99-116">[Running Stored Procedures](../native-client-odbc-stored-procedures/running-stored-procedures.md) </span></span>  
 <span data-ttu-id="f1c99-117">[Aufrufen einer gespeicherten Prozedur](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f1c99-117">[Calling a Stored Procedure](../native-client-odbc-stored-procedures/calling-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="f1c99-118">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f1c99-118">Procedures</span></span>](../native-client-odbc-queries/executing-statements/procedures.md)  
  
  
