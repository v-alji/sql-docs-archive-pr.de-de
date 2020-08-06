---
title: MSSQLSERVER_1457 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620957"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="eb0b9-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="eb0b9-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="eb0b9-103">Details</span><span class="sxs-lookup"><span data-stu-id="eb0b9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb0b9-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="eb0b9-104">Product Name</span></span>|<span data-ttu-id="eb0b9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb0b9-105">SQL Server</span></span>|  
|<span data-ttu-id="eb0b9-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="eb0b9-106">Event ID</span></span>|<span data-ttu-id="eb0b9-107">1457</span><span class="sxs-lookup"><span data-stu-id="eb0b9-107">1457</span></span>|  
|<span data-ttu-id="eb0b9-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="eb0b9-108">Event Source</span></span>|<span data-ttu-id="eb0b9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eb0b9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eb0b9-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="eb0b9-110">Component</span></span>|<span data-ttu-id="eb0b9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eb0b9-111">SQLEngine</span></span>|  
|<span data-ttu-id="eb0b9-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="eb0b9-112">Symbolic Name</span></span>|<span data-ttu-id="eb0b9-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="eb0b9-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="eb0b9-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="eb0b9-114">Message Text</span></span>|<span data-ttu-id="eb0b9-115">Die Synchronisierung der '%.\*ls'-Spiegeldatenbank wurde unterbrochen, und die Datenbank weist nun einen inkonsistenten Status auf.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="eb0b9-116">Der ALTER DATABASE-Befehl ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="eb0b9-117">Stellen Sie sicher, dass die Spiegeldatenbank wieder online ist. Stellen Sie dann erneut eine Verbindung mit der Spiegelserverinstanz her, und warten Sie, bis die Synchronisierung der Spiegeldatenbank beendet ist.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eb0b9-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="eb0b9-118">Explanation</span></span>  
 <span data-ttu-id="eb0b9-119">Mit dieser Meldung wird angegeben, dass mit der ALTER DATABASE *Datenbank_Name* SET PARTNER OFF-Anweisung ein Fehler ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="eb0b9-120">Durch den Fehler beim Versuch, die Datenbankspiegelung zu entfernen, wurde die Synchronisierung der Spiegeldatenbank unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="eb0b9-121">Die Datenbank weist nun einen inkonsistenten Status auf.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eb0b9-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="eb0b9-122">User Action</span></span>  
 <span data-ttu-id="eb0b9-123">So können Sie diesen Fehler mit einer der folgenden Aktionen beheben:</span><span class="sxs-lookup"><span data-stu-id="eb0b9-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="eb0b9-124">Stellen Sie die Verbindung zwischen dem Spiegelserver und dem Prinzipalserver wieder her, um eine Synchronisierung der Spiegeldatenbank zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="eb0b9-125">Löschen Sie die Spiegeldatenbank.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="eb0b9-126">Nach dem Löschvorgang können Sie aus den Sicherungen eine neue Spiegeldatenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb0b9-127">Solange die Spiegelung noch aktiviert ist, können Sie die Spiegeldatenbank nur nach einem Fehler bei der SET PARTNER OFF-Anweisung löschen.</span><span class="sxs-lookup"><span data-stu-id="eb0b9-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0b9-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb0b9-128">See Also</span></span>  
 <span data-ttu-id="eb0b9-129">[Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb0b9-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="eb0b9-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb0b9-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="eb0b9-131">[Einrichten der Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb0b9-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="eb0b9-132">[Entfernen der Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb0b9-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="eb0b9-133">Vorbereiten einer Spiegeldatenbank auf die Spiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb0b9-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
