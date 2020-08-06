---
title: ODBC-Themen zur Vorgehensweise | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 151f2066-1c37-410f-88f4-b27dfca66031
author: rothja
ms.author: jroth
ms.openlocfilehash: cfeb120b9fa1fedb5358b5e12dabed7835f9a6b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722766"
---
# <a name="odbc-how-to-topics"></a><span data-ttu-id="603d9-102">ODBC How-to Topics</span><span class="sxs-lookup"><span data-stu-id="603d9-102">ODBC How-to Topics</span></span>
  <span data-ttu-id="603d9-103">Um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -ODBC-Treiber zu verwenden, müssen Sie in der Lage sein, ODBC-Datenquellen zu erstellen, und sicherstellen, dass der Server über die korrekte Version der gespeicherten Prozeduren für Kataloginformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="603d9-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver, you must be able to create ODBC data sources and ensure that the server has the correct version of the catalog stored procedures.</span></span> <span data-ttu-id="603d9-104">Zur Programmierung einer ODBC-Anwendung, die SQL Server verwendet, müssen Sie wissen, wie Sie ODBC-Handles zuordnen, Attribute festlegen, eine Verbindung mit einer Instanz von SQL Server herstellen, Abfragen ausführen und Ergebnisse verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="603d9-104">To code an ODBC application that uses SQL Server, you must know how to allocate ODBC handles, set attributes, connect to an instance of SQL Server, execute queries, and process results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="603d9-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="603d9-105">In This Section</span></span>  
  
-   [<span data-ttu-id="603d9-106">Themen zur Vorgehensweise: Konfigurieren des SQL Server-ODBC-Treibers</span><span class="sxs-lookup"><span data-stu-id="603d9-106">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
-   [<span data-ttu-id="603d9-107">Zuordnen von Handles und Herstellen einer Verbindung mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-107">Allocate Handles and Connect to SQL Server &#40;ODBC&#41;</span></span>](allocate-handles-and-connect-to-sql-server-odbc.md)  
  
-   [<span data-ttu-id="603d9-108">Gewusst-wie-Themen zum Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-108">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](execute-queries/executing-queries-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="603d9-109">Themen zur Vorgehensweise bei der Verarbeitung von Ergebnissen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-109">Processing Results How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="603d9-110">Gewusst-wie-Themen zur Verwendung von Cursorn &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-110">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](cursors/using-cursors-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="603d9-111">Verwenden Sie Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-111">Use Microsoft Distributed Transaction Coordinator &#40;ODBC&#41;</span></span>](use-microsoft-distributed-transaction-coordinator-odbc.md)  
  
-   [<span data-ttu-id="603d9-112">Gewusst-wie-Themen zur Ausführung gespeicherter Prozeduren &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-112">Running Stored Procedures How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="603d9-113">Gewusst-wie-Themen zum Verwalten von Text-und image-Spalten &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-113">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
-   [<span data-ttu-id="603d9-114">Gewusst-wie-Themen zur Profilerstellung für ODBC-Treiber &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-114">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
-   [<span data-ttu-id="603d9-115">Verarbeiten von ODBC-Fehlern &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-115">Process ODBC Errors &#40;ODBC&#41;</span></span>](process-odbc-errors-odbc.md)  
  
-   [<span data-ttu-id="603d9-116">Massen kopieren mit dem SQL Server ODBC-Treiber &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-116">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copy/bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="603d9-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="603d9-117">See Also</span></span>  
 [<span data-ttu-id="603d9-118">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="603d9-118">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
