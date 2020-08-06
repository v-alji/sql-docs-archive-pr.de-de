---
title: MSSQLSERVER_7911 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7911 (Database Engine error)
ms.assetid: dd8390f3-0f77-4fb2-ba94-631a56e42bc6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d37ce2dc11f231e8a6f8ae6cc8b95d8b2f87c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617998"
---
# <a name="mssqlserver_7911"></a><span data-ttu-id="c45c3-102">MSSQLSERVER_7911</span><span class="sxs-lookup"><span data-stu-id="c45c3-102">MSSQLSERVER_7911</span></span>
    
## <a name="details"></a><span data-ttu-id="c45c3-103">Details</span><span class="sxs-lookup"><span data-stu-id="c45c3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c45c3-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c45c3-104">Product Name</span></span>|<span data-ttu-id="c45c3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c45c3-105">SQL Server</span></span>|  
|<span data-ttu-id="c45c3-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c45c3-106">Event ID</span></span>|<span data-ttu-id="c45c3-107">7911</span><span class="sxs-lookup"><span data-stu-id="c45c3-107">7911</span></span>|  
|<span data-ttu-id="c45c3-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c45c3-108">Event Source</span></span>|<span data-ttu-id="c45c3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c45c3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c45c3-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c45c3-110">Component</span></span>|<span data-ttu-id="c45c3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c45c3-111">SQLEngine</span></span>|  
|<span data-ttu-id="c45c3-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c45c3-112">Symbolic Name</span></span>|<span data-ttu-id="c45c3-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span><span class="sxs-lookup"><span data-stu-id="c45c3-113">DBCC2_REPAIR_PAGE_DEALLOCATED</span></span>|  
|<span data-ttu-id="c45c3-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c45c3-114">Message Text</span></span>|<span data-ttu-id="c45c3-115">Reparaturvorgang: Die Zuordnung der Seite P_ID zu Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (Typ TYPE) wurde aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="c45c3-115">Repair: The page P_ID has been deallocated from object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c45c3-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c45c3-116">Explanation</span></span>  
 <span data-ttu-id="c45c3-117">Dies ist eine Informationsmeldung von REPAIR, die besagt, dass die Zuordnung einer Seite zu dem einseitigen Slotarray einer IAM-Seite (Index Allocation Map) aufgehoben wurde.</span><span class="sxs-lookup"><span data-stu-id="c45c3-117">This is an informational message from REPAIR that states that a page has been deallocated from the single-page slot array of an Index Allocation Map (IAM) page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c45c3-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c45c3-118">User Action</span></span>  
 <span data-ttu-id="c45c3-119">Keine</span><span class="sxs-lookup"><span data-stu-id="c45c3-119">None</span></span>  
  
  
