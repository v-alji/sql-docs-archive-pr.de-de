---
title: MSSQLSERVER_9692 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617034"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="eed40-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="eed40-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="eed40-103">Details</span><span class="sxs-lookup"><span data-stu-id="eed40-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eed40-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="eed40-104">Product Name</span></span>|<span data-ttu-id="eed40-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eed40-105">SQL Server</span></span>|  
|<span data-ttu-id="eed40-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="eed40-106">Event ID</span></span>|<span data-ttu-id="eed40-107">9692</span><span class="sxs-lookup"><span data-stu-id="eed40-107">9692</span></span>|  
|<span data-ttu-id="eed40-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="eed40-108">Event Source</span></span>|<span data-ttu-id="eed40-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eed40-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eed40-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="eed40-110">Component</span></span>|<span data-ttu-id="eed40-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eed40-111">SQLEngine</span></span>|  
|<span data-ttu-id="eed40-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="eed40-112">Symbolic Name</span></span>|<span data-ttu-id="eed40-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="eed40-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="eed40-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="eed40-114">Message Text</span></span>|<span data-ttu-id="eed40-115">Der %S_MSG-Protokolltransport kann nicht an Port %d lauschen, weil er von einem anderen Prozess verwendet wird</span><span class="sxs-lookup"><span data-stu-id="eed40-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eed40-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="eed40-116">Explanation</span></span>  
 <span data-ttu-id="eed40-117">Ein anderes Programm auf dem Computer verwendet den angegebenen TCP-Port.</span><span class="sxs-lookup"><span data-stu-id="eed40-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eed40-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="eed40-118">User Action</span></span>  
 <span data-ttu-id="eed40-119">Führen `netstat -aon` Sie aus, um zu bestimmen, welches Programm den Port verwendet.</span><span class="sxs-lookup"><span data-stu-id="eed40-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="eed40-120">Deaktivieren Sie die entsprechende Anwendung, oder geben Sie einen anderen Port für Service Broker an.</span><span class="sxs-lookup"><span data-stu-id="eed40-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
