---
title: Systemdatenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695670"
---
# <a name="system-databases"></a><span data-ttu-id="40c3c-102">Systemdatenbanken</span><span class="sxs-lookup"><span data-stu-id="40c3c-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="40c3c-103">enthält die folgenden Systemdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="40c3c-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="40c3c-104">Systemdatenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-104">System database</span></span>|<span data-ttu-id="40c3c-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40c3c-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="40c3c-106">master-Datenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-106">master Database</span></span>](master-database.md)|<span data-ttu-id="40c3c-107">Zeichnet alle Informationen auf Systemebene für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]auf.</span><span class="sxs-lookup"><span data-stu-id="40c3c-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="40c3c-108">msdb-Datenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="40c3c-109">Wird vom SQL Server-Agent verwendet, um Termine für Warnungen und Aufträge zu planen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="40c3c-110">model-Datenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-110">model Database</span></span>](model-database.md)|<span data-ttu-id="40c3c-111">Wird als Vorlage für alle Datenbanken verwendet, die für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="40c3c-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="40c3c-112">Änderungen, die an der **model** -Datenbank vorgenommen werden, z. B. an der Datenbankgröße, der -sortierung, am Wiederherstellungsmodell und an anderen Datenbankoptionen, werden auf jede Datenbank angewendet, die anschließend erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="40c3c-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="40c3c-113">Ressourcendatenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="40c3c-114">Eine schreibgeschützte Datenbank, die Systemobjekte enthält, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="40c3c-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="40c3c-115">Systemobjekte werden physisch in der **Ressourcendatenbank** gespeichert, logisch jedoch im **sys** -Schema jeder Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="40c3c-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="40c3c-116">tempdb-Datenbank</span><span class="sxs-lookup"><span data-stu-id="40c3c-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="40c3c-117">Ein Arbeitsbereich zum Speichern von temporären Objekten oder Zwischenresultsets.</span><span class="sxs-lookup"><span data-stu-id="40c3c-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="40c3c-118">Ändern von Systemdaten</span><span class="sxs-lookup"><span data-stu-id="40c3c-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="40c3c-119">unterstützt keine direkten Updates der Informationen in Systemobjekten (z. B. Systemtabellen, gespeicherten Systemprozeduren und Katalogsichten) durch Benutzer.</span><span class="sxs-lookup"><span data-stu-id="40c3c-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="40c3c-120">Stattdessen stellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen vollständigen Satz administrativer Tools zur Verfügung, die Benutzern das umfassende Verwalten des Systems sowie aller Benutzer und Objekte in einer Datenbank ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="40c3c-121">Dabei handelt es sich z. B. um:</span><span class="sxs-lookup"><span data-stu-id="40c3c-121">These include the following:</span></span>  
  
-   <span data-ttu-id="40c3c-122">Verwaltungsprogramme, z. B. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40c3c-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="40c3c-123">SQL-SMO-API.</span><span class="sxs-lookup"><span data-stu-id="40c3c-123">SQL-SMO API.</span></span> <span data-ttu-id="40c3c-124">Über diese API können Programmierer vollständige Funktionen zum Verwalten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ihren Anwendungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="40c3c-125">-Skripts und gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="40c3c-125">scripts and stored procedures.</span></span> <span data-ttu-id="40c3c-126">Diese können gespeicherte Systemprozeduren und [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL-Anweisungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="40c3c-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="40c3c-127">Diese Tools schützen Anwendungen vor Änderungen an den Systemobjekten.</span><span class="sxs-lookup"><span data-stu-id="40c3c-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="40c3c-128">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss z. B. in neuen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in einigen Fällen Änderungen an den Systemtabellen durchführen, um neue Funktionen in den jeweiligen Versionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="40c3c-129">Anwendungen, die SELECT-Anweisungen ausgeben, die direkt auf Systemtabellen verweisen, sind häufig auf das alte Format der Systemtabellen angewiesen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="40c3c-130">Standorte können möglicherweise erst dann auf eine neue Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktualisiert werden, nachdem die Anwendungen umgeschrieben wurden, die SELECT-Anweisungen für Systemtabellen ausführen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="40c3c-131">berücksichtigt die durch gespeicherte Systemprozeduren, DDL und SQL-SMO veröffentlichten Schnittstellen, und versucht, die Abwärtskompatibilität dieser Schnittstellen aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="40c3c-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="40c3c-132">stellt keine Unterstützung für Trigger zur Verfügung, die für die Systemtabellen definiert wurden, da durch sie der Systembetrieb verändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="40c3c-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40c3c-133">Systemdatenbanken dürfen nicht in Verzeichnissen von UNC-Freigaben enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="40c3c-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="40c3c-134">Anzeigen von System-Datenbankdaten</span><span class="sxs-lookup"><span data-stu-id="40c3c-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="40c3c-135">Sie sollten keine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen schreiben, von denen die Systemtabellen direkt abgefragt werden, es sei denn, Sie können die von der Anwendung benötigten Informationen nur auf diese Weise abrufen.</span><span class="sxs-lookup"><span data-stu-id="40c3c-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="40c3c-136">Anwendungen sollten Katalog- und Systeminformationen mithilfe der folgenden Mechanismen abrufen:</span><span class="sxs-lookup"><span data-stu-id="40c3c-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="40c3c-137">Systemkatalogsichten</span><span class="sxs-lookup"><span data-stu-id="40c3c-137">System catalog views</span></span>  
  
-   <span data-ttu-id="40c3c-138">SQL-SMO</span><span class="sxs-lookup"><span data-stu-id="40c3c-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="40c3c-139">WMI-Schnittstelle (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation)</span><span class="sxs-lookup"><span data-stu-id="40c3c-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="40c3c-140">Katalogfunktionen, Methoden, Attribute oder Eigenschaften der in der Anwendung verwendeten Daten-API, z. B. ADO, OLE DB oder ODBC</span><span class="sxs-lookup"><span data-stu-id="40c3c-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="40c3c-141">: Gespeicherte Systemprozeduren und integrierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="40c3c-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="40c3c-142">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="40c3c-142">Related Tasks</span></span>  
 [<span data-ttu-id="40c3c-143">Sichern und Wiederherstellen von Systemdatenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40c3c-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="40c3c-144">System Objekte in Objekt-Explorer ausblenden</span><span class="sxs-lookup"><span data-stu-id="40c3c-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="40c3c-145">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="40c3c-145">Related Content</span></span>  
 [<span data-ttu-id="40c3c-146">Katalogsichten &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="40c3c-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="40c3c-147">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="40c3c-147">Databases</span></span>](databases.md)  
  
  
