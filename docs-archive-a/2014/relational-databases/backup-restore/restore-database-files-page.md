---
title: Datenbank wiederherstellen (Seite „Dateien“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoredb.files.f1 in the code
- sql12.swb.restoredb.files.f1
ms.assetid: 714c36ea-a9f9-43a4-99f9-a6f73d1baf8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: edffd9454b51ea80a18311f735d29407f97f6eb6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620460"
---
# <a name="restore-database-files-page"></a><span data-ttu-id="e57a2-102">Datenbank wiederherstellen (Seite Dateien)</span><span class="sxs-lookup"><span data-stu-id="e57a2-102">Restore Database (Files Page)</span></span>
  <span data-ttu-id="e57a2-103">Auf der Seite **Dateien** des Dialogfelds **Datenbank wiederherstellen** können Sie die Dateien verwalten, die Sie für die Wiederherstellung in der Datenbank ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="e57a2-103">Use the **Files** page of the **Restore Database** dialog box to manage the specific files you have chosen to restore within the database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e57a2-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e57a2-104">Options</span></span>  
  
### <a name="restore-database-files-as"></a><span data-ttu-id="e57a2-105">Datenbankdateien wiederherstellen als</span><span class="sxs-lookup"><span data-stu-id="e57a2-105">Restore database files as</span></span>  
 <span data-ttu-id="e57a2-106">Mit dieser Option weisen Sie den wiederhergestellten Dateien den neuen Dateipfad zu und verwalten den Pfad.</span><span class="sxs-lookup"><span data-stu-id="e57a2-106">Use to assign and manage the new file path to the restored files.</span></span>  
  
 <span data-ttu-id="e57a2-107">**Alle Dateien verschieben in Ordner**</span><span class="sxs-lookup"><span data-stu-id="e57a2-107">**Relocate all files to folder**</span></span>  
 <span data-ttu-id="e57a2-108">Wiederhergestellte Dateien werden verschoben.</span><span class="sxs-lookup"><span data-stu-id="e57a2-108">Relocates restored files.</span></span>  
  
|<span data-ttu-id="e57a2-109">Option</span><span class="sxs-lookup"><span data-stu-id="e57a2-109">Option</span></span>|<span data-ttu-id="e57a2-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e57a2-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e57a2-111">**Datendateiordner**</span><span class="sxs-lookup"><span data-stu-id="e57a2-111">**Data file folder**</span></span>|<span data-ttu-id="e57a2-112">Geben Sie den Namen des Datendateiordners ein, in den die wiederhergestellten Datendateien verschoben werden sollen, oder navigieren Sie zu diesem.</span><span class="sxs-lookup"><span data-stu-id="e57a2-112">Enter or search for the data file folder name that the restored data file or files should be relocated to.</span></span>|  
|<span data-ttu-id="e57a2-113">**Protokolldateiordner**</span><span class="sxs-lookup"><span data-stu-id="e57a2-113">**Log file folder**</span></span>|<span data-ttu-id="e57a2-114">Geben Sie den Ordner mit den Protokolldateien ein, in den die wiederhergestellte Protokolldatei verschoben werden soll, oder navigieren Sie zu diesem.</span><span class="sxs-lookup"><span data-stu-id="e57a2-114">Enter or search for the log file or files folder that the restored log file should be relocated to.</span></span>|  
  
 <span data-ttu-id="e57a2-115">**Logischer Dateiname**</span><span class="sxs-lookup"><span data-stu-id="e57a2-115">**Logical File Name**</span></span>  
 <span data-ttu-id="e57a2-116">Zeigt eine Zeile für jede wiederherzustellende Datenbankdatei an.</span><span class="sxs-lookup"><span data-stu-id="e57a2-116">Displays one row for each database file to be restored.</span></span>  
  
 <span data-ttu-id="e57a2-117">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="e57a2-117">**File Type**</span></span>  
 <span data-ttu-id="e57a2-118">Zeigt den Dateityp an.</span><span class="sxs-lookup"><span data-stu-id="e57a2-118">Displays the file type.</span></span>  
  
 <span data-ttu-id="e57a2-119">**Originaldateiname**</span><span class="sxs-lookup"><span data-stu-id="e57a2-119">**Original File Name**</span></span>  
 <span data-ttu-id="e57a2-120">Zeigt den ursprünglichen Dateipfad für die wiederhergestellte Datei an.</span><span class="sxs-lookup"><span data-stu-id="e57a2-120">Displays the original file path for the restored file.</span></span>  
  
 <span data-ttu-id="e57a2-121">**Wiederherstellen als**</span><span class="sxs-lookup"><span data-stu-id="e57a2-121">**Restore As**</span></span>  
 <span data-ttu-id="e57a2-122">Die Dateinamen werden aufgeführt, unter denen die wiederhergestellten Dateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e57a2-122">Lists the file names that the restored files are to be saved as.</span></span> <span data-ttu-id="e57a2-123">Geben Sie den richtigen Dateinamen ein, oder suchen Sie nach diesem.</span><span class="sxs-lookup"><span data-stu-id="e57a2-123">Enter or search for the appropriate file name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57a2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e57a2-124">See Also</span></span>  
 <span data-ttu-id="e57a2-125">[Datenbank wiederherstellen &#40;Seite „Allgemein“&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e57a2-125">[Restore Database &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e57a2-126">[Datenbank wiederherstellen &#40;Seite „Optionen“&#41;](restore-database-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="e57a2-126">[Restore Database &#40;Options Page&#41;](restore-database-options-page.md) </span></span>  
 <span data-ttu-id="e57a2-127">[RESTORE-Argumente &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e57a2-127">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="e57a2-128">[Definieren eines logischen Sicherungsmediums für ein Bandlaufwerk &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e57a2-128">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="e57a2-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e57a2-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
