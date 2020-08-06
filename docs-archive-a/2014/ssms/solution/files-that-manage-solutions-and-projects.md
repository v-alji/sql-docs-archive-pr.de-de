---
title: Dateien zum Verwalten von Projektmappen und Projekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], files
- .ssmssln files
- .ssmsmobileproj files
- .ssmsasproj files
- .ssmssqlproj files
- .sqlsuo files
- files [SQL Server Management Studio], projects
ms.assetid: e19d2859-0b97-4727-ac27-c4c226d86b2f
author: stevestein
ms.author: sstein
ms.openlocfilehash: c94f1f853263c3969961de91ec95b921f5d78ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700562"
---
# <a name="files-that-manage-solutions-and-projects"></a><span data-ttu-id="d296f-102">Dateien zum Verwalten von Projektmappen und Projekten</span><span class="sxs-lookup"><span data-stu-id="d296f-102">Files That Manage Solutions and Projects</span></span>
  <span data-ttu-id="d296f-103">In diesem Artikel werden die Dateitypen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d296f-103">This topic describes the file types that are specific to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d296f-104">Standardmäßig werden alle Projektmappen und Projekte im Verzeichnis \Meine Dokumente\SQL Server Management Studio Projects erstellt.</span><span class="sxs-lookup"><span data-stu-id="d296f-104">By default, all solutions and their projects are created in \My Documents\SQL Server Management Studio Projects.</span></span>  
  
## <a name="management-studio-solution-files"></a><span data-ttu-id="d296f-105">Management Studio-Projektmappendateien</span><span class="sxs-lookup"><span data-stu-id="d296f-105">Management Studio Solution Files</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d296f-106">verwendet andere Dateitypen als [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d296f-106">uses different file types than [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio.</span></span> <span data-ttu-id="d296f-107">Dies bedeutet, dass Sie eine [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Projektmappe nicht in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder in Visual Studio öffnen können.</span><span class="sxs-lookup"><span data-stu-id="d296f-107">This means you cannot open a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] solution in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or in Visual Studio.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d296f-108">Projektmappendateien ermöglichen dem Projektmappen-Explorer, eine grafische Benutzeroberfläche zum Verwalten Ihrer Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d296f-108">solution files allow Solution Explorer to display a graphical interface for managing your files.</span></span>  
  
|<span data-ttu-id="d296f-109">Durchwahl</span><span class="sxs-lookup"><span data-stu-id="d296f-109">Extension</span></span>|<span data-ttu-id="d296f-110">Dateityp</span><span class="sxs-lookup"><span data-stu-id="d296f-110">File type</span></span>|<span data-ttu-id="d296f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d296f-111">Description</span></span>|<span data-ttu-id="d296f-112">Erstellt von</span><span class="sxs-lookup"><span data-stu-id="d296f-112">Created by</span></span>|  
|---------------|---------------|-----------------|----------------|  
|<span data-ttu-id="d296f-113">SSMSSLN</span><span class="sxs-lookup"><span data-stu-id="d296f-113">.ssmssln</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="d296f-114">Projektmappenobjekt</span><span class="sxs-lookup"><span data-stu-id="d296f-114">Solution Object</span></span>|<span data-ttu-id="d296f-115">Diese Erweiterung stellt der Umgebung Verweise auf den Speicherort auf dem Datenträger von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Projekten, -Projektelementen und -Lösungen bereit.</span><span class="sxs-lookup"><span data-stu-id="d296f-115">Provides the environment with references to the location on disk of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] projects, project items, and solution</span></span>|[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]|  
  
## <a name="management-studio-project-files"></a><span data-ttu-id="d296f-116">Management Studio-Projektdateien</span><span class="sxs-lookup"><span data-stu-id="d296f-116">Management Studio Project Files</span></span>  
 <span data-ttu-id="d296f-117">In derselben Weise, wie Projektmappen Projektmappendateien zum Verwalten von Objekten in einer Projektmappe enthalten, enthalten Projekte Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="d296f-117">In the same way that solutions contain solution files that manage objects in a solution, projects contain project files.</span></span> <span data-ttu-id="d296f-118">Der Projektdateityp, der von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] für ein Projekt erstellt wird, hängt von der Vorlage ab, mit der das Projekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d296f-118">The type of project file that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] creates for a project depends on the template used to create the project.</span></span> <span data-ttu-id="d296f-119">In der folgenden Tabelle werden die Dateitypen beschrieben, die für die einzelnen Projekte erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d296f-119">The following table describes the type of file created for each project.</span></span>  
  
|<span data-ttu-id="d296f-120">Durchwahl</span><span class="sxs-lookup"><span data-stu-id="d296f-120">Extension</span></span>|<span data-ttu-id="d296f-121">Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="d296f-121">Project template</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="d296f-122">SSMSSQLPROJ</span><span class="sxs-lookup"><span data-stu-id="d296f-122">.ssmssqlproj</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d296f-123">Skriptprojekt</span><span class="sxs-lookup"><span data-stu-id="d296f-123">Scripts Project</span></span>|  
|<span data-ttu-id="d296f-124">SSMSASPROJ</span><span class="sxs-lookup"><span data-stu-id="d296f-124">.ssmsasproj</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d296f-125">Skriptprojekt</span><span class="sxs-lookup"><span data-stu-id="d296f-125">Scripts Project</span></span>|  
  
## <a name="location-of-solution-level-files"></a><span data-ttu-id="d296f-126">Speicherort für Dateien auf Projektmappenebene</span><span class="sxs-lookup"><span data-stu-id="d296f-126">Location of Solution-Level Files</span></span>  
 <span data-ttu-id="d296f-127">Standardmäßig werden Dateien auf Projektmappenebene im physischen Verzeichnis des ersten Projekts erstellt, das mit der Projektmappe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d296f-127">By default, solution-level files are created in the physical directory of the first project that is created with the solution.</span></span> <span data-ttu-id="d296f-128">Sie können ein Verzeichnis für die Projektmappe angeben, indem Sie eine Projektmappe erstellen. Sie können das Verzeichnis auch angeben, wenn Sie ein neues Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="d296f-128">You can specify a directory for the solution by creating a solution, or you can specify the directory when you create a new project.</span></span>  
  
 <span data-ttu-id="d296f-129">Wenn eine Verzeichnisstruktur vorhanden ist, die der logischen Struktur im Projektmappen-Explorer ähnelt, lassen sich Projekt- und Projektmappendateien einfacher suchen und mit anderen Entwicklern im Team gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="d296f-129">If you have a directory structure similar to the logical structure shown in Solution Explorer, project and solution files are easier to locate and share with other developers on a team.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d296f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d296f-130">See Also</span></span>  
 <span data-ttu-id="d296f-131">[Verwalten von Dateien mit Codierung](manage-files-with-encoding.md) </span><span class="sxs-lookup"><span data-stu-id="d296f-131">[Manage Files with Encoding](manage-files-with-encoding.md) </span></span>  
 <span data-ttu-id="d296f-132">[Sonstige Dateien](miscellaneous-files.md) </span><span class="sxs-lookup"><span data-stu-id="d296f-132">[Miscellaneous Files](miscellaneous-files.md) </span></span>  
 <span data-ttu-id="d296f-133">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="d296f-133">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="d296f-134">[Lösungen &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d296f-134">[Solutions &#40;SQL Server Management Studio&#41;](solutions-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="d296f-135">[Projekte &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="d296f-135">[Projects &#40;SQL Server Management Studio&#41;](projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="d296f-136">Quellcodeverwaltung des Projektmappen-Explorers</span><span class="sxs-lookup"><span data-stu-id="d296f-136">Solution Explorer Source Control</span></span>](../../database-engine/solution-explorer-source-control.md)  
  
  
