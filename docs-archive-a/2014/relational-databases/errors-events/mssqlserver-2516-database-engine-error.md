---
title: MSSQLSERVER_2516 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696877"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="88b38-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="88b38-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="88b38-103">Details</span><span class="sxs-lookup"><span data-stu-id="88b38-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88b38-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="88b38-104">Product Name</span></span>|<span data-ttu-id="88b38-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="88b38-105">SQL Server</span></span>|  
|<span data-ttu-id="88b38-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="88b38-106">Event ID</span></span>|<span data-ttu-id="88b38-107">2516</span><span class="sxs-lookup"><span data-stu-id="88b38-107">2516</span></span>|  
|<span data-ttu-id="88b38-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="88b38-108">Event Source</span></span>|<span data-ttu-id="88b38-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="88b38-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="88b38-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="88b38-110">Component</span></span>|<span data-ttu-id="88b38-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="88b38-111">SQLEngine</span></span>|  
|<span data-ttu-id="88b38-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="88b38-112">Symbolic Name</span></span>|<span data-ttu-id="88b38-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="88b38-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="88b38-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="88b38-114">Message Text</span></span>|<span data-ttu-id="88b38-115">Die Reparatur hat das differenzielle Bitmuster für die NAME-Datenbank für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="88b38-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="88b38-116">Die Kette differenzieller Sicherungen ist unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="88b38-116">The differential backup chain is broken.</span></span> <span data-ttu-id="88b38-117">Vor einer differenziellen Sicherung müssen Sie eine vollständige Datenbanksicherung ausführen.</span><span class="sxs-lookup"><span data-stu-id="88b38-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="88b38-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="88b38-118">Explanation</span></span>  
 <span data-ttu-id="88b38-119">Diese Informationsmeldung wird zurückgegeben, wenn Fehler MSSQLEngine_2515 behoben wird.</span><span class="sxs-lookup"><span data-stu-id="88b38-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="88b38-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="88b38-120">User Action</span></span>  
 <span data-ttu-id="88b38-121">Führen Sie eine vollständige Datenbanksicherung aus.</span><span class="sxs-lookup"><span data-stu-id="88b38-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88b38-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88b38-122">See Also</span></span>  
 [<span data-ttu-id="88b38-123">Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="88b38-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
