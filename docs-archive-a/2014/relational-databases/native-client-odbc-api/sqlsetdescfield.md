---
title: SQLSetDescField | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLSetDescField function
ms.assetid: de4bed15-15be-4825-994c-1046255e725a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b8290fd90c0c9bb91f08d94e119689d38fbc04e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622045"
---
# <a name="sqlsetdescfield"></a><span data-ttu-id="a70c4-102">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="a70c4-102">SQLSetDescField</span></span>
  <span data-ttu-id="a70c4-103">SQLSetDescField kann verwendet werden, um Deskriptorfelder für Tabellenwert Parameter und Tabellenwert Parameter-Spalten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a70c4-103">SQLSetDescField can be used to set descriptor fields for table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="a70c4-104">Weitere Informationen zu den verfügbaren Feldern finden Sie unter [Tabellenwert Parameter-Deskriptorfelder](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) und [Deskriptorfelder für einzelne Tabellenwert Parameter-Spalten](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-104">For information about the available fields, see [Table-Valued Parameter Descriptor Fields](../native-client-odbc-table-valued-parameters/table-valued-parameter-descriptor-fields.md) and [Descriptor Fields for Table-Valued Parameter Constituent Columns](../native-client-odbc-table-valued-parameters/descriptor-fields-for-table-valued-parameter-constituent-columns.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a70c4-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a70c4-105">Remarks</span></span>  
 <span data-ttu-id="a70c4-106">Tabellenwertparameter-Spalten sind nur verfügbar, wenn das Deskriptorheaderfeld SQL_SOPT_SS_PARAM_FOCUS auf die Ordnungszahl eines Datensatzes festgelegt ist, für den SQL_DESC_TYPE auf SQL_SS_TABLE eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="a70c4-106">Table-valued parameter columns are only available when the descriptor header field SQL_SOPT_SS_PARAM_FOCUS is set to the ordinal of a record that has SQL_DESC_TYPE set to SQL_SS_TABLE.</span></span> <span data-ttu-id="a70c4-107">Weitere Informationen zu SQL_SOPT_SS_PARAM_FOCUS finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-107">For more information about SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="a70c4-108">Wenn versucht wird, SQL_SOPT_SS_PARAM_FOCUS auf die Ordnungszahl eines Parameters festzulegen, bei dem es sich nicht um einen Tabellenwert Parameter handelt, gibt SQLSetStmtAttr SQL_ERROR zurück, und es wird ein Diagnosedaten Satz mit SQLSTATE = HY024 und der Meldung "Ungültiger Attribut Wert" erstellt.</span><span class="sxs-lookup"><span data-stu-id="a70c4-108">If an attempt is made to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a parameter that is not a table-valued parameter, SQLSetStmtAttr returns SQL_ERROR, and a diagnostic record is created with SQLSTATE = HY024 and the message "Invalid attribute value".</span></span> <span data-ttu-id="a70c4-109">SQL_SOPT_SS_PARAM_FOCUS wird nicht geändert, wenn SQL_ERROR zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a70c4-109">SQL_SOPT_SS_PARAM_FOCUS is not changed when SQL_ERROR is returned.</span></span>  
  
 <span data-ttu-id="a70c4-110">Durch das Festlegen von SQL_SOPT_SS_PARAM_FOCUS auf 0 (null) wird der Zugriff auf Deskriptordatensätze für Parameter wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="a70c4-110">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores access to descriptor records for parameters.</span></span>  
  
 <span data-ttu-id="a70c4-111">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a70c4-112">SQLSetDescField-Unterstützung für erweiterte Funktionen zu Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="a70c4-112">SQLSetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a70c4-113">Datum/Uhrzeit-Funktionen wurden in ODBC verbessert.</span><span class="sxs-lookup"><span data-stu-id="a70c4-113">Date/time features have been enhanced in ODBC.</span></span> <span data-ttu-id="a70c4-114">Informationen über das für die neuen Datum/Uhrzeittypen verfügbare Deskriptorfeld finden Sie unter [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-114">For information about the descriptor field provided for the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="a70c4-115">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-115">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="a70c4-116">SQLSetDescField-Unterstützung für große CLR-UDTs</span><span class="sxs-lookup"><span data-stu-id="a70c4-116">SQLSetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="a70c4-117">SQLSetDescField unterstützt große benutzerdefinierte CLR-Typen (UDTs).</span><span class="sxs-lookup"><span data-stu-id="a70c4-117">SQLSetDescField supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="a70c4-118">Weitere Informationen finden Sie unter [große benutzerdefinierte CLR-Typen &#40;ODBC-&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlsetdescfield-support-for-sparse-columns"></a><span data-ttu-id="a70c4-119">SQLSetDescField-Unterstützung für Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="a70c4-119">SQLSetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="a70c4-120">SQLSetDecField kann verwendet werden, um SQL_SOPT_SS_NAME_SCOPE im Anwendungsparameter Deskriptor (Application Parameter Deskriptor, APD) auf die Werte SQL_SS_NAME_SCOPE_EXTENDED und SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a70c4-120">SQLSetDecField can be used to set SQL_SOPT_SS_NAME_SCOPE in the application parameter descriptor (APD) to the values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span>  
  
 <span data-ttu-id="a70c4-121">Weitere Informationen finden Sie [unter Unterstützung für sparsespalten &#40;ODBC-&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a70c4-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a70c4-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a70c4-122">See Also</span></span>  
 <span data-ttu-id="a70c4-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span><span class="sxs-lookup"><span data-stu-id="a70c4-123">[SQLSetDescField](https://go.microsoft.com/fwlink/?LinkId=80705) </span></span>  
 [<span data-ttu-id="a70c4-124">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="a70c4-124">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
