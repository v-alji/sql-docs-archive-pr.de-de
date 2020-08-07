---
title: MSSQLSERVER_8642 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8642 (Database Engine error)
ms.assetid: fc498059-202f-4d0b-8599-4e784b47c186
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30296fa569599b91ca74edc7535d330119e1680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619856"
---
# <a name="mssqlserver_8642"></a><span data-ttu-id="4b262-102">MSSQLSERVER_8642</span><span class="sxs-lookup"><span data-stu-id="4b262-102">MSSQLSERVER_8642</span></span>
    
## <a name="details"></a><span data-ttu-id="4b262-103">Details</span><span class="sxs-lookup"><span data-stu-id="4b262-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b262-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="4b262-104">Product Name</span></span>|<span data-ttu-id="4b262-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b262-105">SQL Server</span></span>|  
|<span data-ttu-id="4b262-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="4b262-106">Event ID</span></span>|<span data-ttu-id="4b262-107">8642</span><span class="sxs-lookup"><span data-stu-id="4b262-107">8642</span></span>|  
|<span data-ttu-id="4b262-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="4b262-108">Event Source</span></span>|<span data-ttu-id="4b262-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4b262-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4b262-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="4b262-110">Component</span></span>|<span data-ttu-id="4b262-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4b262-111">SQLEngine</span></span>|  
|<span data-ttu-id="4b262-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="4b262-112">Symbolic Name</span></span>|<span data-ttu-id="4b262-113">EXCHNGSTART_ERR</span><span class="sxs-lookup"><span data-stu-id="4b262-113">EXCHNGSTART_ERR</span></span>|  
|<span data-ttu-id="4b262-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="4b262-114">Message Text</span></span>|<span data-ttu-id="4b262-115">Der Abfrageprozessor konnte die erforderlichen Threadressourcen für die parallele Abfrageausführung nicht starten.</span><span class="sxs-lookup"><span data-stu-id="4b262-115">The query processor could not start the necessary thread resources for parallel query execution.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b262-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="4b262-116">Explanation</span></span>  
 <span data-ttu-id="4b262-117">Auf dem Server gibt es nicht genügend Threadressourcen.</span><span class="sxs-lookup"><span data-stu-id="4b262-117">Thread resources are low in the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b262-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="4b262-118">User Action</span></span>  
 <span data-ttu-id="4b262-119">Verringern Sie die Last auf dem Server, und führen Sie die Abfrage erneut aus.</span><span class="sxs-lookup"><span data-stu-id="4b262-119">Reduce load on the server, and run the query again.</span></span>  
  
  
