---
title: MSSQLSERVER_3413 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620902"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="e20ce-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="e20ce-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="e20ce-103">Details</span><span class="sxs-lookup"><span data-stu-id="e20ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e20ce-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="e20ce-104">Product Name</span></span>|<span data-ttu-id="e20ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e20ce-105">SQL Server</span></span>|  
|<span data-ttu-id="e20ce-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="e20ce-106">Event ID</span></span>|<span data-ttu-id="e20ce-107">3413</span><span class="sxs-lookup"><span data-stu-id="e20ce-107">3413</span></span>|  
|<span data-ttu-id="e20ce-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="e20ce-108">Event Source</span></span>|<span data-ttu-id="e20ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e20ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e20ce-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="e20ce-110">Component</span></span>|<span data-ttu-id="e20ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e20ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="e20ce-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="e20ce-112">Symbolic Name</span></span>|<span data-ttu-id="e20ce-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="e20ce-113">MARKDB</span></span>|  
|<span data-ttu-id="e20ce-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="e20ce-114">Message Text</span></span>|<span data-ttu-id="e20ce-115">Datenbank-ID %d.</span><span class="sxs-lookup"><span data-stu-id="e20ce-115">Database ID %d.</span></span> <span data-ttu-id="e20ce-116">Die Datenbank konnte nicht als fehlerverdächtig gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="e20ce-116">Could not mark database as suspect.</span></span> <span data-ttu-id="e20ce-117">Fehler beim Getnext-Scan für NC für sys.databases.database_id.</span><span class="sxs-lookup"><span data-stu-id="e20ce-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="e20ce-118">Identifizieren Sie die Ursache anhand vorheriger Fehlermeldungen im Fehlerprotokoll, und beheben Sie etwaige damit verbundene Probleme.</span><span class="sxs-lookup"><span data-stu-id="e20ce-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e20ce-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="e20ce-119">Explanation</span></span>  
 <span data-ttu-id="e20ce-120">Es ist ein unerwarteter Fehler aufgetreten, während versucht wurde, eine Benutzerdatenbank im Katalog als SUSPECT zu markieren.</span><span class="sxs-lookup"><span data-stu-id="e20ce-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="e20ce-121">Der Status SUSPECT wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e20ce-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e20ce-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="e20ce-122">User Action</span></span>  
 <span data-ttu-id="e20ce-123">Zeigen Sie vorherige Fehler an, und beheben Sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="e20ce-123">See previous errors and correct the problem.</span></span>  
  
  
