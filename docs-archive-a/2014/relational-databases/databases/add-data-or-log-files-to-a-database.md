---
title: Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725918"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="e47c2-102">Hinzufügen von Daten- oder Protokolldateien zu einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e47c2-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="e47c2-103">In diesem Thema wird beschrieben, wie Daten- oder Protokolldateien in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]einer Datenbank hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e47c2-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e47c2-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="e47c2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e47c2-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="e47c2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e47c2-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e47c2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="e47c2-107">Security</span><span class="sxs-lookup"><span data-stu-id="e47c2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e47c2-108">**So fügen Sie einer Datenbank Daten- oder Protokolldateien hinzu mit:**</span><span class="sxs-lookup"><span data-stu-id="e47c2-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="e47c2-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e47c2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e47c2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e47c2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e47c2-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="e47c2-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="e47c2-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e47c2-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="e47c2-113">Sie können keine Dateien hinzufügen oder entfernen, während eine BACKUP-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e47c2-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="e47c2-114">Für jede Datenbank können maximal 32.767 Dateien und 32.767 Dateigruppen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e47c2-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e47c2-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e47c2-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e47c2-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e47c2-116">Permissions</span></span>  
 <span data-ttu-id="e47c2-117">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e47c2-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e47c2-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e47c2-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="e47c2-119">So fügen Sie einer Datenbank Daten- oder Protokolldateien hinzu</span><span class="sxs-lookup"><span data-stu-id="e47c2-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="e47c2-120">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="e47c2-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e47c2-121">Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die Datenbank, der die Dateien hinzugefügt werden sollen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e47c2-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e47c2-122">Wählen Sie im Dialogfeld **Datenbankeigenschaften** die Seite **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="e47c2-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="e47c2-123">Zum Hinzufügen einer Daten- oder Transaktionsprotokolldatei klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e47c2-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="e47c2-124">Geben Sie im Bereich **Datenbankdateien** einen logischen Namen für die Datei ein.</span><span class="sxs-lookup"><span data-stu-id="e47c2-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="e47c2-125">Der Dateiname muss innerhalb der Datenbank eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e47c2-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="e47c2-126">Wählen Sie den Dateityp aus: Daten- oder Protokolldatei.</span><span class="sxs-lookup"><span data-stu-id="e47c2-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="e47c2-127">Wählen Sie für eine Datendatei in der Liste die Dateigruppe aus, in die die Datei eingeschlossen werden soll, oder wählen Sie **\<new filegroup>** aus, um eine neue Dateigruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e47c2-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="e47c2-128">Transaktionsprotokolle können nicht in Dateigruppen platziert werden.</span><span class="sxs-lookup"><span data-stu-id="e47c2-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="e47c2-129">Geben Sie die Anfangsgröße der Datei an.</span><span class="sxs-lookup"><span data-stu-id="e47c2-129">Specify the initial size of the file.</span></span> <span data-ttu-id="e47c2-130">Legen Sie die Datendatei so groß wie möglich aus. Orientieren Sie sich dabei an dem maximal zu erwartenden Umfang der Datei, die in der Datenbank gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e47c2-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="e47c2-131">Klicken Sie auf ( **…** ) in der Spalte **Automatische Vergrößerung**, um anzugeben, wie die Datei wachsen soll.</span><span class="sxs-lookup"><span data-stu-id="e47c2-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="e47c2-132">Sie können zwischen folgenden Optionen wählen:</span><span class="sxs-lookup"><span data-stu-id="e47c2-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="e47c2-133">Um ein Anwachsen der aktuell ausgewählten Datei zuzulassen, wenn mehr Datenspeicherplatz benötigt wird, aktivieren Sie das Kontrollkästchen **Automatische Vergrößerung aktivieren** , und wählen Sie dann eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e47c2-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="e47c2-134">Wählen Sie **In Megabyte** aus, um anzugeben, dass die Datei in festen Schritten größer werden soll, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="e47c2-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="e47c2-135">Wählen Sie **In Prozent** aus, um anzugeben, dass die Datei um einen Prozentsatz der aktuellen Dateigröße größer werden soll, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="e47c2-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="e47c2-136">Um die maximale Dateigröße anzugeben, aktivieren Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="e47c2-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="e47c2-137">Wählen Sie **Beschränkt vergrößerbar (MB)** aus, um die maximale Größe für die Datei anzugeben, und geben Sie einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="e47c2-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="e47c2-138">Um ein Anwachsen der Datei bei Bedarf zuzulassen, wählen Sie **Unbeschränkt vergrößerbar**aus.</span><span class="sxs-lookup"><span data-stu-id="e47c2-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="e47c2-139">Um die Vergrößerung der Datei zu verhindern, deaktivieren Sie das Kontrollkästchen **Automatische Vergrößerung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="e47c2-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="e47c2-140">Die Größe der Datei steigt dann nicht über den in der Spalte **Anfangsgröße (MB)** angegebenen Wert hinaus.</span><span class="sxs-lookup"><span data-stu-id="e47c2-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e47c2-141">Die maximale Dateigröße ergibt sich aus dem verfügbaren Speicherplatz und den von der verwendeten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] festgelegten Lizenzierungslimits.</span><span class="sxs-lookup"><span data-stu-id="e47c2-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="e47c2-142">Geben Sie den Pfad für den Dateispeicherort an.</span><span class="sxs-lookup"><span data-stu-id="e47c2-142">Specify the path for the file location.</span></span> <span data-ttu-id="e47c2-143">Der angegebene Pfad muss vorhanden sein, bevor die Datei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e47c2-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e47c2-144">Standardmäßig werden die Daten und Transaktionsprotokolle auf demselben Laufwerk und unter demselben Pfad gespeichert, um Systeme mit nur einem Datenträger zu berücksichtigen. Diese Variante kann jedoch für bestimmte Produktionsumgebungen nicht optimal sein.</span><span class="sxs-lookup"><span data-stu-id="e47c2-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="e47c2-145">Weitere Informationen finden Sie unter [Datenbankdateien und Dateigruppen](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="e47c2-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="e47c2-146">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e47c2-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e47c2-147">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e47c2-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="e47c2-148">So fügen Sie einer Datenbank Daten- oder Protokolldateien hinzu</span><span class="sxs-lookup"><span data-stu-id="e47c2-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="e47c2-149">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="e47c2-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e47c2-150">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="e47c2-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e47c2-151">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e47c2-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e47c2-152">In diesem Beispiel wird eine Dateigruppe mit zwei Dateien einer Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e47c2-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="e47c2-153">Im Beispiel wird die Dateigruppe `Test1FG1` in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank erstellt, und der Dateigruppe werden zwei 5-MB-Dateien hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e47c2-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="e47c2-154">Weitere Beispiele finden Sie unter [ALTER DATABASE-Optionen Datei und Dateigruppe &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="e47c2-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e47c2-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e47c2-155">See Also</span></span>  
 <span data-ttu-id="e47c2-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="e47c2-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="e47c2-157">[Löschen von Daten- oder Protokolldateien aus einer Datenbank](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="e47c2-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="e47c2-158">Erhöhen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="e47c2-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
