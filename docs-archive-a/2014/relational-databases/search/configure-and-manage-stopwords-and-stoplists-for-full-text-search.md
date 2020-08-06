---
title: Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725429"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="dfbf6-102">Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="dfbf6-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="dfbf6-103">Um zu verhindern, dass ein Volltextindex unnötig aufgebläht wird, verfügt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] über einen Mechanismus, der häufig vorkommende, für die Suche nutzlose Zeichenfolgen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="dfbf6-104">Diese verworfenen Zeichenfolgen werden als *Stoppwörter*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="dfbf6-105">Während der Indexerstellung lässt die Volltext-Engine Stoppwörter vom Volltextindex weg.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="dfbf6-106">Dies bedeutet, dass Volltextabfragen nicht nach Stoppwörtern suchen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="dfbf6-107">Grundlegendes zu Stopp Wörtern und Stopp Listen</span><span class="sxs-lookup"><span data-stu-id="dfbf6-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="dfbf6-108">Ein Stoppwort kann ein Wort mit einer Bedeutung in einer bestimmten Sprache oder ein *Token* ohne jegliche linguistische Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="dfbf6-109">Beispielsweise werden in der englischen Sprache Wörter wie "a", "and", "is" und "the" im Volltextindex ausgelassen, da sie erfahrungsgemäß keinen Beitrag zur Suche leisten.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="dfbf6-110">Obwohl der Volltextindex die Inklusion von Stoppwörtern ignoriert, berücksichtigt er ihre Position.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="dfbf6-111">Als Beispiel sei der Ausdruck "Instructions are applicable to these Adventure Works Cycles models" angeführt.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="dfbf6-112">In der folgenden Tabelle sind die Positionen der Wörter im Ausdruck angegeben:</span><span class="sxs-lookup"><span data-stu-id="dfbf6-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="dfbf6-113">Word</span><span class="sxs-lookup"><span data-stu-id="dfbf6-113">Word</span></span>|<span data-ttu-id="dfbf6-114">Position</span><span class="sxs-lookup"><span data-stu-id="dfbf6-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="dfbf6-115">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="dfbf6-115">Instructions</span></span>|<span data-ttu-id="dfbf6-116">1</span><span class="sxs-lookup"><span data-stu-id="dfbf6-116">1</span></span>|  
|<span data-ttu-id="dfbf6-117">are</span><span class="sxs-lookup"><span data-stu-id="dfbf6-117">are</span></span>|<span data-ttu-id="dfbf6-118">2</span><span class="sxs-lookup"><span data-stu-id="dfbf6-118">2</span></span>|  
|<span data-ttu-id="dfbf6-119">applicable</span><span class="sxs-lookup"><span data-stu-id="dfbf6-119">applicable</span></span>|<span data-ttu-id="dfbf6-120">3</span><span class="sxs-lookup"><span data-stu-id="dfbf6-120">3</span></span>|  
|<span data-ttu-id="dfbf6-121">zu</span><span class="sxs-lookup"><span data-stu-id="dfbf6-121">to</span></span>|<span data-ttu-id="dfbf6-122">4</span><span class="sxs-lookup"><span data-stu-id="dfbf6-122">4</span></span>|  
|<span data-ttu-id="dfbf6-123">these</span><span class="sxs-lookup"><span data-stu-id="dfbf6-123">these</span></span>|<span data-ttu-id="dfbf6-124">5</span><span class="sxs-lookup"><span data-stu-id="dfbf6-124">5</span></span>|  
|<span data-ttu-id="dfbf6-125">Adventure</span><span class="sxs-lookup"><span data-stu-id="dfbf6-125">Adventure</span></span>|<span data-ttu-id="dfbf6-126">6</span><span class="sxs-lookup"><span data-stu-id="dfbf6-126">6</span></span>|  
|<span data-ttu-id="dfbf6-127">Works</span><span class="sxs-lookup"><span data-stu-id="dfbf6-127">Works</span></span>|<span data-ttu-id="dfbf6-128">7</span><span class="sxs-lookup"><span data-stu-id="dfbf6-128">7</span></span>|  
|<span data-ttu-id="dfbf6-129">Cycles</span><span class="sxs-lookup"><span data-stu-id="dfbf6-129">Cycles</span></span>|<span data-ttu-id="dfbf6-130">8</span><span class="sxs-lookup"><span data-stu-id="dfbf6-130">8</span></span>|  
|<span data-ttu-id="dfbf6-131">Modelle</span><span class="sxs-lookup"><span data-stu-id="dfbf6-131">models</span></span>|<span data-ttu-id="dfbf6-132">9</span><span class="sxs-lookup"><span data-stu-id="dfbf6-132">9</span></span>|  
  
 <span data-ttu-id="dfbf6-133">Die Stoppwörter "are", "to" und "these" an den Positionen 2, 4 und 5 werden im Volltextindex ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="dfbf6-134">Die Positionsinformationen bleiben jedoch erhalten, sodass die Positionen der anderen Wörter im Ausdruck unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="dfbf6-135">Stoppwörter werden über Objekte mit dem Namen "Stoplisten" in Datenbanken verwaltet.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="dfbf6-136">Eine *Stopp Liste* ist eine Liste von Stopp Wörtern, die, wenn Sie einem Volltextindex zugeordnet ist, auf voll Text Abfragen für diesen Index angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="dfbf6-137">Erstellen einer Stopp Liste</span><span class="sxs-lookup"><span data-stu-id="dfbf6-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="dfbf6-138">Zum Erstellen einer Stopliste stehen die folgenden Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="dfbf6-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="dfbf6-139">Verwenden der vom System bereitgestellten Stopliste in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-139">Using the system-supplied stoplist in the database.</span></span> <span data-ttu-id="dfbf6-140">Der Lieferumfang von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] umfasst eine Systemstopliste, die die am häufigsten verwendeten Stoppwörter für jede unterstützte Sprache enthält, d. h. für jede Sprache, die den jeweiligen Wörtertrennungen standardmäßig zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-140">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="dfbf6-141">Die Systemstoppliste enthält gebräuchliche Stoppwörter für alle unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="dfbf6-142">Sie können die Systemstoppliste kopieren und Ihre Kopie durch das Hinzufügen und Entfernen von Stoppwörtern anpassen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="dfbf6-143">Die Systemstoppliste ist in der [Ressourcendatenbank](../databases/resource-database.md) installiert.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="dfbf6-144">Erstellen einer eigenen Stoppliste und Hinzufügen von Stoppwörtern für jede Sprache, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="dfbf6-145">Sie können bei Bedarf auch Stoppwörter aus der Stoppliste löschen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="dfbf6-146">Verwenden einer vorhandenen benutzerdefinierten Stoppliste aus einer anderen Datenbank in der aktuellen Serverinstanz und anschließendes Hinzufügen und Löschen von Stoppwörtern nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="dfbf6-147">**So erstellen Sie eine Stoppliste**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="dfbf6-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="dfbf6-149">So erstellen Sie eine Volltextstopliste in Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfbf6-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="dfbf6-150">Erweitern Sie im Objekt-Explorer den Server.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="dfbf6-151">Erweitern Sie **Datenbanken**, und erweitern Sie dann die Datenbank, in der die Volltext-Stopliste erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="dfbf6-152">Erweitern Sie **Speicher**, und klicken Sie dann mit der rechten Maustaste auf **Volltext-Stopplisten**.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="dfbf6-153">Wählen Sie **Neue Volltext-Stoppliste**.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="dfbf6-154">Geben Sie den Namen der Stoppliste an.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="dfbf6-155">Optional können Sie eine andere Person als Besitzer der Stoppliste angeben.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="dfbf6-156">Wählen Sie eine der folgenden Optionen zur Erstellung der Stoppliste:</span><span class="sxs-lookup"><span data-stu-id="dfbf6-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="dfbf6-157">**Leere Stoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="dfbf6-158">**Aus der Systemstoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="dfbf6-159">**Aus vorhandener Volltext-Stoppliste erstellen**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="dfbf6-160">Weitere Informationen finden Sie unter [Neue Volltext-Stoppliste &#40;Seite 'Allgemein'&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="dfbf6-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="dfbf6-161">**So löschen Sie eine Stopliste**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="dfbf6-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="dfbf6-163">Verwenden einer Stopp Liste in voll Text Abfragen</span><span class="sxs-lookup"><span data-stu-id="dfbf6-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="dfbf6-164">Wenn Sie eine Stopliste in Abfragen nutzen möchten, müssen Sie diese einem Volltextindex zuordnen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="dfbf6-165">Sie können einem Volltextindex eine Stoppliste zuordnen, wenn Sie den Index erstellen, oder Sie können den Index später ändern, um eine Stoppliste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="dfbf6-166">**So erstellen Sie einen Volltextindex und ordnen diesem eine Stoppliste zu**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="dfbf6-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="dfbf6-168">**So ordnen Sie einem vorhandenen Volltextindex eine Stoppliste zu oder heben eine Zuordnung auf**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="dfbf6-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="dfbf6-170">**So unterdrücken Sie eine Fehlermeldung, wenn ein boolescher Vorgang für eine Volltextabfrage aufgrund von Stoppwörtern fehlschlägt**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="dfbf6-171">Füllwörtertransformation (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="dfbf6-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="dfbf6-172">Anzeigen von Stopp Listen und Stopp Listen-Metadaten</span><span class="sxs-lookup"><span data-stu-id="dfbf6-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="dfbf6-173">**So zeigen Sie alle Stoppwörter einer Stopliste an**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="dfbf6-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="dfbf6-175">**So rufen Sie Informationen zu allen Stopplisten in der aktuellen Datenbank ab**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="dfbf6-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="dfbf6-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="dfbf6-178">**So zeigen Sie das Tokenisierungsergebnis einer Kombination aus Wörtertrennung, Thesaurus und Stoplisten an**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="dfbf6-179">sys. dm_fts_parser &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="dfbf6-180">Ändern der Stoppwörter in einer Stopp Liste</span><span class="sxs-lookup"><span data-stu-id="dfbf6-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="dfbf6-181">**So fügen Sie einer Stopliste Stoppwörter hinzu oder löschen diese**</span><span class="sxs-lookup"><span data-stu-id="dfbf6-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="dfbf6-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfbf6-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="dfbf6-183">So ändern Sie die Stoppwörter in einer Stopliste in Management Studio</span><span class="sxs-lookup"><span data-stu-id="dfbf6-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="dfbf6-184">Erweitern Sie im Objekt-Explorer den Server.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="dfbf6-185">Erweitern Sie **Datenbanken**und dann die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="dfbf6-186">Erweitern Sie **Speicher**, und wählen Sie dann **Volltext-Stopplisten**.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="dfbf6-187">Klicken Sie mit der rechten Maustaste auf die Stoppliste, deren Eigenschaften Sie ändern möchten, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="dfbf6-188">Im Dialogfeld [Volltext-Stopplisten-Eigenschaften](../../database-engine/full-text-stoplist-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="dfbf6-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="dfbf6-189">Wählen Sie im Listenfeld **Aktion** eine der folgenden Aktionen aus: **Stoppwort hinzufügen**, **Stoppwort löschen**, **Alle Stoppwörter löschen**oder **Inhalt der Stoppliste löschen**.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="dfbf6-190">Wenn das Textfeld **Stoppwort** für die ausgewählte Aktion aktiviert ist, geben Sie ein einzelnes Stoppwort ein.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="dfbf6-191">Dieses Stoppwort muss eindeutig sein; das heißt, es darf noch nicht in dieser Stoppliste für die Sprache, die Sie auswählen, enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="dfbf6-192">Wenn das Listenfeld **Volltextsprache** für die ausgewählte Aktion aktiviert ist, wählen Sie eine Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="dfbf6-193">Aktualisieren von Füll Wörtern von SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="dfbf6-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="dfbf6-194">-Füllwörter wurden durch Stoppwörter ersetzt.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="dfbf6-195">Wenn eine Datenbank von [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]aktualisiert wird, werden die Füllwortdateien nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="dfbf6-196">Die Füllwortdateien werden jedoch im Ordner "FTDATA\FTNoiseThesaurusBak" gespeichert, und Sie können sie später beim Aktualisieren oder Erstellen der entsprechenden Stoplisten verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfbf6-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="dfbf6-197">Informationen zum Upgrade von Füllwortdateien auf Stoplisten finden Sie unter [Upgrade der Volltextsuche](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="dfbf6-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
