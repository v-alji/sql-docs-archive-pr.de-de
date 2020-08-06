---
title: MSSQLSERVER_17128 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698270"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="0670e-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="0670e-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="0670e-103">Details</span><span class="sxs-lookup"><span data-stu-id="0670e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0670e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0670e-104">Product Name</span></span>|<span data-ttu-id="0670e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0670e-105">SQL Server</span></span>|  
|<span data-ttu-id="0670e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0670e-106">Event ID</span></span>|<span data-ttu-id="0670e-107">17128</span><span class="sxs-lookup"><span data-stu-id="0670e-107">17128</span></span>|  
|<span data-ttu-id="0670e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0670e-108">Event Source</span></span>|<span data-ttu-id="0670e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0670e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0670e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0670e-110">Component</span></span>|<span data-ttu-id="0670e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0670e-111">SQLEngine</span></span>|  
|<span data-ttu-id="0670e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0670e-112">Symbolic Name</span></span>|<span data-ttu-id="0670e-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="0670e-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="0670e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0670e-114">Message Text</span></span>|<span data-ttu-id="0670e-115">initdata: Nicht genügend Arbeitsspeicher für Kernelpuffer.</span><span class="sxs-lookup"><span data-stu-id="0670e-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0670e-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0670e-116">Explanation</span></span>  
 <span data-ttu-id="0670e-117">Die ursprünglichen Speicherbelegungen oder -reservierungen des Pufferpools sind fehlgeschlagen, und SQL Server wird beendet.</span><span class="sxs-lookup"><span data-stu-id="0670e-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0670e-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0670e-118">User Action</span></span>  
 <span data-ttu-id="0670e-119">Wird normalerweise durch das Starten von SQL Server auf einem Computer mit extrem geringer Kapazität (viel geringer als die minimalen Systemanforderungen) verursacht.</span><span class="sxs-lookup"><span data-stu-id="0670e-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
