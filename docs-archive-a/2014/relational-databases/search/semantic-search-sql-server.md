---
title: Semantische Suche (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719807"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="0dcab-102">Semantische Suche (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0dcab-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="0dcab-103">Die statistische semantische Suche liefert einen tiefen Einblick in unstrukturierte Dokumente, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken gespeichert sind, indem statistisch relevante *Schlüsselausdrücke*extrahiert und indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="0dcab-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="0dcab-104">Anschließend werden diese Schlüsselausdrücke verwendet, um *ähnliche oder verwandte Dokumente*zu identifizieren und zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="0dcab-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="0dcab-105">Sie fragen diese semantischen Indizes mit drei Transact-SQL-Rowsetfunktionen ab, um die Ergebnisse als strukturierte Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="0dcab-106">Was kann ich mit der semantischen Suche tun?</span><span class="sxs-lookup"><span data-stu-id="0dcab-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="0dcab-107">Die semantische Suche basiert auf der vorhandenen Volltextsuchfunktion in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ermöglicht jedoch neue Szenarien, die über Schlüsselwortsuchen hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="0dcab-108">Während Sie bei der Volltextsuche *Wörter* in einem Dokument abfragen können, können Sie bei der *semantischen* Suche die Bedeutung des Dokuments abfragen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="0dcab-109">Die jetzt möglichen Lösungen umfassen die automatische Tagextraktion, die Ermittlung von verwandten Inhalten sowie die hierarchische Navigation über ähnlichen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="0dcab-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="0dcab-110">Sie können beispielsweise den Index von Schlüsselausdrücken abfragen, um die Taxonomie für eine Organisation oder für einen Korpus von Dokumenten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="0dcab-111">Oder sie können den Dokumentähnlichkeitsindex abfragen, um Lebensläufe zu identifizieren, die einer Arbeitsplatzbeschreibung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="0dcab-112">In den folgenden Beispielen sind die Funktionen der semantischen Suche dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0dcab-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="0dcab-113">Suchen der Schlüssel Ausdrücke in einem Dokument</span><span class="sxs-lookup"><span data-stu-id="0dcab-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="0dcab-114">Die folgende Abfrage ruft die Schlüsselausdrücke ab, die im Beispieldokument identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="0dcab-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="0dcab-115">Sie präsentiert die Ergebnisse in absteigender Reihenfolge nach dem Grad der statistischen Bedeutung der einzelnen Schlüsselausdrücke.</span><span class="sxs-lookup"><span data-stu-id="0dcab-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="0dcab-116">Diese Abfrage ruft die Funktion [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) auf.</span><span class="sxs-lookup"><span data-stu-id="0dcab-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="0dcab-117">Suchen von ähnlichen oder verwandten Dokumenten</span><span class="sxs-lookup"><span data-stu-id="0dcab-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="0dcab-118">Die folgende Abfrage ruft die Dokumente ab, die als dem Beispieldokument ähnlich oder damit verwandt identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="0dcab-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="0dcab-119">Sie präsentiert die Ergebnisse in absteigender Reihenfolge nach dem Grad der Ähnlichkeit von zwei Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="0dcab-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="0dcab-120">Diese Abfrage ruft die Funktion [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) auf.</span><span class="sxs-lookup"><span data-stu-id="0dcab-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="0dcab-121">Suchen der Schlüssel Ausdrücke, die Dokumente ähnlich oder verwandt machen</span><span class="sxs-lookup"><span data-stu-id="0dcab-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="0dcab-122">Die folgende Abfrage ruft die Schlüsselausdrücke ab, die zwei Beispieldokumente ähnlich oder verwandt machen.</span><span class="sxs-lookup"><span data-stu-id="0dcab-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="0dcab-123">Sie präsentiert die Ergebnisse in absteigender Reihenfolge nach dem Grad, der die Gewichtung der einzelnen Schlüsselausdrücke angibt.</span><span class="sxs-lookup"><span data-stu-id="0dcab-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="0dcab-124">Diese Abfrage ruft die Funktion [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) auf.</span><span class="sxs-lookup"><span data-stu-id="0dcab-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="0dcab-125">Speichern von Dokumenten in SQL Server</span><span class="sxs-lookup"><span data-stu-id="0dcab-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="0dcab-126">Bevor Sie Dokumente mit der semantischen Suche indizieren können, müssen Sie die Dokumente in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="0dcab-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="0dcab-127">Die FileTable-Funktion in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] macht unstrukturierte Dateien und Dokument zu so genannten "First Class Citizens" (FCCs) der relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0dcab-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="0dcab-128">Folglich können Datenbankentwickler Dokumente zusammen mit strukturierten Daten in Transact-SQL-basierten Vorgängen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0dcab-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="0dcab-129">Weitere Informationen zu der FileTable-Funktion finden Sie unter [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0dcab-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="0dcab-130">Informationen zur FILESTREAM-Funktion, die eine andere Option zum Speichern von Dokumenten in der Datenbank ist, finden Sie unter [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0dcab-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="0dcab-131">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="0dcab-131">Related Tasks</span></span>  
 [<span data-ttu-id="0dcab-132">Installieren und Konfigurieren der semantischen Suche</span><span class="sxs-lookup"><span data-stu-id="0dcab-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="0dcab-133">Beschreibt die erforderlichen Komponenten für die statistische semantische Suche und wie diese Komponenten installiert oder überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0dcab-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="0dcab-134">Aktivieren der semantischen Suche in Tabellen und Spalten</span><span class="sxs-lookup"><span data-stu-id="0dcab-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="0dcab-135">Beschreibt, wie die statistische semantische Indizierung für ausgewählte Spalten, die Dokumente oder Text enthalten, aktiviert bzw. deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="0dcab-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="0dcab-136">Suchen von Schlüsselausdrücken in Dokumenten mit der semantischen Suche</span><span class="sxs-lookup"><span data-stu-id="0dcab-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="0dcab-137">Beschreibt, wie Schlüsselausdrücke in Dokumenten oder Textspalten gesucht werden, die für die statistische semantische Indizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0dcab-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="0dcab-138">Suchen von ähnlichen und verwandten Dokumenten mit semantischer Suche</span><span class="sxs-lookup"><span data-stu-id="0dcab-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="0dcab-139">Beschreibt, wie ähnliche oder verwandte Dokumente oder Textwerte sowie Informationen zur Ähnlichkeit oder Verwandtschaft über Spalten gesucht werden, die für die statistische semantische Indizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="0dcab-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="0dcab-140">Verwalten und Überwachen der semantischen Suche</span><span class="sxs-lookup"><span data-stu-id="0dcab-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="0dcab-141">Beschreibt den Prozess der semantischen Indizierung sowie die Tasks im Zusammenhang mit der Überwachung und Verwaltung der Indizes.</span><span class="sxs-lookup"><span data-stu-id="0dcab-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="0dcab-142">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="0dcab-142">Related Content</span></span>  
 [<span data-ttu-id="0dcab-143">Semantische Such-DDL, Funktionen, gespeicherte Prozeduren und Sichten</span><span class="sxs-lookup"><span data-stu-id="0dcab-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="0dcab-144">Führt die zur Unterstützung der semantischen Suche hinzugefügten oder geänderten Transact-SQL-Anweisungen und SQL Server-Datenbankobjekte auf.</span><span class="sxs-lookup"><span data-stu-id="0dcab-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
