---
title: MSSQLSERVER_11409 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608739"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="c8eec-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="c8eec-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="c8eec-103">Details</span><span class="sxs-lookup"><span data-stu-id="c8eec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c8eec-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="c8eec-104">Product Name</span></span>|<span data-ttu-id="c8eec-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c8eec-105">SQL Server</span></span>|  
|<span data-ttu-id="c8eec-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="c8eec-106">Event ID</span></span>|<span data-ttu-id="c8eec-107">11409</span><span class="sxs-lookup"><span data-stu-id="c8eec-107">11409</span></span>|  
|<span data-ttu-id="c8eec-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="c8eec-108">Event Source</span></span>|<span data-ttu-id="c8eec-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c8eec-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c8eec-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="c8eec-110">Component</span></span>|<span data-ttu-id="c8eec-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c8eec-111">SQLEngine</span></span>|  
|<span data-ttu-id="c8eec-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="c8eec-112">Symbolic Name</span></span>|<span data-ttu-id="c8eec-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="c8eec-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="c8eec-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="c8eec-114">Message Text</span></span>|<span data-ttu-id="c8eec-115">Der '%.\*ls'-Spaltensatz in der '%.\*ls'-Tabelle kann nicht entfernt werden, da die Tabelle mehr als 1025 Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="c8eec-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c8eec-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="c8eec-116">Explanation</span></span>  
 <span data-ttu-id="c8eec-117">Tabellen können maximal 1024 Spalten enthalten, die nicht als Spalte mit geringer Dichte oder berechnete Spalte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="c8eec-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="c8eec-118">Wenn die Tabelle aufgrund von Sparsespalten mehr als 1024 Spalten aufweist, muss für die Tabelle ein Spaltensatz definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8eec-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="c8eec-119">Die Tabelle, auf die verwiesen wird, weist mehr als 1024 Spalten auf, und Sie haben versucht, den Spaltensatz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c8eec-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c8eec-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="c8eec-120">User Action</span></span>  
 <span data-ttu-id="c8eec-121">Mit den aktuellen Spalten in der Tabelle müssen Sie den Spaltensatz beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c8eec-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="c8eec-122">Zum Entfernen des Spaltensatzes entfernen Sie zunächst Spalten aus der Tabelle, bis nur noch 1024 Spalten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c8eec-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="c8eec-123">Dann können Sie den Spaltensatz entfernen.</span><span class="sxs-lookup"><span data-stu-id="c8eec-123">Then, you can remove the column set.</span></span>  
  
  
