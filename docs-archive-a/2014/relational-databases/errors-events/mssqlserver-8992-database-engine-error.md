---
title: MSSQLSERVER_8992 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630654"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="619c5-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="619c5-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="619c5-103">Details</span><span class="sxs-lookup"><span data-stu-id="619c5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="619c5-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="619c5-104">Product Name</span></span>|<span data-ttu-id="619c5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="619c5-105">SQL Server</span></span>|  
|<span data-ttu-id="619c5-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="619c5-106">Event ID</span></span>|<span data-ttu-id="619c5-107">8992</span><span class="sxs-lookup"><span data-stu-id="619c5-107">8992</span></span>|  
|<span data-ttu-id="619c5-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="619c5-108">Event Source</span></span>|<span data-ttu-id="619c5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="619c5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="619c5-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="619c5-110">Component</span></span>|<span data-ttu-id="619c5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="619c5-111">SQLEngine</span></span>|  
|<span data-ttu-id="619c5-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="619c5-112">Symbolic Name</span></span>|<span data-ttu-id="619c5-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="619c5-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="619c5-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="619c5-114">Message Text</span></span>|<span data-ttu-id="619c5-115">Meldung ERROR zum Prüfen des Katalogs, Ebene LEVEL, Status STATE: MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="619c5-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="619c5-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="619c5-116">Explanation</span></span>  
 <span data-ttu-id="619c5-117">DBCC CHECKCATALOG oder DBCC CHECKDB hat in den Systemmetadatentabellen eine Inkonsistenz für das angegebene Objekt festgestellt.</span><span class="sxs-lookup"><span data-stu-id="619c5-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="619c5-118">Es handelt sich um eine Inkonsistenz zwischen der aufgezeichneten Objekt-ID und dem in der Fehlermeldung angegebenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="619c5-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="619c5-119">Dieser Fehler kann auftreten, wenn eine oder mehrere Systemtabellen manuell auf eine Weise aktualisiert wurden, die in den Systemmetadaten eine Inkonsistenz verursacht.</span><span class="sxs-lookup"><span data-stu-id="619c5-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="619c5-120">Zum Beispiel hat ein Benutzer möglicherweise manuell ein Objekt aus der Tabelle **sysobjects** gelöscht, ohne die zugeordneten Zeilen in anderen Tabellen, z.B. **sysindexes** und **syscolumns**, zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="619c5-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="619c5-121">Dieser Fehler kann beim Ausführen von DBCC CHECKDB für eine Datenbank auftreten, die von SQL Server 2000 auf SQL Server 2005 oder höher aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="619c5-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="619c5-122">In SQL Server 2000 enthält DBCC CHECKDB die DBCC CHECKCATALOG-Funktion nicht. Deshalb wird der Fehler nicht vor dem Upgrade abgefangen, es sei denn, DBCC CHECKCATALOG wurde ausdrücklich für die Datenbank in SQL Server 2000 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="619c5-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="619c5-123">In Verbindung mit Fehler 8992 werden möglicherweise folgende Fehler angezeigt:</span><span class="sxs-lookup"><span data-stu-id="619c5-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="619c5-124">Meldung 3851 – Eine ungültige Zeile (%ls) wurde in der sys.%ls%ls-Systemtabelle gefunden.</span><span class="sxs-lookup"><span data-stu-id="619c5-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-125">Meldung 3852 – Für die Zeile (%ls) in sys.%ls%ls ist keine entsprechende Zeile (%ls) in sys.%ls%ls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="619c5-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-126">3853 – Für das Attribut (%ls) der Zeile (%ls) in sys.%ls%ls ist keine entsprechende Zeile (%ls) in sys.%ls%ls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="619c5-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-127">3854 – Für das Attribut (%ls) der Zeile (%ls) in sys.%ls%ls ist eine entsprechende Zeile (%ls) in sys.%ls%ls vorhanden, sie ist jedoch ungültig.</span><span class="sxs-lookup"><span data-stu-id="619c5-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="619c5-128">3855 – Das Attribut (%ls) ist ohne eine Zeile (%ls) in sys.%ls%ls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="619c5-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-129">3856 – Das Attribut (%ls) ist fälschlicherweise für die Zeile (%ls) in sys.%ls%ls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="619c5-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-130">3857 – Das Attribut (%ls) ist für die Zeile (%ls) in sys.%ls%ls erforderlich, fehlt jedoch.</span><span class="sxs-lookup"><span data-stu-id="619c5-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="619c5-131">3858 – Das Attribut (%ls) der Zeile (%ls) in sys.%ls%ls weist einen ungültigen Wert auf.</span><span class="sxs-lookup"><span data-stu-id="619c5-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="619c5-132">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="619c5-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="619c5-133">Löschen und Neuerstellen des angegebenen Objekts</span><span class="sxs-lookup"><span data-stu-id="619c5-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="619c5-134">Wenn möglich, löschen Sie das angegebene Objekt, und erstellen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="619c5-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="619c5-135">Wenn das Objekt z. B. eine gespeicherte Prozedur oder ein benutzerdefinierter Typ ist, behebt die Neuerstellung des Objekts möglicherweise das Problem.</span><span class="sxs-lookup"><span data-stu-id="619c5-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="619c5-136">Sicherungswiederherstellung</span><span class="sxs-lookup"><span data-stu-id="619c5-136">Restore from Backup</span></span>  
 <span data-ttu-id="619c5-137">Stellen Sie die Datenbank aus der Sicherung wieder her, wenn das Problem nicht hardwarebezogen ist und eine bekannte intakte Sicherungskopie vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="619c5-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="619c5-138">Diese Aktion ist nur anwendbar, wenn die Sicherung den Metadatenfehler nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="619c5-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="619c5-139">Exportieren der Daten in eine neue Datenbank</span><span class="sxs-lookup"><span data-stu-id="619c5-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="619c5-140">Wenn die Metadateninkonsistenz auch in der Sicherung enthalten ist, müssen Sie eine neue Datenbank erstellen und den Inhalt der vorhandenen Datenbank in die neue Datenbank exportieren.</span><span class="sxs-lookup"><span data-stu-id="619c5-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="619c5-141">Dieser Fehler kann durch DBCC CHECKDB nicht repariert werden</span><span class="sxs-lookup"><span data-stu-id="619c5-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="619c5-142">Dieser Fehler kann nicht repariert werden.</span><span class="sxs-lookup"><span data-stu-id="619c5-142">This error cannot be repaired.</span></span>  <span data-ttu-id="619c5-143">Wenn Sie die Datenbank nicht mithilfe einer Sicherung wiederherstellen können, wenden Sie sich an den Kundenservice und -support von [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="619c5-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="619c5-144">Systemtabellen dürfen nicht manuell aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="619c5-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="619c5-145">Nehmen Sie keine manuellen Updates an den Systemtabellen vor.</span><span class="sxs-lookup"><span data-stu-id="619c5-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="619c5-146">SQL Server unterstützt keine manuellen Änderungen an den Systemdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="619c5-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="619c5-147">Wenn Sie eine Systemtabelle in einer SQL Server-Datenbank aktualisieren, werden zwei Ereignisse (Ereignis-ID 17659 und Ereignis-ID 3859) protokolliert.</span><span class="sxs-lookup"><span data-stu-id="619c5-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="619c5-148">Weitere Informationen finden Sie im KB-Artikel 2688307 "Beim Aktualisieren von Systemtabellen in einer SQL Server-Datenbank werden Ereignis-ID 17659 und Ereignis-ID 3859 protokolliert".</span><span class="sxs-lookup"><span data-stu-id="619c5-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="619c5-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="619c5-149">See Also</span></span>  
 [<span data-ttu-id="619c5-150">Beim Aktualisieren von Systemtabellen in einer SQL Server-Datenbank werden Ereignis-ID 17659 und Ereignis-ID 3859 protokolliert</span><span class="sxs-lookup"><span data-stu-id="619c5-150">Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database</span></span>](https://support.microsoft.com/kb/2688307/EN-US)  
  
  
