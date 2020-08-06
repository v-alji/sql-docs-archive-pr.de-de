---
title: MSSQLSERVER_2530 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608730"
---
# <a name="mssqlserver_2530"></a><span data-ttu-id="44a65-102">MSSQLSERVER_2530</span><span class="sxs-lookup"><span data-stu-id="44a65-102">MSSQLSERVER_2530</span></span>
    
## <a name="details"></a><span data-ttu-id="44a65-103">Details</span><span class="sxs-lookup"><span data-stu-id="44a65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44a65-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="44a65-104">Product Name</span></span>|<span data-ttu-id="44a65-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44a65-105">SQL Server</span></span>|  
|<span data-ttu-id="44a65-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="44a65-106">Event ID</span></span>|<span data-ttu-id="44a65-107">2530</span><span class="sxs-lookup"><span data-stu-id="44a65-107">2530</span></span>|  
|<span data-ttu-id="44a65-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="44a65-108">Event Source</span></span>|<span data-ttu-id="44a65-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="44a65-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="44a65-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="44a65-110">Component</span></span>|<span data-ttu-id="44a65-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="44a65-111">SQLEngine</span></span>|  
|<span data-ttu-id="44a65-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="44a65-112">Symbolic Name</span></span>|<span data-ttu-id="44a65-113">DBCC_INDEX_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="44a65-113">DBCC_INDEX_IS_OFFLINE</span></span>|  
|<span data-ttu-id="44a65-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="44a65-114">Message Text</span></span>|<span data-ttu-id="44a65-115">Der „%.\*ls“-Index für die „%.\*ls“-Tabelle ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="44a65-115">The index "%.\*ls" on table "%.\*ls" is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="44a65-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="44a65-116">Explanation</span></span>  
 <span data-ttu-id="44a65-117">Die DBCC-Anweisung kann nicht fortfahren, da der angegebene Index deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="44a65-117">The DBCC statement cannot proceed because the specified index is disabled.</span></span> <span data-ttu-id="44a65-118">Nachdem ein Index deaktiviert wurde, verbleibt er in einem deaktivierten Status, bis er neu erstellt oder gelöscht und erneut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="44a65-118">After an index is disabled, it remains in a disabled state until it is rebuilt or dropped and re-created.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="44a65-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="44a65-119">User Action</span></span>  
  
1.  <span data-ttu-id="44a65-120">Aktivieren Sie den deaktivierten Index mit einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="44a65-120">Enable the disabled index by using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="44a65-121">ALTER INDEX-Anweisung mit der REBUILD-Klausel</span><span class="sxs-lookup"><span data-stu-id="44a65-121">ALTER INDEX statement with the REBUILD clause</span></span>  
  
    -   <span data-ttu-id="44a65-122">CREATE INDEX mit der DROP_EXISTING-Klausel</span><span class="sxs-lookup"><span data-stu-id="44a65-122">CREATE INDEX with the DROP_EXISTING clause</span></span>  
  
    -   <span data-ttu-id="44a65-123">DBCC DBREINDEX</span><span class="sxs-lookup"><span data-stu-id="44a65-123">DBCC DBREINDEX</span></span>  
  
2.  <span data-ttu-id="44a65-124">Führen Sie die DBCC-Anweisung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="44a65-124">Rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a65-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44a65-125">See Also</span></span>  
 <span data-ttu-id="44a65-126">[Aktivieren von Indizes und Einschränkungen](../indexes/enable-indexes-and-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="44a65-126">[Enable Indexes and Constraints](../indexes/enable-indexes-and-constraints.md) </span></span>  
 <span data-ttu-id="44a65-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44a65-127">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="44a65-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="44a65-128">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="44a65-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="44a65-129">DBCC DBREINDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
