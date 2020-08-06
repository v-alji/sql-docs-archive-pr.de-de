---
title: Angeben von Datenformaten für die Kompatibilität bei Verwendung von bcp (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722845"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="049c2-102">Angeben von Datenformaten für die Kompatibilität bei Verwendung von bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="049c2-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="049c2-103">In diesem Thema werden die Datenformat Attribute, feldspezifischen Eingabe Aufforderungen und das Speichern von Feld-nach-Feld-Daten in einer nicht-XML-Format Datei des- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` Befehls beschrieben.</span><span class="sxs-lookup"><span data-stu-id="049c2-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="049c2-104">Das Verständnis dieser Konzepte kann für Sie nützlich sein, wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Daten für den Massenimport in ein anderes Programm, z. B. ein anderes Datenbankprogramm, mit einem Massenexportvorgang exportieren.</span><span class="sxs-lookup"><span data-stu-id="049c2-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="049c2-105">Die Standarddatenformate in (systemeigen, Zeichen oder Unicode) der Quelltabelle können mit dem vom anderen Programm erwarteten Datenlayout inkompatibel sein. Falls eine Inkompatibilität vorliegt, müssen Sie beim Exportieren von Daten das Datenlayout beschreiben.</span><span class="sxs-lookup"><span data-stu-id="049c2-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="049c2-106">Wenn Sie keine Erfahrung mit Datenformaten zum Importieren oder Exportieren von Daten haben, finden Sie Informationen unter [Datenformate für Massenimport oder Massenexport &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="049c2-107">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="049c2-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="049c2-108">bcp-Daten Format Attribute</span><span class="sxs-lookup"><span data-stu-id="049c2-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="049c2-109">Übersicht über die feldspezifischen Eingabe Aufforderungen</span><span class="sxs-lookup"><span data-stu-id="049c2-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="049c2-110">Speichern von Feld-nach-Feld-Daten in einer nicht-XML-Format Datei</span><span class="sxs-lookup"><span data-stu-id="049c2-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="049c2-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="049c2-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="049c2-112">bcp-Datenformatattribute</span><span class="sxs-lookup"><span data-stu-id="049c2-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="049c2-113">Mit dem Befehl `bcp` können Sie die Struktur jedes Felds in einer Datendatei im Hinblick auf die folgenden Datenformatattribute angeben:</span><span class="sxs-lookup"><span data-stu-id="049c2-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="049c2-114">Dateispeichertyp</span><span class="sxs-lookup"><span data-stu-id="049c2-114">File storage type</span></span>  
  
     <span data-ttu-id="049c2-115">Der *Dateispeichertyp* beschreibt, wie Daten in der Datendatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="049c2-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="049c2-116">Daten können in eine Datendatei als Typ der Datenbanktabelle (systemeigenes Format), als Zeichendarstellung (Zeichenformat) oder als beliebiger Datentyp, bei dem die implizite Konvertierung unterstützt wird, exportiert werden. Beispielsweise kann ein `smallint` als ein `int` kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="049c2-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="049c2-117">Benutzerdefinierte Datentypen werden als Basistypen exportiert.</span><span class="sxs-lookup"><span data-stu-id="049c2-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="049c2-118">Weitere Informationen finden Sie unter [Angeben des Dateispeichertyps mithilfe von bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="049c2-119">Präfixlänge</span><span class="sxs-lookup"><span data-stu-id="049c2-119">Prefix length</span></span>  
  
     <span data-ttu-id="049c2-120">Als kompakteste Form der Dateispeicherung beim Massenexportieren von Daten im systemeigenen Format in eine Datendatei setzt der Befehl `bcp` mindestens ein Zeichen, das auf die Länge des Felds hinweist, vor jedes Feld.</span><span class="sxs-lookup"><span data-stu-id="049c2-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="049c2-121">Diese Zeichen werden als *Längenpräfixzeichen* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="049c2-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="049c2-122">Weitere Informationen finden Sie unter [Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="049c2-123">Feldlänge</span><span class="sxs-lookup"><span data-stu-id="049c2-123">Field length</span></span>  
  
     <span data-ttu-id="049c2-124">Die Feldlänge weist auf die maximale Anzahl von Zeichen hin, die zum Darstellen der Daten im Zeichenformat benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="049c2-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="049c2-125">Die Feldlänge ist bereits bekannt, wenn die Daten im systemeigenen Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="049c2-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="049c2-126">Weitere Informationen finden Sie unter [Angeben der Feldlänge mithilfe von bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="049c2-127">Feldabschlusszeichen</span><span class="sxs-lookup"><span data-stu-id="049c2-127">Field terminator</span></span>  
  
     <span data-ttu-id="049c2-128">Für Zeichendatenfelder kann mit optionalen abschließenden Zeichen das Ende jedes Felds in einer Datendatei (mithilfe eines *Feldabschlusszeichens*) und das Ende jeder Zeile (mithilfe eines *Zeilenabschlusszeichens*) markiert werden.</span><span class="sxs-lookup"><span data-stu-id="049c2-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="049c2-129">Abschließende Zeichen sind eine Möglichkeit, um Programme, die die Datendatei lesen, darauf hinzuweisen, an welcher Stelle ein Feld oder eine Zeile endet und ein anderes Feld bzw. eine andere Zeile beginnt.</span><span class="sxs-lookup"><span data-stu-id="049c2-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="049c2-130">Weitere Informationen finden Sie unter [Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="049c2-131">Übersicht über die feldspezifischen Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="049c2-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="049c2-132">Wenn ein interaktiver `bcp` Befehl die Option **in** oder **out** enthält, aber nicht auch den Format Datei Schalter (**-f**) oder einen Datenformat Schalter (**-n**, **-c**, **-w**oder **-n**), jede Spalte in der Quell-oder Ziel Tabelle enthält, fordert der Befehl nacheinander die vorangehenden Attribute an.</span><span class="sxs-lookup"><span data-stu-id="049c2-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="049c2-133">Für jede Eingabeaufforderung stellt der Befehl `bcp` einen Standardwert basierend auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp der Tabellenspalte bereit.</span><span class="sxs-lookup"><span data-stu-id="049c2-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="049c2-134">Wenn Sie den Standardwert für alle Eingabeaufforderungen übernehmen, erhalten Sie dieselben Ergebnisse wie beim Angeben des systemeigenen Formats ( **-n**) in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="049c2-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="049c2-135">Für jede Eingabeaufforderung wird ein Standardwert in eckigen Klammern angezeigt: [*Standard*].</span><span class="sxs-lookup"><span data-stu-id="049c2-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="049c2-136">Durch Drücken der EINGABETASTE wird der angezeigte Standardwert übernommen.</span><span class="sxs-lookup"><span data-stu-id="049c2-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="049c2-137">Wenn Sie einen Wert angeben möchten, der vom Standardwert abweicht, geben Sie den neuen Wert an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="049c2-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="049c2-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="049c2-138">Example</span></span>  
 <span data-ttu-id="049c2-139">Im folgenden Beispiel werden mit dem Befehl `bcp` Daten aus der `HumanResources.myTeam`-Tabelle interaktiv in die Datei `myTeam.txt` massenexportiert.</span><span class="sxs-lookup"><span data-stu-id="049c2-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="049c2-140">Bevor Sie das Beispiel ausführen können, müssen Sie diese Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="049c2-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="049c2-141">Informationen zu dieser Tabelle und zum Erstellen der Tabelle finden Sie unter [HumanResources.myTeam-Beispieltabelle &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="049c2-142">Der Befehl gibt weder eine Formatdatei noch einen Datentyp an, weshalb `bcp` zur Eingabe von Datenformatinformationen auffordert.</span><span class="sxs-lookup"><span data-stu-id="049c2-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="049c2-143">Geben Sie an der Eingabeaufforderung von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="049c2-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="049c2-144">bcp fordert für jede Spalte zur Eingabe feldspezifischer Werte auf.</span><span class="sxs-lookup"><span data-stu-id="049c2-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="049c2-145">Das folgende Beispiel zeigt die feldspezifischen Eingabeaufforderungen für die Spalten `EmployeeID` und `Name` der Tabelle und schlägt den Standard-Dateispeichertyp (systemeigenes Format) für jede Spalte vor.</span><span class="sxs-lookup"><span data-stu-id="049c2-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="049c2-146">Die Präfixlängen der Spalten `EmployeeID` und `Name` betragen 0 bzw. 2.</span><span class="sxs-lookup"><span data-stu-id="049c2-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="049c2-147">Der Benutzer gibt ein Komma (`,`) als Feldabschlusszeichen für jedes Feld an.</span><span class="sxs-lookup"><span data-stu-id="049c2-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="049c2-148">Gleichwertige Eingabeaufforderungen (soweit erforderlich) werden für jede Tabellenspalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="049c2-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="049c2-149">Speichern von feldspezifischen Daten in einer Nicht-XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="049c2-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="049c2-150">Nachdem alle Tabellenspalten angegeben wurden, werden Sie vom Befehl `bcp` gefragt, ob optional eine Nicht-XML-Formatdatei generiert werden soll, in der die gerade eingegebenen feldspezifischen Informationen gespeichert werden (siehe vorheriges Beispiel).</span><span class="sxs-lookup"><span data-stu-id="049c2-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="049c2-151">Wenn Sie eine Formatdatei generieren, können Sie diese beim Exportieren von Daten aus dieser Tabelle oder Importieren identisch strukturierter Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="049c2-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="049c2-152">Mithilfe der Formatdatei können Sie Daten aus der Datendatei in eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] massenimportieren oder Daten aus der Tabelle massenexportieren, ohne das Format erneut angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="049c2-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="049c2-153">Weitere Informationen finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="049c2-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="049c2-154">Das folgende Beispiel erstellt die Nicht-XML-Formatdatei `myFormatFile.fmt`:</span><span class="sxs-lookup"><span data-stu-id="049c2-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="049c2-155">Der Standardname der Formatdatei ist bcp.fmt, Sie können aber einen anderen Dateinamen angeben.</span><span class="sxs-lookup"><span data-stu-id="049c2-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="049c2-156">Für eine Datendatei, die ein einziges Datenformat für den Dateispeichertyp verwendet, wie z.B. das Zeichenformat oder das native Format, können Sie mit der Option **format** schnell eine Formatdatei erstellen, ohne Daten zu exportieren oder zu importieren.</span><span class="sxs-lookup"><span data-stu-id="049c2-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="049c2-157">Diese Vorgehensweise hat den Vorteil, dass sie einfach ist und die Möglichkeit bietet, eine XML-Formatdatei oder eine Nicht-XML-Formatdatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="049c2-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="049c2-158">Weitere Informationen finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="049c2-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="049c2-159">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="049c2-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="049c2-160">Angeben des Dateispeichertyps mithilfe von bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="049c2-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="049c2-161">Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="049c2-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="049c2-162">Angeben der Feldlänge mithilfe von bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="049c2-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="049c2-163">Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="049c2-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="049c2-164">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="049c2-164">Related Content</span></span>  
 <span data-ttu-id="049c2-165">Keine.</span><span class="sxs-lookup"><span data-stu-id="049c2-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049c2-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="049c2-166">See Also</span></span>  
 <span data-ttu-id="049c2-167">[Massenimport und -export von Daten &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="049c2-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="049c2-168">[Datenformate für Massenimport oder Massenexport &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="049c2-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="049c2-169">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="049c2-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="049c2-170">Datentypen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="049c2-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
