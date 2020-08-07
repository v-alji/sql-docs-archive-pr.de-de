---
title: bcp_control | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607737"
---
# <a name="bcp_control"></a><span data-ttu-id="cd0a2-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="cd0a2-102">bcp_control</span></span>
  <span data-ttu-id="cd0a2-103">Ändert die Standardeinstellungen für verschiedene Steuerelementparameter für einen Massenkopiervorgang zwischen einer Datei und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd0a2-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd0a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd0a2-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cd0a2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cd0a2-105">Arguments</span></span>  
 <span data-ttu-id="cd0a2-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cd0a2-106">*hdbc*</span></span>  
 <span data-ttu-id="cd0a2-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="cd0a2-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="cd0a2-108">*eOption*</span></span>  
 <span data-ttu-id="cd0a2-109">Ist einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="cd0a2-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="cd0a2-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="cd0a2-110">BCPABORT</span></span>  
 <span data-ttu-id="cd0a2-111">Beendet einen Massenkopiervorgang, der bereits ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="cd0a2-112">Ruft **bcp_control** mit der *eOption* "BCPABORT" von einem anderen Thread auf, um einen ausgelaufenden Massen Kopiervorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="cd0a2-113">Der *iValue* -Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="cd0a2-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="cd0a2-114">BCPBATCH</span></span>  
 <span data-ttu-id="cd0a2-115">Die Anzahl von Zeilen pro Batch.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-115">Is the number of rows per batch.</span></span> <span data-ttu-id="cd0a2-116">Der Standardwert ist 0, womit beim Extrahieren von Daten alle Zeilen in einer Tabelle oder beim Kopieren von Daten nach [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alle Zeilen in der Benutzerdatendatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cd0a2-117">Ein Wert kleiner als 1 setzt BCPBATCH auf den Standardwert zurück.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="cd0a2-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="cd0a2-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="cd0a2-119">Ein boolescher Wert, wenn er auf "true" festgelegt ist, bewirkt, dass [bcp_readfmt](bcp-readfmt.md) bei der Ausführung liest.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="cd0a2-120">Der Standardwert false gibt an, dass bcp_readfmt die Format Datei sofort liest.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="cd0a2-121">Ein Sequenz Fehler tritt auf, wenn bcpdelta ayread fmt den Wert true aufweist und Sie bcp_columns oder bcp_setcolfmt aufgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="cd0a2-122">Ein Sequenz Fehler tritt auch auf, wenn Sie nach dem Aufruf von `bcp_control(hdbc,` `, (void *)FALSE)` `bcp_control(hdbc,` bcpdelta ayread fmt und bcp_writefmt bcpdelta aylefmt aufrufen `, (void *)TRUE)` .</span><span class="sxs-lookup"><span data-stu-id="cd0a2-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="cd0a2-123">Weitere Informationen finden Sie unter [Metadatenermittlung](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="cd0a2-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="cd0a2-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="cd0a2-124">BCPFILECP</span></span>  
 <span data-ttu-id="cd0a2-125">*iValue* enthält die Nummer der Codepage für die Datendatei.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="cd0a2-126">Sie können die Nummer der Codepage angeben, z. B. 1252 oder 850 bzw. einen der folgenden Werte</span><span class="sxs-lookup"><span data-stu-id="cd0a2-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="cd0a2-127">BCPFILE_ACP: Daten in der Datei befinden sich in Microsoft Windows??</span><span class="sxs-lookup"><span data-stu-id="cd0a2-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="cd0a2-128">Codepage des Clients.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-128">code page of the client.</span></span>  
  
 <span data-ttu-id="cd0a2-129">BCPFILE_OEMCP: Daten in der Datei befinden sich auf der OEM-Codepage des Clients (Standard).</span><span class="sxs-lookup"><span data-stu-id="cd0a2-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="cd0a2-130">BCPFILE_RAW: Daten in der Datei befinden sich auf der Codepage von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd0a2-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cd0a2-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="cd0a2-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="cd0a2-132">Die Versionsnummer des Datendateiformats.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-132">The version number of the data file format.</span></span> <span data-ttu-id="cd0a2-133">Dies kann 80 ( [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ), 90 ( [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ), 100 ( [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ), 110 ( [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ) oder 120 () sein [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd0a2-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="cd0a2-134">Der Standardwert ist 120.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-134">120 is the default.</span></span> <span data-ttu-id="cd0a2-135">Dies ist beim Exportieren und Importieren von Daten in Formate nützlich, die in früheren Versionen des Servers unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="cd0a2-136">Wenn Sie z. b. Daten aus einer Text Spalte eines [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Servers in eine **varchar (max)** -Spalte auf einem Server mit oder höher importieren möchten [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , sollten Sie 80 angeben.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="cd0a2-137">Wenn Sie beim Exportieren von Daten aus einer Spalte vom Typ " **varchar (max)** " den Wert "80" angeben, wird dieser ebenso wie Textspalten im [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] Format gespeichert und kann in eine Text Spalte eines Servers importiert werden [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd0a2-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="cd0a2-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="cd0a2-138">BCPFIRST</span></span>  
 <span data-ttu-id="cd0a2-139">Dies ist die erste Datenzeile der zu kopierenden Datei oder Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="cd0a2-140">Der Standard ist 1; ein Wert kleiner als 1 setzt diese Option auf den Standardwert zurück.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="cd0a2-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="cd0a2-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="cd0a2-142">Gibt für BCP-OUT-Vorgänge die erste Zeile der Datenbanktabelle an, die in die Datendatei kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="cd0a2-143">Gibt für BCP-IN-Vorgänge die erste Zeile der Datendatei an, die in die Datenbanktabelle kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="cd0a2-144">Der *iValue* -Parameter wird als Adresse einer signierten 64-Bit-Ganzzahl mit dem Wert erwartet.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="cd0a2-145">Der maximale Wert, der an BCPFIRSTEX übermittelt werden kann, ist 2 ^ 63-1.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="cd0a2-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="cd0a2-146">BCPFMTXML</span></span>  
 <span data-ttu-id="cd0a2-147">Gibt an, dass die generierte Format Datei im XML-Format vorliegen soll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="cd0a2-148">Sie ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-148">It is off by default.</span></span>  
  
 <span data-ttu-id="cd0a2-149">XML-Formatdateien bieten größere Flexibilität, sind jedoch mit einigen Einschränkungen verbunden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="cd0a2-150">Sie können z. b. das Präfix und das Abschluss Zeichen für ein Feld nicht gleichzeitig angeben, was in älteren Format Dateien möglich war.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd0a2-151">XML-Formatdateien werden nur unterstützt, wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zusammen mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client installiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="cd0a2-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="cd0a2-152">BCPHINTS</span></span>  
 <span data-ttu-id="cd0a2-153">*iValue* enthält einen SQLTCHAR-Zeichen folgen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="cd0a2-154">Die adressierte Zeichenfolge gibt entweder Verarbeitungshinweise für das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Massenkopieren oder eine Transact-SQL-Anweisung an, die ein Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="cd0a2-155">Wenn eine Transact-SQL-Anweisung angegeben ist, die mehr als ein Resultset zurückgibt, werden alle auf das erste Resultset folgenden Resultsets nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="cd0a2-156">Weitere Informationen zur Verarbeitung von Massen Kopier Vorgängen finden Sie unter [bcp (Hilfsprogramm](../../tools/bcp-utility.md)).</span><span class="sxs-lookup"><span data-stu-id="cd0a2-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="cd0a2-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="cd0a2-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="cd0a2-158">Wenn *iValue* auf true festgelegt ist, wird angegeben, dass die Massen Kopierfunktionen Datenwerte einfügen, die für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit einer Identitäts Einschränkung definierte Spalten bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="cd0a2-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="cd0a2-159">Die Eingabedatei muss Werte für die IDENTITY-Spalten angeben.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="cd0a2-160">Wenn dies nicht festgelegt ist, werden neue Identitätswerte für die eingefügten Zeilen generiert.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="cd0a2-161">Alle in der Datei für die IDENTITY-Spalten vorhandenen Daten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="cd0a2-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="cd0a2-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="cd0a2-163">Bestimmt, ob leere Datenwerte in der Datei in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle in NULL-Werte konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="cd0a2-164">Wenn *iValue* true ist, werden leere Werte in der Tabelle in NULL konvertiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd0a2-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="cd0a2-165">In der Standardeinstellung werden leere Werte in einen Standardwert für die Spalte in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle konvertiert, sofern ein Standardwert angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="cd0a2-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="cd0a2-166">BCPLAST</span></span>  
 <span data-ttu-id="cd0a2-167">Entspricht der letzten zu kopierenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-167">Is the last row to copy.</span></span> <span data-ttu-id="cd0a2-168">In der Standardeinstellung werden alle Zeilen kopiert. Ein Wert kleiner als 1 setzt diese Option auf den Standardwert zurück.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="cd0a2-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="cd0a2-169">BCPLASTEX</span></span>  
 <span data-ttu-id="cd0a2-170">Gibt für BCP-OUT-Vorgänge die letzte Zeile der Datenbanktabelle an, die in die Datendatei kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="cd0a2-171">Gibt für BCP-IN-Vorgänge die letzte Zeile der Datendatei an, die in die Datenbanktabelle kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="cd0a2-172">Der *iValue* -Parameter wird als Adresse einer signierten 64-Bit-Ganzzahl mit dem Wert erwartet.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="cd0a2-173">Der maximale Wert, der an BCPLASTEX übergeben werden kann, ist 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="cd0a2-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="cd0a2-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="cd0a2-175">Gibt die Anzahl von Fehlern an, die zulässig sind, bevor der Massenkopiervorgang fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="cd0a2-176">Der Standardwert ist 10. ein Wert kleiner als 1 setzt diese Option auf den Standardwert zurück.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="cd0a2-177">Beim Massenkopieren sind maximal 65.535 Fehler zulässig.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="cd0a2-178">Wenn für diese Option größere Werte als 65.535 festgelegt werden, wird diese Option auf 65.535 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="cd0a2-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="cd0a2-179">BCPODBC</span></span>  
 <span data-ttu-id="cd0a2-180">Wenn der Wert true ist, wird angegeben, dass **DateTime** -und **smalldatetime** -Werte, die im Zeichenformat gespeichert werden, das ODBC-Zeitstempel-Präfix und-Suffix</span><span class="sxs-lookup"><span data-stu-id="cd0a2-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="cd0a2-181">Die BCPODBC-Option gilt nur für BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="cd0a2-182">Bei false wird ein **DateTime** -Wert, der den 1. Januar 1997 darstellt, in die Zeichenfolge: 1997-01-01 00:00:00.000 konvertiert.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="cd0a2-183">Wenn der Wert true ist, wird der gleiche **DateTime** -Wert wie folgt dargestellt: {TS "1997-01-01 00:00:00.000"}.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="cd0a2-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="cd0a2-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="cd0a2-185">Gibt die Anzahl von Zeilen zurück, auf die sich der aktuelle (oder letzte) BCP-Vorgang auswirkt.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="cd0a2-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="cd0a2-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="cd0a2-187">Wenn der Wert TRUE ist, wird angegeben, dass die Datendatei eine Textdatei und keine Binärdatei ist.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="cd0a2-188">Bei einer Textdatei bestimmt BCP, ob es sich um Unicode handelt, indem der Unicode-Bytemarker in den ersten beiden Bytes der Datendatei überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="cd0a2-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="cd0a2-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="cd0a2-190">Wenn der Wert TRUE ist, wird angegeben, dass die Eingabedatei eine Unicode-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="cd0a2-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="cd0a2-191">*iValue*</span></span>  
 <span data-ttu-id="cd0a2-192">Der Wert für die angegebene *eOption*.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="cd0a2-193">*iValue* ist ein ganzzahliger Wert (Longlong), der in einen void-Zeiger umgewandelt wird, um zukünftige Erweiterungen auf 64-Bit-Werte zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cd0a2-194">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="cd0a2-194">Returns</span></span>  
 <span data-ttu-id="cd0a2-195">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd0a2-196">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cd0a2-196">Remarks</span></span>  
 <span data-ttu-id="cd0a2-197">Mit dieser Funktion werden verschiedene Steuerelementparameter für Massenkopiervorgänge festgelegt, einschließlich der Anzahl von Fehlern, die vor dem Abbrechen eines Massenkopiervorgangs zulässig sind, der Nummern der ersten und letzten Zeilen, die aus einer Datendatei kopiert werden sollen, und der Batchgröße.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="cd0a2-198">Außerdem wird diese Funktion dazu verwendet, die SELECT-Anweisung beim Massenkopieren des Resultsets einer SELECT-Anweisung aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="cd0a2-199">Legen Sie *eOption* auf BCPHINTS fest, und legen Sie *iValue* auf einen Zeiger auf eine SQLTCHAR-Zeichenfolge fest, die die SELECT-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="cd0a2-200">Diese Steuerelementparameter sind nur beim Kopieren zwischen einer Benutzerdatei und einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="cd0a2-201">Steuerelement Parametereinstellungen wirken sich nicht auf Zeilen aus, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit [bcp_sendrow](bcp-sendrow.md)kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0a2-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd0a2-202">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd0a2-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
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
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd0a2-203">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd0a2-203">See Also</span></span>  
 [<span data-ttu-id="cd0a2-204">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cd0a2-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
