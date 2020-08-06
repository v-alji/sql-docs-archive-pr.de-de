---
title: Behandeln von Fehlern und Meldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC error handling, about error handling
- errors [ODBC]
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], about messages
- ODBC error handling
- SQL_INVALID_HANDLE return code
- errors [ODBC], about error handling
- messages [ODBC]
ms.assetid: 74ea9630-e482-4a46-bb45-f5234f079b48
author: rothja
ms.author: jroth
ms.openlocfilehash: 4701b3224b87e7d19f1121f193d4be20f9d4c441
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698186"
---
# <a name="handling-errors-and-messages"></a><span data-ttu-id="cda38-102">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="cda38-102">Handling Errors and Messages</span></span>
  <span data-ttu-id="cda38-103">Wenn eine Anwendung eine ODBC-Funktion aufruft, führt der Treiber die Funktion aus und gibt Diagnoseinformationen zurück: Ein Rückgabecode gibt das Ergebnis einer ODBC-Funktion zurück (Erfolg oder Fehlschlagen), und Diagnosedatensätze liefern detaillierte Informationen über die Funktion.</span><span class="sxs-lookup"><span data-stu-id="cda38-103">When an application calls an ODBC function, the driver executes the function and returns diagnostic information in two ways: A return code indicates the overall success or failure of an ODBC function, and diagnostic records provide detailed information about the function.</span></span> <span data-ttu-id="cda38-104">Diagnosedatensätze enthalten einen Headerdatensatz und Statusdatensätze.</span><span class="sxs-lookup"><span data-stu-id="cda38-104">Diagnostic records include a header record and status records.</span></span> <span data-ttu-id="cda38-105">Auch wenn die Funktion erfolgreich ausgeführt wurde, wird zumindest ein Diagnosedatensatz, der Headerdatensatz, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cda38-105">At least one diagnostic record, the header record, is returned even if the function succeeds.</span></span>  
  
 <span data-ttu-id="cda38-106">Die Diagnoseinformationen dienen während der Entwicklung zur Erfassung von Programmierfehlern wie ungültigen Handles und Syntaxfehlern in hartcodierten SQL-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="cda38-106">Diagnostic information is used at development time to catch programming errors, such as invalid handles and syntax errors in hard-coded SQL statements.</span></span> <span data-ttu-id="cda38-107">Darüber hinaus dienen sie zur Laufzeit dazu, Laufzeitfehler und Warnungen zu erfassen, beispielsweise das Abschneiden von Daten, Regelverstöße und Syntaxfehler in benutzerdefinierten SQL-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="cda38-107">It is also used at run time to catch run-time errors and warnings, such as data truncation, rule violations, and syntax errors in SQL statements entered by the user.</span></span> <span data-ttu-id="cda38-108">Die Programmlogik basiert im Allgemeinen auf Rückgabecodes.</span><span class="sxs-lookup"><span data-stu-id="cda38-108">Program logic is generally based on return codes.</span></span>  
  
 <span data-ttu-id="cda38-109">Nachdem eine Anwendung z. b. **SQLFetch** aufgerufen hat, um die Zeilen in einem Resultset abzurufen, gibt der Rückgabecode an, ob das Ende des Resultsets erreicht wurde (SQL_NO_DATA), ob Informationsmeldungen zurückgegeben wurden (SQL_SUCCESS_WITH_INFO) oder ob ein Fehler aufgetreten ist (SQL_ERROR).</span><span class="sxs-lookup"><span data-stu-id="cda38-109">For example, after an application calls **SQLFetch** to retrieve the rows in a result set, the return code indicates whether the end of the result set was reached (SQL_NO_DATA), if any informational messages were returned (SQL_SUCCESS_WITH_INFO), or if an error occurred (SQL_ERROR).</span></span>  
  
 <span data-ttu-id="cda38-110">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber etwas anderes als SQL_SUCCESS zurückgibt, kann die Anwendung **SQLGetDiagRec** aufrufen, um Informations-oder Fehlermeldungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cda38-110">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver returns anything other than SQL_SUCCESS, the application can call **SQLGetDiagRec** to retrieve any informational or error messages.</span></span> <span data-ttu-id="cda38-111">Verwenden Sie **SQLGetDiagRec** , um den Nachrichten Satz nach oben oder unten zu scrollen, wenn mehr als eine Nachricht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cda38-111">Use **SQLGetDiagRec** to scroll up and down the message set if there is more than one message.</span></span>  
  
 <span data-ttu-id="cda38-112">Der Rückgabecode SQL_INVALID_HANDLE gibt immer einen Programmierfehler an und sollte zur Laufzeit nie auftreten.</span><span class="sxs-lookup"><span data-stu-id="cda38-112">The return code SQL_INVALID_HANDLE always indicates a programming error and should never be encountered at run time.</span></span> <span data-ttu-id="cda38-113">Alle anderen Rückgabecodes stellen Laufzeitinformationen bereit, wenngleich SQL_ERROR einen Programmierfehler angeben kann.</span><span class="sxs-lookup"><span data-stu-id="cda38-113">All other return codes provide run-time information, although SQL_ERROR may indicate a programming error.</span></span>  
  
 <span data-ttu-id="cda38-114">Die ursprüngliche [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native API (DB-Library für C) ermöglicht einer Anwendung die Installation von Rückruf Fehlerbehandlung und Nachrichten Behandlung, die Fehler oder Meldungen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cda38-114">The original [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native API, DB-Library for C, allows an application to install callback error-handling and message-handling functions that return errors or messages.</span></span> <span data-ttu-id="cda38-115">Einige [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen, wie PRINT, RAISERROR, DBCC und SET, geben ihre Ergebnisse an die Meldungshandlerfunktion der DB-Library anstatt an ein Resultset zurück.</span><span class="sxs-lookup"><span data-stu-id="cda38-115">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, such as PRINT, RAISERROR, DBCC, and SET, return their results to the DB-Library message handler function instead of to a result set.</span></span> <span data-ttu-id="cda38-116">Jedoch verfügt die ODBC-API über keine solche Rückruffähigkeit.</span><span class="sxs-lookup"><span data-stu-id="cda38-116">However, the ODBC API has no such callback capability.</span></span> <span data-ttu-id="cda38-117">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber die von zurückgegebenen Nachrichten erkennt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , wird der ODBC-Rückgabecode auf SQL_SUCCESS_WITH_INFO oder SQL_ERROR festgelegt, und die Nachricht wird als mindestens ein Diagnosedaten Satz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cda38-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver detects messages coming back from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it sets the ODBC return code to SQL_SUCCESS_WITH_INFO or SQL_ERROR and returns the message as one or more diagnostic records.</span></span> <span data-ttu-id="cda38-118">Daher muss eine ODBC-Anwendung diese Rückgabecodes sorgfältig testen und **SQLGetDiagRec** aufrufen, um Nachrichten Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cda38-118">Therefore, an ODBC application must carefully test for these return codes and call **SQLGetDiagRec** to retrieve message data.</span></span>  
  
 <span data-ttu-id="cda38-119">Informationen zur Ablaufverfolgung von Fehlern finden Sie unter [Data Access Tracing (Ablaufverfolgung für den Datenzugriff)](https://go.microsoft.com/fwlink/?LinkId=125805).</span><span class="sxs-lookup"><span data-stu-id="cda38-119">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="cda38-120">Informationen zu Verbesserungen der in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] hinzugefügten Fehlerablaufverfolgung finden Sie unter [Zugreifen auf Diagnoseinformationen im Protokoll der erweiterten Ereignisse](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="cda38-120">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cda38-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cda38-121">In This Section</span></span>  
  
-   [<span data-ttu-id="cda38-122">Verarbeiten von Anweisungen, die Meldungen generieren</span><span class="sxs-lookup"><span data-stu-id="cda38-122">Processing Statements That Generate Messages</span></span>](processing-statements-that-generate-messages.md)  
  
-   [<span data-ttu-id="cda38-123">Diagnosedatensätze und -felder</span><span class="sxs-lookup"><span data-stu-id="cda38-123">Diagnostic Records and Fields</span></span>](diagnostic-records-and-fields.md)  
  
-   [<span data-ttu-id="cda38-124">Systemeigene Fehlernummern</span><span class="sxs-lookup"><span data-stu-id="cda38-124">Native Error Numbers</span></span>](native-error-numbers.md)  
  
-   [<span data-ttu-id="cda38-125">SQLSTATE &#40;ODBC-Fehler Codes&#41;</span><span class="sxs-lookup"><span data-stu-id="cda38-125">SQLSTATE &#40;ODBC Error Codes&#41;</span></span>](sqlstate-odbc-error-codes.md)  
  
-   [<span data-ttu-id="cda38-126">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="cda38-126">Error Messages</span></span>](error-messages.md)  
  
## <a name="see-also"></a><span data-ttu-id="cda38-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cda38-127">See Also</span></span>  
 [<span data-ttu-id="cda38-128">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cda38-128">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
