---
title: Verkleinern einer Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.shrinkfile.f1
helpviewer_keywords:
- shrinking files
- decreasing file size
- databases [SQL Server], shrinking
- reducing file size
- size [SQL Server], files
- file size [SQL Server]
ms.assetid: ce5c8798-c039-4ab2-81e7-90a8d688b893
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac69e4bd2db3ef7fe0815d235dd1de7d3396b302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695689"
---
# <a name="shrink-a-file"></a><span data-ttu-id="6a80e-102">Verkleinern einer Datei</span><span class="sxs-lookup"><span data-stu-id="6a80e-102">Shrink a File</span></span>
  <span data-ttu-id="6a80e-103">In diesem Thema wird beschrieben, wie eine Daten- oder Protokolldatei in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="6a80e-103">This topic describes how to shrink a data or log file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="6a80e-104">Mit dem Verkleinern von Datendateien wird Platz gewonnen, indem Datenseiten vom Ende der Datei an nicht belegten Platz weiter am Dateianfang verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-104">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="6a80e-105">Wurde am Ende der Datei ausreichend Platz geschaffen, kann die Zuordnung der Datenseiten am Ende der Datei aufgehoben und die Datenseiten können ins Dateisystem zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-105">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
 <span data-ttu-id="6a80e-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="6a80e-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6a80e-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="6a80e-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6a80e-108">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6a80e-109">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="6a80e-110">Security</span><span class="sxs-lookup"><span data-stu-id="6a80e-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="6a80e-111">**So verkleinern Sie eine Daten- oder Protokolldatei mit:**</span><span class="sxs-lookup"><span data-stu-id="6a80e-111">**To shrink a data or log file, using:**</span></span>  
  
     [<span data-ttu-id="6a80e-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6a80e-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6a80e-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6a80e-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6a80e-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6a80e-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6a80e-116">Die primäre Datendatei kann nicht kleiner als die Größe der primären Datei in der model-Datenbank werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-116">The primary data file cannot be made smaller than the size of the primary file in the model database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="6a80e-117">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-117">Recommendations</span></span>  
  
-   <span data-ttu-id="6a80e-118">Die zum Verkleinern einer Datei verschobenen Daten können an beliebigen freien Platz in der Datei verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-118">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="6a80e-119">Dies führt zur Indexfragmentierung und kann die Leistung von Abfragen, die einen Bereich des Indexes suchen, verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="6a80e-119">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="6a80e-120">Zur Vermeidung von Fragmentierung sollten die Dateiindizes nach der Verkleinerung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-120">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6a80e-121">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6a80e-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6a80e-122">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6a80e-122">Permissions</span></span>  
 <span data-ttu-id="6a80e-123">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** oder der festen Datenbankrolle **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="6a80e-123">Requires membership in the **sysadmin** fixed server role or the **db_owner** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6a80e-124">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6a80e-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="6a80e-125">So verkleinern Sie eine Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="6a80e-125">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="6a80e-126">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="6a80e-126">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="6a80e-127">Erweitern Sie **Datenbanken** , und klicken Sie dann mit der rechten Maustaste auf die Datenbank, die Sie verkleinern möchten.</span><span class="sxs-lookup"><span data-stu-id="6a80e-127">Expand **Databases** and then right-click the database that you want to shrink.</span></span>  
  
3.  <span data-ttu-id="6a80e-128">Zeigen Sie auf **Tasks**, zeigen Sie auf **Verkleinern**, und klicken Sie dann auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="6a80e-128">Point to **Tasks**, point to **Shrink**, and then click **Files**.</span></span>  
  
     <span data-ttu-id="6a80e-129">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="6a80e-129">**Database**</span></span>  
     <span data-ttu-id="6a80e-130">Zeigt den Namen der ausgewählten Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="6a80e-130">Displays the name of the selected database.</span></span>  
  
     <span data-ttu-id="6a80e-131">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="6a80e-131">**File type**</span></span>  
     <span data-ttu-id="6a80e-132">Wählen Sie den Dateityp für die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="6a80e-132">Select the file type for the file.</span></span> <span data-ttu-id="6a80e-133">Die verfügbaren Auswahlmöglichkeiten für den Dateityp sind **Daten** und **Protokoll** .</span><span class="sxs-lookup"><span data-stu-id="6a80e-133">The available choices are **Data** and **Log** files.</span></span> <span data-ttu-id="6a80e-134">Die Standardauswahl ist **Daten**.</span><span class="sxs-lookup"><span data-stu-id="6a80e-134">The default selection is **Data**.</span></span> <span data-ttu-id="6a80e-135">Bei der Auswahl eines anderen Dateigruppentyps wird die Auswahl in den anderen Feldern entsprechend geändert.</span><span class="sxs-lookup"><span data-stu-id="6a80e-135">Selecting a different filegroup type changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="6a80e-136">**Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="6a80e-136">**Filegroup**</span></span>  
     <span data-ttu-id="6a80e-137">Wählen Sie eine Dateigruppe aus der Liste der Dateigruppen aus, die dem oben genannten **Dateityp** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6a80e-137">Select a filegroup from the list of Filegroups associated with the selected **File type** above.</span></span> <span data-ttu-id="6a80e-138">Bei der Auswahl einer anderen Dateigruppe wird die Auswahl in den anderen Feldern entsprechend geändert.</span><span class="sxs-lookup"><span data-stu-id="6a80e-138">Selecting a different filegroup changes the selections in the other fields accordingly.</span></span>  
  
     <span data-ttu-id="6a80e-139">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="6a80e-139">**File name**</span></span>  
     <span data-ttu-id="6a80e-140">Wählen Sie eine Datei aus der Liste der verfügbaren Dateien aus, die der ausgewählten Dateigruppe und dem Dateityp entspricht.</span><span class="sxs-lookup"><span data-stu-id="6a80e-140">Select a file from the list of available files of the selected filegroup and file type.</span></span>  
  
     <span data-ttu-id="6a80e-141">**Location**</span><span class="sxs-lookup"><span data-stu-id="6a80e-141">**Location**</span></span>  
     <span data-ttu-id="6a80e-142">Zeigt den vollständigen Pfad zur aktuell ausgewählten Datei an.</span><span class="sxs-lookup"><span data-stu-id="6a80e-142">Displays the full path to the currently selected file.</span></span> <span data-ttu-id="6a80e-143">Dieser Pfad kann nicht bearbeitet, aber in die Zwischenablage kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-143">The path is not editable, but it can be copied to the clipboard.</span></span>  
  
     <span data-ttu-id="6a80e-144">**Aktuell zugeordneter Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="6a80e-144">**Currently allocated space**</span></span>  
     <span data-ttu-id="6a80e-145">Zeigt bei Datendateien den aktuell zugeordneten Speicherplatz an.</span><span class="sxs-lookup"><span data-stu-id="6a80e-145">For data files, displays the current allocated space.</span></span> <span data-ttu-id="6a80e-146">Bei Protokolldateien wird der aktuell zugeordnete Speicherplatz angezeigt, der auf der Basis der Ausgabe von DBCC SQLPERF (LOGSPACE) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="6a80e-146">For log files, displays the current allocated space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="6a80e-147">**Verfügbarer freier Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="6a80e-147">**Available free space**</span></span>  
     <span data-ttu-id="6a80e-148">Zeigt bei Datendateien den aktuell verfügbaren freien Speicherplatz an, der auf der Basis der Ausgabe von DBCC SHOWFILESTATS (fileid) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="6a80e-148">For data files, displays the current available free space computed from the output of DBCC SHOWFILESTATS(fileid).</span></span> <span data-ttu-id="6a80e-149">Bei Protokolldateien wird der aktuell verfügbare freie Speicherplatz angezeigt, der auf der Basis der Ausgabe von DBCC SQLPERF (LOGSPACE) berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="6a80e-149">For log files, displays the current available free space computed from the output of DBCC SQLPERF(LOGSPACE).</span></span>  
  
     <span data-ttu-id="6a80e-150">**Nicht verwendeten Speicherplatz freigeben**</span><span class="sxs-lookup"><span data-stu-id="6a80e-150">**Release unused space**</span></span>  
     <span data-ttu-id="6a80e-151">Bewirkt, dass ungenutzter Speicherplatz in den Dateien an das Betriebssystem freigegeben und die Datei auf die zuletzt zugeordnete Größe verkleinert wird, wodurch die Dateigröße ohne Verschieben von Daten reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="6a80e-151">Cause any unused space in the files to be released to the operating system and shrink the file to the last allocated extent, reducing the file size without moving any data.</span></span> <span data-ttu-id="6a80e-152">Es wird nicht versucht, verfügbaren Seiten Zeilen erneut zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6a80e-152">No attempt is made to relocate rows to unallocated pages.</span></span>  
  
     <span data-ttu-id="6a80e-153">**Seiten vor dem Freigeben von nicht verwendetem Speicherplatz neu organisieren**</span><span class="sxs-lookup"><span data-stu-id="6a80e-153">**Reorganize pages before releasing unused space**</span></span>  
     <span data-ttu-id="6a80e-154">Entspricht dem Ausführen von DBCC SHRINKFILE zur Angabe der Zieldateigröße.</span><span class="sxs-lookup"><span data-stu-id="6a80e-154">Equivalent to executing DBCC SHRINKFILE specifying the target file size.</span></span> <span data-ttu-id="6a80e-155">Wenn diese Option ausgewählt ist, muss der Benutzer eine Zieldateigröße im Feld **Datei verkleinern auf** angeben.</span><span class="sxs-lookup"><span data-stu-id="6a80e-155">When this option is selected, the user must specify a target file size in the **Shrink file to** box.</span></span>  
  
     <span data-ttu-id="6a80e-156">**Datei verkleinern auf**</span><span class="sxs-lookup"><span data-stu-id="6a80e-156">**Shrink file to**</span></span>  
     <span data-ttu-id="6a80e-157">Gibt die Zieldateigröße für den Verkleinerungsvorgang an.</span><span class="sxs-lookup"><span data-stu-id="6a80e-157">Specifies the target file size for the shrink operation.</span></span> <span data-ttu-id="6a80e-158">Die Größe kann nicht kleiner als der aktuell zugeordnete Speicherplatz und nicht größer als die Summe der Blöcke sein, die der Datei zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6a80e-158">The size cannot be less than the current allocated space or more than the total extents allocated to the file.</span></span> <span data-ttu-id="6a80e-159">Wenn ein Wert außerhalb der Grenzen eingegeben wird, wird der entsprechend nähere Grenzwert wiederhergestellt, sobald der Fokus geändert oder auf eine der Schaltflächen auf der Symbolleiste geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="6a80e-159">Entering a value beyond the minimum or the maximum will revert to the min or the max once the focus is changed or when any of the buttons on the toolbar are clicked.</span></span>  
  
     <span data-ttu-id="6a80e-160">**Datei durch Migrieren ihrer Daten zu anderen Dateien in der gleichen Dateigruppe leeren**</span><span class="sxs-lookup"><span data-stu-id="6a80e-160">**Empty file by migrating the data to other files in the same filegroup**</span></span>  
     <span data-ttu-id="6a80e-161">Migriert alle Daten aus der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="6a80e-161">Migrate all data from the specified file.</span></span> <span data-ttu-id="6a80e-162">Diese Option ermöglicht das Löschen der Datei mit der ALTER DATABASE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6a80e-162">This option allows the file to be dropped using the ALTER DATABASE statement.</span></span> <span data-ttu-id="6a80e-163">Sie entspricht dem Ausführen von DBCC SHRINKFILE mit der Option EMPTYFILE.</span><span class="sxs-lookup"><span data-stu-id="6a80e-163">This option is equivalent to executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
4.  <span data-ttu-id="6a80e-164">Wählen Sie den Dateityp und den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="6a80e-164">Select the file type and file name.</span></span>  
  
5.  <span data-ttu-id="6a80e-165">Aktivieren Sie optional das Kontrollkästchen **Nicht verwendeten Speicherplatz freigeben** .</span><span class="sxs-lookup"><span data-stu-id="6a80e-165">Optionally, select the **Release unused space** check box.</span></span>  
  
     <span data-ttu-id="6a80e-166">Wenn diese Option ausgewählt wird, wird ungenutzter Speicherplatz in der Datei für das Betriebssystem freigegeben und die Datei auf den zuletzt zugeordneten Block verkleinert.</span><span class="sxs-lookup"><span data-stu-id="6a80e-166">Selecting this option causes any unused space in the file to be released to the operating system and shrinks the file to the last allocated extent.</span></span> <span data-ttu-id="6a80e-167">Durch diesen Vorgang wird die Dateigröße ohne Verschieben von Daten reduziert.</span><span class="sxs-lookup"><span data-stu-id="6a80e-167">This reduces the file size without moving any data.</span></span>  
  
6.  <span data-ttu-id="6a80e-168">Aktivieren Sie optional das Kontrollkästchen **Dateien vor dem Freigeben von nicht belegtem Speicherplatz neu organisieren** .</span><span class="sxs-lookup"><span data-stu-id="6a80e-168">Optionally, select the **Reorganize files before releasing unused space** check box.</span></span> <span data-ttu-id="6a80e-169">Wenn dieses Kontrollkästchen aktiviert ist, muss der Wert **Datei verkleinern auf** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-169">If this is selected, the **Shrink file to** value must be specified.</span></span> <span data-ttu-id="6a80e-170">Standardmäßig ist diese Option deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a80e-170">By default, the option is cleared.</span></span>  
  
     <span data-ttu-id="6a80e-171">Wenn diese Option ausgewählt wird, wird ungenutzter Speicherplatz in der Datei für das Betriebssystem freigegeben, und es wird versucht, Zeilen in nicht zugeordnete Seiten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="6a80e-171">Selecting this option causes any unused space in the file to be released to the operating system and tries to relocate rows to unallocated pages.</span></span>  
  
7.  <span data-ttu-id="6a80e-172">Geben Sie optional den maximalen Prozentsatz an freiem Speicherplatz ein, der in der Datenbankdatei verbleiben soll, nachdem die Datenbank verkleinert wurde.</span><span class="sxs-lookup"><span data-stu-id="6a80e-172">Optionally, enter the maximum percentage of free space to be left in the database file after the database has been shrunk.</span></span> <span data-ttu-id="6a80e-173">Der zulässige Wert liegt zwischen 0 und 99.</span><span class="sxs-lookup"><span data-stu-id="6a80e-173">Permissible values are between 0 and 99.</span></span> <span data-ttu-id="6a80e-174">Diese Option ist nur verfügbar, wenn **Dateien vor dem Freigeben von nicht belegtem Speicherplatz neu organisieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6a80e-174">This option is only available when **Reorganize files before releasing unused space** is enabled.</span></span>  
  
8.  <span data-ttu-id="6a80e-175">Aktivieren Sie optional das Kontrollkästchen **Datei durch Migrieren ihrer Daten zu anderen Dateien in der gleichen Dateigruppe leeren** .</span><span class="sxs-lookup"><span data-stu-id="6a80e-175">Optionally, select the **Empty file by migrating the data to other files in the same filegroup** check box.</span></span>  
  
     <span data-ttu-id="6a80e-176">Wenn Sie diese Option aktivieren, werden alle Daten aus der angegebenen Datei in andere Dateien in der Dateigruppe verschoben.</span><span class="sxs-lookup"><span data-stu-id="6a80e-176">Selecting this option moves all data from the specified file to other files in the filegroup.</span></span> <span data-ttu-id="6a80e-177">Die leere Datei kann anschließend gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="6a80e-177">The empty file can then be deleted.</span></span> <span data-ttu-id="6a80e-178">Diese Option entspricht dem Ausführen von DBCC SHRINKFILE mit der EMPTYFILE-Option.</span><span class="sxs-lookup"><span data-stu-id="6a80e-178">This option is the same as executing DBCC SHRINKFILE with the EMPTYFILE option.</span></span>  
  
9. <span data-ttu-id="6a80e-179">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a80e-179">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6a80e-180">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6a80e-180">Using Transact-SQL</span></span>  
  
#### <a name="to-shrink-a-data-or-log-file"></a><span data-ttu-id="6a80e-181">So verkleinern Sie eine Daten- oder Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="6a80e-181">To shrink a data or log file</span></span>  
  
1.  <span data-ttu-id="6a80e-182">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6a80e-182">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="6a80e-183">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="6a80e-183">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="6a80e-184">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6a80e-184">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="6a80e-185">In diesem Beispiel wird [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) verwendet, um die Größe einer Datendatei mit dem Namen `DataFile1` in der Datenbank `UserDB` auf 7 MB zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="6a80e-185">This example uses [DBCC SHRINKFILE](/sql/t-sql/database-console-commands/dbcc-shrinkfile-transact-sql) to shrink the size of a data file named `DataFile1` in the `UserDB` database to 7 MB.</span></span>  
  
 [!code-sql[DBCC#DBCC_SHRINKFILE1](../../snippets/tsql/SQL14/tsql/dbcc/transact-sql/dbcc_other.sql#dbcc_shrinkfile1)]  
  
## <a name="see-also"></a><span data-ttu-id="6a80e-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a80e-186">See Also</span></span>  
 <span data-ttu-id="6a80e-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a80e-187">[DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql) </span></span>  
 <span data-ttu-id="6a80e-188">[Verkleinern einer Datenbank](shrink-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a80e-188">[Shrink a Database](shrink-a-database.md) </span></span>  
 <span data-ttu-id="6a80e-189">[Löschen von Daten- oder Protokolldateien aus einer Datenbank](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a80e-189">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 <span data-ttu-id="6a80e-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a80e-190">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 [<span data-ttu-id="6a80e-191">sys.database_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a80e-191">sys.database_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql)  
  
  
