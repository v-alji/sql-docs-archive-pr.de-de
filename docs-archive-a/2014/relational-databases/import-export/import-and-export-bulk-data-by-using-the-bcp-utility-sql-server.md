---
title: Importieren und Exportieren von Massendaten mithilfe des Hilfsprogramms bcp (SQL Server) | Microsoft-Dokumentation
ms.prod: sql-server-2014
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], bcp utility
- bulk importing [SQL Server], bcp utility
- bcp utility [SQL Server], about bcp utility
ms.assetid: 73e949de-67a3-4c84-9735-7da1ad4ba34a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: ''
ms.date: 06/14/2017
ms.openlocfilehash: 7d1892b26f3c638a696d8ed15e739f56ac2e682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620378"
---
# <a name="import-and-export-bulk-data-by-using-the-bcp-utility-sql-server"></a><span data-ttu-id="0264a-102">Importieren und Exportieren von Massendaten mithilfe des Hilfsprogramms bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0264a-102">Import and Export Bulk Data by Using the bcp Utility (SQL Server)</span></span>

<span data-ttu-id="0264a-103">In diesem Thema erhalten Sie einen Überblick zum Verwenden des Hilfsprogramms [bcp](../../tools/bcp-utility.md) zum Exportieren von Daten von jeder Stelle innerhalb einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank, an der eine SELECT-Anweisung verwendet werden kann, einschließlich partitionierter Sichten.</span><span class="sxs-lookup"><span data-stu-id="0264a-103">This topic provides an overview for using the [bcp utility](../../tools/bcp-utility.md) to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database where a SELECT statement works, including partitioned views.</span></span>  
  
 <span data-ttu-id="0264a-104">Das Hilfsprogramm bcp (Bcp.exe) ist ein Befehlszeilentool, das die BCP-API (Bulk Copy Program) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0264a-104">The bcp utility (Bcp.exe) is a command-line tool that uses the Bulk Copy Program (BCP) API.</span></span> <span data-ttu-id="0264a-105">Mit dem Hilfsprogramm bcp werden die folgenden Tasks ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="0264a-105">The bcp utility performs the following tasks:</span></span>  
  
-   <span data-ttu-id="0264a-106">Massenexport von Daten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle in eine Datendatei.</span><span class="sxs-lookup"><span data-stu-id="0264a-106">Bulk exports data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into a data file.</span></span>  
  
-   <span data-ttu-id="0264a-107">Massenexport von Daten aus einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="0264a-107">Bulk exports data from a query.</span></span>  
  
-   <span data-ttu-id="0264a-108">Massenimport von Daten aus einer Datendatei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0264a-108">Bulk imports data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
-   <span data-ttu-id="0264a-109">Generieren von Formatdateien.</span><span class="sxs-lookup"><span data-stu-id="0264a-109">Generates format files.</span></span>  
  
 <span data-ttu-id="0264a-110">Auf das Hilfsprogramm „bcp“ wird über den Befehl **bcp** zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="0264a-110">The bcp utility is accessed by the **bcp** command.</span></span> <span data-ttu-id="0264a-111">Für den Massenimport von Daten mithilfe des Befehls **bcp** ist es erforderlich, das Schema der Tabelle und die Datentypen der Spalten zu verstehen, es sei denn, Sie verwenden eine bereits vorhandene Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="0264a-111">To use the **bcp** command to bulk import data, you must understand the schema of the table and the data types of its columns, unless you are using a pre-existing format file.</span></span>  
  
 <span data-ttu-id="0264a-112">Mit dem Hilfsprogramm "bcp" können Daten aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle in eine Datendatei exportiert und dann in anderen Programmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0264a-112">The bcp utility can export data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table to a data file for use in other programs.</span></span> <span data-ttu-id="0264a-113">Das Hilfsprogramm kann auch dazu verwendet werden, Daten aus einem anderen Programm, meist einem anderen Datenbank-Managementsystem (DBMS, Database Management System), in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="0264a-113">The utility can also import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table from another program, usually another database management system (DBMS).</span></span> <span data-ttu-id="0264a-114">Die Daten werden zuerst aus dem Quellprogramm in eine Datendatei exportiert und dann, in einem getrennten Vorgang, aus der Datendatei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle kopiert.</span><span class="sxs-lookup"><span data-stu-id="0264a-114">The data is first exported from the source program to a data file and then, in a separate operation, copied from the data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0264a-115">Der Befehl **bcp** stellt Schalter bereit, mit denen Sie den Datentyp der Datendatei und andere Informationen angeben.</span><span class="sxs-lookup"><span data-stu-id="0264a-115">The **bcp** command provides switches that you use to specify the data type of the data file and other information.</span></span> <span data-ttu-id="0264a-116">Wenn diese Schalter nicht angegeben werden, werden vom Befehl Formatierungsinformationen (z. B. der Typ der Datenfelder in einer Datendatei) abgefragt.</span><span class="sxs-lookup"><span data-stu-id="0264a-116">If these switches are not specified, the command prompts for formatting information, such as the type of data fields in a data file.</span></span> <span data-ttu-id="0264a-117">Anschließend müssen Sie festlegen, ob Sie eine Formatdatei mit Ihren interaktiven Antworten erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0264a-117">The command then asks whether you want to create a format file that contains your interactive responses.</span></span> <span data-ttu-id="0264a-118">Eine Formatdatei ist oft hilfreich, wenn Sie für zukünftige Massenimport- oder Massenexportvorgänge flexibel sein müssen.</span><span class="sxs-lookup"><span data-stu-id="0264a-118">If you want flexibility for future bulk-import or bulk-export operations, a format file is often useful.</span></span> <span data-ttu-id="0264a-119">Sie können die Formatdatei bei späteren **bcp** -Befehlen für äquivalente Datendateien angeben.</span><span class="sxs-lookup"><span data-stu-id="0264a-119">You can specify the format file on later **bcp** commands for equivalent data files.</span></span> <span data-ttu-id="0264a-120">Weitere Informationen finden Sie unter [Angeben von Datenformaten für die Kompatibilität bei Verwendung von „bcp“ &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0264a-120">For more information, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0264a-121">Das bcp-Hilfsprogramm wird mithilfe der ODBC-Massenkopierung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0264a-121">The bcp utility is written by using the ODBC bulk-copy</span></span>  
  
 <span data-ttu-id="0264a-122">Eine Beschreibung der **bcp** -Befehlssyntax finden Sie unter [bcp (Hilfsprogramm)](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="0264a-122">For a description of the **bcp** command syntax, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0264a-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0264a-123">Examples</span></span>

 <span data-ttu-id="0264a-124">**bcp**-Beispiele finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="0264a-124">For **bcp** examples, see:</span></span>  
  
-   [<span data-ttu-id="0264a-125">bcp (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="0264a-125">bcp Utility</span></span>](../../tools/bcp-utility.md)  
  
-   [<span data-ttu-id="0264a-126">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-126">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="0264a-127">Beispiele für den Massenimport und -export von XML-Dokumenten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-127">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="0264a-128">Beibehalten von Identitätswerten beim Massenimport von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-128">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="0264a-129">Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-129">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="0264a-130">Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-130">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="0264a-131">Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-131">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="0264a-132">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="0264a-133">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-133">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="0264a-134">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="0264a-135">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0264a-135">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  

## <a name="see-also"></a><span data-ttu-id="0264a-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0264a-136">See Also</span></span>

<span data-ttu-id="0264a-137">[&#40;Transact-SQL-&#41;einfügen](/sql/t-sql/statements/insert-transact-sql) 
 [SELECT-Klausel &#40;Transact-SQL-&#41;](/sql/t-sql/queries/select-clause-transact-sql) 
 [bcp-Hilfsprogramm](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0264a-137">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql)
[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql)
[bcp Utility](../../tools/bcp-utility.md) </span></span>  
<span data-ttu-id="0264a-138">[Vorbereiten des Massen Imports von Daten &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md) 
 [Bulk Insert &#40;Transact-SQL-&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) 
 [Massen Import und-Export von Daten &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) 
 [OPENROWSET &#40;Transact-SQL-&#41;](/sql/t-sql/functions/openrowset-transact-sql) 
 [Erstellen Sie eine Format Datei &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="0264a-138">[Prepare to Bulk Import Data &#40;SQL Server&#41;](prepare-to-bulk-import-data-sql-server.md)
[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql)
[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md)
[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)
[Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md)</span></span>