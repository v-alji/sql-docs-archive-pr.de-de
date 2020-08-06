---
title: bcp_readfmt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616054"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="48a44-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="48a44-102">bcp_readfmt</span></span>
  <span data-ttu-id="48a44-103">Liest eine Datendatei-Formatdefinition aus der angegebenen Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="48a44-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48a44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48a44-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="48a44-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="48a44-105">Arguments</span></span>  
 <span data-ttu-id="48a44-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="48a44-106">*hdbc*</span></span>  
 <span data-ttu-id="48a44-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="48a44-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="48a44-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="48a44-108">*szFormatFile*</span></span>  
 <span data-ttu-id="48a44-109">Pfad und Dateiname der Datei, die die Formatwerte für die Datendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="48a44-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="48a44-110">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="48a44-110">Returns</span></span>  
 <span data-ttu-id="48a44-111">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="48a44-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48a44-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="48a44-112">Remarks</span></span>  
 <span data-ttu-id="48a44-113">Nachdem `bcp_readfmt` die Format Werte gelesen hat, werden die entsprechenden Aufrufe an [bcp_columns](bcp-columns.md) und [bcp_colfmt](bcp-colfmt.md)durchführt.</span><span class="sxs-lookup"><span data-stu-id="48a44-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="48a44-114">Sie brauchen keine Formatdatei zu analysieren, um diese Aufrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="48a44-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="48a44-115">Um eine Format Datei beizubehalten, wenden Sie [bcp_writefmt](bcp-writefmt.md)an.</span><span class="sxs-lookup"><span data-stu-id="48a44-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="48a44-116">Aufrufe von `bcp_readfmt` können auf gespeicherte Formate verweisen.</span><span class="sxs-lookup"><span data-stu-id="48a44-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="48a44-117">Weitere Informationen finden Sie unter [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="48a44-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="48a44-118">Alternativ kann das Hilfsprogramm zum Massen kopieren (**bcp**) benutzerdefinierte Datenformate in Dateien speichern, auf die von verwiesen werden kann `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="48a44-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="48a44-119">Weitere Informationen zum **bcp** -Hilfsprogramm und zur Struktur von **bcp** -Datenformat Dateien finden Sie unter [Massen Import und-Export von Daten &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="48a44-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="48a44-120">Der `BCPDELAYREADFMT` Wert des *eOption* -Parameters von [bcp_control](bcp-control.md) ändert das Verhalten von bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="48a44-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="48a44-121">Die Format Datei muss von Version 4,2 oder höher des **bcp** -Hilfsprogramms erstellt worden sein.</span><span class="sxs-lookup"><span data-stu-id="48a44-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48a44-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48a44-122">Example</span></span>  
  
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
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="48a44-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48a44-123">See Also</span></span>  
 [<span data-ttu-id="48a44-124">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="48a44-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
