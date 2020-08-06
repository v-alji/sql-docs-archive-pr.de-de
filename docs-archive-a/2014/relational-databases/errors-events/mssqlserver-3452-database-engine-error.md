---
title: MSSQLSERVER_3452 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607802"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="cc779-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="cc779-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="cc779-103">Details</span><span class="sxs-lookup"><span data-stu-id="cc779-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc779-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="cc779-104">Product Name</span></span>|<span data-ttu-id="cc779-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc779-105">SQL Server</span></span>|  
|<span data-ttu-id="cc779-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="cc779-106">Event ID</span></span>|<span data-ttu-id="cc779-107">3452</span><span class="sxs-lookup"><span data-stu-id="cc779-107">3452</span></span>|  
|<span data-ttu-id="cc779-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="cc779-108">Event Source</span></span>|<span data-ttu-id="cc779-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cc779-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cc779-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="cc779-110">Component</span></span>|<span data-ttu-id="cc779-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cc779-111">SQLEngine</span></span>|  
|<span data-ttu-id="cc779-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="cc779-112">Symbolic Name</span></span>|<span data-ttu-id="cc779-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="cc779-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="cc779-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="cc779-114">Message Text</span></span>|<span data-ttu-id="cc779-115">Bei der Wiederherstellung der '%.\*ls'-Datenbank (%d) wurden mögliche inkonsistente Identitätswerte in der Tabelle mit der ID %d erkannt.</span><span class="sxs-lookup"><span data-stu-id="cc779-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="cc779-116">Führen Sie DBCC CHECKIDENT ('%.\*ls') aus.</span><span class="sxs-lookup"><span data-stu-id="cc779-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cc779-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="cc779-117">Explanation</span></span>  
 <span data-ttu-id="cc779-118">Beim Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wurde vom Prozess zum Wiederherstellen der Identitätswerte in der Datenbank eine Inkonsistenz in den Metadaten festgestellt.</span><span class="sxs-lookup"><span data-stu-id="cc779-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc779-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="cc779-119">User Action</span></span>  
 <span data-ttu-id="cc779-120">Führen Sie DBCC CHECKIDENT aus.</span><span class="sxs-lookup"><span data-stu-id="cc779-120">Run DBCC CHECKIDENT.</span></span>  
  
  
