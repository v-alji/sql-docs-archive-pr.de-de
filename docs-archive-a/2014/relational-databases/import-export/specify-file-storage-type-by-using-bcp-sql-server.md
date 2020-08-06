---
title: Angeben des Dateispeichertyps mithilfe von bcp (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609213"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="0cc7c-102">Angeben des Dateispeichertyps mithilfe von bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0cc7c-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="0cc7c-103">Der *Dateispeichertyp* beschreibt, wie Daten in der Datendatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="0cc7c-104">Daten können in eine Datendatei als Typ der Datenbanktabelle (systemeigenes Format), als Zeichendarstellung (Zeichenformat) oder als beliebiger Datentyp, bei dem die implizite Konvertierung unterstützt wird, exportiert werden. Beispielsweise kann ein `smallint` als ein `int` kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="0cc7c-105">Benutzerdefinierte Datentypen werden als Basistypen exportiert.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="0cc7c-106">Die bcp-Eingabeaufforderung für den Dateispeichertyp</span><span class="sxs-lookup"><span data-stu-id="0cc7c-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="0cc7c-107">Wenn ein interaktiver **bcp** -Befehl die Option **in** oder **out** , jedoch keinen Formatdateischalter ( **-f**) bzw. keinen Datenformatschalter ( **-n**, **-c**, **-w**oder **-N**) enthält, fordert der Befehl wie folgt zur Eingabe des Dateispeichertyps für jedes Datenfeld auf:</span><span class="sxs-lookup"><span data-stu-id="0cc7c-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="0cc7c-108">Ihre Eingabe hängt dann von der Aufgabe ab, die Sie ausführen möchten (siehe folgende Liste).</span><span class="sxs-lookup"><span data-stu-id="0cc7c-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="0cc7c-109">Nehmen Sie die von **bcp** bereitgestellten Standarddateispeichertypen an, wenn Sie einen Massenexport für Daten aus einer Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in eine Datendatei in der kompaktesten Speicherform (natives Datenformat) durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="0cc7c-110">Eine Liste der systemeigenen Dateispeichertypen finden Sie unter "Systemeigene Dateispeichertypen" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="0cc7c-111">Für das Massenexportieren von Daten aus einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in eine Datendatei im Zeichenformat geben Sie `char` als Dateispeichertyp für alle Spalten in der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="0cc7c-112">Für den Massenimport von Daten in eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus einer Datendatei geben Sie den Dateispeichertyp als `char` für Typen an, die im Zeichenformat gespeichert sind. Geben Sie für im systemeigenen Datentypformat gespeicherte Daten einen entsprechenden Dateispeichertyp wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="0cc7c-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="0cc7c-113">Dateispeichertyp</span><span class="sxs-lookup"><span data-stu-id="0cc7c-113">File storage type</span></span>|<span data-ttu-id="0cc7c-114">Eingabe an der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="0cc7c-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="0cc7c-115">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="0cc7c-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="0cc7c-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="0cc7c-117">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="0cc7c-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="0cc7c-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="0cc7c-119">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="0cc7c-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="0cc7c-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="0cc7c-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="0cc7c-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="0cc7c-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="0cc7c-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="0cc7c-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="0cc7c-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="0cc7c-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="0cc7c-127">`UDT` (ein benutzerdefinierter Datentyp)</span><span class="sxs-lookup"><span data-stu-id="0cc7c-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="0cc7c-128"><sup>1</sup> die Interaktion von Feldlänge, Präfix Länge und Abschluss Zeichen bestimmt die Menge an Speicherplatz, die in einer Datendatei für nicht auf Zeichen basierende Daten zugeordnet wird, die als `char` Datei Speichertyp exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="0cc7c-129"><sup>2</sup> die `ntext` `text` Datentypen, und werden `image` in einer zukünftigen Version von entfernt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cc7c-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0cc7c-130">Vermeiden Sie den Gebrauch dieser Datentypen bei neuen Entwicklungen, und richten Sie sich auf die Änderung von Anwendungen ein, in denen sie zurzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="0cc7c-131">Verwenden `nvarchar(max)` Sie `varchar(max)` stattdessen, und `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="0cc7c-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="0cc7c-132">Systemeigene Dateispeichertypen</span><span class="sxs-lookup"><span data-stu-id="0cc7c-132">Native File Storage Types</span></span>  
 <span data-ttu-id="0cc7c-133">Jeder systemeigene Speichertyp wird in der Formatdatei als entsprechender Datentyp der Hostdatei aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="0cc7c-134">Dateispeichertyp</span><span class="sxs-lookup"><span data-stu-id="0cc7c-134">File storage type</span></span>|<span data-ttu-id="0cc7c-135">Datentyp in der Hostdatei</span><span class="sxs-lookup"><span data-stu-id="0cc7c-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="0cc7c-136">`char` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="0cc7c-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="0cc7c-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="0cc7c-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="0cc7c-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="0cc7c-141">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="0cc7c-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-142">SQLCHAR</span></span>|  
|<span data-ttu-id="0cc7c-143">`ntext`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="0cc7c-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="0cc7c-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="0cc7c-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="0cc7c-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="0cc7c-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="0cc7c-146">SQLBINARY</span></span>|  
|<span data-ttu-id="0cc7c-147">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0cc7c-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="0cc7c-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="0cc7c-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="0cc7c-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="0cc7c-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="0cc7c-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="0cc7c-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="0cc7c-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="0cc7c-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="0cc7c-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="0cc7c-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="0cc7c-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="0cc7c-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="0cc7c-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="0cc7c-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="0cc7c-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="0cc7c-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="0cc7c-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="0cc7c-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="0cc7c-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="0cc7c-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="0cc7c-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="0cc7c-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="0cc7c-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="0cc7c-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="0cc7c-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="0cc7c-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="0cc7c-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="0cc7c-164">SQLBINARY</span></span>|  
|<span data-ttu-id="0cc7c-165">UDT (ein benutzerdefinierter Datentyp)</span><span class="sxs-lookup"><span data-stu-id="0cc7c-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="0cc7c-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="0cc7c-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="0cc7c-167"><sup>1</sup> Datendateien, die im Zeichenformat gespeichert sind, werden `char` als Datei Speichertyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="0cc7c-168">SQLCHAR ist deshalb für Zeichendatendateien der einzige Datentyp, der in einer Formatdatei aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="0cc7c-169"><sup>2</sup> Sie können keinen Massen Import von Daten in `text` `ntext` -,-und- `image` Spalten mit Standardwerten durchgehen.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="0cc7c-170">Zusätzliche Aspekte von Dateispeichertypen</span><span class="sxs-lookup"><span data-stu-id="0cc7c-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="0cc7c-171">Beachten Sie beim Massenexport von Daten aus einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in eine Datendatei Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0cc7c-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="0cc7c-172">Sie können jederzeit `char` als Dateispeichertyp angeben.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="0cc7c-173">Wenn Sie einen Datei Speichertyp eingeben, der eine ungültige implizite Konvertierung darstellt, schlägt **bcp** fehl. Wenn Sie z `int` . b. für Daten angeben können `smallint` , `smallint` resultieren Überlauf Fehler, wenn Sie für `int` Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="0cc7c-174">Wenn nicht auf Zeichen basierende Datentypen wie `float`, `money`, `datetime` oder `int` als entsprechende Datenbanktypen gespeichert werden, werden die Daten im systemeigenen Format von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in die Datendatei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0cc7c-175">Nachdem Sie interaktiv alle Felder in einem **bcp**-Befehl angegeben haben, werden Sie vom Befehl dazu aufgefordert, Ihre Antworten für die einzelnen Felder in einer Nicht-XML-Formatdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0cc7c-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="0cc7c-176">Weitere Informationen zu Nicht-XML-Formatdateien finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0cc7c-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc7c-177">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cc7c-177">See Also</span></span>  
 <span data-ttu-id="0cc7c-178">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0cc7c-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="0cc7c-179">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0cc7c-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="0cc7c-180">[Angeben der Feldlänge mithilfe von bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cc7c-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="0cc7c-181">[Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0cc7c-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="0cc7c-182">Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0cc7c-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
