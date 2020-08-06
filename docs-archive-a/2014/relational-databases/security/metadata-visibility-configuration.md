---
title: Konfigurieren der Sichtbarkeit von Metadaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618607"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="8a1db-102">Konfigurieren der Sichtbarkeit von Metadaten</span><span class="sxs-lookup"><span data-stu-id="8a1db-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="8a1db-103">Die Sichtbarkeit von Metadaten ist auf sicherungsfähige Elemente eingeschränkt, bei denen der Benutzer entweder der Besitzer ist oder für die dem Benutzer eine Berechtigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a1db-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="8a1db-104">Beispielsweise gibt die folgende Abfrage eine Zeile zurück, wenn dem Benutzer eine Berechtigung, wie etwa SELECT, für die `myTable`-Tabelle erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a1db-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="8a1db-105">Wenn der Benutzer jedoch keine Berechtigungen für `myTable`hat, gibt die Abfrage ein leeres Resultset zurück.</span><span class="sxs-lookup"><span data-stu-id="8a1db-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="8a1db-106">Gültigkeitsbereich und Auswirkung der Konfiguration der Metadatensichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="8a1db-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="8a1db-107">Die Konfiguration der Metadatensichtbarkeit gilt nur für die folgenden sicherungsfähigen Elemente:</span><span class="sxs-lookup"><span data-stu-id="8a1db-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a1db-108">Katalogansichten</span><span class="sxs-lookup"><span data-stu-id="8a1db-108">Catalog views</span></span>|<span data-ttu-id="8a1db-109">gespeicherte [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Prozeduren **sp_help**</span><span class="sxs-lookup"><span data-stu-id="8a1db-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="8a1db-110">Metadaten ausgebende integrierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a1db-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="8a1db-111">Informationsschemasichten</span><span class="sxs-lookup"><span data-stu-id="8a1db-111">Information schema views</span></span>|  
|<span data-ttu-id="8a1db-112">Kompatibilitätssichten</span><span class="sxs-lookup"><span data-stu-id="8a1db-112">Compatibility views</span></span>|<span data-ttu-id="8a1db-113">Erweiterte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8a1db-113">Extended properties</span></span>|  
  
 <span data-ttu-id="8a1db-114">Die Konfiguration der Metadatensichtbarkeit gilt nicht für die folgenden sicherungsfähigen Elemente:</span><span class="sxs-lookup"><span data-stu-id="8a1db-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a1db-115">Protokollversandsystemtabellen</span><span class="sxs-lookup"><span data-stu-id="8a1db-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8a1db-116">-Agents</span><span class="sxs-lookup"><span data-stu-id="8a1db-116">Agent system tables</span></span>|  
|<span data-ttu-id="8a1db-117">Systemtabellen für Datenbank-Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="8a1db-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="8a1db-118">Sicherungssystemtabellen</span><span class="sxs-lookup"><span data-stu-id="8a1db-118">Backup system tables</span></span>|  
|<span data-ttu-id="8a1db-119">Replikationssystemtabellen</span><span class="sxs-lookup"><span data-stu-id="8a1db-119">Replication system tables</span></span>|<span data-ttu-id="8a1db-120">Gespeicherte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sp_help **-Prozeduren für Replikations- und** -Agents</span><span class="sxs-lookup"><span data-stu-id="8a1db-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="8a1db-121">Der eingeschränkte Metadatenzugriff bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8a1db-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="8a1db-122">Anwendungen, die einen **public** -Metadatenzugriff voraussetzen, funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="8a1db-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="8a1db-123">Abfragen für Systemsichten geben möglicherweise nur eine Teilmenge von Zeilen zurück oder manchmal ein leeres Resultset.</span><span class="sxs-lookup"><span data-stu-id="8a1db-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="8a1db-124">Metadaten ausgebende integrierte Funktionen, wie z. B. OBJECTPROPERTYEX, können NULL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8a1db-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="8a1db-125">Die gespeicherten [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Prozeduren **sp_help** geben möglicherweise nur eine Teilmenge von Zeilen oder NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="8a1db-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="8a1db-126">SQL-Module, wie z. B. gespeicherte Prozeduren und Trigger, werden im Sicherheitskontext des Aufrufers ausgeführt und haben deshalb einen eingeschränkten Metadatenzugriff.</span><span class="sxs-lookup"><span data-stu-id="8a1db-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="8a1db-127">Wenn z. B. im folgenden Code die gespeicherte Prozedur versucht, auf Metadaten aus der Tabelle `myTable` zuzugreifen, für die der Aufrufer keine Berechtigung hat, wird ein leeres Resultset zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a1db-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="8a1db-128">In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]wird eine Zeile zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a1db-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="8a1db-129">Um Aufrufern das Anzeigen von Metadaten zu ermöglichen, können Sie ihnen die VIEW DEFINITION-Berechtigung für einen geeigneten Gültigkeitsbereich erteilen: für die Objektebene, für die Datenbankebene oder für die Serverebene.</span><span class="sxs-lookup"><span data-stu-id="8a1db-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="8a1db-130">Wenn der Aufrufer im vorigen Beispiel über die VIEW DEFINITION-Berechtigung für `myTable`verfügt, gibt die gespeicherte Prozedur eine Zeile zurück.</span><span class="sxs-lookup"><span data-stu-id="8a1db-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="8a1db-131">Weitere Informationen finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) und [GRANT (Datenbankberechtigungen)&#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a1db-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="8a1db-132">Sie können die gespeicherte Prozedur auch so ändern, dass sie unter den Anmeldeinformationen des Besitzers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8a1db-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="8a1db-133">Wenn der Besitzer der Prozedur und der Besitzer der Tabelle identisch sind, gilt die Besitzverkettung, und der Sicherheitskontext des Prozedurbesitzers ermöglicht den Zugriff auf die Metadaten von `myTable`.</span><span class="sxs-lookup"><span data-stu-id="8a1db-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="8a1db-134">In diesem Szenario gibt der folgende Code eine Zeile aus Metadaten an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="8a1db-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a1db-135">Das folgende Beispiel verwendet die [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) -Katalogsicht anstelle der [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) -Kompatibilitätssicht.</span><span class="sxs-lookup"><span data-stu-id="8a1db-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="8a1db-136">Sie können EXECUTE AS verwenden, um vorübergehend zum Sicherheitskontext des Aufrufers zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8a1db-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="8a1db-137">Weitere Informationen finden Sie unter [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a1db-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="8a1db-138">Vorteile und Einschränkungen der Konfiguration der Metadatensichtbarkeit</span><span class="sxs-lookup"><span data-stu-id="8a1db-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="8a1db-139">Die Konfiguration der Metadatensichtbarkeit kann eine wichtige Rolle in Ihrem allgemeinen Sicherheitsplan spielen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="8a1db-140">Es gibt jedoch Fälle, in denen ein technisch versierter Benutzer das Anzeigen einiger Metadaten erzwingen kann, wenn er das will.</span><span class="sxs-lookup"><span data-stu-id="8a1db-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="8a1db-141">Wir empfehlen deshalb, dass Sie neben anderen Schutzmaßnahmen Metadatenberechtigungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="8a1db-142">Es ist theoretisch möglich, die Ausgabe von Metadaten in Fehlermeldungen zu erzwingen, indem die Reihenfolge der Prädikatauswertung in Abfragen verändert wird.</span><span class="sxs-lookup"><span data-stu-id="8a1db-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="8a1db-143">Die Möglichkeit solcher *Trial and Error-Angriffe* ist nicht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifisch.</span><span class="sxs-lookup"><span data-stu-id="8a1db-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8a1db-144">Dies wird durch die in relationaler Algebra zulässigen, assoziativen und kommutativen Transformationen impliziert.</span><span class="sxs-lookup"><span data-stu-id="8a1db-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="8a1db-145">Sie können dieses Risiko verringern, indem Sie die in Fehlermeldungen zurückgegebenen Informationen einschränken.</span><span class="sxs-lookup"><span data-stu-id="8a1db-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="8a1db-146">Um die Sichtbarkeit von Metadaten auf diese Weise noch stärker einzuschränken, können Sie den Server mit dem Ablaufverfolgungsflag 3625 starten.</span><span class="sxs-lookup"><span data-stu-id="8a1db-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="8a1db-147">Mit diesem Ablaufverfolgungsflag wird die in Fehlermeldungen angezeigte Menge an Informationen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="8a1db-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="8a1db-148">Auf diese Weise können Sie die erzwungene Anzeige von Daten verhindern.</span><span class="sxs-lookup"><span data-stu-id="8a1db-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="8a1db-149">Der Nachteil hierbei ist jedoch, dass die Fehlermeldungen nicht ausführlich sind und sie u. U. nicht zu Debugzwecken verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8a1db-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="8a1db-150">Weitere Informationen finden Sie unter [Startoptionen für den Datenbank-Engine-Dienst](../../database-engine/configure-windows/database-engine-service-startup-options.md) und [Ablaufverfolgungsflags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a1db-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="8a1db-151">Für die folgenden Metadaten ist die erzwungene Anzeige nicht möglich:</span><span class="sxs-lookup"><span data-stu-id="8a1db-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="8a1db-152">Der in der **provider_string** -Spalte von **sys.servers**gespeicherte Wert.</span><span class="sxs-lookup"><span data-stu-id="8a1db-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="8a1db-153">Ein Benutzer, der keine ALTER ANY LINKED SERVER-Berechtigung hat, sieht in dieser Spalte einen NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="8a1db-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="8a1db-154">Quellendefinition eines benutzerdefinierten Objekts wie z. B. eine gespeicherte Prozedur oder ein Trigger.</span><span class="sxs-lookup"><span data-stu-id="8a1db-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="8a1db-155">Der Quellencode ist nur sichtbar, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8a1db-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="8a1db-156">Der Benutzer hat die VIEW DEFINITION-Berechtigung für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="8a1db-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="8a1db-157">Dem Benutzer wurde nicht die VIEW DEFINITION-Berechtigung für das Objekt verweigert, und er hat die CONTROL-, ALTER- oder TAKE OWNERSHIP-Berechtigung für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="8a1db-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="8a1db-158">Alle anderen Benutzer sehen NULL.</span><span class="sxs-lookup"><span data-stu-id="8a1db-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="8a1db-159">Die Definitionsspalten in den folgenden Katalogsichten:</span><span class="sxs-lookup"><span data-stu-id="8a1db-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="8a1db-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="8a1db-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="8a1db-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="8a1db-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="8a1db-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="8a1db-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="8a1db-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="8a1db-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="8a1db-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="8a1db-164">**sys.default_constraints**</span></span>|<span data-ttu-id="8a1db-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="8a1db-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="8a1db-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="8a1db-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="8a1db-167">Die **ctext** -Spalte in der **syscomments** -Kompatibilitätssicht.</span><span class="sxs-lookup"><span data-stu-id="8a1db-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="8a1db-168">Die Ausgabe der **sp_helptext** -Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8a1db-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="8a1db-169">Die folgenden Spalten in den Informationsschemasichten:</span><span class="sxs-lookup"><span data-stu-id="8a1db-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="8a1db-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="8a1db-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="8a1db-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8a1db-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="8a1db-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8a1db-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="8a1db-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8a1db-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="8a1db-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8a1db-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="8a1db-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8a1db-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="8a1db-176">OBJECT_DEFINITION()-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a1db-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="8a1db-177">Der in der password_hash-Spalte von **sys.sql_logins**gespeicherte Wert.</span><span class="sxs-lookup"><span data-stu-id="8a1db-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="8a1db-178">Einem Benutzer, der nicht über die CONTROL SERVER-Berechtigung verfügt, wird in dieser Spalte ein NULL-Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a1db-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a1db-179">Die SQL-Definitionen von integrierten Systemprozeduren und -funktionen sind über die **sys.system_sql_modules** -Katalogsicht, die gespeicherte Prozedur **sp_helptext** und mithilfe der OBJECT_DEFINITION()-Funktion öffentlich sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8a1db-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="8a1db-180">Allgemeine Prinzipien der Sichtbarkeit von Metadaten</span><span class="sxs-lookup"><span data-stu-id="8a1db-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="8a1db-181">Es folgen einige allgemeine Prinzipien, die im Hinblick auf die Sichtbarkeit von Metadaten beachtet werden müssen:</span><span class="sxs-lookup"><span data-stu-id="8a1db-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="8a1db-182">Feste Rollen und implizite Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8a1db-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="8a1db-183">Geltungsbereich von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8a1db-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="8a1db-184">Vorrang von DENY</span><span class="sxs-lookup"><span data-stu-id="8a1db-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="8a1db-185">Sichtbarkeit der Metadaten von Teilkomponenten</span><span class="sxs-lookup"><span data-stu-id="8a1db-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="8a1db-186">Feste Rollen und implizite Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8a1db-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="8a1db-187">Auf welche Metadaten feste Rollen zugreifen können, richtet sich nach den impliziten Berechtigungen der jeweiligen Rolle.</span><span class="sxs-lookup"><span data-stu-id="8a1db-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="8a1db-188">Geltungsbereich von Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8a1db-188">Scope of Permissions</span></span>  
 <span data-ttu-id="8a1db-189">Berechtigungen in einem Geltungsbereich implizieren die Sichtbarkeit von Metadaten in diesem Geltungsbereich sowie in allen eingeschlossenen Geltungsbereichen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="8a1db-190">So impliziert z. B. die SELECT-Berechtigung für ein Schema, dass der Empfänger dieser Berechtigung die SELECT-Berechtigung auch für alle in diesem Schema enthaltenen sicherungsfähigen Elemente hat.</span><span class="sxs-lookup"><span data-stu-id="8a1db-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="8a1db-191">Das Erteilen der SELECT-Berechtigung für ein Schema ermöglicht deshalb einem Benutzer, die Metadaten des Schemas sowie aller Tabellen, Sichten, Funktionen, Prozeduren, Warteschlangen, Synonyme, Typen und XML-Schemaauflistungen, die im Schema enthalten sind, anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="8a1db-192">Weitere Informationen zu Bereichen finden Sie unter [Berechtigungshierarchie &#40;Datenbank-Engine&#41;](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="8a1db-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="8a1db-193">Vorrang von DENY</span><span class="sxs-lookup"><span data-stu-id="8a1db-193">Precedence of DENY</span></span>  
 <span data-ttu-id="8a1db-194">DENY hat üblicherweise Vorrang vor anderen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="8a1db-195">Wenn einem Datenbankbenutzer z. B. die EXECUTE-Berechtigung für ein Schema erteilt wurde, ihm aber die EXECUTE-Berechtigung für eine gespeicherte Prozedur in diesem Schema verweigert wurde, kann der Benutzer die Metadaten für diese gespeicherte Prozedur nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="8a1db-196">Wenn andererseits einem Benutzer die EXECUTE-Berechtigung für ein Schema verweigert wurde, ihm aber die EXECUTE-Berechtigung für eine gespeicherte Prozedur in diesem Schema erteilt wurde, kann der Benutzer die Metadaten für diese gespeicherte Prozedur nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="8a1db-197">Wenn in einem anderen Beispiel einem Benutzer die EXECUTE-Berechtigung erteilt und verweigert wurde (was über die verschiedenen Rollenmitgliedschaften möglich ist), dann hat DENY Vorrang, und der Benutzer kann die Metadaten für die gespeicherte Prozedur nicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="8a1db-198">Sichtbarkeit der Metadaten von Teilkomponenten</span><span class="sxs-lookup"><span data-stu-id="8a1db-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="8a1db-199">Die Sichtbarkeit von Teilkomponenten wie z. B. Indizes, CHECK-Einschränkungen und Triggern wird durch die Berechtigungen für das übergeordnete Element bestimmt.</span><span class="sxs-lookup"><span data-stu-id="8a1db-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="8a1db-200">Für diese Teilkomponenten gibt es keine erteilbaren Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="8a1db-201">Wenn einem Benutzer z. B. einige Berechtigungen für eine Tabelle erteilt wurden, kann der Benutzer die Metadaten für Tabellen, Spalten, Indizes, CHECK-Einschränkungen, Trigger und andere Teilkomponenten der Tabelle anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a1db-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="8a1db-202">Metadaten, auf die alle Datenbankbenutzer Zugriff haben</span><span class="sxs-lookup"><span data-stu-id="8a1db-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="8a1db-203">Auf einige Metadaten muss der Zugriff durch alle Benutzer in einer bestimmten Datenbank gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="8a1db-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="8a1db-204">So haben z. B. Dateigruppen keine übertragbaren Berechtigungen. Deshalb kann einem Benutzer nicht die Berechtigung zum Zugriff auf die Metadaten einer Dateigruppe erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="8a1db-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="8a1db-205">Allerdings muss jeder Benutzer, der eine Tabelle erstellen kann, auch in der Lage sein, auf die Metadaten der Dateigruppe zuzugreifen, um die ON *filegroup* - oder TEXTIMAGE_ON *filegroup* -Klauseln der CREATE TABLE-Anweisung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8a1db-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="8a1db-206">Die von den Funktionen DB_ID() und DB_NAME() zurückgegebenen Metadaten sind für alle Benutzer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="8a1db-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="8a1db-207">In der folgenden Tabelle sind die Katalogsichten aufgeführt, die für die **public** -Rolle sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="8a1db-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a1db-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="8a1db-208">**sys.partition_functions**</span></span>|<span data-ttu-id="8a1db-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="8a1db-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="8a1db-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="8a1db-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="8a1db-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="8a1db-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="8a1db-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="8a1db-212">**sys.filegroups**</span></span>|<span data-ttu-id="8a1db-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="8a1db-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="8a1db-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="8a1db-214">**sys.database_files**</span></span>|<span data-ttu-id="8a1db-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="8a1db-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="8a1db-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="8a1db-216">**sys.partitions**</span></span>|<span data-ttu-id="8a1db-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="8a1db-217">**sys.messages**</span></span>|  
|<span data-ttu-id="8a1db-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="8a1db-218">**sys.schemas**</span></span>|<span data-ttu-id="8a1db-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="8a1db-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="8a1db-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="8a1db-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="8a1db-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="8a1db-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="8a1db-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="8a1db-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="8a1db-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="8a1db-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a1db-224">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a1db-224">See Also</span></span>  
 <span data-ttu-id="8a1db-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a1db-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="8a1db-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a1db-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="8a1db-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a1db-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="8a1db-228">[EXECUTE AS-Klausel &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a1db-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="8a1db-229">[Katalogsichten &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8a1db-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="8a1db-230">Kompatibilitätssichten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8a1db-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
