---
title: Anfügen einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.attachdatabase.f1
helpviewer_keywords:
- database attaching [SQL Server]
- attaching databases [SQL Server]
ms.assetid: b4efb0ae-cfe6-4d81-a4b4-6e4916885caa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb11b5c257007872e92d3f0a7eadb3e46b4969cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725913"
---
# <a name="attach-a-database"></a><span data-ttu-id="96e9d-102">Anfügen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="96e9d-102">Attach a Database</span></span>
  <span data-ttu-id="96e9d-103">In diesem Thema wird beschrieben, wie eine Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="96e9d-103">This topic describes how to attach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="96e9d-104">Sie können diese Funktion verwenden, um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank zu kopieren, zu verschieben oder zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="96e9d-104">You can use this feature to copy, move, or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="96e9d-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="96e9d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96e9d-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="96e9d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96e9d-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="96e9d-108">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="96e9d-109">Security</span><span class="sxs-lookup"><span data-stu-id="96e9d-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="96e9d-110">**Anfügen einer Datenbank mit:**</span><span class="sxs-lookup"><span data-stu-id="96e9d-110">**To Attach a Database by using:**</span></span>  
  
     [<span data-ttu-id="96e9d-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96e9d-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="96e9d-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96e9d-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="96e9d-113">Nach **Verfolgung:**[nach dem Aktualisieren einer Datenbank](#FollowUp)  </span><span class="sxs-lookup"><span data-stu-id="96e9d-113">**Follow Up:**  [After Upgrading a Database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96e9d-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="96e9d-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="96e9d-116">Die Datenbank muss zuerst getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-116">The database must first be detached.</span></span> <span data-ttu-id="96e9d-117">Wenn Sie versuchen, eine Datenbank anzufügen, die nicht getrennt wurde, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96e9d-117">Attempting to attach a database that has not been detached will return an error.</span></span> <span data-ttu-id="96e9d-118">Weitere Informationen finden Sie unter [Trennen einer Datenbank](detach-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="96e9d-118">For more information, see [Detach a Database](detach-a-database.md).</span></span>  
  
-   <span data-ttu-id="96e9d-119">Wenn Sie eine Datenbank anfügen, müssen alle Datendateien (MDF- und LDF-Dateien) verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="96e9d-119">When you attach a database, all data files (MDF and LDF files) must be available.</span></span> <span data-ttu-id="96e9d-120">Wenn eine Datendatei einen anderen Pfad als beim Erstellen oder beim letzten Anfügen der Datenbank aufweist, müssen Sie den aktuellen Pfad der Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="96e9d-120">If any data file has a different path from when the database was first created or last attached, you must specify the current path of the file.</span></span>  
  
-   <span data-ttu-id="96e9d-121">Wenn Sie eine Datenbank anfügen, MDF- und LDF-Dateien sich in verschiedenen Verzeichnissen befinden und einer der Pfade „ \\\\?\GlobalRoot“ enthält, schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="96e9d-121">When you attach a database, if MDF and LDF files are located in different directories and one of the paths includes \\\\?\GlobalRoot, the operation will fail.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="96e9d-122">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-122">Recommendations</span></span>  
<span data-ttu-id="96e9d-123">Es wird empfohlen, Datenbanken mit dem geplanten Verschiebungs `ALTER DATABASE` Verfahren zu verschieben, anstatt Trenn-und Anfüge Vorgänge zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-123">We recommend that you move databases by using the `ALTER DATABASE` planned relocation procedure, instead of using detach and attach.</span></span> <span data-ttu-id="96e9d-124">Weitere Informationen finden Sie unter [Move User Databases](move-user-databases.md).</span><span class="sxs-lookup"><span data-stu-id="96e9d-124">For more information, see [Move User Databases](move-user-databases.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96e9d-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96e9d-125">Security</span></span>  
<span data-ttu-id="96e9d-126">Dateizugriffsberechtigungen werden während einer Reihe von Datenbankvorgängen festgelegt, einschließlich des Trennens oder Anfügens einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="96e9d-126">File access permissions are set during a number of database operations, including detaching or attaching a database.</span></span> <span data-ttu-id="96e9d-127">Informationen zu Dateiberechtigungen, die beim Trennen und Anfügen einer Datenbank festgelegt werden, finden Sie unter [Sichern von Daten- und Protokolldateien](https://technet.microsoft.com/library/ms189128.aspx) in der [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="96e9d-127">For information about file permissions that are set whenever a database is detached and attached, see [Securing Data and Log Files](https://technet.microsoft.com/library/ms189128.aspx) in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] Books Online.</span></span>  
  
<span data-ttu-id="96e9d-128">Das Anfügen oder Wiederherstellen von Datenbanken aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-128">We recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="96e9d-129">Solche Datenbanken können bösartigen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code ausführt oder Fehler verursacht, indem er das Schema oder die physische Datenbankstruktur ändert.</span><span class="sxs-lookup"><span data-stu-id="96e9d-129">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="96e9d-130">Bevor Sie eine Datenbank aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, führen Sie auf einem Nichtproduktionsserver [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus. Überprüfen Sie außerdem den Code in der Datenbank, z.B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="96e9d-130">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span> <span data-ttu-id="96e9d-131">Weitere Informationen zum Anfügen von Datenbanken sowie Informationen zu Änderungen, die an Metadaten durchgeführt werden, wenn Sie eine Datenbank anfügen, finden Sie unter [Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="96e9d-131">For more information about attaching databases and information about changes that are made to metadata when you attach a database, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96e9d-132">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="96e9d-132">Permissions</span></span>  
<span data-ttu-id="96e9d-133">Erfordert die Berechtigung `CREATE DATABASE`, `CREATE ANY DATABASE` oder `ALTER ANY DATABASE`.</span><span class="sxs-lookup"><span data-stu-id="96e9d-133">Requires `CREATE DATABASE`, `CREATE ANY DATABASE`, or `ALTER ANY DATABASE` permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96e9d-134">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96e9d-134">Using SQL Server Management Studio</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="96e9d-135">So fügen Sie eine Datenbank an</span><span class="sxs-lookup"><span data-stu-id="96e9d-135">To Attach a Database</span></span>  
  
1.  <span data-ttu-id="96e9d-136">Stellen Sie im Objekt-Explorer von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="96e9d-136">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="96e9d-137">Klicken Sie mit der rechten Maustaste auf **Datenbanken** , und klicken Sie auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="96e9d-137">Right-click **Databases** and click **Attach**.</span></span>  
  
3.  <span data-ttu-id="96e9d-138">Wenn Sie die anzufügende Datenbank angeben möchten, klicken Sie im Dialogfeld **Datenbanken anfügen** auf **Hinzufügen**. Wählen Sie dann im Dialogfeld **Datenbankdateien suchen** den Datenträger aus, auf dem die Datenbank gespeichert ist. Erweitern Sie die Verzeichnisstruktur, um die MDF-Datei der Datenbank zu suchen und auszuwählen. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="96e9d-138">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**; and in the **Locate Database Files** dialog box, select the disk drive where the database resides and expand the directory tree to find and select the .mdf file of the database; for example:</span></span>  
  
     `C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\AdventureWorks2012_Data.mdf`  
  
    > [!IMPORTANT]  
    > <span data-ttu-id="96e9d-139">Wenn Sie versuchen, eine Datenbank auszuwählen, die bereits angefügt wurde, wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="96e9d-139">Trying to select a database that is already attached generates an error.</span></span>  
  
     <span data-ttu-id="96e9d-140">**Anzufügende Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="96e9d-140">**Databases to attach**</span></span>  
     <span data-ttu-id="96e9d-141">Zeigt Informationen zu den ausgewählten Datenbanken an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-141">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="96e9d-142">Zeigt ein Symbol an, das den Status des Anfügevorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-142">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="96e9d-143">Die möglichen Symbole werden in der unten stehenden Beschreibung von **Status** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="96e9d-143">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="96e9d-144">**Speicherort für MDF-Datei**</span><span class="sxs-lookup"><span data-stu-id="96e9d-144">**MDF File Location**</span></span>  
     <span data-ttu-id="96e9d-145">Zeigt den Pfad und den Dateinamen der ausgewählten MDF-Datei an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-145">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="96e9d-146">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="96e9d-146">**Database Name**</span></span>  
     <span data-ttu-id="96e9d-147">Zeigt den Namen der Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-147">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="96e9d-148">**Anfügen als**</span><span class="sxs-lookup"><span data-stu-id="96e9d-148">**Attach As**</span></span>  
     <span data-ttu-id="96e9d-149">Gibt wahlweise einen anderen Namen für die anzufügende Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-149">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="96e9d-150">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="96e9d-150">**Owner**</span></span>  
     <span data-ttu-id="96e9d-151">Zeigt eine Dropdownliste mit möglichen Datenbankbesitzern an, aus der Sie wahlweise einen anderen Besitzer auswählen können.</span><span class="sxs-lookup"><span data-stu-id="96e9d-151">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="96e9d-152">**Status**</span><span class="sxs-lookup"><span data-stu-id="96e9d-152">**Status**</span></span>  
     <span data-ttu-id="96e9d-153">Zeigt den Status der Datenbank an (siehe folgende Tabelle).</span><span class="sxs-lookup"><span data-stu-id="96e9d-153">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="96e9d-154">Symbol</span><span class="sxs-lookup"><span data-stu-id="96e9d-154">Icon</span></span>|<span data-ttu-id="96e9d-155">Statustext</span><span class="sxs-lookup"><span data-stu-id="96e9d-155">Status text</span></span>|<span data-ttu-id="96e9d-156">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="96e9d-156">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="96e9d-157">(Kein Symbol)</span><span class="sxs-lookup"><span data-stu-id="96e9d-157">(No icon)</span></span>|<span data-ttu-id="96e9d-158">(Kein Text)</span><span class="sxs-lookup"><span data-stu-id="96e9d-158">(No text)</span></span>|<span data-ttu-id="96e9d-159">Das Anfügen hat noch nicht begonnen oder steht für dieses Objekt noch aus.</span><span class="sxs-lookup"><span data-stu-id="96e9d-159">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="96e9d-160">Dies ist der Standardwert bei Öffnen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="96e9d-160">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="96e9d-161">Grünes, nach rechts zeigendes Dreieck</span><span class="sxs-lookup"><span data-stu-id="96e9d-161">Green, right-pointing triangle</span></span>|<span data-ttu-id="96e9d-162">In Bearbeitung</span><span class="sxs-lookup"><span data-stu-id="96e9d-162">In progress</span></span>|<span data-ttu-id="96e9d-163">Das Anfügen hat begonnen, ist aber noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-163">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="96e9d-164">Grünes Häkchen</span><span class="sxs-lookup"><span data-stu-id="96e9d-164">Green check mark</span></span>|<span data-ttu-id="96e9d-165">Erfolg</span><span class="sxs-lookup"><span data-stu-id="96e9d-165">Success</span></span>|<span data-ttu-id="96e9d-166">Das Objekt wurde erfolgreich angefügt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-166">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="96e9d-167">Roter Kreis mit einem weißen Kreuz darin</span><span class="sxs-lookup"><span data-stu-id="96e9d-167">Red circle containing a white cross</span></span>|<span data-ttu-id="96e9d-168">Fehler</span><span class="sxs-lookup"><span data-stu-id="96e9d-168">Error</span></span>|<span data-ttu-id="96e9d-169">Beim Anfügen ist ein Fehler aufgetreten. Der Vorgang konnte deshalb nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-169">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="96e9d-170">Kreis mit zwei schwarzen Quadranten (links und rechts) und zwei weißen Quadranten (oben und unten) darin</span><span class="sxs-lookup"><span data-stu-id="96e9d-170">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="96e9d-171">Beendet</span><span class="sxs-lookup"><span data-stu-id="96e9d-171">Stopped</span></span>|<span data-ttu-id="96e9d-172">Das Anfügen wurde nicht erfolgreich abgeschlossen, weil der Benutzer den Vorgang angehalten hat.</span><span class="sxs-lookup"><span data-stu-id="96e9d-172">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="96e9d-173">Kreis mit einem gekrümmten Pfeil darin, der entgegengesetzt der Uhrzeigerrichtung zeigt</span><span class="sxs-lookup"><span data-stu-id="96e9d-173">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="96e9d-174">Rollback wurde ausgeführt</span><span class="sxs-lookup"><span data-stu-id="96e9d-174">Rolled Back</span></span>|<span data-ttu-id="96e9d-175">Anfügen war erfolgreich, es wurde jedoch ein Rollback durchgeführt, weil beim Anfügen eines anderen Objekts ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="96e9d-175">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="96e9d-176">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="96e9d-176">**Message**</span></span>  
     <span data-ttu-id="96e9d-177">Zeigt entweder eine leere Meldung oder einen "Datei nicht gefunden"-Link an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-177">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="96e9d-178">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="96e9d-178">**Add**</span></span>  
     <span data-ttu-id="96e9d-179">Suchen Sie die erforderlichen Hauptdatenbankdateien.</span><span class="sxs-lookup"><span data-stu-id="96e9d-179">Find the necessary main database files.</span></span> <span data-ttu-id="96e9d-180">Wenn der Benutzer eine MDF-Datei auswählt, werden entsprechende Informationen automatisch in die jeweiligen Felder des Rasters **Anzufügende Datenbank** eingetragen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-180">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="96e9d-181">**Remove**</span><span class="sxs-lookup"><span data-stu-id="96e9d-181">**Remove**</span></span>  
     <span data-ttu-id="96e9d-182">Entfernt die ausgewählte Datei aus dem Raster **Anzufügende Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="96e9d-182">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="96e9d-183">**"** *<datenbankname>* **" Datenbankdetails**</span><span class="sxs-lookup"><span data-stu-id="96e9d-183">**"** *<database_name>* **" database details**</span></span>  
     <span data-ttu-id="96e9d-184">Zeigt die Namen der anzufügenden Dateien an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-184">Displays the names of the files to be attached.</span></span> <span data-ttu-id="96e9d-185">Klicken Sie zum Überprüfen oder Ändern des Pfadnamens einer Datei auf die Schaltfläche **Durchsuchen** ( **…** ).</span><span class="sxs-lookup"><span data-stu-id="96e9d-185">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    > <span data-ttu-id="96e9d-186">Wenn eine Datei nicht vorhanden ist, wird in der Spalte **Meldung** "Nicht gefunden" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-186">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="96e9d-187">Wenn keine Protokolldatei gefunden wird, liegt sie in einem anderen Verzeichnis oder wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="96e9d-187">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="96e9d-188">Dann müssen Sie entweder den Dateipfad im Raster **Datenbankdetails** ändern, um auf den richtigen Pfad zu verweisen, oder die Protokolldatei aus dem Raster entfernen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-188">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="96e9d-189">Wenn keine .ndf-Datei gefunden wurde, müssen Sie ihren Pfad im Raster aktualisieren, um auf den richtigen Pfad zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-189">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="96e9d-190">**Originaldateiname**</span><span class="sxs-lookup"><span data-stu-id="96e9d-190">**Original File Name**</span></span>  
     <span data-ttu-id="96e9d-191">Zeigt den Namen der angefügten Datei an, die zur Datenbank gehört.</span><span class="sxs-lookup"><span data-stu-id="96e9d-191">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="96e9d-192">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="96e9d-192">**File Type**</span></span>  
     <span data-ttu-id="96e9d-193">Gibt den Dateityp an: **Datendatei** oder **Protokolldatei**.</span><span class="sxs-lookup"><span data-stu-id="96e9d-193">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="96e9d-194">**Aktueller Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="96e9d-194">**Current File Path**</span></span>  
     <span data-ttu-id="96e9d-195">Zeigt den Pfad zur ausgewählten Datenbankdatei an</span><span class="sxs-lookup"><span data-stu-id="96e9d-195">Displays the path to the selected database file.</span></span> <span data-ttu-id="96e9d-196">Die Pfadangabe kann manuell bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-196">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="96e9d-197">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="96e9d-197">**Message**</span></span>  
     <span data-ttu-id="96e9d-198">Zeigt entweder eine leere Meldung oder einen „**Datei nicht gefunden**“-Hyperlink an.</span><span class="sxs-lookup"><span data-stu-id="96e9d-198">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96e9d-199">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96e9d-199">Using Transact-SQL</span></span>  
  
### <a name="to-attach-a-database"></a><span data-ttu-id="96e9d-200">So fügen Sie eine Datenbank an</span><span class="sxs-lookup"><span data-stu-id="96e9d-200">To attach a database</span></span>  
  
1.  <span data-ttu-id="96e9d-201">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="96e9d-201">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="96e9d-202">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="96e9d-202">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="96e9d-203">Verwenden Sie die [Create Database](/sql/t-sql/statements/create-database-sql-server-transact-sql) -Anweisung mit der Close-Anweisung `FOR ATTACH` .</span><span class="sxs-lookup"><span data-stu-id="96e9d-203">Use the [CREATE DATABASE](/sql/t-sql/statements/create-database-sql-server-transact-sql) statement with the `FOR ATTACH` close.</span></span>  
  
     <span data-ttu-id="96e9d-204">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="96e9d-204">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="96e9d-205">In diesem Beispiel werden die Dateien der Datenbank [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] angefügt, und die Datenbank wird in `MyAdventureWorks`umbenannt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-205">This example attaches the files of the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database and renames the database to `MyAdventureWorks`.</span></span>  
  
    ```sql  
    CREATE DATABASE MyAdventureWorks   
        ON (FILENAME = 'C:\MySQLServer\AdventureWorks_Data.mdf'),   
        (FILENAME = 'C:\MySQLServer\AdventureWorks_Log.ldf')   
        FOR ATTACH;  
    ```  
  
    > [!NOTE]  
    > <span data-ttu-id="96e9d-206">Alternativ können Sie die gespeicherte Prozedur [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) oder [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) verwenden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-206">Alternatively, you can use the [sp_attach_db](/sql/relational-databases/system-stored-procedures/sp-attach-db-transact-sql) or [sp_attach_single_file_db](/sql/relational-databases/system-stored-procedures/sp-attach-single-file-db-transact-sql) stored procedure.</span></span> <span data-ttu-id="96e9d-207">Diese Prozeduren werden jedoch in einer zukünftigen Version von Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-207">However, these procedures will be removed in a future version of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="96e9d-208">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="96e9d-208">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="96e9d-209">Wir empfehlen die Verwendung von Create Database... Für anfügen.</span><span class="sxs-lookup"><span data-stu-id="96e9d-209">We recommend that you use CREATE DATABASE ... FOR ATTACH instead.</span></span>  
  
##  <a name="follow-up-after-upgrading-a-sql-server-database"></a><a name="FollowUp"></a><span data-ttu-id="96e9d-210">Nächster Schritt: Nach dem Aktualisieren einer SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="96e9d-210">Follow Up: After Upgrading a SQL Server Database</span></span>  
 <span data-ttu-id="96e9d-211">Wenn Sie ein Upgrade einer Datenbank mithilfe der Attach-Methode durchführen, ist die Datenbank sofort verfügbar und wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="96e9d-211">fter you upgrade a database by using the attach method, the database becomes available immediately and is automatically upgraded.</span></span> <span data-ttu-id="96e9d-212">Wenn die Datenbank Volltextindizes aufweist, werden diese beim Upgrade entweder importiert, zurückgesetzt oder neu erstellt, je nach der Einstellung der Servereigenschaft **Volltextupgrade-Option** .</span><span class="sxs-lookup"><span data-stu-id="96e9d-212">If the database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the **Full-Text Upgrade Option** server property.</span></span> <span data-ttu-id="96e9d-213">Wenn die Upgradeoption auf **Importieren** oder **Neu erstellen**festgelegt ist, sind die Volltextindizes während des Upgrades nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96e9d-213">If the upgrade option is set to **Import** or **Rebuild**, the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="96e9d-214">Je nach Menge der indizierten Daten kann der Importvorgang mehrere Stunden dauern; die Neuerstellung sogar bis zu zehnmal länger.</span><span class="sxs-lookup"><span data-stu-id="96e9d-214">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="96e9d-215">Wenn die Upgradeoption auf **Importieren**festgelegt und kein Volltextkatalog verfügbar ist, werden die zugehörigen Volltextindizes neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="96e9d-215">Note also that when the upgrade option is set to **Import**, if a full-text catalog is not available, the associated full-text indexes are rebuilt.</span></span>  
  
<span data-ttu-id="96e9d-216">War der Kompatibilitätsgrad einer Benutzerdatenbank vor dem Upgrade 100 oder höher, wird er nach dem Upgrade beibehalten.</span><span class="sxs-lookup"><span data-stu-id="96e9d-216">If the compatibility level of a user database is 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="96e9d-217">War der Kompatibilitätsgrad der aktualisierten Datenbank vor dem Upgrade 90, wird er auf 100 gesetzt, was dem niedrigsten unterstützten Kompatibilitätsgrad in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]entspricht.</span><span class="sxs-lookup"><span data-stu-id="96e9d-217">If the compatibility level is 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="96e9d-218">Weitere Informationen finden Sie unter [ALTER DATABASE-Kompatibilitätsgrad &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="96e9d-218">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96e9d-219">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96e9d-219">See Also</span></span>  
 <span data-ttu-id="96e9d-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="96e9d-220">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="96e9d-221">Trennen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="96e9d-221">Detach a Database</span></span>](detach-a-database.md)  
  
  
