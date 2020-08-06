---
title: Projektmappen-Explorer Quell Code Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619985"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="acb02-102">Quellcodeverwaltung des Projektmappen-Explorers</span><span class="sxs-lookup"><span data-stu-id="acb02-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="acb02-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Projektmappen-Explorer können in ein separates Quell Code Verwaltungssystem integriert werden.</span><span class="sxs-lookup"><span data-stu-id="acb02-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="acb02-104">Wenn eine Projektmappe oder ein Projekt in ein Quellcodeverwaltungssystem integriert wird, können Sie Dateizugriff und Versionsverwaltung für die Skripts und Abfragen in Ihren Projekten steuern.</span><span class="sxs-lookup"><span data-stu-id="acb02-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="acb02-105">Quellcodeverwaltung in Projektmappen und Projekten</span><span class="sxs-lookup"><span data-stu-id="acb02-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="acb02-106">Die Quellcodeverwaltung steht für ein System, in dem eine Serversoftware Dateiversionen speichert und nachverfolgt sowie den Zugriff auf Dateien steuert.</span><span class="sxs-lookup"><span data-stu-id="acb02-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="acb02-107">Ein typisches Quellcodeverwaltungssystem enthält einen Quellcodeverwaltungsanbieter und zwei oder mehr Quellcodeverwaltungsclients.</span><span class="sxs-lookup"><span data-stu-id="acb02-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="acb02-108">kann in einen Quellcodeverwaltungsdienst integriert werden.</span><span class="sxs-lookup"><span data-stu-id="acb02-108">can be integrated with a source control service.</span></span> <span data-ttu-id="acb02-109">Das bedeutet, dass Sie das Tool als einen Client für den Quellcodeverwaltungsanbieter verwenden können.</span><span class="sxs-lookup"><span data-stu-id="acb02-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="acb02-110">Sie können auf einfache Weise eigene und teambasierte Projekte verwalten, ohne die Umgebung zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="acb02-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="acb02-111">Der Quellcodeverwaltungsanbieter ist nicht in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="acb02-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="acb02-112">So wählen Sie einen Quellcodeverwaltungsanbieter aus</span><span class="sxs-lookup"><span data-stu-id="acb02-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="acb02-113">Installieren Sie den Teil des Clients auf den Quellcodeverwaltungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="acb02-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="acb02-114">Klicken Sie in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="acb02-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="acb02-115">Erweitern Sie im Dialogfeld **Optionen** den Eintrag **Quell**Code Verwaltung, und klicken Sie dann auf die Seite **Plug-in-Auswahl** .</span><span class="sxs-lookup"><span data-stu-id="acb02-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="acb02-116">Wählen Sie im Feld **Aktuelles Quellcodeverwaltungs-Plug-** in das Quellcodeverwaltungs-Plug-in aus.</span><span class="sxs-lookup"><span data-stu-id="acb02-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acb02-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="acb02-117">In This Section</span></span>  
  
|<span data-ttu-id="acb02-118">Thema</span><span class="sxs-lookup"><span data-stu-id="acb02-118">Topic</span></span>|<span data-ttu-id="acb02-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="acb02-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="acb02-120">Grundlagen zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="acb02-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="acb02-121">Definiert die allgemeinen Terminologie für die Quellcodeverwaltung und beschreibt, auf welche Weise das Projekt von Quellcodeverwaltungsdiensten profitieren kann.</span><span class="sxs-lookup"><span data-stu-id="acb02-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="acb02-122">Hinzufügen von Projektmappen und Projekten zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="acb02-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="acb02-123">Beschreibt, wie Sie mithilfe der [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]-Umgebung Projektmappen und Projekte zur Quellcodeverwaltung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="acb02-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="acb02-124">Öffnen von Projektmappen und Projekten aus der Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="acb02-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="acb02-125">Beschreibt, wie Sie mithilfe der [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]-Umgebung quellcodeverwaltete Projektmappen und Projekte öffnen.</span><span class="sxs-lookup"><span data-stu-id="acb02-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="acb02-126">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="acb02-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="acb02-127">Beschreibt, wie Sie Projektmappen und Dateien aus der Quellcodeverwaltung auschecken.</span><span class="sxs-lookup"><span data-stu-id="acb02-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="acb02-128">Verwalten von Eincheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="acb02-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="acb02-129">Beschreibt, wie Sie Projektmappen und Dateien in die Quellcodeverwaltung einchecken.</span><span class="sxs-lookup"><span data-stu-id="acb02-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="acb02-130">Festlegen und Abrufen von Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="acb02-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="acb02-131">Beschreibt, wie Sie den Verlauf für ein Projekt oder Element abrufen, eine lokale Kopie eines Elements abrufen oder zwei Elementversionen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="acb02-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="acb02-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="acb02-132">See Also</span></span>  
 <span data-ttu-id="acb02-133">[Projektmappen-Explorer](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="acb02-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="acb02-134">[Lösungen &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="acb02-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="acb02-135">[Projekte &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="acb02-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="acb02-136">Dateien zum Verwalten von Projektmappen und Projekten</span><span class="sxs-lookup"><span data-stu-id="acb02-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
