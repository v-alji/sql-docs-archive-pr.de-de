---
title: MSSQLSERVER_5245 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620883"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="610e6-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="610e6-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="610e6-103">Details</span><span class="sxs-lookup"><span data-stu-id="610e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="610e6-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="610e6-104">Product Name</span></span>|<span data-ttu-id="610e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="610e6-105">SQL Server</span></span>|  
|<span data-ttu-id="610e6-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="610e6-106">Event ID</span></span>|<span data-ttu-id="610e6-107">5245</span><span class="sxs-lookup"><span data-stu-id="610e6-107">5245</span></span>|  
|<span data-ttu-id="610e6-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="610e6-108">Event Source</span></span>|<span data-ttu-id="610e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="610e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="610e6-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="610e6-110">Component</span></span>|<span data-ttu-id="610e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="610e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="610e6-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="610e6-112">Symbolic Name</span></span>|<span data-ttu-id="610e6-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="610e6-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="610e6-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="610e6-114">Message Text</span></span>|<span data-ttu-id="610e6-115">Objekt-ID „O_ID“ (Objekt „NAME“): DBCC konnte keine Sperre für das Objekt erhalten, da das Timeout für die Sperranforderung überschritten wurde.</span><span class="sxs-lookup"><span data-stu-id="610e6-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="610e6-116">Das Objekt wurde ausgelassen und wird nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="610e6-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="610e6-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="610e6-117">Explanation</span></span>  
 <span data-ttu-id="610e6-118">Ein Sperrtimeout ist aufgetreten, während DBCC auf eine Tabellensperre für das angegebene Objekt gewartet hat.</span><span class="sxs-lookup"><span data-stu-id="610e6-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="610e6-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="610e6-119">User Action</span></span>  
 <span data-ttu-id="610e6-120">Führen Sie den DBCC-Befehl erneut aus.</span><span class="sxs-lookup"><span data-stu-id="610e6-120">Rerun the DBCC command.</span></span>  
  
  
