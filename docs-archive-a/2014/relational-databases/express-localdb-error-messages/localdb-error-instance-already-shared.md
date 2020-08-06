---
title: LOCALDB_ERROR_INSTANCE_ALREADY_SHARED | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 35b4d6fa-ebb9-49d3-aaab-d4e37b6f3760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 300f9753b721bc3e0a821a6b77929a9bec09312b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608682"
---
# <a name="localdb_error_instance_already_shared"></a><span data-ttu-id="0e3c8-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="0e3c8-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>
    
## <a name="details"></a><span data-ttu-id="0e3c8-103">Details</span><span class="sxs-lookup"><span data-stu-id="0e3c8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0e3c8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0e3c8-104">Product Name</span></span>|<span data-ttu-id="0e3c8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0e3c8-105">SQL Server</span></span>|  
|<span data-ttu-id="0e3c8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0e3c8-106">Event ID</span></span>|<span data-ttu-id="0e3c8-107">284</span><span class="sxs-lookup"><span data-stu-id="0e3c8-107">284</span></span>|  
|<span data-ttu-id="0e3c8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0e3c8-108">Event Source</span></span>|<span data-ttu-id="0e3c8-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="0e3c8-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="0e3c8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0e3c8-110">Component</span></span>|<span data-ttu-id="0e3c8-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="0e3c8-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="0e3c8-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0e3c8-112">Message Text</span></span>|<span data-ttu-id="0e3c8-113">Die angegebene lokale Datenbankinstanz ist bereits freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0e3c8-113">The specified Local Database Instance is already shared.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0e3c8-114">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0e3c8-114">Explanation</span></span>  
 <span data-ttu-id="0e3c8-115">Die angegebene lokale Datenbankinstanz ist bereits unter einem anderen Freigabenamen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0e3c8-115">The specified Local Database Instance is already shared with a different shared name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e3c8-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0e3c8-116">User Action</span></span>  
 <span data-ttu-id="0e3c8-117">Heben Sie die Freigabe der freigegebenen Instanz auf, bevor Sie sie erneut unter einem anderen Freigabenamen freigeben.</span><span class="sxs-lookup"><span data-stu-id="0e3c8-117">Unshare the shared instance before sharing it again with a different shared name.</span></span>  
  
  
