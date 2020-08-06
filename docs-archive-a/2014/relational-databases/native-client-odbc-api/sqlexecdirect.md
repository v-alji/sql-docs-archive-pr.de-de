---
title: SQLExecDirect | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLExecDirect function
ms.assetid: e7c2a5b5-83f4-4c72-9aca-7b9fb4748b11
author: rothja
ms.author: jroth
ms.openlocfilehash: 68188506546e7b4a5dd4c05bc9a94cbf34300001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616992"
---
# <a name="sqlexecdirect"></a><span data-ttu-id="b6a53-102">SQLExecDirect</span><span class="sxs-lookup"><span data-stu-id="b6a53-102">SQLExecDirect</span></span>
  <span data-ttu-id="b6a53-103">Wenn das Anweisungs Attribut SQL_SOPT_SS_PARAM_FOCUS nicht 0 ist, gibt SQLExecDirect SQL_ERROR zurück und generiert einen Diagnosedaten Satz mit SQLSTATE = HY024 und der Meldung "Ungültiger Attribut Wert, SQL_SOPT_SS_PARAM_FOCUS (muss zur Ausführungszeit NULL sein)".</span><span class="sxs-lookup"><span data-stu-id="b6a53-103">If the statement attribute SQL_SOPT_SS_PARAM_FOCUS is not 0, SQLExecDirect will return SQL_ERROR and generate a diagnostic record with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span> <span data-ttu-id="b6a53-104">Weitere Informationen zu SQL_SOPT_SS_PARAM_FOCUS finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b6a53-104">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="b6a53-105">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="b6a53-105">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a53-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6a53-106">See Also</span></span>  
 <span data-ttu-id="b6a53-107">[SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=80709) </span><span class="sxs-lookup"><span data-stu-id="b6a53-107">[SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=80709) </span></span>  
 [<span data-ttu-id="b6a53-108">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="b6a53-108">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
