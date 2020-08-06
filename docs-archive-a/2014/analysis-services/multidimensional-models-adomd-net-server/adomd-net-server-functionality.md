---
title: ADOMD.NET-Server Funktionalität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696278"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="628f4-102">ADOMD.NET-Serverfunktionalität</span><span class="sxs-lookup"><span data-stu-id="628f4-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="628f4-103">Alle ADOMD.NET-Serverobjekte ermöglichen schreibgeschützten Zugriff auf die Daten und Metadaten auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="628f4-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="628f4-104">Verwenden Sie das ADOMD.NET-Serverobjektmodell, um Daten und Metadaten abzurufen, da das Serverobjektmodell keine Schemarowsets unterstützt.</span><span class="sxs-lookup"><span data-stu-id="628f4-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="628f4-105">Mit ADOMD.NET-Server Objekten können Sie eine benutzerdefinierte Funktion (User Defined Function, UDF) oder eine gespeicherte Prozedur für erstellen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="628f4-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="628f4-106">Diese prozessinternen Methoden werden durch Abfrageanweisungen aufgerufen, die in Sprachen wie Multidimensional Expressions (MDX), Data Mining Extensions (DMX) oder SQL erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="628f4-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="628f4-107">Diese prozessinternen Methoden stellen zudem zusätzliche Funktionen bereit, die nicht den Wartezeiten eines Netzwerks unterworfen sind.</span><span class="sxs-lookup"><span data-stu-id="628f4-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="628f4-108">Das [Microsoft. AnalysisServices. AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) -Objekt unterstützt nur DMX.</span><span class="sxs-lookup"><span data-stu-id="628f4-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="628f4-109">Was ist eine UDF?</span><span class="sxs-lookup"><span data-stu-id="628f4-109">What is a UDF?</span></span>  
 <span data-ttu-id="628f4-110">Eine *UDF* ist eine Methode, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="628f4-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="628f4-111">Sie können die UDF im Kontext einer Abfrage aufrufen.</span><span class="sxs-lookup"><span data-stu-id="628f4-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="628f4-112">Die UDF unterstützt eine beliebige Anzahl von Parametern.</span><span class="sxs-lookup"><span data-stu-id="628f4-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="628f4-113">Die UDF kann zahlreiche Datentypen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="628f4-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="628f4-114">Im folgenden Beispiel wird die fiktive UDF `FinalSalesNumber` verwendet:</span><span class="sxs-lookup"><span data-stu-id="628f4-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="628f4-115">Was ist eine gespeichert Prozedur?</span><span class="sxs-lookup"><span data-stu-id="628f4-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="628f4-116">Eine *gespeicherte Prozedur* ist eine Methode, die über die folgenden Eigenschaften verfügt:</span><span class="sxs-lookup"><span data-stu-id="628f4-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="628f4-117">Sie sollten eine gespeicherte Prozedur eigenständig mit der MDX-Anweisung "Statement [" aufzurufen](/sql/mdx/mdx-data-manipulation-call) .</span><span class="sxs-lookup"><span data-stu-id="628f4-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="628f4-118">Eine gespeicherte Prozedur unterstützt eine beliebige Anzahl von Parametern.</span><span class="sxs-lookup"><span data-stu-id="628f4-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="628f4-119">Eine gespeicherte Prozedur kann ein Dataset, einen `IDataReader` oder ein leeres Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="628f4-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="628f4-120">Im folgenden Beispiel wird die fiktive gespeicherte Prozedur `FinalSalesNumbers` verwendet:</span><span class="sxs-lookup"><span data-stu-id="628f4-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="628f4-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="628f4-121">See Also</span></span>  
 [<span data-ttu-id="628f4-122">ADOMD.NET-Serverprogrammierung</span><span class="sxs-lookup"><span data-stu-id="628f4-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
