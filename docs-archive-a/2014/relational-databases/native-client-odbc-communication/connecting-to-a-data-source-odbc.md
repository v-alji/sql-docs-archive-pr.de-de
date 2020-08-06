---
title: Herstellen einer Verbindung mit einer Datenquelle (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617944"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="9e654-102">Herstellen einer Verbindung mit einer Datenquelle (ODBC)</span><span class="sxs-lookup"><span data-stu-id="9e654-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="9e654-103">Nach dem Zuweisen der Umgebungs- und Verbindungshandles und dem Festlegen der Verbindungsattribute stellt die Anwendung eine Verbindung zur Datenquelle oder zum Treiber her.</span><span class="sxs-lookup"><span data-stu-id="9e654-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="9e654-104">Es gibt drei Funktionen, die Sie verwenden können, um eine Verbindung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="9e654-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="9e654-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="9e654-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="9e654-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="9e654-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="9e654-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="9e654-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="9e654-108">Weitere Informationen zum Herstellen von Verbindungen mit einer Datenquelle, einschließlich der verschiedenen Optionen für Verbindungs Zeichenfolgen, finden [Sie unter Verwenden von Verbindungs Zeichenfolgen-Schlüsselwörtern mit SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9e654-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="9e654-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="9e654-109">SQLConnect</span></span>  
 <span data-ttu-id="9e654-110">**SQLCONNECT** ist die einfachste Verbindungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="9e654-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="9e654-111">Sie akzeptiert drei Parameter: Datenquellenname, Benutzer-ID und Kennwort.</span><span class="sxs-lookup"><span data-stu-id="9e654-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="9e654-112">Verwenden Sie **SQLCONNECT** , wenn diese drei Parameter alle Informationen enthalten, die zum Herstellen einer Verbindung mit der Datenbank erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9e654-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="9e654-113">Erstellen Sie dazu eine Liste mit Datenquellen mithilfe von **SQLDataSources**. Benutzer zur Eingabe einer Datenquelle, Benutzer-ID und eines Kennworts auffordern und dann **SQLCONNECT**aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9e654-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="9e654-114">**SQLCONNECT** geht davon aus, dass ein Datenquellen Name, eine Benutzer-ID und ein Kennwort zum Herstellen einer Verbindung mit einer Datenquelle ausreichen und dass die ODBC-Datenquelle alle anderen Informationen enthält, die der ODBC-Treiber zum Herstellen der Verbindung benötigt.</span><span class="sxs-lookup"><span data-stu-id="9e654-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="9e654-115">Im Gegensatz zu [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) und [sqlbrowseconnetct](../native-client-odbc-api/sqlbrowseconnect.md)verwendet **SQLCONNECT** keine Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e654-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="9e654-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="9e654-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="9e654-117">**SQLDriverConnect** wird verwendet, wenn mehr Informationen als Name der Datenquelle, Benutzer-ID und Kennwort erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9e654-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="9e654-118">Einer der Parameter für **SQLDriverConnect** ist eine Verbindungs Zeichenfolge, die Treiber spezifische Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="9e654-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="9e654-119">Sie können **SQLDriverConnect** anstelle von **SQLCONNECT** aus den folgenden Gründen verwenden:</span><span class="sxs-lookup"><span data-stu-id="9e654-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="9e654-120">Um zum Zeitpunkt des Verbindungsaufbaus treiberspezifische Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e654-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="9e654-121">Um anzugeben, dass der Treiber den Benutzer zur Eingabe von Verbindungsinformationen auffordert.</span><span class="sxs-lookup"><span data-stu-id="9e654-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="9e654-122">Um eine Verbindung herzustellen, ohne eine ODBC-Datenquelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e654-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="9e654-123">Die **SQLDriverConnect** -Verbindungs Zeichenfolge enthält eine Reihe von Schlüsselwort-Wert-Paaren, mit denen alle von einem ODBC-Treiber unterstützten Verbindungsinformationen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9e654-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="9e654-124">Bei allen vom Treiber unterstützten Verbindungsinformationen unterstützt jeder Treiber über die treiberspezifischen Schlüsselwörter hinaus die standardmäßigen ODBC-Schlüsselwörter (DSN, FILEDSN, DRIVER, UID, PWD und SAVEFILE).</span><span class="sxs-lookup"><span data-stu-id="9e654-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="9e654-125">**SQLDriverConnect** kann verwendet werden, um eine Verbindung ohne Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9e654-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="9e654-126">Beispielsweise kann eine Anwendung, die so konzipiert ist, dass Sie eine DSN-lose Verbindung mit einer Instanz von herstellt, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQLDriverConnect** mit einer Verbindungs Zeichenfolge aufruft, die die Anmelde-ID, das Kennwort, die Netzwerk Bibliothek, den Servernamen für die Verbindung und die zu verwendende Standarddatenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="9e654-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="9e654-127">Bei der Verwendung von **SQLDriverConnect**stehen zwei Optionen zur Verfügung, um den Benutzer zur Eingabe von erforderlichen Verbindungsinformationen aufzufordern:</span><span class="sxs-lookup"><span data-stu-id="9e654-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="9e654-128">Dialogfeld "Anwendung"</span><span class="sxs-lookup"><span data-stu-id="9e654-128">Application dialog box</span></span>  
  
     <span data-ttu-id="9e654-129">Sie können ein Anwendungs Dialogfeld erstellen, in dem Sie zur Eingabe von Verbindungsinformationen aufgefordert werden, und dann **SQLDriverConnect** mit einem NULL-Fenster Handle und *DriverCompletion* auf SQL_DRIVER_NOPROMPT festlegen.</span><span class="sxs-lookup"><span data-stu-id="9e654-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="9e654-130">Diese Parametereinstellungen verhindern, dass der ODBC-Treiber ein eigenes Dialogfeld öffnet.</span><span class="sxs-lookup"><span data-stu-id="9e654-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="9e654-131">Diese Methode wird verwendet, wenn die Benutzeroberfläche der Anwendung gesteuert werden muss.</span><span class="sxs-lookup"><span data-stu-id="9e654-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="9e654-132">Dialogfeld "Filter"</span><span class="sxs-lookup"><span data-stu-id="9e654-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="9e654-133">Sie können die Anwendung so codieren, dass Sie ein gültiges Fenster Handle an **SQLDriverConnect** übergibt, und den *DriverCompletion* -Parameter auf SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT oder SQL_DRIVER_COMPLETE_REQUIRED festlegen.</span><span class="sxs-lookup"><span data-stu-id="9e654-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="9e654-134">Der Treiber generiert dann ein Dialogfeld, um den Benutzer zur Eingabe von Verbindungsinformationen aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="9e654-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="9e654-135">Diese Methode vereinfacht den Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="9e654-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="9e654-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="9e654-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="9e654-137">**Sqlbrowseconnetct**verwendet, wie **SQLDriverConnect**, eine Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9e654-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="9e654-138">Mithilfe von **sqlbrowseconnetct**kann eine Anwendung jedoch zur Laufzeit eine vollständige Verbindungs Zeichenfolge iterativ mit der Datenquelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e654-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="9e654-139">Dadurch kann die Anwendung zwei Funktionen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9e654-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="9e654-140">Erstellen eigener Dialogfelder, um zur Eingabe dieser Informationen aufzufordern, wodurch die Kontrolle über die Benutzeroberfläche beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="9e654-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="9e654-141">Durchsuchen des Systems nach Datenquellen, die von einem bestimmten Treiber verwendet werden können. Dies sollte nach Möglichkeit in mehreren Schritten erfolgen.</span><span class="sxs-lookup"><span data-stu-id="9e654-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="9e654-142">Beispielsweise kann der Benutzer zunächst das Netzwerk nach Servern durchsuchen und, sobald er einen Server ausgewählt hat, diesen nach Datenbanken durchsuchen, auf die der Treiber zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9e654-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="9e654-143">Wenn **sqlbrowseconnetct** eine erfolgreiche Verbindung abschließt, wird eine Verbindungs Zeichenfolge zurückgegeben, die bei nachfolgenden Aufrufen von **SQLDriverConnect**verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9e654-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="9e654-144">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber gibt bei erfolgreicher Ausführung von **SQLCONNECT**, **SQLDriverConnect**oder **sqlbrowseconnct**immer SQL_SUCCESS_WITH_INFO zurück.</span><span class="sxs-lookup"><span data-stu-id="9e654-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="9e654-145">Wenn eine ODBC-Anwendung nach dem Abrufen von SQL_SUCCESS_WITH_INFO **SQLGetDiagRec** aufruft, kann Sie folgende Meldungen erhalten:</span><span class="sxs-lookup"><span data-stu-id="9e654-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="9e654-146">5701</span><span class="sxs-lookup"><span data-stu-id="9e654-146">5701</span></span>  
 <span data-ttu-id="9e654-147">Gibt an, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den Kontext des Benutzers in die in der Datenquelle angegebene Standarddatenbank oder, wenn für die Datenquelle keine Standarddatenbank angegeben ist, in die Standarddatenbank der zur Verbindung verwendeten Anmelde-ID einfügt.</span><span class="sxs-lookup"><span data-stu-id="9e654-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="9e654-148">5703</span><span class="sxs-lookup"><span data-stu-id="9e654-148">5703</span></span>  
 <span data-ttu-id="9e654-149">Gibt die auf dem Server verwendete Sprache an.</span><span class="sxs-lookup"><span data-stu-id="9e654-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="9e654-150">Bei einer erfolgreichen Verbindung wird die folgende Meldung vom Systemadministrator zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="9e654-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="9e654-151">Sie können die Meldungen 5701 und 5703 ignorieren; sie dienen nur zu Informationszwecken.</span><span class="sxs-lookup"><span data-stu-id="9e654-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="9e654-152">Den Rückgabecode SQL_SUCCESS_WITH_INFO hingegen sollten Sie nicht ignorieren, da auch andere Meldungen als 5701 oder 5703 zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="9e654-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="9e654-153">Wenn ein Treiber z. b. eine Verbindung mit einem Server herstellt, auf dem eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit veralteten gespeicherten Katalog Prozeduren ausgeführt wird, ist einer der Fehler, der durch **SQLGetDiagRec** nach einer SQL_SUCCESS_WITH_INFO zurückgegeben wird,</span><span class="sxs-lookup"><span data-stu-id="9e654-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="9e654-154">Die Fehler Behandlungs Funktion einer Anwendung für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Verbindungen sollte **SQLGetDiagRec** aufrufen, bis SQL_NO_DATA zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9e654-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="9e654-155">Anschließend sollte Sie auf alle Nachrichten reagieren, die nicht mit einem *pfNative* -Code von 5701 oder 5703 zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="9e654-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e654-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e654-156">See Also</span></span>  
 [<span data-ttu-id="9e654-157">Kommunikation mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="9e654-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
