---
title: Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- stored procedures [ODBC], about ODBC stored procedures
- ODBC applications, statements
- statements [ODBC], stored procedures
- ODBC applications, stored procedures
ms.assetid: c64d5f3a-376b-48ef-84f3-b6148ac8600a
author: rothja
ms.author: jroth
ms.openlocfilehash: a7ae4678d324ba7d07ae429793b1f75b57bb15e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608605"
---
# <a name="procedures"></a><span data-ttu-id="a1872-102">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a1872-102">Procedures</span></span>
  <span data-ttu-id="a1872-103">Eine gespeicherte Prozedur ist ein vorkompiliertes ausführbares Objekt, das eine oder mehrere [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen enthält.</span><span class="sxs-lookup"><span data-stu-id="a1872-103">A stored procedure is a precompiled executable object that contains one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="a1872-104">Gespeicherte Prozeduren können Ein- und Ausgabeparameter enthalten und auch einen ganzzahligen Rückgabecode ausgeben.</span><span class="sxs-lookup"><span data-stu-id="a1872-104">Stored procedures can have input and output parameters and can also put out an integer return code.</span></span> <span data-ttu-id="a1872-105">Eine Anwendung kann kann mithilfe von Katalogfunktionen verfügbare gespeicherte Prozeduren auflisten.</span><span class="sxs-lookup"><span data-stu-id="a1872-105">An application can enumerate available stored procedures by using catalog functions.</span></span>  
  
 <span data-ttu-id="a1872-106">ODBC-Anwendungen für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sollten gespeicherte Prozeduren nur mithilfe der direkten Ausführung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a1872-106">ODBC applications that target [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should only use direct execution to call a stored procedure.</span></span> <span data-ttu-id="a1872-107">Bei einer Verbindung mit früheren Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implementiert der Native Client-ODBC-Treiber die [SQLPrepare-Funktion](https://go.microsoft.com/fwlink/?LinkId=59360) , indem eine temporäre gespeicherte Prozedur erstellt wird, die dann für **SQLExecute**aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a1872-107">When connected to earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver implements [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360) by creating a temporary stored procedure, which is then called on **SQLExecute**.</span></span> <span data-ttu-id="a1872-108">Es erhöht den Aufwand, damit **SQLPrepare** eine temporäre gespeicherte Prozedur erstellt, die nur die gespeicherte Ziel Prozedur aufruft und die gespeicherte Ziel Prozedur direkt ausführt.</span><span class="sxs-lookup"><span data-stu-id="a1872-108">It adds overhead to have **SQLPrepare** create a temporary stored procedure that only calls the target stored procedure versus directly executing the target stored procedure.</span></span> <span data-ttu-id="a1872-109">Selbst bei einer Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] muss der Aufruf eines zusätzlichen Roundtrips durch das Netzwerk vorbereitet und ein Ausführungsplan, mit dem nur der Ausführungsplan der gespeicherten Prozedur aufgerufen wird, erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1872-109">Even when connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], preparing a call requires an extra round trip across the network and the building of an execution plan that just calls the stored procedure execution plan.</span></span>  
  
 <span data-ttu-id="a1872-110">Beim Ausführen einer gespeicherten Prozedur sollten ODBC-Anwendungen die ODBC CALL-Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="a1872-110">ODBC applications should use the ODBC CALL syntax when executing a stored procedure.</span></span> <span data-ttu-id="a1872-111">Der Treiber ist für die Verwendung eines Remoteprozeduraufrufsmechanismus zum Aufrufen der Prozedur optimiert, sofern die ODBC CALL-Syntax verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1872-111">The driver is optimized to use a remote procedure call mechanism to call the procedure when the ODBC CALL syntax is used.</span></span> <span data-ttu-id="a1872-112">Dies ist effizienter als der Mechanismus, der verwendet wird, um eine [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE-Anweisung an den Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="a1872-112">This is more efficient than the mechanism used to send a [!INCLUDE[tsql](../../../includes/tsql-md.md)] EXECUTE statement to the server.</span></span>  
  
 <span data-ttu-id="a1872-113">Weitere Informationen finden Sie unter [Ausführen gespeicherter Prozeduren](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a1872-113">For more information, see [Running Stored Procedures](../../native-client-odbc-stored-procedures/running-stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1872-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1872-114">See Also</span></span>  
 [<span data-ttu-id="a1872-115">Ausführen von Anweisungen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="a1872-115">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
