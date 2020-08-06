---
title: MSSQLSERVER_3437 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620891"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="ecf58-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="ecf58-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="ecf58-103">Details</span><span class="sxs-lookup"><span data-stu-id="ecf58-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ecf58-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ecf58-104">Product Name</span></span>|<span data-ttu-id="ecf58-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ecf58-105">SQL Server</span></span>|  
|<span data-ttu-id="ecf58-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ecf58-106">Event ID</span></span>|<span data-ttu-id="ecf58-107">3437</span><span class="sxs-lookup"><span data-stu-id="ecf58-107">3437</span></span>|  
|<span data-ttu-id="ecf58-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ecf58-108">Event Source</span></span>|<span data-ttu-id="ecf58-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ecf58-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ecf58-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ecf58-110">Component</span></span>|<span data-ttu-id="ecf58-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ecf58-111">SQLEngine</span></span>|  
|<span data-ttu-id="ecf58-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="ecf58-112">Symbolic Name</span></span>|<span data-ttu-id="ecf58-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="ecf58-113">NODTC</span></span>|  
|<span data-ttu-id="ecf58-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ecf58-114">Message Text</span></span>|<span data-ttu-id="ecf58-115">Fehler beim Wiederherstellen der '%.\*ls'-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ecf58-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="ecf58-116">Es konnte keine Verbindung mit Microsoft Distributed Transaction Coordinator (MS DTC) hergestellt werden, um den Beendigungsstatus von Transaktion %S_XID zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ecf58-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="ecf58-117">Korrigieren Sie MS DTC, und führen Sie die Wiederherstellung erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ecf58-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ecf58-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ecf58-118">Explanation</span></span>  
 <span data-ttu-id="ecf58-119">Eine oder mehrere verteilte Transaktionen, für die MS DTC ([!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator) verwendet wurde, waren nicht abgeschlossen, als die Datenbank beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ecf58-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="ecf58-120">Bei der Wiederherstellung dieser Datenbank sind Fehler aufgetreten, da in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] keine Verbindung mit MS DTC hergestellt werden kann, um die Transaktionen abzuschließen oder einen Rollback für die Transaktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecf58-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ecf58-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ecf58-121">User Action</span></span>  
 <span data-ttu-id="ecf58-122">Zum Wiederherstellen dieser Datenbank müssen Sie zunächst das Problem mit MS DTC lösen.</span><span class="sxs-lookup"><span data-stu-id="ecf58-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="ecf58-123">Weitere Informationen zu diesem Problem mit MS DTC finden Sie in den Windows-Ereignisprotokollen.</span><span class="sxs-lookup"><span data-stu-id="ecf58-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="ecf58-124">Wenn das Problem mit MS DTC nicht gelöst und die Datenbank nicht wiederhergestellt werden kann, führen Sie die Wiederherstellung einer Sicherungskopie der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="ecf58-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
