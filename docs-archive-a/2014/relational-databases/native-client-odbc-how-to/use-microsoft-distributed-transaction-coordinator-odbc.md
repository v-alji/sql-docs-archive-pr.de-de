---
title: Verwenden von Microsoft Distributed Transaction Coordinator (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- MS DTC, using
ms.assetid: 12a275e1-8c7e-436d-8a4e-b7bee853b35c
author: rothja
ms.author: jroth
ms.openlocfilehash: f7b7da33066a9f4edd01037738ed91155340e6ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616980"
---
# <a name="use-microsoft-distributed-transaction-coordinator-odbc"></a><span data-ttu-id="4b634-102">Verwenden von Microsoft Distributed Transaction Coordinator (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4b634-102">Use Microsoft Distributed Transaction Coordinator (ODBC)</span></span>
    
### <a name="to-update-two-or-more-sql-servers-by-using-ms-dtc"></a><span data-ttu-id="4b634-103">So aktualisieren Sie zwei oder mehr SQL Server mit MS DTC</span><span class="sxs-lookup"><span data-stu-id="4b634-103">To update two or more SQL Servers by using MS DTC</span></span>  
  
1.  <span data-ttu-id="4b634-104">Stellen Sie mit der MS DTC OLE-Funktion DtcGetTransactionManager eine Verbindung mit MS DTC her.</span><span class="sxs-lookup"><span data-stu-id="4b634-104">Connect to MS DTC by using the MS DTC OLE DtcGetTransactionManager function.</span></span> <span data-ttu-id="4b634-105">Informationen zu MS DTC finden Sie unter Microsoft Distributed Transaction Coordinator.</span><span class="sxs-lookup"><span data-stu-id="4b634-105">For information about MS DTC, see Microsoft Distributed Transaction Coordinator.</span></span>  
  
2.  <span data-ttu-id="4b634-106">Nennen Sie SQL driverconnect einmal für jede Microsoft SQL Server Verbindung, die Sie einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="4b634-106">Call SQL DriverConnect once for each Microsoft SQL Server connection you want to establish.</span></span>  
  
3.  <span data-ttu-id="4b634-107">Rufen Sie die MS DTC OLE-Funktion ITransactionDispenser::BeginTransaction auf, um eine MS DTC-Transaktion zu starten und ein Transaction-Objekt zu erhalten, das diese Transaktion repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="4b634-107">Call the MS DTC OLE ITransactionDispenser::BeginTransaction function to begin an MS DTC transaction and obtain a Transaction object that represents the transaction.</span></span>  
  
4.  <span data-ttu-id="4b634-108">Rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mindestens einmal für jede ODBC-Verbindung auf, die Sie in der MS DTC-Transaktion auflisten möchten.</span><span class="sxs-lookup"><span data-stu-id="4b634-108">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) one or more times for each ODBC connection you want to enlist in the MS DTC transaction.</span></span> <span data-ttu-id="4b634-109">Der zweite [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md)-Parameter muss SQL_ATTR_ENLIST_IN_DTC lauten, und der dritte Parameter muss das Transaktionsobjekt (aus Schritt 3) sein.</span><span class="sxs-lookup"><span data-stu-id="4b634-109">[SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) second parameter must be SQL_ATTR_ENLIST_IN_DTC and third parameter must be the Transaction object (obtained in Step 3).</span></span>  
  
5.  <span data-ttu-id="4b634-110">Rufen Sie [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) einmal für jeden SQL Server auf, den Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4b634-110">Call [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) once for each SQL Server you want to update.</span></span>  
  
6.  <span data-ttu-id="4b634-111">Rufen Sie MS DTC OLE-Funktion ITransaction::Commit auf, um ein Commit für die MS DTC-Transaktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4b634-111">Call the MS DTC OLE ITransaction::Commit function to commit the MS DTC transaction.</span></span> <span data-ttu-id="4b634-112">Das Transaction-Objekt ist nicht mehr gültig.</span><span class="sxs-lookup"><span data-stu-id="4b634-112">The Transaction object is no longer valid.</span></span>  
  
 <span data-ttu-id="4b634-113">Um eine Reihe von MS DTC-Transaktionen auszuführen, wiederholen Sie die Schritte 3 bis 6.</span><span class="sxs-lookup"><span data-stu-id="4b634-113">To perform a series of MS DTC transactions, repeat Steps 3 through 6.</span></span>  
  
 <span data-ttu-id="4b634-114">Um den Verweis auf das Transaction-Objekt freizugeben, rufen Sie die MS DTC OLE-Funktion ITransaction::Return auf.</span><span class="sxs-lookup"><span data-stu-id="4b634-114">To release the reference to the Transaction object, call the MS DTC OLE ITransaction::Return function.</span></span>  
  
 <span data-ttu-id="4b634-115">Wenn Sie eine ODBC-Verbindung mit einer MS DTC-Transaktion und dieselbe Verbindung dann mit einer lokalen SQL Server-Transaktion verwenden möchten, rufen Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) mit SQL_DTC_DONE auf.</span><span class="sxs-lookup"><span data-stu-id="4b634-115">To use an ODBC connection with an MS DTC transaction, and then use the same connection with a local SQL Server transaction, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_DTC_DONE.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b634-116">Sie können [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) und [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) auch nacheinander für jeden SQL Server aufrufen, statt sie gemäß dem Vorschlag in den Schritten 4 und 5 aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4b634-116">You can also call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) and [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) in turn for each SQL Server instead of calling them as suggested earlier in Steps 4 and 5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b634-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b634-117">See Also</span></span>  
 [<span data-ttu-id="4b634-118">Ausführen von Transaktionen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="4b634-118">Performing Transactions &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
  
