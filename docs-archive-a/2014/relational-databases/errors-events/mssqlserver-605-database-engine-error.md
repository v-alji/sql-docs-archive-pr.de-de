---
title: MSSQLSERVER_605 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 605 (Database Engine error)
ms.assetid: d8d3a22e-1ff8-48a4-891f-4c8619437e24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e196fba84af492b25e798629d3e808b1bf22857e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620882"
---
# <a name="mssqlserver_605"></a><span data-ttu-id="9807e-102">MSSQLSERVER_605</span><span class="sxs-lookup"><span data-stu-id="9807e-102">MSSQLSERVER_605</span></span>
    
## <a name="details"></a><span data-ttu-id="9807e-103">Details</span><span class="sxs-lookup"><span data-stu-id="9807e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9807e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="9807e-104">Product Name</span></span>|<span data-ttu-id="9807e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9807e-105">SQL Server</span></span>|  
|<span data-ttu-id="9807e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9807e-106">Event ID</span></span>|<span data-ttu-id="9807e-107">605</span><span class="sxs-lookup"><span data-stu-id="9807e-107">605</span></span>|  
|<span data-ttu-id="9807e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="9807e-108">Event Source</span></span>|<span data-ttu-id="9807e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9807e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9807e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="9807e-110">Component</span></span>|<span data-ttu-id="9807e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9807e-111">SQLEngine</span></span>|  
|<span data-ttu-id="9807e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="9807e-112">Symbolic Name</span></span>|<span data-ttu-id="9807e-113">WRONGPAGE</span><span class="sxs-lookup"><span data-stu-id="9807e-113">WRONGPAGE</span></span>|  
|<span data-ttu-id="9807e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="9807e-114">Message Text</span></span>|<span data-ttu-id="9807e-115">Fehler beim Abrufen der logischen Seite %S_PGID in der %d-Datenbank,</span><span class="sxs-lookup"><span data-stu-id="9807e-115">Attempt to fetch logical page %S_PGID in database %d failed.</span></span> <span data-ttu-id="9807e-116">die nicht zur Zuordnungseinheit %I64d, sondern zu %I64d gehört.</span><span class="sxs-lookup"><span data-stu-id="9807e-116">It belongs to allocation unit %I64d not to %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9807e-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="9807e-117">Explanation</span></span>  
 <span data-ttu-id="9807e-118">Dieser Fehler gibt im Allgemeinen eine Seiten- oder Zuordnungsbeschädigung in der angegebenen Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="9807e-118">This error generally signifies page or allocation corruption in the specified database.</span></span> <span data-ttu-id="9807e-119">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden Beschädigungen erkannt, wenn Seiten gelesen werden. Zu diesem Zweck werden entweder Seitenverknüpfungen verfolgt oder IAM (Index Allocation Map) verwendet.</span><span class="sxs-lookup"><span data-stu-id="9807e-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detects corruption when reading pages belonging to a table either by following the page linkages or by using the Index Allocation Map (IAM).</span></span> <span data-ttu-id="9807e-120">Alle Seiten, die einer Tabelle zugeordnet sind, müssen zu einer der Zuordnungseinheiten gehören, die der Tabelle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9807e-120">All pages allocated to a table must belong to one of the allocation units associated with the table.</span></span> <span data-ttu-id="9807e-121">Wenn die im Seitenkopf enthaltene Zuordnungseinheits-ID nicht mit einer zur Tabelle gehörenden Zuordnungseinheits-ID übereinstimmt, wird diese Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9807e-121">If the allocation unit ID contained in the page header does not match an allocation unit ID associated with the table, this exception is raised.</span></span> <span data-ttu-id="9807e-122">Die erste in der Fehlermeldung aufgeführte Zuordnungseinheits-ID entspricht der im Seitenkopf vorhandenen ID, der zweite Zuordnungseinheitswert entspricht der der Tabelle zugeordneten ID.</span><span class="sxs-lookup"><span data-stu-id="9807e-122">The first allocation unit ID listed in the error message is the ID present in the page header, and the second allocation unit value is the ID associated with the table.</span></span>  
  
 <span data-ttu-id="9807e-123">**Datenbeschädigungsfehler**</span><span class="sxs-lookup"><span data-stu-id="9807e-123">**Data Corruption Errors**</span></span>  
  
 <span data-ttu-id="9807e-124">Mit dem Schweregrad 21 wird eine potenzielle Datenbeschädigung angegeben.</span><span class="sxs-lookup"><span data-stu-id="9807e-124">A severity level of 21 indicates potential data corruption.</span></span> <span data-ttu-id="9807e-125">Zu den möglichen Ursachen zählen eine beschädigte Seitenkette, eine fehlerhafte IAM und ein ungültiger Eintrag in der [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql)-Katalogsicht für dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="9807e-125">Possible causes are a damaged page chain, a corrupt IAM, or an invalid entry in the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view for that object.</span></span> <span data-ttu-id="9807e-126">Diese Fehler werden häufig durch Hardwarefehler oder Festplatten-Gerätetreiberfehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="9807e-126">These errors are often caused by hardware or disk device driver failure.</span></span>  
  
 <span data-ttu-id="9807e-127">**Vorübergehende Fehler**</span><span class="sxs-lookup"><span data-stu-id="9807e-127">**Transient Errors**</span></span>  
  
 <span data-ttu-id="9807e-128">Mit dem Schweregrad 12 wird ein potenzieller vorübergehender Fehler angegeben, das heißt, der Fehler tritt im Cache auf und deutet nicht auf eine Beschädigung von Daten auf dem Datenträger hin.</span><span class="sxs-lookup"><span data-stu-id="9807e-128">A severity level of 12 indicates a potential transient error; that is, it occurs in the cache and does not indicate damage to data on disk.</span></span> <span data-ttu-id="9807e-129">Vorübergehende 605-Fehler können durch folgende Bedingungen verursacht werden:</span><span class="sxs-lookup"><span data-stu-id="9807e-129">Transient 605 errors can be caused by the following conditions:</span></span>  
  
-   <span data-ttu-id="9807e-130">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird vorzeitig vom Betriebssystem benachrichtigt, dass ein E/A-Vorgang abgeschlossen wurde; die Fehlermeldung wird angezeigt, obwohl keine tatsächliche Datenbeschädigung vorliegt.</span><span class="sxs-lookup"><span data-stu-id="9807e-130">The operating system prematurely notifies [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that an I/O operation has completed; the error message is displayed even though no actual data corruption exists.</span></span>  
  
 <span data-ttu-id="9807e-131">Durch das Ausführen einer Abfrage mit dem Optimiererhinweis NOLOCK oder durch das Festlegen der Isolationsstufe für Transaktionen auf READ UNCOMMITTED.</span><span class="sxs-lookup"><span data-stu-id="9807e-131">Running a query with the Optimizer hint NOLOCK or setting the transaction isolation level to READ UNCOMMITTED.</span></span> <span data-ttu-id="9807e-132">Wenn eine Abfrage mit NOLOCK oder READ UNCOMMITTED versucht, Daten zu lesen, die von einem anderen Benutzer verschoben oder geändert werden, tritt der Fehler 605 auf.</span><span class="sxs-lookup"><span data-stu-id="9807e-132">When a query that is using NOLOCK or READ UNCOMMITTED tries to read data that is being moved or changed by another user, a 605 error occurs.</span></span> <span data-ttu-id="9807e-133">Wenn Sie sicherstellen möchten, dass es sich um einen vorübergehenden 605-Fehler handelt, führen Sie die Abfrage später erneut aus.</span><span class="sxs-lookup"><span data-stu-id="9807e-133">To verify that it is a transient 605 error, rerun the query later.</span></span> <span data-ttu-id="9807e-134">Weitere Informationen finden Sie im KB-Artikel [235880](https://support.microsoft.com/kb/235880/en-us): „You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server.“ (Fehlermeldung "Fehler 605" beim Ausführen einer Abfrage mit dem NOLOCK-Optimierungshinweis oder Festlegen der Isolationsstufe für Transaktionen auf READ UNCOMMITTED in SQL Server).</span><span class="sxs-lookup"><span data-stu-id="9807e-134">For more information, see this KB article [235880](https://support.microsoft.com/kb/235880/en-us): "You receive an "Error 605" error message when you run a query with the optimizer hint NOLOCK or you set the transaction isolation level to READ UNCOMMITTED in SQL Server."</span></span>  
  
 <span data-ttu-id="9807e-135">Im Allgemeinen war der Fehler 605 wahrscheinlich vorübergehend, wenn der Fehler während des Datenzugriffs auftritt, nachfolgende DBCC CHECKDB-Vorgänge jedoch ohne Fehler abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9807e-135">In general, if the error occurs during data access but subsequent DBCC CHECKDB operations complete without error, the 605 error was probably transient.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9807e-136">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="9807e-136">User Action</span></span>  
 <span data-ttu-id="9807e-137">Wenn der Fehler 605 nicht vorübergehend auftritt, ist das Problem schwerwiegend und muss behoben werden, indem folgende Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9807e-137">If the 605 error is not transient, the problem is severe and must be corrected by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="9807e-138">Geben Sie die Tabellen an, die den in der Meldung angegebenen Zuordnungseinheiten angehören, indem Sie folgende Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="9807e-138">Identify the tables associated with the allocation units specified in the message by running the following query.</span></span> <span data-ttu-id="9807e-139">Ersetzen Sie `allocation_unit_id` durch die in der Fehlermeldung angegebenen Zuordnungseinheiten.</span><span class="sxs-lookup"><span data-stu-id="9807e-139">Replace `allocation_unit_id` with the allocation units specified in the error message.</span></span>  
  
     <span data-ttu-id="9807e-140">USE`database_name`;</span><span class="sxs-lookup"><span data-stu-id="9807e-140">USE`database_name`;</span></span>  
  
     <span data-ttu-id="9807e-141">GO</span><span class="sxs-lookup"><span data-stu-id="9807e-141">GO</span></span>  
  
     <span data-ttu-id="9807e-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span><span class="sxs-lookup"><span data-stu-id="9807e-142">SELECT au.allocation_unit_id, OBJECT_NAME(p.object_id) AS table_name, fg.name AS filegroup_name,</span></span>  
  
     <span data-ttu-id="9807e-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span><span class="sxs-lookup"><span data-stu-id="9807e-143">au.type_desc AS allocation_type, au.data_pages, partition_number</span></span>  
  
     <span data-ttu-id="9807e-144">FROM sys.allocation_units AS au</span><span class="sxs-lookup"><span data-stu-id="9807e-144">FROM sys.allocation_units AS au</span></span>  
  
     <span data-ttu-id="9807e-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span><span class="sxs-lookup"><span data-stu-id="9807e-145">JOIN sys.partitions AS p ON au.container_id = p.partition_id</span></span>  
  
     <span data-ttu-id="9807e-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span><span class="sxs-lookup"><span data-stu-id="9807e-146">JOIN sys.filegroups AS fg ON fg.data_space_id = au.data_space_id</span></span>  
  
     <span data-ttu-id="9807e-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span><span class="sxs-lookup"><span data-stu-id="9807e-147">WHERE au.allocation_unit_id = `allocation_unit_id` OR au.allocation_unit_id = `allocation_unit_id`</span></span>  
  
     <span data-ttu-id="9807e-148">ORDER BY au.allocation_unit_id;</span><span class="sxs-lookup"><span data-stu-id="9807e-148">ORDER BY au.allocation_unit_id;</span></span>  
  
     <span data-ttu-id="9807e-149">GO</span><span class="sxs-lookup"><span data-stu-id="9807e-149">GO</span></span>  
  
2.  <span data-ttu-id="9807e-150">Führen Sie DBCC CHECKTABLE ohne REPAIR-Klausel für die Tabelle aus, die zur zweiten in der Fehlermeldung angegebenen Zuordnungseinheits-ID gehört.</span><span class="sxs-lookup"><span data-stu-id="9807e-150">Execute DBCC CHECKTABLE without a REPAIR clause on the table associated with the second allocation unit ID specified in the error message.</span></span>  
  
3.  <span data-ttu-id="9807e-151">Führen Sie DBCC CHECKDB ohne REPAIR-Klausel so schnell wie möglich aus, um das vollständige Ausmaß der Beschädigung in der gesamten Datenbank zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9807e-151">Execute DBCC CHECKDB without a REPAIR clause as soon as possible to determine the full extent of the corruption in the entire database.</span></span>  
  
4.  <span data-ttu-id="9807e-152">Sehen Sie im Fehlerprotokoll nach Fehlern, die häufig in Kombination mit dem Fehler 605 auftreten, und prüfen Sie das Windows-Ereignisprotokoll auf system- bzw. hardwarebedingte Probleme.</span><span class="sxs-lookup"><span data-stu-id="9807e-152">Check the error log for other errors that often accompany a 605 error and examine the Windows Event Log for any system or hardware related issues.</span></span> <span data-ttu-id="9807e-153">Beheben Sie alle hardwarebedingten Probleme, die in den Protokollen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9807e-153">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9807e-154">Wenn das Problem nicht hardwarebedingt ist, führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9807e-154">If the problem is not hardware related, perform one of the following tasks:</span></span>  
  
1.  <span data-ttu-id="9807e-155">Stellen Sie die Datenbank von einer bekanntermaßen fehlerfreien Sicherung wieder her.</span><span class="sxs-lookup"><span data-stu-id="9807e-155">Restore the database from a known clean backup.</span></span> <span data-ttu-id="9807e-156">Sie können die Sicherungsfunktion der Seitenwiederherstellung verwenden, um nur die beschädigten Seiten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="9807e-156">You can leverage the page restore backup feature to restore just the damaged pages.</span></span>  
  
2.  <span data-ttu-id="9807e-157">Führen Sie DBCC CHECKDB mit der REPAIR-Klausel aus, die im DBCC CHECKDB-Vorgang empfohlen wurde, der in Schritt 2 zum Beheben der Beschädigung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9807e-157">Run DBCC CHECKDB with the REPAIR clause recommended by the DBCC CHECKDB operation performed in step 3 to repair the corruption.</span></span> <span data-ttu-id="9807e-158">Wenn DBCC CHECKDB mit einer der REPAIR-Klauseln ausgeführt wird und das Problem nicht behebt, wenden Sie sich an Ihren primären Unterstützungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="9807e-158">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span> <span data-ttu-id="9807e-159">Halten Sie die Ausgabe von DBCC CHECKDB zur Überprüfung bereit.</span><span class="sxs-lookup"><span data-stu-id="9807e-159">Have the output from DBCC CHECKDB available for review.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="9807e-160">Wenden Sie sich an Ihren primären Unterstützungsanbieter, bevor Sie diese Anweisung ausführen, wenn Sie nicht sicher sind, inwiefern sich die Verwendung von DBCC CHECKDB mit einer REPAIR-Klausel auf Ihre Daten auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9807e-160">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9807e-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9807e-161">See Also</span></span>  
 [<span data-ttu-id="9807e-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9807e-162">DBCC CHECKTABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checktable-transact-sql)  
  
  
