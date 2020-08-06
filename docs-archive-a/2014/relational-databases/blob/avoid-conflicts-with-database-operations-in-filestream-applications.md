---
title: Vermeiden von Konflikten mit Datenbankvorgängen in FILESTREAM-Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Win32 and Transact-SQL Conflicts
ms.assetid: 8b1ee196-69af-4f9b-9bf5-63d8ac2bc39b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0ac7e681766396d3a3b4412d91a968b4cdc653c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621029"
---
# <a name="avoid-conflicts-with-database-operations-in-filestream-applications"></a><span data-ttu-id="c592f-102">Vermeiden von Konflikten mit Datenbankvorgängen in FILESTREAM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="c592f-102">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>
  <span data-ttu-id="c592f-103">Bei Anwendungen, die SqlOpenFilestream() zum Öffnen von Win32-Dateihandles zum Lesen oder Schreiben von FILESTREAM-BLOB-Daten verwenden, können Konfliktfehler mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen auftreten, die in einer gemeinsamen Transaktion verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c592f-103">Applications that use SqlOpenFilestream() to open Win32 file handles for reading or writing FILESTREAM BLOB data can encounter conflict errors with [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that are managed in a common transaction.</span></span> <span data-ttu-id="c592f-104">Dies gilt auch für [!INCLUDE[tsql](../../includes/tsql-md.md)] - oder MARS-Abfragen, bei denen das Beenden der Ausführung viel Zeit in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="c592f-104">This includes [!INCLUDE[tsql](../../includes/tsql-md.md)] or MARS queries that take a long time to finish execution.</span></span> <span data-ttu-id="c592f-105">Anwendungen müssen sorgfältig entworfen werden, wenn diese Art von Konflikten vermieden werden soll.</span><span class="sxs-lookup"><span data-stu-id="c592f-105">Applications must be carefully designed to help avoid these types of conflicts.</span></span>  
  
 <span data-ttu-id="c592f-106">Wenn die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] oder Anwendungen versuchen, FILESTREAM-BLOBs zu öffnen, überprüft die [!INCLUDE[ssDE](../../includes/ssde-md.md)] den zugeordneten Transaktionskontext.</span><span class="sxs-lookup"><span data-stu-id="c592f-106">When [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] or applications try to open FILESTREAM BLOBs, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] checks the associated transaction context.</span></span> <span data-ttu-id="c592f-107">Die [!INCLUDE[ssDE](../../includes/ssde-md.md)] lässt die Anforderung zu bzw. verweigert sie in Abhängigkeit davon, ob der geöffnete Vorgang mit DDL-Anweisungen oder DML-Anweisungen arbeitet, Daten abruft oder Transaktionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c592f-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] allows or denies the request based on whether the open operation is working with DDL statements, DML statements, retrieving data, or managing transactions.</span></span> <span data-ttu-id="c592f-108">Die folgende Tabelle zeigt, wie die [!INCLUDE[ssDE](../../includes/ssde-md.md)] ermittelt, ob eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung basierend auf dem Typ der Dateien, die in der Transaktion geöffnet sind, zugelassen oder verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="c592f-108">The following table shows how the [!INCLUDE[ssDE](../../includes/ssde-md.md)] determines whether a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement will be allowed or denied based on the type of files that are open in the transaction.</span></span>  
  
|<span data-ttu-id="c592f-109">Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="c592f-109">Transact-SQL statements</span></span>|<span data-ttu-id="c592f-110">Geöffnet zum Lesen</span><span class="sxs-lookup"><span data-stu-id="c592f-110">Opened for read</span></span>|<span data-ttu-id="c592f-111">Geöffnet zum Schreiben</span><span class="sxs-lookup"><span data-stu-id="c592f-111">Opened for write</span></span>|  
|------------------------------|---------------------|----------------------|  
|<span data-ttu-id="c592f-112">DDL-Anweisungen, die mit Datenbankmetadaten arbeiten, z. B. CREATE TABLE, CREATE INDEX, DROP TABLE und ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="c592f-112">DDL statements that work with database metadata, such as CREATE TABLE, CREATE INDEX, DROP TABLE, and ALTER TABLE.</span></span>|<span data-ttu-id="c592f-113">Zulässig</span><span class="sxs-lookup"><span data-stu-id="c592f-113">Allowed</span></span>|<span data-ttu-id="c592f-114">Werden blockiert und schlagen mit einem Timeout fehl.</span><span class="sxs-lookup"><span data-stu-id="c592f-114">Are blocked and fail with a time-out.</span></span>|  
|<span data-ttu-id="c592f-115">DML-Anweisungen, die mit den Daten arbeiten, die in der Datenbank gespeichert sind, z. B. UPDATE, DELETE und INSERT.</span><span class="sxs-lookup"><span data-stu-id="c592f-115">DML statements that work with the data that is stored in the database, such as UPDATE, DELETE, and INSERT.</span></span>|<span data-ttu-id="c592f-116">Zulässig</span><span class="sxs-lookup"><span data-stu-id="c592f-116">Allowed</span></span>|<span data-ttu-id="c592f-117">Verweigert</span><span class="sxs-lookup"><span data-stu-id="c592f-117">Denied</span></span>|  
|<span data-ttu-id="c592f-118">SELECT</span><span class="sxs-lookup"><span data-stu-id="c592f-118">SELECT</span></span>|<span data-ttu-id="c592f-119">Zulässig</span><span class="sxs-lookup"><span data-stu-id="c592f-119">Allowed</span></span>|<span data-ttu-id="c592f-120">Zulässig</span><span class="sxs-lookup"><span data-stu-id="c592f-120">Allowed</span></span>|  
|<span data-ttu-id="c592f-121">COMMIT TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="c592f-121">COMMIT TRANSACTION</span></span>|<span data-ttu-id="c592f-122">Verweigert\*</span><span class="sxs-lookup"><span data-stu-id="c592f-122">Denied\*</span></span>|<span data-ttu-id="c592f-123">Verweigert\*</span><span class="sxs-lookup"><span data-stu-id="c592f-123">Denied\*.</span></span>|  
|<span data-ttu-id="c592f-124">SAVE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="c592f-124">SAVE TRANSACTION</span></span>|<span data-ttu-id="c592f-125">Verweigert\*</span><span class="sxs-lookup"><span data-stu-id="c592f-125">Denied\*</span></span>|<span data-ttu-id="c592f-126">Verweigert\*</span><span class="sxs-lookup"><span data-stu-id="c592f-126">Denied\*</span></span>|  
|<span data-ttu-id="c592f-127">ROLLBACK</span><span class="sxs-lookup"><span data-stu-id="c592f-127">ROLLBACK</span></span>|<span data-ttu-id="c592f-128">Zulässig\*</span><span class="sxs-lookup"><span data-stu-id="c592f-128">Allowed\*</span></span>|<span data-ttu-id="c592f-129">Zulässig\*</span><span class="sxs-lookup"><span data-stu-id="c592f-129">Allowed\*</span></span>|  
  
 <span data-ttu-id="c592f-130">\* Die Transaktion wird abgebrochen, und geöffnete Handles für den Transaktionskontext werden für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="c592f-130">\* The transaction is canceled, and open handles for the transaction context are invalidated.</span></span> <span data-ttu-id="c592f-131">Die Anwendung muss alle geöffneten Handles schließen.</span><span class="sxs-lookup"><span data-stu-id="c592f-131">The application must close all open handles.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c592f-132">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c592f-132">Examples</span></span>  
 <span data-ttu-id="c592f-133">In den folgenden Beispielen wird gezeigt, wie [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen und der FILESTREAM-Win32-Zugriff Konflikte verursachen können.</span><span class="sxs-lookup"><span data-stu-id="c592f-133">The following examples show how [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and FILESTREAM Win32 access can cause conflicts.</span></span>  
  
### <a name="a-opening-a-filestream-blob-for-write-access"></a><span data-ttu-id="c592f-134">A.</span><span class="sxs-lookup"><span data-stu-id="c592f-134">A.</span></span> <span data-ttu-id="c592f-135">Öffnen eines FILESTREAM-BLOB für Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="c592f-135">Opening a FILESTREAM BLOB for write access</span></span>  
 <span data-ttu-id="c592f-136">Das folgende Beispiel zeigt die Auswirkung des Öffnens einer Datei nur für den Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="c592f-136">The following example shows the effect of opening a file for write access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//Write some date to the FILESTREAM BLOB.  
WriteFile(dstHandle, updateData, ...);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed. The FILESTREAM BLOB is  
//returned without the modifications that are made by  
//WriteFile(dstHandle, updateData, ...).  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed. The FILESTREAM BLOB  
//is returned with the updateData applied.  
```  
  
### <a name="b-opening-a-filestream-blob-for-read-access"></a><span data-ttu-id="c592f-137">B.</span><span class="sxs-lookup"><span data-stu-id="c592f-137">B.</span></span> <span data-ttu-id="c592f-138">Öffnen eines FILESTREAM-BLOB für Lesezugriff</span><span class="sxs-lookup"><span data-stu-id="c592f-138">Opening a FILESTREAM BLOB for read access</span></span>  
 <span data-ttu-id="c592f-139">Das folgende Beispiel zeigt die Auswirkung des Öffnens einer Datei nur für den Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="c592f-139">The following example shows the effect of opening a file for read access only.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed. Any changes that are  
//made to the FILESTREAM BLOB will not be returned until  
//the dstHandle is closed.  
//SELECT statements will be allowed.  
CloseHandle(dstHandle);  
  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="c-opening-and-closing-multiple-filestream-blob-files"></a><span data-ttu-id="c592f-140">C.</span><span class="sxs-lookup"><span data-stu-id="c592f-140">C.</span></span> <span data-ttu-id="c592f-141">Öffnen und Schließen von mehreren FILESTREAM-BLOB-Dateien</span><span class="sxs-lookup"><span data-stu-id="c592f-141">Opening and closing multiple FILESTREAM BLOB files</span></span>  
 <span data-ttu-id="c592f-142">Wenn mehrere Dateien geöffnet sind, wird die restriktivste Regel verwendet.</span><span class="sxs-lookup"><span data-stu-id="c592f-142">If multiple files are open, the most restrictive rule is used.</span></span> <span data-ttu-id="c592f-143">Im folgenden Beispiel werden zwei Dateien geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c592f-143">The following example opens two files.</span></span> <span data-ttu-id="c592f-144">Die erste Datei wird für den Lesezugriff geöffnet, die zweite für den Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="c592f-144">The first file is opened for read and the second for write.</span></span> <span data-ttu-id="c592f-145">DML-Anweisungen werden verweigert, bis die zweite Datei geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c592f-145">DML statements will be denied until the second file is opened.</span></span>  
  
```  
dstHandle =  OpenSqlFilestream(dstFilePath, Read, 0,  
    transactionToken, cbTransactionToken, 0);  
//DDL statements will be denied.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
  
dstHandle1 =  OpenSqlFilestream(dstFilePath1, Write, 0,  
    transactionToken, cbTransactionToken, 0);  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
//Close the read handle. The write handle is still open.  
CloseHandle(dstHandle);  
//DML statements are still denied because the write handle is open.  
  
//DDL statements will be denied.  
//DML statements will be denied.  
//SELECT statements will be allowed.  
  
CloseHandle(dstHandle1);  
//DDL statements will be allowed.  
//DML statements will be allowed.  
//SELECT statements will be allowed.  
```  
  
### <a name="d-failing-to-close-a-cursor"></a><span data-ttu-id="c592f-146">D:</span><span class="sxs-lookup"><span data-stu-id="c592f-146">D.</span></span> <span data-ttu-id="c592f-147">Fehler beim Schließen eines Cursors</span><span class="sxs-lookup"><span data-stu-id="c592f-147">Failing to close a cursor</span></span>  
 <span data-ttu-id="c592f-148">Das folgende Beispiel zeigt, wie ein nicht geschlossener Anweisungscursor verhindern kann, dass `OpenSqlFilestream()` den BLOB für den Schreibzugriff öffnen kann.</span><span class="sxs-lookup"><span data-stu-id="c592f-148">The following example shows how a statement cursor that is not closed can prevent `OpenSqlFilestream()` from opening the BLOB for write access.</span></span>  
  
```  
TCHAR *sqlDBQuery =  
TEXT("SELECT GET_FILESTREAM_TRANSACTION_CONTEXT(),")  
TEXT("Chart.PathName() FROM Archive.dbo.Records");  
  
//Execute a long-running Transact-SQL statement. Do not allow  
//the statement to complete before trying to  
//open the file.  
  
SQLExecDirect(hstmt, sqlDBQuery, SQL_NTS);  
  
//Before you call OpenSqlFilestream() any open files  
//that the Cursor the Transact-SQL statement is using  
// must be closed. In this example,  
//SQLCloseCursor(hstmt) is not called so that  
//the transaction will indicate that there is a file  
//open for reading. This will cause the call to  
//OpenSqlFilestream() to fail because the file is  
//still open.  
  
HANDLE srcHandle =  OpenSqlFilestream(srcFilePath,  
     Write, 0,  transactionToken,  cbTransactionToken,  0);  
  
//srcHandle will == INVALID_HANDLE_VALUE because the  
//cursor is still open.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c592f-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c592f-149">See Also</span></span>  
 <span data-ttu-id="c592f-150">[ZUgreifen auf FILESTREAM-Daten mit OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span><span class="sxs-lookup"><span data-stu-id="c592f-150">[Access FILESTREAM Data with OpenSqlFilestream](access-filestream-data-with-opensqlfilestream.md) </span></span>  
 [<span data-ttu-id="c592f-151">Verwenden von Multiple Active Result Sets &#40;MARS&#41;</span><span class="sxs-lookup"><span data-stu-id="c592f-151">Using Multiple Active Result Sets &#40;MARS&#41;</span></span>](../native-client/features/using-multiple-active-result-sets-mars.md)  
  
  
