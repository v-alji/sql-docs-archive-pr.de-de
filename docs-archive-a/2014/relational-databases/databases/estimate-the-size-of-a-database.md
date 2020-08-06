---
title: Schätzen der Größe einer Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], database size
- calculating database size
- increasing database size
- database size [SQL Server], estimating
- predicting database size
- size [SQL Server], databases
- estimating database size
- designing databases [SQL Server], estimating size
ms.assetid: 5b240161-eba4-44b0-946c-61a8fc00fc8c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3a390c4ade2c2dc08f67d2d1461955516e866c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617098"
---
# <a name="estimate-the-size-of-a-database"></a><span data-ttu-id="5db15-102">Schätzen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="5db15-102">Estimate the Size of a Database</span></span>
  <span data-ttu-id="5db15-103">Wenn Sie eine Datenbank entwerfen, müssen Sie möglicherweise die Größe der Datenbank schätzen, wenn diese mit Daten aufgefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="5db15-103">When you design a database, you may have to estimate how large the database will be when filled with data.</span></span> <span data-ttu-id="5db15-104">Das Schätzen der Datenbankgröße kann Ihnen helfen, die Hardwarekonfiguration zu bestimmen, die für Folgendes benötigt wird:</span><span class="sxs-lookup"><span data-stu-id="5db15-104">Estimating the size of the database can help you determine the hardware configuration you will require to do the following:</span></span>  
  
-   <span data-ttu-id="5db15-105">Erzielen der Leistung, die von den Anwendungen benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-105">Achieve the performance required by your applications.</span></span>  
  
-   <span data-ttu-id="5db15-106">Bereitstellen von physischem Speicherplatz in angemessenem Umfang, um Daten und Indizes zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5db15-106">Guarantee the appropriate physical amount of disk space required to store the data and indexes.</span></span>  
  
 <span data-ttu-id="5db15-107">Durch das Schätzen der Datenbankgröße können Sie auch bestimmen, ob der Datenbankentwurf verfeinert werden muss.</span><span class="sxs-lookup"><span data-stu-id="5db15-107">Estimating the size of a database can also help you determine whether the database design needs refining.</span></span> <span data-ttu-id="5db15-108">Sie könnten z. B. feststellen, dass die geschätzte Größe der Datenbank viel zu groß ist, um in Ihrer Organisation implementiert zu werden, und dass eine weitere Normalisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5db15-108">For example, you may determine that the estimated size of the database is too large to implement in your organization and that more normalization is required.</span></span> <span data-ttu-id="5db15-109">Umgekehrt kann es auch vorkommen, dass der geschätzte Umfang kleiner ist als erwartet.</span><span class="sxs-lookup"><span data-stu-id="5db15-109">Conversely, the estimated size may be smaller than expected.</span></span> <span data-ttu-id="5db15-110">Dann könnten Sie die Normalisierung teilweise oder ganz aufheben, um auf diese Weise die Abfrageleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5db15-110">This would allow you to denormalize the database to improve query performance.</span></span>  
  
 <span data-ttu-id="5db15-111">Um die Größe einer Datenbank zu schätzen, sollten Sie die Größe jeder einzelnen Tabelle schätzen und dann die ermittelten Werte addieren.</span><span class="sxs-lookup"><span data-stu-id="5db15-111">To estimate the size of a database, estimate the size of each table individually and then add the values obtained.</span></span> <span data-ttu-id="5db15-112">Die Größe einer Tabelle hängt davon ab, ob die Tabelle über Indizes verfügt und, wenn dies der Fall ist, welcher Typ von Indizes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-112">The size of a table depends on whether the table has indexes and, if they do, what type of indexes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5db15-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5db15-113">In This Section</span></span>  
  
|<span data-ttu-id="5db15-114">Thema</span><span class="sxs-lookup"><span data-stu-id="5db15-114">Topic</span></span>|<span data-ttu-id="5db15-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5db15-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5db15-116">Schätzen der Größe einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="5db15-116">Estimate the Size of a Table</span></span>](estimate-the-size-of-a-table.md)|<span data-ttu-id="5db15-117">Beschreibt die Schritte und Berechnungen, die zum Schätzen des Umfangs des Speicherplatzes erforderlich sind, der zum Speichern der Daten in einer Tabelle und für die zugehörigen Indizes benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-117">Defines the steps and calculations needed to estimate the amount of space required to store the data in a table and associated indexes.</span></span>|  
|[<span data-ttu-id="5db15-118">Schätzen der Größe eines Heaps</span><span class="sxs-lookup"><span data-stu-id="5db15-118">Estimate the Size of a Heap</span></span>](estimate-the-size-of-a-heap.md)|<span data-ttu-id="5db15-119">Beschreibt die Schritte und Berechnungen, die zum Schätzen des Umfangs des Speicherplatzes erforderlich sind, der zum Speichern der Daten in einem Heap benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-119">Defines the steps and calculations needed to estimate the amount of space required to store the data in a heap.</span></span> <span data-ttu-id="5db15-120">Ein Heap ist eine Tabelle, die nicht über einen gruppierten Index verfügt.</span><span class="sxs-lookup"><span data-stu-id="5db15-120">A heap is a table that does not have a clustered index.</span></span>|  
|[<span data-ttu-id="5db15-121">Schätzen der Größe eines gruppierten Indexes</span><span class="sxs-lookup"><span data-stu-id="5db15-121">Estimate the Size of a Clustered Index</span></span>](estimate-the-size-of-a-clustered-index.md)|<span data-ttu-id="5db15-122">Beschreibt die Schritte und Berechnungen, die zum Schätzen des Umfangs des Speicherplatzes erforderlich sind, der zum Speichern der Daten in einem gruppierten Index benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-122">Defines the steps and calculations needed to estimate the amount of space required to store the data in a clustered index.</span></span>|  
|[<span data-ttu-id="5db15-123">Schätzen der Größe eines nicht gruppierten Index</span><span class="sxs-lookup"><span data-stu-id="5db15-123">Estimate the Size of a Nonclustered Index</span></span>](estimate-the-size-of-a-nonclustered-index.md)|<span data-ttu-id="5db15-124">Beschreibt die Schritte und Berechnungen, die zum Schätzen des Umfangs des Speicherplatzes erforderlich sind, der zum Speichern der Daten in einem nicht gruppierten Index benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="5db15-124">Defines the steps and calculations needed to estimate the amount of space required to store the data in a nonclustered index.</span></span>|  
  
  
