---
title: Volltext-Stopp Listen-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622832"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="a9367-102">Volltext-Stopplisten-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a9367-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="a9367-103">Verwenden Sie dieses Dialogfeld, um einzelne Stoppwörter hinzuzufügen oder zu löschen, um alle Stoppwörter für eine bestimmte Sprache zu löschen oder um die aktuelle Stoppliste zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a9367-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="a9367-104">Ein Stoppwort ist ein häufig verwendetes Wort, das in eine Stoppliste aufgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="a9367-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="a9367-105">Die Stoppwörter in einer Stoppliste werden bei der Volltextindizierung für Tabellen, die diese Stoppliste verwenden, ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="a9367-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="a9367-106">Weitere Informationen finden sie unter [Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="a9367-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="a9367-107">**So verwenden Sie SQL Server Management Studio zum Ändern der Stopplisteneigenschaften**</span><span class="sxs-lookup"><span data-stu-id="a9367-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="a9367-108">Konfigurieren und Verwalten von Stoppwörtern und Stopplisten für Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="a9367-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="a9367-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a9367-109">Options</span></span>  
 <span data-ttu-id="a9367-110">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="a9367-110">**Action**</span></span>  
 <span data-ttu-id="a9367-111">Gibt die Aktion an, die Sie durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="a9367-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="a9367-112">**Stoppwort hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="a9367-112">**Add stopword**</span></span>  
 <span data-ttu-id="a9367-113">Fügt der Stoppliste ein häufig verwendetes Wort hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9367-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="a9367-114">**Stoppwort löschen**</span><span class="sxs-lookup"><span data-stu-id="a9367-114">**Delete stopword**</span></span>  
 <span data-ttu-id="a9367-115">Löscht ein Stoppwort aus der Stoppliste.</span><span class="sxs-lookup"><span data-stu-id="a9367-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="a9367-116">**Alle Stoppwörter löschen**</span><span class="sxs-lookup"><span data-stu-id="a9367-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="a9367-117">Löscht alle Stoppwörter für eine bestimmte Sprache.</span><span class="sxs-lookup"><span data-stu-id="a9367-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="a9367-118">**Inhalt der Stoppliste löschen**</span><span class="sxs-lookup"><span data-stu-id="a9367-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="a9367-119">Löscht die Stoppliste, indem alle Stoppwörter für alle Sprachen gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a9367-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="a9367-120">**Stoppwort**</span><span class="sxs-lookup"><span data-stu-id="a9367-120">**Stopword**</span></span>  
 <span data-ttu-id="a9367-121">Wenn Sie **Stoppwort hinzufügen** oder **Stoppwort löschen**ausgewählt haben, geben Sie das Stoppwort im Feld **Stoppwort** ein.</span><span class="sxs-lookup"><span data-stu-id="a9367-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="a9367-122">Ein neues Stoppwort muss eindeutig sein; das heißt, es darf noch nicht in dieser Stoppliste für die Sprache, die Sie auswählen, enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a9367-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="a9367-123">**Volltextsprache**</span><span class="sxs-lookup"><span data-stu-id="a9367-123">**Full-text language**</span></span>  
 <span data-ttu-id="a9367-124">Wenn Sie **Stoppwort hinzufügen**, **Stoppwort löschen**oder **Alle Stoppwörter löschen**ausgewählt haben, wählen Sie die Sprache des Stoppworts bzw. der Stoppwörter aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a9367-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="a9367-125">Diese Liste umfasst alle Volltextsprachen, die von der Serverinstanz unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a9367-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9367-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9367-126">See Also</span></span>  
 <span data-ttu-id="a9367-127">[sys. fulltext_stopwords &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9367-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="a9367-128">[sys. fulltext_stoplists &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9367-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="a9367-129">[Konfigurieren und Verwalten von Stopp Wörtern und Stopp Listen für die voll Text Suche](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="a9367-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="a9367-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9367-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="a9367-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL-&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a9367-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="a9367-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a9367-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
