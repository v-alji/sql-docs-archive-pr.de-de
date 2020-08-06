---
title: SQLNumResultCols | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLNumResultCols function
ms.assetid: f79d8b3c-521e-4e50-a564-21d73ae5767b
author: rothja
ms.author: jroth
ms.openlocfilehash: 45e72165eef621dc377b02ed3d2e7e1e3cf7ab8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622063"
---
# <a name="sqlnumresultcols"></a><span data-ttu-id="d0656-102">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="d0656-102">SQLNumResultCols</span></span>
  <span data-ttu-id="d0656-103">Bei ausgeführten Anweisungen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nimmt der Native Client-ODBC-Treiber den Server nicht an, um die Anzahl der Spalten in einem Resultset zu melden.</span><span class="sxs-lookup"><span data-stu-id="d0656-103">For executed statements, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not visit the server to report the number of columns in a result set.</span></span> <span data-ttu-id="d0656-104">In diesem Fall `SQLNumResultCols` verursacht keinen Serverroundtrip.</span><span class="sxs-lookup"><span data-stu-id="d0656-104">In this case, `SQLNumResultCols` does not cause a server roundtrip.</span></span> <span data-ttu-id="d0656-105">Wie [SQLDescribeCol](sqldescribecol.md) und [SQLColAttribute](sqlcolattribute.md)wird durch `SQLNumResultCols` den Aufruf von für vorbereitete, aber nicht ausgeführte Anweisungen ein Serverroundtrip generiert.</span><span class="sxs-lookup"><span data-stu-id="d0656-105">Like [SQLDescribeCol](sqldescribecol.md) and [SQLColAttribute](sqlcolattribute.md), calling `SQLNumResultCols` on prepared but not executed statements generates a server roundtrip.</span></span>  
  
 <span data-ttu-id="d0656-106">Wenn eine [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung oder ein Anweisungsbatch mehrere Resultsets für Zeilen zurückgibt, kann die Anzahl der Resultset-Spalten sich von einem Set zum nächsten ändern.</span><span class="sxs-lookup"><span data-stu-id="d0656-106">When a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or statement batch returns multiple result row sets, it is possible for the number of result set columns to change from one set to another.</span></span> <span data-ttu-id="d0656-107">`SQLNumResultCols`muss für jeden Satz aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d0656-107">`SQLNumResultCols` should be called for each set.</span></span> <span data-ttu-id="d0656-108">Wenn sich die Anzahl der Spalten ändert, sollte die Anwendung Datenwerte vor dem Abrufen von Zeilenergebnissen erneut binden.</span><span class="sxs-lookup"><span data-stu-id="d0656-108">When the number of columns changes, the application should rebind data values prior to fetching row results.</span></span> <span data-ttu-id="d0656-109">Weitere Informationen zum Verarbeiten mehrerer Resultsets finden Sie unter [SQLMoreResults](sqlmoreresults.md).</span><span class="sxs-lookup"><span data-stu-id="d0656-109">For more information about handling multiple result set returns, see [SQLMoreResults](sqlmoreresults.md).</span></span>  
  
 <span data-ttu-id="d0656-110">Verbesserungen in der Datenbank-Engine, die mit beginnen [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , ermöglichen SQLNumResultCols, genauere Beschreibungen der erwarteten Ergebnisse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d0656-110">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow SQLNumResultCols to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="d0656-111">Diese präziseren Ergebnisse können sich von den Werten unterscheiden, die von SQLNumResultCols in früheren Versionen von zurückgegeben wurden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0656-111">These more accurate results may differ from the values returned by SQLNumResultCols in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0656-112">Weitere Informationen finden Sie unter [Metadatenermittlung](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="d0656-112">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0656-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0656-113">See Also</span></span>  
 <span data-ttu-id="d0656-114">[SQLNumResultCols-Funktion](https://go.microsoft.com/fwlink/?LinkId=59359) </span><span class="sxs-lookup"><span data-stu-id="d0656-114">[SQLNumResultCols Function](https://go.microsoft.com/fwlink/?LinkId=59359) </span></span>  
 [<span data-ttu-id="d0656-115">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="d0656-115">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
