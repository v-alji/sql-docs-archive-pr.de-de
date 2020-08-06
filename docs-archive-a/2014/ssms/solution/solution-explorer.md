---
title: Projektmappen-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], solutions
- projects [SQL Server Management Studio], about projects
- SQL Server Management Studio [SQL Server], projects
- solutions [SQL Server Management Studio], about solutions
- SQL Server Management Studio [SQL Server], items
- items [SQL Server]
ms.assetid: 0df09843-0d4f-4925-bc6c-99265035a0c1
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa312f5e097fa1c59b9ba545709dc964a184c3f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616308"
---
# <a name="solution-explorer"></a><span data-ttu-id="0aa5f-102">Projektmappen-Explorer</span><span class="sxs-lookup"><span data-stu-id="0aa5f-102">Solution Explorer</span></span>
  <span data-ttu-id="0aa5f-103">Der Bereich des Projektmappen-Explorers in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] enthält als Projekte bezeichnete Container, mit denen sich Elementen wie Datenbankskripts, Abfragen, Datenverbindungen und Dateien verwalten lassen.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-103">The Solution Explorer pane in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides containers called projects for managing items such as database scripts, queries, data connections, and files.</span></span> <span data-ttu-id="0aa5f-104">Miteinander verknüpfte Projekte können in einem Projektmappe genannten Container zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-104">One or more projects that are related to each other can be combined in a container called a solution.</span></span>  
  
 <span data-ttu-id="0aa5f-105">Eine Projektmappe enthält ein oder mehrere Projekte sowie Dateien und Metadaten, die zur Definition der Projektmappe als Ganzes dienen.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-105">A solution includes one or more projects, plus files and metadata that help define the solution as a whole.</span></span> <span data-ttu-id="0aa5f-106">Ein Projekt ist eine Gruppe von Dateien und zugehörigen Metadaten, wie Verbindungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-106">A project is a set of files, plus related metadata such as connection information.</span></span> <span data-ttu-id="0aa5f-107">Projektmappen und Projekte enthalten Elemente, die die Skripts, Abfragen, Verbindungsinformationen und Dateien repräsentieren, die Sie zum Erstellen der Datenbankprojektmappe benötigen.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-107">Solutions and projects contain items that represent the scripts, queries, connection information and files that you need to create your database solution.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
## <a name="benefits-of-using-solutions"></a><span data-ttu-id="0aa5f-108">Vorteile der Verwendung von Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0aa5f-108">Benefits of Using Solutions</span></span>  
 <span data-ttu-id="0aa5f-109">Verwenden Sie diese Container zu folgenden Zwecken:</span><span class="sxs-lookup"><span data-stu-id="0aa5f-109">Use these containers to:</span></span>  
  
-   <span data-ttu-id="0aa5f-110">Implementieren der Quellcodeverwaltung für Abfragen und Skripts.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-110">Implement source control on queries and scripts.</span></span>  
  
-   <span data-ttu-id="0aa5f-111">Verwalten der Einstellungen für eine Projektmappe als Ganzes oder für einzelne Projekte.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-111">Manage settings for your solution as a whole or for individual projects.</span></span>  
  
-   <span data-ttu-id="0aa5f-112">Behandlung der Dateiverwaltung im Detail mit Schwerpunkt auf den Elementen, aus denen die Datenbankprojektmappe besteht.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-112">Handle the details of file management while you focus on items that make up your database solution.</span></span>  
  
-   <span data-ttu-id="0aa5f-113">Hinzufügen von Elementen, die für mehrere Projekte in der Projektmappe oder für die Projektmappe nützlich sind, ohne auf das Element in den einzelnen Projekten verweisen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-113">Add items that are useful to multiple projects in the solution or to the solution without referencing the item in each project.</span></span>  
  
-   <span data-ttu-id="0aa5f-114">Arbeiten an verschiedenen, von Projektmappen oder Projekten unabhängigen Dateien.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-114">Work on miscellaneous files that are independent from solutions or projects.</span></span>  
  
 <span data-ttu-id="0aa5f-115">Die Elemente in Projekten hängen vom Projekttyp ab und davon, ob Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-115">The items contained in projects depend on the project type and whether you are using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0aa5f-116">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0aa5f-116">Related Tasks</span></span>  
 <span data-ttu-id="0aa5f-117">Erste Schritte mit den SQL Server-Lösungen mithilfe der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="0aa5f-117">Use the following topics to get started with SQL Server Solutions:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0aa5f-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0aa5f-118">**Description**</span></span>|<span data-ttu-id="0aa5f-119">**Thema**</span><span class="sxs-lookup"><span data-stu-id="0aa5f-119">**Topic**</span></span>|  
|<span data-ttu-id="0aa5f-120">Beschreibt, wie ein Projekt oder mehrere Projekte in einer Projektmappe gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-120">Describes how to collect one or more projects in a solution.</span></span>|[<span data-ttu-id="0aa5f-121">Projektmappen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0aa5f-121">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solutions-sql-server-management-studio.md)|  
|<span data-ttu-id="0aa5f-122">Beschreibt, wie ein Projekt erstellt und Elemente wie Skripts und Verbindungen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-122">Describes how to create a project and add items like scripts and connections.</span></span>|[<span data-ttu-id="0aa5f-123">Projekte &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0aa5f-123">Projects &#40;SQL Server Management Studio&#41;</span></span>](projects-sql-server-management-studio.md)|  
|<span data-ttu-id="0aa5f-124">Beschreibt, wie Lösungen oder einzelne Projekte in ein Quellcodeverwaltungssystem integriert werden.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-124">Describes how to integrate solutions or individual projects into a source code control system.</span></span>|[<span data-ttu-id="0aa5f-125">Quellcodeverwaltung des Projektmappen-Explorers</span><span class="sxs-lookup"><span data-stu-id="0aa5f-125">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)|  
|<span data-ttu-id="0aa5f-126">Enthält Informationen zu den Dateien, mit denen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Projektmappen und Dateien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0aa5f-126">Provides information about the files used by [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage solutions and files.</span></span>|[<span data-ttu-id="0aa5f-127">Dateien zum Verwalten von Projektmappen und Projekten</span><span class="sxs-lookup"><span data-stu-id="0aa5f-127">Files That Manage Solutions and Projects</span></span>](files-that-manage-solutions-and-projects.md)|  
  
  
