---
title: Wiederherstellen einer Datenbanksicherung unter dem einfachen Wiederherstellungsmodell (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698330"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="da286-102">Wiederherstellen einer Datenbanksicherung unter dem einfachen Wiederherstellungsmodell (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="da286-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="da286-103">In diesem Thema wird erläutert, wie eine vollständige Datenbanksicherung wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="da286-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="da286-104">Nur der Systemadministrator, der die vollständige Datenbanksicherung wiederherstellt, darf die wiederherzustellende Datenbank aktuell verwenden.</span><span class="sxs-lookup"><span data-stu-id="da286-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="da286-105">Voraussetzungen und Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="da286-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="da286-106">Um eine verschlüsselte Datenbank wiederherstellen zu können, muss das Zertifikat oder der asymmetrische Schlüssel verfügbar sein, das oder der zum Verschlüsseln der Datenbank verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="da286-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="da286-107">Ohne das Zertifikat oder den asymmetrischen Schlüssel kann die Datenbank nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="da286-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="da286-108">Darum muss das Zertifikat, das zur Verschlüsselung des Verschlüsselungsschlüssels für die Datenbank verwendet wurde, so lange beibehalten werden, wie die Sicherung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="da286-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="da286-109">Weitere Informationen finden Sie unter [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="da286-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="da286-110">Aus Sicherheitsgründen empfiehlt es sich nicht, Datenbanken aus unbekannten oder nicht vertrauenswürdigen Quellen anzufügen oder wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="da286-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="da286-111">Solche Datenbanken können bösartigen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code ausführt oder Fehler verursacht, indem er das Schema oder die physische Datenbankstruktur ändert.</span><span class="sxs-lookup"><span data-stu-id="da286-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="da286-112">Bevor Sie eine Datenbank aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, führen Sie auf einem Nichtproduktionsserver [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus. Überprüfen Sie außerdem den Code in der Datenbank, z.B. gespeicherte Prozeduren oder anderen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="da286-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="da286-113">Datenbank-Kompatibilitätsgrad nach dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="da286-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="da286-114">Der Kompatibilitätsgrad der Datenbanken **tempdb**, **model**, **msdb** und **Resource** wird nach dem Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] festgelegt.</span><span class="sxs-lookup"><span data-stu-id="da286-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="da286-115">Die **master** -Systemdatenbank behält den Kompatibilitätsgrad bei, der vor dem Upgrade bestand, sofern dieser nicht unter 100 lag.</span><span class="sxs-lookup"><span data-stu-id="da286-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="da286-116">War der Kompatibilitätsgrad von **master** vor dem Upgrade geringer als 100, wird er nach dem Upgrade auf 100 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="da286-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="da286-117">War der Kompatibilitätsgrad einer Benutzerdatenbank vor dem Upgrade 100 oder höher, wird er nach dem Upgrade beibehalten.</span><span class="sxs-lookup"><span data-stu-id="da286-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="da286-118">War der Kompatibilitätsgrad der aktualisierten Datenbank vor dem Upgrade 90, wird er auf 100 gesetzt, was dem niedrigsten unterstützten Kompatibilitätsgrad in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]entspricht.</span><span class="sxs-lookup"><span data-stu-id="da286-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da286-119">Neue Benutzerdatenbanken erben den Kompatibilitätsgrad der **model** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="da286-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="da286-120">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="da286-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="da286-121">So stellen Sie eine vollständige Datenbanksicherung wieder her</span><span class="sxs-lookup"><span data-stu-id="da286-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="da286-122">Führen Sie die RESTORE DATABASE-Anweisung aus, um die vollständige Datenbanksicherung wiederherzustellen, und geben Sie dabei Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="da286-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="da286-123">Den Namen der wiederherzustellenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="da286-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="da286-124">Das Sicherungsmedium, von dem die vollständige Datenbanksicherung wiederhergestellt wird</span><span class="sxs-lookup"><span data-stu-id="da286-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="da286-125">Die NORECOVERY-Klausel, wenn nach dem Wiederherstellen der vollständigen Datenbanksicherung eine Transaktionsprotokollsicherung oder eine differenzielle Datenbanksicherung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="da286-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="da286-126">Um eine verschlüsselte Datenbank wiederherstellen zu können, muss das Zertifikat oder der asymmetrische Schlüssel verfügbar sein, das oder der zum Verschlüsseln der Datenbank verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="da286-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="da286-127">Ohne das Zertifikat oder den asymmetrischen Schlüssel kann die Datenbank nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="da286-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="da286-128">Darum muss das Zertifikat, das zur Verschlüsselung des Verschlüsselungsschlüssels für die Datenbank verwendet wurde, so lange beibehalten werden, wie die Sicherung benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="da286-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="da286-129">Weitere Informationen finden Sie unter [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="da286-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="da286-130">Geben Sie wahlweise Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="da286-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="da286-131">Die FILE-Klausel, um den Sicherungssatz auf dem wiederherzustellenden Sicherungsmedium zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="da286-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da286-132">Wenn Sie eine Datenbank einer früheren Version nach [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]wiederherstellen, wird die Datenbank automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="da286-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="da286-133">In der Regel ist die Datenbank sofort verfügbar.</span><span class="sxs-lookup"><span data-stu-id="da286-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="da286-134">Wenn eine [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Datenbank aber Volltextindizes aufweist, werden diese beim Upgrade entweder importiert, zurückgesetzt oder neu erstellt, je nach der Einstellung der Servereigenschaft  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="da286-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="da286-135">Wenn die Upgradeoption auf „Importieren“ (**upgrade_option** = 2) oder „Neu erstellen“ (**upgrade_option** = 0) festgelegt ist, sind die Volltextindizes während des Upgrades nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="da286-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="da286-136">Je nach Menge der indizierten Daten kann der Importvorgang mehrere Stunden dauern; die Neuerstellung sogar bis zu zehnmal länger.</span><span class="sxs-lookup"><span data-stu-id="da286-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="da286-137">Wenn die Upgradeoption auf Importieren festgelegt ist und kein Volltextkatalog verfügbar ist, werden die zugehörigen Volltextindizes neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="da286-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="da286-138">Verwenden Sie **sp_fulltext_service** , um die Einstellung der Servereigenschaft [upgrade_option](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql)zu ändern.</span><span class="sxs-lookup"><span data-stu-id="da286-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da286-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da286-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="da286-140">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da286-140">Description</span></span>  
 <span data-ttu-id="da286-141">In diesem Beispiel wird die vollständige Datenbanksicherung der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank von Band wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="da286-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="da286-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="da286-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="da286-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da286-143">See Also</span></span>  
 <span data-ttu-id="da286-144">[Vollständige Datenbankwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="da286-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="da286-145">[Vollständige Datenbankwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="da286-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="da286-146">[Vollständige Datenbanksicherungen &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da286-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="da286-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="da286-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="da286-148">[Sicherungsverlauf und Headerinformationen &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="da286-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="da286-149">Neuerstellen von Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="da286-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
