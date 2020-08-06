---
title: MSSQLSERVER_8966 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630661"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="45da0-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="45da0-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="45da0-103">Details</span><span class="sxs-lookup"><span data-stu-id="45da0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45da0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="45da0-104">Product Name</span></span>|<span data-ttu-id="45da0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="45da0-105">SQL Server</span></span>|  
|<span data-ttu-id="45da0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="45da0-106">Event ID</span></span>|<span data-ttu-id="45da0-107">8966</span><span class="sxs-lookup"><span data-stu-id="45da0-107">8966</span></span>|  
|<span data-ttu-id="45da0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="45da0-108">Event Source</span></span>|<span data-ttu-id="45da0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="45da0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="45da0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="45da0-110">Component</span></span>|<span data-ttu-id="45da0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="45da0-111">SQLEngine</span></span>|  
|<span data-ttu-id="45da0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="45da0-112">Symbolic Name</span></span>|<span data-ttu-id="45da0-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="45da0-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="45da0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="45da0-114">Message Text</span></span>|<span data-ttu-id="45da0-115">Die Seite P_ID konnte nicht gelesen und mit dem Latchtyp TYPE versehen werden.</span><span class="sxs-lookup"><span data-stu-id="45da0-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="45da0-116">Fehler bei OPERATION.</span><span class="sxs-lookup"><span data-stu-id="45da0-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="45da0-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="45da0-117">Explanation</span></span>  
 <span data-ttu-id="45da0-118">Es ist ein Fehler bei einem Seitenlesevorgang aufgetreten, oder ein Latch konnte nicht auf einer PFS- oder GAM-Seite verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45da0-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="45da0-119">Möglicherweise werden im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll ein Latchtimeout oder andere damit verbundenen Meldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45da0-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45da0-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="45da0-120">User Action</span></span>  
 <span data-ttu-id="45da0-121">Überprüfen Sie das SQL-Fehlerprotokoll auf zugehörige Meldungen, und begeben Sie die Fehler.</span><span class="sxs-lookup"><span data-stu-id="45da0-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
