---
title: MSSQLSERVER_10003 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608746"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="df517-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="df517-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="df517-103">Details</span><span class="sxs-lookup"><span data-stu-id="df517-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df517-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="df517-104">Product Name</span></span>|<span data-ttu-id="df517-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="df517-105">SQL Server</span></span>|  
|<span data-ttu-id="df517-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="df517-106">Event ID</span></span>|<span data-ttu-id="df517-107">10003</span><span class="sxs-lookup"><span data-stu-id="df517-107">10003</span></span>|  
|<span data-ttu-id="df517-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="df517-108">Event Source</span></span>|<span data-ttu-id="df517-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="df517-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="df517-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="df517-110">Component</span></span>|<span data-ttu-id="df517-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="df517-111">SQLEngine</span></span>|  
|<span data-ttu-id="df517-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="df517-112">Symbolic Name</span></span>|<span data-ttu-id="df517-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="df517-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="df517-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="df517-114">Message Text</span></span>|<span data-ttu-id="df517-115">Dem Anbieter steht nicht genügend Arbeitsspeicher zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="df517-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df517-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="df517-116">Explanation</span></span>  
 <span data-ttu-id="df517-117">Zu geringer Systemspeicher hat bewirkt, dass der OLE DB-Anbieter nicht mehr über genügend Speicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="df517-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df517-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="df517-118">User Action</span></span>  
 <span data-ttu-id="df517-119">Starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="df517-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="df517-120">Falls der Fehler dadurch nicht behoben wird, starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="df517-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="df517-121">Wenn das Problem weiterhin auftritt, listen Sie OLE DB-Ablaufverfolgungsereignisse mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] auf, und stellen Sie diese Daten für den Produktsupport des OLE DB-Anbieters bereit.</span><span class="sxs-lookup"><span data-stu-id="df517-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df517-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df517-122">See Also</span></span>  
 <span data-ttu-id="df517-123">[Vorlagen und Berechtigungen in SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="df517-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="df517-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="df517-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
