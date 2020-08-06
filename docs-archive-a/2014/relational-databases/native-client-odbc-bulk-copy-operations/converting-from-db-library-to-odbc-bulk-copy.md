---
title: Umstellen von DB-Library in ODBC-Massen Kopiervorgänge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- converting DB-Library to ODBC bulk copy
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], DB-Library bulk copy
- ODBC, bulk copy operations
- DB-Library bulk copy
ms.assetid: 0bc15bdb-f19f-4537-ac6c-f249f42cf07f
author: rothja
ms.author: jroth
ms.openlocfilehash: 866900606e582f08695fd4695a1098f34fb2b426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620348"
---
# <a name="converting-from-db-library-to-odbc-bulk-copy"></a><span data-ttu-id="44d7c-102">Konvertieren von DB-Library-Programmen zum Massenkopieren in ODBC-Programme</span><span class="sxs-lookup"><span data-stu-id="44d7c-102">Converting from DB-Library to ODBC Bulk Copy</span></span>
  <span data-ttu-id="44d7c-103">Die Umstellung eines DB-Library-Massen Kopier Programms in ODBC ist einfach, da die vom Native Client-ODBC-Treiber unterstützten Massen Kopierfunktionen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit den DB-Library-Funktionen zum Massen kopieren vergleichbar sind, mit den folgenden Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="44d7c-103">Converting a DB-Library bulk copy program to ODBC is easy because the bulk copy functions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver are similar to the DB-Library bulk copy functions, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="44d7c-104">DB-Library-Anwendungen übergeben als ersten Parameter von Funktionen zum Massenkopieren einen Zeiger auf eine DBPROCESS-Struktur.</span><span class="sxs-lookup"><span data-stu-id="44d7c-104">DB-Library applications pass a pointer to a DBPROCESS structure as the first parameter of bulk copy functions.</span></span> <span data-ttu-id="44d7c-105">In ODBC-Anwendungen wird der DBPROCESS-Zeiger durch ein ODBC-Verbindungshandle ersetzt.</span><span class="sxs-lookup"><span data-stu-id="44d7c-105">In ODBC applications, the DBPROCESS pointer is replaced with an ODBC connection handle.</span></span>  
  
-   <span data-ttu-id="44d7c-106">DB-Library-Anwendungen **BCP_SETL** vor dem Herstellen einer Verbindung, um Massen Kopiervorgänge für einen DBPROCESS zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44d7c-106">DB-Library applications call **BCP_SETL** before connecting to enable bulk copy operations on a DBPROCESS.</span></span> <span data-ttu-id="44d7c-107">ODBC-Anwendungen aufrufen stattdessen [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) , bevor Sie eine Verbindung herstellen, um Massen Vorgänge für ein Verbindungs Handle zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="44d7c-107">ODBC applications instead call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) before connecting to enable bulk operations on a connection handle:</span></span>  
  
    ```  
    SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP,  
        (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
    ```  
  
-   <span data-ttu-id="44d7c-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt keine DB-Library-Nachrichten-und Fehlerhandler. Sie müssen **SQLGetDiagRec** aufrufen, um Fehler und Nachrichten zu erhalten, die von den ODBC-Funktionen zum Massen kopieren ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="44d7c-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support DB-Library message and error handlers; you must call **SQLGetDiagRec** to get errors and messages raised by the ODBC bulk copy functions.</span></span> <span data-ttu-id="44d7c-109">Die ODBC-Versionen der Massenkopierfunktionen geben die Standardrückgabecodes SUCCEED bzw. FAILED für das Massenkopieren zurück statt der Rückgabecodes im ODBC-Stil, wie SQL_SUCCESS oder SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="44d7c-109">The ODBC versions of bulk copy functions return the standard bulk copy return codes of SUCCEED or FAILED, not ODBC-style return codes, such as SQL_SUCCESS or SQL_ERROR.</span></span>  
  
-   <span data-ttu-id="44d7c-110">Die für den DB-Library- [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* -Parameter angegebenen Werte werden anders interpretiert als der ODBC- **bcp_bind**_cbData_ -Parameter.</span><span class="sxs-lookup"><span data-stu-id="44d7c-110">The values specified for the DB-Library [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md)*varlen* parameter are interpreted differently than the ODBC **bcp_bind**_cbData_ parameter.</span></span>  
  
    |<span data-ttu-id="44d7c-111">Angegebene Bedingung</span><span class="sxs-lookup"><span data-stu-id="44d7c-111">Condition indicated</span></span>|<span data-ttu-id="44d7c-112">DB-Library- *varlen* -Wert</span><span class="sxs-lookup"><span data-stu-id="44d7c-112">DB-Library *varlen* value</span></span>|<span data-ttu-id="44d7c-113">ODBC *cbData* -Wert</span><span class="sxs-lookup"><span data-stu-id="44d7c-113">ODBC *cbData* value</span></span>|  
    |-------------------------|--------------------------------|-------------------------|  
    |<span data-ttu-id="44d7c-114">Angabe von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="44d7c-114">Null values supplied</span></span>|<span data-ttu-id="44d7c-115">0</span><span class="sxs-lookup"><span data-stu-id="44d7c-115">0</span></span>|<span data-ttu-id="44d7c-116">-1 (SQL_NULL_DATA)</span><span class="sxs-lookup"><span data-stu-id="44d7c-116">-1 (SQL_NULL_DATA)</span></span>|  
    |<span data-ttu-id="44d7c-117">Angabe von variablen Daten</span><span class="sxs-lookup"><span data-stu-id="44d7c-117">Variable data supplied</span></span>|<span data-ttu-id="44d7c-118">-1</span><span class="sxs-lookup"><span data-stu-id="44d7c-118">-1</span></span>|<span data-ttu-id="44d7c-119">-10 (SQL_VARLEN_DATA)</span><span class="sxs-lookup"><span data-stu-id="44d7c-119">-10 (SQL_VARLEN_DATA)</span></span>|  
    |<span data-ttu-id="44d7c-120">Zeichen oder binäre Zeichenfolge mit der Länge 0</span><span class="sxs-lookup"><span data-stu-id="44d7c-120">Zero length character or binary string</span></span>|<span data-ttu-id="44d7c-121">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="44d7c-121">NA</span></span>|<span data-ttu-id="44d7c-122">0</span><span class="sxs-lookup"><span data-stu-id="44d7c-122">0</span></span>|  
  
     <span data-ttu-id="44d7c-123">In DB-Library gibt der *varlen* -Wert-1 an, dass Daten variabler Länge angegeben werden, die in den ODBC- *cbData* so interpretiert werden, dass nur NULL-Werte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="44d7c-123">In DB-Library, a *varlen* value of -1 indicates that variable length data is being supplied, which in the ODBC *cbData* is interpreted to mean that only NULL values are being supplied.</span></span> <span data-ttu-id="44d7c-124">Ändern Sie alle DB-Library- *varlen* -Spezifikationen von-1 in SQL_VARLEN_DATA und alle *varlen* -Spezifikationen von 0 in SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="44d7c-124">Change any DB-Library *varlen* specifications of -1 to SQL_VARLEN_DATA and any *varlen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="44d7c-125">Die **bcp \_ Colf**-_Datei ( \_ Collen_ ) der DB-Library und der ODBC- [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* haben das gleiche Problem wie die oben genannten Parameter **bcp_bind**_varlen_ und *cbData* .</span><span class="sxs-lookup"><span data-stu-id="44d7c-125">The DB-Library **bcp\_colfmt**_file\_collen_ and the ODBC [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md)*cbUserData* have the same issue as the **bcp_bind**_varlen_ and *cbData* parameters noted above.</span></span> <span data-ttu-id="44d7c-126">Ändern Sie alle DB-Library- *file_collen* Spezifikationen von-1 in SQL_VARLEN_DATA und alle *file_collen* Spezifikationen von 0 bis SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="44d7c-126">Change any DB-Library *file_collen* specifications of -1 to SQL_VARLEN_DATA and any *file_collen* specifications of 0 to SQL_NULL_DATA.</span></span>  
  
-   <span data-ttu-id="44d7c-127">Der *iValue* -Parameter der ODBC- [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) Funktion ist ein void-Zeiger.</span><span class="sxs-lookup"><span data-stu-id="44d7c-127">The *iValue* parameter of the ODBC [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) function is a void pointer.</span></span> <span data-ttu-id="44d7c-128">In DB-Library war *iValue* eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="44d7c-128">In DB-Library, *iValue* was an integer.</span></span> <span data-ttu-id="44d7c-129">Konvertieren Sie die Werte für den ODBC *iValue* in void \*.</span><span class="sxs-lookup"><span data-stu-id="44d7c-129">Cast the values for the ODBC *iValue* to void \*.</span></span>  
  
-   <span data-ttu-id="44d7c-130">Die **bcp_control** Option BCPMAXERRS gibt an, wie viele einzelne Zeilen Fehler aufweisen können, bevor ein Massen Kopiervorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="44d7c-130">The **bcp_control** option BCPMAXERRS specifies how many individual rows can have errors before a bulk copy operation fails.</span></span> <span data-ttu-id="44d7c-131">Der Standardwert für BCPMAXERRS ist 0 (Fehler beim ersten Fehler) in der DB-Library-Version von **bcp_control** und 10 in der ODBC-Version.</span><span class="sxs-lookup"><span data-stu-id="44d7c-131">The default for BCPMAXERRS is 0 (fail on first error) in the DB-Library version of **bcp_control** and 10 in the ODBC version.</span></span> <span data-ttu-id="44d7c-132">DB-Library-Anwendungen, die vom Standardwert 0 zum Beenden eines Massen Kopiervorgangs abhängen, müssen so geändert werden, dass der ODBC- **bcp_control** aufgerufen wird, um BCPMAXERRS auf 0 (null) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="44d7c-132">DB-Library applications that depend on the default of 0 to terminate a bulk copy operation must be changed to call the ODBC **bcp_control** to set BCPMAXERRS to 0.</span></span>  
  
-   <span data-ttu-id="44d7c-133">Die ODBC- **bcp_control** Funktion unterstützt die folgenden Optionen, die von der DB-Library-Version von **bcp_control**nicht unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="44d7c-133">The ODBC **bcp_control** function supports the following options not supported by the DB-Library version of **bcp_control**:</span></span>  
  
    -   <span data-ttu-id="44d7c-134">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="44d7c-134">BCPODBC</span></span>  
  
         <span data-ttu-id="44d7c-135">Wenn diese Einstellung auf true festgelegt ist, wird angegeben, dass die im Zeichenformat gespeicherten Werte **DateTime** und **smalldatetime** das ODBC-Zeitstempel-escapesequenzpräfix und-Suffix aufweisen</span><span class="sxs-lookup"><span data-stu-id="44d7c-135">When set to TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will have the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="44d7c-136">Dies gilt nur für BCP_OUT-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="44d7c-136">This only applies to BCP_OUT operations.</span></span>  
  
         <span data-ttu-id="44d7c-137">Wenn BCPODBC auf false festgelegt ist, wird ein in eine Zeichenfolge konvertierter **DateTime** -Wert wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="44d7c-137">With BCPODBC set to FALSE, a **datetime** value converted to a character string is output as:</span></span>  
  
        ```  
        1997-01-01 00:00:00.000  
        ```  
  
         <span data-ttu-id="44d7c-138">Wenn BCPODBC auf true festgelegt ist, wird der gleiche **DateTime** -Wert wie folgt ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="44d7c-138">With BCPODBC set to TRUE, the same **datetime** value is output as:</span></span>  
  
        ```  
        {ts '1997-01-01 00:00:00.000' }  
        ```  
  
    -   <span data-ttu-id="44d7c-139">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="44d7c-139">BCPKEEPIDENTITY</span></span>  
  
         <span data-ttu-id="44d7c-140">Durch die Festlegung dieser Option auf TRUE wird angegeben, dass Massenkopierfunktionen Datenwerte einfügen, die für Spalten mit einer IDENTITY-Einschränkung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="44d7c-140">When set to TRUE, specifies that bulk copy functions insert data values supplied for columns with identity constraints.</span></span> <span data-ttu-id="44d7c-141">Wenn dies nicht festgelegt ist, werden neue Identitätswerte für die eingefügten Zeilen generiert.</span><span class="sxs-lookup"><span data-stu-id="44d7c-141">If this is not set, new identity values are generated for the inserted rows.</span></span>  
  
    -   <span data-ttu-id="44d7c-142">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="44d7c-142">BCPHINTS</span></span>  
  
         <span data-ttu-id="44d7c-143">Gibt verschiedene Optimierungen für das Massenkopieren an.</span><span class="sxs-lookup"><span data-stu-id="44d7c-143">Specifies various bulk copy optimizations.</span></span> <span data-ttu-id="44d7c-144">Diese Option kann in Version 6.5 und früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="44d7c-144">This option cannot be used on 6.5 or earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="44d7c-145">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="44d7c-145">BCPFILECP</span></span>  
  
         <span data-ttu-id="44d7c-146">Gibt die Codepage für die Datendatei des Massenkopiervorgangs an.</span><span class="sxs-lookup"><span data-stu-id="44d7c-146">Specifies the code page of the bulk copy file.</span></span>  
  
    -   <span data-ttu-id="44d7c-147">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="44d7c-147">BCPUNICODEFILE</span></span>  
  
         <span data-ttu-id="44d7c-148">Gibt an, dass eine Datendatei für das Massenkopieren im Zeichenmodus eine Unicode-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="44d7c-148">Specifies that a character mode bulk copy file is a Unicode file.</span></span>  
  
-   <span data-ttu-id="44d7c-149">Die ODBC- **bcp_colfmt** Funktion unterstützt den *file_type* -Indikator von SQLCHAR nicht, da Sie mit der ODBC SQLCHAR typedef in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="44d7c-149">The ODBC **bcp_colfmt** function does not support the *file_type* indicator of SQLCHAR because it conflicts with the ODBC SQLCHAR typedef.</span></span> <span data-ttu-id="44d7c-150">Verwenden Sie stattdessen SQLCHARACTER für **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="44d7c-150">Use SQLCHARACTER instead for **bcp_colfmt**.</span></span>  
  
-   <span data-ttu-id="44d7c-151">In den ODBC-Versionen der Funktionen zum Massen kopieren ist das Format für das Arbeiten mit **DateTime** -und **smalldatetime** -Werten in Zeichen folgen das ODBC-Format yyyy-mm-dd hh: mm: SS. sss;. **smalldatetime** -Werte verwenden das ODBC-Format yyyy-mm-dd hh: mm: SS.</span><span class="sxs-lookup"><span data-stu-id="44d7c-151">In the ODBC versions of bulk copy functions, the format for working with **datetime** and **smalldatetime** values in character strings is the ODBC format of yyyy-mm-dd hh:mm:ss.sss; **smalldatetime** values use the ODBC format of yyyy-mm-dd hh:mm:ss.</span></span>  
  
     <span data-ttu-id="44d7c-152">Die DB-Library-Versionen der Funktionen zum Massen kopieren akzeptieren **DateTime** -und **smalldatetime** -Werte in Zeichen folgen unter Verwendung verschiedener Formate:</span><span class="sxs-lookup"><span data-stu-id="44d7c-152">The DB-Library versions of the bulk copy functions accept **datetime** and **smalldatetime** values in character strings using several formats:</span></span>  
  
    -   <span data-ttu-id="44d7c-153">Das Standardformat ist *mmm DD JJJJ HH: mmxx* , wobei *xx* entweder am oder PM steht.</span><span class="sxs-lookup"><span data-stu-id="44d7c-153">The default format is *mmm dd yyyy hh:mmxx* where *xx* is either AM or PM.</span></span>  
  
    -   <span data-ttu-id="44d7c-154">**DateTime** -und **smalldatetime** -Zeichen folgen in einem beliebigen Format, das von der DB-Library-Funktion **DBConvert** unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="44d7c-154">**datetime** and **smalldatetime** character strings in any format supported by the DB-Library **dbconvert** function.</span></span>  
  
    -   <span data-ttu-id="44d7c-155">Wenn das Feld **internationale Einstellungen verwenden** auf der Registerkarte DB-Library- **Optionen** des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Netzwerk-Hilfsprogramms aktiviert ist, akzeptieren die DB-Library-Massen Kopierfunktionen auch Datumsangaben in dem regionalen Datumsformat, das für die Gebiets Schema Einstellung der Client Computer Registrierung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="44d7c-155">When the **Use international settings** box is checked on the DB-Library **Options** tab of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility, the DB-Library bulk copy functions also accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
     <span data-ttu-id="44d7c-156">Die DB-Library-Funktionen zum Massen kopieren akzeptieren die ODBC **DateTime** -und **smalldatetime** -Formate nicht.</span><span class="sxs-lookup"><span data-stu-id="44d7c-156">The DB-Library bulk copy functions do not accept the ODBC **datetime** and **smalldatetime** formats.</span></span>  
  
     <span data-ttu-id="44d7c-157">Wenn das SQL_SOPT_SS_REGIONALIZE-Anweisungsattribut auf SQL_RE_ON festgelegt wurde, akzeptieren die ODBC-Funktionen zum Massenkopieren auch Datumsangaben in dem regionalen Datumsformat, das für die Einstellung des Gebietsschemas in der Registrierung des Clientcomputers definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="44d7c-157">If the SQL_SOPT_SS_REGIONALIZE statement attribute is set to SQL_RE_ON, the ODBC bulk copy functions accept dates in the regional date format defined for the locale setting of the client computer registry.</span></span>  
  
-   <span data-ttu-id="44d7c-158">Beim Ausgeben von **Money** -Werten im Zeichenformat stellen ODBC-Funktionen zum Massen kopieren vier Ziffern der Genauigkeit und keine Komma Trennzeichen bereit. DB-Library-Versionen bieten nur zwei Ziffern der Genauigkeit und enthalten die Komma Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="44d7c-158">When outputting **money** values in character format, ODBC bulk copy functions supply four digits of precision and no comma separators; DB-Library versions only supply two digits of precision and include the comma separators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d7c-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44d7c-159">See Also</span></span>  
 <span data-ttu-id="44d7c-160">[Ausführen von Massen Kopier Vorgängen &#40;ODBC-&#41;](performing-bulk-copy-operations-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="44d7c-160">[Performing Bulk Copy Operations &#40;ODBC&#41;](performing-bulk-copy-operations-odbc.md) </span></span>  
 [<span data-ttu-id="44d7c-161">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="44d7c-161">Bulk Copy Functions</span></span>](../native-client-odbc-extensions-bulk-copy-functions/sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
