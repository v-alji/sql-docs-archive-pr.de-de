---
title: Verwenden von Autofetch mit ODBC-Cursorn | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, autofetch
- autofetch option
- cursors [ODBC], autofetch
ms.assetid: 57bd55f4-8945-4d8d-9f58-d30c81d2a514
author: rothja
ms.author: jroth
ms.openlocfilehash: e3d9374cf9ceab4a7e73cc0059783486f2bf9c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620341"
---
# <a name="using-autofetch-with-odbc-cursors"></a><span data-ttu-id="8ec5a-102">Verwenden von Autofetch mit ODBC-Cursorn</span><span class="sxs-lookup"><span data-stu-id="8ec5a-102">Using Autofetch with ODBC Cursors</span></span>
  <span data-ttu-id="8ec5a-103">Wenn eine Verbindung mit einer Instanz von besteht [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützt der Native Client ODBC-Treiber bei Verwendung eines beliebigen Server Cursor Typs eine Autofetch-Option.</span><span class="sxs-lookup"><span data-stu-id="8ec5a-103">When connected to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports an autofetch option when using any server cursor type.</span></span> <span data-ttu-id="8ec5a-104">Mit Autofetch verfügt die **SQLExecute** -oder **SQLExecDirect** -Funktion, die den Cursor öffnet, auch über eine implizite [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST)-Funktion.</span><span class="sxs-lookup"><span data-stu-id="8ec5a-104">With autofetch, the **SQLExecute** or **SQLExecDirect** function that opens the cursor also has an implicit [SQLFetchScroll](../../native-client-odbc-api/sqlfetchscroll.md)(SQL_FIRST) function.</span></span> <span data-ttu-id="8ec5a-105">Die Zeilen des ersten Rowsets werden während der Ausführung der Anweisung an die gebundenen Anwendungsvariablen zurückgegeben, wodurch ein weiterer Roundtrip über das Netzwerk bis zum Server vermieden wird.</span><span class="sxs-lookup"><span data-stu-id="8ec5a-105">The rows comprising the first rowset are returned to the bound application variables as part of the statement execution, saving another roundtrip across the network to the server.</span></span> <span data-ttu-id="8ec5a-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) wird nicht unterstützt, wenn die Autofetch-Option aktiviert ist. die Resultsetspalten müssen an Programmvariablen gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="8ec5a-106">[SQLGetData](../../native-client-odbc-api/sqlgetdata.md) is not supported when the autofetch option is enabled; the result set columns must be bound to program variables.</span></span>  
  
 <span data-ttu-id="8ec5a-107">Autofetch wird von Anwendungen angefordert, wenn für das treiberspezifische SQL_SOPT_SS_CURSOR_OPTIONS-Anweisungsattribut SQL_CO_AF festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8ec5a-107">Applications request autofetch by setting the driver-specific SQL_SOPT_SS_CURSOR_OPTIONS statement attribute to SQL_CO_AF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec5a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ec5a-108">See Also</span></span>  
 [<span data-ttu-id="8ec5a-109">Details zur Cursor Programmierung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="8ec5a-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
