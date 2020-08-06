---
title: Verwenden von Microsoft SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Management Studio [SQL Server]
- Enterprise Manager (See SQL Server Management Studio [Analysis Services])
- SQL Server Management Studio [SQL Server], about SQL Server Management Studio
ms.assetid: f289e978-14ca-46ef-9e61-e1fe5fd593be
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fed75ae8d4a1cfba7fb890a5b0b9c159c13366f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608798"
---
# <a name="use-sql-server-management-studio"></a><span data-ttu-id="8f284-102">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-102">Use SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]<span data-ttu-id="8f284-103">(SSMS) ist eine integrierte Umgebung für den Zugriff, die Konfiguration, Verwaltung und Entwicklung aller Komponenten von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f284-103">(SSMS) is an integrated environment for accessing, configuring, managing, administering, and developing all components of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8f284-104">SSMS kombiniert eine Vielzahl grafischer Tools mit einer Reihe umfassender Skript-Editoren, um Entwicklern und Administratoren mit verschiedenem Kenntnisstand den Zugriff auf [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8f284-104">SSMS combines a broad group of graphical tools with a number of rich script editors to provide access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to developers and administrators of all skill levels.</span></span>  
  
 <span data-ttu-id="8f284-105">SSMS kombiniert die Funktionen von Enterprise Manager, Query Analyzer und dem Analysis-Manager aus den vorherigen Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]in einer einzigen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="8f284-105">SSMS combines the features of Enterprise Manager, Query Analyzer, and Analysis Manager, included in previous releases of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], into a single environment.</span></span> <span data-ttu-id="8f284-106">Darüber hinaus kann SSMS mit allen Komponenten von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] verwendet werden, z. B. [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] und [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f284-106">In addition, SSMS works with all components of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] such as [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="8f284-107">Diese Umgebung ist Entwicklern vertraut und stellt für Administratoren ein einziges Hilfsprogramm mit einfachen grafischen Tools und umfangreichen Skripterstellungsfunktionen zum Ausführen ihrer Aufgaben bereit.</span><span class="sxs-lookup"><span data-stu-id="8f284-107">Developers get a familiar experience, and database administrators get a single comprehensive utility that combines easy-to-use graphical tools with rich scripting capabilities.</span></span>  
  
 <span data-ttu-id="8f284-108">Laden Sie SSMS aus dem [Microsoft Developer Network](https://msdn.microsoft.com/library/dn434042.aspx)herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="8f284-108">Download and install SSMS from the [Microsoft Developer Network](https://msdn.microsoft.com/library/dn434042.aspx).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f284-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8f284-109">In This Section</span></span>  
 [<span data-ttu-id="8f284-110">Funktionen in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-110">Features in SQL Server Management Studio</span></span>](features-in-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-111">Führt die vielfältigen Funktionen in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]auf.</span><span class="sxs-lookup"><span data-stu-id="8f284-111">Lists the rich feature set included in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-112">Toolfenster in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-112">Tool Windows in SQL Server Management Studio</span></span>](../ssms/tool-windows-in-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-113">Beschreibt die Tools, die Komponenten von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]sind.</span><span class="sxs-lookup"><span data-stu-id="8f284-113">Describes the tools that are components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-114">Grundlegendes zur SQL Server Management Studio-Fensterverwaltung</span><span class="sxs-lookup"><span data-stu-id="8f284-114">Understand SQL Server Management Studio Windows Management</span></span>](../ssms/understand-sql-server-management-studio-windows-management.md)  
 <span data-ttu-id="8f284-115">Beschreibt, wie die Fenster verwaltet werden, die in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8f284-115">Describes how to manage the windows displayed in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-116">Verwalten von Servern mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-116">Administer Servers with SQL Server Management Studio</span></span>](../ssms/administer-servers-with-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-117">Beschreibt, wie die Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8f284-117">Describes how to administer instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-118">Herstellen einer Verbindung mit einer beliebigen SQL Server-Komponente aus SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-118">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>](../ssms/f1-help/connect-to-any-sql-server-component-from-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-119">Beschreibt, wie eine Verbindung mit Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] hergestellt wird und bestimmte Aufgaben ohne bestehende Verbindung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8f284-119">Describes how to connect to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and how to perform certain tasks without a connection.</span></span>  
  
 [<span data-ttu-id="8f284-120">Objekt-Explorers</span><span class="sxs-lookup"><span data-stu-id="8f284-120">Object Explorer</span></span>](../ssms/object/object-explorer.md)  
 <span data-ttu-id="8f284-121">Beschreibt die Funktionen des Objekt-Explorers.</span><span class="sxs-lookup"><span data-stu-id="8f284-121">Describes the features of the Object Explorer.</span></span>  
  
 [<span data-ttu-id="8f284-122">Benutzerunterstützung in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-122">User Assistance in SQL Server Management Studio</span></span>](../ssms/user-assistance-in-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-123">Beschreibt das Konfigurieren der Benutzerunterstützung, z. B. die Hilfe, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f284-123">Describes how to configure user assistance, such as Help, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-124">Abfrage- und Text-Editoren &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8f284-124">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-125">Beschreibt das Verwenden der funktionsreichen Umgebung in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , um [!INCLUDE[tsql](../includes/tsql-md.md)]-, MDX-, DMX- und XML/A-Skripts zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f284-125">Describes how to use the rich editing environment in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to edit [!INCLUDE[tsql](../includes/tsql-md.md)], MDX, DMX and XML/A scripts.</span></span>  
  
 [<span data-ttu-id="8f284-126">Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="8f284-126">Edit SQLCMD Scripts with Query Editor</span></span>](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md)  
 <span data-ttu-id="8f284-127">Beschreibt die Möglichkeiten und Einschränkungen beim Verwenden des Abfrage-Editors im SQLCMD-Modus.</span><span class="sxs-lookup"><span data-stu-id="8f284-127">Describes the capabilities and limitations of using Query Editor in SQLCMD mode.</span></span>  
  
 [<span data-ttu-id="8f284-128">Farbcodierung im Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="8f284-128">Color Coding in Query Editors</span></span>](../relational-databases/scripting/color-coding-in-query-editors.md)  
 <span data-ttu-id="8f284-129">Beschreibt die Bedeutung der Farbcodierung in Fenstern des Code-Editors.</span><span class="sxs-lookup"><span data-stu-id="8f284-129">Describes the meaning of the color coding in Code Editor windows.</span></span>  
  
 [<span data-ttu-id="8f284-130">Tastenkombinationen für SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-130">SQL Server Management Studio Keyboard Shortcuts</span></span>](../ssms/sql-server-management-studio-keyboard-shortcuts.md)  
 <span data-ttu-id="8f284-131">Führt die verfügbaren Tastenkombinationen in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]auf.</span><span class="sxs-lookup"><span data-stu-id="8f284-131">Lists the keyboard shortcuts available in the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-132">Anpassen von Menüs und Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="8f284-132">Customize Menus and Shortcut Keys</span></span>](../ssms/customize-menus-and-shortcut-keys.md)  
 <span data-ttu-id="8f284-133">Beschreibt das Erstellen von benutzerdefinierten Menüs und Tastenkombinationen.</span><span class="sxs-lookup"><span data-stu-id="8f284-133">Describes how to create custom menus and shortcuts.</span></span>  
  
 [<span data-ttu-id="8f284-134">Projektmappen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8f284-134">Solutions &#40;SQL Server Management Studio&#41;</span></span>](../ssms/solution/solutions-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-135">Beschreibt das Entwickeln von Skriptprojekten und Projektmappen.</span><span class="sxs-lookup"><span data-stu-id="8f284-135">Describes how to develop script projects and solutions.</span></span>  
  
 [<span data-ttu-id="8f284-136">Template Explorer</span><span class="sxs-lookup"><span data-stu-id="8f284-136">Template Explorer</span></span>](../ssms/template/template-explorer.md)  
 <span data-ttu-id="8f284-137">Beschreibt das Verwenden der [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] -Vorlagen und das Erstellen von benutzerdefinierten Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="8f284-137">Describes how to use the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] templates and how to create custom templates.</span></span>  
  
 [<span data-ttu-id="8f284-138">Eigenschaftenseiten in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f284-138">Property Pages in SQL Server Management Studio</span></span>](../ssms/property-pages-in-sql-server-management-studio.md)  
 <span data-ttu-id="8f284-139">Beschreibt das neue Layout des Eigenschaftenfensters in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f284-139">Describes the new property window layout in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [<span data-ttu-id="8f284-140">Designer in Visual Database Tools</span><span class="sxs-lookup"><span data-stu-id="8f284-140">Visual Database Tool Designers</span></span>](../ssms/visual-db-tools/visual-database-tool-designers.md)  
 <span data-ttu-id="8f284-141">Beschreibt die Visual Database Tools, die Sie zum Erstellen von Abfragen, zum Entwerfen oder Ändern einer Datenbankstruktur oder zum Aktualisieren von Daten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8f284-141">Describes the Visual Database Tools that you can use to create queries, design or modify a database structure, or update data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f284-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f284-142">See Also</span></span>  
 [<span data-ttu-id="8f284-143">Anzeigen oder Ändern von Servereigenschaften &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8f284-143">View or Change Server Properties &#40;SQL Server&#41;</span></span>](configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
