---
title: Nicht mehr unterstützte Datenbank-Engine Funktionen in SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: release-landing
ms.topic: conceptual
helpviewer_keywords:
- VIA protocol
- unsupported features [SQL Server]
- SQL Mail
- discontinued functionality [SQL Server]
- RESTORE WITH DBO_ONLY
- BACKUP WITH PASSWORD
- user instances enabled
- BACKUP WITH MEDIAPASSWORD
- AWE
- SQL-DMO
- '*= and =*'
- 80 compatibility levels
- COMPUTE BY
- user instance timeout
- sp_dropalias
- COMPUTE
- WITH APPEND
- sys.database_principal_aliases
- sp_dboption
- DATABASEPROPERTY
- FASTFIRSTROW hint
- SET DISABLE_DEF_CNST_CHK
ms.assetid: d686cdf0-d11d-4dba-9ec8-de1a5f189f25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e7fbc371526c4623cf289019b506aa01eb683ad0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701643"
---
# <a name="discontinued-database-engine-functionality-in-sql-server-2014"></a><span data-ttu-id="2097c-102">Nicht mehr unterstützte Datenbank-Engine-Funktionalität in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2097c-102">Discontinued Database Engine Functionality in SQL Server 2014</span></span>
  <span data-ttu-id="2097c-103">In diesem Thema werden die [!INCLUDE[ssDE](../includes/ssde-md.md)] -Funktionen beschrieben, die in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2097c-103">This topic describes the [!INCLUDE[ssDE](../includes/ssde-md.md)] features that are no longer available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
## <a name="discontinued-features-in-sssql14"></a><a name="SQL14"></a><span data-ttu-id="2097c-104">Nicht mehr unterstützte Features[!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2097c-104">Discontinued Features in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="2097c-105">In der folgenden Tabelle sind Funktionen aufgeführt, die nicht mehr in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2097c-105">The following table lists features that were removed in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
|<span data-ttu-id="2097c-106">Category</span><span class="sxs-lookup"><span data-stu-id="2097c-106">Category</span></span>|<span data-ttu-id="2097c-107">Nicht mehr unterstützte Funktion</span><span class="sxs-lookup"><span data-stu-id="2097c-107">Discontinued feature</span></span>|<span data-ttu-id="2097c-108">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="2097c-108">Replacement</span></span>|  
|--------------|--------------------------|-----------------|  
|<span data-ttu-id="2097c-109">Kompatibilitätsgrad</span><span class="sxs-lookup"><span data-stu-id="2097c-109">Compatibility level</span></span>|<span data-ttu-id="2097c-110">Kompatibilitätsgrad 90</span><span class="sxs-lookup"><span data-stu-id="2097c-110">90 compatibility level</span></span>|<span data-ttu-id="2097c-111">Der Kompatibilitätsgrad der Datenbanken muss mindestens auf 100 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2097c-111">Databases must be set to at least compatibility level 100.</span></span> <span data-ttu-id="2097c-112">Wird eine Datenbank mit einem Kompatibilitätsgrad unter 100 auf [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] aktualisiert, wird der Kompatibilitätsgrad der Datenbank während des Upgradevorgangs auf 100 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2097c-112">When a database with a compatibility level of less than 100 is upgraded to [!INCLUDE[ssSQL14](../includes/sssql14-md.md)], the compatibility level of the database is set to 100 during the upgrade operation.</span></span>|  
  
## <a name="discontinued-features-in-sssql11"></a><a name="Denali"></a><span data-ttu-id="2097c-113">Nicht mehr unterstützte Features[!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2097c-113">Discontinued Features in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="2097c-114">In der folgenden Tabelle sind Funktionen aufgeführt, die nicht mehr in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2097c-114">The following table lists features that were removed in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].</span></span>  
  
|<span data-ttu-id="2097c-115">Category</span><span class="sxs-lookup"><span data-stu-id="2097c-115">Category</span></span>|<span data-ttu-id="2097c-116">Nicht mehr unterstützte Funktion</span><span class="sxs-lookup"><span data-stu-id="2097c-116">Discontinued feature</span></span>|<span data-ttu-id="2097c-117">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="2097c-117">Replacement</span></span>|  
|--------------|--------------------------|-----------------|  
|<span data-ttu-id="2097c-118">Sichern und Wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="2097c-118">Backup and Restore</span></span>|<span data-ttu-id="2097c-119">Die **Sicherung von {Database &#124; Log} mit Kennwort** und **Backup {Database &#124; log} with MEDIAPASSWORD** wird eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2097c-119">**BACKUP { DATABASE &#124; LOG } WITH PASSWORD** and **BACKUP { DATABASE &#124; LOG } WITH MEDIAPASSWORD** are discontinued.</span></span> <span data-ttu-id="2097c-120">**Restore {Database &#124; log} with [Media] Password**wird weiterhin als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="2097c-120">**RESTORE { DATABASE &#124; LOG } WITH [MEDIA]PASSWORD**continues to be deprecated.</span></span>|<span data-ttu-id="2097c-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2097c-121">None</span></span>|  
|<span data-ttu-id="2097c-122">Sichern und Wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="2097c-122">Backup and Restore</span></span>|<span data-ttu-id="2097c-123">**{Database &#124; Log} wiederherstellen... mit DBO_ONLY**</span><span class="sxs-lookup"><span data-stu-id="2097c-123">**RESTORE { DATABASE &#124; LOG } ... WITH DBO_ONLY**</span></span>|<span data-ttu-id="2097c-124">**{Database &#124; Log} wiederherstellen...... mit RESTRICTED_USER**</span><span class="sxs-lookup"><span data-stu-id="2097c-124">**RESTORE { DATABASE &#124; LOG } ... ... WITH RESTRICTED_USER**</span></span>|  
|<span data-ttu-id="2097c-125">Kompatibilitätsgrad</span><span class="sxs-lookup"><span data-stu-id="2097c-125">Compatibility level</span></span>|<span data-ttu-id="2097c-126">Kompatibilitätsgrad 80</span><span class="sxs-lookup"><span data-stu-id="2097c-126">80 compatibility level</span></span>|<span data-ttu-id="2097c-127">Der Kompatibilitätsgrad der Datenbanken muss mindestens auf 90 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2097c-127">Databases must be set to at least compatibility level 90.</span></span>|  
|<span data-ttu-id="2097c-128">Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="2097c-128">Configuration Options</span></span>|<span data-ttu-id="2097c-129">`sp_configure 'user instance timeout'` und `'user instances enabled'`</span><span class="sxs-lookup"><span data-stu-id="2097c-129">`sp_configure 'user instance timeout'` and `'user instances enabled'`</span></span>|<span data-ttu-id="2097c-130">Verwenden Sie die Funktion Lokale Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2097c-130">Use the Local Database feature.</span></span> <span data-ttu-id="2097c-131">Weitere Informationen finden Sie unter [sqllocaldb-Hilfsprogramm](../tools/sqllocaldb-utility.md) .</span><span class="sxs-lookup"><span data-stu-id="2097c-131">For more information, see [SqlLocalDB Utility](../tools/sqllocaldb-utility.md)</span></span>|  
|<span data-ttu-id="2097c-132">Verbindungsprotokolle</span><span class="sxs-lookup"><span data-stu-id="2097c-132">Connection protocols</span></span>|<span data-ttu-id="2097c-133">Die Unterstützung für das VIA-Protokoll wird eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2097c-133">Support for the VIA protocol is discontinued.</span></span>|<span data-ttu-id="2097c-134">Verwenden Sie stattdessen TCP.</span><span class="sxs-lookup"><span data-stu-id="2097c-134">Use TCP instead.</span></span>|  
|<span data-ttu-id="2097c-135">Datenbankobjekte</span><span class="sxs-lookup"><span data-stu-id="2097c-135">Database objects</span></span>|<span data-ttu-id="2097c-136">`WITH APPEND`-Klausel für Trigger</span><span class="sxs-lookup"><span data-stu-id="2097c-136">`WITH APPEND` clause on triggers</span></span>|<span data-ttu-id="2097c-137">Erstellen Sie den ganzen Trigger neu.</span><span class="sxs-lookup"><span data-stu-id="2097c-137">Re-create the whole trigger.</span></span>|  
|<span data-ttu-id="2097c-138">Datenbankoptionen</span><span class="sxs-lookup"><span data-stu-id="2097c-138">Database options</span></span>|`sp_dboption`|`ALTER DATABASE`|  
|<span data-ttu-id="2097c-139">Mail</span><span class="sxs-lookup"><span data-stu-id="2097c-139">Mail</span></span>|<span data-ttu-id="2097c-140">SQL Mail</span><span class="sxs-lookup"><span data-stu-id="2097c-140">SQL Mail</span></span>|<span data-ttu-id="2097c-141">Verwenden Sie Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="2097c-141">Use Database Mail.</span></span> <span data-ttu-id="2097c-142">Weitere Informationen finden Sie unter [Datenbank-E-Mail](../relational-databases/database-mail/database-mail.md) und [Verwenden von Datenbank-E-Mail anstelle von SQL Mail](../relational-databases/policy-based-management/use-database-mail-instead-of-sql-mail.md).</span><span class="sxs-lookup"><span data-stu-id="2097c-142">For more information, see [Database Mail](../relational-databases/database-mail/database-mail.md) and  [Use Database Mail Instead of SQL Mail](../relational-databases/policy-based-management/use-database-mail-instead-of-sql-mail.md).</span></span>|  
|<span data-ttu-id="2097c-143">Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="2097c-143">Memory Management</span></span>|<span data-ttu-id="2097c-144">Unterstützung für 32-Bit-AWE (Address Windowing Extensions) und für das Hinzufügen von 32-Bit-Speicher im laufenden Systembetrieb (Hot Add Memory).</span><span class="sxs-lookup"><span data-stu-id="2097c-144">32-bit Address Windowing Extensions (AWE) and 32-bit Hot Add memory support.</span></span>|<span data-ttu-id="2097c-145">Verwenden Sie ein 64-Bit-Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="2097c-145">Use a 64-bit operating system.</span></span>|  
|<span data-ttu-id="2097c-146">Metadaten</span><span class="sxs-lookup"><span data-stu-id="2097c-146">Metadata</span></span>|`DATABASEPROPERTY`|`DATABASEPROPERTYEX`|  
|<span data-ttu-id="2097c-147">Programmierbarkeit</span><span class="sxs-lookup"><span data-stu-id="2097c-147">Programmability</span></span>|<span data-ttu-id="2097c-148">SQL Server-Distributed Management Objects (SQL-DMO)</span><span class="sxs-lookup"><span data-stu-id="2097c-148">SQL Server Distributed Management Objects (SQL-DMO)</span></span>|<span data-ttu-id="2097c-149">SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="2097c-149">SQL Server Management Objects (SMO)</span></span>|  
|<span data-ttu-id="2097c-150">Abfragehinweise</span><span class="sxs-lookup"><span data-stu-id="2097c-150">Query hints</span></span>|<span data-ttu-id="2097c-151">`FASTFIRSTROW`-Hinweis</span><span class="sxs-lookup"><span data-stu-id="2097c-151">`FASTFIRSTROW` hint</span></span>|<span data-ttu-id="2097c-152">`OPTION (FAST`*n* `)` .</span><span class="sxs-lookup"><span data-stu-id="2097c-152">`OPTION (FAST` *n* `)`.</span></span>|  
|<span data-ttu-id="2097c-153">Remoteserver</span><span class="sxs-lookup"><span data-stu-id="2097c-153">Remote servers</span></span>|<span data-ttu-id="2097c-154">Das Erstellen neuer Remoteserver durch Benutzer mithilfe von `sp_addserver` wird eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2097c-154">The ability for users to create new remote servers by using `sp_addserver` is discontinued.</span></span> <span data-ttu-id="2097c-155">`sp_addserver` mit der Option "local" bleibt erhalten.</span><span class="sxs-lookup"><span data-stu-id="2097c-155">`sp_addserver` with the 'local' option remains available.</span></span> <span data-ttu-id="2097c-156">Während des Upgrades beibehaltene oder durch Replikation erstellte Remoteserver können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2097c-156">Remote servers preserved during upgrade or created by replication can be used.</span></span>|<span data-ttu-id="2097c-157">Ersetzen Sie Remoteserver mithilfe von Verbindungsservern.</span><span class="sxs-lookup"><span data-stu-id="2097c-157">Replace remote servers by using linked servers.</span></span>|  
|<span data-ttu-id="2097c-158">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2097c-158">Security</span></span>|`sp_dropalias`|<span data-ttu-id="2097c-159">Ersetzen Sie Aliase durch eine Kombination von Benutzerkonten und Datenbankrollen.</span><span class="sxs-lookup"><span data-stu-id="2097c-159">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="2097c-160">Verwenden Sie `sp_dropalias`, um Aliase in aktualisierten Datenbanken zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2097c-160">Use `sp_dropalias` to remove aliases in upgraded databases.</span></span>|  
|<span data-ttu-id="2097c-161">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2097c-161">Security</span></span>|<span data-ttu-id="2097c-162">Der Versions Parameter von **PWDCOMPARE** , der einen Wert aus einer Anmeldung vor 2000 darstellt, wird nicht mehr unterstützt [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2097c-162">The version parameter of **PWDCOMPARE** representing a value from a login earlier than [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] 2000 is discontinued.</span></span>|<span data-ttu-id="2097c-163">Keine</span><span class="sxs-lookup"><span data-stu-id="2097c-163">None</span></span>|  
|<span data-ttu-id="2097c-164">Service Broker-Programmierbarkeit in SMO</span><span class="sxs-lookup"><span data-stu-id="2097c-164">Service Broker programmability in SMO</span></span>|<span data-ttu-id="2097c-165">Die **Microsoft. SqlServer. Management. Smo. Broker. brokerpriority** -Klasse implementiert nicht mehr die **Microsoft. SqlServer. Management. Smo. iobjectberechtigungs** -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2097c-165">The **Microsoft.SqlServer.Management.Smo.Broker.BrokerPriority** class no longer implements the **Microsoft.SqlServer.Management.Smo.IObjectPermission** interface.</span></span>||  
|<span data-ttu-id="2097c-166">SET-Optionen</span><span class="sxs-lookup"><span data-stu-id="2097c-166">SET options</span></span>|`SET DISABLE_DEF_CNST_CHK`|<span data-ttu-id="2097c-167">Keine.</span><span class="sxs-lookup"><span data-stu-id="2097c-167">None.</span></span>|  
|<span data-ttu-id="2097c-168">Systemtabellen</span><span class="sxs-lookup"><span data-stu-id="2097c-168">System tables</span></span>|<span data-ttu-id="2097c-169">sys.database_principal_aliases</span><span class="sxs-lookup"><span data-stu-id="2097c-169">sys.database_principal_aliases</span></span>|<span data-ttu-id="2097c-170">Verwenden Sie anstelle von Aliasen Rollen.</span><span class="sxs-lookup"><span data-stu-id="2097c-170">Use roles instead of aliases.</span></span>|  
|<span data-ttu-id="2097c-171">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2097c-171">Transact-SQL</span></span>|<span data-ttu-id="2097c-172">`RAISERROR` im Format `RAISERROR integer 'string'` wird eingestellt.</span><span class="sxs-lookup"><span data-stu-id="2097c-172">`RAISERROR` in the format `RAISERROR integer 'string'` is discontinued.</span></span>|<span data-ttu-id="2097c-173">Schreiben Sie die Anweisung mithilfe der aktuellen **RAISERROR (...)** -Syntax um.</span><span class="sxs-lookup"><span data-stu-id="2097c-173">Rewrite the statement using the current **RAISERROR(...)** syntax.</span></span>|  
|<span data-ttu-id="2097c-174">Transact-SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="2097c-174">Transact-SQL syntax</span></span>|`COMPUTE / COMPUTE BY`|<span data-ttu-id="2097c-175">Verwenden Sie `ROLLUP`</span><span class="sxs-lookup"><span data-stu-id="2097c-175">Use `ROLLUP`</span></span>|  
|<span data-ttu-id="2097c-176">Transact-SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="2097c-176">Transact-SQL syntax</span></span>|<span data-ttu-id="2097c-177">Verwendung von **\*=** und **=&#42;**</span><span class="sxs-lookup"><span data-stu-id="2097c-177">Use of **\*=** and **=&#42;**</span></span>|<span data-ttu-id="2097c-178">Verwenden Sie die ANSI-Joinsyntax.</span><span class="sxs-lookup"><span data-stu-id="2097c-178">Use ANSI join syntax.</span></span> <span data-ttu-id="2097c-179">Weitere Informationen finden Sie unter [from (Transact-SQL).](https://msdn.microsoft.com/library/ms177634\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2097c-179">For more information, see [FROM (Transact-SQL).](https://msdn.microsoft.com/library/ms177634\(SQL.105\).aspx)</span></span>|  
|<span data-ttu-id="2097c-180">XEvents</span><span class="sxs-lookup"><span data-stu-id="2097c-180">XEvents</span></span>|<span data-ttu-id="2097c-181">databases_data_file_size_changed, databases_log_file_size_changed</span><span class="sxs-lookup"><span data-stu-id="2097c-181">databases_data_file_size_changed, databases_log_file_size_changed</span></span><br /><br /> <span data-ttu-id="2097c-182">eventdatabases_log_file_used_size_changed</span><span class="sxs-lookup"><span data-stu-id="2097c-182">eventdatabases_log_file_used_size_changed</span></span><br /><br /> <span data-ttu-id="2097c-183">locks_lock_timeouts_greater_than_0</span><span class="sxs-lookup"><span data-stu-id="2097c-183">locks_lock_timeouts_greater_than_0</span></span><br /><br /> <span data-ttu-id="2097c-184">locks_lock_timeouts</span><span class="sxs-lookup"><span data-stu-id="2097c-184">locks_lock_timeouts</span></span>|<span data-ttu-id="2097c-185">Ersetzt durch database_file_size_change event, database_file_size_change</span><span class="sxs-lookup"><span data-stu-id="2097c-185">Replaced by database_file_size_change event, database_file_size_change</span></span><br /><br /> <span data-ttu-id="2097c-186">database_file_size_change-Ereignis</span><span class="sxs-lookup"><span data-stu-id="2097c-186">database_file_size_change event</span></span><br /><br /> <span data-ttu-id="2097c-187">lock_timeout_greater_than_0</span><span class="sxs-lookup"><span data-stu-id="2097c-187">lock_timeout_greater_than_0</span></span><br /><br /> <span data-ttu-id="2097c-188">lock_timeout</span><span class="sxs-lookup"><span data-stu-id="2097c-188">lock_timeout</span></span>|  
  
 <span data-ttu-id="2097c-189">**Zusätzliche XEvent-Änderungen**</span><span class="sxs-lookup"><span data-stu-id="2097c-189">**Additional XEvent changes**</span></span>  
  
 <span data-ttu-id="2097c-190">**resource_monitor_ring_buffer_record**:</span><span class="sxs-lookup"><span data-stu-id="2097c-190">**resource_monitor_ring_buffer_record**:</span></span>  
  
-   <span data-ttu-id="2097c-191">Entfernte Felder: single_pages_kb, multiple_pages_kb</span><span class="sxs-lookup"><span data-stu-id="2097c-191">Fields removed: single_pages_kb, multiple_pages_kb</span></span>  
  
-   <span data-ttu-id="2097c-192">Hinzugefügte Felder: target_kb, pages_kb</span><span class="sxs-lookup"><span data-stu-id="2097c-192">Fields added: target_kb, pages_kb</span></span>  
  
 <span data-ttu-id="2097c-193">**memory_node_oom_ring_buffer_recorded**:</span><span class="sxs-lookup"><span data-stu-id="2097c-193">**memory_node_oom_ring_buffer_recorded**:</span></span>  
  
-   <span data-ttu-id="2097c-194">Entfernte Felder: single_pages_kb, multiple_pages_kb</span><span class="sxs-lookup"><span data-stu-id="2097c-194">Fields removed: single_pages_kb, multiple_pages_kb</span></span>  
  
-   <span data-ttu-id="2097c-195">Hinzugefügte Felder: target_kb, pages_kb</span><span class="sxs-lookup"><span data-stu-id="2097c-195">Fields added: target_kb, pages_kb</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2097c-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2097c-196">See Also</span></span>  
 [<span data-ttu-id="2097c-197">Als veraltet markierte Funktionen der Datenbank-Engine in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="2097c-197">Deprecated Database Engine Features in SQL Server 2014</span></span>](deprecated-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  