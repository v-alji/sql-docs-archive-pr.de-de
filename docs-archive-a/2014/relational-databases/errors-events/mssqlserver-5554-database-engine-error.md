---
title: MSSQLSERVER_5554 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618719"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="0fb68-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="0fb68-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="0fb68-103">Details</span><span class="sxs-lookup"><span data-stu-id="0fb68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fb68-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0fb68-104">Product Name</span></span>|<span data-ttu-id="0fb68-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0fb68-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0fb68-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0fb68-106">Event ID</span></span>|<span data-ttu-id="0fb68-107">5554</span><span class="sxs-lookup"><span data-stu-id="0fb68-107">5554</span></span>|  
|<span data-ttu-id="0fb68-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0fb68-108">Event Source</span></span>|<span data-ttu-id="0fb68-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0fb68-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0fb68-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0fb68-110">Component</span></span>|<span data-ttu-id="0fb68-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0fb68-111">SQLEngine</span></span>|  
|<span data-ttu-id="0fb68-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0fb68-112">Symbolic Name</span></span>|<span data-ttu-id="0fb68-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="0fb68-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="0fb68-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0fb68-114">Message Text</span></span>|<span data-ttu-id="0fb68-115">Das maximale Limit des Dateisystems an Versionen insgesamt für eine einzige Datei wurde erreicht.</span><span class="sxs-lookup"><span data-stu-id="0fb68-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0fb68-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0fb68-116">Explanation</span></span>  
 <span data-ttu-id="0fb68-117">In MARS (Multiple Active Result Sets) oder Triggerszenarios verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Miniversion des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="0fb68-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0fb68-118">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0fb68-118">User Action</span></span>  
 <span data-ttu-id="0fb68-119">Versuchen Sie, wiederholte Datenupdates in derselben Transaktion zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0fb68-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
