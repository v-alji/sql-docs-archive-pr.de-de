---
title: Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699416"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="d6202-102">Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="d6202-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="d6202-103">In diesem Thema wird das Erstellen und Testen einer benutzerdefinierten Klassifizierungsfunktion (User-Defined Function, UDF) erläutert.</span><span class="sxs-lookup"><span data-stu-id="d6202-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="d6202-104">Die Schritte umfassen das Ausführen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="d6202-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="d6202-105">Das in der folgenden Prozedur dargestellte Beispiel veranschaulicht die Möglichkeiten zum Erstellen einer recht komplexen benutzerdefinierten Klassifizierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="d6202-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="d6202-106">In unserem Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d6202-106">In our example:</span></span>  
  
-   <span data-ttu-id="d6202-107">Ein Ressourcenpool (pProductionProcessing) und eine Arbeitsauslastungsgruppe (gProductionProcessing) werden zur Produktionsverarbeitung während eines angegebenen Zeitbereichs erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6202-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="d6202-108">Ein Ressourcenpool (pOffHoursProcessing) und eine Arbeitsauslastungsgruppe (gOffHoursProcessing) werden für das Verwalten von Verbindungen erstellt, die die Anforderungen für die Produktionsverarbeitung nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d6202-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="d6202-109">In der Masterdatenbank wird eine Tabelle (TblClassificationTimeTable) erstellt, in der die Start- und Endzeiten gespeichert werden, die bezüglich eines Anmeldungszeitraums ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="d6202-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="d6202-110">Diese Tabelle muss in der Masterdatenbank erstellt werden, da die Ressourcenkontrolle die Schemabindung für Klassifizierungsfunktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6202-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d6202-111">Als Vorgehensweise wird empfohlen, in der Masterdatenbank keine großen, häufig aktualisierten Tabellen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d6202-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="d6202-112">Die Klassifizierungsfunktion verlängert die Anmeldezeit.</span><span class="sxs-lookup"><span data-stu-id="d6202-112">The classifier function extends the login time.</span></span> <span data-ttu-id="d6202-113">Eine übermäßig komplexe Funktion kann zu einem Timeout bei Anmeldungen oder zur Verlangsamung schneller Verbindungen führen.</span><span class="sxs-lookup"><span data-stu-id="d6202-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="d6202-114">So erstellen Sie die benutzerdefinierte Klassifizierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="d6202-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="d6202-115">Erstellen und konfigurieren Sie die neuen Ressourcenpools und Arbeitsauslastungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="d6202-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="d6202-116">Weisen Sie jeder Arbeitsauslastungsgruppe den entsprechenden Ressourcenpool zu.</span><span class="sxs-lookup"><span data-stu-id="d6202-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="d6202-117">Aktualisieren Sie die Konfiguration im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="d6202-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="d6202-118">Erstellen Sie eine Tabelle, und definieren Sie die Start- und Endzeiten für den Zeitbereich der Produktionsverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="d6202-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="d6202-119">Erstellen Sie die Klassifizierungsfunktion, die Zeitfunktionen und -werte verwendet, die bezüglich der Zeiten in der Suchtabelle ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="d6202-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="d6202-120">Informationen zum Verwenden von Nachschlagetabellen in einer Klassifizierungsfunktion finden Sie in diesem Artikel unter „Best Practices für die Verwendung von Nachschlagetabellen in Klassifizierungsfunktionen“.</span><span class="sxs-lookup"><span data-stu-id="d6202-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="d6202-121">wurde ein erweiterter Satz von Datums- und Uhrzeitdatentypen und zugehörigen Funktionen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d6202-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="d6202-122">Weitere Informationen finden Sie unter [Datums- und Uhrzeitdatentypen und zugehörige Funktionen &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6202-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="d6202-123">Registrieren Sie die Klassifizierungsfunktion, und aktualisieren Sie die Konfiguration im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="d6202-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="d6202-124">So überprüfen Sie die Ressourcenpools, die Arbeitsauslastungsgruppen und die benutzerdefinierte Klassifizierungsfunktion</span><span class="sxs-lookup"><span data-stu-id="d6202-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="d6202-125">Ermitteln Sie die Konfiguration von Ressourcenpools und Arbeitsauslastungsgruppen mit der folgenden Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d6202-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="d6202-126">Stellen Sie unter Verwendung der folgenden Abfragen sicher, dass die Klassifizierungsfunktion vorhanden und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d6202-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="d6202-127">Rufen Sie mit der folgenden Abfrage die aktuellen Laufzeitdaten für die Ressourcenpools und Arbeitsauslastungsgruppen ab.</span><span class="sxs-lookup"><span data-stu-id="d6202-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="d6202-128">Ermitteln Sie mit der folgenden Abfrage, welche Sitzungen in jeder Gruppe vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d6202-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="d6202-129">Ermitteln Sie mit der folgenden Abfrage, welche Anforderungen in jeder Gruppe vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d6202-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="d6202-130">Ermitteln Sie mit der folgenden Abfrage, welche Anforderungen in der Klassifizierung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6202-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="d6202-131">Best Practices für die Verwendung von Nachschlagetabellen in Klassifizierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="d6202-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="d6202-132">Verwenden Sie Nachschlagetabellen nur, wenn es unbedingt notwendig ist.</span><span class="sxs-lookup"><span data-stu-id="d6202-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="d6202-133">Wenn Sie eine Nachschlagetabelle verwenden müssen, kann diese in die Funktion selbst hartcodiert werden. Dies muss jedoch unter Berücksichtigung der Komplexität und der dynamischen Änderungen der Klassifizierungsfunktion geschehen.</span><span class="sxs-lookup"><span data-stu-id="d6202-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="d6202-134">Begrenzen Sie die E/A, die für Nachschlagetabellen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6202-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="d6202-135">Verwenden Sie TOP 1, um nur eine Zeile zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6202-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="d6202-136">Minimieren Sie die Anzahl der Zeilen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d6202-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="d6202-137">Stellen Sie sicher, dass alle Zeilen der Tabelle auf einer einzigen oder einer kleinen Anzahl von Seiten vorliegen.</span><span class="sxs-lookup"><span data-stu-id="d6202-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="d6202-138">Stellen Sie sicher, dass Zeilen, die mithilfe von Index Seek-Vorgängen gefunden werden, so viele Suchspalten wie möglich verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6202-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="d6202-139">Denormalisieren Sie auf eine einzige Tabelle, wenn Sie die Verwendung mehrerer Tabellen mit Joins erwägen.</span><span class="sxs-lookup"><span data-stu-id="d6202-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="d6202-140">Verhindern Sie ein Blockieren der Nachschlagetabelle.</span><span class="sxs-lookup"><span data-stu-id="d6202-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="d6202-141">Verwenden Sie den Hinweis `NOLOCK` , um Blockierungen zu verhindern, oder verwenden Sie in der Funktion die Option `SET LOCK_TIMEOUT` mit einem Maximalwert von 1000 Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="d6202-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="d6202-142">Die Tabelle(n) muss bzw. müssen in der Masterdatenbank vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d6202-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="d6202-143">(Die Masterdatenbank ist die einzige Datenbank, die mit Sicherheit wiederhergestellt wird, wenn die Clientcomputer versuchen, eine Verbindung herzustellen.)</span><span class="sxs-lookup"><span data-stu-id="d6202-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="d6202-144">Der Tabellenname muss mit dem Schema stets vollqualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d6202-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="d6202-145">Da es sich um die Masterdatenbank handeln muss, ist kein Datenbankname erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6202-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="d6202-146">Keine Trigger für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d6202-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="d6202-147">Wenn Sie die Tabelleninhalte aktualisieren, stellen Sie sicher, dass eine Momentaufnahme-Isolationsstufentransaktion verwendet wird, um das Blockieren von Lesern (Readers) durch einen Schreiber (Writer) zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d6202-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="d6202-148">Beachten Sie, dass die Verwendung des Hinweises `NOLOCK` dies ebenfalls verhindern kann.</span><span class="sxs-lookup"><span data-stu-id="d6202-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="d6202-149">Deaktivieren Sie beim Ändern der Tabelleninhalte die Klassifizierungsfunktion, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="d6202-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="d6202-150">Es wird dringend empfohlen, diese Best Practices zu befolgen.</span><span class="sxs-lookup"><span data-stu-id="d6202-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="d6202-151">Wenn Sie die Best Practices aufgrund von Problemen nicht befolgen können, wenden Sie sich an den Microsoft Support, um zukünftigen Problemen vorzubeugen.</span><span class="sxs-lookup"><span data-stu-id="d6202-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6202-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6202-152">See Also</span></span>  
 <span data-ttu-id="d6202-153">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="d6202-154">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="d6202-155">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="d6202-156">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="d6202-157">[Konfigurieren der Ressourcenkontrolle mit einer Vorlage](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="d6202-158">[Anzeigen der Eigenschaften der Ressourcenkontrolle](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="d6202-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="d6202-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6202-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="d6202-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6202-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="d6202-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6202-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="d6202-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6202-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="d6202-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6202-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
