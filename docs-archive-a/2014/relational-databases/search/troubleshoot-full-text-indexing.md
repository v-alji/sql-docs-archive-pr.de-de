---
title: Behandeln von Problemen mit der Volltextindizierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622514"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="d6f19-102">Behandeln von Problemen mit der Volltextindizierung</span><span class="sxs-lookup"><span data-stu-id="d6f19-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="d6f19-103">Beheben von Fehlern bei der Volltextindizierung</span><span class="sxs-lookup"><span data-stu-id="d6f19-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="d6f19-104">Beim Auffüllen oder Verwalten eines Volltextindexes werden vom Volltextindexer aus den unten beschriebenen Gründen möglicherweise eine oder mehrere Zeilen nicht indiziert.</span><span class="sxs-lookup"><span data-stu-id="d6f19-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="d6f19-105">Diese Fehler auf Zeilenebene verhindern nicht, dass die Auffüllung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d6f19-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="d6f19-106">Diese Zeilen werden vom Indexer ausgelassen, was bedeutet, dass Sie anschließend keine in diesen Zeilen enthaltenen Inhalte abfragen können.</span><span class="sxs-lookup"><span data-stu-id="d6f19-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="d6f19-107">Indizierungsfehler können in folgenden Fällen auftreten:</span><span class="sxs-lookup"><span data-stu-id="d6f19-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="d6f19-108">Vom Indexer kann eine Filter- oder Wörtertrennungskomponente nicht gefunden oder geladen werden.</span><span class="sxs-lookup"><span data-stu-id="d6f19-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="d6f19-109">Dieser Fehler kann auftreten, wenn die Tabellenzeile ein Dokumentformat oder Inhalte in einer Sprache enthält, die bei der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nicht registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6f19-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d6f19-110">Zu diesem Fehler kann es auch kommen, wenn die registrierte Wörtertrennungs- oder Filterungskomponente nicht signiert wurde oder die Signaturprüfung beim Laden fehlschlug.</span><span class="sxs-lookup"><span data-stu-id="d6f19-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="d6f19-111">Eine Komponente wie eine Wörtertrennung oder ein Filter schlägt fehl und gibt dem Indexer einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="d6f19-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="d6f19-112">Dies kann vorkommen, wenn das indizierte Dokument beschädigt ist und der Filter keinen Text aus dem Dokument extrahieren kann.</span><span class="sxs-lookup"><span data-stu-id="d6f19-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="d6f19-113">Dazu kann es auch kommen, wenn eine Komponente den Inhalt einer einzelnen Zeile oberhalb einer bestimmten Größe aufgrund von Arbeitsspeicherlimits beim Host des Volltextfilterdaemons (fdhost.exe) nicht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d6f19-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="d6f19-114">Für jeden Fehler auf Zeilenebene enthält das Durchforstungsprotokoll Details zum Grund des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="d6f19-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="d6f19-115">Die Fehleranzahl wird am Ende einer vollständigen oder inkrementellen Auffüllung zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="d6f19-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="d6f19-116">Es gibt noch weitere Fehler, die den Indizierungsprozess selbst beeinträchtigen können und verhindern, dass die Auffüllung beendet wird:</span><span class="sxs-lookup"><span data-stu-id="d6f19-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="d6f19-117">Der Volltextindex überschreitet die maximale Anzahl von Zeilen, die in einem Volltextkatalog enthalten sein dürfen.</span><span class="sxs-lookup"><span data-stu-id="d6f19-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="d6f19-118">Ein gruppierter Index oder Volltextschlüsselindex in der indizierten Tabelle wird geändert, gelöscht oder neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="d6f19-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="d6f19-119">Ein Hardwarefehler oder eine Datenträgerbeschädigung führt zur Beschädigung des Volltextkatalogs.</span><span class="sxs-lookup"><span data-stu-id="d6f19-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="d6f19-120">Eine Dateigruppe, die die Tabelle enthält, für die der Volltextindex erstellt werden soll, wird offline genommen oder auf schreibgeschützt gesetzt.</span><span class="sxs-lookup"><span data-stu-id="d6f19-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="d6f19-121">Sie sollten das Durchforstungsprotokoll am Ende eines wichtigen Volltext-Indexauffüllungsvorgangs anzeigen oder aber dann, wenn eine Auffüllung nicht beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d6f19-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="d6f19-122">Unsignierte Komponenten</span><span class="sxs-lookup"><span data-stu-id="d6f19-122">Unsigned Components</span></span>  
 <span data-ttu-id="d6f19-123">Standardmäßig müssen vom Volltextindexer geladene Filter und Wörtertrennungen signiert sein.</span><span class="sxs-lookup"><span data-stu-id="d6f19-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="d6f19-124">Wenn sie nicht signiert sind, was manchmal der Fall  ist, wenn benutzerdefinierte Komponenten installiert werden, müssen Sie den Volltextindexer so konfigurieren, dass die Signaturprüfung ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="d6f19-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d6f19-125">Das Ignorieren der Signaturprüfung macht die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weniger sicher.</span><span class="sxs-lookup"><span data-stu-id="d6f19-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="d6f19-126">Es empfiehlt sich, von Ihnen implementierte Komponenten zu signieren oder sicherzustellen, dass von Ihnen erworbene Komponenten signiert sind.</span><span class="sxs-lookup"><span data-stu-id="d6f19-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="d6f19-127">Informationen zum Signieren von Komponenten finden Sie unter [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d6f19-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="d6f19-128">Volltextindex nach der Wiederherstellung eines Transaktionsprotokolls inkonsistent</span><span class="sxs-lookup"><span data-stu-id="d6f19-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="d6f19-129">Beim Wiederherstellen des Transaktionsprotokolls einer Datenbank wird möglicherweise eine Warnung angezeigt, die besagt, dass sich der Volltextindex nicht in einem konsistenten Status befindet.</span><span class="sxs-lookup"><span data-stu-id="d6f19-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="d6f19-130">Der Grund ist, dass der Volltextindex für eine Tabelle nach der Sicherung der Datenbank geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6f19-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="d6f19-131">Sie müssen eine vollständige Auffüllung (Durchforstung) für die Tabelle ausführen, um den Volltextindex in einen konsistenten Status zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="d6f19-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="d6f19-132">Weitere Informationen finden Sie unter [Auffüllen von Volltextindizes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="d6f19-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="d6f19-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6f19-133">See Also</span></span>  
 <span data-ttu-id="d6f19-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6f19-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="d6f19-135">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="d6f19-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
