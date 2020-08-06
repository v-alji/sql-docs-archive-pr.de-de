---
title: Zuordnen von Handles und Herstellen einer Verbindung mit SQL Server (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725685"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="fdf3b-102">Zuordnen von Handles und Herstellen einer Verbindung mit SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fdf3b-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="fdf3b-103">So ordnen Sie Handles zu und stellen eine Verbindung mit SQL Server her</span><span class="sxs-lookup"><span data-stu-id="fdf3b-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="fdf3b-104">Schließen Sie die ODBC-Headerdateien Sql.h, Sqlext.h und Sqltypes.h ein.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="fdf3b-105">Schließen Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-treiberspezifische Headerdatei Odbcss.h ein.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="fdf3b-106">Ruft [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) mit einem `HandleType` von SQL_HANDLE_ENV auf, um ODBC zu initialisieren und ein Umgebungs Handle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="fdf3b-107">Rufen Sie [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) auf `Attribute` , wobei auf SQL_ATTR_ODBC_VERSION festgelegt und `ValuePtr` auf SQL_OV_ODBC3 festgelegt wird, um anzugeben, dass die Anwendung ODBC 3. x-Format-Funktionsaufrufe verwendet.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="fdf3b-108">Sie können optional auch [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) aufrufen, um andere Umgebungsoptionen festzulegen, oder [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) aufrufen, um Umgebungsoptionen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="fdf3b-109">Ruft [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) mit einem `HandleType` von SQL_HANDLE_DBC auf, um ein Verbindungs Handle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="fdf3b-110">Sie können optional auch [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) aufrufen, um Verbindungsoptionen festzulegen, oder [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) aufrufen, um die Verbindungsoptionen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="fdf3b-111">Verwenden Sie SQLConnect, um eine vorhandene Datenquelle zum Herstellen einer Verbindung mit zu verwenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fdf3b-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="fdf3b-112">oder</span><span class="sxs-lookup"><span data-stu-id="fdf3b-112">Or</span></span>  
  
     <span data-ttu-id="fdf3b-113">Verwenden Sie [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) , um eine Verbindungs Zeichenfolge zum Herstellen einer Verbindung mit zu verwenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fdf3b-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="fdf3b-114">Eine minimale vollständige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verbindungszeichenfolge weist eine der beiden folgenden Formen auf:</span><span class="sxs-lookup"><span data-stu-id="fdf3b-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="fdf3b-115">Wenn die Verbindungszeichenfolge nicht vollständig ist, kann `SQLDriverConnect` den Benutzer auffordern, die erforderlichen Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="fdf3b-116">Dies wird durch den für den *DriverCompletion* -Parameter angegebenen Wert gesteuert.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="fdf3b-117">\- oder -</span><span class="sxs-lookup"><span data-stu-id="fdf3b-117">\- or -</span></span>  
  
     <span data-ttu-id="fdf3b-118">Sie können [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) mehrmals auf iterative Weise aufzurufen, um die Verbindungs Zeichenfolge zu erstellen und eine Verbindung mit herzustellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fdf3b-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="fdf3b-119">Optional können Sie [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) aufrufen, um Treiber Attribute und das Verhalten für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="fdf3b-120">Ordnen Sie Anweisungen zu und verwenden Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="fdf3b-121">Führen Sie SQLDisconnect aus, um die Verbindung mit zu trennen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und das Verbindungs Handle für eine neue Verbindung verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="fdf3b-122">Ruft [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) mit einem `HandleType` von SQL_HANDLE_DBC auf, um das Verbindungs Handle freizugeben.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="fdf3b-123">Rufen Sie `SQLFreeHandle` mit dem `HandleType` SQL_HANDLE_ENV auf, um das Umgebungshandle wieder freizugeben.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fdf3b-124">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="fdf3b-125">Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="fdf3b-126">Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="fdf3b-127">Wenn Sie Anmelde Informationen beibehalten müssen, sollten Sie diese mit der [Win32-kryptografieapi](https://go.microsoft.com/fwlink/?LinkId=64532)verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf3b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdf3b-128">Example</span></span>  
 <span data-ttu-id="fdf3b-129">In diesem Beispiel wird ein Aufruf von `SQLDriverConnect` zum Herstellen einer Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gezeigt, bei der keine vorhandene ODBC-Datenquelle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="fdf3b-130">Die Übergabe einer unvollständigen Verbindungszeichenfolge an `SQLDriverConnect` führt dazu, dass der ODBC-Treiber den Benutzer dazu auffordert, die fehlenden Informationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="fdf3b-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
