---
title: Zugreifen auf FILESTREAM-Daten mit Transact-SQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718289"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="b10e8-102">Zugreifen auf FILESTREAM-Daten mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b10e8-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="b10e8-103">In diesem Thema erfahren Sie, wie Sie FILESTREAM-Daten mit den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen INSERT, UPDATE und DELETE verwalten.</span><span class="sxs-lookup"><span data-stu-id="b10e8-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b10e8-104">Für die Beispiele in diesem Thema sind die FILESTREAM-aktivierte Datenbank und die Tabelle erforderlich, die unter [Erstellen einer FILESTREAM-aktivierten Datenbank](create-a-filestream-enabled-database.md) und [Erstellen einer Tabelle zum Speichern von FILESTREAM-Daten](create-a-table-for-storing-filestream-data.md)erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b10e8-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="b10e8-105">Einfügen einer Zeile mit FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="b10e8-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="b10e8-106">Zum Hinzufügen einer Zeile in einer Tabelle, die FILESTREAM-Daten unterstützt, verwenden Sie die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung INSERT.</span><span class="sxs-lookup"><span data-stu-id="b10e8-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="b10e8-107">Wenn Sie Daten in eine FILESTREAM-Spalte einfügen, können Sie NULL oder einen`varbinary(max)`-Wert einfügen.</span><span class="sxs-lookup"><span data-stu-id="b10e8-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="b10e8-108">Einfügen von NULL</span><span class="sxs-lookup"><span data-stu-id="b10e8-108">Inserting NULL</span></span>  
 <span data-ttu-id="b10e8-109">Im folgenden Beispiel wird gezeigt, wie `NULL`eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b10e8-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="b10e8-110">Wenn der FILESTREAM-Wert `NULL`ist, erstellt [!INCLUDE[ssDE](../../includes/ssde-md.md)] keine Datei im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="b10e8-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="b10e8-111">Einfügen eines Datensatzes mit der Länge 0 (null)</span><span class="sxs-lookup"><span data-stu-id="b10e8-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="b10e8-112">Das folgende Beispiel veranschaulicht, wie mit `INSERT` ein Datensatz mit der Länge 0 (null) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b10e8-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="b10e8-113">Dies ist hilfreich, wenn Sie ein Dateihandle abrufen müssen, die Datei jedoch durch die Verwendung von Win32-APIs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b10e8-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="b10e8-114">Erstellen einer Datendatei</span><span class="sxs-lookup"><span data-stu-id="b10e8-114">Creating a Data File</span></span>  
 <span data-ttu-id="b10e8-115">Das folgende Beispiel veranschaulicht, wie mit `INSERT` eine Datei mit Daten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b10e8-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="b10e8-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] konvertiert die Zeichenfolge `Seismic Data` in einen `varbinary(max)` -Wert.</span><span class="sxs-lookup"><span data-stu-id="b10e8-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="b10e8-117">FILESTREAM erstellt die Windows-Datei, falls diese noch nicht erstellt wurde. Die Daten werden dann der Datendatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b10e8-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="b10e8-118">Wenn Sie alle Daten in der Tabelle `Archive`.`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="b10e8-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="b10e8-119">auswählen, sollten ähnliche Ergebnisse wie in der folgenden Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b10e8-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="b10e8-120">Die `Id` -Spalte enthält jedoch andere GUIDs.</span><span class="sxs-lookup"><span data-stu-id="b10e8-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="b10e8-121">Id</span><span class="sxs-lookup"><span data-stu-id="b10e8-121">Id</span></span>|<span data-ttu-id="b10e8-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="b10e8-122">SerialNumber</span></span>|<span data-ttu-id="b10e8-123">Fortsetzen</span><span class="sxs-lookup"><span data-stu-id="b10e8-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="b10e8-124">Aktualisieren von FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="b10e8-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="b10e8-125">Sie können [!INCLUDE[tsql](../../includes/tsql-md.md)] zum Aktualisieren der Daten in der Dateisystemdatei verwenden. Dies ist jedoch nicht empfehlenswert, wenn Sie große Datenmengen in eine Datei streamen müssen.</span><span class="sxs-lookup"><span data-stu-id="b10e8-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="b10e8-126">Im folgenden Beispiel wird der gesamte Text im Dateidatensatz durch den Text `Xray 1`ersetzt.</span><span class="sxs-lookup"><span data-stu-id="b10e8-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="b10e8-127">Löschen von FILESTREAM-Daten</span><span class="sxs-lookup"><span data-stu-id="b10e8-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="b10e8-128">Wenn Sie eine Zeile mit einem FILESTREAM-Feld löschen, löschen Sie auch die zugrunde liegenden Dateisystemdateien.</span><span class="sxs-lookup"><span data-stu-id="b10e8-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="b10e8-129">Die einzige Möglichkeit zum Löschen einer Zeile, und somit der Datei, ist die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung DELETE.</span><span class="sxs-lookup"><span data-stu-id="b10e8-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="b10e8-130">Im folgenden Beispiel wird das Löschen einer Zeile und der entsprechenden Dateisystemdateien veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b10e8-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="b10e8-131">Wenn Sie alle Daten in der Tabelle `dbo.Archive` auswählen, sollten Sie sehen, dass die Zeile gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="b10e8-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="b10e8-132">Sie können die zugeordnete Datei nicht mehr verwenden.</span><span class="sxs-lookup"><span data-stu-id="b10e8-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b10e8-133">Die zugrunde liegenden Dateien werden vom FILESTREAM Garbage Collector entfernt.</span><span class="sxs-lookup"><span data-stu-id="b10e8-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10e8-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b10e8-134">See Also</span></span>  
 <span data-ttu-id="b10e8-135">[Aktivieren und Konfigurieren von FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="b10e8-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="b10e8-136">Vermeiden von Konflikten mit Datenbankvorgängen in FILESTREAM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b10e8-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
