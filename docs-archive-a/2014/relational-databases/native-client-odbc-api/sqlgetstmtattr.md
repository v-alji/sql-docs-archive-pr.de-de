---
title: SQLGetStmtAttr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618675"
---
# <a name="sqlgetstmtattr"></a><span data-ttu-id="bad9e-102">'SQLGetStmtAttr'</span><span class="sxs-lookup"><span data-stu-id="bad9e-102">SQLGetStmtAttr</span></span>
  <span data-ttu-id="bad9e-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber erweitert SQLGetStmtAttr, um Treiber spezifische Anweisungs Attribute verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="bad9e-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver extends SQLGetStmtAttr to expose driver-specific statement attributes.</span></span>  
  
 <span data-ttu-id="bad9e-104">[SQLSetStmtAttr](sqlsetstmtattr.md) listet Anweisungsattribute auf, auf die sowohl Schreib- als auch Lesezugriff möglich ist.</span><span class="sxs-lookup"><span data-stu-id="bad9e-104">[SQLSetStmtAttr](sqlsetstmtattr.md) lists statement attributes that are both read and write.</span></span> <span data-ttu-id="bad9e-105">In diesem Thema sind die schreibgeschützten Anweisungsattribute aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bad9e-105">This topic lists the read only statement attributes.</span></span>  
  
## <a name="sql_sopt_ss_current_command"></a><span data-ttu-id="bad9e-106">SQL_SOPT_SS_CURRENT_COMMAND</span><span class="sxs-lookup"><span data-stu-id="bad9e-106">SQL_SOPT_SS_CURRENT_COMMAND</span></span>  
 <span data-ttu-id="bad9e-107">Das SQL_SOPT_SS_CURRENT_COMMAND-Attribut macht den aktuellen Befehl eines Befehlsbatches verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bad9e-107">The SQL_SOPT_SS_CURRENT_COMMAND attribute exposes the current command of a command batch.</span></span> <span data-ttu-id="bad9e-108">Zurückgegeben wird ein ganzzahliger Wert, der die Position des Befehls im Batch angibt.</span><span class="sxs-lookup"><span data-stu-id="bad9e-108">The return is an integer that specifies the location of the command in the batch.</span></span> <span data-ttu-id="bad9e-109">Der *ValuePtr* -Wert ist vom Typ SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="bad9e-109">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
## <a name="sql_sopt_ss_nocount_status"></a><span data-ttu-id="bad9e-110">SQL_SOPT_SS_NOCOUNT_STATUS</span><span class="sxs-lookup"><span data-stu-id="bad9e-110">SQL_SOPT_SS_NOCOUNT_STATUS</span></span>  
 <span data-ttu-id="bad9e-111">Das SQL_SOPT_SS_NOCOUNT_STATUS-Attribut zeigt die aktuelle Einstellung der NOCOUNT-Option an. Diese Option steuert, ob [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Anzahl der von einer Anweisung betroffenen Zeilen ausweist, wenn [SQLRowCount](sqlrowcount.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bad9e-111">The SQL_SOPT_SS_NOCOUNT_STATUS attribute indicates the current setting of the NOCOUNT option, which controls whether [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reports the numbers of rows affected by a statement when [SQLRowCount](sqlrowcount.md) is called.</span></span> <span data-ttu-id="bad9e-112">Der *ValuePtr* -Wert ist vom Typ SQLLEN.</span><span class="sxs-lookup"><span data-stu-id="bad9e-112">The *ValuePtr* value is of type SQLLEN.</span></span>  
  
|<span data-ttu-id="bad9e-113">Wert</span><span class="sxs-lookup"><span data-stu-id="bad9e-113">Value</span></span>|<span data-ttu-id="bad9e-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bad9e-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bad9e-115">SQL_NC_OFF</span><span class="sxs-lookup"><span data-stu-id="bad9e-115">SQL_NC_OFF</span></span>|<span data-ttu-id="bad9e-116">NOCOUNT ist OFF.</span><span class="sxs-lookup"><span data-stu-id="bad9e-116">NOCOUNT is OFF.</span></span> <span data-ttu-id="bad9e-117">SQLRowCount gibt die Anzahl der betroffenen Zeilen zurück.</span><span class="sxs-lookup"><span data-stu-id="bad9e-117">SQLRowCount returns number of rows affected.</span></span>|  
|<span data-ttu-id="bad9e-118">SQL_NC_ON</span><span class="sxs-lookup"><span data-stu-id="bad9e-118">SQL_NC_ON</span></span>|<span data-ttu-id="bad9e-119">NOCOUNT ist ON.</span><span class="sxs-lookup"><span data-stu-id="bad9e-119">NOCOUNT is ON.</span></span> <span data-ttu-id="bad9e-120">Die Anzahl der betroffenen Zeilen wird von SQLRowCount nicht zurückgegeben, und der zurückgegebene Wert ist 0.</span><span class="sxs-lookup"><span data-stu-id="bad9e-120">The number of rows affected is not returned by SQLRowCount and the returned value is 0.</span></span>|  
  
 <span data-ttu-id="bad9e-121">Wenn SQLRowCount 0 zurückgibt, sollte die Anwendung SQL_SOPT_SS_NOCOUNT_STATUS testen.</span><span class="sxs-lookup"><span data-stu-id="bad9e-121">If SQLRowCount returns 0, the application should test SQL_SOPT_SS_NOCOUNT_STATUS.</span></span> <span data-ttu-id="bad9e-122">Wenn SQL_NC_ON zurückgegeben wird, gibt der Wert 0 von SQLRowCount lediglich an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] keine Zeilen Anzahl zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="bad9e-122">If SQL_NC_ON is returned, the value of 0 from SQLRowCount only indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has not returned a row count.</span></span> <span data-ttu-id="bad9e-123">Wird SQL_NC_OFF zurückgegeben, bedeutet dies, dass NOCOUNT deaktiviert ist, und der Wert 0 aus SQLRowCount zeigt an, dass keine Zeilen von der Anweisung betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="bad9e-123">If SQL_NC_OFF is returned, it means that NOCOUNT is off and the value of 0 from SQLRowCount indicates that the statement did not affect any rows.</span></span>  
  
 <span data-ttu-id="bad9e-124">Anwendungen sollten den Wert von SQLRowCount nicht anzeigen, wenn SQL_SOPT_SS_NOCOUNT_STATUS SQL_NC_OFF ist.</span><span class="sxs-lookup"><span data-stu-id="bad9e-124">Applications should not display the value of SQLRowCount when SQL_SOPT_SS_NOCOUNT_STATUS is SQL_NC_OFF.</span></span> <span data-ttu-id="bad9e-125">Große Batches oder gespeicherte Prozeduren können mehrere SET NOCOUNT-Anweisungen enthalten. Daher kann nicht davon ausgegangen werden, dass SQL_SOPT_SS_NOCOUNT_STATUS konstant bleibt.</span><span class="sxs-lookup"><span data-stu-id="bad9e-125">Large batches or stored procedures can contain multiple SET NOCOUNT statements, so it cannot be assumed that SQL_SOPT_SS_NOCOUNT_STATUS remains constant.</span></span> <span data-ttu-id="bad9e-126">Diese Option sollte jedes Mal getestet werden, wenn SQLRowCount 0 zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bad9e-126">This option should be tested each time SQLRowCount returns 0.</span></span>  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a><span data-ttu-id="bad9e-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span><span class="sxs-lookup"><span data-stu-id="bad9e-127">SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT</span></span>  
 <span data-ttu-id="bad9e-128">Das SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT-Attribut gibt den Meldungstext für die Abfragebenachrichtigungsanforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="bad9e-128">The SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT attribute returns the message text for the query notification request.</span></span>  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a><span data-ttu-id="bad9e-129">'SQLGetStmtAttr' und Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="bad9e-129">SQLGetStmtAttr and Table-valued Parameters</span></span>  
 <span data-ttu-id="bad9e-130">SQLGetStmtAttr kann aufgerufen werden, um beim Arbeiten mit Tabellenwert Parametern den Wert von SQL_SOPT_SS_PARAM_FOCUS im Anwendungsparameter Deskriptor (APD) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bad9e-130">SQLGetStmtAttr can be called to get the value of SQL_SOPT_SS_PARAM_FOCUS in the application parameter descriptor (APD) when working with table-valued parameters.</span></span> <span data-ttu-id="bad9e-131">Weitere Informationen zu SQL_SOPT_SS_PARAM_FOCUS finden Sie unter [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="bad9e-131">For more information on SQL_SOPT_SS_PARAM_FOCUS, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="bad9e-132">Weitere Informationen zu Tabellenwert Parametern finden Sie unter [Tabellenwert Parameter &#40;ODBC-&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="bad9e-132">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad9e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bad9e-133">See Also</span></span>  
 <span data-ttu-id="bad9e-134">[SQLSetStmtAttr-Funktion](https://go.microsoft.com/fwlink/?LinkId=59370) </span><span class="sxs-lookup"><span data-stu-id="bad9e-134">[SQLSetStmtAttr Function](https://go.microsoft.com/fwlink/?LinkId=59370) </span></span>  
 [<span data-ttu-id="bad9e-135">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="bad9e-135">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
