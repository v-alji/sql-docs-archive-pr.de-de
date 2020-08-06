---
title: MSSQLSERVER_30089 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d0b9c71ea620174f993ae87befed8a21bb3d0bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618031"
---
# <a name="mssqlserver_30089"></a><span data-ttu-id="8dafa-102">MSSQLSERVER_30089</span><span class="sxs-lookup"><span data-stu-id="8dafa-102">MSSQLSERVER_30089</span></span>
    
## <a name="details"></a><span data-ttu-id="8dafa-103">Details</span><span class="sxs-lookup"><span data-stu-id="8dafa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8dafa-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8dafa-104">Product Name</span></span>|<span data-ttu-id="8dafa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8dafa-105">SQL Server</span></span>|  
|<span data-ttu-id="8dafa-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8dafa-106">Event ID</span></span>|<span data-ttu-id="8dafa-107">30089</span><span class="sxs-lookup"><span data-stu-id="8dafa-107">30089</span></span>|  
|<span data-ttu-id="8dafa-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8dafa-108">Event Source</span></span>|<span data-ttu-id="8dafa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8dafa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8dafa-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8dafa-110">Component</span></span>|<span data-ttu-id="8dafa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8dafa-111">SQLEngine</span></span>|  
|<span data-ttu-id="8dafa-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8dafa-112">Symbolic Name</span></span>|<span data-ttu-id="8dafa-113">IFTS_FDHOST_TERMINATEDABNORMAL</span><span class="sxs-lookup"><span data-stu-id="8dafa-113">IFTS_FDHOST_TERMINATEDABNORMAL</span></span>|  
|<span data-ttu-id="8dafa-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8dafa-114">Message Text</span></span>|<span data-ttu-id="8dafa-115">Der Hostprozess des Volltextfilterdaemons (FDHost) wurde fehlerbedingt beendet.</span><span class="sxs-lookup"><span data-stu-id="8dafa-115">The fulltext filter daemon host (FDHost) process has stopped abnormally.</span></span> <span data-ttu-id="8dafa-116">Dieser Fehler kann auftreten, wenn eine falsch konfigurierte oder nicht ordnungsgemäß funktionierende linguistische Komponente, wie z. B. eine Wörtertrennung, eine Wortstammerkennung oder ein Filter, bei der Volltextindizierung oder Abfrageverarbeitung einen nicht behebbaren Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="8dafa-116">This can occur if an incorrectly configured or malfunctioning linguistic component, such as a wordbreaker, stemmer or filter has caused an irrecoverable error during full-text indexing or query processing.</span></span> <span data-ttu-id="8dafa-117">Der Prozess wird automatisch neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="8dafa-117">The process will be restarted automatically.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8dafa-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8dafa-118">Explanation</span></span>  
 <span data-ttu-id="8dafa-119">Der Host des Volltextfilterdaemons hat ein Problem erkannt, wodurch der Prozess fehlerbedingt beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8dafa-119">The full-text filter daemon host has encountered some problem that has forced it to stop abnormally.</span></span> <span data-ttu-id="8dafa-120">Die Ursache des Problems kann ein falsch formatiertes Dokument, ein Fehler im Filter oder in der Wörtertrennung oder ein Fehler im Filterdaemon sein.</span><span class="sxs-lookup"><span data-stu-id="8dafa-120">The cause of the problem could be a badly formatted document, a bug in the filter or word-breaker, or a problem in filter daemon.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8dafa-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8dafa-121">User Action</span></span>  
 <span data-ttu-id="8dafa-122">Normalerweise wird der Daemon wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8dafa-122">Typically, the daemon will recover from the error.</span></span> <span data-ttu-id="8dafa-123">Wenn der Fehler weiterhin auftritt, ist eine Problembehandlung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dafa-123">If it is consistently failing, troubleshooting is necessary.</span></span> <span data-ttu-id="8dafa-124">Versuchen Sie Folgendes, um das Problem zu isolieren:</span><span class="sxs-lookup"><span data-stu-id="8dafa-124">Try the following to isolate the issue:</span></span>  
  
1.  <span data-ttu-id="8dafa-125">Wenn kürzlich eine neue linguistische Komponente installiert wurde, entfernen Sie diese vom System.</span><span class="sxs-lookup"><span data-stu-id="8dafa-125">If a new linguistic component has been installed recently, remove it from the system.</span></span>  
  
2.  <span data-ttu-id="8dafa-126">Suchen Sie im Durchforstungsprotokoll nach neuen Dokumenten, bei deren Volltextindizierung ein Fehler aufgetreten ist, und entfernen Sie diese Dokumente.</span><span class="sxs-lookup"><span data-stu-id="8dafa-126">Look at the crawl log to identify any new document that failed to be full-text indexed, and remove it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dafa-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8dafa-127">See Also</span></span>  
 <span data-ttu-id="8dafa-128">[sp_help_fulltext_system_components &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8dafa-128">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="8dafa-129">[Konfigurieren und Verwalten von Wörter Trennungen und Wort Stamm Erkennungen für die Suche](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="8dafa-129">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="8dafa-130">Konfigurieren und Verwalten von Filtern für die Suche</span><span class="sxs-lookup"><span data-stu-id="8dafa-130">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
