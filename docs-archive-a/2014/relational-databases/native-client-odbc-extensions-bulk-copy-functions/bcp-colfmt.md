---
title: bcp_colfmt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725697"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="c76e4-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="c76e4-102">bcp_colfmt</span></span>
  <span data-ttu-id="c76e4-103">Gibt das Quell- oder Zielformat der Daten in einer Benutzerdatei an.</span><span class="sxs-lookup"><span data-stu-id="c76e4-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="c76e4-104">Bei Verwendung als Quellformat gibt **bcp_colfmt** das Format einer vorhandenen Datendatei an, die als Datenquelle in einem Massen Kopiervorgang in eine Tabelle verwendet wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c76e4-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c76e4-105">Bei Verwendung als Zielformat wird die Datendatei mithilfe der mit **bcp_colfmt**angegebenen Spalten Formate erstellt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c76e4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c76e4-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c76e4-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="c76e4-107">Arguments</span></span>  
 <span data-ttu-id="c76e4-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="c76e4-108">*hdbc*</span></span>  
 <span data-ttu-id="c76e4-109">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="c76e4-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="c76e4-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="c76e4-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="c76e4-111">Die Ordnungsnummer der Spalte in der Benutzerdatendatei, für die das Format angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c76e4-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="c76e4-112">Die erste Spalte ist 1.</span><span class="sxs-lookup"><span data-stu-id="c76e4-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="c76e4-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="c76e4-113">*eUserDataType*</span></span>  
 <span data-ttu-id="c76e4-114">Der Datentyp dieser Spalte in der Benutzerdatei.</span><span class="sxs-lookup"><span data-stu-id="c76e4-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="c76e4-115">Wenn Sie sich vom Datentyp der entsprechenden Spalte in der Datenbanktabelle (*idxServerColumn*) unterscheiden, werden die Daten nach Möglichkeit durch Massen kopieren konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c76e4-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="c76e4-116">in wurde die Unterstützung für die Datentyp Token SQLXML und SQLUDT im *eUserDataType* -Parameter eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="c76e4-117">Der *eUserDataType* -Parameter wird durch die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datentyp Token in sqlncli. h, nicht die ODBC-C-Datentyp Enumeratoren, aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c76e4-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="c76e4-118">Sie können beispielsweise mithilfe des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifischen SQLCHARACTER-Typs eine Zeichenfolge vom ODBC-Typ SQL_C_CHAR angeben.</span><span class="sxs-lookup"><span data-stu-id="c76e4-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="c76e4-119">Um die Standarddatendarstellung für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp anzugeben, legen Sie diesen Parameter auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="c76e4-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="c76e4-120">Bei einem Massen Kopiervorgang aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in eine Datei, wenn *eUserDataType* SqlDecimal oder SQLNUMERIC lautet:</span><span class="sxs-lookup"><span data-stu-id="c76e4-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="c76e4-121">Wenn die Quell Spalte nicht **Dezimal** oder **numerisch**ist, werden die Standardgenauigkeit und die Standardskala verwendet.</span><span class="sxs-lookup"><span data-stu-id="c76e4-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="c76e4-122">Wenn die Quell Spalte **Dezimal** oder **numerisch**ist, werden die Genauigkeit und die Dezimalstellen der Quell Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c76e4-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="c76e4-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="c76e4-123">*cbIndicator*</span></span>  
 <span data-ttu-id="c76e4-124">Die Länge eines Längen-/NULL-Indikators innerhalb der Spaltendaten in Byte.</span><span class="sxs-lookup"><span data-stu-id="c76e4-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="c76e4-125">Gültige Indikatorlängenwerte sind 0 (wenn kein Indikator verwendet wird), 1, 2, 4 oder 8.</span><span class="sxs-lookup"><span data-stu-id="c76e4-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="c76e4-126">Legen Sie diesen Parameter auf SQL_VARLEN_DATA fest, um die Verwendung eines standardmäßigen Massenkopierindikators anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c76e4-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="c76e4-127">Indikatoren werden im Speicher direkt vor allen anderen Daten angezeigt. In der Datendatei werden sie direkt vor den Daten, auf die sie sich beziehen, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="c76e4-128">Wird mehr als eine Methode zur Angabe der Länge der Datendateispalte verwendet (z. B. ein Indikator und eine maximale Spaltenlänge oder ein Indikator und eine Abschlusszeichensequenz), wird beim Massenkopieren die Methode ausgewählt, die zu der kleineren zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="c76e4-129">Datendateien, die durch Massenkopieren generiert wurden, wobei das Datenformat nicht durch Benutzereingriff angepasst wird, enthalten Indikatoren, wenn die Spaltendaten eine unterschiedliche Länge haben oder die Spalte NULL als Wert akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="c76e4-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="c76e4-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="c76e4-130">*cbUserData*</span></span>  
 <span data-ttu-id="c76e4-131">Die maximale Länge (in Byte) der Daten dieser Spalte in der Benutzerdatei, ohne die Länge eines Längenindikators oder Abschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="c76e4-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="c76e4-132">Wenn *cbUserData* auf SQL_NULL_DATA festgelegt wird, wird angegeben, dass alle Werte in der Datendatei Spalte auf NULL festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="c76e4-133">Durch Festlegen von *cbUserData* auf SQL_VARLEN_DATA wird angegeben, dass das System die Länge der Daten in den einzelnen Spalten bestimmen soll.</span><span class="sxs-lookup"><span data-stu-id="c76e4-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="c76e4-134">Für einige Spalten könnte dies bedeuten, dass ein Längen-/NULL-Indikator generiert wird, der den Daten in einer Kopie von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vorangestellt wird, oder dass der Indikator in Daten, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kopiert werden, erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="c76e4-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c76e4-135">Bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zeichen-und Binär Datentypen kann *cbUserData* SQL_VARLEN_DATA, SQL_NULL_DATA, 0 oder ein positiver Wert sein.</span><span class="sxs-lookup"><span data-stu-id="c76e4-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="c76e4-136">Wenn *cbUserData* SQL_VARLEN_DATA ist, verwendet das System entweder den Längen Indikator, falls vorhanden, oder eine Abschluss Zeichen Sequenz, um die Länge der Daten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="c76e4-137">Wenn sowohl ein Längenindikator als auch eine Abschlusszeichensequenz angegeben sind, wird beim Massenkopieren der Wert verwendet, der zu der kleineren zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="c76e4-138">Wenn *cbUserData* SQL_VARLEN_DATA ist, der Datentyp ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Zeichen-oder Binärtyp ist und weder ein Längen Indikator noch eine Abschluss Zeichen Sequenz angegeben ist, gibt das System eine Fehlermeldung zurück.</span><span class="sxs-lookup"><span data-stu-id="c76e4-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="c76e4-139">Wenn *cbUserData* 0 oder ein positiver Wert ist, verwendet das System *cbUserData* als maximale Datenlänge.</span><span class="sxs-lookup"><span data-stu-id="c76e4-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="c76e4-140">Wenn jedoch zusätzlich zu einem positiven *cbUserData*-Wert ein Längenindikator oder eine Abschlusszeichensequenz angegeben ist, bestimmt das System die Datenlänge mit der Methode, die zu der kleineren zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="c76e4-141">Der *cbUserData* -Wert stellt die Anzahl der Datenbytes dar.</span><span class="sxs-lookup"><span data-stu-id="c76e4-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="c76e4-142">Werden Zeichendaten durch Unicode-Zeichen dargestellt, repräsentiert ein positiver *cbUserData* -Parameterwert die Anzahl der Zeichen multipliziert mit der Größe (in Byte) der einzelnen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="c76e4-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="c76e4-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="c76e4-144">Die Abschlusszeichensequenz, die für diese Spalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c76e4-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="c76e4-145">Dieser Parameter ist in erster Linie für Zeichendatentypen nützlich, da alle anderen Typen eine feste Länge besitzen oder, im Falle von Binärdaten, einen Indikator für die Länge erfordern, um die Anzahl der vorhandenen Bytes präzise zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="c76e4-146">Legen Sie diesen Parameter auf NULL fest, um zu vermeiden, dass extrahierte Daten terminiert werden, oder um anzugeben, dass Daten in einer Benutzerdatei nicht terminiert werden.</span><span class="sxs-lookup"><span data-stu-id="c76e4-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="c76e4-147">Wird mehr als eine Methode zur Angabe der Länge der Benutzerdateispalte verwendet (z. B. ein Abschlusszeichen und ein Längenindikator oder ein Abschlusszeichen und eine maximale Spaltenlänge), wird beim Massenkopieren die Methode ausgewählt, die zu der kleineren zu kopierenden Datenmenge führt.</span><span class="sxs-lookup"><span data-stu-id="c76e4-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="c76e4-148">Die API für das Massenkopieren führt nach Bedarf eine Zeichenkonvertierung von Unicode in MBCS aus.</span><span class="sxs-lookup"><span data-stu-id="c76e4-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="c76e4-149">Stellen Sie unbedingt sicher, dass sowohl die Bytezeichenfolge des Abschlusszeichens und die Länge der Bytezeichenfolge richtig festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c76e4-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="c76e4-150">*cbUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="c76e4-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="c76e4-151">Die Länge (in Byte) der Abschlusszeichensequenz, die für diese Spalte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c76e4-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="c76e4-152">Wenn kein Abschlusszeichen vorhanden ist oder in den Daten gewünscht wird, legen Sie diesen Wert auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="c76e4-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="c76e4-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="c76e4-153">*idxServerCol*</span></span>  
 <span data-ttu-id="c76e4-154">Die Ordinalposition der Spalte in der Datenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="c76e4-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="c76e4-155">Die erste Spaltennummer ist 1.</span><span class="sxs-lookup"><span data-stu-id="c76e4-155">The first column number is 1.</span></span> <span data-ttu-id="c76e4-156">Die Ordnungsposition einer Spalte wird von [SQLColumns](../native-client-odbc-api/sqlcolumns.md)ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c76e4-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="c76e4-157">Wenn dieser Wert 0 ist, wird beim Massenkopieren die Spalte in der Datendatei ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c76e4-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c76e4-158">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="c76e4-158">Returns</span></span>  
 <span data-ttu-id="c76e4-159">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="c76e4-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c76e4-160">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c76e4-160">Remarks</span></span>  
 <span data-ttu-id="c76e4-161">Mit der **bcp_colfmt** -Funktion können Sie das Benutzerdatei Format für Massen Kopien angeben.</span><span class="sxs-lookup"><span data-stu-id="c76e4-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="c76e4-162">Für Massenkopieren besteht ein Format aus folgenden Bestandteilen:</span><span class="sxs-lookup"><span data-stu-id="c76e4-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="c76e4-163">Eine Zuordnung von Benutzerdateispalten zu Datenbankspalten</span><span class="sxs-lookup"><span data-stu-id="c76e4-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="c76e4-164">Der Datentyp der einzelnen Benutzerdateispalten</span><span class="sxs-lookup"><span data-stu-id="c76e4-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="c76e4-165">Die Länge des optionalen Indikators für jede Spalte</span><span class="sxs-lookup"><span data-stu-id="c76e4-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="c76e4-166">Die maximale Länge der Daten pro Benutzerdateispalte</span><span class="sxs-lookup"><span data-stu-id="c76e4-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="c76e4-167">Die optionale abschließende Bytesequenz für jede Spalte</span><span class="sxs-lookup"><span data-stu-id="c76e4-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="c76e4-168">Die Länge der optionalen abschließenden Bytesequenz</span><span class="sxs-lookup"><span data-stu-id="c76e4-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="c76e4-169">Jeder **bcp_colfmt** Aufrufe gibt das Format für eine Benutzerdatei Spalte an.</span><span class="sxs-lookup"><span data-stu-id="c76e4-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="c76e4-170">Wenn Sie z. b. die Standardeinstellungen für drei Spalten in einer Benutzer Datendatei mit fünf Spalten ändern möchten, rufen Sie zuerst [bcp_columns](bcp-columns.md)**(5)** auf, und rufen Sie dann **bcp_colfmt** fünfmal auf, wobei drei dieser Aufrufe Ihr benutzerdefiniertes Format festlegen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="c76e4-171">Legen Sie für die verbleibenden zwei Aufrufe *eUserDataType* auf 0 fest, und legen Sie *cbIndicator*, *cbUserData*und *cbUserDataTerm* auf 0, SQL_VARLEN_DATA bzw. 0 fest.</span><span class="sxs-lookup"><span data-stu-id="c76e4-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="c76e4-172">Mit diesem Verfahren werden alle fünf Spalten kopiert, drei mit dem benutzerdefinierten Format und zwei mit dem Standardformat.</span><span class="sxs-lookup"><span data-stu-id="c76e4-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="c76e4-173">Für *cbIndicator*ist der Wert 8, um anzugeben, dass ein großer Werttyp nun gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c76e4-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="c76e4-174">Wenn das Präfix für ein Feld angegeben wird, dessen entsprechende Spalte den neuen max-Typ aufweist, kann dafür nur 8 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c76e4-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="c76e4-175">Weitere Informationen finden Sie unter [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="c76e4-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="c76e4-176">Die **bcp_columns** -Funktion muss vor allen Aufrufen von **bcp_colfmt**aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c76e4-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="c76e4-177">Sie müssen **bcp_colfmt** einmal für jede Spalte in der Benutzerdatei abrufen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="c76e4-178">Wenn Sie **bcp_colfmt** mehr als einmal für eine Benutzerdatei Spalte aufrufen, wird ein Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="c76e4-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="c76e4-179">Sie brauchen nicht alle Daten in einer Benutzerdatei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle kopieren.</span><span class="sxs-lookup"><span data-stu-id="c76e4-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c76e4-180">Um eine Spalte zu überspringen, geben Sie das Format der Daten für die Spalte an, indem Sie den *idxServerCol* -Parameter auf 0 festlegen.</span><span class="sxs-lookup"><span data-stu-id="c76e4-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="c76e4-181">Wenn Sie eine Spalte überspringen möchten, müssen Sie ihren Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="c76e4-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="c76e4-182">Die [bcp_writefmt](bcp-writefmt.md) -Funktion kann verwendet werden, um die Format Spezifikation beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="c76e4-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="c76e4-183">'bcp_colfmt'-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="c76e4-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="c76e4-184">Informationen zu den Typen, die mit dem *eUserDataType* -Parameter für Datums-/Uhrzeittypen verwendet werden, finden Sie unter [Massen Kopier Änderungen für verbesserte Datums-und Uhrzeittypen &#40;OLE DB und ODBC-&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c76e4-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="c76e4-185">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c76e4-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76e4-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c76e4-186">See Also</span></span>  
 [<span data-ttu-id="c76e4-187">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="c76e4-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
