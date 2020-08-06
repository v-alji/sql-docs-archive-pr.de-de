---
title: Erstellen von Datenbankprojekten mit SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], database projects
- database projects [SQL Server]
- projects [SQL Server Management Studio], about projects
- projects [SQL Server Management Studio]
ms.assetid: c2e80045-894d-44cf-b65c-e547ed738947
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3ddf3f61e69623716b2987c5c4d849398e822d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607534"
---
# <a name="build-database-projects-by-using-sql-server-management-studio"></a><span data-ttu-id="4117e-102">Erstellen von Datenbankprojekten mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4117e-102">Build Database Projects by Using SQL Server Management Studio</span></span>
  <span data-ttu-id="4117e-103">Bei einem Datenbankskriptprojekt handelt es sich um einen organisierten Satz von Skripts, Verbindungsinformationen und Vorlagen, die alle einer Datenbank oder einem Teil einer Datenbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4117e-103">A database script project is an organized set of scripts, connection information, and templates that are all associated with a database or one part of a database.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="4117e-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] stellt [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] zum Verwalten und Entwerfen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Datenbanken im Kontext eines Skriptprojekts bereit.</span><span class="sxs-lookup"><span data-stu-id="4117e-104">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provides the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] for administering and designing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] databases within the context of a script project.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4117e-105">umfasst Designer, Editoren, Handbücher und Assistenten, die Benutzern bei der Entwicklung, Bereitstellung und Verwaltung von Datenbanken behilflich sind.</span><span class="sxs-lookup"><span data-stu-id="4117e-105">includes designers, editors, guides and wizards to assist users in developing, deploying and maintaining databases.</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="4117e-106">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4117e-106">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4117e-107">ist eine Sammlung von Verwaltungstools zum Verwalten der Komponenten, die zu [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gehören.</span><span class="sxs-lookup"><span data-stu-id="4117e-107">is a suite of administrative tools for managing the components belonging to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4117e-108">Diese integrierte Umgebung ermöglicht es Benutzern, eine Reihe von Aufgaben, wie z. B. das Sichern von Daten, das Bearbeiten von Abfragen und das Automatisieren häufiger Funktionen, in einer einzigen Benutzeroberfläche auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4117e-108">This integrated environment allows users to perform a variety of tasks, such as backing up data, editing queries, and automating common functions within a single interface.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4117e-109">enthält folgende Tools:</span><span class="sxs-lookup"><span data-stu-id="4117e-109">includes the following tools:</span></span>  
  
-   <span data-ttu-id="4117e-110">Der Code-Editor ist ein Skript-Editor mit vielen Funktionen zum Erstellen und Bearbeiten von Skripts.</span><span class="sxs-lookup"><span data-stu-id="4117e-110">Code Editor is a rich script editor for writing and editing scripts.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4117e-111">stellt vier Versionen des Code-Editors bereit: den [!INCLUDE[ssDE](../includes/ssde-md.md)] Abfrage-Editor für [!INCLUDE[tsql](../includes/tsql-md.md)] -Skripts, den DMX-Abfrage-Editor, den MDX-Abfrage-Editor und den XML-/A-Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="4117e-111">provides four versions of the Code Editor; the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor for [!INCLUDE[tsql](../includes/tsql-md.md)] scripts, the DMX Query Editor, the MDX Query Editor, and the XML/A Query Editor.</span></span>  
  
-   <span data-ttu-id="4117e-112">Objekt-Explorer, um Objekte, die zu Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]gehören, zu suchen, zu ändern, auszuführen oder um ein Skript für diese Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4117e-112">Object Explorer for locating, modifying, scripting or running objects belonging to instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4117e-113">Vorlagen-Explorer, um Vorlagen zu suchen und ein Skript dafür zu erstellen</span><span class="sxs-lookup"><span data-stu-id="4117e-113">Template Explorer for locating and scripting templates.</span></span>  
  
-   <span data-ttu-id="4117e-114">Projektmappen-Explorer, um zusammengehörige Skripts als Teile eines Projekts anzuordnen und zu speichern</span><span class="sxs-lookup"><span data-stu-id="4117e-114">Solution Explorer for organizing and storing related scripts as parts of a project.</span></span>  
  
-   <span data-ttu-id="4117e-115">Eigenschaftenfenster, um die aktuellen Eigenschaften von ausgewählten Objekten anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="4117e-115">Properties Window for displaying the current properties of selected objects.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="4117e-116">unterstützt rationelle Arbeitsprozesse, indem Folgendes bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="4117e-116">supports efficient work processes by providing:</span></span>  
  
-   <span data-ttu-id="4117e-117">Zugriff bei getrennter Verbindung.</span><span class="sxs-lookup"><span data-stu-id="4117e-117">Disconnected access.</span></span> <span data-ttu-id="4117e-118">Sie können Skripts erstellen und bearbeiten, ohne mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verbunden zu sein.</span><span class="sxs-lookup"><span data-stu-id="4117e-118">You can write and edit scripts without connecting to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4117e-119">Skripterstellung in jedem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="4117e-119">Scripting from any dialog box.</span></span> <span data-ttu-id="4117e-120">Sie können ein Skript in jedem Dialogfeld erstellen, damit Sie die Skripts nach dem Erstellen lesen, ändern, speichern und wieder verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4117e-120">You can create a script from any dialog box so that you can read, modify, store and reuse the scripts after you create them.</span></span>  
  
-   <span data-ttu-id="4117e-121">Nicht-modale Dialogfelder.</span><span class="sxs-lookup"><span data-stu-id="4117e-121">Nonmodal dialog boxes.</span></span> <span data-ttu-id="4117e-122">Wenn Sie auf ein Benutzeroberflächen-Dialogfeld zugreifen, können Sie andere Ressourcen in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] durchsuchen, ohne das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="4117e-122">When you access a UI dialog box you can browse other resources in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] without closing the dialog box.</span></span>  
  
## <a name="solutions-and-script-projects"></a><span data-ttu-id="4117e-123">Projektmappen und Skriptprojekte</span><span class="sxs-lookup"><span data-stu-id="4117e-123">Solutions and Script Projects</span></span>  
 <span data-ttu-id="4117e-124">Mit dem Projektmappen-Explorer können Sie Datenbankprojektmappen speichern und erneut öffnen.</span><span class="sxs-lookup"><span data-stu-id="4117e-124">Solution Explorer is a utility to store and reopen database solutions.</span></span> <span data-ttu-id="4117e-125">Mit Projektmappen werden zusammengehörige Skriptprojekte und Dateien angeordnet.</span><span class="sxs-lookup"><span data-stu-id="4117e-125">Solutions organize related script projects and files.</span></span> <span data-ttu-id="4117e-126">In Skriptprojekten werden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Skriptdateien, SQL-Vorlagen, Verbindungsinformationen und sonstige Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4117e-126">Script projects store [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] script files, SQL templates, connection information and other miscellaneous files.</span></span> <span data-ttu-id="4117e-127">Wenn ein Skript in einem Skriptprojekt gespeichert wird, können Benutzer folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="4117e-127">When a script is saved in a script project, users are able to:</span></span>  
  
-   <span data-ttu-id="4117e-128">Aufrechterhalten der Versionskontrolle für Skripts</span><span class="sxs-lookup"><span data-stu-id="4117e-128">Maintain version control on scripts.</span></span>  
  
-   <span data-ttu-id="4117e-129">Speichern von Ergebnisoptionen mit einem Skript</span><span class="sxs-lookup"><span data-stu-id="4117e-129">Store results options with a script.</span></span>  
  
-   <span data-ttu-id="4117e-130">Organisieren von zusammengehörigen Skripts zu einem einzigen Skriptprojekt</span><span class="sxs-lookup"><span data-stu-id="4117e-130">Organize related scripts in a single script project.</span></span>  
  
-   <span data-ttu-id="4117e-131">Speichern von Verbindungsinformationen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="4117e-131">Save connection information with scripts.</span></span>  
  
 <span data-ttu-id="4117e-132">Der Projektmappen-Explorer ist ein Tool für Entwickler, die Skripts, die zum gleichen Projekt gehören, erstellen und wieder verwenden.</span><span class="sxs-lookup"><span data-stu-id="4117e-132">Solution Explorer is a tool for developers who are creating and reusing scripts that are related to the same project.</span></span> <span data-ttu-id="4117e-133">Wenn ein ähnlicher Task später erforderlich ist, können Sie Skriptgruppen verwenden, die in einem Projekt gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="4117e-133">If a similar task is required later, you can use group of scripts that were stored in a project.</span></span> <span data-ttu-id="4117e-134">Wenn Sie bereits Anwendungen mithilfe von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] erstellt haben, wird Ihnen der Projektmappen-Explorer vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="4117e-134">If you have created applications by using [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], you will find Solution Explorer very familiar.</span></span>  
  
 <span data-ttu-id="4117e-135">Eine Projektmappe besteht aus mindestens einem Skriptprojekt.</span><span class="sxs-lookup"><span data-stu-id="4117e-135">A solution consists of one or more script projects.</span></span> <span data-ttu-id="4117e-136">Ein Projekt besteht aus mindestens einem Skript oder mindestens einer Verbindung.</span><span class="sxs-lookup"><span data-stu-id="4117e-136">A project consists of one or more scripts or connections.</span></span> <span data-ttu-id="4117e-137">In einem Projekt können außerdem andere Dateien als nur Skriptdateien vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4117e-137">A project may also include nonscript files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4117e-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4117e-138">See Also</span></span>  
 <span data-ttu-id="4117e-139">[SQL Server Management Studio verwenden](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4117e-139">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="4117e-140">[Abfrage-und Text-Editoren &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4117e-140">[Query and Text Editors &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/query-and-text-editors-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="4117e-141">Projektmappen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4117e-141">Solutions &#40;SQL Server Management Studio&#41;</span></span>](solution/solutions-sql-server-management-studio.md)  
  
  
