---
title: Andere Datenbank-Engine Upgradeprobleme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615767"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="96cac-102">Weitere Probleme beim Upgrade der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="96cac-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="96cac-103">Die folgenden Upgradeprobleme können von der aktuellen Version von Upgrade Advisor nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="96cac-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="96cac-104">Überprüfen Sie die nachfolgend aufgeführten Probleme, um ihre potenziellen Auswirkungen auf Ihre Systeme zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="96cac-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="96cac-105">Mehrere Funktionen der Datenbank-Engine veraltet</span><span class="sxs-lookup"><span data-stu-id="96cac-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="96cac-106">Die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen oder -Optionen sind veraltet:</span><span class="sxs-lookup"><span data-stu-id="96cac-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="96cac-107">NO_LOG-Option und TRUNCATE_ONLY-Option von BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="96cac-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="96cac-108">BACKUP TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="96cac-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="96cac-109">RESTORE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="96cac-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="96cac-110">DUMP</span><span class="sxs-lookup"><span data-stu-id="96cac-110">DUMP</span></span>  
  
-   <span data-ttu-id="96cac-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="96cac-111">LOAD</span></span>  
  
-   <span data-ttu-id="96cac-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="96cac-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="96cac-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="96cac-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="96cac-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="96cac-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="96cac-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="96cac-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="96cac-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="96cac-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="96cac-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="96cac-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="96cac-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="96cac-118">syssegments</span></span>  
  
 <span data-ttu-id="96cac-119">Die Verwendung des VIA-Protokolls zum Herstellen einer Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="96cac-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="96cac-120">Neue Datentypen</span><span class="sxs-lookup"><span data-stu-id="96cac-120">New Data Types</span></span>  
 <span data-ttu-id="96cac-121">Die folgenden Systemtypen sind reserviert.</span><span class="sxs-lookup"><span data-stu-id="96cac-121">The following will be reserved system types.</span></span> <span data-ttu-id="96cac-122">Benennen Sie vorhandene, miteinander in Konflikt stehende benutzerdefinierte Typen vor oder nach dem Upgrade um.</span><span class="sxs-lookup"><span data-stu-id="96cac-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="96cac-123">Geografie</span><span class="sxs-lookup"><span data-stu-id="96cac-123">Geography</span></span>  
  
-   <span data-ttu-id="96cac-124">Geometrie</span><span class="sxs-lookup"><span data-stu-id="96cac-124">Geometry</span></span>  
  
-   <span data-ttu-id="96cac-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="96cac-125">Datetime2</span></span>  
  
-   <span data-ttu-id="96cac-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="96cac-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="96cac-127">Die Zieltabelle der OUTPUT INTO-Klausel kann keine definierten Trigger enthalten</span><span class="sxs-lookup"><span data-stu-id="96cac-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="96cac-128">Ausgabe in eine Ziel Tabelle, wenn die Tabelle über aktivierte Trigger verfügt, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96cac-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="96cac-129">Kompilieren von Zeitfehlern für UDFs, wenn das Ziel einer OUTPUT INTO-Klausel eine Tabelle ist</span><span class="sxs-lookup"><span data-stu-id="96cac-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="96cac-130">Mit benutzerdefinierten Funktionen (UDFs) können keine Aktionen ausgeführt werden, die den Status einer Datenbank ändern.</span><span class="sxs-lookup"><span data-stu-id="96cac-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="96cac-131">Beispielsweise kann ein UDF keine DDL-Aktionen (CREATE/ALTER/DROP) oder DML-Aktionen (INSERT/UPDATE/DELETE) für Objekte ausführen, ausgenommen für Tabellenvariablen.</span><span class="sxs-lookup"><span data-stu-id="96cac-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="96cac-132">MERGE ist ein reserviertes Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="96cac-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="96cac-133">MERGE ist jetzt ein vollständig reserviertes Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="96cac-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="96cac-134">Anwendungen dürfen nicht länger Objekte (Tabellen, Spalten usw.) mit dem Namen MERGE enthalten.</span><span class="sxs-lookup"><span data-stu-id="96cac-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="96cac-135">Umbenennen des CDC-Schemas</span><span class="sxs-lookup"><span data-stu-id="96cac-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="96cac-136">Es ist ein Schemaname mit dem Namen CDC vorhanden.</span><span class="sxs-lookup"><span data-stu-id="96cac-136">There is a schema name called CDC.</span></span> <span data-ttu-id="96cac-137">Dieser Schema Name kann nicht verwendet werden, wenn **Change Data Capture** für die Datenbank aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="96cac-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="96cac-138">Sie müssen das CDC-Schema löschen, bevor Sie **Change Data Capture** für die Datenbank aktivieren.</span><span class="sxs-lookup"><span data-stu-id="96cac-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="96cac-139">Dieser Schritt kann vor oder nach dem Upgrade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="96cac-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="96cac-140">Gehen Sie folgendermaßen vor, um das Schema zu löschen:</span><span class="sxs-lookup"><span data-stu-id="96cac-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="96cac-141">Übertragen Sie die Objekte mit ALTER SCHEMA vom CDC-Schema auf einen neuen Schemanamen.</span><span class="sxs-lookup"><span data-stu-id="96cac-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="96cac-142">Überprüfen Sie die Berechtigungen für die Objekte im neuen Schema.</span><span class="sxs-lookup"><span data-stu-id="96cac-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="96cac-143">Nehmen Sie notwendige Änderungen an der Anwendung vor.</span><span class="sxs-lookup"><span data-stu-id="96cac-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="96cac-144">Löschen Sie das CDC-Schema mit DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="96cac-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96cac-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96cac-145">See Also</span></span>  
 [<span data-ttu-id="96cac-146">Probleme beim Upgrade der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="96cac-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
