---
title: MSSQL_ENG021286 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697940"
---
# <a name="mssql_eng021286"></a><span data-ttu-id="8fdeb-102">MSSQL_ENG021286</span><span class="sxs-lookup"><span data-stu-id="8fdeb-102">MSSQL_ENG021286</span></span>
    
## <a name="message-details"></a><span data-ttu-id="8fdeb-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="8fdeb-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fdeb-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8fdeb-104">Product Name</span></span>|<span data-ttu-id="8fdeb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fdeb-105">SQL Server</span></span>|  
|<span data-ttu-id="8fdeb-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8fdeb-106">Event ID</span></span>|<span data-ttu-id="8fdeb-107">21286</span><span class="sxs-lookup"><span data-stu-id="8fdeb-107">21286</span></span>|  
|<span data-ttu-id="8fdeb-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8fdeb-108">Event Source</span></span>|<span data-ttu-id="8fdeb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8fdeb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8fdeb-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8fdeb-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="8fdeb-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8fdeb-111">Symbolic Name</span></span>||  
|<span data-ttu-id="8fdeb-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8fdeb-112">Message Text</span></span>|<span data-ttu-id="8fdeb-113">Die %1!s!-Konflikttabelle ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-113">Conflict table '%s' does not exist.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8fdeb-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8fdeb-114">Explanation</span></span>  
 <span data-ttu-id="8fdeb-115">Dieser Fehler wird ausgelöst, wenn es für einen Artikel in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) keine Konflikttabelle gibt.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-115">This error is raised if the conflict table for an article listed in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) does not actually exist.</span></span> <span data-ttu-id="8fdeb-116">Der Fehler kann bei dem Versuch auftreten, einer Tabelle, die für die Mergereplikation veröffentlicht wurde, eine Spalte hinzuzufügen oder aber eine Spalte aus der Tabelle zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-116">The error can occur when you attempt to add a column to or drop a column from a table published for merge replication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fdeb-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8fdeb-117">User Action</span></span>  
 <span data-ttu-id="8fdeb-118">Führen Sie [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank mit der fehlenden Konflikttabelle aus, um sich zu vergewissern, dass keine Probleme mit der Datenkonsistenz bestehen.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-118">Execute [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database with the missing conflict table to verify there are no data consistency issues.</span></span>  
  
 <span data-ttu-id="8fdeb-119">Wenn die Konflikttabelle auf einem Abonnenten fehlt, sollten Sie das Abonnement löschen und es dann gänzlich neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-119">If the conflict table is missing on a Subscriber, drop the subscription and recreate it.</span></span> <span data-ttu-id="8fdeb-120">Fehlt die Konflikttabelle auf einem Verleger, empfiehlt es sich, alle Abonnements und die Veröffentlichung zu löschen und dann die Veröffentlichung und alle Abonnements neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fdeb-120">If the conflict table is missing on a Publisher, drop all subscriptions, drop the publication, and then recreate the publication and all subscriptions.</span></span> <span data-ttu-id="8fdeb-121">Weitere Informationen finden Sie unter [Veröffentlichen von Daten und Datenbankobjekten](publish/publish-data-and-database-objects.md) und [Abonnieren von Veröffentlichungen](subscribe-to-publications.md).</span><span class="sxs-lookup"><span data-stu-id="8fdeb-121">For more information, see [Publish Data and Database Objects](publish/publish-data-and-database-objects.md) and [Subscribe to Publications](subscribe-to-publications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fdeb-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8fdeb-122">See Also</span></span>  
 [<span data-ttu-id="8fdeb-123">Fehler- und Ereignisreferenz &#40;Replikation&#41;</span><span class="sxs-lookup"><span data-stu-id="8fdeb-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
