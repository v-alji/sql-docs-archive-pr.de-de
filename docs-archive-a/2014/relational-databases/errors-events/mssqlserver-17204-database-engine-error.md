---
title: MSSQLSERVER_17204 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17204 (Database Engine error)
ms.assetid: 40db66f9-dd5e-478c-891e-a06d363a2552
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c63f0b3d2aff8b909e3a7fc841c9038cf95a475e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617078"
---
# <a name="mssqlserver_17204"></a><span data-ttu-id="33ca8-102">MSSQLSERVER_17204</span><span class="sxs-lookup"><span data-stu-id="33ca8-102">MSSQLSERVER_17204</span></span>
    
## <a name="details"></a><span data-ttu-id="33ca8-103">Details</span><span class="sxs-lookup"><span data-stu-id="33ca8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33ca8-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="33ca8-104">Product Name</span></span>|<span data-ttu-id="33ca8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="33ca8-105">SQL Server</span></span>|  
|<span data-ttu-id="33ca8-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="33ca8-106">Event ID</span></span>|<span data-ttu-id="33ca8-107">17204</span><span class="sxs-lookup"><span data-stu-id="33ca8-107">17204</span></span>|  
|<span data-ttu-id="33ca8-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="33ca8-108">Event Source</span></span>|<span data-ttu-id="33ca8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="33ca8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="33ca8-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="33ca8-110">Component</span></span>|<span data-ttu-id="33ca8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="33ca8-111">SQLEngine</span></span>|  
|<span data-ttu-id="33ca8-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="33ca8-112">Symbolic Name</span></span>|<span data-ttu-id="33ca8-113">DBLKIO_DEVOPENFAILED</span><span class="sxs-lookup"><span data-stu-id="33ca8-113">DBLKIO_DEVOPENFAILED</span></span>|  
|<span data-ttu-id="33ca8-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="33ca8-114">Message Text</span></span>|<span data-ttu-id="33ca8-115">%ls: Die Datei %ls für die Dateinummer %d konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="33ca8-115">%ls: Could not open file %ls for file number %d.</span></span>  <span data-ttu-id="33ca8-116">Betriebssystemfehler: %ls.</span><span class="sxs-lookup"><span data-stu-id="33ca8-116">OS error: %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="33ca8-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="33ca8-117">Explanation</span></span>  
 <span data-ttu-id="33ca8-118">SQL Server konnte die angegebene Datei aufgrund des angegebenen Fehlers nicht öffnen.</span><span class="sxs-lookup"><span data-stu-id="33ca8-118">SQL Server was unable to open the specified file due to the specified error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="33ca8-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="33ca8-119">User Action</span></span>  
 <span data-ttu-id="33ca8-120">Erstellen Sie eine Diagnose für das Betriebssystem, und korrigieren Sie es, wiederholen Sie dann den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="33ca8-120">Diagnose and correct the operating system, then retry the operation.</span></span>  
  
  
