---
title: MSSQLSERVER_7916 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618712"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="f9408-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="f9408-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="f9408-103">Details</span><span class="sxs-lookup"><span data-stu-id="f9408-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f9408-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f9408-104">Product Name</span></span>|<span data-ttu-id="f9408-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9408-105">SQL Server</span></span>|  
|<span data-ttu-id="f9408-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f9408-106">Event ID</span></span>|<span data-ttu-id="f9408-107">7916</span><span class="sxs-lookup"><span data-stu-id="f9408-107">7916</span></span>|  
|<span data-ttu-id="f9408-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f9408-108">Event Source</span></span>|<span data-ttu-id="f9408-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f9408-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f9408-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f9408-110">Component</span></span>|<span data-ttu-id="f9408-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f9408-111">SQLEngine</span></span>|  
|<span data-ttu-id="f9408-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f9408-112">Symbolic Name</span></span>|<span data-ttu-id="f9408-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="f9408-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="f9408-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f9408-114">Message Text</span></span>|<span data-ttu-id="f9408-115">Reparaturvorgang: Der Datensatz für Objekt-ID O_ID, Index-ID I_ID, Partitions-ID PN_ID, Zuordnungseinheits-ID A_ID (TYPE-Typ) auf der Seite P_ID, Slot S_ID wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f9408-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="f9408-116">Die Indizes werden neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f9408-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f9408-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f9408-117">Explanation</span></span>  
 <span data-ttu-id="f9408-118">Dies ist eine Informationsmeldung von REPAIR, die angibt, dass der angegebene Datensatz aus der Seite gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="f9408-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f9408-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f9408-119">User Action</span></span>  
 <span data-ttu-id="f9408-120">Keine</span><span class="sxs-lookup"><span data-stu-id="f9408-120">None</span></span>  
  
  
