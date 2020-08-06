---
title: Bestimmen der Eigenschaften eines Resultsets (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC], characteristics
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- SQLDescribeCol function
- metadata [ODBC]
- SQLColAttribute function
- SQLNumResultCols function
ms.assetid: 90be414c-04b3-46c0-906b-ae7537989b7d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5957092cdddfbcbce904d9a6483914672565d337
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616041"
---
# <a name="determining-the-characteristics-of-a-result-set-odbc"></a><span data-ttu-id="bac3b-102">Bestimmen der Eigenschaften eines Resultsets (ODBC)</span><span class="sxs-lookup"><span data-stu-id="bac3b-102">Determining the Characteristics of a Result Set (ODBC)</span></span>
  <span data-ttu-id="bac3b-103">Metadaten sind Daten, die andere Daten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="bac3b-103">Metadata is data that describes other data.</span></span> <span data-ttu-id="bac3b-104">Resultsetmetadaten beschreiben beispielsweise die Merkmale eines Resultsets, wie die Spaltenanzahl im Resultset, die Datentypen in diesen Spalten, ihre Namen, Genauigkeit und NULL-Zulässigkeit.</span><span class="sxs-lookup"><span data-stu-id="bac3b-104">For example, result set metadata describes the characteristics of a result set, such as the number of columns in the result set, the data types of those columns, their names, precision, and nullability.</span></span>  
  
 <span data-ttu-id="bac3b-105">ODBC liefert Metadaten an Anwendungen durch seine API-Katalogfunktionen.</span><span class="sxs-lookup"><span data-stu-id="bac3b-105">ODBC supplies metadata to applications through its catalog API functions.</span></span> <span data-ttu-id="bac3b-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber implementiert viele der ODBC-API-Katalog Funktionen als Aufrufe einer entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Katalog Prozedur.</span><span class="sxs-lookup"><span data-stu-id="bac3b-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver implements many of the ODBC API catalog functions as calls to a corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] catalog procedure.</span></span>  
  
 <span data-ttu-id="bac3b-107">Anwendungen erfordern Metadaten für die meisten Resultsetvorgänge.</span><span class="sxs-lookup"><span data-stu-id="bac3b-107">Applications require metadata for most result set operations.</span></span> <span data-ttu-id="bac3b-108">Die Anwendung verwendet z. B. den Datentyp einer Spalte, um zu bestimmen, welche Art von Variable an diese Spalte gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="bac3b-108">For example, the application uses the data type of a column to determine what kind of variable to bind to that column.</span></span> <span data-ttu-id="bac3b-109">Sie verwendet die Bytelänge einer Zeichenspalte, um zu bestimmen, wie viel Platz zur Anzeige von Daten aus dieser Spalte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="bac3b-109">It uses the byte length of a character column to determine how much space it must have to display data from that column.</span></span> <span data-ttu-id="bac3b-110">Wie eine Anwendung die Metadaten für eine Spalte bestimmt, hängt vom Typ der Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="bac3b-110">How an application determines the metadata for a column depends on the type of the application.</span></span>  
  
 <span data-ttu-id="bac3b-111">Vertikale Anwendungen funktionieren i. d. R. mit vordefinierten Tabellen und führen vordefinierte Vorgänge auf diese Tabellen aus.</span><span class="sxs-lookup"><span data-stu-id="bac3b-111">Vertical applications typically work with predefined tables and perform predefined operations on those tables.</span></span> <span data-ttu-id="bac3b-112">Da die Resultsetmetadaten für solche Anwendungen definiert werden, bevor die Anwendung überhaupt geschrieben wird, und vom Entwickler gesteuert werden, können sie in die Anwendung hartcodiert werden.</span><span class="sxs-lookup"><span data-stu-id="bac3b-112">Because the result set metadata for such applications is defined before the application is even written and is controlled by the developer, it can be hard-coded into the application.</span></span> <span data-ttu-id="bac3b-113">Wenn beispielsweise eine OrderID-Spalte in der Datenquelle als 4-Byte-Ganzzahl definiert ist, kann die Anwendung stets eine 4-Byte-Ganzzahl an diese Spalte binden.</span><span class="sxs-lookup"><span data-stu-id="bac3b-113">For example, if an order ID column is defined as a 4-byte integer in the data source, the application can always bind a 4-byte integer to that column.</span></span> <span data-ttu-id="bac3b-114">Wenn Metadaten in der Anwendung hartcodiert sind, bedeutet eine Änderung an den von der Anwendung verwendeten Tabelle im Allgemeinen eine Änderung am Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="bac3b-114">When metadata is hard-coded in the application, a change to the tables used by the application generally implies a change to the application code.</span></span>  
  
 <span data-ttu-id="bac3b-115">In generischen Anwendungen, vor allem Anwendungen, die Ad-Hoc-Abfragen unterstützen, sind die Metadaten des von ihnen erstellten Resultsets typischerweise bis zur Laufzeit unbekannt.</span><span class="sxs-lookup"><span data-stu-id="bac3b-115">In generic applications, especially applications that support ad hoc queries, the metadata of the result sets they create is typically unknown until run time.</span></span>  
  
 <span data-ttu-id="bac3b-116">Ein Anwendung kann folgende Aufrufe durchführen, um die Eigenschaften eines Resultsets zu bestimmen:</span><span class="sxs-lookup"><span data-stu-id="bac3b-116">To determine the characteristics of a result set, an application can call:</span></span>  
  
-   <span data-ttu-id="bac3b-117">[SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) , um zu bestimmen, wie viele Spalten eine Anforderung zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="bac3b-117">[SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to determine how many columns a request returned.</span></span>  
  
-   <span data-ttu-id="bac3b-118">[SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) oder [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) , um eine Spalte im Resultset zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="bac3b-118">[SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) or [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to describe a column in the result set.</span></span>  
  
 <span data-ttu-id="bac3b-119">Eine wohlgeformte Anwendung wird ausgehend von der Annahme geschrieben, dass das Resultset unbekannt ist, und verwendet die von diesen Funktionen zurückgegebenen Informationen dazu, die Spalten im Resultset zu binden.</span><span class="sxs-lookup"><span data-stu-id="bac3b-119">A well-designed application is written with the assumption that the result set is unknown and uses the information returned by these functions to bind the columns in the result set.</span></span> <span data-ttu-id="bac3b-120">Eine Anwendung kann diese Funktionen jederzeit aufrufen, nachdem eine Anweisung vorbereitet oder ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bac3b-120">An application can call these functions at any time after a statement is prepared or executed.</span></span> <span data-ttu-id="bac3b-121">Um eine optimale Leistung zu erzielen, sollte eine Anwendung jedoch nach der Ausführung einer-Anweisung **SQLColAttribute**, **SQLDescribeCol**und **SQLNumResultCols** aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bac3b-121">However, for optimal performance, an application should call **SQLColAttribute**, **SQLDescribeCol**, and **SQLNumResultCols** after a statement is executed.</span></span>  
  
 <span data-ttu-id="bac3b-122">Sie können mehrere gleichzeitige Abrufe auf Metadaten durchführen.</span><span class="sxs-lookup"><span data-stu-id="bac3b-122">You can have multiple concurrent calls for metadata.</span></span> <span data-ttu-id="bac3b-123">Die den ODBC-API-Implementierungen zugrunde liegenden Systemkatalogprozeduren können mit dem ODBC-Treiber aufgerufen werden, während dieser statische Servercursor verwendet.</span><span class="sxs-lookup"><span data-stu-id="bac3b-123">The system catalog procedures underlying the ODBC catalog API implementations can be called by the ODBC driver while it is using static server cursors.</span></span> <span data-ttu-id="bac3b-124">So können Anwendungen mehrere Aufrufe an ODBC-Katalogfunktionen gleichzeitig verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="bac3b-124">This lets applications concurrently process multiple calls to ODBC catalog functions.</span></span>  
  
 <span data-ttu-id="bac3b-125">Wenn die Anwendung einen bestimmten Metadatensatz mehr als ein Mal verwendet, ist es möglicherweise von Vorteil, wenn die Informationen beim ersten Abrufen in privaten Variablen zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="bac3b-125">If an application uses a particular set of metadata more than one time, it will probably benefit from caching the information in private variables when it is first obtained.</span></span> <span data-ttu-id="bac3b-126">Dadurch werden spätere Aufrufe an die ODBC-Katalogfunktionen für die gleichen Informationen vermieden, durch die der Treiber zu Roundtrips zum Server gezwungen wird.</span><span class="sxs-lookup"><span data-stu-id="bac3b-126">This prevents later calls to the ODBC catalog functions for the same information, which force the driver to make round trips to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac3b-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bac3b-127">See Also</span></span>  
 [<span data-ttu-id="bac3b-128">Verarbeitungsergebnisse &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="bac3b-128">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  