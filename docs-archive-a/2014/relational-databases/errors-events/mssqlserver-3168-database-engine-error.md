---
title: MSSQLSERVER_3168 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618023"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="f387e-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="f387e-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="f387e-103">Details</span><span class="sxs-lookup"><span data-stu-id="f387e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f387e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f387e-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="f387e-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f387e-105">Event ID</span></span>|<span data-ttu-id="f387e-106">3168</span><span class="sxs-lookup"><span data-stu-id="f387e-106">3168</span></span>|  
|<span data-ttu-id="f387e-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f387e-107">Event Source</span></span>|<span data-ttu-id="f387e-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f387e-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f387e-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="f387e-109">Component</span></span>|<span data-ttu-id="f387e-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f387e-110">SQLEngine</span></span>|  
|<span data-ttu-id="f387e-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f387e-111">Symbolic Name</span></span>|<span data-ttu-id="f387e-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="f387e-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="f387e-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f387e-113">Message Text</span></span>|<span data-ttu-id="f387e-114">Die Sicherung der Systemdatenbank auf dem Medium %ls kann nicht wiederhergestellt werden, da sie im Vergleich zu dieser Version des Servers (%ls) mit einer anderen Version (%ls) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f387e-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f387e-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f387e-115">Explanation</span></span>  
 <span data-ttu-id="f387e-116">Sie können eine Sicherung einer Systemdatenbank (**master**, **model** oder **msdb**) nicht auf einem Serverbuild wiederherstellen, der sich von dem Build unterscheidet, auf dem die Sicherung ursprünglich vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="f387e-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f387e-117">Durch die Installation eines Service Packs oder eines Hotfixbuilds ändert sich die Serverbuildnummer, und Serverbuilds sind stets inkrementell.</span><span class="sxs-lookup"><span data-stu-id="f387e-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="f387e-118">Mögliche Ursachen</span><span class="sxs-lookup"><span data-stu-id="f387e-118">Possible Causes</span></span>  
 <span data-ttu-id="f387e-119">Das Datenbankschema für Systemdatenbanken kann serverbuildübergreifend geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f387e-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="f387e-120">Damit sichergestellt wird, dass eine Schemaänderung keine Inkonsistenzen verursacht, wird mit der RESTORE-Anweisung die Serverbuildnummer für die Sicherungsdatei mit der Buildnummer des Servers verglichen, auf dem Sie die Sicherung wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f387e-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="f387e-121">Wenn sich die Builds unterscheiden, wird mit der Anweisung die Fehlermeldung 3168 ausgegeben, und der Wiederherstellungsvorgang wird fehlerbedingt beendet.</span><span class="sxs-lookup"><span data-stu-id="f387e-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="f387e-122">Im Folgenden werden Szenarien angegeben, in denen dieses Problem auftreten kann:</span><span class="sxs-lookup"><span data-stu-id="f387e-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="f387e-123">Ein Benutzer versucht, eine Systemdatenbank auf Server A aus einer Sicherung wiederherzustellen, die auf Server B vorgenommen wurde. Server A und Server B befinden sich auf verschiedenen Serverbuilds.</span><span class="sxs-lookup"><span data-stu-id="f387e-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="f387e-124">Server A könnte sich beispielsweise auf der ursprünglichen Buildversion befinden und Server B auf einem Build mit Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="f387e-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="f387e-125">Ein Benutzer versucht, eine Systemdatenbank aus einer Sicherung wiederherzustellen, die auf demselben Server vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="f387e-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="f387e-126">Auf dem Server wurde jedoch ein anderer Build ausgeführt, als die Sicherung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="f387e-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="f387e-127">Das heißt, der Server wurde aktualisiert, seitdem die Sicherung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f387e-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f387e-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f387e-128">User Action</span></span>  
 <span data-ttu-id="f387e-129">Der Wiederherstellungsvorgang gestaltet sich in dieser Situation ziemlich kompliziert und wird nur als letzte Möglichkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="f387e-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="f387e-130">Weitere Informationen finden Sie unter „[Sie können Sicherungen von Systemdatenbanken nicht auf einem anderen Build von SQL Server wiederherstellen](https://support.microsoft.com/kb/264474)“.</span><span class="sxs-lookup"><span data-stu-id="f387e-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f387e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f387e-131">See Also</span></span>  
 [<span data-ttu-id="f387e-132">Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f387e-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
