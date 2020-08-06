---
title: Abrufen von Resultsetinformationen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f7ed275eb9b6558a77160c3c7fb2fc233c199cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616042"
---
# <a name="retrieve-result-set-information-odbc"></a><span data-ttu-id="529c8-102">Abrufen von Resultsetinformationen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="529c8-102">Retrieve Result Set Information (ODBC)</span></span>
    
### <a name="to-get-information-about-a-result-set"></a><span data-ttu-id="529c8-103">So rufen Sie Informationen zu einem Resultset ab</span><span class="sxs-lookup"><span data-stu-id="529c8-103">To get information about a result set</span></span>  
  
1.  <span data-ttu-id="529c8-104">Führen Sie [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) aus, um die Anzahl der Spalten im Resultset abzurufen.</span><span class="sxs-lookup"><span data-stu-id="529c8-104">Call [SQLNumResultCols](../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns in the result set.</span></span>  
  
2.  <span data-ttu-id="529c8-105">Für jede Spalte im Resultset führt die Anwendung nun Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="529c8-105">For each column in the result set:</span></span>  
  
    -   <span data-ttu-id="529c8-106">Führen Sie [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) aus, um Informationen über die Ergebnisspalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="529c8-106">Call [SQLDescribeCol](../native-client-odbc-api/sqldescribecol.md) to get information about the result column.</span></span>  
  
     <span data-ttu-id="529c8-107">oder</span><span class="sxs-lookup"><span data-stu-id="529c8-107">Or</span></span>  
  
    -   <span data-ttu-id="529c8-108">Führen Sie [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) aus, um bestimmte Deskriptorinformationen über die Ergebnisspalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="529c8-108">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) to get specific descriptor information about the result column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529c8-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="529c8-109">See Also</span></span>  
 <span data-ttu-id="529c8-110">[Themen zur Vorgehensweise bei der Verarbeitung von Ergebnissen &#40;ODBC-&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="529c8-110">[Processing Results How-to Topics &#40;ODBC&#41;](../../database-engine/dev-guide/processing-results-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="529c8-111">Bestimmen der Eigenschaften eines Resultsets &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="529c8-111">Determining the Characteristics of a Result Set &#40;ODBC&#41;</span></span>](../native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
