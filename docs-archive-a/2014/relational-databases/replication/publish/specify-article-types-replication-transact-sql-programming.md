---
title: Angeben von Artikeltypen (Replikationsprogrammierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- articles [SQL Server replication], transactional replication options
- articles [SQL Server replication], merge replication options
- stored procedures [SQL Server replication], publishing
ms.assetid: d7effbac-c45b-423f-97ae-fd426b1050ba
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7864825891203530bf30015471ca22a1daccf9b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721292"
---
# <a name="specify-article-types-replication-transact-sql-programming"></a><span data-ttu-id="a6cea-102">Angeben von Artikeltypen (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a6cea-102">Specify Article Types (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="a6cea-103">Die Standardartikeltypen für die Replikation sind Tabellen. Sie können aber auch andere Datenbankobjekte als Artikel veröffentlichen, einschließlich Sichten, gespeicherte Prozeduren, benutzerdefinierte Funktionen und die Ausführung von gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="a6cea-103">The default article types for replication are table articles, but you can publish other database objects as articles, including views, stored procedures, user-defined functions, and stored procedure execution.</span></span> <span data-ttu-id="a6cea-104">Sie können gespeicherte Replikationsprozeduren verwenden, um einen Artikeltyp beim Definieren eines Artikels programmgesteuert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a6cea-104">You can use replication stored procedures to specify an article type programmatically when you define an article.</span></span> <span data-ttu-id="a6cea-105">Welche Prozeduren Sie verwenden, hängt vom Typ der Replikation und des Artikels ab.</span><span class="sxs-lookup"><span data-stu-id="a6cea-105">The procedures that you use depend on the type of replication and article type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6cea-106">Beim Definieren von Artikeln für Tabellen, Sichten und gespeicherte Prozeduren gibt die Bezeichnung schema only an, dass nur die Objektdefinition repliziert wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-106">The schema-only designation when defining table, view, and stored procedure articles indicates that only the object definition is replicated.</span></span>  
  
### <a name="to-publish-a-table-article-in-a-transactional-or-snapshot-publication"></a><span data-ttu-id="a6cea-107">So veröffentlichen Sie einen Tabellenartikel in einer Transaktions- oder Momentaufnahmeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a6cea-107">To publish a table article in a transactional or snapshot publication</span></span>  
  
1.  <span data-ttu-id="a6cea-108">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="a6cea-108">At the Publisher on the publication database, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span> <span data-ttu-id="a6cea-109">Geben Sie einen der folgenden Werte für \*\* \@ Typ\*\* an, um den Typ des Artikels zu definieren:</span><span class="sxs-lookup"><span data-stu-id="a6cea-109">Specify one of the following values for **\@type** to define the type of article:</span></span>  
  
    -   <span data-ttu-id="a6cea-110">**logbased** &ndash; ein protokollbasierter Tabellenartikel, der der Standard für die Transaktions- und Momentaufnahmereplikation ist.</span><span class="sxs-lookup"><span data-stu-id="a6cea-110">**logbased** - a log-based table article, which is the default for transactional and snapshot replication.</span></span> <span data-ttu-id="a6cea-111">Die Replikation generiert automatisch die gespeicherte Prozedur, die für das horizontale Filtern verwendet wird, sowie die Sicht, die einen vertikal gefilterten Artikel definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-111">Replication automatically generates the stored procedure used for horizontal filtering and the view that defines a vertically filtered article.</span></span>  
  
    -   <span data-ttu-id="a6cea-112">**logbased manualfilter** : ein Protokoll basierter, horizontal gefilterter Artikel, in dem die gespeicherte Prozedur für das horizontale Filtern manuell vom Benutzer erstellt und definiert und für \*\* \@ Filter\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-112">**logbased manualfilter** - a log-based, horizontally filtered article where the stored procedure used for horizontal filtering is manually created and defined by the user and specified for **\@filter**.</span></span> <span data-ttu-id="a6cea-113">Weitere Informationen finden Sie unter [Definieren oder Ändern eines statischen Zeilenfilters](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-113">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-114">**logbased manualview** : ein Protokoll basierter, vertikal gefilterter Artikel, in dem die Sicht, die den vertikal gefilterten Artikel definiert, vom Benutzer erstellt und definiert und für \*\* \@ sync_object\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-114">**logbased manualview** - a log-based, vertically filtered article where the view that defines the vertically filtered article is created and defined by the user and specified for **\@sync_object**.</span></span> <span data-ttu-id="a6cea-115">Weitere Informationen finden Sie unter [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) und [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-115">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) and [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-116">**logbased manualboth** : ein Protokoll basierter, horizontal und vertikal gefilterter Artikel, in dem sowohl die gespeicherte Prozedur für das horizontale Filtern als auch die Sicht, die den vertikal gefilterten Artikel definiert, vom Benutzer erstellt und definiert und für \*\* \@ Filter\*\* bzw. \*\* \@ sync_object\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-116">**logbased manualboth** - a log-based, horizontally and vertically filtered article where both the stored procedure used for horizontal filtering and the view that defines the vertically filtered article are created and defined by the user and specified for **\@filter** and **\@sync_object**, respectively.</span></span> <span data-ttu-id="a6cea-117">Weitere Informationen finden Sie unter [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) und [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-117">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) and [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
     <span data-ttu-id="a6cea-118">Damit wird ein neuer Artikel für die Veröffentlichung definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-118">This defines a new article for the publication.</span></span> <span data-ttu-id="a6cea-119">Weitere Informationen finden Sie unter [Definieren eines Artikels](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-119">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
2.  <span data-ttu-id="a6cea-120">Führen Sie für **logbased manualboth** -Artikel und **logbased manualfilter** -Artikel [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) aus, um die gespeicherte Filterprozedur für einen horizontal gefilterten Artikel zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a6cea-120">For **logbased manualboth** and **logbased manualfilter** articles, execute [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) to generate the filtering stored procedure for a horizontally filtered article.</span></span> <span data-ttu-id="a6cea-121">Weitere Informationen finden Sie unter [Definieren oder Ändern eines statischen Zeilenfilters](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-121">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span>  
  
3.  <span data-ttu-id="a6cea-122">Führen Sie für Artikel vom Typ **logbased manualboth**, **logbased manualview**und **logbased manualfilter**[sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) aus, um die Sicht zu generieren, die den vertikal gefilterten Artikel definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-122">For **logbased manualboth**, **logbased manualview**, and **logbased manualfilter** articles, execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) to generate the view that defines the vertically filtered article.</span></span> <span data-ttu-id="a6cea-123">Weitere Informationen finden Sie unter [Definieren und Ändern eines Spaltenfilters](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-123">For more information, see [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
### <a name="to-publish-a-view-or-indexed-view-article-in-a-transactional-or-snapshot-publication"></a><span data-ttu-id="a6cea-124">So veröffentlichen Sie einen Artikel für eine Sicht oder eine indizierte Sicht in einer Transaktions- oder Momentaufnahmeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a6cea-124">To publish a view or indexed view article in a transactional or snapshot publication</span></span>  
  
1.  <span data-ttu-id="a6cea-125">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="a6cea-125">At the Publisher on the publication database, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span> <span data-ttu-id="a6cea-126">Geben Sie einen der folgenden Werte für \*\* \@ Typ\*\* an, um den Typ des Artikels zu definieren:</span><span class="sxs-lookup"><span data-stu-id="a6cea-126">Specify one of the following values for **\@type** to define the type of article:</span></span>  
  
    -   <span data-ttu-id="a6cea-127">**indexed view logbased** &ndash; ein Artikel für eine protokollbasierte, indizierte Sicht.</span><span class="sxs-lookup"><span data-stu-id="a6cea-127">**indexed view logbased** - a log-based indexed view article.</span></span> <span data-ttu-id="a6cea-128">Die Replikation generiert automatisch die gespeicherte Prozedur, die für das horizontale Filtern verwendet wird, sowie die Sicht, die einen vertikal gefilterten Artikel definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-128">Replication automatically generates the stored procedure used for horizontal filtering and the view that defines a vertically filtered article.</span></span>  
  
    -   <span data-ttu-id="a6cea-129">**view schema only** &ndash; ein Artikel für eine Sicht vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-129">**view schema only** - a schema-only view article.</span></span> <span data-ttu-id="a6cea-130">Die Basistabelle muss ebenfalls repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="a6cea-130">The base table must also be replicated.</span></span>  
  
    -   <span data-ttu-id="a6cea-131">**indexed view schema only** &ndash; ein Artikel für eine indizierte Sicht vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-131">**indexed view schema only** - a schema-only indexed view article.</span></span> <span data-ttu-id="a6cea-132">Die Basistabelle muss ebenfalls repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="a6cea-132">The base table must also be replicated.</span></span>  
  
    -   <span data-ttu-id="a6cea-133">**indizierte Sicht logbased manualfilter** -ein Protokoll basierter, horizontal gefilterter Artikel für eine indizierte Sicht, in dem die gespeicherte Prozedur für das horizontale Filtern manuell vom Benutzer erstellt und definiert und für \*\* \@ Filter\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-133">**indexed view logbased manualfilter** - a log-based, horizontally filtered indexed view article where the stored procedure used for horizontal filtering is manually created and defined by the user and specified for **\@filter**.</span></span> <span data-ttu-id="a6cea-134">Weitere Informationen finden Sie unter [Definieren oder Ändern eines statischen Zeilenfilters](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-134">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-135">**indizierte Sicht logbased manualview** : ein Protokoll basierter, gefilterter Artikel für eine indizierte Sicht, in dem die Sicht, die einen vertikal gefilterten Artikel definiert, vom Benutzer erstellt und definiert und für \*\* \@ sync_object\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-135">**indexed view logbased manualview** - a log-based, filtered indexed view article where the view that defines a vertically filtered article is created and defined by the user and specified for **\@sync_object**.</span></span> <span data-ttu-id="a6cea-136">Weitere Informationen finden Sie unter [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) und [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-136">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) and [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-137">**indizierte Sicht logbased manualboth** : ein Protokoll basierter, gefilterter Artikel für eine indizierte Sicht, in dem sowohl die gespeicherte Prozedur für das horizontale Filtern als auch die Sicht, die einen vertikal gefilterten Artikel definiert, vom Benutzer erstellt und definiert und für \*\* \@ Filter\*\* bzw. \*\* \@ sync_object\*\*angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-137">**indexed view logbased manualboth** - a log-based, filtered indexed view article where both the stored procedure used for horizontal filtering and the view that defines a vertically filtered article are created and defined by the user and specified for **\@filter** and **\@sync_object**, respectively.</span></span> <span data-ttu-id="a6cea-138">Weitere Informationen finden Sie unter [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) und [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-138">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md) and [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
     <span data-ttu-id="a6cea-139">Damit wird ein neuer Artikel für die Veröffentlichung definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-139">This defines a new article for the publication.</span></span> <span data-ttu-id="a6cea-140">Weitere Informationen finden Sie unter [Definieren eines Artikels](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-140">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
2.  <span data-ttu-id="a6cea-141">Führen Sie für **logbased manualboth** -Artikel und **logbased manualfilter** -Artikel [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) aus, um die gespeicherte Filterprozedur für einen horizontal gefilterten Artikel zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a6cea-141">For **logbased manualboth** and **logbased manualfilter** articles, execute [sp_articlefilter](/sql/relational-databases/system-stored-procedures/sp-articlefilter-transact-sql) to generate the filtering stored procedure for a horizontally filtered article.</span></span> <span data-ttu-id="a6cea-142">Weitere Informationen finden Sie unter [Definieren oder Ändern eines statischen Zeilenfilters](define-and-modify-a-static-row-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-142">For more information, see [Define and Modify a Static Row Filter](define-and-modify-a-static-row-filter.md).</span></span>  
  
3.  <span data-ttu-id="a6cea-143">Führen Sie für Artikel vom Typ **logbased manualboth**, **logbased manualview**und **logbased manualfilter**[sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) aus, um die Sicht zu generieren, die den vertikal gefilterten Artikel definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-143">For **logbased manualboth**, **logbased manualview**, and **logbased manualfilter** articles, execute [sp_articleview](/sql/relational-databases/system-stored-procedures/sp-articleview-transact-sql) to generate the view that defines the vertically filtered article.</span></span> <span data-ttu-id="a6cea-144">Weitere Informationen finden Sie unter [Definieren und Ändern eines Spaltenfilters](define-and-modify-a-column-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-144">For more information, see [Define and Modify a Column Filter](define-and-modify-a-column-filter.md).</span></span>  
  
### <a name="to-publish-a-stored-procedure-stored-procedure-execution-or-user-defined-function-article-in-a-transactional-or-snapshot-publication"></a><span data-ttu-id="a6cea-145">So veröffentlichen Sie einen Artikel für eine gespeicherte Prozedur, für die Ausführung einer gespeicherten Prozedur oder für eine benutzerdefinierte Funktion in einer Transaktions- oder Momentaufnahmeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a6cea-145">To publish a stored procedure, stored procedure execution, or user-defined function article in a transactional or snapshot publication</span></span>  
  
1.  <span data-ttu-id="a6cea-146">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="a6cea-146">At the Publisher on the publication database, execute [sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql).</span></span> <span data-ttu-id="a6cea-147">Geben Sie einen der folgenden Werte für \*\* \@ Typ\*\* an, um den Typ des Artikels zu definieren:</span><span class="sxs-lookup"><span data-stu-id="a6cea-147">Specify one of the following values for **\@type** to define the type of article:</span></span>  
  
    -   <span data-ttu-id="a6cea-148">**proc schema only** &ndash; ein Artikel für eine gespeicherte Prozedur vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-148">**proc schema only** - a schema-only stored procedure article.</span></span>  
  
    -   <span data-ttu-id="a6cea-149">**proc exec** &ndash; repliziert die Ausführung der gespeicherten Prozedur auf alle Abonnenten des Artikels.</span><span class="sxs-lookup"><span data-stu-id="a6cea-149">**proc exec** - replicates the execution of the stored procedure to all Subscribers of the article.</span></span> <span data-ttu-id="a6cea-150">Weitere Informationen finden Sie unter [Publishing Stored Procedure Execution in Transactional Replication](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-150">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-151">**serializable proc exec** &ndash; repliziert die Ausführung der gespeicherten Prozedur nur, wenn die Prozedur im Kontext einer serialisierbaren Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a6cea-151">**serializable proc exec** - replicates the execution of the stored procedure only if it is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="a6cea-152">Weitere Informationen finden Sie unter [Publishing Stored Procedure Execution in Transactional Replication](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-152">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
    -   <span data-ttu-id="a6cea-153">**func schema only** &ndash; ein Artikel für eine benutzerdefinierte Funktion vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-153">**func schema only** - a schema-only user-defined function article.</span></span>  
  
     <span data-ttu-id="a6cea-154">Damit wird ein neuer Artikel für die Veröffentlichung definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-154">This defines a new article for the publication.</span></span> <span data-ttu-id="a6cea-155">Weitere Informationen finden Sie unter [Definieren eines Artikels](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-155">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
### <a name="to-publish-a-table-or-view-article-in-a-merge-publication"></a><span data-ttu-id="a6cea-156">So veröffentlichen Sie einen Tabellen- oder Sichtartikel in einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a6cea-156">To publish a table or view article in a merge publication</span></span>  
  
1.  <span data-ttu-id="a6cea-157">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="a6cea-157">At the Publisher on the publication database, execute [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="a6cea-158">Geben Sie einen der folgenden Werte für \*\* \@ Typ\*\* an, um den Typ des Artikels zu definieren:</span><span class="sxs-lookup"><span data-stu-id="a6cea-158">Specify one of the following values for **\@type** to define the type of article:</span></span>  
  
    -   <span data-ttu-id="a6cea-159">**table** &ndash; ein Tabellenartikel.</span><span class="sxs-lookup"><span data-stu-id="a6cea-159">**table** - a table article.</span></span>  
  
    -   <span data-ttu-id="a6cea-160">**indexed view schema only** &ndash; ein Artikel für eine indizierte Sicht vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-160">**indexed view schema only** - a schema-only indexed view article.</span></span>  
  
    -   <span data-ttu-id="a6cea-161">**view schema only** &ndash; ein Artikel für eine Sicht vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-161">**view schema only** - a schema-only view article.</span></span>  
  
     <span data-ttu-id="a6cea-162">Damit wird ein neuer Artikel für die Veröffentlichung definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-162">This defines a new article for the publication.</span></span> <span data-ttu-id="a6cea-163">Weitere Informationen finden Sie unter [Definieren eines Artikels](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-163">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
### <a name="to-publish-a-stored-procedure-or-user-defined-function-article-in-a-merge-publication"></a><span data-ttu-id="a6cea-164">So veröffentlichen Sie einen Artikel für eine gespeicherte Prozedur oder eine benutzerdefinierte Funktion in einer Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a6cea-164">To publish a stored procedure or user-defined function article in a merge publication</span></span>  
  
1.  <span data-ttu-id="a6cea-165">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="a6cea-165">At the Publisher on the publication database, execute [sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="a6cea-166">Geben Sie einen der folgenden Werte für \*\* \@ Typ\*\* an, um den Typ des Artikels zu definieren:</span><span class="sxs-lookup"><span data-stu-id="a6cea-166">Specify one of the following values for **\@type** to define the type of article:</span></span>  
  
    -   <span data-ttu-id="a6cea-167">**func schema only** &ndash; ein Artikel für eine benutzerdefinierte Funktion vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-167">**func schema only** - a schema-only user-defined function article.</span></span>  
  
    -   <span data-ttu-id="a6cea-168">**proc schema only** &ndash; ein Artikel für eine gespeicherte Prozedur vom Typ schema only.</span><span class="sxs-lookup"><span data-stu-id="a6cea-168">**proc schema only** - a schema-only stored procedure article.</span></span>  
  
     <span data-ttu-id="a6cea-169">Damit wird ein neuer Artikel für die Veröffentlichung definiert.</span><span class="sxs-lookup"><span data-stu-id="a6cea-169">This defines a new article for the publication.</span></span> <span data-ttu-id="a6cea-170">Weitere Informationen finden Sie unter [Definieren eines Artikels](define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="a6cea-170">For more information, see [Define an Article](define-an-article.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6cea-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6cea-171">See Also</span></span>  
 <span data-ttu-id="a6cea-172">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="a6cea-172">[Replication System Stored Procedures Concepts](../concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="a6cea-173">Veröffentlichen von Daten und Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="a6cea-173">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  