---
title: Asynchroner Modus und SQLCancel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- asynchronous operations [SQL Server Native Client]
- SQLCancel function
- SQLSetConnectAttr function
- SQL Server Native Client, asynchronous operations
- ODBC functions
- ODBC applications, asynchronous operations
- SQL Server Native Client ODBC driver, asynchronous mode
ms.assetid: f31702a2-df76-4589-ac3b-da5412c03dc2
author: rothja
ms.author: jroth
ms.openlocfilehash: 9071c6821e6edeb577b639223e42899d2927bced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620300"
---
# <a name="asynchronous-mode-and-sqlcancel"></a><span data-ttu-id="c3007-102">Asynchroner Modus und SQLCancel</span><span class="sxs-lookup"><span data-stu-id="c3007-102">Asynchronous Mode and SQLCancel</span></span>
  <span data-ttu-id="c3007-103">Einige ODBC-Funktionen können synchron oder asynchron verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c3007-103">Some ODBC functions can operate either synchronously or asynchronously.</span></span> <span data-ttu-id="c3007-104">Die Anwendung kann asynchrone Vorgänge für ein Anweisungshandle oder ein Verbindungshandle aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c3007-104">The application can enable asynchronous operations for either a statement handle or a connection handle.</span></span> <span data-ttu-id="c3007-105">Wenn die Option für ein Verbindungshandle eingerichtet ist, wirkt sie sich auf alle Anweisungshandles auf dem Verbindungshandle aus.</span><span class="sxs-lookup"><span data-stu-id="c3007-105">If the option is set for a connection handle, it affects all statement handles on the connection handle.</span></span> <span data-ttu-id="c3007-106">Die Anwendung verwendet die folgenden Anweisungen, um asynchrone Vorgänge zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="c3007-106">The application uses the following statements to enable or disable asynchronous operations:</span></span>  
  
```  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetConnectAttr(hdbc, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_ON, SQL_IS_INTEGER);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ASYNC_ENABLE,  
                        SQL_ASYNC_ENABLE_OFF, SQL_IS_INTEGER);  
```  
  
 <span data-ttu-id="c3007-107">Wenn eine Anwendung eine ODBC-Funktion im synchronen Modus aufruft, gibt der Treiber die Steuerung nicht an die Anwendung zurück, bis sie darüber benachrichtigt wird, dass der Server den Befehl abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="c3007-107">When an application calls an ODBC function in synchronous mode, the driver does not return control to the application until it is notified that the server has completed the command.</span></span>  
  
 <span data-ttu-id="c3007-108">Beim asynchronen Betrieb gibt der Treiber unmittelbar die Steuerung an die Anwendung zurück, noch bevor der Befehl an den Server gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3007-108">When operating asynchronously, the driver immediately returns control to the application, even before sending the command to the server.</span></span> <span data-ttu-id="c3007-109">Der Treiber setzt den Rückgabecode auf SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="c3007-109">The driver sets the return code to SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="c3007-110">Die Anwendung kann dann andere Arbeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c3007-110">The application can then perform other work.</span></span>  
  
 <span data-ttu-id="c3007-111">Wenn die Anwendung überprüft, ob der Befehl ausgeführt wurde, führt sie den gleichen Funktionsaufruf mit den gleichen Parametern für den Treiber durch.</span><span class="sxs-lookup"><span data-stu-id="c3007-111">When the application tests for completion of the command, it makes the same function call with the same parameters to the driver.</span></span> <span data-ttu-id="c3007-112">Wenn der Treiber noch keine Antwort vom Server erhalten hat, gibt er erneut SQL_STILL_EXECUTING zurück.</span><span class="sxs-lookup"><span data-stu-id="c3007-112">If the driver has not yet received an answer from the server, it will again return SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="c3007-113">Die Anwendung muss den Befehl regelmäßig testen, bis der Rückgabecode einen anderen Wert als SQL_STILL_EXECUTING annimmt.</span><span class="sxs-lookup"><span data-stu-id="c3007-113">The application must test the command periodically until the return code is something other than SQL_STILL_EXECUTING.</span></span> <span data-ttu-id="c3007-114">Wenn die Anwendung einen anderen Rückgabecode erhält (auch SQL_ERROR), kann sie ermitteln, ob der Befehl abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c3007-114">When the application gets some other return code, even SQL_ERROR, it can determine that the command has completed.</span></span>  
  
 <span data-ttu-id="c3007-115">Gelegentlich ist ein Befehl längere Zeit ausstehend.</span><span class="sxs-lookup"><span data-stu-id="c3007-115">Sometimes a command is outstanding for a long time.</span></span> <span data-ttu-id="c3007-116">Wenn die Anwendung den Befehl abbrechen muss, ohne auf eine Antwort zu warten, kann dies dazu führen, dass **SQLCancel** mit dem gleichen Anweisungs Handle wie der ausstehende Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c3007-116">If the application needs to cancel the command without waiting for a reply, it can do so by calling **SQLCancel** with the same statement handle as the outstanding command.</span></span> <span data-ttu-id="c3007-117">Dies ist der einzige Zeitpunkt, an dem **SQLCancel** verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="c3007-117">This is the only time **SQLCancel** should be used.</span></span> <span data-ttu-id="c3007-118">Einige Programmierer verwenden **SQLCancel** , wenn Sie einen Teil des Resultsets verarbeitet haben und den Rest des Resultsets abbrechen möchten.</span><span class="sxs-lookup"><span data-stu-id="c3007-118">Some programmers use **SQLCancel** when they have processed part way through a result set and want to cancel the rest of the result set.</span></span> <span data-ttu-id="c3007-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) oder [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) sollte verwendet werden, um den Rest eines ausstehenden Resultsets, nicht **SQLCancel**, abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="c3007-119">[SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) or [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) should be used to cancel the remainder of an outstanding result set, not **SQLCancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3007-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3007-120">See Also</span></span>  
 [<span data-ttu-id="c3007-121">Erstellen einer SQL Server Native Client-ODBC-Treiberanwendung</span><span class="sxs-lookup"><span data-stu-id="c3007-121">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
