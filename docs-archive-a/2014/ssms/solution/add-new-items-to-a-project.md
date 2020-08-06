---
title: Hinzufügen von neuen Elementen zu einem Projekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622328"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="22448-102">Hinzufügen neuer Elemente zu einem Projekt</span><span class="sxs-lookup"><span data-stu-id="22448-102">Add New Items to a Project</span></span>
  <span data-ttu-id="22448-103">Sie können neue Elemente zu einem Projekt hinzufügen, um die Funktionalität der Anwendung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="22448-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="22448-104">Bei einem neuen Element kann es sich um eine Abfrage oder eine Verbindung handeln.</span><span class="sxs-lookup"><span data-stu-id="22448-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="22448-105">hat zwei Projekttypen: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Skriptprojekt und Analysis Services-Skriptprojekt.</span><span class="sxs-lookup"><span data-stu-id="22448-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="22448-106">Der Projekttyp bestimmt die Elemente, die Sie zu einem Projekt hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="22448-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="22448-107">So können Sie beispielsweise eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfrage (eine Datei mit einer SQL-Erweiterung) zu einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Skriptprojekt hinzufügen, nicht jedoch zu einem Analysis Services-Skriptprojekt.</span><span class="sxs-lookup"><span data-stu-id="22448-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="22448-108">gestattet es Ihnen nicht, Ordner innerhalb von Projekten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="22448-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="22448-109">Um Ihre Arbeit zu organisieren, erstellen Sie mehrere Projekte innerhalb der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="22448-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="22448-110">So fügen Sie einem vorhandenen Projekt eine neue Abfrage hinzu</span><span class="sxs-lookup"><span data-stu-id="22448-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="22448-111">Wählen Sie im Projektmappen-Explorer ein Zielprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="22448-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="22448-112">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22448-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="22448-113">Wählen Sie im linken Bereich des Dialogfelds **Neues Element hinzufügen** eine Kategorie aus.</span><span class="sxs-lookup"><span data-stu-id="22448-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="22448-114">Wählen Sie im rechten Bereich eine Abfragevorlage aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22448-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="22448-115">Die neue Abfrage wird im Ordner **Abfragen** des Projekts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="22448-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="22448-116">Geben Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** eine Verbindung für die neue Abfrage an, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="22448-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="22448-117">Wenn Sie der neuen Abfrage keine Verbindung zuordnen möchten, klicken Sie in dem Verbindungsdialog auf **Abbrechen** .</span><span class="sxs-lookup"><span data-stu-id="22448-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="22448-118">Bei Bedarf können Sie die Abfrage im Projektmappen-Explorer umbenennen.</span><span class="sxs-lookup"><span data-stu-id="22448-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="22448-119">So fügen Sie einem vorhandenen Projekt eine neue Verbindung hinzu</span><span class="sxs-lookup"><span data-stu-id="22448-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="22448-120">Wählen Sie im Projektmappen-Explorer ein Zielprojekt aus.</span><span class="sxs-lookup"><span data-stu-id="22448-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="22448-121">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22448-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="22448-122">Wählen Sie im linken Bereich die Option **Verbindung** aus.</span><span class="sxs-lookup"><span data-stu-id="22448-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="22448-123">Wählen Sie im rechten Bereich die Option **Neue Verbindung** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22448-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="22448-124">Geben Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** eine Verbindung für die neue Abfrage an, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="22448-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="22448-125">Die neue Verbindung wird im Ordner **Verbindungen** des Projekts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="22448-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22448-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22448-126">See Also</span></span>  
 <span data-ttu-id="22448-127">[Projektmappen-Explorer](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="22448-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="22448-128">[Zuordnen von Dateierweiterungen zu einem Code-Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="22448-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="22448-129">[Hinzufügen vorhandener Elemente zu einem Projekt](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="22448-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="22448-130">Entfernen oder Löschen eines Elements oder Projekts</span><span class="sxs-lookup"><span data-stu-id="22448-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
