---
title: bcp_bind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698168"
---
# <a name="bcp_bind"></a><span data-ttu-id="fbae1-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="fbae1-102">bcp_bind</span></span>
  <span data-ttu-id="fbae1-103">Bindet Daten einer Programmvariablen an eine Tabellenspalte im Hinblick auf einen Massenkopiervorgang in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbae1-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbae1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbae1-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fbae1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="fbae1-105">Arguments</span></span>  
 <span data-ttu-id="fbae1-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="fbae1-106">*hdbc*</span></span>  
 <span data-ttu-id="fbae1-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="fbae1-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="fbae1-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="fbae1-108">*pData*</span></span>  
 <span data-ttu-id="fbae1-109">Ein Zeiger auf die kopierten Daten.</span><span class="sxs-lookup"><span data-stu-id="fbae1-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="fbae1-110">Wenn *eDataType* SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR oder SQLIMAGE ist, kann *pData* NULL sein.</span><span class="sxs-lookup"><span data-stu-id="fbae1-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="fbae1-111">Ein *pData* -Wert von NULL gibt an, dass lange Datenwerte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [bcp_moretext](bcp-moretext.md)in Blöcken an gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="fbae1-112">Der Benutzer sollte *pData* nur auf NULL festlegen, wenn die Spalte, die dem Benutzer gebundenen Feld entspricht, eine BLOB-Spalte ist, andernfalls **bcp_bind** fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="fbae1-113">Falls Indikatoren in den Daten vorhanden sind, stehen sie im Speicher direkt vor den Daten.</span><span class="sxs-lookup"><span data-stu-id="fbae1-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="fbae1-114">Der *pData* -Parameter verweist in diesem Fall auf die Indikator Variable, und die Breite des Indikators, der *cbIndicator* -Parameter, wird vom Massen Kopiervorgang verwendet, um die Benutzerdaten ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="fbae1-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="fbae1-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="fbae1-115">*cbIndicator*</span></span>  
 <span data-ttu-id="fbae1-116">Die Länge eines Längen- oder NULL-Indikators für die Spaltendaten in Byte.</span><span class="sxs-lookup"><span data-stu-id="fbae1-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="fbae1-117">Gültige Indikatorlängenwerte sind 0 (wenn kein Indikator verwendet wird), 1, 2, 4 oder 8.</span><span class="sxs-lookup"><span data-stu-id="fbae1-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="fbae1-118">Indikatoren stehen im Speicher direkt vor allen Daten.</span><span class="sxs-lookup"><span data-stu-id="fbae1-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="fbae1-119">Beispielsweise könnte die folgende Strukturtypdefinition verwendet werden, um für einen Massenkopiervorgang Ganzzahlwerte in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle einzufügen:</span><span class="sxs-lookup"><span data-stu-id="fbae1-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="fbae1-120">Im Beispiel Fall wird der *pData* -Parameter auf die Adresse einer deklarierten Instanz der Struktur festgelegt, die Adresse des bcpboundint- *iIndicator* -Strukturmembers.</span><span class="sxs-lookup"><span data-stu-id="fbae1-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="fbae1-121">Der *cbIndicator* -Parameter wird auf die Größe einer ganzen Zahl (sizeof (int)) festgelegt, und der *cbData* -Parameter würde erneut auf die Größe einer ganzen Zahl (sizeof (int)) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="fbae1-122">Um einen Massen Kopiervorgang für eine Zeile auf den Server mit einem NULL-Wert für die gebundene Spalte durchzusetzen, sollte der Wert des *iIndicator* -Members der Instanz auf SQL_NULL_DATA festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="fbae1-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="fbae1-123">*cbData*</span></span>  
 <span data-ttu-id="fbae1-124">Die Anzahl der Datenbytes in der Programmvariablen ohne die Länge eventuell vorhandener Längenindikatoren, NULL-Indikatoren oder Abschlusszeichen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="fbae1-125">Wenn *cbData* auf SQL_NULL_DATA festgelegt wird, bedeutet dies, dass alle auf den Server kopierten Zeilen einen NULL-Wert für die Spalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="fbae1-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="fbae1-126">Wenn *cbData* auf SQL_VARLEN_DATA festgelegt wird, wird angegeben, dass das System ein Zeichen folgen Abschluss Zeichen oder eine andere Methode verwendet, um die Länge der kopierten Daten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="fbae1-127">Bei Datentypen mit fester Länge wie ganzen Zahlen gibt der Datentyp dem System die Länge der Daten an.</span><span class="sxs-lookup"><span data-stu-id="fbae1-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="fbae1-128">Daher können *cbData* für Datentypen mit fester Länge sicher SQL_VARLEN_DATA oder die Länge der Daten sein.</span><span class="sxs-lookup"><span data-stu-id="fbae1-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="fbae1-129">Für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zeichen-und Binär Datentypen können *cbData* SQL_VARLEN_DATA, SQL_NULL_DATA, ein positiver Wert oder 0 sein.</span><span class="sxs-lookup"><span data-stu-id="fbae1-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="fbae1-130">Wenn *cbData* SQL_VARLEN_DATA ist, verwendet das System entweder einen Längen-/NULL-Indikator (sofern vorhanden) oder eine Abschluss Zeichen Sequenz, um die Länge der Daten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="fbae1-131">Wenn beide Indikatoren bereitgestellt werden, verwendet das System beim Massenkopieren den Wert, der zu der kleineren zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="fbae1-132">Wenn *cbData* SQL_VARLEN_DATA ist, der Datentyp der Spalte ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zeichen-oder Binärtyp ist und weder ein Längen Indikator noch eine Abschluss Zeichen Sequenz angegeben ist, gibt das System eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="fbae1-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="fbae1-133">Wenn *cbData* 0 oder ein positiver Wert ist, verwendet das System *cbData* als Daten Länge.</span><span class="sxs-lookup"><span data-stu-id="fbae1-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="fbae1-134">Wenn jedoch zusätzlich zu einem positiven *cbData* -Wert ein Längen Indikator oder eine Abschluss Zeichen Sequenz angegeben ist, bestimmt das System die Daten Länge mithilfe der Methode, die zu der geringsten zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="fbae1-135">Der *cbData* -Parameterwert stellt die Anzahl der Daten Bytes dar.</span><span class="sxs-lookup"><span data-stu-id="fbae1-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="fbae1-136">Wenn Zeichendaten durch Unicode-breit Zeichen dargestellt werden, stellt ein positiver *cbData* -Parameterwert die Anzahl der Zeichen multipliziert mit der Größe in Bytes jedes Zeichens dar.</span><span class="sxs-lookup"><span data-stu-id="fbae1-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="fbae1-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="fbae1-137">*pTerm*</span></span>  
 <span data-ttu-id="fbae1-138">Ein Zeiger auf das Bytemuster, falls vorhanden, das das Ende dieser Programmvariablen markiert.</span><span class="sxs-lookup"><span data-stu-id="fbae1-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="fbae1-139">Beispielsweise weisen ANSI- und MBCS-C-Zeichenfolgen normalerweise ein 1-Byte-Abschlusszeichen (\0) auf.</span><span class="sxs-lookup"><span data-stu-id="fbae1-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="fbae1-140">Wenn kein Abschluss Zeichen für die Variable vorhanden ist, legen Sie *pterm* auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="fbae1-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="fbae1-141">Sie können eine leere Zeichenfolge ("") verwenden, um das C-NULL-Abschlusszeichen als Programmvariablen-Abschlusszeichen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="fbae1-142">Da die NULL-terminierte leere Zeichenfolge ein einzelnes Byte (das Abschluss Zeichen selbst) bildet, legen Sie *cbTerm* auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="fbae1-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="fbae1-143">Um z. b. anzugeben, dass die Zeichenfolge in *szName* NULL-terminiert ist und das Abschluss Zeichen verwendet werden soll, um die Länge anzugeben:</span><span class="sxs-lookup"><span data-stu-id="fbae1-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="fbae1-144">Eine nicht beendete Form dieses Beispiels könnte darauf hindeuten, dass 15 Zeichen aus der *szName* -Variablen in die zweite Spalte der gebundenen Tabelle kopiert werden:</span><span class="sxs-lookup"><span data-stu-id="fbae1-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="fbae1-145">Die API für das Massenkopieren führt nach Bedarf eine Zeichenkonvertierung von Unicode in MBCS aus.</span><span class="sxs-lookup"><span data-stu-id="fbae1-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="fbae1-146">Stellen Sie sicher, dass sowohl die Bytezeichenfolge des Abschlusszeichens als auch die Länge der Bytezeichenfolge richtig festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="fbae1-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="fbae1-147">Um beispielsweise anzugeben, dass die Zeichenfolge in *szName* eine Unicode-Zeichenfolge mit breit Zeichen ist, die durch den Unicode-Wert des NULL-Abschluss Zeichens beendet wird</span><span class="sxs-lookup"><span data-stu-id="fbae1-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="fbae1-148">Wenn die gebundene [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Spalte breit Zeichen ist, wird keine Konvertierung auf [bcp_sendrow](bcp-sendrow.md)ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="fbae1-149">Wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Spalte vom Typ MBCS-Zeichen ist, wird eine Konvertierung von Doppelbytezeichen in Multibytezeichen durchgeführt, wenn die Daten an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fbae1-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="fbae1-150">*cbTerm*</span></span>  
 <span data-ttu-id="fbae1-151">Anzahl von Bytes im Abschlusszeichen für die Programmvariable, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="fbae1-152">Wenn kein Abschluss Zeichen für die Variable vorhanden ist, legen Sie *cbTerm* auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="fbae1-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="fbae1-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="fbae1-153">*eDataType*</span></span>  
 <span data-ttu-id="fbae1-154">Der C-Datentyp der Programmvariablen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="fbae1-155">Die Daten in der Programmvariablen werden in den Typ der Datenbankspalte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="fbae1-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="fbae1-156">Wenn dieser Parameter 0 ist, wird keine Konvertierung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="fbae1-157">Der *eDataType* -Parameter wird durch die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentyp Token in sqlncli. h, nicht die ODBC-C-Datentyp Enumeratoren, aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fbae1-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="fbae1-158">Beispielsweise können Sie eine 2-Byte-Ganzzahl, ODBC-Typ SQL_C_SHORT, angeben, indem Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifischen Typ SQLINT2 verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="fbae1-159">in wurde die Unterstützung für die Datentyp Token SQLXML und SQLUDT im *`eDataType`* Paramenter eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="fbae1-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="fbae1-160">*idxServerCol*</span></span>  
 <span data-ttu-id="fbae1-161">Die Ordnungsposition der Spalte in der Datenbanktabelle, in die die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="fbae1-162">Die erste Spalte einer Tabelle ist die Spalte 1.</span><span class="sxs-lookup"><span data-stu-id="fbae1-162">The first column in a table is column 1.</span></span> <span data-ttu-id="fbae1-163">Die Ordnungsposition einer Spalte wird von [SQLColumns](../native-client-odbc-api/sqlcolumns.md)ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbae1-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fbae1-164">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="fbae1-164">Returns</span></span>  
 <span data-ttu-id="fbae1-165">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="fbae1-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fbae1-166">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fbae1-166">Remarks</span></span>  
 <span data-ttu-id="fbae1-167">Verwenden Sie **bcp_bind** für eine schnelle, effiziente Methode zum Kopieren von Daten aus einer Programmvariablen in eine Tabelle in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbae1-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fbae1-168">Rufen Sie [bcp_init](bcp-init.md) auf, bevor Sie diese oder eine andere Massen Kopierfunktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="fbae1-169">Durch Aufrufen von **bcp_init** wird die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ziel Tabelle für das Massen kopieren festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="fbae1-170">Wenn **bcp_init** für die Verwendung mit **bcp_bind** und [bcp_sendrow](bcp-sendrow.md)aufgerufen wird, wird der **bcp_init** _szDataFile_ -Parameter, der die Datendatei angibt, auf NULL festgelegt. der **bcp_init**_eDirection_ -Parameter ist auf DB_IN festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="fbae1-171">Erstellen Sie für jede Spalte in der Tabelle, in die kopiert werden soll, einen separaten **bcp_bind** -aufzurufen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbae1-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="fbae1-172">Nachdem die erforderlichen **bcp_bind** Aufrufe durchgeführt wurden, rufen Sie **bcp_sendrow** auf, um eine Daten Zeile aus den Programmvariablen an zu senden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbae1-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fbae1-173">Das erneute Binden einer Spalte wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="fbae1-174">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die bereits empfangenen Zeilen übertragen möchten, wenden Sie [bcp_batch](bcp-batch.md)an.</span><span class="sxs-lookup"><span data-stu-id="fbae1-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="fbae1-175">Beispielsweise können Sie **bcp_batch** einmal für alle 1000 Zeilen, die eingefügt werden, oder in einem beliebigen anderen Intervall abrufen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="fbae1-176">Wenn keine weiteren Zeilen eingefügt werden müssen, wenden Sie [bcp_done](bcp-done.md)an.</span><span class="sxs-lookup"><span data-stu-id="fbae1-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="fbae1-177">Andernfalls wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fbae1-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="fbae1-178">Die Parametereinstellungen für Steuerelemente, die mit [bcp_control](bcp-control.md)angegeben werden, haben keine Auswirkung auf **bcp_bind** Zeilen Übertragungen.</span><span class="sxs-lookup"><span data-stu-id="fbae1-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="fbae1-179">Wenn *pData* für eine Spalte auf NULL festgelegt ist, da der Wert durch Aufrufe von [bcp_moretext](bcp-moretext.md)bereitgestellt wird, alle nachfolgenden Spalten mit *eDataType* , die auf SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary, SQLNCHAR oder SQLIMAGE festgelegt sind, müssen ebenfalls mit *pData* auf NULL festgelegt werden `bcp_moretext`</span><span class="sxs-lookup"><span data-stu-id="fbae1-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="fbae1-180">Für neue große Werttypen, wie z. b. `varchar(max)` , `varbinary(max)` oder `nvarchar(max)` , können Sie SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SqlBinary und SQLNCHAR als Typindikatoren im *eDataType* -Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbae1-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="fbae1-181">Wenn *cbTerm* nicht 0 ist, ist jeder Wert (1, 2, 4 oder 8) für das Präfix (*cbIndicator*) gültig.</span><span class="sxs-lookup"><span data-stu-id="fbae1-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="fbae1-182">In dieser Situation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sucht Native Client nach dem Abschluss Zeichen, berechnet die Daten Länge in Bezug auf das Abschluss Zeichen (*i*) und legt die *cbData* auf den kleineren Wert von i und den Wert des Präfixes fest.</span><span class="sxs-lookup"><span data-stu-id="fbae1-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="fbae1-183">Wenn *cbTerm* den Wert 0 hat und *cbIndicator* (das Präfix) nicht 0 ist, muss *cbIndicator* 8 lauten.</span><span class="sxs-lookup"><span data-stu-id="fbae1-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="fbae1-184">Das 8-Byte-Präfix kann die folgenden Werte annehmen:</span><span class="sxs-lookup"><span data-stu-id="fbae1-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="fbae1-185">0xFFFFFFFFFFFFFFFF bedeutet einen NULL-Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="fbae1-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="fbae1-186">0xFFFFFFFFFFFFFFFE wird als spezieller Präfixwert behandelt und wird für die effiziente Übertragung von Datensegmenten an den Server verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbae1-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="fbae1-187">Die Daten mit diesem speziellen Präfix weisen das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="fbae1-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="fbae1-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK>, wobei:</span><span class="sxs-lookup"><span data-stu-id="fbae1-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="fbae1-189">SPECIAL_PREFIX 0xFFFFFFFFFFFFFFFE entspricht.</span><span class="sxs-lookup"><span data-stu-id="fbae1-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="fbae1-190">DATA_CHUNK ist ein 4-Byte-Präfix, das die Länge des Segments enthält, gefolgt von den Daten selbst, deren Länge in dem 4-Byte-Präfix angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="fbae1-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="fbae1-191">ZERO_CHUNK ist ein 4-Byte-Wert, der alle Nullen (00000000) enthält, die das Ende der Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="fbae1-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="fbae1-192">Jede andere gültige 8 Byte-Länge wird als reguläre Datenlänge behandelt.</span><span class="sxs-lookup"><span data-stu-id="fbae1-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="fbae1-193">Das Aufrufen von [bcp_columns](bcp-columns.md) , wenn **bcp_bind** verwendet wird, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="fbae1-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="fbae1-194">bcp_bind-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fbae1-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="fbae1-195">Informationen zu den Typen, die mit dem *eDataType* -Parameter für Datums-/Uhrzeittypen verwendet werden, finden Sie unter [Massen Kopier Änderungen für verbesserte Datums-und Uhrzeit Typen &#40;OLE DB und ODBC-&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fbae1-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="fbae1-196">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="fbae1-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbae1-197">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbae1-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbae1-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbae1-198">See Also</span></span>  
 [<span data-ttu-id="fbae1-199">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="fbae1-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
