---
title: Trennen der Verbindung mit einer Datenquelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- disconnecting [ODBC]
- ODBC applications, disconnecting
- SQLDisconnect function
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLFreeHandle function
- ODBC data sources, disconnecting
- SQL Server Native Client ODBC driver, data sources
- ODBC functions
- SQL Server Native Client ODBC driver, connections
ms.assetid: 65b0267d-b2ab-4a59-83f2-436d90cfbf79
author: rothja
ms.author: jroth
ms.openlocfilehash: 5db3b83ab65d854f3a4d2182d9a4a1314e097681
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617945"
---
# <a name="disconnecting-from-a-data-source"></a><span data-ttu-id="67f66-102">Trennen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="67f66-102">Disconnecting from a Data Source</span></span>
  <span data-ttu-id="67f66-103">Wenn eine Anwendung mit der Verwendung einer Datenquelle fertig ist, wird **SQLDisconnect**aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="67f66-103">When an application has finished using a data source, it calls **SQLDisconnect**.</span></span> <span data-ttu-id="67f66-104">**SQLDisconnect** gibt alle-Anweisungen frei, die der Verbindung zugeordnet sind, und trennt den Treiber von der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="67f66-104">**SQLDisconnect** frees any statements that are allocated on the connection and disconnects the driver from the data source.</span></span> <span data-ttu-id="67f66-105">Nach dem Trennen der Verbindung kann die Anwendung [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) aufzurufen, um das Verbindungs Handle freizugeben.</span><span class="sxs-lookup"><span data-stu-id="67f66-105">After disconnecting, the application can call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) to free the connection handle.</span></span> <span data-ttu-id="67f66-106">Vor dem Beenden Ruft eine Anwendung auch **SQLFreeHandle** auf, um das Umgebungs Handle freizugeben.</span><span class="sxs-lookup"><span data-stu-id="67f66-106">Before exiting, an application also calls **SQLFreeHandle** to free the environment handle.</span></span>  
  
 <span data-ttu-id="67f66-107">Nach dem Trennen der Verbindung kann eine Anwendung das zugeordnete Verbindungshandle wiederverwenden. Hierbei kann entweder eine neue Verbindung zu derselben oder zu einer anderen Datenquelle aufgebaut werden.</span><span class="sxs-lookup"><span data-stu-id="67f66-107">After disconnecting, an application can reuse the allocated connection handle, either to connect to a different data source or reconnect to the same data source.</span></span> <span data-ttu-id="67f66-108">Sollte der Anwendungsentwickler entscheiden, die Verbindung aufrecht zu erhalten anstatt die Verbindung zu trennen und später wieder erneut herzustellen, sollte er dabei die relativen Kosten dieser Optionen in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="67f66-108">The decision to remain connected instead of disconnecting and reconnecting later requires that the application writer consider the relative costs of each option.</span></span> <span data-ttu-id="67f66-109">Eine Verbindung mit einer Datenquelle herzustellen und aufrecht zu erhalten kann abhängig vom verwendeten Verbindungsmedium relativ kostspielig sein.</span><span class="sxs-lookup"><span data-stu-id="67f66-109">Connecting to a data source and remaining connected can be relatively costly, depending on the connection medium.</span></span> <span data-ttu-id="67f66-110">Unter Berücksichtigung dieses Nachteils muss auch die Wahrscheinlichkeit erwogen werden, dass dieselbe Datenquelle unter Umständen von anderen Vorgängen beansprucht wird, und der Zeitpunkt dieser Nutzung bedacht werden.</span><span class="sxs-lookup"><span data-stu-id="67f66-110">In making a trade-off, the application must also make assumptions about the probability and timing of additional operations on the same data source.</span></span> <span data-ttu-id="67f66-111">Eine Anwendung beansprucht möglicherweise auch mehr als eine Verbindung.</span><span class="sxs-lookup"><span data-stu-id="67f66-111">An application may also have to use more than one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f66-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67f66-112">See Also</span></span>  
 [<span data-ttu-id="67f66-113">Kommunikation mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="67f66-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
