---
title: MSSQLSERVER_3619 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620890"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="da597-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="da597-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="da597-103">Details</span><span class="sxs-lookup"><span data-stu-id="da597-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da597-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="da597-104">Product Name</span></span>|<span data-ttu-id="da597-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="da597-105">SQL Server</span></span>|  
|<span data-ttu-id="da597-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="da597-106">Event ID</span></span>|<span data-ttu-id="da597-107">3619</span><span class="sxs-lookup"><span data-stu-id="da597-107">3619</span></span>|  
|<span data-ttu-id="da597-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="da597-108">Event Source</span></span>|<span data-ttu-id="da597-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="da597-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="da597-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="da597-110">Component</span></span>|<span data-ttu-id="da597-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="da597-111">SQLEngine</span></span>|  
|<span data-ttu-id="da597-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="da597-112">Symbolic Name</span></span>|<span data-ttu-id="da597-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="da597-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="da597-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="da597-114">Message Text</span></span>|<span data-ttu-id="da597-115">In die Datenbank mit der ID %d konnte kein Prüfpunktdatensatz geschrieben werden, da für das Protokoll kein Speicherplatz mehr zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="da597-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="da597-116">Bitten Sie den Datenbankadministrator, das Protokoll abzuschneiden oder den Datenbankprotokolldateien mehr Speicherplatz zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="da597-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="da597-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="da597-117">Explanation</span></span>  
 <span data-ttu-id="da597-118">Für das Transaktionsprotokoll steht kein Speicherplatz mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="da597-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da597-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="da597-119">User Action</span></span>  
 <span data-ttu-id="da597-120">Schneiden Sie das Protokoll ab, um Speicherplatz freizugeben, oder ordnen Sie dem Protokoll mehr Speicherplatz zu.</span><span class="sxs-lookup"><span data-stu-id="da597-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="da597-121">Weitere Informationen finden Sie unter "Problembehandlung bei vollen Transaktionsprotokollen (Fehler 9002)" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="da597-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
