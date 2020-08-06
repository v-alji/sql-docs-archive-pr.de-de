---
title: SQLGetConnectAttr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607751"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="fe81f-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="fe81f-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="fe81f-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber definiert treiberspezifische Verbindungsattribute.</span><span class="sxs-lookup"><span data-stu-id="fe81f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="fe81f-104">Einige der Attribute sind für verfügbar `SQLGetConnectAttr` , und die-Funktion wird verwendet, um Ihre aktuellen Einstellungen zu melden.</span><span class="sxs-lookup"><span data-stu-id="fe81f-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="fe81f-105">Die für diese Attribute gemeldeten Werte werden erst nach dem Herstellen einer Verbindung oder dem Festlegen des Attributs mithilfe von [SQLSetConnectAttr](sqlsetconnectattr.md)sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="fe81f-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="fe81f-106">In diesem Thema sind die schreibgeschützten Attribute aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe81f-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="fe81f-107">Weitere Informationen zu den anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC-treiberspezifischen Verbindungs Attributen für Native Client finden Sie unter [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="fe81f-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="fe81f-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="fe81f-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="fe81f-109">Das SQL_COPT_SS_CONNECTION_DEAD-Attribut meldet den Status einer Verbindung zu einem Server.</span><span class="sxs-lookup"><span data-stu-id="fe81f-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="fe81f-110">Der Treiber sendet eine Abfrage an das Netzwerk bezüglich des aktuellen Status der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="fe81f-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe81f-111">Das Standard-ODBC-Verbindungsattribut SQL_ATTR_CONNECTION_DEAD gibt den letzten Status der Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="fe81f-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="fe81f-112">Dabei handelt es sich nicht zwingend um den aktuellen Verbindungsstatus.</span><span class="sxs-lookup"><span data-stu-id="fe81f-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="fe81f-113">Wert</span><span class="sxs-lookup"><span data-stu-id="fe81f-113">Value</span></span>|<span data-ttu-id="fe81f-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe81f-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe81f-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="fe81f-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="fe81f-116">Die Verbindung zum Server wurde unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="fe81f-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="fe81f-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="fe81f-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="fe81f-118">Die Verbindung besteht und ist für die Anweisungsverarbeitung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe81f-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="fe81f-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="fe81f-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="fe81f-120">Das SQL_COPT_SS_CLIENT_CONNECTION_ID-Attribut ruft die Clientverbindungs-ID ab, die dann für die Suche verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="fe81f-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="fe81f-121">Diagnoseinformationen im XEvents-Protokoll, wenn aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="fe81f-122">Verbindungsfehlerinformationen im Verbindungsringpuffer.</span><span class="sxs-lookup"><span data-stu-id="fe81f-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="fe81f-123">Diagnoseinformationen in den Datenzugriff-Ablaufverfolgungsprotokollen, wenn aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="fe81f-124">Weitere Informationen finden Sie unter [zugreifen auf Diagnoseinformationen im Protokoll für erweiterte Ereignisse](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="fe81f-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="fe81f-125">Wert</span><span class="sxs-lookup"><span data-stu-id="fe81f-125">Value</span></span>|<span data-ttu-id="fe81f-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe81f-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe81f-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="fe81f-127">SQL_ERROR</span></span>|<span data-ttu-id="fe81f-128">Die Verbindung konnte nicht hergestellt werden</span><span class="sxs-lookup"><span data-stu-id="fe81f-128">The connection failed.</span></span>|  
|<span data-ttu-id="fe81f-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="fe81f-129">SQL_SUCCESS</span></span>|<span data-ttu-id="fe81f-130">Die Verbindung wurde erfolgreich hergestellt.</span><span class="sxs-lookup"><span data-stu-id="fe81f-130">The connection succeeded.</span></span> <span data-ttu-id="fe81f-131">Die Clientverbindungs-ID befindet sich im Ausgabepuffer.</span><span class="sxs-lookup"><span data-stu-id="fe81f-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="fe81f-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="fe81f-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="fe81f-133">Das SQL_COPT_SS_PERF_DATA-Attribut gibt einen Zeiger auf eine SQLPERF-Struktur zurück, die die aktuellen statistischen Daten zur Treiberleistung enthält.</span><span class="sxs-lookup"><span data-stu-id="fe81f-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="fe81f-134">`SQLGetConnectAttr`gibt NULL zurück, wenn die Leistungs Protokollierung nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fe81f-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="fe81f-135">Die Statistik in der SQLPERF-Struktur wird nicht dynamisch vom Treiber aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="fe81f-136">`SQLGetConnectAttr`Wird jedes Mal aufgerufen, wenn die Leistungsstatistik aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="fe81f-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="fe81f-137">Wert</span><span class="sxs-lookup"><span data-stu-id="fe81f-137">Value</span></span>|<span data-ttu-id="fe81f-138">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe81f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe81f-139">NULL</span><span class="sxs-lookup"><span data-stu-id="fe81f-139">NULL</span></span>|<span data-ttu-id="fe81f-140">Die Leistungsprotokollierung wird nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="fe81f-141">Ein beliebiger anderer Wert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-141">Any other value</span></span>|<span data-ttu-id="fe81f-142">Ein Zeiger auf eine SQLPERF-Struktur.</span><span class="sxs-lookup"><span data-stu-id="fe81f-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="fe81f-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="fe81f-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="fe81f-144">Das SQL_COPT_SS_PERF_QUERY-Attribut gibt TRUE zurück, wenn die Protokollierung von Abfragen mit langer Ausführungszeit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fe81f-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="fe81f-145">Die Anforderung gibt FALSE zurück, wenn die Abfrageprotokollierung nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="fe81f-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="fe81f-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="fe81f-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="fe81f-147">Das SQL_COPT_SS_USER_DATA-Attribut ruft den Benutzerdatenzeiger ab.</span><span class="sxs-lookup"><span data-stu-id="fe81f-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="fe81f-148">Benutzerdaten werden im Besitz des Client Speichers gespeichert und pro Verbindung aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fe81f-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="fe81f-149">Wenn der Benutzerdatenzeiger nicht festgelegt wurde, wird SQL_UD_NOTSET, ein NULL-Zeiger, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe81f-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="fe81f-150">Wert</span><span class="sxs-lookup"><span data-stu-id="fe81f-150">Value</span></span>|<span data-ttu-id="fe81f-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe81f-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fe81f-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="fe81f-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="fe81f-153">Es ist kein Benutzerdatenzeiger festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fe81f-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="fe81f-154">Ein beliebiger anderer Wert.</span><span class="sxs-lookup"><span data-stu-id="fe81f-154">Any other value</span></span>|<span data-ttu-id="fe81f-155">Ein Zeiger auf die Benutzerdaten.</span><span class="sxs-lookup"><span data-stu-id="fe81f-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="fe81f-156">SQLGetConnectAttr-Unterstützung für Dienstprinzipalnamen (SPNs)</span><span class="sxs-lookup"><span data-stu-id="fe81f-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="fe81f-157">SQLGetConnectAttr kann verwendet werden, um den Wert der neuen Verbindungs Attribute SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED und SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD abzufragen.</span><span class="sxs-lookup"><span data-stu-id="fe81f-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="fe81f-158">(SQLGetConnectOption kann auch verwendet werden, um diese Werte abzufragen.)</span><span class="sxs-lookup"><span data-stu-id="fe81f-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="fe81f-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD ist nur für geöffnete Verbindungen verfügbar, die die Windows-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe81f-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="fe81f-160">Wenn SQL_COPT_SS_SERVER_SPN oder SQL_COPT_SS_FAILOVER_PARTNER nicht festgelegt wurde, wird der Standardwert (eine leere Zeichenfolge) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe81f-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="fe81f-161">Weitere Informationen zu SPNs finden Sie unter [Dienst Prinzipal Namen &#40;SPNs&#41; in Client Verbindungen &#40;ODBC-&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fe81f-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe81f-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe81f-162">See Also</span></span>  
 <span data-ttu-id="fe81f-163">[SQLGetConnectAttr-Funktion](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="fe81f-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="fe81f-164">[Details zur ODBC-API-Implementierung](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="fe81f-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="fe81f-165">[Festlegen QUOTED_IDENTIFIER &#40;Transact-SQL-&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe81f-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="fe81f-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe81f-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="fe81f-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fe81f-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="fe81f-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fe81f-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
