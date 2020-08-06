---
title: Formatdateien zum Importieren oder Exportieren von Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620384"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="51cc8-102">Formatdateien zum Importieren oder Exportieren von Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51cc8-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="51cc8-103">Beim Massenimportieren bzw. -exportieren von Daten in eine bzw. aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle können Sie eine *Formatdatei* verwenden, um alle für den Massenimport oder -export erforderlichen Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51cc8-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="51cc8-104">Dazu zählen Formatinformationen für jedes Feld einer Datendatei in Bezug auf die betreffende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="51cc8-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="51cc8-105">unterstützt zwei Typen von Formatdateien: XML-Formatdateien und Nicht-XML-Formatdateien.</span><span class="sxs-lookup"><span data-stu-id="51cc8-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="51cc8-106">Sowohl Nicht-XML-Formatdateien als auch XML-Formatdateien enthalten Beschreibungen jedes Felds in einer Datendatei. XML-Formatdateien enthalten darüber hinaus auch Beschreibungen der entsprechenden Tabellenspalten.</span><span class="sxs-lookup"><span data-stu-id="51cc8-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="51cc8-107">Im Allgemeinen sind XML-Formatdateien und Nicht-XML-Formatdateien austauschbar.</span><span class="sxs-lookup"><span data-stu-id="51cc8-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="51cc8-108">Es empfiehlt sich jedoch, für neue Formatdateien die XML-Syntax zu verwenden, weil sich im Vergleich zu Nicht-XML-Formatdateien mehrere Vorteile ergeben.</span><span class="sxs-lookup"><span data-stu-id="51cc8-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="51cc8-109">Weitere Informationen finden Sie unter [XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51cc8-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="51cc8-110">Vorteile von Formatdateien</span><span class="sxs-lookup"><span data-stu-id="51cc8-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="51cc8-111">Formatdateien stellen ein flexibles System für das Schreiben von Datendateien bereit, die für die Kompatibilität mit anderen Datenformaten und zum Lesen von Datendateien aus anderen Softwareprogrammen nur geringfügig oder gar nicht bearbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="51cc8-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="51cc8-112">Durch Verwenden einer Formatdatei ist es möglich, Daten per Massenimport zu kopieren, ohne überflüssige Daten hinzufügen oder löschen oder vorhandene Daten in der Datendatei neu anordnen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="51cc8-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="51cc8-113">Formatdateien sind besonders hilfreich, wenn Felder in der Datendatei und Spalten in der Tabelle nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="51cc8-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="51cc8-114">Beispiele für Formatdateien</span><span class="sxs-lookup"><span data-stu-id="51cc8-114">Examples of Format Files</span></span>  
 <span data-ttu-id="51cc8-115">Die folgenden Beispiele zeigen das Layout einer Nicht-XML-Formatdatei und einer XML-Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="51cc8-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="51cc8-116">Diese Formatdateien entsprechen der `HumanResources.myTeam` -Tabelle in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="51cc8-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="51cc8-117">Diese Tabelle enthält vier Spalten: `EmployeeID`, `Name`, `Title`und `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="51cc8-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51cc8-118">Informationen zu dieser Tabelle und zum Erstellen der Tabelle finden Sie unter [HumanResources.myTeam-Beispieltabelle & #40;SQL Server& #41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51cc8-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="51cc8-119">A.</span><span class="sxs-lookup"><span data-stu-id="51cc8-119">A.</span></span> <span data-ttu-id="51cc8-120">Verwenden einer Nicht-XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="51cc8-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="51cc8-121">Die folgende Nicht-XML-Formatdatei verwendet das systemeigene Datenformat von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Tabelle `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="51cc8-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="51cc8-122">Diese Formatdatei wurde mithilfe des folgenden `bcp` -Befehls erstellt.</span><span class="sxs-lookup"><span data-stu-id="51cc8-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="51cc8-123">Weitere Informationen finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](non-xml-format-files-sql-server.md)unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="51cc8-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="51cc8-124">B.</span><span class="sxs-lookup"><span data-stu-id="51cc8-124">B.</span></span> <span data-ttu-id="51cc8-125">Verwenden einer XML-Formatdatei</span><span class="sxs-lookup"><span data-stu-id="51cc8-125">Using an XML format file</span></span>  
 <span data-ttu-id="51cc8-126">Die folgende XML-Formatdatei verwendet das systemeigene Datenformat von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Tabelle `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="51cc8-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="51cc8-127">Diese Formatdatei wurde mithilfe des folgenden `bcp` -Befehls erstellt.</span><span class="sxs-lookup"><span data-stu-id="51cc8-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="51cc8-128">Die Formatdatei enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="51cc8-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="51cc8-129">Weitere Informationen finden Sie unter [XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51cc8-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="51cc8-130">Wann ist eine Formatdatei erforderlich?</span><span class="sxs-lookup"><span data-stu-id="51cc8-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="51cc8-131">Eine INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung erfordert stets eine Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="51cc8-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="51cc8-132">Für **bcp** oder BULK INSERT ist in einfachen Situationen das Verwenden einer Formatdatei optional und selten notwendig.</span><span class="sxs-lookup"><span data-stu-id="51cc8-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="51cc8-133">In komplexen Massenimportsituationen ist jedoch oft eine Formatdatei erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51cc8-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="51cc8-134">Formatdateien sind in folgenden Fällen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="51cc8-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="51cc8-135">Dieselbe Datendatei wird als Quelle für mehrere Tabellen mit unterschiedlichen Schemas verwendet.</span><span class="sxs-lookup"><span data-stu-id="51cc8-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="51cc8-136">Die Datendatei hat eine andere Anzahl von Feldern, als die Zieltabelle Spalten hat. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51cc8-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="51cc8-137">Die Zieltabelle enthält mindestens eine Spalte, für die entweder ein Standardwert definiert oder NULL zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="51cc8-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="51cc8-138">Den Benutzern fehlen für mindestens eine Spalte in der Tabelle die SELECT/INSERT-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="51cc8-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="51cc8-139">Eine einzige Datendatei wird für mindestens zwei Tabellen mit unterschiedlichen Schemas verwendet.</span><span class="sxs-lookup"><span data-stu-id="51cc8-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="51cc8-140">Die Spaltenreihenfolge ist bei der Datendatei und der Tabelle unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="51cc8-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="51cc8-141">Die abschließenden Zeichen oder Präfixlängen weichen bei den Spalten der Datendatei ab.</span><span class="sxs-lookup"><span data-stu-id="51cc8-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51cc8-142">Wenn keine Formatdatei vorhanden und für einen **bcp** -Befehl ein Datenformatschalter angegeben ist ( **-n**, **-c**, **-w**oder **-N**) oder für einen BULK INSERT-Vorgang die Option DATAFILETYPE angegeben ist, wird das angegebene Datenformat als Standardmethode zum Interpretieren der Felder der Datendatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="51cc8-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="51cc8-143">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="51cc8-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="51cc8-144">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="51cc8-145">Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="51cc8-146">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="51cc8-147">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="51cc8-148">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="51cc8-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51cc8-149">See Also</span></span>  
 <span data-ttu-id="51cc8-150">[Nicht-XML-Formatdateien &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="51cc8-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="51cc8-151">[XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="51cc8-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="51cc8-152">Datenformate für Massenimport oder Massenexport &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51cc8-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
