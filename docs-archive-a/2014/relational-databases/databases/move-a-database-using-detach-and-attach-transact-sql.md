---
title: Verschieben einer Datenbank durch Trennen und Anfügen (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database attaching [SQL Server]
- moving databases [SQL Server]
- database detaching [SQL Server]
- relocating databases [SQL Server]
- detaching databases [SQL Server]
- attaching databases [SQL Server]
ms.assetid: 6732a431-cdef-4f1e-9262-4ac3b77c275e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 768a70dfe94af6f8d65f7c76fa08d3dff650fe7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622664"
---
# <a name="move-a-database-using-detach-and-attach-transact-sql"></a><span data-ttu-id="f45aa-102">Verschieben einer Datenbank durch Trennen und Anfügen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f45aa-102">Move a Database Using Detach and Attach (Transact-SQL)</span></span>
  <span data-ttu-id="f45aa-103">In diesem Thema wird beschrieben, wie eine getrennte Datenbank an einen anderen Speicherort verschoben und in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]an die gleiche oder eine andere Serverinstanz angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f45aa-103">This topic describes how to move a detached database to another location and re-attach it to the same or a different server instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="f45aa-104">Es wird jedoch empfohlen, Datenbanken mit der ALTER DATABASE-Prozedur für geplante Verschiebungen zu verschieben, anstatt die Optionen zum Trennen und Anfügen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f45aa-104">However, we recommend that you move databases by using the ALTER DATABASE planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="f45aa-105">Weitere Informationen finden Sie unter [Move User Databases](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f45aa-105">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f45aa-106">Das Anfügen oder Wiederherstellen von Datenbanken aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="f45aa-106">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="f45aa-107">Solche Datenbanken können bösartigen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code ausführt oder Fehler verursacht, indem er das Schema oder die physische Datenbankstruktur ändert.</span><span class="sxs-lookup"><span data-stu-id="f45aa-107">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="f45aa-108">Bevor Sie eine Datenbank aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, führen Sie auf einem Nichtproduktionsserver [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus. Überprüfen Sie außerdem den Code in der Datenbank, z.B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="f45aa-108">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="f45aa-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f45aa-109">Procedure</span></span>  
  
#### <a name="to-move-a-database-by-using-detach-and-attach"></a><span data-ttu-id="f45aa-110">So verschieben Sie eine Datenbank durch Trennen und Anfügen</span><span class="sxs-lookup"><span data-stu-id="f45aa-110">To move a database by using detach and attach</span></span>  
  
1.  <span data-ttu-id="f45aa-111">Trennen Sie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f45aa-111">Detach the database.</span></span> <span data-ttu-id="f45aa-112">Weitere Informationen finden Sie unter [Trennen einer Datenbank](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="f45aa-112">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
2.  <span data-ttu-id="f45aa-113">Verschieben Sie die getrennten Datenbankdateien und Protokolldateien im Windows-Explorer oder an der Windows-Eingabeaufforderung an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="f45aa-113">In a Windows Explorer or Windows Command Prompt window, move the detached database file or files and log file or files to the new location.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f45aa-114">Um eine Datenbank mit nur einer Datei zu verschieben, können Sie E-Mail verwenden, falls die Datei nicht allzu groß ist.</span><span class="sxs-lookup"><span data-stu-id="f45aa-114">To move a single-file database, you can use email if the file size is small enough for email to accommodate.</span></span>  
  
     <span data-ttu-id="f45aa-115">Sie sollten die Protokolldateien verschieben, selbst wenn Sie neue Protokolldateien erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f45aa-115">You should move the log files even if you intend to create new log files.</span></span> <span data-ttu-id="f45aa-116">In manchen Fällen sind zum erneuten Anfügen der Datenbank die vorhandenen Protokolldateien erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f45aa-116">In some cases, reattaching a database requires its existing log files.</span></span> <span data-ttu-id="f45aa-117">Deshalb sollten Sie immer alle getrennten Protokolldateien behalten, bis die Datenbank ohne sie erfolgreich angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="f45aa-117">Therefore, always keep all the detached log files until the database has been successfully attached without them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f45aa-118">Wenn Sie versuchen, die Datenbank ohne Angabe der Protokolldatei anzufügen, wird die Protokolldatei an ihrem ursprünglichen Speicherort gesucht.</span><span class="sxs-lookup"><span data-stu-id="f45aa-118">If you try to attach the database without specifying the log file, the attach operation will look for the log file in its original location.</span></span> <span data-ttu-id="f45aa-119">Falls noch eine Kopie der Protokolldatei im ursprünglichen Speicherort vorhanden ist, wird diese Kopie angefügt.</span><span class="sxs-lookup"><span data-stu-id="f45aa-119">If a copy of the log still exists in the original location, that copy is attached.</span></span> <span data-ttu-id="f45aa-120">Wenn Sie die Verwendung der ursprünglichen Protokolldatei verhindern möchten, geben Sie entweder den Pfad der neuen Protokolldatei an, oder entfernen Sie die ursprüngliche Kopie der Protokolldatei (nachdem Sie sie an einen neuen Speicherort kopiert haben).</span><span class="sxs-lookup"><span data-stu-id="f45aa-120">To avoid using the original log file, either specify the path of the new log file or remove the original copy of the log file (after copying it to the new location).</span></span>  
  
3.  <span data-ttu-id="f45aa-121">Fügen Sie die kopierten Dateien an.</span><span class="sxs-lookup"><span data-stu-id="f45aa-121">Attach the copied files.</span></span> <span data-ttu-id="f45aa-122">Weitere Informationen finden Sie unter [Attach a Database](attach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="f45aa-122">For more information, see [Attach a Database](attach-a-database.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f45aa-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f45aa-123">Example</span></span>  
 <span data-ttu-id="f45aa-124">Das folgende Beispiel erstellt eine Kopie der- [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] Anweisungen, die in einem Abfrage-Editor-Fenster ausgeführt werden, das mit der Serverinstanz verbunden ist, an die angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="f45aa-124">The following example creates a copy of the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements are executed in a Query Editor window that is connected to the server instance to which is attached.</span></span>  
  
1.  <span data-ttu-id="f45aa-125">Trennen Sie die- [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="f45aa-125">Detach the [!INCLUDE[ssSampleDBnormal](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sp_detach_db @dbname = N'AdventureWorks2012';  
    GO  
    ```  
  
2.  <span data-ttu-id="f45aa-126">Verwenden Sie die gewünschte Methode, und kopieren Sie die Datenbankdateien (AdventureWorks208R2_Data.mdf und AdventureWorks208R2_log) nach C:\MySQLServer\AdventureWorks208R2_Data.mdf bzw. C:\MySQLServer\AdventureWorks208R2_Log.ldf.</span><span class="sxs-lookup"><span data-stu-id="f45aa-126">Using the method of your choice, copy the database files (AdventureWorks208R2_Data.mdf and AdventureWorks208R2_log) to: C:\MySQLServer\AdventureWorks208R2_Data.mdf and C:\MySQLServer\AdventureWorks208R2_Log.ldf, respectively.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f45aa-127">Platzieren Sie Datenbank und Transaktionsprotokoll bei einer Produktionsdatenbank auf separaten Datenträgern.</span><span class="sxs-lookup"><span data-stu-id="f45aa-127">For a production database, place the database and transaction log on separate disks.</span></span>  
  
     <span data-ttu-id="f45aa-128">Um Dateien im Netzwerk auf einen Datenträger auf einem Remotecomputer zu kopieren, verwenden Sie den UNC-Namen (Universal Naming Convention) des Remotespeicherorts.</span><span class="sxs-lookup"><span data-stu-id="f45aa-128">To copy files over the network to a disk on a remote computer, use the universal naming convention (UNC) name of the remote location.</span></span> <span data-ttu-id="f45aa-129">Ein UNC-Name hat das Format **\\\\** _Servername_ **\\** _Sharename_ **\\** _Path_ **\\** _Filename_.</span><span class="sxs-lookup"><span data-stu-id="f45aa-129">A UNC name takes the form **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="f45aa-130">Wie beim Schreiben von Dateien auf die lokale Festplatte müssen die entsprechenden Berechtigungen für das Lesen oder Schreiben einer Datei auf dem Remotedatenträger dem von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz verwendeten Benutzerkonto erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="f45aa-130">As with writing files to the local hard disk, the appropriate permissions that are required to read or write to a file on the remote disk must be granted to the user account used by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="f45aa-131">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen aus, um die verschobene Datenbank und optional das zugehörige Protokoll anzufügen:</span><span class="sxs-lookup"><span data-stu-id="f45aa-131">Attach the moved database and, optionally, its log by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    GO  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Data.mdf'),  
        (FILENAME = 'C:\MySQLServer\AdventureWorks2012_Log.ldf')  
        FOR ATTACH;  
    GO  
    ```  
  
     <span data-ttu-id="f45aa-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ist eine neu angefügte Datenbank nicht sofort im Objekt-Explorer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="f45aa-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a newly attached database is not immediately visible in Object Explorer.</span></span> <span data-ttu-id="f45aa-133">Um die Datenbank anzuzeigen, klicken Sie im Objekt-Explorer im Menü **Ansicht** auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="f45aa-133">To view the database, in Object Explorer, click **View,** and then **Refresh**.</span></span> <span data-ttu-id="f45aa-134">Wenn der **Datenbanken** -Knoten im Objekt-Explorer erweitert wird, wird nun die neu angefügte Datenbank in der Liste der Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f45aa-134">When the **Databases** node is expanded in Object Explorer, the newly attached database now appears in the list of databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f45aa-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f45aa-135">See Also</span></span>  
 [<span data-ttu-id="f45aa-136">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f45aa-136">Database Detach and Attach &#40;SQL Server&#41;</span></span>](database-detach-and-attach-sql-server.md)  
  
  
