---
title: Wiederherstellung fortsetzen | Microsoft-Dokumentation
description: Verwenden Sie in SQL Server das Dialogfeld Wiederherstellung fortsetzen, um anzugeben, ob der nächste Sicherungs Satz wieder hergestellt werden soll.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.continuerestore.f1
ms.assetid: 987ac05f-57c0-49a9-9903-9889717aae4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c7a438ac7b8696d2f57bdf93ff86030cf607e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724105"
---
# <a name="continue-with-restore"></a><span data-ttu-id="f0b05-103">Wiederherstellung fortsetzen</span><span class="sxs-lookup"><span data-stu-id="f0b05-103">Continue with Restore</span></span>
  <span data-ttu-id="f0b05-104">Mithilfe des Dialogfelds **Wiederherstellung fortsetzen** können Sie angeben, ob der nächste Sicherungssatz wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0b05-104">Use the **Continue with Restore** dialog box to indicate whether you want to restore the next backup set.</span></span> <span data-ttu-id="f0b05-105">Zum Verzögern des Wiederherstellungsvorgangs, z. B. zum Wechseln von Bändern, klicken Sie erst dann auf **OK**, wenn der Vorgang fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0b05-105">To delay the restore operation, for example, to swap tapes, wait until you are ready to proceed before you click **OK**.</span></span>  
  
 <span data-ttu-id="f0b05-106">Wenn Sie auf **Nein** klicken, wird die Wiederherstellungssequenz beendet, und die Datenbank bleibt im Wiederherstellungsstatus.</span><span class="sxs-lookup"><span data-stu-id="f0b05-106">Clicking **No** terminates the restore sequence, leaving the database in the restoring state.</span></span> <span data-ttu-id="f0b05-107">Verwenden Sie je nach Bedarf den Task **Datenbank wiederherstellen** oder **Transaktionsprotokoll wiederherstellen** , um die Wiederherstellung zu einem späteren Zeitpunkt fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="f0b05-107">To continue with the restore later, use either the **Restore Database** or **Restore Transaction Log** task, as appropriate.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0b05-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f0b05-108">Options</span></span>  
 <span data-ttu-id="f0b05-109">**Mediensatz**</span><span class="sxs-lookup"><span data-stu-id="f0b05-109">**Media set**</span></span>  
 <span data-ttu-id="f0b05-110">Zeigt den Namen des nächsten Mediensatzes an (sofern verfügbar).</span><span class="sxs-lookup"><span data-stu-id="f0b05-110">Displays the next media set name (if available).</span></span>  
  
 <span data-ttu-id="f0b05-111">**Sicherungs Satz**</span><span class="sxs-lookup"><span data-stu-id="f0b05-111">**Backup set**</span></span>  
 <span data-ttu-id="f0b05-112">Zeigt den Namen des Sicherungssatzes an.</span><span class="sxs-lookup"><span data-stu-id="f0b05-112">Displays the backup set name.</span></span>  
  
 <span data-ttu-id="f0b05-113">**Sicherungs Satz Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0b05-113">**Backup set description**</span></span>  
 <span data-ttu-id="f0b05-114">Zeigt eine Beschreibung des Sicherungssatzes an.</span><span class="sxs-lookup"><span data-stu-id="f0b05-114">Displays the backup set description.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b05-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0b05-115">See Also</span></span>  
 <span data-ttu-id="f0b05-116">[Anzeigen der Inhalte eines Sicherungsbands oder einer -datei &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f0b05-116">[View the Contents of a Backup Tape or File &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span></span>  
 <span data-ttu-id="f0b05-117">[Anzeigen der Eigenschaften und des Inhalts eines logischen Sicherungsmediums &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f0b05-117">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="f0b05-118">[Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="f0b05-118">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="f0b05-119">Wiederherstellen einer Transaktionsprotokollsicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0b05-119">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
  
