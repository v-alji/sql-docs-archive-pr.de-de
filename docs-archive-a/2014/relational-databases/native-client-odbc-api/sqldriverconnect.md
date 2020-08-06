---
title: SQLDriverConnect | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721437"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="724f5-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="724f5-102">SQLDriverConnect</span></span>
  <span data-ttu-id="724f5-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber definiert Verbindungsattribute, die entweder Schlüsselwörter für Verbindungszeichenfolgen ersetzen oder verbessern.</span><span class="sxs-lookup"><span data-stu-id="724f5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="724f5-104">Mehrere Schlüsselwörter für Verbindungszeichenfolgen verfügen über vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber angegebene Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="724f5-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="724f5-105">Eine Liste der Schlüsselwörter, die im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber verfügbar sind, finden [Sie unter Verwenden von Verbindungs Zeichenfolgen-Schlüsselwörtern mit SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="724f5-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="724f5-106">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Verbindungs Attributen und Standardverhalten von Treibern finden Sie unter [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="724f5-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="724f5-107">Eine Erläuterung der Schlüsselwörter für Verbindungs Zeichenfolgen, die für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client gültig sind, finden [Sie unter Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="724f5-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="724f5-108">Wenn der `SQLDriverConnect` Wert für den *DriverCompletion* -Parameter SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE oder SQL_DRIVER_COMPLETE_REQUIRED ist, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ruft der Native Client-ODBC-Treiber Schlüsselwort Werte aus dem angezeigten Dialogfeld ab.</span><span class="sxs-lookup"><span data-stu-id="724f5-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="724f5-109">Wenn der Schlüsselwortwert in der Verbindungszeichenfolge übergeben wird und der Benutzer den Schlüsselwortwert nicht im Dialogfeld ändert, verwendet der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber den Wert aus der Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="724f5-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="724f5-110">Wenn der Wert in der Verbindungszeichenfolge nicht festgelegt wird und der Benutzer keine Zuweisung im Dialogfeld vornimmt, verwendet der Treiber den Standardwert.</span><span class="sxs-lookup"><span data-stu-id="724f5-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="724f5-111">`SQLDriverConnect`muss ein gültiges *WindowHandle* erhalten, wenn ein *DriverCompletion* -Wert die Anzeige des Dialog Felds Verbindung des Treibers erfordert (oder möglicherweise erfordert).</span><span class="sxs-lookup"><span data-stu-id="724f5-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="724f5-112">Ein ungültiges Handle gibt SQL_ERROR zurück.</span><span class="sxs-lookup"><span data-stu-id="724f5-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="724f5-113">Geben Sie entweder das Schlüsselwort DRIVER oder DSN an.</span><span class="sxs-lookup"><span data-stu-id="724f5-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="724f5-114">ODBC gibt an, dass ein Treiber das äußere linke dieser beiden Schlüsselwörter verwendet und das andere ignoriert, wenn beide Schlüsselwörter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="724f5-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="724f5-115">Wenn der Treiber angegeben ist oder der äußteste der beiden ist und der Wert des `SQLDriverConnect` *DriverCompletion* -Parameters SQL_DRIVER_NOPROMPT ist, sind das Server Schlüsselwort und ein entsprechender Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="724f5-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="724f5-116">Wenn SQL_DRIVER_NOPROMPT angegeben wird, müssen Schlüsselwörter für die Benutzerauthentifizierung mit Werten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="724f5-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="724f5-117">Der Treiber stellt sicher, dass entweder die Zeichenfolge "Trusted_Connection=yes" oder sowohl das UID- als auch das PWD-Schlüsselwort vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="724f5-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="724f5-118">Wenn der Wert für den *DriverCompletion* -Parameter SQL_DRIVER_NOPROMPT oder SQL_DRIVER_COMPLETE_REQUIRED ist und die Sprache oder Datenbank aus der Verbindungs Zeichenfolge stammt und ungültig ist, wird `SQLDriverConnect` SQL_ERROR zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="724f5-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="724f5-119">Wenn der Wert für den *DriverCompletion* -Parameter SQL_DRIVER_NOPROMPT oder SQL_DRIVER_COMPLETE_REQUIRED ist und die Sprache oder Datenbank aus den ODBC-Datenquellen Definitionen stammt und entweder ungültig ist, `SQLDriverConnect` verwendet die Standardsprache oder-Datenbank für die angegebene Benutzer-ID und gibt SQL_SUCCESS_WITH_INFO zurück.</span><span class="sxs-lookup"><span data-stu-id="724f5-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="724f5-120">Wenn der Wert für den *DriverCompletion* -Parameter SQL_DRIVER_COMPLETE oder SQL_DRIVER_PROMPT ist und die Sprache oder Datenbank ungültig ist, wird `SQLDriverConnect` das Dialogfeld erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="724f5-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="724f5-121">SQLDriverConnect-Unterstützung für hohe Verfügbarkeit, Wiederherstellung im Notfall</span><span class="sxs-lookup"><span data-stu-id="724f5-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="724f5-122">Weitere Informationen zum `SQLDriverConnect` Herstellen einer Verbindung mit einem Cluster mithilfe von [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] finden Sie [unter SQL Server Native Client-Unterstützung für hohe Verfügbarkeit und Notfall Wiederherstellung](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="724f5-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="724f5-123">SQLDriverConnect-Unterstützung für Dienstprinzipalnamen (Service Principal Names, SPNs)</span><span class="sxs-lookup"><span data-stu-id="724f5-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="724f5-124">SQLDDriverConnect verwendet das ODBC-Anmelde Dialogfeld, wenn die Eingabeaufforderung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="724f5-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="724f5-125">Damit können SPNs sowohl für den Prinzipalserver als auch für seinen Failoverpartner eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="724f5-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="724f5-126">SQLDriverConnect akzeptiert die neuen Verbindungs Zeichenfolgen `ServerSPN` -Schlüsselwörter und und `FailoverPartnerSPN` erkennt die neuen Verbindungs Attribute SQL_COPT_SS_SERVER_SPN und SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="724f5-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="724f5-127">Wenn ein Wert für ein Verbindungsattribut mehrfach angegeben wird, hat ein programmgesteuert festgelegter Wert Vorrang vor dem Wert in einem DSN und einem Wert in einer Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="724f5-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="724f5-128">Ein Wert in einem DSN hat Vorrang vor einem Wert in einer Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="724f5-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="724f5-129">Wenn eine Verbindung hergestellt wird, legt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client für SQL_COPT_SS_MUTUALLY_AUTHENTICATED und SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD die für das Herstellen der Verbindung zu verwendende Authentifizierungsmethode fest.</span><span class="sxs-lookup"><span data-stu-id="724f5-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="724f5-130">Weitere Informationen zu SPNs finden Sie unter [Dienst Prinzipal Namen &#40;SPNs&#41; in Client Verbindungen &#40;ODBC-&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="724f5-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="724f5-131">Beispiele</span><span class="sxs-lookup"><span data-stu-id="724f5-131">Examples</span></span>  
 <span data-ttu-id="724f5-132">Der folgende-Befehl veranschaulicht die geringste Menge an Daten, die für erforderlich ist `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="724f5-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="724f5-133">Die folgenden Verbindungs Zeichenfolgen veranschaulichen die minimal erforderlichen Daten, wenn der Wert für den *DriverCompletion* -Parameter SQL_DRIVER_NOPROMPT ist:</span><span class="sxs-lookup"><span data-stu-id="724f5-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="724f5-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="724f5-134">See Also</span></span>  
 <span data-ttu-id="724f5-135">[SQLDriverConnect-Funktion](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="724f5-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="724f5-136">[Details zur ODBC-API-Implementierung](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="724f5-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="724f5-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="724f5-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="724f5-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="724f5-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="724f5-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="724f5-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
