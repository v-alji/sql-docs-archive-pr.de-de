---
title: Erstellen einer Datenbankmomentaufnahme (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725905"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="5f027-102">Erstellen einer Datenbankmomentaufnahme (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f027-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="5f027-103">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankmomentaufnahme kann nur mithilfe von [!INCLUDE[tsql](../../includes/tsql-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5f027-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5f027-104">nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f027-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="5f027-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="5f027-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5f027-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5f027-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="5f027-107">Security</span><span class="sxs-lookup"><span data-stu-id="5f027-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="5f027-108">Bewährte Methode: Benennen von Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="5f027-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="5f027-109">**So erstellen Sie eine Datenbank-Momentaufnahme mit:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="5f027-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f027-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5f027-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="5f027-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5f027-111">Prerequisites</span></span>  
 <span data-ttu-id="5f027-112">Die Quelldatenbank, die ein Wiederherstellungsmodell verwenden kann, muss die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5f027-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="5f027-113">Die Serverinstanz muss eine Edition von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführen, die Datenbankmomentaufnahmen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f027-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="5f027-114">Informationen zur Unterstützung von Daten Bank Momentaufnahmen in finden Sie unter [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [von den Editionen von SQL Server 2014 unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="5f027-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="5f027-115">Die Quelldatenbank muss online sein, es sei denn, bei der Datenbank handelt es sich um eine Spiegeldatenbank innerhalb einer Datenbank-Spiegelungssitzung.</span><span class="sxs-lookup"><span data-stu-id="5f027-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="5f027-116">Zum Erstellen einer Datenbankmomentaufnahme für die Spiegeldatenbank muss sich die Datenbank im synchronisierten[Spiegelungsstatus](../../database-engine/database-mirroring/mirroring-states-sql-server.md)befinden.</span><span class="sxs-lookup"><span data-stu-id="5f027-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="5f027-117">Die Quelldatenbank kann nicht als skalierbare freigegebene Datenbank konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5f027-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5f027-118">Informationen zu anderen bedeutenden Überlegungen finden Sie unter [Datenbank-Momentaufnahmen &#40;SQL Server&#41;](database-snapshots-sql-server.md)erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5f027-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="5f027-119">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="5f027-119">Recommendations</span></span>  
 <span data-ttu-id="5f027-120">In diesem Abschnitt werden die folgenden bewährten Methoden erläutert:</span><span class="sxs-lookup"><span data-stu-id="5f027-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="5f027-121">Bewährte Methode: Benennen von Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="5f027-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="5f027-122">Bewährte Methode: Beschränken der Anzahl von Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="5f027-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="5f027-123">Bewährte Methode: Clientverbindungen mit einer Datenbankmomentaufnahme</span><span class="sxs-lookup"><span data-stu-id="5f027-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="5f027-124">Bewährte Methode: Benennen von Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="5f027-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="5f027-125">Vor dem Erstellen von Momentaufnahmen müssen Sie unbedingt überlegen, wie Sie diese benennen.</span><span class="sxs-lookup"><span data-stu-id="5f027-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="5f027-126">Jede Datenbankmomentaufnahme erfordert einen eindeutigen Datenbanknamen.</span><span class="sxs-lookup"><span data-stu-id="5f027-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="5f027-127">Um den Verwaltungsaufwand zu reduzieren, kann der Name einer Momentaufnahme Informationen enthalten, mit denen die Datenbank identifiziert wird:</span><span class="sxs-lookup"><span data-stu-id="5f027-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="5f027-128">Der Name der Quelldatenbank.</span><span class="sxs-lookup"><span data-stu-id="5f027-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="5f027-129">Einen Hinweis, dass der neue Name für eine Momentaufnahme ist</span><span class="sxs-lookup"><span data-stu-id="5f027-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="5f027-130">Das Erstellungsdatum und die Erstellungszeit der Momentaufnahme, eine Sequenznummer oder sonstige Informationen, wie z. B. die Tageszeit, um sequenzielle Momentaufnahmen in einer bestimmten Datenbank zu unterscheiden</span><span class="sxs-lookup"><span data-stu-id="5f027-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="5f027-131">Angenommen, Sie haben eine Reihe von Momentaufnahmen für die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5f027-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="5f027-132">Täglich werden drei Momentaufnahmen im Abstand von sechs Stunden zwischen 6:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="5f027-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="5f027-133">und 18:00 Uhr erstellt (24-Stunden-System).</span><span class="sxs-lookup"><span data-stu-id="5f027-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="5f027-134">Jede tägliche Momentaufnahme wird nach 24 Stunden gelöscht und durch eine neue gleichnamige Momentaufnahme ersetzt.</span><span class="sxs-lookup"><span data-stu-id="5f027-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="5f027-135">Beachten Sie, dass jeder Momentaufnahmename einen Hinweis auf die Uhrzeit, aber nicht auf den Tag enthält:</span><span class="sxs-lookup"><span data-stu-id="5f027-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="5f027-136">Falls alternativ die Erstellungszeit dieser täglichen Momentaufnahmen von Tag zu Tag variiert, ist möglicherweise eine weniger präzise Benennungskonvention vorzuziehen, wie beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="5f027-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="5f027-137">Bewährte Methode: Beschränken der Anzahl von Datenbankmomentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="5f027-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="5f027-138">Durch das Erstellen einer Reihe von Momentaufnahmen werden im Laufe der Zeit sequenzielle Momentaufnahmen der Quelldatenbank aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5f027-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="5f027-139">Jede Momentaufnahme wird so lange persistent gespeichert, bis sie explizit gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5f027-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="5f027-140">Durch jede Momentaufnahme nehmen die ursprünglichen Seiten beim Aktualisieren an Größe zu. Deshalb sollten Sie Speicherplatz freigeben, indem Sie eine ältere Momentaufnahme löschen, nachdem eine neue Momentaufnahme erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5f027-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f027-141">Wenn Sie eine Datenbankmomentaufnahme wiederherstellen möchten, müssen Sie andere Momentaufnahmen in dieser Datenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="5f027-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="5f027-142">Bewährte Methode: Clientverbindungen mit einer Datenbankmomentaufnahme</span><span class="sxs-lookup"><span data-stu-id="5f027-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="5f027-143">Zur Verwendung einer Datenbankmomentaufnahme müssen die Clients wissen, wo sie diese finden.</span><span class="sxs-lookup"><span data-stu-id="5f027-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="5f027-144">Die Benutzer können aus einer Datenbankmomentaufnahme lesen, während eine andere Datenbankmomentaufnahme erstellt oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="5f027-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="5f027-145">Wenn Sie jedoch eine vorhandenen Momentaufnahme durch eine neue Momentaufnahme ersetzen, müssen Sie Clients an die neue Momentaufnahme umleiten.</span><span class="sxs-lookup"><span data-stu-id="5f027-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="5f027-146">Die Benutzer können mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]manuell eine Verbindung mit einer Datenbankmomentaufnahme herstellen.</span><span class="sxs-lookup"><span data-stu-id="5f027-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5f027-147">Für die Unterstützung einer Produktionsumgebung sollten Sie jedoch eine programmatische Lösung erstellen, die Berichterstellungsclients transparent an die neueste Momentaufnahme der Datenbank weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="5f027-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f027-148">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5f027-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5f027-149">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="5f027-149">Permissions</span></span>  
 <span data-ttu-id="5f027-150">Jeder Benutzer, der eine Datenbank erstellen kann, kann auch eine Datenbankmomentaufnahme erstellen. Eine Momentaufnahme einer Spiegeldatenbank kann jedoch nur von Mitgliedern der festen Serverrolle **sysadmin** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5f027-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5f027-151">So erstellen Sie eine Datenbankmomentaufnahme (mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f027-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="5f027-152">**So erstellen Sie eine Datenbankmomentaufnahme**</span><span class="sxs-lookup"><span data-stu-id="5f027-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f027-153">Ein Beispiel für diese Prozedur finden Sie in [Beispiele (Transact-SQL)](#TsqlExample)an späterer Stelle in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5f027-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="5f027-154">Prüfen Sie die aktuelle Größe der Quelldatenbank, um sicherzustellen, dass der verfügbare Festplattenspeicher zum Speichern der Datenbankmomentaufnahme ausreicht.</span><span class="sxs-lookup"><span data-stu-id="5f027-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="5f027-155">Die maximale Größe einer Datenbankmomentaufnahme beläuft sich auf die Größe der Quelldatenbank zum Zeitpunkt der Momentaufnahmeerstellung.</span><span class="sxs-lookup"><span data-stu-id="5f027-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="5f027-156">Weitere Informationen finden Sie unter [Anzeigen der Größe der Datei mit geringer Dichte einer Datenbank-Momentaufnahme &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="5f027-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="5f027-157">Geben Sie eine CREATE DATABASE-Anweisung für die Dateien aus, und verwenden Sie dabei die AS SNAPSHOT OF-Klausel.</span><span class="sxs-lookup"><span data-stu-id="5f027-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="5f027-158">Bei der Erstellung einer Momentaufnahme müssen die logischen Namen aller in der Quelldatenbank enthaltenen Datenbankdateien angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5f027-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="5f027-159">Die Syntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5f027-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="5f027-160">CREATE DATABASE *Name der Datenbank-Momentaufnahme*</span><span class="sxs-lookup"><span data-stu-id="5f027-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="5f027-161">EIN</span><span class="sxs-lookup"><span data-stu-id="5f027-161">ON</span></span>  
  
     <span data-ttu-id="5f027-162">(</span><span class="sxs-lookup"><span data-stu-id="5f027-162">(</span></span>  
  
     <span data-ttu-id="5f027-163">NAME =*logischer Dateiname*,</span><span class="sxs-lookup"><span data-stu-id="5f027-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="5f027-164">FILENAME = '*physischer Dateiname*'</span><span class="sxs-lookup"><span data-stu-id="5f027-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="5f027-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="5f027-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="5f027-166">ALS SNAPSHOT OF *Name der Quelldatenbank*</span><span class="sxs-lookup"><span data-stu-id="5f027-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="5f027-167">[;]</span><span class="sxs-lookup"><span data-stu-id="5f027-167">[;]</span></span>  
  
     <span data-ttu-id="5f027-168">Dabei ist *Name der Quelldatenbank* die Quelldatenbank, *logischer Dateiname* der in SQL Server beim Verweis auf die Datei verwendete logische Name, *physischer Dateiname* der vom Betriebssystem beim Erstellen der Datei verwendete Pfad- und Dateiname und *Name der Datenbank-Momentaufnahme* der Name der Momentaufnahme, aus der die Datenbank wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f027-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="5f027-169">Eine vollständige Beschreibung dieser Syntax finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f027-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5f027-170">Wenn Sie eine Datenbankmomentaufnahme erstellen, darf die CREATE DATABASE-Anweisung weder Protokolldateien noch Offlinedateien, Wiederherstellungsdateien oder außer Kraft gesetzte Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f027-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="5f027-171">Beispiele (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5f027-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f027-172">Die in den Beispielen verwendete Erweiterung `.ss` ist willkürlich.</span><span class="sxs-lookup"><span data-stu-id="5f027-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="5f027-173">Dieser Abschnitt enthält folgende Beispiele:</span><span class="sxs-lookup"><span data-stu-id="5f027-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="5f027-174">A.</span><span class="sxs-lookup"><span data-stu-id="5f027-174">A.</span></span> [<span data-ttu-id="5f027-175">Erstellen einer Momentaufnahme für die AdventureWorks-Datenbank</span><span class="sxs-lookup"><span data-stu-id="5f027-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="5f027-176">B.</span><span class="sxs-lookup"><span data-stu-id="5f027-176">B.</span></span> [<span data-ttu-id="5f027-177">Erstellen einer Momentaufnahme für die Sales-Datenbank</span><span class="sxs-lookup"><span data-stu-id="5f027-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="5f027-178">A.</span><span class="sxs-lookup"><span data-stu-id="5f027-178">A.</span></span> <span data-ttu-id="5f027-179">Erstellen einer Momentaufnahme für die AdventureWorks-Datenbank</span><span class="sxs-lookup"><span data-stu-id="5f027-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="5f027-180">In diesem Beispiel wird eine Datenbankmomentaufnahme für die `AdventureWorks` -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f027-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="5f027-181">Der Momentaufnahmename, `AdventureWorks_dbss_1800`, und der Dateiname der entsprechenden Sparsedatei, `AdventureWorks_data_1800.ss`, geben als Erstellungszeit 18:00 Uhr an.</span><span class="sxs-lookup"><span data-stu-id="5f027-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="5f027-182">B.</span><span class="sxs-lookup"><span data-stu-id="5f027-182">B.</span></span> <span data-ttu-id="5f027-183">Erstellen einer Momentaufnahme für die Sales-Datenbank</span><span class="sxs-lookup"><span data-stu-id="5f027-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="5f027-184">In diesem Beispiel wird eine Datenbankmomentaufnahme, `sales_snapshot1200`, für die `Sales` -Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f027-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="5f027-185">Diese Datenbank wurde in dem Beispiel "Erstellen einer Datenbank mit Dateigruppen" in [Create Database &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f027-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5f027-186">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="5f027-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="5f027-187">Anzeigen einer Datenbank-Momentaufnahme &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f027-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="5f027-188">Wiederherstellen einer Datenbank zu einer Datenbank-Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="5f027-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="5f027-189">Löschen einer Datenbankmomentaufnahme &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f027-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="5f027-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f027-190">See Also</span></span>  
 <span data-ttu-id="5f027-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5f027-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="5f027-192">Datenbank-Momentaufnahmen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f027-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
