---
title: Sichern und Wiederherstellen von Analysis Services-Datenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/25/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.Backup.f1
- sql12.asvs.ssmsimbi.Restore.f1
helpviewer_keywords:
- backing up databases [Analysis Services]
- encryption [Analysis Services]
- databases [Analysis Services], restoring
- cryptography [Analysis Services]
- databases [Analysis Services], backing up
- restoring databases [Analysis Services]
- recovery [Analysis Services]
ms.assetid: 947eebd2-3622-479e-8aa6-57c11836e4ec
author: minewiskan
ms.author: owend
ms.openlocfilehash: 00a05fa39b57836490dde3dc6d4a1095e4b3ccaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702015"
---
# <a name="backup-and-restore-of-analysis-services-databases"></a><span data-ttu-id="4d152-102">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="4d152-102">Backup and Restore of Analysis Services Databases</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="4d152-103">verfügt über Sicherungs- und Wiederherstellungsfunktionen, weshalb Sie für eine Datenbank und ihre Objekte einen Zustand wiederherstellen können, der zu einem bestimmten Zeitpunkt gültig war.</span><span class="sxs-lookup"><span data-stu-id="4d152-103">includes backup and restore so that you can recover a database and its objects from a particular point in time.</span></span> <span data-ttu-id="4d152-104">Die Sicherung und Wiederherstellung ist auch eine zulässige Methode zum Migrieren von Datenbanken zu aktualisierten Servern, zum Verschieben von Datenbanken zwischen Servern oder zum Bereitstellen einer Datenbank auf einem Produktionsserver.</span><span class="sxs-lookup"><span data-stu-id="4d152-104">Backup and restore is also a valid technique for migrating databases to upgraded servers, moving databases between servers, or deploying a database to a production server.</span></span> <span data-ttu-id="4d152-105">Zur Datenwiederherstellung sollten Sie, falls Sie noch nicht über einen Sicherungsplan verfügen und Ihre Daten wertvoll sind, so schnell wie möglich einen solchen Plan entwerfen und implementieren.</span><span class="sxs-lookup"><span data-stu-id="4d152-105">For the purposes of data recovery, if you do not already have a backup plan and your data is valuable, you should design and implement a plan as soon as possible.</span></span>  
  
 <span data-ttu-id="4d152-106">Die Befehle zur Sicherung und die Wiederherstellung werden in einer bereitgestellten Analysis Services-Datenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d152-106">The backup and restore commands are performed on a deployed Analysis Services database.</span></span> <span data-ttu-id="4d152-107">Für die Projekte und Projektmappen in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]sollten Sie mithilfe der Quellcodeverwaltung sicherstellen, dass Sie bestimmte Versionen der Quelldateien wiederherstellen können, und anschließend einen Datenwiederherstellungsplan für das Repository des von Ihnen verwendeten Quellcodeverwaltungssystems erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d152-107">For your projects and solutions in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you should use source control to ensure you can recover specific versions of your source files, and then create a data recovery plan for the repository of the source control system you are using.</span></span>  
  
 <span data-ttu-id="4d152-108">Eine vollständige Sicherung einschließlich der Quelldaten erfordert das Sichern der Datenbank, die Detaildaten enthält.</span><span class="sxs-lookup"><span data-stu-id="4d152-108">For a full backup that includes source data, you have to back up the database which contains detail data.</span></span> <span data-ttu-id="4d152-109">Insbesondere, wenn Sie ROLAP- oder DirectQuery-Datenbankspeicher verwenden, werden Detaildaten in einer externen relationalen SQL Server-Datenbank gespeichert, die sich von der Analysis Services-Datenbank unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="4d152-109">Specifically, if you are using ROLAP or DirectQuery database storage, detail data is stored in an external SQL Server relational database that is distinct from the Analysis Services database.</span></span> <span data-ttu-id="4d152-110">Wenn alle Objekte demgegenüber tabellarisch oder mehrdimensional sind, schließt die Analysis Services-Sicherung sowohl die Metadaten als auch die Quelldaten ein.</span><span class="sxs-lookup"><span data-stu-id="4d152-110">Otherwise, if all objects are tabular or multidimensional, the Analysis Services backup will include both the metadata and source data.</span></span>  
  
 <span data-ttu-id="4d152-111">Ein eindeutiger Vorzug der automatischen Sicherung besteht darin, dass die Datenmomentaufnahme stets so aktuell ist wie durch die automatisch gesteuerte Sicherungshäufigkeit vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="4d152-111">One clear benefit of automating backup is that the data snapshot will always be as up-to-date as the automated frequency of backup specifies.</span></span> <span data-ttu-id="4d152-112">Automatische Planer stellen sicher, dass das Sichern nicht vergessen wird.</span><span class="sxs-lookup"><span data-stu-id="4d152-112">Automated schedulers ensure that backups are not forgotten.</span></span> <span data-ttu-id="4d152-113">Auch das Wiederherstellen einer Datenbank kann automatisiert werden. Dies ist gleichzeitig eine gute Möglichkeit zum Replizieren der Daten, doch achten Sie stets darauf, die Verschlüsselungsschlüsseldatei auf der Instanz, die die replizierten Daten erhält, ebenfalls zu sichern.</span><span class="sxs-lookup"><span data-stu-id="4d152-113">Restoring a database can also be automated, and can be a good way to replicate data, but be sure to back up the encryption key file on the instance you replicate to.</span></span> <span data-ttu-id="4d152-114">Die Synchronisierungsfunktion ist für die Replizierung von Datenbanken von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bestimmt, doch sie erfasst nur veraltete Daten.</span><span class="sxs-lookup"><span data-stu-id="4d152-114">The synchronization feature is dedicated to replication of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] databases, but only for the data that is out of date.</span></span> <span data-ttu-id="4d152-115">Alle der hier genannten Funktionen können über die Benutzerschnittstelle implementiert werden, und zwar über XML/A-Befehle oder programmgesteuert über AMO.</span><span class="sxs-lookup"><span data-stu-id="4d152-115">All of the features mentioned here can be implemented through the user interface, by way of XML/A commands or programmatically run through AMO.</span></span>  
  
 <span data-ttu-id="4d152-116">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="4d152-116">This topic includes the following sections:</span></span>  
  
-   [<span data-ttu-id="4d152-117">Vorbereiten der Sicherung</span><span class="sxs-lookup"><span data-stu-id="4d152-117">Preparing for Backup</span></span>](#bkmk_prep)  
  
-   [<span data-ttu-id="4d152-118">Sichern einer mehrdimensionalen oder tabellarischen Datenbank</span><span class="sxs-lookup"><span data-stu-id="4d152-118">Backing Up a Multidimensional or a Tabular Database</span></span>](#bkmk_cube)  
  
-   [<span data-ttu-id="4d152-119">Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="4d152-119">Restoring an Analysis Services Database</span></span>](#bkmk_restore)  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq"></a> <span data-ttu-id="4d152-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4d152-120">Prerequisites</span></span>  
 <span data-ttu-id="4d152-121">Sie müssen über Administratorberechtigungen für die Analysis Services-Instanz oder die Vollzugriffsberechtigungen (Administrator) für die Datenbank verfügen, die Sie sichern.</span><span class="sxs-lookup"><span data-stu-id="4d152-121">You must have administrative permissions on the Analysis Services instance or Full Control (Administrator) permissions on the database you are backing up.</span></span>  
  
 <span data-ttu-id="4d152-122">Der Wiederherstellungsort muss einer Analysis Services-Instanz entsprechen, die dieselbe Version oder eine neuere Version aufweist als die Instanz, auf der die Sicherung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4d152-122">Restore location must be an Analysis Services instance that is the same version, or a newer version, as the instance from which the backup was taken.</span></span> <span data-ttu-id="4d152-123">Obwohl Sie eine Datenbank von einer [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Instanz nicht auf einer früheren Version von Analysis Services wiederherstellen können, ist es üblich, eine Datenbank einer älteren Version, z.B. SQL Server 2012, auf einer neueren [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Instanz wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d152-123">Although you cannot restore a database from a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance to an earlier version of Analysis Services, it is common practice to restore an older version database, such as SQL Server 2012, on a newer [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance.</span></span>  
  
 <span data-ttu-id="4d152-124">Der Wiederherstellungsort muss den gleichen Servertyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4d152-124">Restore location must be the same server type.</span></span> <span data-ttu-id="4d152-125">Tabellarische Datenbanken können nur auf einer Analysis Services-Instanz wiederhergestellt werden, die im tabellarischen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d152-125">Tabular databases can only be restored to Analysis Services running in tabular mode.</span></span> <span data-ttu-id="4d152-126">Mehrdimensionale Datenbanken erfordern eine Instanz, die im mehrdimensionalen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4d152-126">Multidimensional databases require an instance running in multidimensional mode.</span></span>  
  
##  <a name="preparing-for-backup"></a><a name="bkmk_prep"></a><span data-ttu-id="4d152-127">Vorbereiten der Sicherung</span><span class="sxs-lookup"><span data-stu-id="4d152-127">Preparing for Backup</span></span>  
 <span data-ttu-id="4d152-128">Verwenden Sie die folgende Prüfliste, um die Sicherung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="4d152-128">Use the following checklist to prepare for backup:</span></span>  
  
-   <span data-ttu-id="4d152-129">Überprüfen Sie den Speicherort, an der die Sicherungsdatei gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4d152-129">Check the location where the backup file will be stored.</span></span> <span data-ttu-id="4d152-130">Wenn Sie einen Remotestandort verwenden, müssen Sie es als UNC-Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="4d152-130">If you are using a remote location, you must specify it as a UNC folder.</span></span> <span data-ttu-id="4d152-131">Überprüfen Sie, ob Sie auf den UNC-Pfad zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4d152-131">Verify that you can access the UNC path.</span></span>  
  
-   <span data-ttu-id="4d152-132">Überprüfen Sie die Berechtigungen für den Ordner, um sicherzustellen, dass das Analysis Services-Dienstkonto über Lese-/Schreibberechtigungen für den Ordner verfügt.</span><span class="sxs-lookup"><span data-stu-id="4d152-132">Check the permissions on the folder to ensure that the Analysis Services service account has Read/Write permissions on the folder.</span></span>  
  
-   <span data-ttu-id="4d152-133">Kontrollieren Sie den Zielserver auf ausreichenden Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="4d152-133">Check for sufficient disk space on the target server.</span></span>  
  
-   <span data-ttu-id="4d152-134">Überprüfen Sie vorhandene Dateien mit gleichem Namen.</span><span class="sxs-lookup"><span data-stu-id="4d152-134">Check for existing files of the same name.</span></span> <span data-ttu-id="4d152-135">Wenn bereits eine Datei mit dem gleichen Namen vorhanden ist, tritt ein Sicherungsfehler auf, sofern Sie keine Optionen zum Überschreiben der Datei festlegen.</span><span class="sxs-lookup"><span data-stu-id="4d152-135">If a file of the same name already exists, backup will fail unless you specify options to overwrite the file.</span></span>  
  
##  <a name="backing-up-a-multidimensional-or-a-tabular-database"></a><a name="bkmk_cube"></a><span data-ttu-id="4d152-136">Sichern einer mehrdimensionalen oder tabellarischen Datenbank</span><span class="sxs-lookup"><span data-stu-id="4d152-136">Backing Up a Multidimensional or a Tabular Database</span></span>  
 <span data-ttu-id="4d152-137">Administratoren können eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank unabhängig von der Datenbankgröße in einer einzelnen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Sicherungsdatei (.abf) sichern.</span><span class="sxs-lookup"><span data-stu-id="4d152-137">Administrators can back up an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database to a single [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] backup file (.abf), regardless of size of the database.</span></span> <span data-ttu-id="4d152-138">Schritt-für-Schritt-Anweisungen finden Sie auf der TechMantra-Seite unter [How to Backup an Analysis Services Database](http://www.mytechmantra.com/LearnSQLServer/Backup_an_Analysis_Services_Database.html) (Sichern einer Analysis Services-Datenbank) und unter [Automate Backup an Analysis Services Database](http://www.mytechmantra.com/LearnSQLServer/Automate_Backup_of_Analysis_Services_Database.html)(Automatische Sicherung einer Analysis Services-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="4d152-138">For step by step instructions, see [How to Backup an Analysis Services Database (TechMantra)](http://www.mytechmantra.com/LearnSQLServer/Backup_an_Analysis_Services_Database.html) and [Automate Backup an Analysis Services Database (TechMantra)](http://www.mytechmantra.com/LearnSQLServer/Automate_Backup_of_Analysis_Services_Database.html).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d152-139">Wenn [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] zum Laden und Abfragen von PowerPivot-Datenmodellen in einer SharePoint-Umgebung verwendet wird, werden die zugehörigen Modelle aus SharePoint-Inhaltsdatenbanken geladen.</span><span class="sxs-lookup"><span data-stu-id="4d152-139">[!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], used for loading and querying PowerPivot data models in a SharePoint environment, loads its models from SharePoint content databases.</span></span> <span data-ttu-id="4d152-140">Diese Inhaltsdatenbanken sind relational und werden in der relationalen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank-Engine ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d152-140">These content databases are relational and run on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational database engine.</span></span> <span data-ttu-id="4d152-141">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bietet folglich keine Sicherungs-/Wiederherstellungsstrategie für PowerPivot-Datenmodelle.</span><span class="sxs-lookup"><span data-stu-id="4d152-141">As such, there is no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] backup and restore strategy for PowerPivot data models.</span></span> <span data-ttu-id="4d152-142">Wenn Sie einen Notfallwiederherstellungsplan für SharePoint-Inhalte eingerichtet haben, umfasst der Plan die in den Inhaltsdatenbanken gespeicherten PowerPivot-Datenmodelle.</span><span class="sxs-lookup"><span data-stu-id="4d152-142">If you have a disaster recovery plan in place for SharePoint content, that plan encompasses the PowerPivot data models stored in the content databases.</span></span>  
  
 <span data-ttu-id="4d152-143">**Remotepartitionen**</span><span class="sxs-lookup"><span data-stu-id="4d152-143">**Remote Partitions**</span></span>  
  
 <span data-ttu-id="4d152-144">Falls die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank Remotepartitionen enthält, sollten diese ebenfalls gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="4d152-144">If the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database contains remote partitions, the remote partitions should also be backed up.</span></span> <span data-ttu-id="4d152-145">Wenn Sie eine Datenbank mit Remotepartitionen sichern, werden alle Remotepartitionen auf jedem Remoteserver in einer einzigen Datei auf jedem der jeweiligen Remoteserver gesichert.</span><span class="sxs-lookup"><span data-stu-id="4d152-145">When you back up a database with remote partitions, all the remote partitions on each remote server are backed up to a single file on each of those remote servers respectively.</span></span> <span data-ttu-id="4d152-146">Sollen diese Remotesicherungen also außerhalb der jeweiligen Hostcomputer erstellt werden, müssen Sie die zu sichernden Dateien manuell in die für sie bestimmten Speicherplatzbereiche kopieren.</span><span class="sxs-lookup"><span data-stu-id="4d152-146">Therefore, if you want to create those remote backups off their respective host computers, you will have to manually copy those files to the designated storage areas.</span></span>  
  
 <span data-ttu-id="4d152-147">**Inhalt einer Sicherungsdatei**</span><span class="sxs-lookup"><span data-stu-id="4d152-147">**Contents of a backup file**</span></span>  
  
 <span data-ttu-id="4d152-148">Beim Sichern einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank entsteht eine Sicherungsdatei, deren Inhalt je nach dem von den Datenbankobjekten verwendeten Speichermodus variiert.</span><span class="sxs-lookup"><span data-stu-id="4d152-148">Backing up an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database produces a backup file whose contents vary depending upon the storage mode used by the database objects.</span></span> <span data-ttu-id="4d152-149">Dieser Unterschied beim Sicherungsinhalt geht auf den Umstand zurück, dass mit jedem Speichermodus eine andere Gruppe von Informationen innerhalb einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4d152-149">This difference in backup content results from the fact that each storage mode actually stores a different set of information within an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="4d152-150">So werden beispielsweise bei mehrdimensionalen, hybriden OLAP-Partitionen und -Dimensionen (HOLAP) sowohl Aggregationen als auch Metadaten in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank gespeichert, während relationale OLAP-Partitionen und -Dimensionen (ROLAP) nur Metadaten in der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="4d152-150">For example, multidimensional hybrid OLAP (HOLAP) partitions and dimensions store aggregations and metadata in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, while relational OLAP (ROLAP) partitions and dimensions only store metadata in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="4d152-151">Da der eigentliche Inhalt einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank je nach Speichermodus der einzelnen Partitionen variiert, variiert auch der Inhalt der Sicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="4d152-151">Because the actual contents of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database vary based on the storage mode of each partition, the contents of the backup file also vary.</span></span> <span data-ttu-id="4d152-152">Die folgende Tabelle ordnet den Inhalt der Sicherungsdatei dem von den Objekten verwendeten Speichermodus zu.</span><span class="sxs-lookup"><span data-stu-id="4d152-152">The following table associates the contents of the backup file to the storage mode used by the objects.</span></span>  
  
|<span data-ttu-id="4d152-153">Speichermodus</span><span class="sxs-lookup"><span data-stu-id="4d152-153">Storage Mode</span></span>|<span data-ttu-id="4d152-154">Inhalt der Sicherungsdatei</span><span class="sxs-lookup"><span data-stu-id="4d152-154">Contents of backup file</span></span>|  
|------------------|-----------------------------|  
|<span data-ttu-id="4d152-155">Multidimensionale MOLAP-Partitionen und -Dimensionen</span><span class="sxs-lookup"><span data-stu-id="4d152-155">Multidimensional MOLAP partitions and dimensions</span></span>|<span data-ttu-id="4d152-156">Metadaten, Quelldaten und Aggregationen</span><span class="sxs-lookup"><span data-stu-id="4d152-156">Metadata, source data, and aggregations</span></span>|  
|<span data-ttu-id="4d152-157">HOLAP-Partitionen und -Dimensionen (Multidimensionale OLAP)</span><span class="sxs-lookup"><span data-stu-id="4d152-157">Multidimensional HOLAP partitions and dimensions</span></span>|<span data-ttu-id="4d152-158">Metadaten und Aggregationen</span><span class="sxs-lookup"><span data-stu-id="4d152-158">Metadata and aggregations</span></span>|  
|<span data-ttu-id="4d152-159">ROLAP-Partitionen und -Dimensionen (Multidimensionale OLAP)</span><span class="sxs-lookup"><span data-stu-id="4d152-159">Multidimensional ROLAP partitions and dimensions</span></span>|<span data-ttu-id="4d152-160">Metadaten</span><span class="sxs-lookup"><span data-stu-id="4d152-160">Metadata</span></span>|  
|<span data-ttu-id="4d152-161">Tabellarische, speicherinterne Modelle</span><span class="sxs-lookup"><span data-stu-id="4d152-161">Tabular In-Memory Models</span></span>|<span data-ttu-id="4d152-162">Meta- und Quelldaten</span><span class="sxs-lookup"><span data-stu-id="4d152-162">Metadata and source data</span></span>|  
|<span data-ttu-id="4d152-163">Tabellarische DirectQuery-Modelle</span><span class="sxs-lookup"><span data-stu-id="4d152-163">Tabular DirectQuery Models</span></span>|<span data-ttu-id="4d152-164">Nur Metadaten</span><span class="sxs-lookup"><span data-stu-id="4d152-164">Metadata only</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="4d152-165">Beim Sichern einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank werden nicht die Daten in den zugrunde liegenden Datenquellen, wie z. B. eine relationale Datenbank, gesichert.</span><span class="sxs-lookup"><span data-stu-id="4d152-165">Backing up an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database does not back up the data in any underlying data sources, such as a relational database.</span></span> <span data-ttu-id="4d152-166">Nur der Inhalt der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank wird gesichert.</span><span class="sxs-lookup"><span data-stu-id="4d152-166">Only the contents of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database are backed up.</span></span>  
  
 <span data-ttu-id="4d152-167">Wenn Sie eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank sichern, können Sie unter folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="4d152-167">When you back up an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, you can choose from the following options:</span></span>  
  
-   <span data-ttu-id="4d152-168">Ob alle Datenbanksicherungen komprimiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d152-168">Whether to compress all database backups.</span></span> <span data-ttu-id="4d152-169">Standardmäßig werden Sicherungen komprimiert.</span><span class="sxs-lookup"><span data-stu-id="4d152-169">The default is to compress backups.</span></span>  
  
-   <span data-ttu-id="4d152-170">Ob der Inhalt der Sicherungsdateien verschlüsselt werden und für das Entschlüsseln und Wiederherstellen der Datei ein Kennwort erforderlich sein soll.</span><span class="sxs-lookup"><span data-stu-id="4d152-170">Whether to encrypt the contents of the backup files and require a password before the file can be unencrypted and restored.</span></span> <span data-ttu-id="4d152-171">Standardmäßig werden Sicherungsdateien nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4d152-171">By default, the backed up data is not encrypted.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4d152-172">Für jede Sicherungsdatei muss der Benutzer, der den Sicherungsbefehl ausführt, über die Berechtigung zum Schreiben in den für jede Datei angegebenen Sicherungsspeicherort verfügen.</span><span class="sxs-lookup"><span data-stu-id="4d152-172">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="4d152-173">Dem Benutzer muss zudem eine der folgenden Rollen zugewiesen worden sein: Mitglied einer Serverrolle für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4d152-173">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="4d152-174">Weitere Informationen zum Sichern einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank finden Sie unter [Sicherungsoptionen](backup-options.md).</span><span class="sxs-lookup"><span data-stu-id="4d152-174">For more information about backing up an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Backup Options](backup-options.md).</span></span>  
  
##  <a name="restoring-an-analysis-services-database"></a><a name="bkmk_restore"></a><span data-ttu-id="4d152-175">Wiederherstellen einer Analysis Services Datenbank</span><span class="sxs-lookup"><span data-stu-id="4d152-175">Restoring an Analysis Services Database</span></span>  
 <span data-ttu-id="4d152-176">Administratoren können eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank von einer oder mehreren Sicherungsdateien wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="4d152-176">Administrators can restore an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database from one or more backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d152-177">Falls die Sicherungsdatei verschlüsselt ist, können Sie sie erst für die Wiederherstellung einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank verwenden, nachdem Sie das beim Sichern verwendete Kennwort angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4d152-177">If a backup file is encrypted, you must provide the password specified during backup before you can use that file to restore an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="4d152-178">Während der Wiederherstellung stehen Ihnen folgende Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4d152-178">During restoration, you have the following options:</span></span>  
  
-   <span data-ttu-id="4d152-179">Sie können die Datenbank mit ihrem ursprünglichen Datenbanknamen wiederherstellen, oder Sie können einen neuen Datenbanknamen angeben.</span><span class="sxs-lookup"><span data-stu-id="4d152-179">You can restore the database using the original database name, or you can specify a new database name.</span></span>  
  
-   <span data-ttu-id="4d152-180">Sie können eine vorhandene Datenbank überschreiben.</span><span class="sxs-lookup"><span data-stu-id="4d152-180">You can overwrite an existing database.</span></span> <span data-ttu-id="4d152-181">Falls Sie sich für das Überschreiben der Datenbank entscheiden, müssen Sie ausdrücklich angeben, dass die vorhandene Datenbank überschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d152-181">If you choose to overwrite the database, you must expressly specify that you want to overwrite the existing database.</span></span>  
  
-   <span data-ttu-id="4d152-182">Sie können wählen, ob vorhandene Sicherheitsinformationen wiederhergestellt werden sollen oder ob Sie die Informationen zur Sicherheitsmitgliedschaft auslassen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d152-182">You can choose whether to restore existing security information or skip security membership information.</span></span>  
  
-   <span data-ttu-id="4d152-183">Sie können auswählen, ob der Wiederherstellungsbefehl den Wiederherstellungsordner für jede wiederherzustellende Partition ändern soll.</span><span class="sxs-lookup"><span data-stu-id="4d152-183">You can choose to have the restore command change the restoration folder for each partition being restored.</span></span> <span data-ttu-id="4d152-184">Lokale Partitionen können an jedem Ordnerstandort wiederhergestellt werden, der für die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , auf der die Datenbank wiederhergestellt wird, als lokal gilt.</span><span class="sxs-lookup"><span data-stu-id="4d152-184">Local partitions can be restored to any folder location that is local to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance to which the database is being restored.</span></span> <span data-ttu-id="4d152-185">Remotepartitionen können in jedem Ordner und auf jedem Server außer dem lokalen Server wiederhergestellt werden. Remotepartitionen können nicht zu lokalen Partitionen werden.</span><span class="sxs-lookup"><span data-stu-id="4d152-185">Remote partitions can be restored to any folder on any server, other than the local server; remote partitions cannot become local.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4d152-186">Für jede Sicherungsdatei muss der Benutzer, der den Wiederherstellungsbefehl ausführt, über die Berechtigung zum Lesen von dem für jede Datei angegebenen Sicherungsspeicherort verfügen.</span><span class="sxs-lookup"><span data-stu-id="4d152-186">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="4d152-187">Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank, die nicht auf dem Server installiert ist, muss der Benutzer zusätzlich Mitglied der Serverrolle für die betreffende [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="4d152-187">To restore an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="4d152-188">Zum Überschreiben einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank muss der Benutzer entweder Mitglied der Serverrolle für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="4d152-188">To overwrite an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d152-189">Nach dem Wiederherstellen einer vorhandenen Datenbank verliert der Benutzer, der die Datenbank wiederhergestellt hat, möglicherweise den Zugriff auf diese Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4d152-189">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="4d152-190">Dies ist u. U. der Fall, wenn der Benutzer zum Zeitpunkt der Sicherung kein Mitglied der Serverrolle oder der Datenbankrolle mit der Berechtigung "Vollzugriff (Administrator)" war.</span><span class="sxs-lookup"><span data-stu-id="4d152-190">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="4d152-191">Informationen zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank finden Sie unter [Wiederherstellungsoptionen](restore-options.md).</span><span class="sxs-lookup"><span data-stu-id="4d152-191">For more information about restoring an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Restore Options](restore-options.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d152-192">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d152-192">See Also</span></span>  
 <span data-ttu-id="4d152-193">[Sichern, wiederherstellen und Synchronisieren von Datenbanken &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="4d152-193">[Backing Up, Restoring, and Synchronizing Databases &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md) </span></span>  
 [<span data-ttu-id="4d152-194">Analysis Services PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d152-194">Analysis Services PowerShell</span></span>](../analysis-services-powershell.md)  
  
  