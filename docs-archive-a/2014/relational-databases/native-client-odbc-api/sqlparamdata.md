---
title: SQLParamData | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLParamData function
ms.assetid: 92349482-ea22-4a6a-8484-e9c6566794fa
author: rothja
ms.author: jroth
ms.openlocfilehash: a4e0e8b31a65f28ce83e0d114231bdedd7a35a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622062"
---
# <a name="sqlparamdata"></a><span data-ttu-id="63a7b-102">SQLParamData</span><span class="sxs-lookup"><span data-stu-id="63a7b-102">SQLParamData</span></span>
  <span data-ttu-id="63a7b-103">Wenn SQLParamData den einem Tabellenwert Parameter zugeordneten *ValuePtrPtr* -Wert zurückgibt, sollte die Anwendung SQLPutData mit *StrLen_Or_Ind*aufrufen.</span><span class="sxs-lookup"><span data-stu-id="63a7b-103">When SQLParamData returns the *ValuePtrPtr* associated with a table-valued parameter, the application should call SQLPutData with *StrLen_Or_Ind*.</span></span> <span data-ttu-id="63a7b-104">Wenn *StrLen_Or_Ind* einen Wert größer als 0 (null) aufweist, bedeutet dies, dass die Anwendung bereit ist, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Parameterdaten für die nächste Tabellenwert Parameter-Zeile sammelt.</span><span class="sxs-lookup"><span data-stu-id="63a7b-104">If *StrLen_Or_Ind* has a value greater than 0, it means that the application is ready for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to gather parameter data for the next table-valued parameter row.</span></span> <span data-ttu-id="63a7b-105">Wenn *StrLen_Or_Ind* den Wert 0 aufweist, bedeutet dies, dass es keine weiteren Daten Zeilen für den Tabellenwert Parameter gibt.</span><span class="sxs-lookup"><span data-stu-id="63a7b-105">If *StrLen_Or_Ind* has a value of 0, it means there are no more rows of data for the table-valued parameter.</span></span> <span data-ttu-id="63a7b-106">Weitere Informationen finden Sie unter [binden und Datenübertragung von Tabellenwert Parametern und Spaltenwerten](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="63a7b-106">For more information, see [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="63a7b-107">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="63a7b-107">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a7b-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63a7b-108">See Also</span></span>  
 <span data-ttu-id="63a7b-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span><span class="sxs-lookup"><span data-stu-id="63a7b-109">[SQLParamData](/sql/odbc/reference/syntax/sqlparamdata-function) </span></span>  
 [<span data-ttu-id="63a7b-110">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="63a7b-110">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
