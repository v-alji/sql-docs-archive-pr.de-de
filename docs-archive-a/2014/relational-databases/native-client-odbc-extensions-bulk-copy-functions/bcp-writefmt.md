---
title: bcp_writefmt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_writefmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_writefmt function
ms.assetid: cb4c1d37-667d-4bcd-b13c-eb638bcc9b69
author: rothja
ms.author: jroth
ms.openlocfilehash: 13785469e0b02f63f14d28f0db87e77df3a15cfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619097"
---
# <a name="bcp_writefmt"></a><span data-ttu-id="43c82-102">bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="43c82-102">bcp_writefmt</span></span>
  <span data-ttu-id="43c82-103">Erstellt eine Formatdatei, die eine Beschreibung des Formats der aktuellen Datendatei für das Massenkopieren enthält.</span><span class="sxs-lookup"><span data-stu-id="43c82-103">Creates a format file containing a description of the format of the current bulk copy data file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43c82-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_writefmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="43c82-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="43c82-105">Arguments</span></span>  
 <span data-ttu-id="43c82-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="43c82-106">*hdbc*</span></span>  
 <span data-ttu-id="43c82-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="43c82-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="43c82-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="43c82-108">*szFormatFile*</span></span>  
 <span data-ttu-id="43c82-109">Pfad und Dateiname der Benutzerdatei zum Abrufen der Formatwerte für die Datendatei.</span><span class="sxs-lookup"><span data-stu-id="43c82-109">Is the path and file name of the user file to receive format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="43c82-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="43c82-110">Returns</span></span>  
 <span data-ttu-id="43c82-111">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="43c82-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c82-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="43c82-112">Remarks</span></span>  
 <span data-ttu-id="43c82-113">Die Formatdatei gibt das Datenformat einer durch Massenkopieren erstellten Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="43c82-113">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="43c82-114">Durch Aufrufen von [bcp_columns](bcp-columns.md) und [bcp_colfmt](bcp-colfmt.md) wird das Format der Datendatei definiert.</span><span class="sxs-lookup"><span data-stu-id="43c82-114">Calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md) define the format of the data file.</span></span> <span data-ttu-id="43c82-115">**bcp_writefmt** speichert diese Definition in der Datei, auf die von *szFormatFile*verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="43c82-115">**bcp_writefmt** saves this definition in the file referenced by *szFormatFile*.</span></span> <span data-ttu-id="43c82-116">Weitere Informationen finden Sie unter [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="43c82-116">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="43c82-117">Weitere Informationen zur Struktur von **bcp** -Datenformat Dateien finden Sie unter [importieren und Exportieren von Massendaten mithilfe des Hilfsprogramms bcp &#40;SQL Server&#41;](../import-export/import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="43c82-117">For more information about the structure of **bcp** data format files, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](../import-export/import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md).</span></span>  
  
 <span data-ttu-id="43c82-118">Verwenden Sie [bcp_readfmt](bcp-readfmt.md), um eine gespeicherte Formatdatei zu laden.</span><span class="sxs-lookup"><span data-stu-id="43c82-118">To load a saved format file, use [bcp_readfmt](bcp-readfmt.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43c82-119">Die von **bcp_writefmt** erstellte Formatdatei wird nur von Versionen des in Version **7.0 und höher enthaltenen Hilfsprogramms** bcp [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43c82-119">The format file produced by **bcp_writefmt** is supported only by versions of the **bcp** utility distributed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43c82-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43c82-120">Example</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_OUT) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_columns(hdbc, 3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
bcp_colfmt(hdbc, 1, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 1);  
bcp_colfmt(hdbc, 2, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 2);  
bcp_colfmt(hdbc, 3, SQLCHARACTER, 0, SQL_VARLEN_DATA, '\t', 1, 3);  
  
if (bcp_writefmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   printf_s("%ld rows copied from SQL Server\n", nRowsProcessed);  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="43c82-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43c82-121">See Also</span></span>  
 [<span data-ttu-id="43c82-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="43c82-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
