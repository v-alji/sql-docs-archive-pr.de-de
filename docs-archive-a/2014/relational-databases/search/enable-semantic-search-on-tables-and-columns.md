---
title: Aktivieren der semantischen Suche in Tabellen und Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717755"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="17ce7-102">Aktivieren der semantischen Suche in Tabellen und Spalten</span><span class="sxs-lookup"><span data-stu-id="17ce7-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="17ce7-103">Beschreibt, wie die statistische semantische Indizierung für ausgewählte Spalten, die Dokumente oder Text enthalten, aktiviert bzw. deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="17ce7-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="17ce7-104">Die statistische semantische Suche verwendet die Indizes, die von der Volltextsuche erstellt werden, und erstellt zusätzliche Indizes.</span><span class="sxs-lookup"><span data-stu-id="17ce7-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="17ce7-105">Als Ergebnis dieser Abhängigkeit von der Volltextsuche erstellen Sie einen neuen semantischen Index, wenn Sie einen neuen Volltextindex definieren oder einen vorhandenen Volltextindex ändern.</span><span class="sxs-lookup"><span data-stu-id="17ce7-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="17ce7-106">Einen neuen semantischen Index können Sie mit [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen oder mit dem Volltextindizierungs-Assistenten und anderen Dialogfeldern in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen, wie in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="17ce7-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="17ce7-107">Erstellen eines semantischen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="17ce7-108">Anforderungen und Einschränkungen beim Erstellen eines semantischen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="17ce7-109">Sie können einen Index für alle Datenbankobjekte erstellen, die für Volltextindizierung unterstützt werden, einschließlich Tabellen und indizierte Sichten.</span><span class="sxs-lookup"><span data-stu-id="17ce7-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="17ce7-110">Bevor Sie die semantische Indizierung für bestimmte Spalten aktivieren können, müssen die folgenden Anforderungen erfüllt werden:</span><span class="sxs-lookup"><span data-stu-id="17ce7-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="17ce7-111">Für die Datenbank muss ein Volltextkatalog vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="17ce7-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="17ce7-112">Die Tabelle muss über einen Volltextindex verfügen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="17ce7-113">Die ausgewählten Spalten müssen Teil des Volltextindexes sein.</span><span class="sxs-lookup"><span data-stu-id="17ce7-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="17ce7-114">Diese Anforderungen können alle gleichzeitig erstellt und aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="17ce7-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="17ce7-115">Sie können einen semantischen Index für Spalten erstellen, die einen der für Volltextindizierung unterstützten Datentypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="17ce7-116">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Volltextindizes](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="17ce7-117">Sie können einen beliebigen Dokumenttyp angeben, der für Volltextindizierung für `varbinary(max)`-Spalten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="17ce7-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="17ce7-118">Weitere Informationen finden Sie unter [Vorgehensweise: Ermitteln, welche Dokumenttypen indiziert werden können](#doctypes) .</span><span class="sxs-lookup"><span data-stu-id="17ce7-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="17ce7-119">Bei der semantischen Indizierung werden zwei Typen von Indizes für die ausgewählten Spalten erstellt: ein Index mit Schlüsselausdrücken und ein Index für Dokumentähnlichkeit.</span><span class="sxs-lookup"><span data-stu-id="17ce7-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="17ce7-120">Wenn Sie die semantische Indizierung aktivieren, können Sie nur einen Indextyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="17ce7-121">Sie können diese beiden Indizes jedoch unabhängig voneinander abfragen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="17ce7-122">Weitere Informationen finden Sie unter [Suchen von Schlüsselausdrücken in Dokumenten mit der semantischen Suche](find-key-phrases-in-documents-with-semantic-search.md) und [Suchen von ähnlichen und verwandten Dokumenten mit semantischer Suche](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="17ce7-123">Wenn Sie nicht explizit eine LCID für einen semantischen Index angeben, werden nur die primäre Sprache und ihre zugeordneten Sprachstatistiken für die semantische Indizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="17ce7-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="17ce7-124">Wenn Sie eine Sprache für eine Spalte angeben, für die das Sprachmodell nicht verfügbar ist, schlägt die Erstellung des Indexes fehl, und es wird eine Fehlermeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17ce7-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="17ce7-125">Vorgehensweise: Erstellen eines semantischen Indexes, wenn kein voll Text Index vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="17ce7-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="17ce7-126">Wenn Sie einen neuen Volltextindex mit der **CREATE FULLTEXT INDEX** -Anweisung erstellen, können Sie die semantische Indizierung auf Spaltenebene aktivieren, indem Sie das Schlüsselwort **STATISTICAL_SEMANTICS** als Teil der Spaltendefinition angeben.</span><span class="sxs-lookup"><span data-stu-id="17ce7-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="17ce7-127">Sie können die semantische Indizierung auch aktivieren, wenn Sie einen neuen Volltextindex mithilfe des Volltextindizierungs-Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="17ce7-128">**Erstellen eines neuen semantischen Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="17ce7-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="17ce7-129">Rufen Sie die **CREATE FULLTEXT INDEX**-Anweisung auf, und geben Sie **STATISTICAL_SEMANTICS** für jede Spalte an, in der Sie einen semantischen Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="17ce7-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="17ce7-130">Weitere Informationen zu allen Optionen für diese Anweisung finden Sie unter [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17ce7-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="17ce7-131">**Beispiel 1: Erstellen eines eindeutigen Indexes, eines Volltextindexes und eines semantischen Indexes**</span><span class="sxs-lookup"><span data-stu-id="17ce7-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="17ce7-132">Im folgenden Beispiel wird der Standardvolltextkatalog **ft**erstellt. Im folgenden Beispiel wird ein eindeutiger Index für die **JobCandidateID** -Spalte der **HumanResources.JobCandidate** -Tabelle der AdventureWorks2012-Beispieldatenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="17ce7-133">Dieser eindeutige Index ist als Schlüsselspalte für einen Volltextindex erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17ce7-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="17ce7-134">Im Beispiel werden dann ein Volltextindex und ein semantischer Index in der **Resume** -Spalte erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="17ce7-135">**Beispiel 2: Erstellen eines Volltextindexes und eines semantischen Indexes in mehreren Spalten mit verzögerter Indexauffüllung**</span><span class="sxs-lookup"><span data-stu-id="17ce7-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="17ce7-136">Im folgenden Beispiel wird ein Volltextkatalog **documents_catalog**in der AdventureWorks2012-Beispieldatenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="17ce7-137">Im Beispiel wird dann ein Volltextindex erstellt, der diesen neuen Katalog verwendet.</span><span class="sxs-lookup"><span data-stu-id="17ce7-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="17ce7-138">Der Volltextindex wird in den Spalten **Title**, **DocumentSummary**und **Document** der Tabelle **Production.Document** erstellt, wohingegen der semantische Index nur in der Spalte **Document** erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="17ce7-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="17ce7-139">Dieser Volltextindex verwendet den neu erstellten Volltextkatalog und den vorhandenen eindeutigen Schlüsselindex **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="17ce7-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="17ce7-140">Wie empfohlen, wird dieser Indexschlüssel in der ganzzahligen Spalte **DocumentID**erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="17ce7-141">Im Beispiel ist die LCID für Englisch, 1033, angegeben. Dies entspricht der Sprache der Daten in den Spalten.</span><span class="sxs-lookup"><span data-stu-id="17ce7-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="17ce7-142">In diesem Beispiel wird auch angegeben, dass die Änderungsnachverfolgung ohne Auffüllung deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17ce7-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="17ce7-143">Im Beispiel wird eine **ALTER FULLTEXT INDEX** -Anweisung verwendet, um außerhalb der Spitzenbetriebszeiten eine vollständige Auffüllung mit dem neuen Index zu beginnen und die automatische Änderungsnachverfolgung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="17ce7-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="17ce7-144">Der Index wird später zu einem Zeitpunkt mit wenig Datenverkehr aufgefüllt:</span><span class="sxs-lookup"><span data-stu-id="17ce7-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="17ce7-145">**Erstellen eines neuen semantischen Indexes mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="17ce7-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="17ce7-146">Führen Sie den Volltextindizierungs-Assistenten aus, und aktivieren Sie für jede Spalte, in der Sie einen semantischen Index erstellen möchten, die Option **Statistische Semantik** auf der Seite **Tabellenspalten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="17ce7-147">Weitere Informationen, einschließlich Informationen zum Starten des Volltextindizierungs-Assistenten, finden Sie unter [Verwenden des Volltextindizierungs-Assistenten](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="17ce7-148">Vorgehensweise: Erstellen eines semantischen Indexes, wenn ein voll Text Index vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="17ce7-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="17ce7-149">Sie können die semantische Indizierung hinzufügen, wenn Sie einen vorhandenen Volltextindex mit der **ALTER FULLTEXT INDEX** -Anweisung ändern.</span><span class="sxs-lookup"><span data-stu-id="17ce7-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="17ce7-150">Sie können die semantische Indizierung auch mithilfe verschiedener Dialogfelder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="17ce7-151">**Hinzufügen eines semantischen Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="17ce7-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="17ce7-152">Rufen Sie für jede Spalte, in der Sie einen semantischen Index hinzufügen möchten, die **ALTER FULLTEXT INDEX**-Anweisung mit den unten beschriebenen Optionen auf.</span><span class="sxs-lookup"><span data-stu-id="17ce7-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="17ce7-153">Weitere Informationen zu allen Optionen für diese Anweisung finden Sie unter [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17ce7-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="17ce7-154">Sofern Sie nichts anderes angegeben haben, werden sowohl Volltext- als auch semantische Indizes nach einem Aufruf von **ALTER** erneut aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="17ce7-155">Um einer Spalte nur Volltextindizierung hinzuzufügen, verwenden Sie die **ADD** -Syntax.</span><span class="sxs-lookup"><span data-stu-id="17ce7-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="17ce7-156">Um einer Spalte sowohl Volltext- als auch semantische Indizierung hinzuzufügen, verwenden Sie die **ADD** -Syntax mit der **STATISTICAL_SEMANTICS** -Option.</span><span class="sxs-lookup"><span data-stu-id="17ce7-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="17ce7-157">Um einer Spalte, die bereits für Volltextindizierung aktiviert wurde, eine semantische Indizierung hinzuzufügen, verwenden Sie die **ADD STATISTICAL_SEMANTICS** -Option.</span><span class="sxs-lookup"><span data-stu-id="17ce7-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="17ce7-158">In einer einzigen **ALTER** -Anweisung können Sie einer Spalte nur semantische Indizierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="17ce7-159">**Beispiel: Hinzufügen von semantischer Indizierung zu einer Spalte, die bereits eine Volltextindizierung aufweist**</span><span class="sxs-lookup"><span data-stu-id="17ce7-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="17ce7-160">Im folgenden Beispiel wird ein vorhandener Volltextindex für die **Production.Document** -Tabelle in der AdventureWorks2012-Beispieldatenbank geändert.</span><span class="sxs-lookup"><span data-stu-id="17ce7-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="17ce7-161">Im Beispiel wird ein semantischer Index in der Spalte **Document** der Tabelle **Production.Document** hinzugefügt, die bereits einen Volltextindex hat.</span><span class="sxs-lookup"><span data-stu-id="17ce7-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="17ce7-162">Das Beispiel gibt an, dass der Index nicht automatisch erneut aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="17ce7-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="17ce7-163">**Hinzufügen eines semantischen Indexes mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="17ce7-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="17ce7-164">Sie können die Spalten, die für die semantische Indizierung und die Volltextindizierung verfügbar sind, auf der Seite **Volltextindexspalten** des Dialogfelds **Volltextindex-Eigenschaften** ändern.</span><span class="sxs-lookup"><span data-stu-id="17ce7-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="17ce7-165">Weitere Informationen finden Sie unter [Verwalten von Volltextindizes](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="17ce7-166">Anforderungen und Einschränkungen beim Ändern eines vorhandenen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="17ce7-167">Sie können einen vorhandenen Index nicht ändern, während die Auffüllung des Indexes ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17ce7-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="17ce7-168">Weitere Informationen zum Überwachen des Status der Indexauffüllung finden Sie unter [Verwalten und Überwachen der semantischen Suche](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="17ce7-169">Sie können in einem einzigen Aufruf der **ALTER FULLTEXT INDEX** -Anweisung einer Spalte keine Indizierung hinzufügen und die Indizierung für dieselbe Spalte ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="17ce7-170">Löschen eines semantischen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="17ce7-171">Vorgehensweise: Löschen eines semantischen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="17ce7-172">Sie können die semantische Indizierung löschen, wenn Sie einen vorhandenen Volltextindex mit der **ALTER FULLTEXT INDEX** -Anweisung ändern.</span><span class="sxs-lookup"><span data-stu-id="17ce7-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="17ce7-173">Sie können die semantische Indizierung auch mithilfe verschiedener Dialogfelder in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="17ce7-174">**Löschen eines semantischen Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="17ce7-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="17ce7-175">Rufen Sie zum ausschließlichen Löschen der semantischen Indizierung aus Spalten die **ALTER FULLTEXT INDEX** -Anweisung mit der Option **ALTER COLUMN***Spaltenname***DROP STATISTICAL_SEMANTICS** auf.</span><span class="sxs-lookup"><span data-stu-id="17ce7-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="17ce7-176">Sie können die Indizierung in einer einzigen **ALTER** -Anweisung aus mehreren Spalten löschen.</span><span class="sxs-lookup"><span data-stu-id="17ce7-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="17ce7-177">Rufen Sie zum Löschen der Volltextindizierung und der semantischen Indizierung aus einer Spalte die **ALTER FULLTEXT INDEX**-Anweisung mit der Option **ALTER COLUMN***Spaltenname***DROP** auf.</span><span class="sxs-lookup"><span data-stu-id="17ce7-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="17ce7-178">**Löschen eines semantischen Indexes mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="17ce7-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="17ce7-179">Sie können die Spalten, die für die semantische Indizierung und die Volltextindizierung verfügbar sind, auf der Seite **Volltextindexspalten** des Dialogfelds **Volltextindex-Eigenschaften** ändern.</span><span class="sxs-lookup"><span data-stu-id="17ce7-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="17ce7-180">Weitere Informationen finden Sie unter [Verwalten von Volltextindizes](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="17ce7-181">Anforderungen und Einschränkungen für das Löschen eines semantischen Indexes</span><span class="sxs-lookup"><span data-stu-id="17ce7-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="17ce7-182">Sie können die Volltextindizierung nicht aus einer Spalte löschen, während Sie die semantische Indizierung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="17ce7-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="17ce7-183">Die semantische Indizierung ist für Dokumentähnlichkeitsergebnisse von der Volltextindizierung abhängig.</span><span class="sxs-lookup"><span data-stu-id="17ce7-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="17ce7-184">Sie können die **NO POPULATION** -Option nicht angeben, wenn Sie die semantische Indizierung aus der letzten Spalte in einer Tabelle löschen, für die die semantische Indizierung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="17ce7-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="17ce7-185">Zur Entfernung der Ergebnisse, die zuvor indiziert wurden, ist ein Auffüllungszyklus erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17ce7-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="17ce7-186">Überprüfen, ob die semantische Suche für Datenbankobjekte aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="17ce7-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="17ce7-187">Gewusst wie: überprüfen, ob die semantische Suche für Datenbankobjekte aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="17ce7-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="17ce7-188">**Ist die semantische Suche für eine Datenbank aktiviert?**</span><span class="sxs-lookup"><span data-stu-id="17ce7-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="17ce7-189">Fragen Sie die Eigenschaft **IsFullTextEnabled** der Metadatenfunktion [DATABASEPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="17ce7-190">Der Rückgabewert 1 gibt an, dass die Volltextsuche und die semantische Suche für die Datenbank aktiviert sind; der Rückgabewert 0 gibt an, dass sie nicht aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="17ce7-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="17ce7-191">**Ist die semantische Suche für eine Tabelle aktiviert?**</span><span class="sxs-lookup"><span data-stu-id="17ce7-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="17ce7-192">Fragen Sie die Eigenschaft **TableFullTextSemanticExtraction** der Metadatenfunktion [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="17ce7-193">Der Rückgabewert 1 gibt an, dass die semantische Suche für die Tabelle aktiviert ist; der Rückgabewert 0 gibt an, dass sie nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17ce7-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="17ce7-194">**Ist die semantische Suche für eine Spalte aktiviert?**</span><span class="sxs-lookup"><span data-stu-id="17ce7-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="17ce7-195">So bestimmen Sie, ob die semantische Suche für eine bestimmte Spalte aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="17ce7-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="17ce7-196">Fragen Sie die Eigenschaft **StatisticalSemantics** der Metadatenfunktion [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="17ce7-197">Der Rückgabewert 1 gibt an, dass die semantische Suche für die Spalte aktiviert ist; der Rückgabewert 0 gibt an, dass sie nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17ce7-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="17ce7-198">Fragen Sie die Katalogsicht [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) für den Volltextindex ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="17ce7-199">Der Wert 1 in der **statistical_semantics**-Spalte gibt an, dass die angegebene Spalte zusätzlich zur Volltextindizierung für die semantische Indizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17ce7-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="17ce7-200">Klicken Sie im Objekt-Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf eine Spalte, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="17ce7-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="17ce7-201">Überprüfen Sie auf der Seite **Allgemein** des Dialogfelds **Spalteneigenschaften** den Wert der Eigenschaft **Statistical Semantics** .</span><span class="sxs-lookup"><span data-stu-id="17ce7-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="17ce7-202">Der Wert TRUE gibt an, dass die angegebene Spalte zusätzlich zur Volltextindizierung für die semantische Indizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="17ce7-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="17ce7-203">Ermitteln der indizierbaren Objekte für die semantische Suche</span><span class="sxs-lookup"><span data-stu-id="17ce7-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="17ce7-204">Gewusst wie: überprüfen, welche Sprachen für die semantische Suche unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="17ce7-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="17ce7-205">Für die semantische Indizierung werden weniger Sprachen als für die Volltextindizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="17ce7-206">Es gibt daher möglicherweise Spalten, die für die Volltextsuche, aber nicht für die semantische Suche indiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="17ce7-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="17ce7-207">Fragen Sie die Katalogsicht [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="17ce7-208">Für die semantische Indizierung werden die folgenden Sprachen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="17ce7-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="17ce7-209">Dieses Liste stellt die Ausgabe der Katalogsicht [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql) nach der LCID sortiert dar.</span><span class="sxs-lookup"><span data-stu-id="17ce7-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="17ce7-210">Sprache</span><span class="sxs-lookup"><span data-stu-id="17ce7-210">Language</span></span>|<span data-ttu-id="17ce7-211">LCID</span><span class="sxs-lookup"><span data-stu-id="17ce7-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="17ce7-212">Deutsch</span><span class="sxs-lookup"><span data-stu-id="17ce7-212">German</span></span>|<span data-ttu-id="17ce7-213">1031</span><span class="sxs-lookup"><span data-stu-id="17ce7-213">1031</span></span>|  
|<span data-ttu-id="17ce7-214">Englisch (USA)</span><span class="sxs-lookup"><span data-stu-id="17ce7-214">English (US)</span></span>|<span data-ttu-id="17ce7-215">1033</span><span class="sxs-lookup"><span data-stu-id="17ce7-215">1033</span></span>|  
|<span data-ttu-id="17ce7-216">Französisch</span><span class="sxs-lookup"><span data-stu-id="17ce7-216">French</span></span>|<span data-ttu-id="17ce7-217">1036</span><span class="sxs-lookup"><span data-stu-id="17ce7-217">1036</span></span>|  
|<span data-ttu-id="17ce7-218">Italienisch</span><span class="sxs-lookup"><span data-stu-id="17ce7-218">Italian</span></span>|<span data-ttu-id="17ce7-219">1040</span><span class="sxs-lookup"><span data-stu-id="17ce7-219">1040</span></span>|  
|<span data-ttu-id="17ce7-220">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="17ce7-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="17ce7-221">1046</span><span class="sxs-lookup"><span data-stu-id="17ce7-221">1046</span></span>|  
|<span data-ttu-id="17ce7-222">Russisch</span><span class="sxs-lookup"><span data-stu-id="17ce7-222">Russian</span></span>|<span data-ttu-id="17ce7-223">1049</span><span class="sxs-lookup"><span data-stu-id="17ce7-223">1049</span></span>|  
|<span data-ttu-id="17ce7-224">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="17ce7-224">Swedish</span></span>|<span data-ttu-id="17ce7-225">1053</span><span class="sxs-lookup"><span data-stu-id="17ce7-225">1053</span></span>|  
|<span data-ttu-id="17ce7-226">English (UK)</span><span class="sxs-lookup"><span data-stu-id="17ce7-226">English (UK)</span></span>|<span data-ttu-id="17ce7-227">2057</span><span class="sxs-lookup"><span data-stu-id="17ce7-227">2057</span></span>|  
|<span data-ttu-id="17ce7-228">Portugiesisch (Portugal)</span><span class="sxs-lookup"><span data-stu-id="17ce7-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="17ce7-229">2070</span><span class="sxs-lookup"><span data-stu-id="17ce7-229">2070</span></span>|  
|<span data-ttu-id="17ce7-230">Spanisch</span><span class="sxs-lookup"><span data-stu-id="17ce7-230">Spanish</span></span>|<span data-ttu-id="17ce7-231">3082</span><span class="sxs-lookup"><span data-stu-id="17ce7-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="17ce7-232">Gewusst wie: bestimmen, welche Dokumenttypen indiziert werden können</span><span class="sxs-lookup"><span data-stu-id="17ce7-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="17ce7-233">Fragen Sie die Katalogsicht [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql) ab.</span><span class="sxs-lookup"><span data-stu-id="17ce7-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="17ce7-234">Wenn der zu indizierende Dokumenttyp nicht in der Liste der unterstützten Typen aufgeführt wird, müssen Sie möglicherweise zusätzliche Filter suchen, herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="17ce7-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="17ce7-235">Weitere Informationen finden Sie unter [anzeigen oder Ändern von registrierten filtern und Wörtertrennungen](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="17ce7-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="17ce7-236">Bewährte Vorgehensweise: Erstellen einer separaten Datei Gruppe für die Volltext-und semantischen Indizes</span><span class="sxs-lookup"><span data-stu-id="17ce7-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="17ce7-237">Erwägen Sie, eine separate Dateigruppe für den Volltext- und den semantischen Index zu erstellen, wenn Sie Bedenken im Hinblick auf die Speicherplatzzuordnung haben.</span><span class="sxs-lookup"><span data-stu-id="17ce7-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="17ce7-238">Die semantischen Indizes werden in derselben Dateigruppe wie der Volltextindex erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ce7-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="17ce7-239">Ein vollständig aufgefüllter semantischer Index kann eine große Datenmenge enthalten.</span><span class="sxs-lookup"><span data-stu-id="17ce7-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="17ce7-240">Problem: das Durchsuchen einer bestimmten Spalte gibt keine Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="17ce7-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="17ce7-241">**Wurde eine Nicht-Unicode-LCID für eine Unicode-Sprache angegeben?**</span><span class="sxs-lookup"><span data-stu-id="17ce7-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="17ce7-242">Es ist möglich, die semantische Indizierung für einen Nicht-Unicode-Spaltentyp mit einer LCID für eine Sprache zu aktivieren, die nur Unicode-Wörter aufweist, z. B. LCID 1049 für Russisch.</span><span class="sxs-lookup"><span data-stu-id="17ce7-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="17ce7-243">In diesem Fall werden nie Ergebnisse von den semantischen Indizes in dieser Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17ce7-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
