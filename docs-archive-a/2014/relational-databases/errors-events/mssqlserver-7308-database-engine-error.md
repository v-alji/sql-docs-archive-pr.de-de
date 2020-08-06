---
title: MSSQLSERVER_7308 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7308 (Database Engine error)
- single-threaded apartment mode
ms.assetid: cca9eab9-afb9-463d-abfd-0802257e2c99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9978f35ebe41eeda1470220772f87e83ab1ad942
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618016"
---
# <a name="mssqlserver_7308"></a><span data-ttu-id="42937-102">MSSQLSERVER_7308</span><span class="sxs-lookup"><span data-stu-id="42937-102">MSSQLSERVER_7308</span></span>
    
## <a name="details"></a><span data-ttu-id="42937-103">Details</span><span class="sxs-lookup"><span data-stu-id="42937-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42937-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="42937-104">Product Name</span></span>|<span data-ttu-id="42937-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="42937-105">SQL Server</span></span>|  
|<span data-ttu-id="42937-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="42937-106">Event ID</span></span>|<span data-ttu-id="42937-107">7308</span><span class="sxs-lookup"><span data-stu-id="42937-107">7308</span></span>|  
|<span data-ttu-id="42937-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="42937-108">Event Source</span></span>|<span data-ttu-id="42937-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="42937-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="42937-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="42937-110">Component</span></span>|<span data-ttu-id="42937-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="42937-111">SQLEngine</span></span>|  
|<span data-ttu-id="42937-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="42937-112">Symbolic Name</span></span>|<span data-ttu-id="42937-113">RMT_STA_DISABLED</span><span class="sxs-lookup"><span data-stu-id="42937-113">RMT_STA_DISABLED</span></span>|  
|<span data-ttu-id="42937-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="42937-114">Message Text</span></span>|<span data-ttu-id="42937-115">Der OLE DB-Anbieter ‚%ls’ kann nicht für verteilte Abfragen verwendet werden, weil der Anbieter so konfiguriert ist, dass er im Singlethread-Apartment-Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42937-115">OLE DB provider '%ls' cannot be used for distributed queries because the provider is configured to run in single-threaded apartment mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="42937-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="42937-116">Explanation</span></span>  
 <span data-ttu-id="42937-117">Sie haben einen OLE DB-Anbieter verwendet, der so konfiguriert ist, dass er im Singlethread-Apartment-Modus (STA) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42937-117">You have used an OLE DB provider that is configured to run in single-threaded apartment (STA) mode.</span></span> <span data-ttu-id="42937-118">OLE DB-Anbieter, die im Singlethread-Apartment-Modus (STA) ausgeführt werden, können nicht für verteilte Abfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42937-118">OLE DB providers that run in single-threaded apartment (STA) mode cannot be used for distributed queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="42937-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="42937-119">User Action</span></span>  
 <span data-ttu-id="42937-120">Um diesen Fehler zu beheben, konfigurieren Sie den Anbieter so, dass er im Multithread-Apartment-Modus (MTA) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42937-120">To resolve this error, configure the provider to run in multithreaded apartment (MTA) mode.</span></span> <span data-ttu-id="42937-121">Wenn der Anbieter den MTA nicht unterstützt und der Anbieter nicht auf eine Version aktualisiert werden kann, die MTA unterstützt, ziehen Sie in Erwägung, den Anbieter so zu konfigurieren, dass er außerhalb des Prozesses ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="42937-121">If the provider does not support MTA, and the provider cannot be upgraded to a version that supports MTA, consider configuring the provider to run out-of-process.</span></span> <span data-ttu-id="42937-122">Der Anbieterhersteller kann Ihnen mitteilen, ob der Anbieter den MTA oder die Ausführung außerhalb des Prozesses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42937-122">The provider vendor should be able to tell you if the provider supports MTA or running out-of-process.</span></span>  
  
  
