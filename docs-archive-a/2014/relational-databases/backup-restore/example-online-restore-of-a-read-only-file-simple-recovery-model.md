---
title: 'Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei (einfaches Wiederherstellungsmodell) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726005"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="c9dfe-102">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei (einfaches Wiederherstellungsmodell)</span><span class="sxs-lookup"><span data-stu-id="c9dfe-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="c9dfe-103">Dieses Thema ist nur für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken relevant, für die ein einfaches Wiederherstellungsmodell mit einer schreibgeschützten Dateigruppe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="c9dfe-104">Bei einem einfachen Wiederherstellungsmodell kann eine schreibgeschützte Datei online wiederhergestellt werden, wenn eine Dateisicherung vorhanden ist, die erstellt wurde, nachdem der Schreibschutz letztmalig festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="c9dfe-105">In diesem Beispiel sind in der Datenbank `adb` drei Dateigruppen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="c9dfe-106">Die Dateigruppe `A` weist Lese-/Schreibzugriff auf, die Dateigruppen `B` und `C` sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="c9dfe-107">Zu Beginn sind alle Dateigruppen online.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="c9dfe-108">Eine schreibgeschützte Datei in Dateigruppe `B`, `b1`, muss wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="c9dfe-109">Der Datenbankadministrator kann sie mithilfe einer Sicherung wiederherstellen, die erstellt wurde, nachdem der Schreibschutz für die Datei festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="c9dfe-110">Für die Dauer der Wiederherstellung ist die Dateigruppe `B` offline, der Rest der Datenbank bleibt jedoch online.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="c9dfe-111">Wiederherstellungssequenz</span><span class="sxs-lookup"><span data-stu-id="c9dfe-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9dfe-112">Die Syntax für eine Onlinewiederherstellungssequenz ist dieselbe wie bei einer Offlinewiederherstellungssequenz.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="c9dfe-113">Zum Wiederherstellen der Datei befolgt der Datenbankadministrator die folgende Wiederherstellungssequenz:</span><span class="sxs-lookup"><span data-stu-id="c9dfe-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="c9dfe-114">Die Datei ist zurzeit online.</span><span class="sxs-lookup"><span data-stu-id="c9dfe-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="c9dfe-115">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="c9dfe-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="c9dfe-116">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c9dfe-117">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;einfaches Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="c9dfe-118">Beispiel: Schrittweise Wiederherstellung einer Datenbank &#40;Vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="c9dfe-119">Beispiel: Schrittweise Wiederherstellung nur bestimmter Dateigruppen &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="c9dfe-120">Beispiel: Onlinewiederherstellung einer Datei mit Lese-/Schreibzugriff &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="c9dfe-121">Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="c9dfe-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9dfe-122">See Also</span></span>  
 <span data-ttu-id="c9dfe-123">[Onlinewiederherstellungen &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9dfe-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="c9dfe-124">[Schrittweise Wiederherstellungen &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9dfe-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="c9dfe-125">[Dateiwiederherstellungen &#40;einfaches Wiederherstellungsmodell&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="c9dfe-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="c9dfe-126">[Übersicht über Wiederherstellungsvorgänge &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9dfe-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="c9dfe-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9dfe-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
