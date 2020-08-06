---
title: Isolationsstufe für Cursor Transaktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- isolation levels [ODBC]
- ODBC applications, row versioning
- cursors [ODBC], isolation levels
- ODBC cursors, isolation levels
- row versioning [SQL Server], ODBC
ms.assetid: 0c6663a4-5a25-44aa-8fe4-e35af9bf4a83
author: rothja
ms.author: jroth
ms.openlocfilehash: 30f3dc8a9136a7cbe1d5897cb0bcc9fff8c35ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722805"
---
# <a name="cursor-transaction-isolation-level"></a><span data-ttu-id="d3972-102">Transaktionsisolationsstufen von Cursorn</span><span class="sxs-lookup"><span data-stu-id="d3972-102">Cursor Transaction Isolation Level</span></span>
  <span data-ttu-id="d3972-103">Das komplette Sperrverhalten von Cursorn basiert auf der Interaktion zwischen Parallelitätsattributen und der vom Client festgelegten Transaktionsisolationsstufe.</span><span class="sxs-lookup"><span data-stu-id="d3972-103">The complete locking behavior of cursors is based on an interaction between concurrency attributes and the transaction isolation level set by the client.</span></span> <span data-ttu-id="d3972-104">ODBC-Clients legen die Transaktions Isolationsstufe mithilfe der Attribute [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION oder SQL_COPT_SS_TXN_ISOLATION fest.</span><span class="sxs-lookup"><span data-stu-id="d3972-104">ODBC clients set the transaction isolation level using the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) SQL_ATTR_TXN_ISOLATION or SQL_COPT_SS_TXN_ISOLATION attributes.</span></span> <span data-ttu-id="d3972-105">Das Transaktionssperrverhalten einer bestimmten Cursorumgebung wird durch die Kombination des Sperrverhaltens der Parallelitätseinstellung mit den Optionen für die Transaktionsisolationsstufen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d3972-105">The locking behavior of a specific cursor environment is determined by combining the locking behaviors of the concurrency and transaction isolation level options.</span></span>  
  
 <span data-ttu-id="d3972-106">Die folgenden Cursor Transaktions Isolations Stufen werden vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d3972-106">The following cursor transaction isolation levels are supported by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver:</span></span>  
  
-   <span data-ttu-id="d3972-107">Read Committed (SQL_TXN_READ_COMMITTED)</span><span class="sxs-lookup"><span data-stu-id="d3972-107">Read committed (SQL_TXN_READ_COMMITTED)</span></span>  
  
-   <span data-ttu-id="d3972-108">Read Uncommitted (SQL_TXN_READ_UNCOMMITTED)</span><span class="sxs-lookup"><span data-stu-id="d3972-108">Read uncommitted (SQL_TXN_READ_UNCOMMITTED)</span></span>  
  
-   <span data-ttu-id="d3972-109">Repeatable Read (SQL_TXN_REPEATABLE_READ) lesen Sie</span><span class="sxs-lookup"><span data-stu-id="d3972-109">Repeatable read (SQL_TXN_REPEATABLE_READ)</span></span>  
  
-   <span data-ttu-id="d3972-110">Serializable (SQL_TXN_SERIALIZABLE)</span><span class="sxs-lookup"><span data-stu-id="d3972-110">Serializable (SQL_TXN_SERIALIZABLE)</span></span>  
  
-   <span data-ttu-id="d3972-111">Momentaufnahme (SQL_TXN_SS_SNAPSHOT)</span><span class="sxs-lookup"><span data-stu-id="d3972-111">Snapshot (SQL_TXN_SS_SNAPSHOT)</span></span>  
  
 <span data-ttu-id="d3972-112">Beachten Sie, dass die ODBC-API zusätzliche Transaktions Isolations Stufen angibt. Diese werden jedoch von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d3972-112">Note that the ODBC API specifies additional transaction isolation levels, but these are not supported by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3972-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3972-113">See Also</span></span>  
 [<span data-ttu-id="d3972-114">Cursoreigenschaften</span><span class="sxs-lookup"><span data-stu-id="d3972-114">Cursor Properties</span></span>](cursor-properties.md)  
  
  
