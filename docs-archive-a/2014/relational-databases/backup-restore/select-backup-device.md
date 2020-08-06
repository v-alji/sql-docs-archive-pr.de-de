---
title: Sicherungsmedium auswählen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721509"
---
# <a name="select-backup-device"></a><span data-ttu-id="244de-102">Sicherungsmedium auswählen</span><span class="sxs-lookup"><span data-stu-id="244de-102">Select Backup Device</span></span>
  <span data-ttu-id="244de-103">Mithilfe des Dialogfelds **Sicherungsmedium auswählen** können Sie ein logisches Sicherungsmedium für die Wiederherstellung auswählen.</span><span class="sxs-lookup"><span data-stu-id="244de-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="244de-104">Ein logisches Sicherungsmedium ist ein benutzerdefiniertes logisches Medium, das einem vom Betriebssystem bereitgestellten physischen Medium, entweder Bandlaufwerk oder Disketten- bzw. Festplattenlaufwerk, entspricht.</span><span class="sxs-lookup"><span data-stu-id="244de-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="244de-105">Wenn eine Sicherung mehrere Sicherungsmedien verwendet, müssen diese alle einem einzigen Medientyp entsprechen.</span><span class="sxs-lookup"><span data-stu-id="244de-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="244de-106">**So verwenden Sie SQL Server Management Studio zum Anzeigen des Inhalts eines Sicherungsmediums**</span><span class="sxs-lookup"><span data-stu-id="244de-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="244de-107">Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="244de-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="244de-108">Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="244de-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="244de-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="244de-109">Options</span></span>  
 <span data-ttu-id="244de-110">**Sicherungsmedium**</span><span class="sxs-lookup"><span data-stu-id="244de-110">**Backup device**</span></span>  
 <span data-ttu-id="244de-111">Wählen Sie im Listenfeld den Namen eines logischen Sicherungsmediums aus, von dem die Wiederherstellung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="244de-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="244de-112">Weitere Informationen zum Anzeigen des Inhalts eines Sicherungsmediums finden Sie unter [Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="244de-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="244de-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="244de-113">Remarks</span></span>  
 <span data-ttu-id="244de-114">Wenn kein logisches Sicherungsmedium in der Liste angezeigt wird, das die gesuchte Sicherung enthält, wurde die Sicherung möglicherweise direkt in eine oder mehrere Dateien oder Bandlaufwerke geschrieben.</span><span class="sxs-lookup"><span data-stu-id="244de-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="244de-115">Schließen Sie in diesem Fall das Dialogfeld **Sicherungsmedium auswählen** , und wählen Sie im Dialogfeld **Sicherung angeben** im Listenfeld **Sicherungsmedium** die Option **Datei** oder **Band** aus.</span><span class="sxs-lookup"><span data-stu-id="244de-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244de-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="244de-116">See Also</span></span>  
 [<span data-ttu-id="244de-117">Sicherungsmedien &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="244de-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
