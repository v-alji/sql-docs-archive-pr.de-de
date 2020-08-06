---
title: MSSQLSERVER_17803 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17803 (Database Engine error)
ms.assetid: 28591a19-258d-4891-b78a-4686789bb2d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8be63b3d05bff2ebf90122f66af4297d77376fce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620929"
---
# <a name="mssqlserver_17803"></a><span data-ttu-id="8cc24-102">MSSQLSERVER_17803</span><span class="sxs-lookup"><span data-stu-id="8cc24-102">MSSQLSERVER_17803</span></span>
    
## <a name="details"></a><span data-ttu-id="8cc24-103">Details</span><span class="sxs-lookup"><span data-stu-id="8cc24-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cc24-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="8cc24-104">Product Name</span></span>|<span data-ttu-id="8cc24-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8cc24-105">SQL Server</span></span>|  
|<span data-ttu-id="8cc24-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="8cc24-106">Event ID</span></span>|<span data-ttu-id="8cc24-107">17803</span><span class="sxs-lookup"><span data-stu-id="8cc24-107">17803</span></span>|  
|<span data-ttu-id="8cc24-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="8cc24-108">Event Source</span></span>|<span data-ttu-id="8cc24-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8cc24-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8cc24-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="8cc24-110">Component</span></span>|<span data-ttu-id="8cc24-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8cc24-111">SQLEngine</span></span>|  
|<span data-ttu-id="8cc24-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="8cc24-112">Symbolic Name</span></span>|<span data-ttu-id="8cc24-113">SRV_NOMEMORY</span><span class="sxs-lookup"><span data-stu-id="8cc24-113">SRV_NOMEMORY</span></span>|  
|<span data-ttu-id="8cc24-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8cc24-114">Message Text</span></span>|<span data-ttu-id="8cc24-115">Bei der Verbindungsherstellung ist ein Fehler bei der Speicherbelegung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8cc24-115">There was a memory allocation failure during connection establishment.</span></span> <span data-ttu-id="8cc24-116">Reduzieren Sie die vermeidbare Arbeitsspeicherlast, oder vergrößern Sie den Systemarbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8cc24-116">Reduce nonessential memory load, or increase system memory.</span></span> <span data-ttu-id="8cc24-117">Die Verbindung wurde geschlossen.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="8cc24-117">The connection has been closed.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8cc24-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8cc24-118">Explanation</span></span>  
 <span data-ttu-id="8cc24-119">Der Server verfügt nicht über genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8cc24-119">Server is running out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8cc24-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8cc24-120">User Action</span></span>  
 <span data-ttu-id="8cc24-121">Bestimmen Sie, warum der Server nicht über genügend Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cc24-121">Determine the cause for server running out of memory.</span></span> <span data-ttu-id="8cc24-122">Allgemeine Schritte zur Behandlung von Problemen mit dem Arbeitsspeicher sind möglicherweise nützlich.</span><span class="sxs-lookup"><span data-stu-id="8cc24-122">Generic memory troubleshooting steps may be useful</span></span>  
  
  
