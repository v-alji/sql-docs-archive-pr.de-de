---
title: bcp_moretext | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616057"
---
# <a name="bcp_moretext"></a><span data-ttu-id="26fe9-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="26fe9-102">bcp_moretext</span></span>
  <span data-ttu-id="26fe9-103">Sendet einen Teil eines langen Datentypwerts variabler Länge an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26fe9-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26fe9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26fe9-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="26fe9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="26fe9-105">Arguments</span></span>  
 <span data-ttu-id="26fe9-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="26fe9-106">*hdbc*</span></span>  
 <span data-ttu-id="26fe9-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="26fe9-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="26fe9-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="26fe9-108">*cbData*</span></span>  
 <span data-ttu-id="26fe9-109">Entspricht der Anzahl der Datenbytes, die aus den Daten, auf die *pData*verweist, auf den SQL Server kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="26fe9-110">Der Wert SQL_NULL_DATA gibt NULL an.</span><span class="sxs-lookup"><span data-stu-id="26fe9-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="26fe9-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="26fe9-111">*pData*</span></span>  
 <span data-ttu-id="26fe9-112">Ist ein Zeiger auf den unterstützten, langen Datenausschnitt variabler Länge, der an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="26fe9-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="26fe9-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="26fe9-113">Returns</span></span>  
 <span data-ttu-id="26fe9-114">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="26fe9-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26fe9-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="26fe9-115">Remarks</span></span>  
 <span data-ttu-id="26fe9-116">Diese Funktion kann zusammen mit [bcp_bind](bcp-bind.md) und [bcp_sendrow](bcp-sendrow.md) verwendet werden, um lange Datenwerte mit variabler Länge in mehreren kleineren Blöcken nach SQL Server zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="26fe9-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="26fe9-117">**bcp_moretext** können mit Spalten verwendet werden, die die folgenden SQL Server Datentypen aufweisen: `text` , `ntext` , `image` , `varchar(max)` , `nvarchar(max)` , `varbinary(max)` , benutzerdefinierter Typ (User-Defined Type, UDT) und XML.</span><span class="sxs-lookup"><span data-stu-id="26fe9-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="26fe9-118">**bcp_moretext** unterstützt keine Datenkonvertierungen. Die angegebenen Daten müssen mit dem Datentyp der Zielspalte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="26fe9-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="26fe9-119">Wenn **bcp_bind** mit einem *pData* -Parameter ungleich NULL für Datentypen aufgerufen wird, die von **bcp_moretext**unterstützt werden, `bcp_sendrow` sendet unabhängig von der Länge den gesamten Datenwert.</span><span class="sxs-lookup"><span data-stu-id="26fe9-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="26fe9-120">Wenn **bcp_bind** jedoch einen *pData* -Parameter für unterstützte Datentypen NULL aufweist, können **bcp_moretext** verwendet werden, um Daten unmittelbar nach einer erfolgreichen Rückgabe von zu kopieren `bcp_sendrow` . Dies deutet darauf hin, dass alle gebundenen Spalten mit vorhandenen Daten verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="26fe9-121">Wenn Sie **bcp_moretext** verwenden, um eine unterstützte Datentypspalte in einer Zeile zu senden, müssen Sie alle anderen unterstützten Datentypspalten in der Zeile ebenfalls mit diesem Parameter senden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="26fe9-122">Es dürfen keine Spalten übersprungen werden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-122">No columns may be skipped.</span></span> <span data-ttu-id="26fe9-123">Unterstützte Datentypen sind SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT und SQLXML.</span><span class="sxs-lookup"><span data-stu-id="26fe9-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="26fe9-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY und SQLVARBINARY gehören auch zu dieser Kategorie, wenn die Spalte den Datentyp varchar(max), nvarchar(max) bzw. varbinary(max) aufweist.</span><span class="sxs-lookup"><span data-stu-id="26fe9-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="26fe9-125">Durch Aufrufen von **bcp_bind** oder [bcp_collen](bcp-collen.md) wird festgelegt, dass die gesamte Länge aller Datenausschnitte in die SQL Server-Spalte kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="26fe9-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="26fe9-126">Es wurde versucht, SQL Server mehr Bytes zu senden, als im **bcp_bind** aufgerufen werden, oder es wird `bcp_collen` ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="26fe9-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="26fe9-127">Dieser Fehler tritt z. b. in einer Anwendung auf, die verwendet wurde, `bcp_collen` um die Länge der verfügbaren Daten für eine SQL Server `text` Spalte auf 4500 festzulegen. Anschließend wird **bcp_moretext** fünfmal aufgerufen, während für jeden Aufruf angegeben wird, dass die Länge des Daten Puffers 1000 Byte beträgt.</span><span class="sxs-lookup"><span data-stu-id="26fe9-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="26fe9-128">Wenn eine kopierte Zeile mehr als eine lange Spalte variabler Länge enthält, sendet **bcp_moretext** die Daten zunächst an die Spalte mit der niedrigsten Ordnungszahl, dann an die Spalte mit der zweitniedrigsten Ordnungszahl usw.</span><span class="sxs-lookup"><span data-stu-id="26fe9-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="26fe9-129">Die richtige Einstellung der gesamten Länge der erwarteten Daten ist wichtig.</span><span class="sxs-lookup"><span data-stu-id="26fe9-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="26fe9-130">Es gibt außer der Längeneinstellung keine Möglichkeit zu signalisieren, dass alle Daten für eine Spalte durch Massenkopieren empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="26fe9-131">Wenn `var(max)` Werte mithilfe von bcp_sendrow und bcp_moretext an den Server gesendet werden, ist es nicht erforderlich, bcp_collen aufzurufen, um die Spaltenlänge festzulegen.</span><span class="sxs-lookup"><span data-stu-id="26fe9-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="26fe9-132">Stattdessen wird der Wert nur für diese Typen beendet, indem bcp_sendrow mit der Länge 0 (null) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="26fe9-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="26fe9-133">Eine Anwendung ruft in der Regel `bcp_sendrow` auf und **bcp_moretext** in Schleifen, um eine Reihe von Daten Zeilen zu senden.</span><span class="sxs-lookup"><span data-stu-id="26fe9-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="26fe9-134">Im folgenden finden Sie einen Überblick über die Vorgehensweise für eine Tabelle mit zwei `text` Spalten:</span><span class="sxs-lookup"><span data-stu-id="26fe9-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="26fe9-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26fe9-135">Example</span></span>  
 <span data-ttu-id="26fe9-136">Dieses Beispiel zeigt, wie Sie **bcp_moretext** mit **bcp_bind** und verwenden `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="26fe9-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
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
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="26fe9-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26fe9-137">See Also</span></span>  
 [<span data-ttu-id="26fe9-138">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="26fe9-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
