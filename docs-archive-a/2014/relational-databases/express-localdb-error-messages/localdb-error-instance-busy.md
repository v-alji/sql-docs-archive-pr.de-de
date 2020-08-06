---
title: LOCALDB_ERROR_INSTANCE_BUSY | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 0ed9d0f8-3297-4e31-a3e9-4a827f381789
author: stevestein
ms.author: sstein
ms.openlocfilehash: c587ada5f08d3743f4fe7eafccfc923c38a2b7b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617001"
---
# <a name="localdb_error_instance_busy"></a><span data-ttu-id="c45fd-102">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="c45fd-102">LOCALDB_ERROR_INSTANCE_BUSY</span></span>
    
## <a name="details"></a><span data-ttu-id="c45fd-103">Details</span><span class="sxs-lookup"><span data-stu-id="c45fd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c45fd-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c45fd-104">Product Name</span></span>|<span data-ttu-id="c45fd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c45fd-105">SQL Server</span></span>|  
|<span data-ttu-id="c45fd-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c45fd-106">Event ID</span></span>|<span data-ttu-id="c45fd-107">274</span><span class="sxs-lookup"><span data-stu-id="c45fd-107">274</span></span>|  
|<span data-ttu-id="c45fd-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c45fd-108">Event Source</span></span>|<span data-ttu-id="c45fd-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="c45fd-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="c45fd-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c45fd-110">Component</span></span>|<span data-ttu-id="c45fd-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="c45fd-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="c45fd-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c45fd-112">Message Text</span></span>|<span data-ttu-id="c45fd-113">Der angeforderte Vorgang für die lokale Datenbankinstanz kann nicht ausgeführt werden, weil die angegebene Instanz gerade verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c45fd-113">Requested operation on Local Database instance cannot be performed because specified instance is currently in use.</span></span> <span data-ttu-id="c45fd-114">Beenden Sie die Instanz, und wiederholen Sie den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="c45fd-114">Stop the instance and try again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c45fd-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c45fd-115">Explanation</span></span>  
 <span data-ttu-id="c45fd-116">Die angegebene Instanz wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c45fd-116">The specified instance is running.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c45fd-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c45fd-117">User Action</span></span>  
 <span data-ttu-id="c45fd-118">Stoppen Sie die angegebene Laufzeitinstanz der lokalen Datenbank, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="c45fd-118">Stop the specified Local Database Runtime instance and try again.</span></span>  
  
  
