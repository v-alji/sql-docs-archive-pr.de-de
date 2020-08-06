---
title: MSSQLSERVER_1807 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617079"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="c1c02-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="c1c02-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="c1c02-103">Details</span><span class="sxs-lookup"><span data-stu-id="c1c02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1c02-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c1c02-104">Product Name</span></span>|<span data-ttu-id="c1c02-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c1c02-105">SQL Server</span></span>|  
|<span data-ttu-id="c1c02-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c1c02-106">Event ID</span></span>|<span data-ttu-id="c1c02-107">1807</span><span class="sxs-lookup"><span data-stu-id="c1c02-107">1807</span></span>|  
|<span data-ttu-id="c1c02-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c1c02-108">Event Source</span></span>|<span data-ttu-id="c1c02-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c1c02-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c1c02-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c1c02-110">Component</span></span>|<span data-ttu-id="c1c02-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c1c02-111">SQLEngine</span></span>|  
|<span data-ttu-id="c1c02-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c1c02-112">Symbolic Name</span></span>|<span data-ttu-id="c1c02-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="c1c02-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="c1c02-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c1c02-114">Message Text</span></span>|<span data-ttu-id="c1c02-115">Es konnte keine exklusive Sperre für die '%.\*ls'-Datenbank erhalten werden.</span><span class="sxs-lookup"><span data-stu-id="c1c02-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="c1c02-116">Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="c1c02-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c1c02-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c1c02-117">Explanation</span></span>  
 <span data-ttu-id="c1c02-118">Ein Vorgang, für den ein exklusiver Zugriff auf die Datenbank erforderlich war, konnte ihn nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="c1c02-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1c02-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c1c02-119">User Action</span></span>  
 <span data-ttu-id="c1c02-120">Trennen Sie alle Verbindungen mit der entsprechenden Datenbank, oder versuchen Sie die Abfrage zu einem späteren Zeitpunkt erneut.</span><span class="sxs-lookup"><span data-stu-id="c1c02-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
