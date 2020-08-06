---
title: MSSQLSERVER_30053 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 8ad23889-e243-4bd7-bc3e-150403399d89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 02d6262f93ef3dbbc9834053f864046b4dca30f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618036"
---
# <a name="mssqlserver_30053"></a><span data-ttu-id="d4040-102">MSSQLSERVER_30053</span><span class="sxs-lookup"><span data-stu-id="d4040-102">MSSQLSERVER_30053</span></span>
    
## <a name="details"></a><span data-ttu-id="d4040-103">Details</span><span class="sxs-lookup"><span data-stu-id="d4040-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4040-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d4040-104">Product Name</span></span>|<span data-ttu-id="d4040-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4040-105">SQL Server</span></span>|  
|<span data-ttu-id="d4040-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d4040-106">Event ID</span></span>|<span data-ttu-id="d4040-107">30053</span><span class="sxs-lookup"><span data-stu-id="d4040-107">30053</span></span>|  
|<span data-ttu-id="d4040-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d4040-108">Event Source</span></span>|<span data-ttu-id="d4040-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d4040-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d4040-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d4040-110">Component</span></span>|<span data-ttu-id="d4040-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d4040-111">SQLEngine</span></span>|  
|<span data-ttu-id="d4040-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d4040-112">Symbolic Name</span></span>|<span data-ttu-id="d4040-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4040-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span></span>|  
|<span data-ttu-id="d4040-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d4040-114">Message Text</span></span>|<span data-ttu-id="d4040-115">Timeout bei der Wörtertrennung für die Volltextabfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d4040-115">Word breaking timed out for the full-text query string.</span></span> <span data-ttu-id="d4040-116">Dies kann passieren, wenn die Verarbeitung der Volltextabfragezeichenfolge lange dauert oder eine große Anzahl von Abfragen auf dem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4040-116">This can happen if the wordbreaker took a long time to process the full-text query string, or if a large number of queries are running on the server.</span></span> <span data-ttu-id="d4040-117">Führen Sie die Abfrage bei geringerer Auslastung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d4040-117">Try running the query again under a lighter load.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4040-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d4040-118">Explanation</span></span>  
 <span data-ttu-id="d4040-119">In den folgenden Fällen kann es zu Timeoutfehlern bei der Wörtertrennung kommen:</span><span class="sxs-lookup"><span data-stu-id="d4040-119">A word-breaking timeout error can occur in the following situations:</span></span>  
  
-   <span data-ttu-id="d4040-120">Die Wörtertrennung für die Abfragesprache ist falsch konfiguriert; z. B. sind die entsprechenden Registrierungseinstellungen falsch.</span><span class="sxs-lookup"><span data-stu-id="d4040-120">The word breaker for the query language is configured incorrectly; for example, its registry settings are incorrect.</span></span>  
  
-   <span data-ttu-id="d4040-121">Die Wörtertrennung schlägt bei einer bestimmten Abfragezeichenfolge fehl.</span><span class="sxs-lookup"><span data-stu-id="d4040-121">The word breaker malfunctions for a specific query string.</span></span>  
  
-   <span data-ttu-id="d4040-122">Die Wörtertrennung gibt bei einer bestimmten Abfragezeichenfolge zu viele Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="d4040-122">The word breaker returns too much data for a specific query string.</span></span> <span data-ttu-id="d4040-123">Diese Daten werden als möglicher Angriff in Form eines Pufferüberlaufs interpretiert, was dafür sorgt, dass der für die Ausführung der Wörtertrennungsdienste verantwortliche Filterdaemonprozess (fdhost.exe) beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d4040-123">Excess data is treated as a potential buffer overrun attack, and shuts down the filter daemon process (fdhost.exe), which hosts the word-breaking services.</span></span>  
  
-   <span data-ttu-id="d4040-124">Der Filterdaemonprozess wurde falsch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d4040-124">The filter daemon process configuration is incorrect.</span></span>  
  
     <span data-ttu-id="d4040-125">Zu den häufigsten Konfigurationsproblemen gehören abgelaufene Kennwörter oder Domänenrichtlinien, die eine Anmeldung am Filterdaemonkonto verhindern.</span><span class="sxs-lookup"><span data-stu-id="d4040-125">The most common configuration problems are password expiration or a domain policy that prevents the filter daemon account from logging on.</span></span>  
  
-   <span data-ttu-id="d4040-126">Auf der Serverinstanz wird eine sehr große Abfragelast ausgeführt, z. B. dauert die Verarbeitung der Volltextabfragezeichenfolge sehr lange, oder es wird eine große Anzahl von Abfragen auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4040-126">A very heavy query workload is running on the server instance; for example, the word-breaker took a long time to process the full-text query string, or a large number of queries are running on the server.</span></span> <span data-ttu-id="d4040-127">Dies ist die wahrscheinliche Ursache.</span><span class="sxs-lookup"><span data-stu-id="d4040-127">Note that this is the least likely cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4040-128">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d4040-128">User Action</span></span>  
 <span data-ttu-id="d4040-129">Wählen Sie wie folgt die Benutzeraktion aus, die der wahrscheinlichen Ursache des Timeouts entspricht:</span><span class="sxs-lookup"><span data-stu-id="d4040-129">Select the user action that is appropriate to the probable cause of the timeout, as follows:</span></span>  
  
|<span data-ttu-id="d4040-130">Wahrscheinliche Ursache</span><span class="sxs-lookup"><span data-stu-id="d4040-130">Probable cause</span></span>|<span data-ttu-id="d4040-131">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d4040-131">User action</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d4040-132">Die Wörtertrennung ist für die Abfragesprache nicht richtig konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d4040-132">The word breaker for the query language is configured incorrectly.</span></span>|<span data-ttu-id="d4040-133">Wenn Sie die Wörtertrennung eines Drittanbieters verwenden, ist sie möglicherweise auf dem Betriebssystem falsch registriert.</span><span class="sxs-lookup"><span data-stu-id="d4040-133">If you are using a third-party word breaker it might be incorrectly registered with the operating system.</span></span> <span data-ttu-id="d4040-134">Registrieren Sie die Wörtertrennung in diesem Fall erneut.</span><span class="sxs-lookup"><span data-stu-id="d4040-134">In this case, re-register the word breaker.</span></span> <span data-ttu-id="d4040-135">Weitere Informationen finden Sie unter [Wiederherstellen der von der Suche verwendeten Wörtertrennungen auf die vorherige Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span><span class="sxs-lookup"><span data-stu-id="d4040-135">For more information, see [Revert the Word Breakers Used by Search to the Previous Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span></span>|  
|<span data-ttu-id="d4040-136">Die Wörtertrennung schlägt bei einer bestimmten Abfragezeichenfolge fehl.</span><span class="sxs-lookup"><span data-stu-id="d4040-136">The word breaker malfunctions for a specific query string.</span></span>|<span data-ttu-id="d4040-137">Wenn die Wörtertrennung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt wird, wenden Sie sich an den Microsoft-Kundenservice und -support.</span><span class="sxs-lookup"><span data-stu-id="d4040-137">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="d4040-138">Die Wörtertrennung gibt bei einer bestimmten Abfragezeichenfolge zu viele Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="d4040-138">The word breaker returns too much data for a specific query string.</span></span>|<span data-ttu-id="d4040-139">Wenn die Wörtertrennung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt wird, wenden Sie sich an den Microsoft-Kundenservice und -support.</span><span class="sxs-lookup"><span data-stu-id="d4040-139">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="d4040-140">Der Filterdaemonprozess wurde falsch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d4040-140">The filter daemon process configuration is incorrect.</span></span>|<span data-ttu-id="d4040-141">Stellen Sie sicher, dass Sie das aktuelle Kennwort verwenden und dass die Anmeldung unter dem Filterdaemonkonto nicht von einer Domänenrichtlinie verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="d4040-141">Ensure that you are using the current password and that a domain policy is not preventing the filter daemon account from logging on.</span></span>|  
|<span data-ttu-id="d4040-142">Auf der Serverinstanz wird eine große Abfragelast ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4040-142">A very heavy query workload is running on the server instance.</span></span>|<span data-ttu-id="d4040-143">Führen Sie die Abfrage bei geringerer Auslastung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d4040-143">Try running the query again under a lighter load.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4040-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4040-144">See Also</span></span>  
 <span data-ttu-id="d4040-145">[Festlegen des Dienst Kontos für das Start Programm des Volltextfilterdaemons](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="d4040-145">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="d4040-146">[Volltextsuche](../search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="d4040-146">[Full-Text Search](../search/full-text-search.md) </span></span>  
 <span data-ttu-id="d4040-147">[sp_help_fulltext_system_components &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d4040-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="d4040-148">[Konfigurieren und Verwalten von Wörter Trennungen und Wort Stamm Erkennungen für die Suche](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="d4040-148">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="d4040-149">Konfigurieren und Verwalten von Filtern für die Suche</span><span class="sxs-lookup"><span data-stu-id="d4040-149">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
