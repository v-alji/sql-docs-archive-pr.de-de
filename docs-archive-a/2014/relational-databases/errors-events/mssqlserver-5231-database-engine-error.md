---
title: MSSQLSERVER_5231 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696862"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="bb2b2-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="bb2b2-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="bb2b2-103">Details</span><span class="sxs-lookup"><span data-stu-id="bb2b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bb2b2-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="bb2b2-104">Product Name</span></span>|<span data-ttu-id="bb2b2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bb2b2-105">SQL Server</span></span>|  
|<span data-ttu-id="bb2b2-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="bb2b2-106">Event ID</span></span>|<span data-ttu-id="bb2b2-107">5231</span><span class="sxs-lookup"><span data-stu-id="bb2b2-107">5231</span></span>|  
|<span data-ttu-id="bb2b2-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="bb2b2-108">Event Source</span></span>|<span data-ttu-id="bb2b2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bb2b2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bb2b2-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="bb2b2-110">Component</span></span>|<span data-ttu-id="bb2b2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bb2b2-111">SQLEngine</span></span>|  
|<span data-ttu-id="bb2b2-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="bb2b2-112">Symbolic Name</span></span>|<span data-ttu-id="bb2b2-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="bb2b2-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="bb2b2-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="bb2b2-114">Message Text</span></span>|<span data-ttu-id="bb2b2-115">Objekt-ID „O_ID“ (Objekt „NAME“): Deadlock beim Versuch, dieses Objekt für die Überprüfung zu sperren.</span><span class="sxs-lookup"><span data-stu-id="bb2b2-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="bb2b2-116">Das Objekt wurde ausgelassen und wird nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bb2b2-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bb2b2-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="bb2b2-117">Explanation</span></span>  
 <span data-ttu-id="bb2b2-118">Es kam zu einem Deadlock, als von DBCC versucht wurde, das Objekt zu sperren. DBCC wurde als Deadlockopfer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="bb2b2-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="bb2b2-119">Das Objekt wird nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="bb2b2-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb2b2-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="bb2b2-120">User Action</span></span>  
 <span data-ttu-id="bb2b2-121">Keine</span><span class="sxs-lookup"><span data-stu-id="bb2b2-121">None</span></span>  
  
  
