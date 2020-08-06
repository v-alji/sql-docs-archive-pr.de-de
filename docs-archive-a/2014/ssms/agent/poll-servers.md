---
title: Abfragen von Servern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619536"
---
# <a name="poll-servers"></a><span data-ttu-id="7d348-102">Abfragen von Servern</span><span class="sxs-lookup"><span data-stu-id="7d348-102">Poll Servers</span></span>
  <span data-ttu-id="7d348-103">Wenn die Multiserververwaltung implementiert ist, stellen die Zielserver regelmäßig eine Verbindung mit dem Masterserver her, um Informationen zu ausgeführten Aufträgen hochzuladen und neue Aufträge herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7d348-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="7d348-104">Der Vorgang der Verbindungsherstellung mit dem Masterserver wird als *Serverabruf* bezeichnet und findet in regelmäßigen *Abrufintervallen*statt.</span><span class="sxs-lookup"><span data-stu-id="7d348-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="7d348-105">Abrufintervalle</span><span class="sxs-lookup"><span data-stu-id="7d348-105">Polling Intervals</span></span>  
 <span data-ttu-id="7d348-106">Das Abrufintervall (standardmäßig eine Minute) steuert, wie oft der Zielserver eine Verbindung mit dem Masterserver herstellt, um Anweisungen herunterzuladen und die Ergebnisse der Auftragsausführung hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="7d348-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="7d348-107">Wenn ein Zielserver den Masterserver abruft, liest er die dem Zielserver zugewiesenen Vorgänge aus der **sysdownloadlist** -Tabelle in der **msdb** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="7d348-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="7d348-108">Diese Operationen steuern Multiserveraufträge sowie verschiedene Aspekte des Verhaltens eines Zielservers.</span><span class="sxs-lookup"><span data-stu-id="7d348-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="7d348-109">Dazu gehören beispielsweise das Löschen, Einfügen oder Starten eines Auftrags und das Aktualisieren des Abrufintervalls eines Zielservers.</span><span class="sxs-lookup"><span data-stu-id="7d348-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="7d348-110">Vorgänge werden in der **sysdownloadlist** -Tabelle auf eine der folgenden Arten bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="7d348-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="7d348-111">Explizit durch Verwenden der gespeicherten Prozedur **sp_post_msx_operation** .</span><span class="sxs-lookup"><span data-stu-id="7d348-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="7d348-112">Implizit durch Verwenden anderer gespeicherter Auftragsprozeduren.</span><span class="sxs-lookup"><span data-stu-id="7d348-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="7d348-113">Wenn Sie gespeicherte Auftragsprozeduren zum Ändern von Multiserver-Auftragszeitplänen oder Multiserverauftragsschritten bzw. von SQL-DMO-Objekten (SQL Distributed Management Objects) zum Steuern von Multiserveraufträgen verwenden, geben Sie den folgenden Befehl nach dem Ändern der Multiserverauftragsschritte oder Multiserver-Auftragszeitpläne aus:</span><span class="sxs-lookup"><span data-stu-id="7d348-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="7d348-114">Durch die Ausgabe dieses Befehls bleiben die Zielserver mit der aktuellen Auftragsdefinition synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="7d348-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="7d348-115">Es ist nicht notwendig, Vorgänge explizit bereitzustellen, wenn Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d348-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="7d348-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zum Steuern von Multiserveraufträgen.</span><span class="sxs-lookup"><span data-stu-id="7d348-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="7d348-117">Gespeicherte Auftragsprozeduren, die weder Auftragszeitpläne noch Auftragsschritte ändern.</span><span class="sxs-lookup"><span data-stu-id="7d348-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="7d348-118">**So erzwingen Sie, dass ein Zielserver den Masterserver abruft**</span><span class="sxs-lookup"><span data-stu-id="7d348-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="7d348-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d348-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="7d348-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d348-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="7d348-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d348-121">See Also</span></span>  
 [<span data-ttu-id="7d348-122">Verwalten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="7d348-122">Manage Events</span></span>](manage-events.md)  
  
  
