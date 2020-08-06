---
title: MSSQLSERVER_2511 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2511 (Database Engine error)
ms.assetid: 9a00c0ed-eb4b-4fae-8016-192396006c37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23e91b0d64140329639cf57f3a336cd2eab8e4e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699638"
---
# <a name="mssqlserver_2511"></a><span data-ttu-id="b6df0-102">MSSQLSERVER_2511</span><span class="sxs-lookup"><span data-stu-id="b6df0-102">MSSQLSERVER_2511</span></span>
    
## <a name="details"></a><span data-ttu-id="b6df0-103">Details</span><span class="sxs-lookup"><span data-stu-id="b6df0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6df0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b6df0-104">Product Name</span></span>|<span data-ttu-id="b6df0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6df0-105">SQL Server</span></span>|  
|<span data-ttu-id="b6df0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b6df0-106">Event ID</span></span>|<span data-ttu-id="b6df0-107">2511</span><span class="sxs-lookup"><span data-stu-id="b6df0-107">2511</span></span>|  
|<span data-ttu-id="b6df0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b6df0-108">Event Source</span></span>|<span data-ttu-id="b6df0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b6df0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b6df0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b6df0-110">Component</span></span>|<span data-ttu-id="b6df0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b6df0-111">SQLEngine</span></span>|  
|<span data-ttu-id="b6df0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b6df0-112">Symbolic Name</span></span>|<span data-ttu-id="b6df0-113">DBCC_KEYS_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="b6df0-113">DBCC_KEYS_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="b6df0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b6df0-114">Message Text</span></span>|<span data-ttu-id="b6df0-115">Tabellenfehler: Objekt-ID %d, Index-ID %d, Partitions-ID %I64d, Zuordnungseinheits-ID %I64d (%.\*ls-Typ).</span><span class="sxs-lookup"><span data-stu-id="b6df0-115">Table error: Object ID %d, index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls).</span></span> <span data-ttu-id="b6df0-116">Falsche Schlüsselreihenfolge auf Seite %S_PGID, Slots %d und %d.</span><span class="sxs-lookup"><span data-stu-id="b6df0-116">Keys out of order on page %S_PGID, slots %d and %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b6df0-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b6df0-117">Explanation</span></span>  
 <span data-ttu-id="b6df0-118">Im angegebenen Index wurden Schlüssel mit falscher Reihenfolge erkannt.</span><span class="sxs-lookup"><span data-stu-id="b6df0-118">Out-of-order keys were detected in the specified index.</span></span> <span data-ttu-id="b6df0-119">Die Seite, in der die Schlüssel enthalten sind, ist möglicherweise beschädigt.</span><span class="sxs-lookup"><span data-stu-id="b6df0-119">The page in which the keys are contained may be corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b6df0-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b6df0-120">User Action</span></span>  
 <span data-ttu-id="b6df0-121">Erstellen Sie den angegebenen Index mithilfe der ALTER INDEX REBUILD-Anweisung neu.</span><span class="sxs-lookup"><span data-stu-id="b6df0-121">Rebuild the specified index by using the ALTER INDEX REBUILD statement.</span></span>  
  
  
