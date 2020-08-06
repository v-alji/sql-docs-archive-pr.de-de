---
title: Projektmappen (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- solutions [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d06a8a05-7201-4055-8cf3-21bcb4e82c25
author: stevestein
ms.author: sstein
ms.openlocfilehash: 836d3b3002d72541ad88ae55eac6d951530e0ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616306"
---
# <a name="solutions-sql-server-management-studio"></a><span data-ttu-id="381db-102">Projektmappen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="381db-102">Solutions (SQL Server Management Studio)</span></span>
  <span data-ttu-id="381db-103">Eine [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Projektmappe ist eine Auflistung von einem oder mehreren verwandten Projekten.</span><span class="sxs-lookup"><span data-stu-id="381db-103">A [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution is a collection of one or more related projects.</span></span> <span data-ttu-id="381db-104">Projekte sind Container, mit denen Entwickler verwandte Dateien organisieren, z. B. Sätze häufig verwendeter Verwaltungsskripts.</span><span class="sxs-lookup"><span data-stu-id="381db-104">Projects are containers that developers use to organize related files, such as sets of commonly used administration scripts.</span></span>  
  
## <a name="solution-overview"></a><span data-ttu-id="381db-105">Übersicht über die Lösungen</span><span class="sxs-lookup"><span data-stu-id="381db-105">Solution Overview</span></span>  
 <span data-ttu-id="381db-106">Sie können [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] als Plattform für die Skriptentwicklung für [!INCLUDE[ssDE](../../includes/ssde-md.md)] und [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="381db-106">You can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] as a script development platform for [!INCLUDE[ssDE](../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="381db-107">Entwickeln Sie Skripts und Abfragen für relationale und mehrdimensionale Datenbanken mithilfe der [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] -Code-Editoren, und sammeln Sie verwandte Skripts und Abfragen in Projekten.</span><span class="sxs-lookup"><span data-stu-id="381db-107">Use the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] code editors to develop scripts and queries for relational and multidimensional databases, and collect related scripts and queries together in projects.</span></span>  
  
 <span data-ttu-id="381db-108">Projekte können Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="381db-108">Projects can contain:</span></span>  
  
-   <span data-ttu-id="381db-109">Abfragen und Skripts, die Produktionsprozesse implementieren.</span><span class="sxs-lookup"><span data-stu-id="381db-109">Queries and scripts that implement production processes.</span></span>  
  
-   <span data-ttu-id="381db-110">Verbindungsinformationen und Dateien, die von den Abfragen und Skripts verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="381db-110">Connection information and files used by the queries and scripts.</span></span>  
  
 <span data-ttu-id="381db-111">Ein oder mehrere verwandte Projekte können in einer Projektmappe kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="381db-111">One or more related projects can be combined in a solution.</span></span> <span data-ttu-id="381db-112">Projektmappen und Projekte können mit dem Bereich Projektmappen-Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="381db-112">Solutions and projects can be managed by using the Solution Explorer pane in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="381db-113">Projektmappen und Projekte können in eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] VSS-Datenbank (Visual SourceSafe)-Datenbank oder in anderen Anbietern der Quellcodeverwaltung von Drittanbietern zum Entwickeln der Änderungsnachverfolgung und Lebensdauerverwaltung integriert werden.</span><span class="sxs-lookup"><span data-stu-id="381db-113">Solutions and projects can be integrated into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe (VSS) database or other third-party source control providers, for development change tracking and life-cycle management.</span></span>  
  
## <a name="solution-tasks"></a><span data-ttu-id="381db-114">Projektmappentasks</span><span class="sxs-lookup"><span data-stu-id="381db-114">Solution Tasks</span></span>  
  
|<span data-ttu-id="381db-115">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="381db-115">Task Description</span></span>|<span data-ttu-id="381db-116">Thema</span><span class="sxs-lookup"><span data-stu-id="381db-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="381db-117">Beschreibt, wie eine neue Projektmappe erstellt wird, die dann ein oder mehrere Projekte enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="381db-117">Describes how to create a new solution that can then be used to contain one or more projects.</span></span>|[<span data-ttu-id="381db-118">Erstellen einer neuen Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-118">Create a New Solution</span></span>](create-a-new-solution.md)|  
|<span data-ttu-id="381db-119">Beschreibt, wie eine vorhandene Projektmappe im Projektmappen-Explorer geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="381db-119">Describes how to open an existing solution in Solution Explorer.</span></span>|[<span data-ttu-id="381db-120">Öffnen einer vorhandenen Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-120">Open an Existing Solution</span></span>](open-an-existing-solution.md)|  
|<span data-ttu-id="381db-121">Beschreibt, wie eine Projektmappe geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="381db-121">Describes how to close a solution.</span></span>|[<span data-ttu-id="381db-122">Schließen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-122">Close a Solution</span></span>](close-a-solution.md)|  
|<span data-ttu-id="381db-123">Beschreibt, wie eine Projektmappe gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="381db-123">Describes how to delete a solution.</span></span>|[<span data-ttu-id="381db-124">Löschen einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-124">Delete a Solution</span></span>](delete-a-solution.md)|  
|<span data-ttu-id="381db-125">Beschreibt, wie Elemente zwischen Projekten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="381db-125">Describes how to copy items between projects.</span></span>|[<span data-ttu-id="381db-126">Kopieren von Elementen in einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-126">Copy Items in a Solution</span></span>](copy-items-in-a-solution.md)|  
|<span data-ttu-id="381db-127">Beschreibt, wie Elemente in einem Projekt oder ein gesamtes Projekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="381db-127">Describes how to delete items in a project, or an entire project.</span></span>|[<span data-ttu-id="381db-128">Entfernen oder Löschen eines Elements oder Projekts</span><span class="sxs-lookup"><span data-stu-id="381db-128">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)|  
|<span data-ttu-id="381db-129">Beschreibt, wie Elemente zwischen Projekten in einer Projektmappe verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="381db-129">Describes how to move items between projects in a solution.</span></span>|[<span data-ttu-id="381db-130">Verschieben von Elementen in einer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="381db-130">Move Items in a Solution</span></span>](move-items-in-a-solution.md)|  
|<span data-ttu-id="381db-131">Beschreibt, wie eine Projektmappe oder die Elemente in der Projektmappe umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="381db-131">Describes how to rename a solution or the items in the solution.</span></span>|[<span data-ttu-id="381db-132">Umbenennen von Projektmappen und Projektelementen</span><span class="sxs-lookup"><span data-stu-id="381db-132">Rename Solutions and Project Items</span></span>](rename-solutions-and-project-items.md)|  
  
## <a name="see-also"></a><span data-ttu-id="381db-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="381db-133">See Also</span></span>  
 <span data-ttu-id="381db-134">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="381db-134">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="381db-135">[Projekte &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="381db-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="381db-136">Quellcodeverwaltung des Projektmappen-Explorers</span><span class="sxs-lookup"><span data-stu-id="381db-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
