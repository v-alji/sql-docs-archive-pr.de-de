---
title: Optionen (Umgebung, Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Environment.SQLEnvironmentOptions
ms.assetid: c32ccdb8-2cf8-4c78-b474-a3abd3dbbd13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7712c568b478bd2ba958237ba3204246657b3a72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630469"
---
# <a name="options-environment-general-page"></a><span data-ttu-id="d57bd-102">Optionen (Seite „Umgebung“/„Allgemein“)</span><span class="sxs-lookup"><span data-stu-id="d57bd-102">Options (Environment-General Page)</span></span>
  <span data-ttu-id="d57bd-103">Im Dialogfeld **Optionen** können Sie die Startaktionen, Optionen für die Fensterverwaltung und andere allgemeine Optionen für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d57bd-103">Use the **Options** dialog box to configure [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] startup actions, general window management options, and other general settings.</span></span> <span data-ttu-id="d57bd-104">Klicken Sie im Menü **Extras** auf **Optionen**, erweitern Sie den Ordner **Umgebung** , und klicken Sie anschließend auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="d57bd-104">On the **Tools** menu, click **Options**, expand the **Environment** folder, and then click **General**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d57bd-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="d57bd-105">UI element list</span></span>  
 <span data-ttu-id="d57bd-106">**Beim Start**</span><span class="sxs-lookup"><span data-stu-id="d57bd-106">**At startup**</span></span>  
 <span data-ttu-id="d57bd-107">Wählen Sie die Aktion aus, die beim Start von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d57bd-107">Select the action for [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to perform when it is started.</span></span> <span data-ttu-id="d57bd-108">Die Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="d57bd-108">The options are:</span></span>  
  
-   <span data-ttu-id="d57bd-109">Mit**Objekt-Explorer öffnen** werden Sie aufgefordert, eine Verbindung anzugeben, und der Objekt-Explorer wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-109">**Open Object Explorer** prompts for a connection and then opens Object Explorer.</span></span>  
  
-   <span data-ttu-id="d57bd-110">Mit**Neues Abfragefenster öffnen** werden Sie aufgefordert, eine Verbindung anzugeben, und der SQL-Abfrage-Editor wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-110">**Open new query window** prompts for a connection and then opens SQL Query Editor.</span></span>  
  
-   <span data-ttu-id="d57bd-111">Mit**Objekt-Explorer und neue Abfrage öffnen** werden Sie aufgefordert, eine Verbindung anzugeben, und anschließend werden mit dieser Verbindung sowohl der Objekt-Explorer als auch der SQL-Abfrage-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d57bd-111">**Open Object Explorer and new query** prompts for a connection, then opens both Object Explorer and SQL Query Editor with that connection.</span></span>  
  
-   <span data-ttu-id="d57bd-112">Mit**Leere Umgebung öffnen** wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aufgerufen, ohne dass das Fenster des SQL-Abfrage-Editors geöffnet oder eine Objekt-Explorer-Verbindung zu einem Server hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d57bd-112">**Open empty environment** opens [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] without a SQL Query editor window and without connecting Object Explorer to a server.</span></span>  
  
 <span data-ttu-id="d57bd-113">**Systemobjekte im Objekt-Explorer ausblenden**</span><span class="sxs-lookup"><span data-stu-id="d57bd-113">**Hide system objects in Object Explorer**</span></span>  
 <span data-ttu-id="d57bd-114">Aktivieren Sie dieses Kontrollkästchen, um Systemdatenbanken, Systemtabellen, Systemsichten und gespeicherte Systemprozeduren aus der Struktursicht des Objekt-Explorers zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-114">Select this check box to remove the system databases, system tables, system views, and system stored procedures from tree view in Object Explorer.</span></span> <span data-ttu-id="d57bd-115">Systemfunktionen und Systemdatentypen werden nicht ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d57bd-115">System functions and system data types are not hidden.</span></span> <span data-ttu-id="d57bd-116">Diese Option betrifft nur Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , d. h., sie wirkt sich nicht auf Server aus, die im Objekt-Explorer bereits verbunden wurden.</span><span class="sxs-lookup"><span data-stu-id="d57bd-116">This option only applies to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and does not affect servers already connected in Object Explorer.</span></span>  
  
## <a name="environment-layout"></a><span data-ttu-id="d57bd-117">Umgebungslayout</span><span class="sxs-lookup"><span data-stu-id="d57bd-117">Environment Layout</span></span>  
 <span data-ttu-id="d57bd-118">Um zwischen den Umgebungsmodi MDI-Schnittstelle (Multiple Document Interface) und Dokumente im Registerformat wechseln zu können, müssen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] schließen und wieder öffnen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-118">You must close and reopen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change between tabbed document and multiple-document interface (MDI) environment mode.</span></span>  
  
 <span data-ttu-id="d57bd-119">**Dokumente im Registerformat**</span><span class="sxs-lookup"><span data-stu-id="d57bd-119">**Tabbed documents**</span></span>  
 <span data-ttu-id="d57bd-120">Wählen Sie diese Option aus, um Dokumentfenster anzuzeigen, die in Editoren als Registerkarten zusammengefasst sind.</span><span class="sxs-lookup"><span data-stu-id="d57bd-120">Select this option to display document windows that are tabbed together within editors.</span></span> <span data-ttu-id="d57bd-121">Dokumentfenster im Registerformat werden verwendet, um mehrere offene Dokumente zu organisieren und problemlos zwischen den Dokumenten wechseln zu können.</span><span class="sxs-lookup"><span data-stu-id="d57bd-121">Tabbed document windows are useful for organizing and switching between multiple open documents.</span></span>  
  
 <span data-ttu-id="d57bd-122">**MDI-Umgebung**</span><span class="sxs-lookup"><span data-stu-id="d57bd-122">**MDI environment**</span></span>  
 <span data-ttu-id="d57bd-123">Wählen Sie diese Option aus, um Dokumente in einer MDI-Umgebung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-123">Select this option to open documents in a MDI environment.</span></span> <span data-ttu-id="d57bd-124">MDI-Dokumentfenster werden verwendet, um auf dem Bildschirm wieder Platz zu gewinnen, der andernfalls durch die Registerkarten der Dokumente im Registerformat belegt ist.</span><span class="sxs-lookup"><span data-stu-id="d57bd-124">MDI document windows are useful for gaining the screen space that is otherwise taken up by the tabs in the tabbed documents environment.</span></span> <span data-ttu-id="d57bd-125">Wenn Sie im MDI-Modus arbeiten und zwischen Dokumenten wechseln müssen, verwenden Sie die Tastenkombination STRG+TAB oder die im Menü **Fenster** verfügbaren Optionen zum Anordnen von Fenstern.</span><span class="sxs-lookup"><span data-stu-id="d57bd-125">When working in MDI mode, you can switch between documents by pressing CTRL+TAB, or you can use the tile options located on the **Window** menu.</span></span>  
  
## <a name="docked-tool-window-behavior"></a><span data-ttu-id="d57bd-126">Verhalten angedockter Toolfenster</span><span class="sxs-lookup"><span data-stu-id="d57bd-126">Docked Tool Window Behavior</span></span>  
 <span data-ttu-id="d57bd-127">**Die Schaltfläche 'Schließen' betrifft nur die aktive Registerkarte**</span><span class="sxs-lookup"><span data-stu-id="d57bd-127">**Close button affects active tab only**</span></span>  
 <span data-ttu-id="d57bd-128">Wenn dieses Kontrollkästchen aktiviert wird, werden nicht alle Toolfenster im angedockten Satz, sondern nur das aktuell fokussierte Toolfenster geschlossen.</span><span class="sxs-lookup"><span data-stu-id="d57bd-128">Specifies that when this check box is selected, only the tool window that has focus currently is closed and not all of the tool windows in the docked set.</span></span> <span data-ttu-id="d57bd-129">Standardmäßig ist dieses Kontrollkästchen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d57bd-129">By default, this check box is selected.</span></span>  
  
 <span data-ttu-id="d57bd-130">**Die Schaltfläche zum automatischen Ausblenden betrifft nur die aktive Registerkarte**</span><span class="sxs-lookup"><span data-stu-id="d57bd-130">**Auto Hide button affects active tab only**</span></span>  
 <span data-ttu-id="d57bd-131">Wenn dieses Kontrollkästchen aktiviert wird, werden nicht alle Toolfenster im angedockten Satz, sondern nur das aktuell fokussierte Toolfenster ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="d57bd-131">Specifies that when this check box is selected, only the tool window that has focus currently is hidden automatically, not all of the tool windows in the docked set.</span></span> <span data-ttu-id="d57bd-132">Standardmäßig ist dieses Kontrollkästchen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d57bd-132">By default, this check box is cleared.</span></span>  
  
## <a name="display"></a><span data-ttu-id="d57bd-133">Anzeige</span><span class="sxs-lookup"><span data-stu-id="d57bd-133">Display</span></span>  
 <span data-ttu-id="d57bd-134">**Dateien in der Liste zuletzt verwendeter Dateien**</span><span class="sxs-lookup"><span data-stu-id="d57bd-134">**Display n files in recently used list**</span></span>  
 <span data-ttu-id="d57bd-135">Passt die Anzahl zuletzt bearbeiteter Projekte und Dateien an, die im Menü **Datei** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d57bd-135">Customizes the number of recent projects and recent files that appear on the **File** menu.</span></span> <span data-ttu-id="d57bd-136">Geben Sie eine Zahl zwischen 1 und 24 ein.</span><span class="sxs-lookup"><span data-stu-id="d57bd-136">Type a number between 1 and 24.</span></span> <span data-ttu-id="d57bd-137">Der Standardwert ist 4.</span><span class="sxs-lookup"><span data-stu-id="d57bd-137">The default is 4.</span></span> <span data-ttu-id="d57bd-138">Diese Option erleichtert das Abrufen kürzlich verwendeter Skriptprojekte und -dateien.</span><span class="sxs-lookup"><span data-stu-id="d57bd-138">This is an easy way to retrieve recently used script projects and files and script projects.</span></span>  
  
  
