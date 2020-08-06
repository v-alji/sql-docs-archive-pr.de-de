---
title: Sicherungsziel auswählen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdest.f1
ms.assetid: f79e824b-1525-45de-8ede-513563af41b6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5ffd1d2529dd13e42689bcf168c972d757fb5499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620450"
---
# <a name="select-backup-destination"></a><span data-ttu-id="5fb21-102">Sicherungsziel auswählen</span><span class="sxs-lookup"><span data-stu-id="5fb21-102">Select Backup Destination</span></span>
  <span data-ttu-id="5fb21-103">Wählen Sie im Dialogfeld **Sicherungsziel auswählen** ein Gerät als Sicherungsziel aus.</span><span class="sxs-lookup"><span data-stu-id="5fb21-103">Use the **Select Backup Destination** dialog box to select a device as your backup destination.</span></span> <span data-ttu-id="5fb21-104">Ein Sicherungsziel kann entweder ein Datenträger oder ein logisches Sicherungsmedium sein.</span><span class="sxs-lookup"><span data-stu-id="5fb21-104">A backup destination can be either a disk or a logical backup device.</span></span>  
  
 <span data-ttu-id="5fb21-105">**So verwenden Sie SQL Server Management Studio zum Sichern einer Datenbank**</span><span class="sxs-lookup"><span data-stu-id="5fb21-105">**To use SQL Server Management Studio to back up a database**</span></span>  
  
-   [<span data-ttu-id="5fb21-106">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb21-106">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="5fb21-107">Erstellen einer differenziellen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb21-107">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="5fb21-108">Sichern von Dateien und Dateigruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb21-108">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="5fb21-109">Sichern eines Transaktionsprotokolls &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb21-109">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="5fb21-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5fb21-110">Options</span></span>  
 <span data-ttu-id="5fb21-111">Die Optionen in diesem Dialogfeld sind davon abhängig, ob Sie ein Ziel auf einem Datenträger oder einem Band auswählen.</span><span class="sxs-lookup"><span data-stu-id="5fb21-111">The options of this dialog box depend on whether you are selecting a destination on disk or on tape.</span></span>  
  
 <span data-ttu-id="5fb21-112">**Ziele auf dem Datenträger**</span><span class="sxs-lookup"><span data-stu-id="5fb21-112">**Destination on disk**</span></span>  
 <span data-ttu-id="5fb21-113">Zum Angeben eines Sicherungsziels wählen Sie eine der folgenden Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="5fb21-113">To specify a backup destination, choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fb21-114">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="5fb21-114">**File name**</span></span>|<span data-ttu-id="5fb21-115">Wählen Sie diese Option aus, um eine lokale Datei oder Remotedatei als Sicherungsziel im Textfeld einzugeben.</span><span class="sxs-lookup"><span data-stu-id="5fb21-115">Choose this option to enter a local or remote file as the backup destination in the text box.</span></span><br /><br /> <span data-ttu-id="5fb21-116">Klicken Sie zum Angeben einer lokalen Datei rechts vom Textfeld auf die Schaltfläche zum Durchsuchen, und wählen Sie dann auf den Festplatten des Computers, auf dem der Server ausgeführt wird, eine Datei aus. Sie können auch den vollständigen Pfad und Dateinamen direkt eingeben, z. B. `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="5fb21-116">To specify a local file, click the browse button to the right of the text box and navigate to a file on the fixed drives of the computer running the server, or enter the full path and file name directly; for example, `C:\Program Files\Microsoft SQL Server\MSSQL\Backup\AdventureWorksBackup.bak`.</span></span><br /><br /> <span data-ttu-id="5fb21-117">Zum Angeben einer Remotedatei als Sicherungsziel geben Sie ihren vollqualifizierten UNC-Namen (Universal Naming Convention) ein.</span><span class="sxs-lookup"><span data-stu-id="5fb21-117">To specify a remote file as your backup destination, enter its fully qualified universal naming convention (UNC) name.</span></span> <span data-ttu-id="5fb21-118">Weitere Informationen finden Sie unter [Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md)aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5fb21-118">For more information, see [Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md).</span></span><br /><br /> <span data-ttu-id="5fb21-119">**\*\* Wichtig \*\*** Beim Sichern von Daten über ein Netzwerk können Netzwerkfehler auftreten. Aus diesem Grund wird empfohlen, dass Sie den Sicherungsvorgang nach der Fertigstellung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5fb21-119">**\*\* Important \*\*** Backing up data over a network can be subject to network errors; therefore, we recommend that you verify the backup operation after it finishes.</span></span> <span data-ttu-id="5fb21-120">Weitere Informationen finden Sie unter [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5fb21-120">For more information, see [RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql).</span></span>|  
|<span data-ttu-id="5fb21-121">**Sicherungsmedium**</span><span class="sxs-lookup"><span data-stu-id="5fb21-121">**Backup device**</span></span>|<span data-ttu-id="5fb21-122">Wählen Sie diese Option aus, um ein logisches Sicherungsmedium auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5fb21-122">Choose this option to select a logical backup device.</span></span><br /><br /> <span data-ttu-id="5fb21-123">Hinweis: Informationen zum Erstellen eines Datenträgersicherungsmediums finden Sie unter [Definieren eines logischen Sicherungsmediums für eine Datenträgerdatei &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5fb21-123">Note: For information about how to create a disk backup device, see [Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md).</span></span>|  
  
 <span data-ttu-id="5fb21-124">**Ziele auf Band**</span><span class="sxs-lookup"><span data-stu-id="5fb21-124">**Destination on tape**</span></span>  
 <span data-ttu-id="5fb21-125">Gibt ein Sicherungsziel auf einem Bandlaufwerk an, das physisch mit dem Computer verbunden ist, auf dem der Server ausgeführt wird (d. h. die Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="5fb21-125">Specify a backup destination on a tape drive physically connected to the computer running the server (that is, the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)]).</span></span> <span data-ttu-id="5fb21-126">Wählen Sie eine der folgenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="5fb21-126">Choose one of the following options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fb21-127">**Bandlaufwerk**</span><span class="sxs-lookup"><span data-stu-id="5fb21-127">**Tape drive**</span></span>|<span data-ttu-id="5fb21-128">Wählen Sie diese Option aus, um ein Bandlaufwerk als Sicherungsziel aus der Liste der Bandlaufwerke auszuwählen, die physisch mit dem Computer verbunden sind, auf dem die Serverinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fb21-128">Choose this option to select a tape drive as the backup destination from the list of tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="5fb21-129">Hinweis: Bandsicherungsmedien auf Remotecomputern sind keine gültigen Sicherungsziele.</span><span class="sxs-lookup"><span data-stu-id="5fb21-129">Note: Tape backup devices on remote computers are not valid backup destinations.</span></span>|  
|<span data-ttu-id="5fb21-130">**Sicherungsmedium**</span><span class="sxs-lookup"><span data-stu-id="5fb21-130">**Backup device**</span></span>|<span data-ttu-id="5fb21-131">Wählen Sie diese Option aus, um ein vorhandenes logisches Sicherungsmedium auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5fb21-131">Choose this option to select an existing logical backup device.</span></span> <span data-ttu-id="5fb21-132">Diese logischen Sicherungsmedien entsprechen Bandgeräten, die physisch mit dem Computer verbunden sind, auf dem die Serverinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5fb21-132">These logical backup devices correspond to tape drives that are physically connected to the computer that is running the server instance.</span></span><br /><br /> <span data-ttu-id="5fb21-133">Hinweis: Informationen zum Erstellen eines Bandsicherungsmediums finden Sie unter [Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="5fb21-133">Note: For information about how to create a tape backup device, see [Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5fb21-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5fb21-134">See Also</span></span>  
 <span data-ttu-id="5fb21-135">[Sicherungsmedien &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5fb21-135">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="5fb21-136">Mediensätze, Medienfamilien und Sicherungssätze &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5fb21-136">Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;</span></span>](media-sets-media-families-and-backup-sets-sql-server.md)  
  
  
