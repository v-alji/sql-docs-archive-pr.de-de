---
title: Replication System Stored Procedures Concepts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- stored procedures [SQL Server replication], programming
- programming [SQL Server replication], system stored procedures
- programming interfaces [SQL Server replication]
- system stored procedures [SQL Server replication]
- replication [SQL Server], how-to topics
ms.assetid: 816d2bda-ed72-43ec-aa4d-7ee3dc25fd8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 50536e5b6816c84dff26c9c9f99c46d02272b7de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725533"
---
# <a name="replication-system-stored-procedures-concepts"></a><span data-ttu-id="43a21-102">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="43a21-102">Replication System Stored Procedures Concepts</span></span>
  <span data-ttu-id="43a21-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ermöglichen gespeicherte Systemprozeduren den programmgesteuerten Zugriff auf alle vom Benutzer konfigurierbaren Funktionen in einer Replikationstopologie.</span><span class="sxs-lookup"><span data-stu-id="43a21-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], programmatic access to all of the user-configurable functionality in a replication topology is provided by system stored procedures.</span></span> <span data-ttu-id="43a21-104">Gespeicherte Prozeduren können einzeln mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder dem sqlcmd-Befehlszeilenhilfsprogramm ausgeführt werden. Es ist jedoch nützlich, [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Skriptdateien zu schreiben, mit denen eine logische Sequenz von Replikationstasks ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="43a21-104">While stored procedures may be executed individually using the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the sqlcmd command-line utility, it may be beneficial to write [!INCLUDE[tsql](../../../includes/tsql-md.md)] script files that can be executed to perform a logical sequence of replication tasks.</span></span>  
  
 <span data-ttu-id="43a21-105">Skriptreplikationstasks bieten die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="43a21-105">Scripting replication tasks provides the following benefits:</span></span>  
  
-   <span data-ttu-id="43a21-106">Sie behalten eine dauerhafte Kopie der Schritte bei, die zum Bereitstellen der Replikationstopologie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-106">Keeps a permanent copy of the steps used to deploy your replication topology.</span></span>  
  
-   <span data-ttu-id="43a21-107">Sie verwenden ein einzelnes Skript, um mehrere Abonnenten zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="43a21-107">Uses a single script to configure multiple Subscribers.</span></span>  
  
-   <span data-ttu-id="43a21-108">Sie bieten neuen Datenbankadministratoren eine schnelle Einführung, da Skripts die Möglichkeiten zur Verfügung stellen, den Code auszuwerten, zu verstehen, zu ändern oder Probleme im Code zu finden und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="43a21-108">Quickly educates new database administrators by enabling them to evaluate, understand, change, or troubleshoot the code.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="43a21-109">Skripts können Quellen für Sicherheitsbeeinträchtigungen sein. Sie können Systemfunktionen ohne Wissen oder Eingriff des Benutzers aufrufen und Sicherheitsanmeldeinformationen im Nur-Text-Format enthalten.</span><span class="sxs-lookup"><span data-stu-id="43a21-109">Scripts can be the source of security vulnerabilities; they can invoke system functions without user knowledge or intervention and may contain security credentials in plain text.</span></span> <span data-ttu-id="43a21-110">Überprüfen Sie Skripts auf Sicherheitsprobleme, bevor Sie sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="43a21-110">Review scripts for security issues before you use them.</span></span>  
  
## <a name="creating-replication-scripts"></a><span data-ttu-id="43a21-111">Erstellen von Replikationsskripts</span><span class="sxs-lookup"><span data-stu-id="43a21-111">Creating Replication Scripts</span></span>  
 <span data-ttu-id="43a21-112">Aus der Sicht der Replikation besteht ein Skript aus einer oder mehreren [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen, wobei jede Anweisung eine gespeicherte Replikationsprozedur ausführt.</span><span class="sxs-lookup"><span data-stu-id="43a21-112">From the standpoint of replication, a script is a series of one or more [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements where each statement executes a replication stored procedure.</span></span> <span data-ttu-id="43a21-113">Skripts sind Textdateien, die meist die Dateierweiterung SQL aufweisen und mit dem sqlcmd-Hilfsprogramm ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="43a21-113">Scripts are text files, often with a .sql file extension, that can be run using the sqlcmd utility.</span></span> <span data-ttu-id="43a21-114">Beim Ausführen einer Skriptdatei führt das Hilfsprogramm die in der Datei gespeicherten SQL-Anweisungen aus.</span><span class="sxs-lookup"><span data-stu-id="43a21-114">When a script file is run, the utility executes the SQL statements stored in the file.</span></span> <span data-ttu-id="43a21-115">Entsprechend kann ein Skript als Abfrageobjekt in einem [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Projekt gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-115">Similarly, a script can be stored as a query object in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span>  
  
 <span data-ttu-id="43a21-116">Replikationsskripts können wie folgt erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="43a21-116">Replication scripts can be created in the following ways:</span></span>  
  
-   <span data-ttu-id="43a21-117">Erstellen Sie das Skript manuell.</span><span class="sxs-lookup"><span data-stu-id="43a21-117">Manually create the script.</span></span>  
  
-   <span data-ttu-id="43a21-118">Verwenden Sie die Skriptgenerierungsfunktionen, die in den Replikations-Assistenten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-118">Use the script generation features that are provided in the replication wizards or</span></span>  
  
-   <span data-ttu-id="43a21-119">[https://login.microsoftonline.com/consumers/]([!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="43a21-119">[!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="43a21-120">Weitere Informationen finden Sie unter [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="43a21-120">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
-   <span data-ttu-id="43a21-121">Verwenden Sie Replikationsverwaltungsobjekte (RMO), um das Skript programmgesteuert zu generieren und ein RMO-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43a21-121">Use Replication Management Objects (RMOs) to programmatically generate the script to create an RMO object.</span></span>  
  
 <span data-ttu-id="43a21-122">Beachten Sie bei der manuellen Erstellung von Replikationsskripts die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="43a21-122">When you manually create replication scripts, keep the following considerations in mind:</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)]<span data-ttu-id="43a21-123">-Skripts enthalten mindestens einen Batch.</span><span class="sxs-lookup"><span data-stu-id="43a21-123">scripts have one or more batches.</span></span> <span data-ttu-id="43a21-124">Der GO-Befehl signalisiert das Ende eines Batches.</span><span class="sxs-lookup"><span data-stu-id="43a21-124">The GO command signals the end of a batch.</span></span> <span data-ttu-id="43a21-125">Wenn ein [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Skript keine GO-Befehle enthält, wird es als einzelner Batch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43a21-125">If a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script does not have any GO commands, it is executed as a single batch.</span></span>  
  
-   <span data-ttu-id="43a21-126">Beim Ausführen mehrerer gespeicherter Replikationsprozeduren in einem einzelnen Batch muss nach der ersten Prozedur allen folgenden Prozeduren das EXECUTE-Schlüsselwort vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-126">When executing multiple replication stored procedures in a single batch, after the first procedure, all subsequent procedures in the batch must be preceded by the EXECUTE keyword.</span></span>  
  
-   <span data-ttu-id="43a21-127">Alle gespeicherten Prozeduren in einem Batch müssen kompiliert werden, bevor ein Batch ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43a21-127">All stored procedures in a batch must compile before a batch will execute.</span></span> <span data-ttu-id="43a21-128">Nachdem der Batch kompiliert und ein Ausführungsplan erstellt wurde, kann ggf. jedoch ein Laufzeitfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="43a21-128">However, once the batch has been compiled, and an execution plan has been created, a run-time error may or may not occur.</span></span>  
  
-   <span data-ttu-id="43a21-129">Beim Erstellen von Skripts zur Konfiguration der Replikation sollten Sie die Windows-Authentifizierung verwenden, um zu vermeiden, dass Sicherheitsanmeldeinformationen in der Skriptdatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-129">When creating scripts to configure replication, you should use Windows Authentication to avoid storing security credentials in the script file.</span></span> <span data-ttu-id="43a21-130">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, muss die Datei an einem sicheren Ort gespeichert werden, um unberechtigten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="43a21-130">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
## <a name="sample-replication-script"></a><span data-ttu-id="43a21-131">Beispiel für ein Replikationsskript</span><span class="sxs-lookup"><span data-stu-id="43a21-131">Sample Replication Script</span></span>  
 <span data-ttu-id="43a21-132">Das folgende Skript kann zum Einrichten der Veröffentlichung und Verteilung auf einem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-132">The following script can be executed to setup publishing and distribution on a server.</span></span>  
  
```  
-- This script uses sqlcmd scripting variables. They are in the form  
-- $(MyVariable). For information about how to use scripting variables    
-- on the command line and in SQL Server Management Studio, see the   
-- "Executing Replication Scripts" section in the topic  
-- "Programming Replication Using System Stored Procedures".  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
-- Specify the replication working directory.  
SET @directory = N'\\' + $(DistPubServer) + '\repldata';  
-- Specify the publication database.  
SET @publicationDB = N'AdventureWorks2012';   
  
-- Install the server MYDISTPUB as a Distributor using the defaults,  
-- including autogenerating the distributor password.  
USE master  
EXEC sp_adddistributor @distributor = @distributor;  
  
-- Create a new distribution database using the defaults, including  
-- using Windows Authentication.  
USE master  
EXEC sp_adddistributiondb @database = @distributionDB,   
    @security_mode = 1;  
GO  
  
-- Create a Publisher and enable AdventureWorks2012 for replication.  
-- Add MYDISTPUB as a publisher with MYDISTPUB as a local distributor  
-- and use Windows Authentication.  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
USE [distribution]  
EXEC sp_adddistpublisher @publisher=@publisher,   
    @distribution_db=@distributionDB,   
    @security_mode = 1;  
GO  
  
```  
  
 <span data-ttu-id="43a21-133">Dieses Skript kann dann lokal unter dem Namen `instdistpub.sql` gespeichert werden, sodass es bei Bedarf wiederholt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="43a21-133">This script can then be saved locally as `instdistpub.sql` so that it can be run or rerun when needed.</span></span>  
  
 <span data-ttu-id="43a21-134">Das vorherige Skript umfasst **sqlcmd**-Skriptvariablen, die in vielen Replikationscodebeispielen in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Onlinedokumentation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-134">The previous script includes **sqlcmd** scripting variables, which are used in many of the replication code samples in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="43a21-135">Skriptvariablen werden mit der `$(MyVariable)`-Syntax definiert.</span><span class="sxs-lookup"><span data-stu-id="43a21-135">Scripting variables are defined by using `$(MyVariable)` syntax.</span></span> <span data-ttu-id="43a21-136">Werte für Variablen können in der Befehlszeile oder in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] an ein Skript übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-136">Values for variables can be passed to a script at the command line or in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="43a21-137">Weitere Informationen finden Sie im nächsten Abschnitt dieses Themas, "Ausführen von Replikationsskripts".</span><span class="sxs-lookup"><span data-stu-id="43a21-137">For more information, see the next section in this topic, "Executing Replication Scripts."</span></span>  
  
## <a name="executing-replication-scripts"></a><span data-ttu-id="43a21-138">Ausführen von Replikationsskripts</span><span class="sxs-lookup"><span data-stu-id="43a21-138">Executing Replication Scripts</span></span>  
 <span data-ttu-id="43a21-139">Sobald ein Replikationsskript erstellt wurde, kann es wie folgt ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="43a21-139">Once created, a replication script can be executed in one of the following ways:</span></span>  
  
### <a name="creating-a-sql-query-file-in-sql-server-management-studio"></a><span data-ttu-id="43a21-140">Erstellen einer SQL-Abfragedatei in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43a21-140">Creating a SQL Query File in SQL Server Management Studio</span></span>  
 <span data-ttu-id="43a21-141">Eine [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Replikationsskriptdatei kann als SQL-Abfragedatei in einem [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]-Projekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-141">A replication [!INCLUDE[tsql](../../../includes/tsql-md.md)] script file can be created as a SQL Query file in a [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] project.</span></span> <span data-ttu-id="43a21-142">Nachdem das Skript geschrieben wurde, kann für diese Abfragedatei eine Verbindung mit der Datenbank hergestellt und das Skript ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-142">After the script is written, a connection can be made to the database for this query file and the script can be executed.</span></span> <span data-ttu-id="43a21-143">Weitere Informationen zum Erstellen [!INCLUDE[tsql](../../../includes/tsql-md.md)] von Skripts mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] finden Sie unter [Abfrage-und Text-Editoren &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span><span class="sxs-lookup"><span data-stu-id="43a21-143">For more information about how to create [!INCLUDE[tsql](../../../includes/tsql-md.md)] scripts by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], see [Query and Text Editors &#40;SQL Server Management Studio&#41;](../../scripting/query-and-text-editors-sql-server-management-studio.md)).</span></span>  
  
 <span data-ttu-id="43a21-144">Um ein Skript zu verwenden, das Skriptvariablen enthält, muss [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] im **sqlcmd**-Modus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-144">To use a script that includes scripting variables, [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] must be running in **sqlcmd** mode.</span></span> <span data-ttu-id="43a21-145">Im **sqlcmd**-Modus lässt der Abfrage-Editor zusätzliche **sqlcmd**-spezifische Syntax zu, wie `:setvar` zum Festlegen eines Werts für eine Variable.</span><span class="sxs-lookup"><span data-stu-id="43a21-145">In **sqlcmd** mode, the Query Editor accepts additional syntax specific to **sqlcmd**, such as `:setvar`, which is used to a value for a variable.</span></span> <span data-ttu-id="43a21-146">Weitere Informationen zum **sqlcmd**-Modus finden Sie unter [Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="43a21-146">For more information about **sqlcmd** mode, see [Edit SQLCMD Scripts with Query Editor](../../scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span> <span data-ttu-id="43a21-147">Im folgenden Skript wird `:setvar` verwendet, um einen Wert für die `$(DistPubServer)`-Variable bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="43a21-147">In the following script, `:setvar` is used to provide a value for the `$(DistPubServer)` variable.</span></span>  
  
```  
:setvar DistPubServer N'MyPublisherAndDistributor';  
  
-- Install the Distributor and the distribution database.  
DECLARE @distributor AS sysname;  
DECLARE @distributionDB AS sysname;  
DECLARE @publisher AS sysname;  
DECLARE @directory AS nvarchar(500);  
DECLARE @publicationDB AS sysname;  
-- Specify the Distributor name.  
SET @distributor = $(DistPubServer);  
-- Specify the distribution database.  
SET @distributionDB = N'distribution';  
-- Specify the Publisher name.  
SET @publisher = $(DistPubServer);  
  
--  
-- Additional code goes here  
--  
```  
  
### <a name="using-the-sqlcmd-utility-from-the-command-line"></a><span data-ttu-id="43a21-148">Verwenden des sqlcmd-Hilfsprogramms über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="43a21-148">Using the sqlcmd Utility from the Command Line</span></span>  
 <span data-ttu-id="43a21-149">Das folgende Beispiel veranschaulicht, wie die Befehlszeile zur Ausführung der `instdistpub.sql`-Skriptdatei mit dem [sqlcmd Hilfsprogramm](../../../tools/sqlcmd-utility.md) verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="43a21-149">The following example shows how the command line is used to execute the `instdistpub.sql` script file using the [sqlcmd utility](../../../tools/sqlcmd-utility.md):</span></span>  
  
```  
sqlcmd.exe -E -S sqlserverinstance -i C:\instdistpub.sql -o C:\output.log -v DistPubServer="N'MyDistributorAndPublisher'"  
```  
  
 <span data-ttu-id="43a21-150">In diesem Beispiel gibt der `-E`-Schalter an, dass beim Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Windows-Authentifizierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="43a21-150">In this example, the `-E` switch indicates that Windows Authentication is used when connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="43a21-151">Bei Verwendung der Windows-Authentifizierung entfällt das Speichern des Benutzernamens und Kennworts in der Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="43a21-151">When using Windows Authentication, there is no need to store a username and password in the script file.</span></span> <span data-ttu-id="43a21-152">Der Name und Pfad der Skriptdatei wird mit dem `-i`-Schalter und der Name der Ausgabedatei mit dem `-o`-Schalter angegeben (bei Verwendung dieses Schalters wird die Ausgabe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in diese Datei statt in die Konsole geschrieben).</span><span class="sxs-lookup"><span data-stu-id="43a21-152">The name and path of the script file is specified by the `-i` switch and the name of the output file is specified by the `-o` switch (output from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is written to this file instead of the console when this switch is used).</span></span> <span data-ttu-id="43a21-153">Mit dem `sqlcmd`-Hilfsprogramm können Sie Skriptvariablen mit dem `-v`-Schalter zur Laufzeit an das [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Skript übergeben.</span><span class="sxs-lookup"><span data-stu-id="43a21-153">The `sqlcmd` utility enables you to pass scripting variables to a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script at runtime using the `-v` switch.</span></span> <span data-ttu-id="43a21-154">In diesem Beispiel ersetzt `sqlcmd` vor der Ausführung jede Instanz von `$(DistPubServer)` im Skript durch den `N'MyDistributorAndPublisher'`-Wert.</span><span class="sxs-lookup"><span data-stu-id="43a21-154">In this example, `sqlcmd` replaces every instance of `$(DistPubServer)` in the script with the value `N'MyDistributorAndPublisher'` before execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43a21-155">Der `-X`-Schalter deaktiviert Skriptvariablen.</span><span class="sxs-lookup"><span data-stu-id="43a21-155">The `-X` switch disables scripting variables.</span></span>  
  
### <a name="automating-tasks-in-a-batch-file"></a><span data-ttu-id="43a21-156">Automatisieren von Tasks in einer Batchdatei</span><span class="sxs-lookup"><span data-stu-id="43a21-156">Automating Tasks in a Batch File</span></span>  
 <span data-ttu-id="43a21-157">Mit einer Batchdatei können Replikationsverwaltungstasks, Replikationssynchronisierungstasks und andere Tasks in der gleichen Batchdatei automatisiert werden.</span><span class="sxs-lookup"><span data-stu-id="43a21-157">By using a batch file, replication administration tasks, replication synchronization tasks, and other tasks can be automated in the same batch file.</span></span> <span data-ttu-id="43a21-158">Die folgende Batchdatei verwendet das **sqlcmd**-Hilfsprogramm, um die Abonnementdatenbank zu löschen und neu zu erstellen und ein Mergepullabonnement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="43a21-158">The following batch file uses the **sqlcmd** utility to drop and recreate the subscription database and add a merge pull subscription.</span></span> <span data-ttu-id="43a21-159">Anschließend startet die Datei den Merge-Agent, um das neue Abonnement zu synchronisieren:</span><span class="sxs-lookup"><span data-stu-id="43a21-159">Then the file invokes the merge agent to synchronize the new subscription:</span></span>  
  
```  
REM ----------------------Script to synchronize merge subscription ----------------------  
REM -- Creates subscription database and   
REM -- synchronizes the subscription to MergeSalesPerson.  
REM -- Current computer acts as both Publisher and Subscriber.  
REM -------------------------------------------------------------------------------------  
  
SET Publisher=%computername%  
SET Subscriber=%computername%  
SET PubDb=AdventureWorks  
SET SubDb=AdventureWorksReplica  
SET PubName=AdvWorksSalesOrdersMerge  
  
REM -- Drop and recreate the subscription database at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE master IF EXISTS (SELECT * FROM sysdatabases WHERE name='%SubDb%' ) DROP DATABASE %SubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE master CREATE DATABASE %SubDb%"  
  
REM -- Add a pull subscription at the Subscriber  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb% EXEC sp_addmergepullsubscription @publisher = %Publisher%, @publication = %PubName%, @publisher_db = %PubDb%"  
sqlcmd /S%Subscriber% /E /Q"USE %SubDb%  EXEC sp_addmergepullsubscription_agent @publisher = %Publisher%, @publisher_db = %PubDb%, @publication = %PubName%, @subscriber = %Subscriber%, @subscriber_db = %SubDb%, @distributor = %Publisher%"  
  
REM -- This batch file starts the merge agent at the Subscriber to   
REM -- synchronize a pull subscription to a merge publication.  
REM -- The following must be supplied on one line.  
"\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE"  -Publisher  %Publisher% -Subscriber  %Subscriber%  -Distributor %Publisher%  -PublisherDB  %PubDb% -SubscriberDB %SubDb% -Publication %PubName% -PublisherSecurityMode 1 -OutputVerboseLevel 1  -Output  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1 -Validate 3  
  
```  
  
## <a name="scripting-common-replication-tasks"></a><span data-ttu-id="43a21-160">Skripterstellung für allgemeine Replikationstasks</span><span class="sxs-lookup"><span data-stu-id="43a21-160">Scripting Common Replication Tasks</span></span>  
 <span data-ttu-id="43a21-161">Im Folgenden sind einige der häufigsten Replikationstasks aufgeführt, für die mit gespeicherten Systemprozeduren ein Skript erstellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="43a21-161">The following are some of the most common replication tasks can be scripted using system stored procedures:</span></span>  
  
-   <span data-ttu-id="43a21-162">Konfigurieren der Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="43a21-162">Configuring publishing and distribution</span></span>  
  
-   <span data-ttu-id="43a21-163">Ändern von Verleger- und Verteilereigenschaften</span><span class="sxs-lookup"><span data-stu-id="43a21-163">Modifying Publisher and Distributor properties</span></span>  
  
-   <span data-ttu-id="43a21-164">Deaktivieren von Veröffentlichung und Verteilung</span><span class="sxs-lookup"><span data-stu-id="43a21-164">Disabling publishing and distribution</span></span>  
  
-   <span data-ttu-id="43a21-165">Erstellen von Veröffentlichungen und Definieren von Artikeln</span><span class="sxs-lookup"><span data-stu-id="43a21-165">Creating publications and defining articles</span></span>  
  
-   <span data-ttu-id="43a21-166">Löschen von Veröffentlichungen und Artikeln</span><span class="sxs-lookup"><span data-stu-id="43a21-166">Deleting publications and articles</span></span>  
  
-   <span data-ttu-id="43a21-167">Erstellung eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-167">Creating a pull subscription</span></span>  
  
-   <span data-ttu-id="43a21-168">Ändern eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-168">Modifying a pull subscription</span></span>  
  
-   <span data-ttu-id="43a21-169">Löschen eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-169">Deleting a pull subscription</span></span>  
  
-   <span data-ttu-id="43a21-170">Erstellen eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-170">Creating a push subscription</span></span>  
  
-   <span data-ttu-id="43a21-171">Ändern eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-171">Modifying a push subscription</span></span>  
  
-   <span data-ttu-id="43a21-172">Löschen eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-172">Deleting a push subscription</span></span>  
  
-   <span data-ttu-id="43a21-173">Synchronisieren eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="43a21-173">Synchronizing a pull subscription</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a21-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43a21-174">See Also</span></span>  
 <span data-ttu-id="43a21-175">[Konzepte für die Replikationsprogrammierung](replication-programming-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="43a21-175">[Replication Programming Concepts](replication-programming-concepts.md) </span></span>  
 <span data-ttu-id="43a21-176">[Gespeicherte Replikationsprozeduren &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43a21-176">[Replication Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="43a21-177">Erstellen von Skripts für die Replikation</span><span class="sxs-lookup"><span data-stu-id="43a21-177">Scripting Replication</span></span>](../scripting-replication.md)  
  
  
