---
title: MSSQLSERVER_3431 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620896"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="58ddc-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="58ddc-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="58ddc-103">Details</span><span class="sxs-lookup"><span data-stu-id="58ddc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58ddc-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="58ddc-104">Product Name</span></span>|<span data-ttu-id="58ddc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="58ddc-105">SQL Server</span></span>|  
|<span data-ttu-id="58ddc-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="58ddc-106">Event ID</span></span>|<span data-ttu-id="58ddc-107">3431</span><span class="sxs-lookup"><span data-stu-id="58ddc-107">3431</span></span>|  
|<span data-ttu-id="58ddc-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="58ddc-108">Event Source</span></span>|<span data-ttu-id="58ddc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="58ddc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="58ddc-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="58ddc-110">Component</span></span>|<span data-ttu-id="58ddc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="58ddc-111">SQLEngine</span></span>|  
|<span data-ttu-id="58ddc-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="58ddc-112">Symbolic Name</span></span>|<span data-ttu-id="58ddc-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="58ddc-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="58ddc-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="58ddc-114">Message Text</span></span>|<span data-ttu-id="58ddc-115">Die '%.\*ls'-Datenbank (Datenbank-ID %d) konnte aufgrund von nicht aufgelösten Transaktionsergebnissen nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="58ddc-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="58ddc-116">MS DTC-Transaktionen (Microsoft Distributed Transaction Coordinator) wurden vorbereitet, aber MS DTC konnte die Auflösung nicht bestimmen.</span><span class="sxs-lookup"><span data-stu-id="58ddc-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="58ddc-117">Zum Auflösen müssen Sie MS DTC reparieren, eine Wiederherstellung von einer vollständigen Sicherung ausführen oder die Datenbank reparieren.</span><span class="sxs-lookup"><span data-stu-id="58ddc-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="58ddc-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="58ddc-118">Explanation</span></span>  
 <span data-ttu-id="58ddc-119">Eine oder mehrere verteilte Transaktionen, für die MS DTC ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) verwendet wurde, waren nicht abgeschlossen, als die Datenbank beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="58ddc-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="58ddc-120">Bei der Wiederherstellung dieser Datenbank sind Fehler aufgetreten, da die Transaktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht abgeschlossen werden können bzw. ohne weitere Informationen von MS DTC kein Rollback für die Transaktionen ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="58ddc-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="58ddc-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="58ddc-121">User Action</span></span>  
 <span data-ttu-id="58ddc-122">Zum Wiederherstellen dieser Datenbank müssen Sie zunächst das Problem mit MS DTC lösen.</span><span class="sxs-lookup"><span data-stu-id="58ddc-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="58ddc-123">Weitere Informationen zu diesem Problem mit MS DTC finden Sie in den Windows-Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="58ddc-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="58ddc-124">Wenn das Problem mit MS DTC nicht gelöst und die Datenbank nicht wiederhergestellt werden kann, führen Sie die Wiederherstellung einer Sicherungskopie der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="58ddc-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
