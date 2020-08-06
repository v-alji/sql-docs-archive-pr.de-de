---
title: MSSQLSERVER_125 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618045"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="3723d-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="3723d-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="3723d-103">Details</span><span class="sxs-lookup"><span data-stu-id="3723d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3723d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="3723d-104">Product Name</span></span>|<span data-ttu-id="3723d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3723d-105">SQL Server</span></span>|  
|<span data-ttu-id="3723d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="3723d-106">Event ID</span></span>|<span data-ttu-id="3723d-107">125</span><span class="sxs-lookup"><span data-stu-id="3723d-107">125</span></span>|  
|<span data-ttu-id="3723d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="3723d-108">Event Source</span></span>|<span data-ttu-id="3723d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3723d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3723d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="3723d-110">Component</span></span>|<span data-ttu-id="3723d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3723d-111">SQLEngine</span></span>|  
|<span data-ttu-id="3723d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="3723d-112">Symbolic Name</span></span>||  
|<span data-ttu-id="3723d-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="3723d-113">Message Text</span></span>|<span data-ttu-id="3723d-114">CASE-Ausdrücke können nur bis zu %d Ebenen geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="3723d-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3723d-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="3723d-115">Explanation</span></span>  
 <span data-ttu-id="3723d-116">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist für CASE-Ausdrücke nur eine Schachtelung von 10 Ebenen zulässig.</span><span class="sxs-lookup"><span data-stu-id="3723d-116">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3723d-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="3723d-117">User Action</span></span>  
 <span data-ttu-id="3723d-118">Reduzieren Sie die Anzahl der Ebenen von CASE-Anweisungen auf 10 oder weniger.</span><span class="sxs-lookup"><span data-stu-id="3723d-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3723d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3723d-119">See Also</span></span>  
 [<span data-ttu-id="3723d-120">CASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3723d-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  
