---
title: MSSQL_REPL020011 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL020011 error
ms.assetid: f72072d7-bbb6-48ad-ac88-afa74aeb4d58
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 646f25740ebb007f8d04a89690d3b712781efcc8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721349"
---
# <a name="mssql_repl020011"></a><span data-ttu-id="0f4b3-102">MSSQL_REPL020011</span><span class="sxs-lookup"><span data-stu-id="0f4b3-102">MSSQL_REPL020011</span></span>
    
## <a name="message-details"></a><span data-ttu-id="0f4b3-103">Meldungsdetails</span><span class="sxs-lookup"><span data-stu-id="0f4b3-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f4b3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0f4b3-104">Product Name</span></span>|<span data-ttu-id="0f4b3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f4b3-105">SQL Server</span></span>|  
|<span data-ttu-id="0f4b3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0f4b3-106">Event ID</span></span>|<span data-ttu-id="0f4b3-107">20011</span><span class="sxs-lookup"><span data-stu-id="0f4b3-107">20011</span></span>|  
|<span data-ttu-id="0f4b3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0f4b3-108">Event Source</span></span>|<span data-ttu-id="0f4b3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0f4b3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0f4b3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0f4b3-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="0f4b3-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0f4b3-111">Symbolic Name</span></span>||  
|<span data-ttu-id="0f4b3-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0f4b3-112">Message Text</span></span>|<span data-ttu-id="0f4b3-113">Der Prozess konnte '%1' nicht auf '%2' ausführen.</span><span class="sxs-lookup"><span data-stu-id="0f4b3-113">The process could not execute '%1' on '%2'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f4b3-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0f4b3-114">Explanation</span></span>  
 <span data-ttu-id="0f4b3-115">Dieser Fehler kann unter verschiedenen Bedingungen während der Transaktionsreplikationsverarbeitung ausgelöst werden, z. B., wenn der Protokolllese-Agent **sp_replcmds** (Der Prozess konnte „sp_replcmds“ nicht auf \<ServerName> ausführen.) oder **sp_repldone** ausführt (Der Prozess konnte „sp_repldone“ nicht auf \<ServerName> ausführen.).</span><span class="sxs-lookup"><span data-stu-id="0f4b3-115">This error can be raised in a number of circumstances during transactional replication processing, such as when the Log Reader Agent executes **sp_replcmds** (The process could not execute 'sp_replcmds' on \<ServerName>) or **sp_repldone** (The process could not execute 'sp_repldone' on \<ServerName>).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f4b3-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0f4b3-116">User Action</span></span>  
 <span data-ttu-id="0f4b3-117">Wenn der Fehler in einer Datenbank ausgelöst wird, die Sie gerade erst aus einer Sicherung wiederhergestellt haben, müssen Sie sicherstellen, dass die in der Dokumentation zum Sichern und Wiederherstellen genannten Schritte ausgeführt wurden. Dazu zählt bei Bedarf auch die Ausführung von **sp_replrestart** .</span><span class="sxs-lookup"><span data-stu-id="0f4b3-117">If this error is raised in a database that you have just restored from a backup, ensure you have followed the steps outlined in the backup and restore documentation, including executing **sp_replrestart** if appropriate.</span></span> <span data-ttu-id="0f4b3-118">Weitere Informationen finden Sie unter [Strategien zum Sichern und Wiederherstellen einer Momentaufnahme- und Transaktionsreplikation](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0f4b3-118">For more information, see [Strategies for Backing Up and Restoring Snapshot and Transactional Replication](administration/strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md).</span></span>  
  
 <span data-ttu-id="0f4b3-119">Bei diesem Fehler handelt es sich um einen internen Verarbeitungsfehler. Wenn er nicht im Zusammenhang mit einer Wiederherstellung ausgelöst wird, weist er in der Regel darauf hin, dass die Replikation entfernt und neu konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="0f4b3-119">This error is an internal processing error and if it is raised in circumstances other than a restore, it typically indicates that replication must be removed and reconfigured.</span></span> <span data-ttu-id="0f4b3-120">Wenn das Entfernen der Replikation nicht möglich ist, wenden Sie sich an den Kundendienst.</span><span class="sxs-lookup"><span data-stu-id="0f4b3-120">If you cannot remove replication, contact customer support for assistance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4b3-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f4b3-121">See Also</span></span>  
 <span data-ttu-id="0f4b3-122">[Fehler- und Ereignisreferenz &#40;Replikation&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="0f4b3-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="0f4b3-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f4b3-123">[sp_replcmds &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-replcmds-transact-sql) </span></span>  
 [<span data-ttu-id="0f4b3-124">sp_repldone &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f4b3-124">sp_repldone &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-repldone-transact-sql)  
  
  
