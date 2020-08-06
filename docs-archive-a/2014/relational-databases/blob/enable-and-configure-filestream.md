---
title: Aktivieren und Konfigurieren von FILESTREAM | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607849"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="c938f-102">Aktivieren und Konfigurieren von FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c938f-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="c938f-103">Vor der Verwendung von FILESTREAM müssen Sie FILESTREAM in der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]instanz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c938f-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="c938f-104">In diesem Thema erfahren Sie, wie Sie FILESTREAM mit dem SQL Server-Konfigurations-Manager aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c938f-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c938f-105">Sie können FILESTREAM nicht in einer 32-Bit-Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktivieren, die unter einem 64-Bit-Betriebssystem ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c938f-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="c938f-106">Aktivieren von FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="c938f-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="c938f-107">So aktivieren und ändern Sie FILESTREAM-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="c938f-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="c938f-108">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="c938f-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="c938f-109">Klicken Sie in der Dienstliste mit der rechten Maustaste auf **SQL Server-Dienste**, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c938f-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="c938f-110">Suchen Sie im Snap-In **SQL Server-Konfigurations-Manager** die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , auf der Sie FILESTREAM aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c938f-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="c938f-111">Klicken Sie mit der rechten Maustaste auf die Instanz, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c938f-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="c938f-112">Klicken Sie im Dialogfeld **Eigenschaften von SQL Server** auf die Registerkarte **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="c938f-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="c938f-113">Aktivieren Sie das Kontrollkästchen **FILESTREAM für Transact-SQL-Zugriff aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="c938f-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="c938f-114">Wenn das Lesen und Schreiben von FILESTREAM-Daten über Windows erforderlich ist, klicken Sie auf **FILESTREAM für E/A-Streamingzugriff auf Datei aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c938f-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="c938f-115">Geben Sie den Namen der Windows-Freigabe in das Feld **Windows-Freigabename** ein.</span><span class="sxs-lookup"><span data-stu-id="c938f-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="c938f-116">Wenn Remoteclients auf FILESTREAM-Daten auf dieser Freigabe zugreifen müssen, wählen Sie **Streamingzugriff von Remoteclients auf FILESTREAM-Daten zulassen**.</span><span class="sxs-lookup"><span data-stu-id="c938f-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="c938f-117">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="c938f-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="c938f-118">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Neue Abfrage** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c938f-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="c938f-119">Geben Sie im Abfrage-Editor den folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code ein:</span><span class="sxs-lookup"><span data-stu-id="c938f-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="c938f-120">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c938f-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="c938f-121">Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="c938f-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="c938f-122">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="c938f-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="c938f-123">Physische Konfiguration und Wartung</span><span class="sxs-lookup"><span data-stu-id="c938f-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="c938f-124">Beachten Sie beim Einrichten von FILESTREAM-Speichervolumes die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="c938f-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="c938f-125">Deaktivieren Sie kurze Dateinamen auf FILESTREAM-Computersystemen.</span><span class="sxs-lookup"><span data-stu-id="c938f-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="c938f-126">Bei kurzen Dateinamen dauert das Erstellen erheblich länger.</span><span class="sxs-lookup"><span data-stu-id="c938f-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="c938f-127">Um kurze Dateinamen zu deaktivieren, verwenden Sie das Windows-Hilfsprogramm **fsutil** .</span><span class="sxs-lookup"><span data-stu-id="c938f-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="c938f-128">Defragmentieren Sie FILESTREAM-Computersysteme in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="c938f-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="c938f-129">Verwenden Sie 64-KB-NTFS-Cluster.</span><span class="sxs-lookup"><span data-stu-id="c938f-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="c938f-130">Komprimierte Volumes müssen auf 4-KB-NTFS-Cluster festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c938f-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="c938f-131">Deaktivieren Sie die Indizierung von FILESTREAM-Volumes, und legen Sie **disablelastaccess** fest. Verwenden Sie zum Festlegen von **disablelastaccess**das Windows-Hilfsprogramm **fsutil** .</span><span class="sxs-lookup"><span data-stu-id="c938f-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="c938f-132">Deaktivieren Sie die Virenüberprüfung für FILESTREAM-Volumes, wenn diese nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c938f-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="c938f-133">Wenn eine Virenüberprüfung erforderlich ist, sollten keine Richtlinien festgelegt werden, durch die verdächtige oder infizierte Dateien automatisch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c938f-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="c938f-134">Richten Sie die RAID-Stufe ein, die für Fehlertoleranz und die für Anwendungen erforderliche Leistung optimal geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c938f-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="c938f-135">RAID-Stufe</span><span class="sxs-lookup"><span data-stu-id="c938f-135">RAID level</span></span>|<span data-ttu-id="c938f-136">Schreibleistung</span><span class="sxs-lookup"><span data-stu-id="c938f-136">Write performance</span></span>|<span data-ttu-id="c938f-137">Leseleistung</span><span class="sxs-lookup"><span data-stu-id="c938f-137">Read performance</span></span>|<span data-ttu-id="c938f-138">Fehlertoleranz</span><span class="sxs-lookup"><span data-stu-id="c938f-138">Fault tolerance</span></span>|<span data-ttu-id="c938f-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c938f-139">Remarks</span></span>|  
|<span data-ttu-id="c938f-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="c938f-140">RAID 5</span></span>|<span data-ttu-id="c938f-141">Normal</span><span class="sxs-lookup"><span data-stu-id="c938f-141">Normal</span></span>|<span data-ttu-id="c938f-142">Normal</span><span class="sxs-lookup"><span data-stu-id="c938f-142">Normal</span></span>|<span data-ttu-id="c938f-143">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-143">Excellent</span></span>|<span data-ttu-id="c938f-144">Die Leistung ist besser als bei einem einzelnen Datenträger oder JBOD und geringer als bei RAID 0 oder RAID 5 mit Striping.</span><span class="sxs-lookup"><span data-stu-id="c938f-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="c938f-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="c938f-145">RAID 0</span></span>|<span data-ttu-id="c938f-146">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-146">Excellent</span></span>|<span data-ttu-id="c938f-147">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-147">Excellent</span></span>|<span data-ttu-id="c938f-148">Keine</span><span class="sxs-lookup"><span data-stu-id="c938f-148">None</span></span>||  
|<span data-ttu-id="c938f-149">RAID 5 + Striping</span><span class="sxs-lookup"><span data-stu-id="c938f-149">RAID 5 + stripping</span></span>|<span data-ttu-id="c938f-150">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-150">Excellent</span></span>|<span data-ttu-id="c938f-151">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-151">Excellent</span></span>|<span data-ttu-id="c938f-152">Hervorragend</span><span class="sxs-lookup"><span data-stu-id="c938f-152">Excellent</span></span>|<span data-ttu-id="c938f-153">Die aufwendigste Option.</span><span class="sxs-lookup"><span data-stu-id="c938f-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="c938f-154">Physischer Daten bankentwurf</span><span class="sxs-lookup"><span data-stu-id="c938f-154">Physical Database Design</span></span>  
 <span data-ttu-id="c938f-155">Beachten Sie beim Entwerfen einer FILESTREAM-Datenbank die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="c938f-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="c938f-156">FILESTREAM-Spalten müssen von einer entsprechenden `uniqueidentifier` ROWGUID-Spalte begleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c938f-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="c938f-157">Diese Arten von Tabellen müssen auch über einen eindeutigen Index verfügen.</span><span class="sxs-lookup"><span data-stu-id="c938f-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="c938f-158">In der Regel ist dieser Index kein gruppierter Index.</span><span class="sxs-lookup"><span data-stu-id="c938f-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="c938f-159">Wenn die Geschäftslogik für Datenbanken einen gruppierten Index erfordert, müssen Sie sicherstellen, dass die im Index gespeicherten Werte nicht zufällig sind.</span><span class="sxs-lookup"><span data-stu-id="c938f-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="c938f-160">Zufallswerte bewirken, dass der Index neu sortiert wird, sobald in der Tabelle eine Zeile hinzugefügt oder entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="c938f-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="c938f-161">Aus Leistungsgründen sollten die FILESTREAM-Dateigruppen und -Container nicht auf Volumes gespeichert werden, auf denen sich das Betriebssystem, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank, das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokoll, tempdb oder die Auslagerungsdatei befindet.</span><span class="sxs-lookup"><span data-stu-id="c938f-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="c938f-162">Speicherplatzverwaltung und Richtlinien werden von FILESTREAM nicht direkt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c938f-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="c938f-163">Sie können jedoch indirekt Speicherplatz verwalten und Richtlinien anwenden, indem Sie jede FILESTREAM-Dateigruppe einem separaten Volume zuweisen und die Verwaltungsfunktionen des Volumes verwenden.</span><span class="sxs-lookup"><span data-stu-id="c938f-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
