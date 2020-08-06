---
title: Verhaltensänderungen des ODBC-Treibers beim Verarbeiten von Zeichen Konvertierungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698066"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="7453e-102">Verhaltensänderungen des ODBC-Treibers bei der Behandlung von Zeichenkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="7453e-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="7453e-103">Der [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client-ODBC-Treiber (SQLNCLI11.dll) hat geändert, wie er SQL_WCHAR \* (nchar/nvarchar/nvarchar (max)) und SQL_CHAR \* (char/varchar/narchar (max))-Konvertierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7453e-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="7453e-104">ODBC-Funktionen wie SQLGetData, SQLBindCol und SQLBindParameter geben bei Verwendung des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client-ODBC-Treibers (-4) SQL_NO_TOTAL als Längen-/Indikatorparameter zurück.</span><span class="sxs-lookup"><span data-stu-id="7453e-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="7453e-105">Von früheren Versionen des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treibers wurde ein Längenwert zurückgegeben, was möglicherweise falsch ist.</span><span class="sxs-lookup"><span data-stu-id="7453e-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="7453e-106">SQLGetData-Verhalten</span><span class="sxs-lookup"><span data-stu-id="7453e-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="7453e-107">Bei vielen Windows-Funktionen können Sie die Puffergröße 0 angeben, wobei die zurückgegebene Länge der Größe der zurückgegebenen Daten entspricht.</span><span class="sxs-lookup"><span data-stu-id="7453e-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="7453e-108">Windows-Programmierer verwenden häufig das folgende Muster:</span><span class="sxs-lookup"><span data-stu-id="7453e-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="7453e-109">**SQLGetData** sollte in diesem Szenario jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7453e-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="7453e-110">Das folgende Muster sollte nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="7453e-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="7453e-111">**SQLGetData** kann nur aufgerufen werden, um Segmente von tatsächlichen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7453e-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="7453e-112">Die Verwendung von **SQLGetData** , um die Größe der Daten zu erhalten, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7453e-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="7453e-113">Im Folgenden wird veranschaulicht, wie sich der Treiberwechsel bei Verwendung des falschen Musters auswirkt.</span><span class="sxs-lookup"><span data-stu-id="7453e-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="7453e-114">Von der Anwendung wird eine als Unicode definierte `varchar`-Spalte und -Bindung (SQL_UNICODE/SQL_WCHAR) abgefragt:</span><span class="sxs-lookup"><span data-stu-id="7453e-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="7453e-115">Such`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="7453e-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7453e-116">Native Client-ODBC-Treiberversion</span><span class="sxs-lookup"><span data-stu-id="7453e-116">Native Client ODBC Driver version</span></span>|<span data-ttu-id="7453e-117">Längen- oder Indikatorergebnis</span><span class="sxs-lookup"><span data-stu-id="7453e-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="7453e-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7453e-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="7453e-119">Native Client oder früher</span><span class="sxs-lookup"><span data-stu-id="7453e-119">Native Client or earlier</span></span>|<span data-ttu-id="7453e-120">6</span><span class="sxs-lookup"><span data-stu-id="7453e-120">6</span></span>|<span data-ttu-id="7453e-121">Der Treiber geht fälschlicherweise davon aus, dass die Konvertierung von CHAR in WCHAR als "Länge \* 2" durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7453e-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="7453e-122">Native Client (Version 11.0.2100.60) oder höher</span><span class="sxs-lookup"><span data-stu-id="7453e-122">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="7453e-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="7453e-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="7453e-124">Der Treiber geht nicht mehr davon aus, dass die Umstellung von Char in WCHAR oder wchar in Char eine (Multiplikation) \* 2 oder (dividieren)/2-Aktion ist.</span><span class="sxs-lookup"><span data-stu-id="7453e-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="7453e-125">Durch den Aufruf von **SQLGetData** wird die Länge der erwarteten Konvertierung nicht mehr zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7453e-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="7453e-126">Der Treiber erkennt die Konvertierung in bzw. aus CHAR und WCHAR und gibt anstelle von "\*2" oder "/2" das Ergebnis (-4) SQL_NO_TOTAL zurück; dieses Verhalten kann falsch sein.</span><span class="sxs-lookup"><span data-stu-id="7453e-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="7453e-127">Verwenden Sie **SQLGetData** , um die Segmente der Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7453e-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="7453e-128">(Dargestellter Pseudocode:)</span><span class="sxs-lookup"><span data-stu-id="7453e-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="7453e-129">SQLBindCol-Verhalten</span><span class="sxs-lookup"><span data-stu-id="7453e-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="7453e-130">Such`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="7453e-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7453e-131">Native Client-ODBC-Treiberversion</span><span class="sxs-lookup"><span data-stu-id="7453e-131">Native Client ODBC Driver version</span></span>|<span data-ttu-id="7453e-132">Längen- oder Indikatorergebnis</span><span class="sxs-lookup"><span data-stu-id="7453e-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="7453e-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7453e-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="7453e-134">Native Client oder früher</span><span class="sxs-lookup"><span data-stu-id="7453e-134">Native Client or earlier</span></span>|<span data-ttu-id="7453e-135">20</span><span class="sxs-lookup"><span data-stu-id="7453e-135">20</span></span>|<span data-ttu-id="7453e-136">-   **SQLFetch** meldet, dass auf der rechten Seite der Daten abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="7453e-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="7453e-137">-Length ist die Länge der zurückgegebenen Daten, nicht der gespeicherten Daten (von wird die Konvertierung von \* 2 Char in WCHAR angenommen, die für Glyphen falsch sein kann).</span><span class="sxs-lookup"><span data-stu-id="7453e-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="7453e-138">-Die im Puffer gespeicherten Daten sind 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="7453e-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="7453e-139">Der Puffer ist garantiert NULL-terminiert.</span><span class="sxs-lookup"><span data-stu-id="7453e-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="7453e-140">Native Client (Version 11.0.2100.60) oder höher</span><span class="sxs-lookup"><span data-stu-id="7453e-140">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="7453e-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="7453e-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="7453e-142">-   **SQLFetch** meldet, dass auf der rechten Seite der Daten abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="7453e-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="7453e-143">-Length gibt-4 (SQL_NO_TOTAL) an, da die restlichen Daten nicht konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7453e-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="7453e-144">-Die im Puffer gespeicherten Daten sind 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="7453e-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="7453e-145">- Der Puffer ist garantiert NULL-terminiert.</span><span class="sxs-lookup"><span data-stu-id="7453e-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="7453e-146">SQLBindParameter (Verhalten des OUTPUT-Parameters)</span><span class="sxs-lookup"><span data-stu-id="7453e-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="7453e-147">Such`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="7453e-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="7453e-148">Native Client-ODBC-Treiberversion</span><span class="sxs-lookup"><span data-stu-id="7453e-148">Native Client ODBC Driver version</span></span>|<span data-ttu-id="7453e-149">Längen- oder Indikatorergebnis</span><span class="sxs-lookup"><span data-stu-id="7453e-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="7453e-150">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7453e-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="7453e-151">Native Client oder früher</span><span class="sxs-lookup"><span data-stu-id="7453e-151">Native Client or earlier</span></span>|<span data-ttu-id="7453e-152">2.468</span><span class="sxs-lookup"><span data-stu-id="7453e-152">2468</span></span>|<span data-ttu-id="7453e-153">-   **SQLFetch** gibt keine weiteren verfügbaren Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="7453e-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="7453e-154">-   **SQLMoreResults** gibt keine weiteren verfügbaren Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="7453e-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="7453e-155">-Length gibt die Größe der Daten an, die vom Server zurückgegeben und nicht im Puffer gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7453e-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="7453e-156">-Der ursprüngliche Puffer enthält 63 Bytes und ein NULL-Terminator.</span><span class="sxs-lookup"><span data-stu-id="7453e-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="7453e-157">Der Puffer ist garantiert NULL-terminiert.</span><span class="sxs-lookup"><span data-stu-id="7453e-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="7453e-158">Native Client (Version 11.0.2100.60) oder höher</span><span class="sxs-lookup"><span data-stu-id="7453e-158">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="7453e-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="7453e-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="7453e-160">-   **SQLFetch** gibt keine weiteren verfügbaren Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="7453e-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="7453e-161">-   **SQLMoreResults** gibt keine weiteren verfügbaren Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="7453e-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="7453e-162">-Length zeigt (-4) SQL_NO_TOTAL an, da die restlichen Daten nicht konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="7453e-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="7453e-163">-Der ursprüngliche Puffer enthält 63 Bytes und ein NULL-Terminator.</span><span class="sxs-lookup"><span data-stu-id="7453e-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="7453e-164">Der Puffer ist garantiert NULL-terminiert.</span><span class="sxs-lookup"><span data-stu-id="7453e-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="7453e-165">Ausführen von CHAR- und WCHAR-Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="7453e-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="7453e-166">Der [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client-ODBC-Treiber bietet verschiedene Möglichkeiten zum Durchführen von CHAR- und WCHAR-Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="7453e-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="7453e-167">Die Logik ähnelt der Bearbeitung von blobzeichen (varchar (max), nvarchar (max),...):</span><span class="sxs-lookup"><span data-stu-id="7453e-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="7453e-168">Daten werden bei der Bindung mit **SQLBindCol** oder **SQLBindParameter**in den angegebenen Puffer gespeichert oder abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="7453e-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="7453e-169">Wenn Sie keine Bindung durchführen, können Sie die Daten in Blöcken mithilfe von **SQLGetData** und **SQLParamData**abrufen.</span><span class="sxs-lookup"><span data-stu-id="7453e-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7453e-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7453e-170">See Also</span></span>  
 [<span data-ttu-id="7453e-171">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="7453e-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
