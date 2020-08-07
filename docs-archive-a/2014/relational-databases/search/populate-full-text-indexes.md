---
title: Auffüllen von Volltextindizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620787"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="a3106-102">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="a3106-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="a3106-103">Das Erstellen und Verwalten eines Volltextindexes umfasst das Auffüllen des Indexes mithilfe eines Prozesses, der als *Auffüllung* (oder auch als *Crawl*) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a3106-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="a3106-104">Auffüllungs Typen</span><span class="sxs-lookup"><span data-stu-id="a3106-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a3106-105">unterstützt die folgenden auffüllungs Typen: vollständige Auffüllung, auf Änderungs Nachverfolgung basierende automatische oder manuelle Auffüllung sowie inkrementelle Zeitstempel basierte Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="a3106-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="a3106-106">Vollständige Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-106">Full Population</span></span>  
 <span data-ttu-id="a3106-107">Während einer vollständigen Auffüllung werden Indexeinträge für alle Zeilen einer Tabelle oder einer indizierten Sicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3106-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="a3106-108">Eine vollständige Auffüllung eines Volltextindexes erstellt Indexeinträge für alle Zeilen der Basistabelle oder der indizierten Sicht.</span><span class="sxs-lookup"><span data-stu-id="a3106-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="a3106-109">Standardmäßig füllt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einen neuen Volltextindex vollständig auf, sobald er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a3106-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="a3106-110">Die vollständige Auffüllung kann jedoch eine deutliche Beanspruchung der Ressourcen bedeuten.</span><span class="sxs-lookup"><span data-stu-id="a3106-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="a3106-111">Beim Erstellen eines Volltextindexes zu Zeiten mit hohen Lastwerten wird daher empfohlen, die vollständige Auffüllung bis zu einem späteren Zeitpunkt mit geringerer Auslastung zu verzögern, insbesondere, wenn die Basistabelle eines Volltextindexes sehr groß ist.</span><span class="sxs-lookup"><span data-stu-id="a3106-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="a3106-112">Der Volltextkatalog ist dann allerdings bis zum Abschluss der vollständigen Auffüllung der zugehörigen Volltextindizes nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3106-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="a3106-113">Um einen Volltextindex zu erstellen, ohne ihn sofort aufzufüllen, geben Sie die Klausel CHANGE_TRACKING OFF, NO POPULATION in der CREATE FULLTEXT INDEX-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="a3106-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="a3106-114">Wenn Sie CHANGE_TRACKING MANUAL angeben, verwendet die Volltext-Engine die Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a3106-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a3106-115">füllt den neuen Volltextindex erst auf, wenn Sie eine ALTER FULLTEXT INDEX-Anweisung mithilfe der Klausel Start Full Population oder Start inkrementelle Auffüllung ausführen.</span><span class="sxs-lookup"><span data-stu-id="a3106-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="a3106-116">Weitere Informationen finden Sie unter den Beispielen "A.</span><span class="sxs-lookup"><span data-stu-id="a3106-116">For more information, see examples "A.</span></span> <span data-ttu-id="a3106-117">Erstellen eines Volltextindexes ohne Ausführung der vollständigen Auffüllung" und "B.</span><span class="sxs-lookup"><span data-stu-id="a3106-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="a3106-118">Ausführen einer vollständigen Auffüllung einer Tabelle " weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a3106-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="a3106-119">Auffüllung mithilfe von Änderungsnachverfolgung</span><span class="sxs-lookup"><span data-stu-id="a3106-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="a3106-120">Optional können Sie die Änderungsnachverfolgung verwenden, um nach seiner ursprünglichen vollständigen Auffüllung einen Volltextindex beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="a3106-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="a3106-121">Die Änderungsnachverfolgung bedeutet einen geringen zusätzlichen Leistungsaufwand, da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Tabelle verwaltet, in der Änderungen der Basistabelle seit der letzten Auffüllung verfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="a3106-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="a3106-122">Beim Verwenden der Änderungsnachverfolgung registriert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Zeilen in der Basistabelle oder indizierten Sicht, die durch Updates, Löschungen oder Einfügungen geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="a3106-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="a3106-123">Datenänderungen durch WRITETEXT und UPDATETEXT werden im Volltextindex nicht wiedergegeben und bei der Änderungsnachverfolgung nicht ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a3106-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3106-124">Für Tabellen, die eine `timestamp`-Spalte enthalten, können Sie inkrementelle Auffüllungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3106-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="a3106-125">Wenn die Änderungsnachverfolgung während der Indexerstellung aktiviert ist, führt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die vollständige Auffüllung des neuen Volltextindexes unmittelbar nach dessen Erstellung aus.</span><span class="sxs-lookup"><span data-stu-id="a3106-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="a3106-126">Danach werden Änderungen nachverfolgt und an den Volltextindex weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="a3106-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="a3106-127">Es gibt zwei Typen der Änderungsnachverfolgung, automatisch (Option CHANGE_TRACKING AUTO) und manuell (Option CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="a3106-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="a3106-128">Die automatische Änderungsnachverfolgung ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="a3106-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="a3106-129">Der Typ der Änderungsnachverfolgung bestimmt, wie der Volltextindex aufgefüllt wird, wie im Folgenden dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a3106-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="a3106-130">Automatische Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-130">Automatic population</span></span>  
  
     <span data-ttu-id="a3106-131">Wenn Sie CHANGE_TRACKING AUTO angeben, verwendet die Volltext-Engine die automatische Auffüllung für den Volltextindex.</span><span class="sxs-lookup"><span data-stu-id="a3106-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="a3106-132">Nachdem die ursprüngliche vollständige Auffüllung abgeschlossen wurde, werden Änderungen nachverfolgt und automatisch weitergegeben, wenn Daten in der Basistabelle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3106-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="a3106-133">Der Volltextindex wird im Hintergrund aktualisiert. Die so weitergegebenen Änderungen werden u. U. jedoch nicht sofort im Index wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="a3106-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="a3106-134">**So richten Sie die Nachverfolgung von Änderungen mit automatischer Auffüllung ein**</span><span class="sxs-lookup"><span data-stu-id="a3106-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="a3106-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="a3106-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="a3106-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="a3106-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="a3106-137">Weitere Informationen finden Sie unter Beispiel "E.</span><span class="sxs-lookup"><span data-stu-id="a3106-137">For more information, see example "E.</span></span> <span data-ttu-id="a3106-138">Änderung eines Volltextindexes zur Verwendung der automatischen Änderungsnachverfolgung" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a3106-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="a3106-139">Manuelle Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-139">Manual population</span></span>  
  
     <span data-ttu-id="a3106-140">Wenn Sie CHANGE_TRACKING MANUAL angeben, verwendet die Volltext-Engine die manuelle Auffüllung für den Volltextindex.</span><span class="sxs-lookup"><span data-stu-id="a3106-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="a3106-141">Nachdem die ursprüngliche vollständige Auffüllung abgeschlossen wurde, werden Änderungen nachverfolgt, wenn Daten in der Basistabelle geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a3106-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="a3106-142">Sie werden jedoch nicht an den Volltextindex weitergegeben, bis Sie eine ALTER FULLTEXT INDEX ... START UPDATE POPULATION -Anweisung anwenden.</span><span class="sxs-lookup"><span data-stu-id="a3106-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="a3106-143">Sie können den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent verwenden, um die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung in regelmäßigen Abständen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a3106-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="a3106-144">**So beginnen Sie die Änderungsnachverfolgung mit manueller Auffüllung**</span><span class="sxs-lookup"><span data-stu-id="a3106-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="a3106-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="a3106-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="a3106-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="a3106-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="a3106-147">Weitere Informationen finden Sie unter den Beispielen "C.</span><span class="sxs-lookup"><span data-stu-id="a3106-147">For more information, see examples "C.</span></span> <span data-ttu-id="a3106-148">Erstellen eines Volltextindexes mit manueller Änderungsnachverfolgung" und "D.</span><span class="sxs-lookup"><span data-stu-id="a3106-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="a3106-149">Ausführung einer manuellen Auffüllung" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a3106-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="a3106-150">**So schalten Sie die Änderungsnachverfolgung aus**</span><span class="sxs-lookup"><span data-stu-id="a3106-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="a3106-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="a3106-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="a3106-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="a3106-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="a3106-153">Inkrementelle, auf Timestamps basierende Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="a3106-154">Eine inkrementelle Auffüllung ist ein alternativer Mechanismus zum manuellen Auffüllen eines Volltextindexes.</span><span class="sxs-lookup"><span data-stu-id="a3106-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="a3106-155">Sie können eine inkrementelle Auffüllung für einen Volltextindex ausführen, für den CHANGE_TRACKING auf den Wert MANUAL oder OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a3106-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="a3106-156">Wenn es sich bei der ersten Auffüllung eines Volltextindexes um eine inkrementelle Auffüllung handelt, werden alle Zeilen indiziert. Damit entspricht die Auffüllung einer vollständigen Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="a3106-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="a3106-157">Voraussetzung für die inkrementelle Auffüllung ist, dass die indizierte Tabelle eine Spalte vom `timestamp`-Datentyp aufweist.</span><span class="sxs-lookup"><span data-stu-id="a3106-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="a3106-158">Ist keine `timestamp`-Spalte vorhanden, kann die inkrementelle Auffüllung nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a3106-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="a3106-159">Eine Anforderung für eine inkrementelle Auffüllung für eine Tabelle ohne `timestamp`-Spalte führt zu einer vollständigen Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="a3106-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="a3106-160">Anforderungen für eine inkrementelle Auffüllung werden als vollständige Auffüllung implementiert, wenn sich Metadaten, die sich auf den Volltextindex für die Tabelle auswirken, seit der letzten Auffüllung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="a3106-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="a3106-161">Dies umfasst Metadatenänderungen durch Spalten-, Index- oder Volltextindexdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="a3106-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a3106-162">verwendet die `timestamp`-Spalte, um Zeilen zu identifizieren, die sich seit der letzten Auffüllung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="a3106-162">uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="a3106-163">Bei der inkrementellen Auffüllung wird der Volltextindex bezüglich der Zeilen aktualisiert, die seit der letzten Auffüllung oder während des letzten Auffüllungsvorgangs hinzugefügt, gelöscht oder geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="a3106-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="a3106-164">Wenn in einer Tabelle sehr viele Einfügungen stattfinden, ist die inkrementelle Auffüllung ggf. effizienter als die manuelle Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="a3106-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="a3106-165">Am Ende einer Auffüllung wird von der Volltext-Engine ein neuer `timestamp`-Wert aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a3106-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="a3106-166">Dieser Wert entspricht dem größten in SQL Gatherer aufgetretenen `timestamp`-Wert.</span><span class="sxs-lookup"><span data-stu-id="a3106-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="a3106-167">Der Wert wird verwendet, wenn eine nachfolgende inkrementelle Auffüllung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a3106-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="a3106-168">Um eine inkrementelle Auffüllung auszuführen, führen Sie eine ALTER FULLTEXT INDEX-Anweisung mit der Klausel START INCREMENTAL POPULATION aus.</span><span class="sxs-lookup"><span data-stu-id="a3106-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="a3106-169">Beispiele für das Auffüllen von voll Text Indizes</span><span class="sxs-lookup"><span data-stu-id="a3106-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3106-170">In den Beispielen in diesem Abschnitt wird die `Production.Document` -Tabelle oder die `HumanResources.JobCandidate` -Tabelle der `AdventureWorks` -Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3106-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="a3106-171">A.</span><span class="sxs-lookup"><span data-stu-id="a3106-171">A.</span></span> <span data-ttu-id="a3106-172">Erstellen eines Volltextindexes ohne Ausführung der vollständigen Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="a3106-173">Im folgenden Beispiel wird ein Volltextindex für die `Production.Document` -Tabelle der `AdventureWorks` -Beispieldatenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3106-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="a3106-174">In diesem Beispiel wird WITH CHANGE_TRACKING OFF, NO POPULATION verwendet, um die erste vollständige Auffüllung zu verzögern.</span><span class="sxs-lookup"><span data-stu-id="a3106-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="a3106-175">B.</span><span class="sxs-lookup"><span data-stu-id="a3106-175">B.</span></span> <span data-ttu-id="a3106-176">Ausführen einer vollständigen Auffüllung einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="a3106-176">Running a full population on table</span></span>  
 <span data-ttu-id="a3106-177">Im folgenden Beispiel wird eine vollständige Auffüllung der `Production.Document` -Tabelle der `AdventureWorks` -Beispieldatenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3106-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="a3106-178">C.</span><span class="sxs-lookup"><span data-stu-id="a3106-178">C.</span></span> <span data-ttu-id="a3106-179">Erstellen eines Volltextindexes mit manueller Änderungsnachverfolgung</span><span class="sxs-lookup"><span data-stu-id="a3106-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="a3106-180">Im folgenden Beispiel wird ein Volltextindex mit Änderungsnachverfolgung und manueller Auffüllung für die `HumanResources.JobCandidate` -Tabelle der `AdventureWorks` -Beispieldatenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3106-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="a3106-181">D:</span><span class="sxs-lookup"><span data-stu-id="a3106-181">D.</span></span> <span data-ttu-id="a3106-182">Ausführen einer manuellen Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-182">Running a manual population</span></span>  
 <span data-ttu-id="a3106-183">Im folgenden Beispiel wird eine manuelle Auffüllung des Volltextindexes mit Änderungsnachverfolgung für die `HumanResources.JobCandidate` -Tabelle der `AdventureWorks` -Beispieldatenbank ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3106-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="a3106-184">E.</span><span class="sxs-lookup"><span data-stu-id="a3106-184">E.</span></span> <span data-ttu-id="a3106-185">Umstellen eines Volltextindexes auf die automatische Änderungsnachverfolgung</span><span class="sxs-lookup"><span data-stu-id="a3106-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="a3106-186">Im folgenden Beispiel wird der Volltextindex für die `HumanResources.JobCandidate` -Tabelle der `AdventureWorks` -Beispieldatenbank so geändert, dass dieser die automatische Auffüllung mit Änderungsnachverfolgung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3106-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="a3106-187">Erstellen oder Ändern eines Zeitplans für inkrementelle Auffüllung</span><span class="sxs-lookup"><span data-stu-id="a3106-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="a3106-188">So erstellen oder ändern Sie einen Zeitplan für inkrementelle Auffüllung in Management Studio</span><span class="sxs-lookup"><span data-stu-id="a3106-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="a3106-189">Erweitern Sie im Objekt-Explorer den Server.</span><span class="sxs-lookup"><span data-stu-id="a3106-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="a3106-190">Erweitern Sie **Datenbanken**, und erweitern Sie dann die Datenbank, die den Volltextindex enthält.</span><span class="sxs-lookup"><span data-stu-id="a3106-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="a3106-191">Erweitern Sie **Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="a3106-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="a3106-192">Klicken Sie mit der rechten Maustaste auf die Tabelle, für die der Volltextindex definiert ist. Wählen Sie **Volltextindex**, und klicken Sie dann im Kontextmenü **Volltextindex** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a3106-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="a3106-193">Das Dialogfeld **Volltextindexeigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a3106-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="a3106-194">Wählen Sie im Bereich **Seite auswählen** die Option Zeitpläne aus.</span><span class="sxs-lookup"><span data-stu-id="a3106-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="a3106-195">Verwenden Sie diese Seite, um Zeitpläne für einen SQL Server-Agent-Auftrag zu erstellen oder zu verwalten, der eine inkrementelle Tabellenauffüllung für die Basistabelle oder indizierte Sicht eines Volltextindex beginnt.</span><span class="sxs-lookup"><span data-stu-id="a3106-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a3106-196">Wenn die Basistabelle oder Sicht keine Spalte für den Datentyp `timestamp` enthält, wird eine vollständige Auffüllung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3106-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="a3106-197">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a3106-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="a3106-198">Um einen neuen Zeitplan zu erstellen, klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="a3106-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="a3106-199">Das Dialogfeld **Neuer Zeitplan für Tabellen-Volltextindizierung** wird geöffnet und erlaubt das Erstellen eines neuen Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="a3106-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="a3106-200">Klicken Sie auf **OK**, um den Zeitplan zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a3106-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="a3106-201">Einem neuen Zeitplan wird ein SQL Server-Agent-Auftrag (Start Incremental Table Population on *database_name*.*table_name*) zugeordnet, sobald Sie das Dialogfeld **Volltextindexeigenschaften** schließen.</span><span class="sxs-lookup"><span data-stu-id="a3106-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="a3106-202">Wenn Sie mehrere Zeitpläne für den Volltextindex erstellen, verwenden alle denselben Auftrag.</span><span class="sxs-lookup"><span data-stu-id="a3106-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="a3106-203">Um einen Zeitplan zu ändern, wählen Sie ihn aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a3106-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="a3106-204">Das Dialogfeld **Neuer Zeitplan für Tabellen-Volltextindizierung** wird geöffnet und erlaubt das Bearbeiten des Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="a3106-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="a3106-205">Informationen zum Bearbeiten eines Auftrags finden Sie unter [Ändern eines Auftrags](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="a3106-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="a3106-206">Um einen Zeitplan zu entfernen, wählen Sie ihn aus, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a3106-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="a3106-207">Problembehandlung bei Fehlern in einer voll Text Auffüllung (durch Forstung)</span><span class="sxs-lookup"><span data-stu-id="a3106-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="a3106-208">Tritt während eines Durchforstungsvorgangs ein Fehler auf, wird von der Durchforstungsprotokollfunktion der Volltextsuche ein Durchforstungsprotokoll erstellt und gewartet. Dabei handelt es sich um eine Nur-Text-Datei.</span><span class="sxs-lookup"><span data-stu-id="a3106-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="a3106-209">Jedes Durchforstungsprotokoll gehört zu einem bestimmten Volltextkatalog.</span><span class="sxs-lookup"><span data-stu-id="a3106-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="a3106-210">Standardmäßig befinden sich Durchforstungsprotokolle für eine bestimmte Instanz, in diesem Fall die erste Instanz, im Ordner %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG.</span><span class="sxs-lookup"><span data-stu-id="a3106-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="a3106-211">Das Benennungsschema für Durchforstungsprotokolldateien lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="a3106-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="a3106-212">Sqlft \<DatabaseID> \<FullTextCatalogID> . Log [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="a3106-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="a3106-213">Die ID einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a3106-213">The ID of a database.</span></span><span data-ttu-id="a3106-214"> <`dbid`> ist eine fünfstellige Zahl mit führenden Nullen.</span><span class="sxs-lookup"><span data-stu-id="a3106-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="a3106-215">Volltextkatalog-ID.</span><span class="sxs-lookup"><span data-stu-id="a3106-215">Full-text catalog ID.</span></span><span data-ttu-id="a3106-216"> <`catid`> ist eine fünfstellige Zahl mit führenden Nullen.</span><span class="sxs-lookup"><span data-stu-id="a3106-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="a3106-217">Ist eine ganze Zahl, die angibt, dass mindestens ein Durchforstungsprotokoll desselben Volltextkatalogs vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3106-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="a3106-218">SQLFT0000500008.2 ist z. B. die Durchforstungsprotokolldatei für eine Datenbank mit der Datenbank-ID = 5 und der Volltextkatalog-ID = 8.</span><span class="sxs-lookup"><span data-stu-id="a3106-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="a3106-219">Die 2 am Ende des Dateinamens gibt an, dass zwei Durchforstungsprotokolldateien für dieses Datenbank-Katalog-Paar vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a3106-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="a3106-220">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3106-220">See Also</span></span>  
 <span data-ttu-id="a3106-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a3106-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="a3106-222">[Erste Schritte mit der Volltextsuche](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="a3106-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="a3106-223">[Erstellen und Verwalten von Volltextindizes](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a3106-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="a3106-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a3106-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="a3106-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a3106-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
