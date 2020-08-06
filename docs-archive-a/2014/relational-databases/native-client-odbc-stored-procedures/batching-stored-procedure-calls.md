---
title: Batch Verarbeitung von Aufrufen gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC], batching
- ODBC, stored procedures
- SQL Server Native Client ODBC driver, stored procedures
- batches [ODBC]
- ODBC CALL escape sequence
ms.assetid: b7f53e11-15f0-4602-8134-b166160888f0
author: rothja
ms.author: jroth
ms.openlocfilehash: a0df58ce59853ee15b863cbc7bce34041c37fee4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725645"
---
# <a name="batching-stored-procedure-calls"></a><span data-ttu-id="ddf94-102">Batchverarbeitung von gespeicherten Prozeduraufrufen</span><span class="sxs-lookup"><span data-stu-id="ddf94-102">Batching Stored Procedure Calls</span></span>
  <span data-ttu-id="ddf94-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber stapelt bei Bedarf automatisch Aufrufe gespeicherter Prozeduren an den Server.</span><span class="sxs-lookup"><span data-stu-id="ddf94-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver automatically batches stored procedure calls to the server when appropriate.</span></span> <span data-ttu-id="ddf94-104">Der Treiber führt diese Aktion nur aus, wenn die ODBC CALL-Escapesequenz verwendet wird, aber nicht für die [!INCLUDE[tsql](../../includes/tsql-md.md)]-EXECUTE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ddf94-104">The driver only does this when the ODBC CALL escape sequence is used; it does not do this for the [!INCLUDE[tsql](../../includes/tsql-md.md)] EXECUTE statement.</span></span> <span data-ttu-id="ddf94-105">Durch die Batchverarbeitung gespeicherter Prozeduraufrufe wird die Anzahl der Roundtrips zum Server reduziert und die Leistung deutlich verbessert.</span><span class="sxs-lookup"><span data-stu-id="ddf94-105">Batching stored procedure calls can reduce the number of round trips to the server and significantly increase performance.</span></span>  
  
 <span data-ttu-id="ddf94-106">Der Treiber führt Prozeduraufrufe an den Server als Batches aus, wenn Sie einen Batch ausführen, der mehrere ODBC CALL-Escapesequenzen enthält.</span><span class="sxs-lookup"><span data-stu-id="ddf94-106">The driver batches procedure calls to the server when you execute a batch that contains multiple ODBC CALL escape sequences.</span></span> <span data-ttu-id="ddf94-107">Außerdem werden Prozeduraufrufe als Batches ausgeführt, wenn gebundene Parameterarrays mit einer ODBC CALL-Escapesequenz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ddf94-107">It also batches procedure calls when bound parameter arrays are used with an ODBC CALL escape sequence.</span></span> <span data-ttu-id="ddf94-108">Wenn Sie z. b. entweder zeilenweise oder spaltenweise Parameter Bindung verwenden, um ein Array mit fünf Elementen an die Parameter einer SQL-Anweisung des ODBC-Anrufs zu binden, sendet der Treiber beim Aufrufen von **SQLExecute** oder **SQLExecDirect** einen einzelnen Batch mit fünf Prozedur aufrufen an den Server.</span><span class="sxs-lookup"><span data-stu-id="ddf94-108">For example, if you use either row-wise or column-wise parameter binding to bind an array with five elements to the parameters of an ODBC CALL SQL statement, when **SQLExecute** or **SQLExecDirect** is called, the driver sends a single batch with five procedure calls to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf94-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddf94-109">See Also</span></span>  
 [<span data-ttu-id="ddf94-110">Ausführen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ddf94-110">Running Stored Procedures</span></span>](running-stored-procedures.md)  
  
  
