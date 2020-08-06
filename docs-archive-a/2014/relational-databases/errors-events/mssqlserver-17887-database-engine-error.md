---
title: MSSQLSERVER_17887 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608738"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="6348b-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="6348b-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="6348b-103">Details</span><span class="sxs-lookup"><span data-stu-id="6348b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6348b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6348b-104">Product Name</span></span>|<span data-ttu-id="6348b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6348b-105">SQL Server</span></span>|  
|<span data-ttu-id="6348b-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6348b-106">Event ID</span></span>|<span data-ttu-id="6348b-107">17887</span><span class="sxs-lookup"><span data-stu-id="6348b-107">17887</span></span>|  
|<span data-ttu-id="6348b-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6348b-108">Event Source</span></span>|<span data-ttu-id="6348b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6348b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6348b-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6348b-110">Component</span></span>|<span data-ttu-id="6348b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6348b-111">SQLEngine</span></span>|  
|<span data-ttu-id="6348b-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6348b-112">Symbolic Name</span></span>|<span data-ttu-id="6348b-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="6348b-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="6348b-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6348b-114">Message Text</span></span>|<span data-ttu-id="6348b-115">E/A-Abschlussüberwachung (0x%lx) Arbeitsthread 0x%p stellt im Knoten %ld kein Ergebnis bereit.</span><span class="sxs-lookup"><span data-stu-id="6348b-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="6348b-116">Ungefähre CPU-Belegung: Kernel %I64d Millisek., Benutzer %I64d Millisek., Intervall: %I64d.</span><span class="sxs-lookup"><span data-stu-id="6348b-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6348b-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6348b-117">Explanation</span></span>  
 <span data-ttu-id="6348b-118">Kennzeichnet ein mögliches Problem mit der E/A-Abschlussportüberwachung an dem spezifischen Knoten, wenn die E/A-Abschlussroutine für ein Netzwerk-Lese-/Schreibereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6348b-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="6348b-119">Dieser Fehler wird behoben, wenn die E/A-Abschlussportüberwachung nach der Ausführung der E/A-Abschlussroutine zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6348b-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6348b-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6348b-120">User Action</span></span>  
 <span data-ttu-id="6348b-121">Wenden Sie sich an den Microsoft-Kundendienst (Customer Support Services, CSS).</span><span class="sxs-lookup"><span data-stu-id="6348b-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
