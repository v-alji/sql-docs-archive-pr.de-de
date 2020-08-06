---
title: Sicherungskomprimierung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609276"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="1a329-102">Sicherungskomprimierung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a329-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="1a329-103">In diesem Thema wird die Komprimierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungen beschrieben, einschließlich Einschränkungen und Leistungseinbußen bei der Sicherungskomprimierung, Konfiguration der Sicherungskomprimierung sowie Komprimierungsverhältnis.</span><span class="sxs-lookup"><span data-stu-id="1a329-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a329-104">Informationen zu den Editionen von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , die die Sicherungs Komprimierung unterstützen, finden Sie unter [von den Editionen von SQL Server 2014 unterstützte Funktionen](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="1a329-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="1a329-105">Jede Edition von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höhere Versionen können eine komprimierte Sicherung wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="1a329-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="1a329-106">Vorteile</span><span class="sxs-lookup"><span data-stu-id="1a329-106">Benefits</span></span>  
  
-   <span data-ttu-id="1a329-107">Da eine komprimierte Sicherung kleiner als eine unkomprimierte Sicherung derselben Daten ist, wird für das Komprimieren einer Sicherung normalerweise weniger Geräte-E/A benötigt, und daher steigt die Sicherungsgeschwindigkeit in der Regel erheblich.</span><span class="sxs-lookup"><span data-stu-id="1a329-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="1a329-108">Weitere Informationen finden Sie unter [Auswirkungen der Sicherungskomprimierung auf die Leistung](#PerfImpact)weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1a329-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1a329-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1a329-109">Restrictions</span></span>  
 <span data-ttu-id="1a329-110">Für komprimierte Sicherungen gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="1a329-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="1a329-111">Komprimierte und nicht komprimierte Sicherungen können nicht nebeneinander in einem Mediensatz bestehen.</span><span class="sxs-lookup"><span data-stu-id="1a329-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="1a329-112">Frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können komprimierte Sicherungen nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="1a329-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="1a329-113">Mit "NTbackup" erstellte Sicherungen können nicht auf demselben Band gespeichert werden wie komprimierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sicherungen.</span><span class="sxs-lookup"><span data-stu-id="1a329-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="1a329-114">Auswirkungen der Sicherungskomprimierung auf die Leistung</span><span class="sxs-lookup"><span data-stu-id="1a329-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="1a329-115">Standardmäßig steigt die CPU-Nutzung durch die Komprimierung erheblich, und die bei der Komprimierung zusätzlich verbrauchten CPU-Ressourcen können sich negativ auf gleichzeitige Vorgänge auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a329-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="1a329-116">Daher ist es u.U. sinnvoll, in einer Sitzung, bei der die CPU-Nutzung durch[Resource Governor](../resource-governor/resource-governor.md)eingeschränkt ist, komprimierte Sicherungen mit niedriger Priorität zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a329-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="1a329-117">Weitere Informationen finden Sie unter [Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1a329-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="1a329-118">Wenn Sie genau wissen möchten, welche Leistung die Sicherungs-E/A erbringt, können Sie die Sicherungs-E/A zu und von den Geräten beurteilen, indem Sie die folgenden Arten von Leistungsindikatoren analysieren:</span><span class="sxs-lookup"><span data-stu-id="1a329-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="1a329-119">Windows-E/A-Leistungsindikatoren, wie die Indikatoren für physische Datenträger</span><span class="sxs-lookup"><span data-stu-id="1a329-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="1a329-120">Der Leistungsindikator **Mediumsdurchsatz Bytes/Sekunde** des Objekts [SQLServer:Sicherungsmedium](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="1a329-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="1a329-121">Der Leistungsindikator **Sicherungs-/Wiederherstellungsdurchsatz/Sekunde** des Objekts [SQLServer:Datenbanken](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="1a329-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="1a329-122">Informationen zu den Windows-Indikatoren finden Sie in der Windows-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="1a329-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="1a329-123">Informationen zur Arbeit mit SQL Server-Indikatoren finden Sie unter [Verwenden von SQL Server-Objekten](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="1a329-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="1a329-124">Berechnen des Komprimierungsverhältnisses einer komprimierten Sicherung</span><span class="sxs-lookup"><span data-stu-id="1a329-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="1a329-125">Zum Berechnen des Komprimierungsverhältnisses einer Sicherung verwenden Sie die Werte für die Sicherung in den Spalten **backup_size** und **compressed_backup_size** der Verlaufstabelle [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1a329-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="1a329-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="1a329-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="1a329-127">So gibt ein Komprimierungsverhältnis von 3:1 beispielsweise an, dass Sie etwa 66 Prozent an Speicherplatz sparen.</span><span class="sxs-lookup"><span data-stu-id="1a329-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="1a329-128">Für eine Abfrage in diesen Spalten können Sie die folgende Transact-SQL-Anweisung verwenden:</span><span class="sxs-lookup"><span data-stu-id="1a329-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="1a329-129">Das Komprimierungsverhältnis einer komprimierten Sicherung ist abhängig von den komprimierten Daten.</span><span class="sxs-lookup"><span data-stu-id="1a329-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="1a329-130">Das erzielte Komprimierungsverhältnis kann durch eine Reihe von Faktoren beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="1a329-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="1a329-131">Zu den Hauptfaktoren gehören:</span><span class="sxs-lookup"><span data-stu-id="1a329-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="1a329-132">Die Art der Daten.</span><span class="sxs-lookup"><span data-stu-id="1a329-132">The type of data.</span></span>  
  
     <span data-ttu-id="1a329-133">Zeichendaten lassen sich stärker komprimieren als andere Arten von Daten.</span><span class="sxs-lookup"><span data-stu-id="1a329-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="1a329-134">Die Einheitlichkeit der Daten unter den Zeilen einer Seite.</span><span class="sxs-lookup"><span data-stu-id="1a329-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="1a329-135">In der Regel enthält eine Seite mehrere Zeilen, in denen ein Feld den gleichen Wert aufweist. Dieser Wert kann möglicherweise sehr stark komprimiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a329-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="1a329-136">Dagegen ist bei Datenbanken mit Zufallsdaten oder nur einer großen Zeile pro Seite die komprimierte Sicherung beinahe so groß wie eine nicht komprimierte Sicherung.</span><span class="sxs-lookup"><span data-stu-id="1a329-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="1a329-137">Verschlüsselungsstatus der Daten.</span><span class="sxs-lookup"><span data-stu-id="1a329-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="1a329-138">Verschlüsselte Daten lassen sich deutlich weniger komprimieren als entsprechende unverschlüsselte Daten.</span><span class="sxs-lookup"><span data-stu-id="1a329-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="1a329-139">Wird die transparente Datenverschlüsselung zum Verschlüsseln einer gesamten Datenbank verwendet, ändert sich ihre Größe bei einer komprimierten Sicherung unter Umständen kaum oder gar nicht.</span><span class="sxs-lookup"><span data-stu-id="1a329-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="1a329-140">Komprimierungsstatus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="1a329-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="1a329-141">Falls die Datenbank bereits komprimiert ist, ändert sich ihre Größe bei einer komprimierten Sicherung unter Umständen kaum oder gar nicht.</span><span class="sxs-lookup"><span data-stu-id="1a329-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="1a329-142">Speicherplatzzuordnung für die Sicherungsdatei</span><span class="sxs-lookup"><span data-stu-id="1a329-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="1a329-143">Bei komprimierten Sicherungen ist die Größe der finalen Sicherungsdatei davon abhängig, wie stark die Daten komprimiert werden können, und dies ist erst bekannt, wenn der Sicherungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1a329-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="1a329-144">Wenn eine Datenbank daher mithilfe einer Komprimierung gesichert wird, verwendet die Datenbank-Engine standardmäßig einen Vorabzuordnungsalgorithmus für die Sicherungsdatei.</span><span class="sxs-lookup"><span data-stu-id="1a329-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="1a329-145">Dieser Algorithmus ordnet der Sicherungsdatei vorab einen vordefinierten Prozentsatz der Größe der Datenbank zu.</span><span class="sxs-lookup"><span data-stu-id="1a329-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="1a329-146">Wenn während des Sicherungsvorgangs mehr Platz benötigt wird, lässt die Datenbank-Engine die Datei wachsen.</span><span class="sxs-lookup"><span data-stu-id="1a329-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="1a329-147">Wenn die finale Größe kleiner als der reservierte Platz ist, verkleinert die Datenbank-Engine die Datei am Ende des Sicherungsvorgangs auf die tatsächliche finale Größe der Sicherung.</span><span class="sxs-lookup"><span data-stu-id="1a329-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="1a329-148">Verwenden Sie das Ablaufverfolgungsflag 3042, damit die Sicherungsdatei nur so viel größer werden kann, wie erforderlich, um die finale Größe zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="1a329-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="1a329-149">Durch das Ablaufverfolgungsflag 3042 wird bewirkt, dass der Sicherungsvorgang den standardmäßigen Vorabzuordnungsalgorithmus für die Sicherungskomprimierung umgeht.</span><span class="sxs-lookup"><span data-stu-id="1a329-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="1a329-150">Dieses Ablaufverfolgungsflag ist nützlich, wenn Sie Speicherplatz einsparen müssen, indem Sie nur die tatsächliche für die komprimierte Sicherung benötigte Größe zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1a329-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="1a329-151">Dieses Ablaufverfolgungsflag kann jedoch eine leichte Leistungseinbuße (eine mögliche Verlängerung des Sicherungsvorgangs) verursachen.</span><span class="sxs-lookup"><span data-stu-id="1a329-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="1a329-152">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1a329-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1a329-153">Konfigurieren von Sicherungskomprimierung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1a329-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="1a329-154">Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="1a329-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="1a329-155">Einschränken der CPU-Nutzung durch die Sicherungskomprimierung mithilfe der Ressourcenkontrolle &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a329-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="1a329-156">DBCC TRACEON &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a329-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="1a329-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a329-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="1a329-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a329-158">See Also</span></span>  
 <span data-ttu-id="1a329-159">[Übersicht über Sicherungen &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1a329-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="1a329-160">Ablaufverfolgungsflags &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a329-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
