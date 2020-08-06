---
title: Verkleinern einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkdatabase.f1
helpviewer_keywords:
- shrinking databases
- databases [SQL Server], shrinking
- decreasing database size
- database shrinking [SQL Server]
- reducing database size
ms.assetid: 83afbf74-fd50-4c39-831c-b1f473a50620
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246036bfea6dc8431f878165330f7f0571949897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695690"
---
# <a name="shrink-a-database"></a><span data-ttu-id="4002c-102">Verkleinern einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="4002c-102">Shrink a Database</span></span>
  <span data-ttu-id="4002c-103">In diesem Thema wird beschrieben, wie eine Datenbank mit dem Objekt-Explorer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="4002c-103">This topic describes how to shrink a database by using Object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4002c-104">Mit dem Verkleinern von Datendateien wird Platz gewonnen, indem Datenseiten vom Ende der Datei an nicht belegten Platz weiter am Dateianfang verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4002c-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="4002c-105">Wurde am Ende der Datei ausreichend Platz geschaffen, kann die Zuordnung der Datenseiten am Ende der Datei aufgehoben und die Datenseiten können ins Dateisystem zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4002c-105">When enough free space is created at the end of the file, data pages at end of the file can be deallocated and returned to the file system.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4002c-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4002c-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4002c-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4002c-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4002c-108">Die Datenbank kann nicht unter die Mindestgröße der Datenbank verkleinert werden.</span><span class="sxs-lookup"><span data-stu-id="4002c-108">The database cannot be made smaller than the minimum size of the database.</span></span> <span data-ttu-id="4002c-109">Die Mindestgröße stellt die Größe dar, die bei der ursprünglichen Erstellung der Datenbank angegeben wurde, bzw. die letzte explizite Größe, die bei einer Dateigrößenänderung, z. B. mit DBCC SHRINKFILE, festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4002c-109">The minimum size is the size specified when the database was originally created, or the last explicit size set by using a file-size-changing operation, such as DBCC SHRINKFILE.</span></span> <span data-ttu-id="4002c-110">Wenn z. B. eine Datenbank ursprünglich mit einer Größe von 10 MB erstellt und auf 100 MB vergrößert wurde, kann die Datenbank höchstens auf 10 MB verkleinert werden, auch wenn alle Daten in der Datenbank gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="4002c-110">For example, if a database was originally created with a size of 10 MB and grew to 100 MB, the smallest size the database could be reduced to is 10 MB, even if all the data in the database has been deleted.</span></span>  
  
-   <span data-ttu-id="4002c-111">Während einer Datenbanksicherung können Sie die Datenbank nicht verkleinern.</span><span class="sxs-lookup"><span data-stu-id="4002c-111">You cannot shrink a database while the database is being backed up.</span></span> <span data-ttu-id="4002c-112">Umgekehrt können Sie eine Datenbank nicht sichern, während ein Verkleinerungsvorgang für die Datenbank ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4002c-112">Conversely, you cannot backup a database while a shrink operation on the database is in process.</span></span>  
  
-   <span data-ttu-id="4002c-113">Bei DBCC SHRINKDATABASE tritt ein Fehler auf, wenn ein speicheroptimierter xVelocity-columnstore-Index gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="4002c-113">DBCC SHRINKDATABASE will fail when it encounters an xVelocity memory optimized columnstore index.</span></span> <span data-ttu-id="4002c-114">Vor dem Aufeinandertreffen mit dem columnstore-Index erledigte Arbeiten werden erfolgreich durchgeführt, die Datenbank ist daher möglicherweise kleiner.</span><span class="sxs-lookup"><span data-stu-id="4002c-114">Work completed before encountering the columnstore index will succeed so the database might be smaller.</span></span> <span data-ttu-id="4002c-115">Zum Abschließen von DBCC SHRINKDATABASE deaktivieren Sie alle columnstore-Indizes, bevor Sie DBCC SHRINKDATABASE ausführen, und erstellen die columnstore-Indizes dann neu.</span><span class="sxs-lookup"><span data-stu-id="4002c-115">To complete DBCC SHRINKDATABASE, disable all columnstore indexes before executing DBCC SHRINKDATABASE, and then rebuild the columnstore indexes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="4002c-116">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="4002c-116">Recommendations</span></span>  
  
-   <span data-ttu-id="4002c-117">Zum Anzeigen des aktuellen freien (nicht zugeordneten) Speicherplatzes in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4002c-117">To view the current amount of free (unallocated) space in the database.</span></span> <span data-ttu-id="4002c-118">Weitere Informationen finden Sie unter [Anzeigen von Informationen zum Daten- und Protokollspeicherplatz einer Datenbank](display-data-and-log-space-information-for-a-database.md)</span><span class="sxs-lookup"><span data-stu-id="4002c-118">For more information, see [Display Data and Log Space Information for a Database](display-data-and-log-space-information-for-a-database.md)</span></span>  
  
-   <span data-ttu-id="4002c-119">Berücksichtigen Sie die folgenden Informationen, wenn Sie eine Datenbank verkleinern möchten:</span><span class="sxs-lookup"><span data-stu-id="4002c-119">Consider the following information when you plan to shrink a database:</span></span>  
  
    -   <span data-ttu-id="4002c-120">Ein Verkleinerungsvorgang ist am effektivsten nach einem Vorgang, durch den umfangreicher nicht verwendeter Speicherplatz bereitgestellt wird, z. B. das Abschneiden oder Löschen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4002c-120">A shrink operation is most effective after an operation that creates lots of unused space, such as a truncate table or a drop table operation.</span></span>  
  
    -   <span data-ttu-id="4002c-121">Die meisten Datenbanken erfordern verfügbaren freien Speicherplatz für die normalen alltäglichen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="4002c-121">Most databases require some free space to be available for regular day-to-day operations.</span></span> <span data-ttu-id="4002c-122">Wenn Sie eine Datenbank wiederholt verkleinern und feststellen, dass die Datenbankgröße wieder zunimmt, deutet dies darauf hin, dass der verkleinerte Speicherplatz für regelmäßige Vorgänge benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="4002c-122">If you shrink a database repeatedly and notice that the database size grows again, this indicates that the space that was shrunk is required for regular operations.</span></span> <span data-ttu-id="4002c-123">In diesem Fall ist das Verkleinern der Datenbank vergeblich.</span><span class="sxs-lookup"><span data-stu-id="4002c-123">In these cases, repeatedly shrinking the database is a wasted operation.</span></span>  
  
    -   <span data-ttu-id="4002c-124">Bei einem Verkleinerungsvorgang bleibt der Fragmentierungszustand der Indizes in der Datenbank nicht erhalten. Im Allgemeinen wird die Fragmentierung zu einem gewissen Grad verstärkt.</span><span class="sxs-lookup"><span data-stu-id="4002c-124">A shrink operation does not preserve the fragmentation state of indexes in the database, and generally increases fragmentation to a degree.</span></span> <span data-ttu-id="4002c-125">Dies ist ein weiterer Grund, die Datenbank nicht wiederholt zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="4002c-125">This is another reason not to repeatedly shrink the database.</span></span>  
  
    -   <span data-ttu-id="4002c-126">Legen Sie die Datenbankoption AUTO_SHRINK nicht auf ON fest, es sei denn, besondere Anforderungen machen dies erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4002c-126">Unless you have a specific requirement, do not set the AUTO_SHRINK database option to ON.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4002c-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4002c-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4002c-128">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4002c-128">Permissions</span></span>  
 <span data-ttu-id="4002c-129">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** oder der festen Datenbankrolle **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="4002c-129">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4002c-130">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4002c-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="4002c-131">So verkleinern Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="4002c-131">To shrink a database</span></span>  
  
1.  <span data-ttu-id="4002c-132">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="4002c-132">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="4002c-133">Erweitern Sie **Datenbanken**, und klicken Sie dann mit der rechten Maustaste auf die Datenbank, die Sie verkleinern möchten.</span><span class="sxs-lookup"><span data-stu-id="4002c-133">Expand **Databases**, and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="4002c-134">Zeigen Sie auf **Tasks**, zeigen Sie auf **Verkleinern**, und klicken Sie dann auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="4002c-134">Point to **Tasks**, point to **Shrink**, and then click **Database**.</span></span>  
  
     <span data-ttu-id="4002c-135">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="4002c-135">**Database**</span></span>  
     <span data-ttu-id="4002c-136">Zeigt den Namen der ausgewählten Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="4002c-136">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="4002c-137">**Aktuell zugeordneter Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="4002c-137">**Current allocated space**</span></span>  
     <span data-ttu-id="4002c-138">Zeigt den gesamten verwendeten und nicht verwendeten Speicherplatz für die ausgewählte Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="4002c-138">Displays the total used and unused space for the selected database.</span></span>  
  
     <span data-ttu-id="4002c-139">**Verfügbarer freier Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="4002c-139">**Available free space**</span></span>  
     <span data-ttu-id="4002c-140">Zeigt die Summe des freien Speicherplatzes in den Protokoll- und Datendateien der ausgewählten Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="4002c-140">Displays the sum of free space in the log and data files of the selected database.</span></span>  
  
     <span data-ttu-id="4002c-141">**Dateien vor dem Freigeben von nicht belegtem Speicherplatz neu organisieren**</span><span class="sxs-lookup"><span data-stu-id="4002c-141">**Reorganize files before releasing unused space**</span></span>  
     <span data-ttu-id="4002c-142">Wenn diese Option ausgewählt wird, entspricht dies dem Ausführen von DBCC SHRINKDATABASE mit der Angabe einer Option zur Prozentvorgabe.</span><span class="sxs-lookup"><span data-stu-id="4002c-142">Selecting this option is equivalent to executing DBCC SHRINKDATABASE specifying a target percent option.</span></span> <span data-ttu-id="4002c-143">Das Deaktivieren dieser Option entspricht dem Ausführen von DBCC SHRINKDATABASE mit der Option TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="4002c-143">Clearing this option is equivalent to executing DBCC SHRINKDATABASE with TRUNCATEONLY option.</span></span> <span data-ttu-id="4002c-144">Standardmäßig ist diese Option beim Öffnen des Dialogfelds nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="4002c-144">By default, this option is not selected when the dialog is opened.</span></span> <span data-ttu-id="4002c-145">Wenn diese Option ausgewählt ist, muss der Benutzer eine Option zur Prozentvorgabe angeben.</span><span class="sxs-lookup"><span data-stu-id="4002c-145">If this option is selected, the user must specify a target percent option.</span></span>  
  
     <span data-ttu-id="4002c-146">**Maximal verfügbarer Speicherplatz in Dateien nach dem Verkleinern**</span><span class="sxs-lookup"><span data-stu-id="4002c-146">**Maximum free space in files after shrinking**</span></span>  
     <span data-ttu-id="4002c-147">Geben Sie den Maximalwert für den freien Speicherplatz in Prozent an, der in den Datenbankdateien übrig bleiben soll, nachdem die Datenbank verkleinert wurde.</span><span class="sxs-lookup"><span data-stu-id="4002c-147">Enter the maximum percentage of free space to be left in the database files after the database has been shrunk.</span></span> <span data-ttu-id="4002c-148">Der zulässige Wert liegt zwischen 0 und 99.</span><span class="sxs-lookup"><span data-stu-id="4002c-148">Permissible values are between 0 and 99.</span></span>  
  
4.  <span data-ttu-id="4002c-149">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4002c-149">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4002c-150">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4002c-150">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-database"></a><span data-ttu-id="4002c-151">So verkleinern Sie eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="4002c-151">To shrink a database</span></span>  
  
1.  <span data-ttu-id="4002c-152">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="4002c-152">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4002c-153">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="4002c-153">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4002c-154">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="4002c-154">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="4002c-155">In diesem Beispiel wird [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) verwendet, um die Größe der Daten- und Protokolldateien in der Datenbank `UserDB` zu verringern und für `10` Prozent freien Speicherplatz in der Datenbank zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="4002c-155">This example uses [DBCC SHRINKDATABASE](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) to decreases the size of the data and log files in the `UserDB` database and to allow for `10` percent free space in the database.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKDB1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkdb1)]  
  
##  <a name="follow-up-after-you-shrink-a-database"></a><a name="FollowUp"></a><span data-ttu-id="4002c-156">Nächster Schritt: Nach dem Verkleinern einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="4002c-156">Follow Up: After you shrink a database</span></span>  
 <span data-ttu-id="4002c-157">Die zum Verkleinern einer Datei verschobenen Daten können an beliebigen freien Platz in der Datei verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="4002c-157">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="4002c-158">Dies führt zur Indexfragmentierung und kann die Leistung von Abfragen, die einen Bereich des Indexes suchen, verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="4002c-158">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="4002c-159">Zur Vermeidung von Fragmentierung sollten die Dateiindizes nach der Verkleinerung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4002c-159">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4002c-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4002c-160">See Also</span></span>  
 <span data-ttu-id="4002c-161">[Verkleinern einer Datei](shrink-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="4002c-161">[Shrink a File](shrink-a-file.md) </span></span>  
 <span data-ttu-id="4002c-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4002c-162">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="4002c-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4002c-163">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="4002c-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4002c-164">[DBCC &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-transact-sql) </span></span>  
 <span data-ttu-id="4002c-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4002c-165">[DBCC SHRINKFILE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) </span></span>  
 [<span data-ttu-id="4002c-166">Datenbankdateien und Dateigruppen</span><span class="sxs-lookup"><span data-stu-id="4002c-166">Database Files and Filegroups</span></span>](database-files-and-filegroups.md)  
  
  
