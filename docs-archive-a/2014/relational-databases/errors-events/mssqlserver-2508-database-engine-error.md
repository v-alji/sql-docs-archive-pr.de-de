---
title: MSSQLSERVER_2508 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699639"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="00052-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="00052-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="00052-103">Details</span><span class="sxs-lookup"><span data-stu-id="00052-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00052-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="00052-104">Product Name</span></span>|<span data-ttu-id="00052-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00052-105">SQL Server</span></span>|  
|<span data-ttu-id="00052-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="00052-106">Event ID</span></span>|<span data-ttu-id="00052-107">2508</span><span class="sxs-lookup"><span data-stu-id="00052-107">2508</span></span>|  
|<span data-ttu-id="00052-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="00052-108">Event Source</span></span>|<span data-ttu-id="00052-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="00052-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="00052-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="00052-110">Component</span></span>|<span data-ttu-id="00052-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="00052-111">SQLEngine</span></span>|  
|<span data-ttu-id="00052-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="00052-112">Symbolic Name</span></span>|<span data-ttu-id="00052-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="00052-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="00052-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="00052-114">Message Text</span></span>|<span data-ttu-id="00052-115">Die %.\*ls-Anzahl für das "%.\*ls"-Objekt, Index-ID %d, Partitions-ID %I64d, Zuordnungseinheits-ID %I64d (%.\*ls-Typ) ist nicht richtig.</span><span class="sxs-lookup"><span data-stu-id="00052-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="00052-116">Führen Sie DBCC UPDATEUSAGE aus.</span><span class="sxs-lookup"><span data-stu-id="00052-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00052-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="00052-117">Explanation</span></span>  
 <span data-ttu-id="00052-118">In Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ist es möglich, dass für die Zeilen- und Seitenanzahl von Tabellen und Indizes falsche Werte entstehen.</span><span class="sxs-lookup"><span data-stu-id="00052-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="00052-119">Datenbanken, die in Versionen vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] erstellt wurden, können falsche Zählwerte enthalten.</span><span class="sxs-lookup"><span data-stu-id="00052-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="00052-120">DBCC CHECKDB wurde verbessert, sodass diese Fehler nun erkannt werden und diese Meldung zurückgegeben wird, wenn der Fehler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="00052-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00052-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="00052-121">User Action</span></span>  
 <span data-ttu-id="00052-122">Führen Sie DBCC UPDATEUSAGE für das angegebene Objekt bzw. den angegeben Index oder für die Datenbank aus, in der das Objekt enthalten ist, um die falsche Anzahl zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="00052-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
