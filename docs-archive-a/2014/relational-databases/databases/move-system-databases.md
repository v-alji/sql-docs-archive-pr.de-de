---
title: Verschieben von Systemdatenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- moving system databases
- disaster recovery [SQL Server], moving database files
- database files [SQL Server], moving
- data files [SQL Server], moving
- tempdb database [SQL Server], moving
- system databases [SQL Server], moving
- scheduled disk maintenace [SQL Server]
- moving databases
- msdb database [SQL Server], moving
- moving database files
- relocating database files
- planned database relocations [SQL Server]
- master database [SQL Server], moving
- model database [SQL Server], moving
- Resource database [SQL Server]
- databases [SQL Server], moving
ms.assetid: 72bb62ee-9602-4f71-be51-c466c1670878
author: stevestein
ms.author: sstein
ms.openlocfilehash: 748d781d6bbefb0dc710427a34ebd71ec7037fdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727009"
---
# <a name="move-system-databases"></a><span data-ttu-id="b6184-102">Verschieben von Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="b6184-102">Move System Databases</span></span>
  <span data-ttu-id="b6184-103">In diesem Thema wird beschrieben, wie Systemdatenbanken in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-103">This topic describes how to move system databases in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6184-104">Das Verschieben von Systemdatenbanken kann in den folgenden Situationen nützlich sein:</span><span class="sxs-lookup"><span data-stu-id="b6184-104">Moving system databases may be useful in the following situations:</span></span>  
  
-   <span data-ttu-id="b6184-105">Bei der Wiederherstellung nach Fehlern.</span><span class="sxs-lookup"><span data-stu-id="b6184-105">Failure recovery.</span></span> <span data-ttu-id="b6184-106">Wenn z. B. die Datenbank aufgrund eines Hardwarefehlers als fehlerverdächtig eingestuft oder heruntergefahren wurde.</span><span class="sxs-lookup"><span data-stu-id="b6184-106">For example, the database is in suspect mode or has shut down because of a hardware failure.</span></span>  
  
-   <span data-ttu-id="b6184-107">Bei geplanter Verschiebung.</span><span class="sxs-lookup"><span data-stu-id="b6184-107">Planned relocation.</span></span>  
  
-   <span data-ttu-id="b6184-108">Verschiebung aufgrund planmäßiger Datenträgerwartung.</span><span class="sxs-lookup"><span data-stu-id="b6184-108">Relocation for scheduled disk maintenance.</span></span>  
  
 <span data-ttu-id="b6184-109">Die folgenden Verfahren gelten für das Verschieben von Datenbankdateien innerhalb derselben Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6184-109">The following procedures apply to moving database files within the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6184-110">Zum Verschieben einer Datenbank in eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder auf einen anderen Server können Sie die Vorgänge [Sichern und Wiederherstellen](../backup-restore/back-up-and-restore-of-sql-server-databases.md) oder [Trennen und Anfügen](move-a-database-using-detach-and-attach-transact-sql.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6184-110">To move a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to another server, use the [backup and restore](../backup-restore/back-up-and-restore-of-sql-server-databases.md) or [detach and attach](move-a-database-using-detach-and-attach-transact-sql.md) operations.</span></span>  
  
 <span data-ttu-id="b6184-111">Für die Prozeduren in diesem Thema ist der logische Name der Datenbankdateien erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b6184-111">The procedures in this topic require the logical name of the database files.</span></span> <span data-ttu-id="b6184-112">Zum Abrufen des Namens führen Sie eine Abfrage für die Namensspalte in der [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) -Katalogsicht aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-112">To obtain the name, query the name column in the [sys.master_files](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) catalog view.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6184-113">Wenn Sie eine Systemdatenbank verschieben und anschließend die master-Datenbank neu erstellen, müssen Sie die Systemdatenbank erneut verschieben, da bei der Neuerstellung alle Systemdatenbanken an ihrem standardmäßigen Speicherort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-113">If you move a system database and later rebuild the master database, you must move the system database again because the rebuild operation installs all system databases to their default location.</span></span>  
  
##  <a name="in-this-topic"></a><a name="Intro"></a> <span data-ttu-id="b6184-114">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b6184-114">**In This Topic**</span></span>  
  
-   [<span data-ttu-id="b6184-115">Prozeduren für geplante Verschiebungen und geplante Datenträger Wartung</span><span class="sxs-lookup"><span data-stu-id="b6184-115">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>](#Planned)  
  
-   [<span data-ttu-id="b6184-116">Prozedur zur Fehlerwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="b6184-116">Failure Recovery Procedure</span></span>](#Failure)  
  
-   [<span data-ttu-id="b6184-117">Verschieben der Master-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-117">Moving the master Database</span></span>](#master)  
  
-   [<span data-ttu-id="b6184-118">Verschieben der Ressourcendatenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-118">Moving the Resource Database</span></span>](#Resource)  
  
-   [<span data-ttu-id="b6184-119">Nachverfolgung: nach dem Verschieben aller System Datenbanken</span><span class="sxs-lookup"><span data-stu-id="b6184-119">Follow-up: After Moving All System Databases</span></span>](#Follow)  
  
-   [<span data-ttu-id="b6184-120">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b6184-120">Examples</span></span>](#Examples)  
  
##  <a name="planned-relocation-and-scheduled-disk-maintenance-procedure"></a><a name="Planned"></a> <span data-ttu-id="b6184-121">Prozedur zur geplanten Verschiebung und planmäßigen Datenträgerwartung</span><span class="sxs-lookup"><span data-stu-id="b6184-121">Planned Relocation and Scheduled Disk Maintenance Procedure</span></span>  
 <span data-ttu-id="b6184-122">Zum Verschieben von Systemdatenbankdaten- oder Protokolldateien im Rahmen einer geplanten Verschiebung oder planmäßiger Wartungsarbeiten führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b6184-122">To move a system database data or log file as part of a planned relocation or scheduled maintenance operation, follow these steps.</span></span> <span data-ttu-id="b6184-123">Diese Prozedur gilt für alle Systemdatenbanken mit Ausnahme der master- und Resource-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="b6184-123">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
1.  <span data-ttu-id="b6184-124">Führen Sie für jede zu verschiebende Datei die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-124">For each file to be moved, run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE ( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
2.  <span data-ttu-id="b6184-125">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , oder fahren Sie das System für die Wartungsarbeiten herunter.</span><span class="sxs-lookup"><span data-stu-id="b6184-125">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or shut down the system to perform maintenance.</span></span> <span data-ttu-id="b6184-126">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten von SQL Server-Diensten](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="b6184-126">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="b6184-127">Verschieben Sie die Datei(en) an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b6184-127">Move the file or files to the new location.</span></span>  
  
4.  <span data-ttu-id="b6184-128">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder den Server neu.</span><span class="sxs-lookup"><span data-stu-id="b6184-128">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the server.</span></span> <span data-ttu-id="b6184-129">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten von SQL Server-Diensten](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="b6184-129">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
5.  <span data-ttu-id="b6184-130">Überprüfen Sie die Dateiänderung durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b6184-130">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
 <span data-ttu-id="b6184-131">Wenn die msdb-Datenbank verschoben wurde und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz für [Datenbank-E-Mail](../database-mail/database-mail.md)konfiguriert ist, führen Sie zusätzlich die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-131">If the msdb database is moved and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured for [Database Mail](../database-mail/database-mail.md), complete these additional steps.</span></span>  
  
1.  <span data-ttu-id="b6184-132">Überprüfen Sie mit der folgenden Abfrage, ob [!INCLUDE[ssSB](../../../includes/sssb-md.md)] für die msdb-Datenbank aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b6184-132">Verify that [!INCLUDE[ssSB](../../../includes/sssb-md.md)] is enabled for the msdb database by running the following query.</span></span>  
  
    ```  
    SELECT is_broker_enabled   
    FROM sys.databases  
    WHERE name = N'msdb';  
    ```  
  
     <span data-ttu-id="b6184-133">Weitere Informationen zum Aktivieren von [!INCLUDE[ssSB](../../../includes/sssb-md.md)]finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql)verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-133">For more information about enabling [!INCLUDE[ssSB](../../../includes/sssb-md.md)], see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
2.  <span data-ttu-id="b6184-134">Überprüfen Sie, ob Datenbank-E-Mail funktionsfähig ist, indem Sie eine Test-E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="b6184-134">Verify that Database Mail is working by sending a test mail.</span></span>  
  
##  <a name="failure-recovery-procedure"></a><a name="Failure"></a> <span data-ttu-id="b6184-135">Prozedur zur Wiederherstellung nach Fehlern</span><span class="sxs-lookup"><span data-stu-id="b6184-135">Failure Recovery Procedure</span></span>  
 <span data-ttu-id="b6184-136">Wenn eine Datei aufgrund eines Hardwarefehlers verschoben werden muss, müssen Sie die folgenden Schritte ausführen, um die Datei an einen neuen Speicherort zu verschieben:</span><span class="sxs-lookup"><span data-stu-id="b6184-136">If a file must be moved because of a hardware failure, follow these steps to relocate the file to a new location.</span></span> <span data-ttu-id="b6184-137">Diese Prozedur gilt für alle Systemdatenbanken mit Ausnahme der master- und Resource-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="b6184-137">This procedure applies to all system databases except the master and Resource databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b6184-138">Wenn die Datenbank nicht gestartet werden kann, d. h., wenn sie als fehlerverdächtig eingestuft wurde oder sich in einem nicht wiederhergestellten Status befindet, können nur Mitglieder der festen Rolle sysadmin die Datei verschieben.</span><span class="sxs-lookup"><span data-stu-id="b6184-138">If the database cannot be started, that is it is in suspect mode or in an unrecovered state, only members of the sysadmin fixed role can move the file.</span></span>  
  
1.  <span data-ttu-id="b6184-139">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , wenn sie gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="b6184-139">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if it is started.</span></span>  
  
2.  <span data-ttu-id="b6184-140">Starten Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz im ausschließlichen Wiederherstellungsmodus der master-Datenbank durch Eingeben der folgenden Befehle an der Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="b6184-140">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in master-only recovery mode by entering one of the following commands at the command prompt.</span></span> <span data-ttu-id="b6184-141">Bei den in diesen Befehlen angegebenen Parametern wird nach Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="b6184-141">The parameters specified in these commands are case sensitive.</span></span> <span data-ttu-id="b6184-142">Die Befehle werden nicht ausgeführt, wenn die Parameter nicht wie gezeigt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-142">The commands fail when the parameters are not specified as shown.</span></span>  
  
    -   <span data-ttu-id="b6184-143">Führen Sie für die Standardinstanz (MSSQLSERVER) den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b6184-143">For the default (MSSQLSERVER) instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQLSERVER /f /T3608  
        ```  
  
    -   <span data-ttu-id="b6184-144">Führen Sie für eine benannte Instanz den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b6184-144">For a named instance, run the following command:</span></span>  
  
        ```  
        NET START MSSQL$instancename /f /T3608  
        ```  
  
     <span data-ttu-id="b6184-145">Weitere Informationen finden Sie unter [Starten, Beenden, Anhalten, Fortsetzen und Neustarten von SQL Server-Diensten](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span><span class="sxs-lookup"><span data-stu-id="b6184-145">For more information, see [Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md).</span></span>  
  
3.  <span data-ttu-id="b6184-146">Verwenden Sie für jede zu verschiebende Datei die **sqlcmd** -Befehle oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , um die folgende Anweisung auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b6184-146">For each file to be moved, use **sqlcmd** commands or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to run the following statement.</span></span>  
  
    ```  
    ALTER DATABASE database_name MODIFY FILE( NAME = logical_name , FILENAME = 'new_path\os_file_name' )  
    ```  
  
     <span data-ttu-id="b6184-147">Weitere Informationen zum Verwenden des **sqlcmd** -Hilfsprogramms finden Sie unter [Verwenden des Hilfsprogramms „sqlcmd“](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b6184-147">For more information about using the **sqlcmd** utility, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
4.  <span data-ttu-id="b6184-148">Starten Sie das Hilfsprogramm **sqlcmd** oder [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6184-148">Exit the **sqlcmd** utility or [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span>  
  
5.  <span data-ttu-id="b6184-149">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6184-149">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6184-150">Führen Sie dazu z. B. `NET STOP MSSQLSERVER`aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-150">For example, run `NET STOP MSSQLSERVER`.</span></span>  
  
6.  <span data-ttu-id="b6184-151">Verschieben Sie die Datei(en) an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b6184-151">Move the file or files to the new location.</span></span>  
  
7.  <span data-ttu-id="b6184-152">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="b6184-152">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6184-153">Führen Sie dazu z. B. `NET START MSSQLSERVER`aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-153">For example, run `NET START MSSQLSERVER`.</span></span>  
  
8.  <span data-ttu-id="b6184-154">Überprüfen Sie die Dateiänderung durch Ausführen der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b6184-154">Verify the file change by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'<database_name>');  
    ```  
  
##  <a name="moving-the-master-database"></a><a name="master"></a> <span data-ttu-id="b6184-155">Verschieben der master-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-155">Moving the master Database</span></span>  
 <span data-ttu-id="b6184-156">Führen Sie die folgenden Schritte aus, um die master-Datenbank zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b6184-156">To move the master database, follow these steps.</span></span>  
  
1.  <span data-ttu-id="b6184-157">Zeigen Sie im Menü **Start** auf **Alle Programme**, auf **Microsoft SQL Server 2005**, auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="b6184-157">From the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="b6184-158">Klicken Sie im Knoten **SQL Server-Dienste** mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (z. B. **SQL Server (MSSQLSERVER)** ), und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-158">In the **SQL Server Services** node, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (for example, **SQL Server (MSSQLSERVER)**) and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="b6184-159">Klicken Sie im Dialogfeld \*\*Eigenschaften von SQL Server ( \*\*\*Instanzname \***)** auf die Registerkarte **Startparameter** .</span><span class="sxs-lookup"><span data-stu-id="b6184-159">In the **SQL Server (***instance_name***) Properties** dialog box, click the **Startup Parameters** tab.</span></span>  
  
4.  <span data-ttu-id="b6184-160">Wählen Sie im Feld **Vorhandene Parameter** den Parameter „-d“aus, um die Masterdatendatei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b6184-160">In the **Existing parameters** box, select the -d parameter to move the master data file.</span></span> <span data-ttu-id="b6184-161">Klicken Sie auf **Aktualisieren** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b6184-161">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="b6184-162">Ändern Sie im Feld **Startparameter angeben** den Parameter in den neuen Pfad der Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="b6184-162">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
5.  <span data-ttu-id="b6184-163">Wählen Sie im Feld **Vorhandene Parameter** den Parameter „-l“aus, um die Masterprotokolldatei zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b6184-163">In the **Existing parameters** box, select the -l parameter to move the master log file.</span></span> <span data-ttu-id="b6184-164">Klicken Sie auf **Aktualisieren** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b6184-164">Click **Update** to save the change.</span></span>  
  
     <span data-ttu-id="b6184-165">Ändern Sie im Feld **Startparameter angeben** den Parameter in den neuen Pfad der Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="b6184-165">In the **Specify a startup parameter** box, change the parameter to the new path of the master database.</span></span>  
  
     <span data-ttu-id="b6184-166">Der Parameterwert der Datendatei muss dem `-d` -Parameter und der Wert der Protokolldatei muss dem `-l` -Parameter entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b6184-166">The parameter value for the data file must follow the `-d` parameter and the value for the log file must follow the `-l` parameter.</span></span> <span data-ttu-id="b6184-167">Im folgenden Beispiel werden die Parameterwerte für den Standardspeicherort der Masterdatendatei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b6184-167">The following example shows the parameter values for the default location of the master data file.</span></span>  
  
     `-dC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\master.mdf`  
  
     `-lC:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\mastlog.ldf`  
  
     <span data-ttu-id="b6184-168">Wenn der geplante Speicherort für das Verschieben der Masterdatendatei `E:\SQLData`lautet, werden die Parameterwerte folgendermaßen geändert:</span><span class="sxs-lookup"><span data-stu-id="b6184-168">If the planned relocation for the master data file is `E:\SQLData`, the parameter values would be changed as follows:</span></span>  
  
     `-dE:\SQLData\master.mdf`  
  
     `-lE:\SQLData\mastlog.ldf`  
  
6.  <span data-ttu-id="b6184-169">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , indem Sie mit der rechten Maustaste auf den Instanznamen klicken und **Beenden**auswählen.</span><span class="sxs-lookup"><span data-stu-id="b6184-169">Stop the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by right-clicking the instance name and choosing **Stop**.</span></span>  
  
7.  <span data-ttu-id="b6184-170">Verschieben Sie die Dateien master.mdf und mastlog.ldf an den neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b6184-170">Move the master.mdf and mastlog.ldf files to the new location.</span></span>  
  
8.  <span data-ttu-id="b6184-171">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="b6184-171">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="b6184-172">Überprüfen Sie die Dateiänderung für die master-Datenbank, indem Sie die folgende Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="b6184-172">Verify the file change for the master database by running the following query.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID('master');  
    GO  
    ```  
  
##  <a name="moving-the-resource-database"></a><a name="Resource"></a> <span data-ttu-id="b6184-173">Verschieben der Ressourcendatenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-173">Moving the Resource Database</span></span>  
 <span data-ttu-id="b6184-174">Der Speicherort der Ressourcendatenbank lautet \<*drive*>:\Programme\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span><span class="sxs-lookup"><span data-stu-id="b6184-174">The location of the Resource database is \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\\.</span></span> <span data-ttu-id="b6184-175">Die Datenbank kann nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-175">The database cannot be moved.</span></span>  
  
##  <a name="follow-up-after-moving-all-system-databases"></a><a name="Follow"></a> <span data-ttu-id="b6184-176">Nächster Schritt: Nach dem Verschieben aller Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="b6184-176">Follow-up: After Moving All System Databases</span></span>  
 <span data-ttu-id="b6184-177">Wenn Sie alle Systemdatenbanken auf ein neues Laufwerk oder Volume bzw. auf einen anderen Server mit einem anderen Laufwerkbuchstaben verschoben haben, führen Sie die folgenden Updates aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-177">If you have moved all of the system databases to a new drive or volume or to another server with a different drive letter, make the following updates.</span></span>  
  
-   <span data-ttu-id="b6184-178">Ändern Sie den Pfad des SQL Server-Agent-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="b6184-178">Change the SQL Server Agent log path.</span></span> <span data-ttu-id="b6184-179">Wenn Sie diesen Pfad nicht aktualisieren, kann SQL Server-Agent nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-179">If you do not update this path, SQL Server Agent will fail to start.</span></span>  
  
-   <span data-ttu-id="b6184-180">Ändern Sie den Standardspeicherort der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b6184-180">Change the database default location.</span></span> <span data-ttu-id="b6184-181">Beim Erstellen einer neuen Datenbank kann ein Fehler auftreten, wenn der als Standardspeicherort angegebene Laufwerkbuchstabe und Pfad nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b6184-181">Creating a new database may fail if the drive letter and path specified as the default location do not exist.</span></span>  
  
#### <a name="change-the-sql-server-agent-log-path"></a><span data-ttu-id="b6184-182">Ändern des Pfads des SQL Server-Agent-Protokolls</span><span class="sxs-lookup"><span data-stu-id="b6184-182">Change the SQL Server Agent Log Path</span></span>  
  
1.  <span data-ttu-id="b6184-183">Erweitern Sie in SQL Server Management Studio im Objekt-Explorer **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="b6184-183">From SQL Server Management Studio, in Object Explorer, expand **SQL Server Agent**.</span></span>  
  
2.  <span data-ttu-id="b6184-184">Klicken Sie mit der rechten Maustaste auf **Fehlerprotokolle** , und klicken Sie auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="b6184-184">Right-click **Error Logs** and click **Configure**.</span></span>  
  
3.  <span data-ttu-id="b6184-185">Geben Sie im Dialogfeld **Fehlerprotokolle des SQL Server-Agents konfigurieren** den neuen Speicherort der Datei SQLAGENT.OUT an.</span><span class="sxs-lookup"><span data-stu-id="b6184-185">In the **Configure SQL Server Agent Error Logs** dialog box, specify the new location of the SQLAGENT.OUT file.</span></span> <span data-ttu-id="b6184-186">Der Standard Speicherort ist "c:\Programme\Microsoft SQL server\mssql12. <instance_name> \MSSQL\LOG" \\ .</span><span class="sxs-lookup"><span data-stu-id="b6184-186">The default location is C:\Program Files\Microsoft SQL Server\MSSQL12.<instance_name>\MSSQL\Log\\.</span></span>  
  
#### <a name="change-the-database-default-location"></a><span data-ttu-id="b6184-187">Ändern des Standardspeicherorts der Datenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-187">Change the database default location</span></span>  
  
1.  <span data-ttu-id="b6184-188">Klicken Sie in SQL Server Management Studio im Objekt-Explorer mit der rechten Maustaste auf den SQL Server-Server, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b6184-188">From SQL Server Management Studio, in Object Explorer, right-click the SQL Server server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b6184-189">Wählen Sie im Dialogfeld **Servereigenschaften** die Option **Datenbankeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="b6184-189">In the **Server Properties** dialog box, select **Database Settings**.</span></span>  
  
3.  <span data-ttu-id="b6184-190">Wechseln Sie unter **Standardspeicherorte für Datenbank**zum neuen Speicherort sowohl für die Daten- als auch die Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="b6184-190">Under **Database Default Locations**, browse to the new location for both the data and log files.</span></span>  
  
4.  <span data-ttu-id="b6184-191">Starten und beenden Sie den SQL Server-Dienst, um die Änderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b6184-191">Stop and start the SQL Server service to complete the change.</span></span>  
  
##  <a name="examples"></a><a name="Examples"></a> <span data-ttu-id="b6184-192">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b6184-192">Examples</span></span>  
  
### <a name="a-moving-the-tempdb-database"></a><span data-ttu-id="b6184-193">A.</span><span class="sxs-lookup"><span data-stu-id="b6184-193">A.</span></span> <span data-ttu-id="b6184-194">Verschieben der tempdb-Datenbank</span><span class="sxs-lookup"><span data-stu-id="b6184-194">Moving the tempdb database</span></span>  
 <span data-ttu-id="b6184-195">Im folgenden Beispiel werden die `tempdb` -Daten- und Protokolldatei im Rahmen einer geplanten Verschiebung an einen neuen Speicherort verschoben.</span><span class="sxs-lookup"><span data-stu-id="b6184-195">The following example moves the `tempdb` data and log files to a new location as part of a planned relocation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6184-196">Da tempdb jedes Mal neu erstellt wird, wenn die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gestartet wird, müssen die Daten- und Protokolldateien nicht physisch verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b6184-196">Because tempdb is re-created each time the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, you do not have to physically move the data and log files.</span></span> <span data-ttu-id="b6184-197">Die Dateien werden am neuen Speicherort erstellt, sobald der Dienst in Schritt 3 neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b6184-197">The files are created in the new location when the service is restarted in step 3.</span></span> <span data-ttu-id="b6184-198">Bis der Dienst neu gestartet wird, verwendet tempdb weiterhin die Daten und die Protokolldateien des vorhandenen Speicherorts.</span><span class="sxs-lookup"><span data-stu-id="b6184-198">Until the service is restarted, tempdb continues to use the data and log files in existing location.</span></span>  
  
1.  <span data-ttu-id="b6184-199">Ermitteln Sie die logischen Dateinamen der `tempdb` -Datenbank und ihren aktuellen Speicherort auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="b6184-199">Determine the logical file names of the `tempdb` database and their current location on the disk.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    GO  
    ```  
  
2.  <span data-ttu-id="b6184-200">Ändern Sie den Speicherort der einzelnen Dateien mithilfe von `ALTER DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="b6184-200">Change the location of each file by using `ALTER DATABASE`.</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = tempdev, FILENAME = 'E:\SQLData\tempdb.mdf');  
    GO  
    ALTER DATABASE tempdb   
    MODIFY FILE (NAME = templog, FILENAME = 'F:\SQLLog\templog.ldf');  
    GO  
    ```  
  
3.  <span data-ttu-id="b6184-201">Beenden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], und starten Sie sie erneut.</span><span class="sxs-lookup"><span data-stu-id="b6184-201">Stop and restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="b6184-202">Überprüfen Sie die Dateiänderung.</span><span class="sxs-lookup"><span data-stu-id="b6184-202">Verify the file change.</span></span>  
  
    ```  
    SELECT name, physical_name AS CurrentLocation, state_desc  
    FROM sys.master_files  
    WHERE database_id = DB_ID(N'tempdb');  
    ```  
  
5.  <span data-ttu-id="b6184-203">Löschen Sie die Dateien `tempdb.mdf` und `templog.ldf` am ursprünglichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b6184-203">Delete the `tempdb.mdf` and `templog.ldf` files from the original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6184-204">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6184-204">See Also</span></span>  
 <span data-ttu-id="b6184-205">[Ressourcendatenbank](resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-205">[Resource Database](resource-database.md) </span></span>  
 <span data-ttu-id="b6184-206">[tempdb-Datenbank](tempdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-206">[tempdb Database](tempdb-database.md) </span></span>  
 <span data-ttu-id="b6184-207">[master-Datenbank](master-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-207">[master Database](master-database.md) </span></span>  
 <span data-ttu-id="b6184-208">[msdb-Datenbank](msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-208">[msdb Database](msdb-database.md) </span></span>  
 <span data-ttu-id="b6184-209">[model-Datenbank](model-database.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-209">[model Database](model-database.md) </span></span>  
 <span data-ttu-id="b6184-210">[Verschieben von Benutzerdatenbanken](move-user-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-210">[Move User Databases](move-user-databases.md) </span></span>  
 <span data-ttu-id="b6184-211">[Verschieben von Datenbankdateien](move-database-files.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-211">[Move Database Files](move-database-files.md) </span></span>  
 <span data-ttu-id="b6184-212">[Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="b6184-212">[Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md) </span></span>  
 <span data-ttu-id="b6184-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6184-213">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b6184-214">Neuerstellen von Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="b6184-214">Rebuild System Databases</span></span>](system-databases.md)  
  
  
