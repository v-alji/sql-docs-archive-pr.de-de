---
title: Kommunikation mit SQL Server (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, communicating with SQL Server
- ODBC applications, communicating with SQL Server
- ODBC, communicating with SQL Server
ms.assetid: cca3dcf0-2a7e-465a-84de-7ce055360eb6
author: rothja
ms.author: jroth
ms.openlocfilehash: c41ac2dcce9c5bdbdd351148d16bcaa8f067d22f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722809"
---
# <a name="communicating-with-sql-server-odbc"></a><span data-ttu-id="7029e-102">Kommunikation mit SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7029e-102">Communicating with SQL Server (ODBC)</span></span>
  <span data-ttu-id="7029e-103">Damit eine ODBC-Anwendung mit einer Instanz von kommunizieren [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann, muss Sie Umgebungs-und Verbindungs Handles zuordnen und eine Verbindung mit der Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="7029e-103">For an ODBC application to communicate with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it must allocate environment and connection handles and connect to the data source.</span></span> <span data-ttu-id="7029e-104">Nach dem Herstellen einer Verbindung kann die Anwendung Abfragen an den Server senden und Resultsets verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7029e-104">After a connection is established, the application can send queries to the server and process any result sets.</span></span> <span data-ttu-id="7029e-105">Wenn die Anwendung die Datenquelle nicht mehr benötigt, wird die Verbindung mit der Datenquelle getrennt und das Verbindungshandle freigegeben.</span><span class="sxs-lookup"><span data-stu-id="7029e-105">When the application has finished using the data source, it disconnects from the data source and frees the connection handle.</span></span> <span data-ttu-id="7029e-106">Wenn die Anwendung alle Verbindungshandles freigegeben hat, wird das Umgebungshandle freigegeben.</span><span class="sxs-lookup"><span data-stu-id="7029e-106">When the application has freed all its connection handles, it frees the environment handle.</span></span>  
  
 <span data-ttu-id="7029e-107">Eine Anwendung kann mit beliebig vielen Datenquellen eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="7029e-107">An application can connect to any number of data sources.</span></span> <span data-ttu-id="7029e-108">Die Anwendung kann eine Kombination aus Treibern und Datenquellen, denselben Treiber und eine Kombination aus Datenquellen oder auch denselben Treiber und mehrere Verbindungen mit derselben Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="7029e-108">The application can use a combination of drivers and data sources, the same driver and a combination of data sources, or even the same driver and multiple connections to the same data source.</span></span>  
  
 <span data-ttu-id="7029e-109">Sie können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Beispiele auf der Seite [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) auf MSDN herunterladen.</span><span class="sxs-lookup"><span data-stu-id="7029e-109">You can download [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC samples from the [SQL Server Downloads](https://go.microsoft.com/fwlink/?LinkId=62796) page on MSDN.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7029e-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7029e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="7029e-111">Zuordnen eines Umgebungshandles</span><span class="sxs-lookup"><span data-stu-id="7029e-111">Allocating an Environment Handle</span></span>](allocating-an-environment-handle.md)  
  
-   [<span data-ttu-id="7029e-112">Zuordnen eines Verbindungshandles</span><span class="sxs-lookup"><span data-stu-id="7029e-112">Allocating a Connection Handle</span></span>](allocating-a-connection-handle.md)  
  
-   [<span data-ttu-id="7029e-113">SQL Server Native Client ODBC-Datenquellen</span><span class="sxs-lookup"><span data-stu-id="7029e-113">SQL Server Native Client ODBC Data Sources</span></span>](../../integration-services/connection-manager/data-sources.md)  
  
-   [<span data-ttu-id="7029e-114">Herstellen einer Verbindung mit einer Datenquelle &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="7029e-114">Connecting to a Data Source &#40;ODBC&#41;</span></span>](connecting-to-a-data-source-odbc.md)  
  
-   [<span data-ttu-id="7029e-115">Trennen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="7029e-115">Disconnecting from a Data Source</span></span>](disconnecting-from-a-data-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="7029e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7029e-116">See Also</span></span>  
 <span data-ttu-id="7029e-117">[SQL Server Native Client &#40;ODBC-&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="7029e-117">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="7029e-118">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="7029e-118">SQLSetEnvAttr</span></span>](../native-client-odbc-api/sqlsetenvattr.md)  
  
  
