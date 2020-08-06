---
title: MSSQLSERVER_7915 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7915 (Database Engine error)
ms.assetid: 63338587-7dd3-40e6-b70e-d8ae18fff47b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1dc7a69023e49b48a10da9f0388cbd72fbe46be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618711"
---
# <a name="mssqlserver_7915"></a><span data-ttu-id="b2846-102">MSSQLSERVER_7915</span><span class="sxs-lookup"><span data-stu-id="b2846-102">MSSQLSERVER_7915</span></span>
    
## <a name="details"></a><span data-ttu-id="b2846-103">Details</span><span class="sxs-lookup"><span data-stu-id="b2846-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2846-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="b2846-104">Product Name</span></span>|<span data-ttu-id="b2846-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2846-105">SQL Server</span></span>|  
|<span data-ttu-id="b2846-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="b2846-106">Event ID</span></span>|<span data-ttu-id="b2846-107">7915</span><span class="sxs-lookup"><span data-stu-id="b2846-107">7915</span></span>|  
|<span data-ttu-id="b2846-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="b2846-108">Event Source</span></span>|<span data-ttu-id="b2846-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b2846-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b2846-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="b2846-110">Component</span></span>|<span data-ttu-id="b2846-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b2846-111">SQLEngine</span></span>|  
|<span data-ttu-id="b2846-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="b2846-112">Symbolic Name</span></span>|<span data-ttu-id="b2846-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span><span class="sxs-lookup"><span data-stu-id="b2846-113">DBCC2_REPAIR_IAM_CHAIN_REBUILT</span></span>|  
|<span data-ttu-id="b2846-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="b2846-114">Message Text</span></span>|<span data-ttu-id="b2846-115">Reparaturvorgang: Die IAM-Kette für Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (Typ TYPE), wurde vor Seite P_ID abgeschnitten und wird neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="b2846-115">Repair: IAM chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), has been truncated before page P_ID and will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2846-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="b2846-116">Explanation</span></span>  
 <span data-ttu-id="b2846-117">Dies ist eine Informationsmeldung, die von REPAIR gesendet wurde und anzeigt, dass die angegebene IAM-Kette (Index Allocation Map) gepatcht wurde, damit sie neu erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="b2846-117">This is an information message sent by REPAIR that indicates that the specified Index Allocation Map (IAM) chain was patched so that it could be rebuilt.</span></span> <span data-ttu-id="b2846-118">Für diesen Patch war möglicherweise die Zuordnung eines neuen Kopfteils der IAM-Kette oder die Entfernung von fehlerhaften Seiten aus der Kette erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b2846-118">This patching may have required the allocation of a new head of the IAM chain or the removal of bad pages from the chain.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2846-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="b2846-119">User Action</span></span>  
 <span data-ttu-id="b2846-120">Keine</span><span class="sxs-lookup"><span data-stu-id="b2846-120">None</span></span>  
  
  
