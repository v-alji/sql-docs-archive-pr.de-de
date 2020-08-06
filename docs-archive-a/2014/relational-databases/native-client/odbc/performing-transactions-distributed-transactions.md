---
title: Durchführen verteilter Transaktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, performing distributed transactions
- SQL Server Native Client ODBC driver, transactions
- distributed transactions [ODBC]
- transactions [ODBC]
- ODBC, transactions
ms.assetid: 2c17fba0-7a3c-453c-91b7-f801e7b39ccb
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ec23fd1883749e35e67f888e26bdf031ccf7fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615355"
---
# <a name="performing-distributed-transactions"></a><span data-ttu-id="93906-102">Durchführen verteilter Transaktionen</span><span class="sxs-lookup"><span data-stu-id="93906-102">Performing Distributed Transactions</span></span>
  <span data-ttu-id="93906-103">Microsoft Distributed Transaction Coordinator (MS DTC) ermöglicht es Anwendungen, Transaktionen über zwei oder mehr Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="93906-103">The Microsoft Distributed Transaction Coordinator (MS DTC) allows applications to extend transactions across two or more instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="93906-104">Außerdem können Anwendungen an von Transaktions-Managern verwalteten Transaktionen teilnehmen, die den Standard Open Group DTP XA erfüllen.</span><span class="sxs-lookup"><span data-stu-id="93906-104">It also allows applications to participate in transactions managed by transaction managers that comply with the Open Group DTP XA standard.</span></span>  
  
 <span data-ttu-id="93906-105">Normalerweise werden alle Transaktionsverwaltungsbefehle durch den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Native Client-ODBC-Treiber an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="93906-105">Normally, all transaction management commands are sent through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to the server.</span></span> <span data-ttu-id="93906-106">Die Anwendung startet eine Transaktion durch Aufrufen von [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) mit deaktiviertem Autocommit-Modus.</span><span class="sxs-lookup"><span data-stu-id="93906-106">The application starts a transaction by calling [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) with the autocommit mode turned off.</span></span> <span data-ttu-id="93906-107">Die Anwendung führt anschließend die Updates durch, aus denen die Transaktion besteht, und ruft [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) entweder mit der SQL_COMMIT-Option oder der SQL_ROLLBACK-Option auf.</span><span class="sxs-lookup"><span data-stu-id="93906-107">The application then performs the updates comprising the transaction and calls [SQLEndTran](../../native-client-odbc-api/sqlendtran.md) with either the SQL_COMMIT or SQL_ROLLBACK option.</span></span>  
  
 <span data-ttu-id="93906-108">Bei Verwendung von MS DTC wird MS DTC zum Transaktions-Manager, und **SQLEndTran**wird von der Anwendung nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="93906-108">When using MS DTC, however, MS DTC becomes the transaction manager and the application no longer uses **SQLEndTran**.</span></span>  
  
 <span data-ttu-id="93906-109">Wenn der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver in einer verteilten Transaktion eingetragen ist und dann in einer zweiten verteilten Transaktion eingetragen wird, wird er von der ursprünglichen verteilten Transaktion übernommen und in die neue Transaktion eingetragen.</span><span class="sxs-lookup"><span data-stu-id="93906-109">When enlisted in a distributed transaction, and then enlist in a second distributed transaction, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver defects from the original distributed transaction and enlists in the new transaction.</span></span> <span data-ttu-id="93906-110">Weitere Informationen finden Sie in der [DTC-Programmierreferenz](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="93906-110">For more information, see [DTC Programmer's Reference](https://msdn.microsoft.com/library/ms686108\(VS.85\).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93906-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93906-111">See Also</span></span>  
 [<span data-ttu-id="93906-112">Ausführen von Transaktionen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="93906-112">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
