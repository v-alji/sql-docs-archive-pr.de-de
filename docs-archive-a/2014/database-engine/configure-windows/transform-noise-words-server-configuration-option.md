---
title: Füllwörtertransformation (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- full-text queries [SQL Server], performance
- transform noise words option
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 69bd388e-a86c-4de4-b5d5-d093424d9c57
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 49de4a381de3e998073a73c284e3e3e5960f4921
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723025"
---
# <a name="transform-noise-words-server-configuration-option"></a><span data-ttu-id="2b432-102">Füllwörtertransformation (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="2b432-102">transform noise words Server Configuration Option</span></span>
  <span data-ttu-id="2b432-103">Verwenden `transform noise words` Sie die Server Konfigurationsoption, um eine Fehlermeldung zu unterdrücken, wenn Füll Wörter, d. [h. Stoppwörter](../../relational-databases/search/full-text-search.md), bewirken, dass eine boolesche Operation für eine Volltextabfrage 0 Zeilen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b432-103">Use the `transform noise words` server configuration option to suppress an error message if noise words, that is [stopwords](../../relational-databases/search/full-text-search.md), cause a Boolean operation on a full-text query to return zero rows.</span></span> <span data-ttu-id="2b432-104">Diese Option ist für Volltextabfragen nützlich, bei denen das CONTAINS-Prädikat verwendet wird, in dem boolesche oder NEAR-Operationen Füllwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b432-104">This option is useful for full-text queries that use the CONTAINS predicate in which Boolean operations or NEAR operations include noise words.</span></span> <span data-ttu-id="2b432-105">Eine Beschreibung der möglichen Werte finden Sie in der folgenden Tabelle:</span><span class="sxs-lookup"><span data-stu-id="2b432-105">The possible values are described in the following table.</span></span>  
  
|<span data-ttu-id="2b432-106">Wert</span><span class="sxs-lookup"><span data-stu-id="2b432-106">Value</span></span>|<span data-ttu-id="2b432-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2b432-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2b432-108">0</span><span class="sxs-lookup"><span data-stu-id="2b432-108">0</span></span>|<span data-ttu-id="2b432-109">Füllwörter (oder Stoppwörter) werden nicht umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2b432-109">Noise words (or stopwords) are not transformed.</span></span> <span data-ttu-id="2b432-110">Wenn eine Volltextabfrage Füllwörter enthält, gibt die Abfrage 0 Zeilen zurück und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] löst eine Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="2b432-110">When a full-text query contains noise words, the query returns zero rows, and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] raises a warning.</span></span> <span data-ttu-id="2b432-111">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="2b432-111">This is the default behavior.</span></span><br /><br /> <span data-ttu-id="2b432-112">Beachten Sie, dass die Warnung eine Laufzeitwarnung ist.</span><span class="sxs-lookup"><span data-stu-id="2b432-112">Note that the warning is a run-time warning.</span></span> <span data-ttu-id="2b432-113">Die Warnung wird daher nicht ausgegeben, wenn die Volltextklausel in der Abfrage nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b432-113">Therefore, if the full-text clause in the query is not executed, the warning is not raised.</span></span> <span data-ttu-id="2b432-114">Bei lokalen Abfragen wird auch bei mehreren Volltextabfrageklauseln immer nur eine einzige Warnung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b432-114">For a local query, only one warning is raised, even when there are multiple full-text query clauses.</span></span> <span data-ttu-id="2b432-115">Bei Remoteabfragen übermittelt der Verbindungsserver u. U. den Fehler nicht, und die Warnung wird daher möglicherweise nicht ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b432-115">For a remote query, the linked server might not relay the error; therefore, the warning might not be raised.</span></span>|  
|<span data-ttu-id="2b432-116">1</span><span class="sxs-lookup"><span data-stu-id="2b432-116">1</span></span>|<span data-ttu-id="2b432-117">Füllwörter (oder Stoppwörter) werden umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2b432-117">Noise words (or stopwords) are transformed.</span></span> <span data-ttu-id="2b432-118">Sie werden ignoriert, und der Rest der Abfrage wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="2b432-118">They are ignored, and the rest of the query is evaluated.</span></span><br /><br /> <span data-ttu-id="2b432-119">Wenn Füllwörter in einem NEAR-Begriff angegeben werden, werden sie von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entfernt.</span><span class="sxs-lookup"><span data-stu-id="2b432-119">If noise words are specified in a proximity term, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] removes them.</span></span> <span data-ttu-id="2b432-120">Das Füllwort `is` wird beispielsweise aus `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`entfernt, und die Suchabfrage wird in `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="2b432-120">For example, the noise word `is` is removed from `CONTAINS(<column_name>, 'NEAR (hello,is,goodbye)')`, transforming the search query into `CONTAINS(<column_name>, 'NEAR(hello,goodbye)')`.</span></span> <span data-ttu-id="2b432-121">Beachten Sie, dass `CONTAINS(<column_name>, 'NEAR(hello,is)')` einfach in `CONTAINS(<column_name>, hello)` umgewandelt werden würde, da es nur einen gültigen Suchbegriff gibt.</span><span class="sxs-lookup"><span data-stu-id="2b432-121">Notice that `CONTAINS(<column_name>, 'NEAR(hello,is)')` would be transformed into simply `CONTAINS(<column_name>, hello)` because there is only one valid search term.</span></span>|  
  
## <a name="effects-of-the-transform-noise-words-setting"></a><span data-ttu-id="2b432-122">Auswirkungen der Einstellung von „Füllwörtertransformation“</span><span class="sxs-lookup"><span data-stu-id="2b432-122">Effects of the transform noise words Setting</span></span>  
 <span data-ttu-id="2b432-123">In diesem Abschnitt wird das Verhalten von Abfragen mit dem Füllwort "`the`" unter den alternativen Einstellungen von `transform noise words` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2b432-123">This section illustrates the behavior of queries containing a noise word, "`the`", under the alternate settings of `transform noise words`.</span></span>  <span data-ttu-id="2b432-124">Für die Beispielzeichenfolgen für Volltextabfragen wird angenommen, dass sie in einer Tabellenzeile mit den folgenden Daten ausgeführt werden: `[1, "The black cat"]`.</span><span class="sxs-lookup"><span data-stu-id="2b432-124">The sample full-text query strings are assumed to be run against a table row containing the following data: `[1, "The black cat"]`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b432-125">Alle derartigen Szenarien können eine Füllwortwarnung generieren.</span><span class="sxs-lookup"><span data-stu-id="2b432-125">All such scenarios can generate a noise word warning.</span></span>  
  
-   <span data-ttu-id="2b432-126">Mit „Füllwörtertransformation“ auf „0“ festgelegt:</span><span class="sxs-lookup"><span data-stu-id="2b432-126">With transform noise words set to 0:</span></span>  
  
    |<span data-ttu-id="2b432-127">Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b432-127">Query string</span></span>|<span data-ttu-id="2b432-128">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2b432-128">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="2b432-129">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-129">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="2b432-130">Keine Ergebnisse (das Verhalten ist für "`the`" AND "`cat`" genau gleich.)</span><span class="sxs-lookup"><span data-stu-id="2b432-130">No results (The behavior is the same for "`the`" AND "`cat`".)</span></span>|  
    |<span data-ttu-id="2b432-131">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-131">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="2b432-132">Keine Ergebnisse (das Verhalten ist für "`the`" NEAR "`cat`" genau gleich.)</span><span class="sxs-lookup"><span data-stu-id="2b432-132">No results (The behavior is the same for "`the`" NEAR "`cat`".)</span></span>|  
    |<span data-ttu-id="2b432-133">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="2b432-133">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="2b432-134">Keine Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="2b432-134">No results</span></span>|  
    |<span data-ttu-id="2b432-135">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-135">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="2b432-136">Keine Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="2b432-136">No results</span></span>|  
  
-   <span data-ttu-id="2b432-137">Mit „Füllwörtertransformation“ auf „1“ festgelegt:</span><span class="sxs-lookup"><span data-stu-id="2b432-137">With transform noise words set to 1:</span></span>  
  
    |<span data-ttu-id="2b432-138">Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2b432-138">Query string</span></span>|<span data-ttu-id="2b432-139">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2b432-139">Result</span></span>|  
    |------------------|------------|  
    |<span data-ttu-id="2b432-140">"`cat`" AND "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-140">"`cat`" AND "`the`"</span></span>|<span data-ttu-id="2b432-141">Treffer für Zeile mit ID 1</span><span class="sxs-lookup"><span data-stu-id="2b432-141">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="2b432-142">"`cat`" NEAR "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-142">"`cat`" NEAR "`the`"</span></span>|<span data-ttu-id="2b432-143">Treffer für Zeile mit ID 1</span><span class="sxs-lookup"><span data-stu-id="2b432-143">Hit for row with ID 1</span></span>|  
    |<span data-ttu-id="2b432-144">"`the`" AND NOT "`black`"</span><span class="sxs-lookup"><span data-stu-id="2b432-144">"`the`" AND NOT "`black`"</span></span>|<span data-ttu-id="2b432-145">Keine Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="2b432-145">No results</span></span>|  
    |<span data-ttu-id="2b432-146">"`black`" AND NOT "`the`"</span><span class="sxs-lookup"><span data-stu-id="2b432-146">"`black`" AND NOT "`the`"</span></span>|<span data-ttu-id="2b432-147">Treffer für Zeile mit ID 1</span><span class="sxs-lookup"><span data-stu-id="2b432-147">Hit for row with ID 1</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b432-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b432-148">Example</span></span>  
 <span data-ttu-id="2b432-149">Mit dem folgenden Beispiel wird `transform noise words` auf `1` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b432-149">The following example sets `transform noise words` to `1`.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
GO  
sp_configure 'transform noise words', 1;  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b432-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b432-150">See Also</span></span>  
 <span data-ttu-id="2b432-151">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2b432-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2b432-152">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b432-152">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
