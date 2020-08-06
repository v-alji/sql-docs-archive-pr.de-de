---
title: Speichern von Skripts als Projekte oder Projektmappen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717131"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="ddda0-102">Speichern von Skripts als Projekte oder Lösungen</span><span class="sxs-lookup"><span data-stu-id="ddda0-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="ddda0-103">Entwickler, die mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio vertraut sind, werden die Einführung des Projektmappen-Explorers in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]begrüßen.</span><span class="sxs-lookup"><span data-stu-id="ddda0-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ddda0-104">Die Skripts, die Ihre Geschäftsaktivitäten unterstützen, können in Skriptprojekten zusammengestellt werden, und die Skriptprojekte können zusammen als Projektmappe verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ddda0-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="ddda0-105">Wenn Skripts in Skriptprojekten und Projektmappen verwaltet werden, können sie zusammen als Gruppe geöffnet werden. Sie können aber auch gemeinsam in einem Quellcodeverwaltungsprogramm wie Visual SourceSafe gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ddda0-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="ddda0-106">Skriptprojekte umfassen die Verbindungsinformationen für die Skripts, sodass diese ordnungsgemäß ausgeführt werden. Sie können auch andere Dateien enthalten, wie z. B. eine unterstützende Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ddda0-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="ddda0-107">In der folgenden Übung erstellen Sie ein kurzes Skript, mit dem die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank abgefragt wird und das in einem Skriptprojekt und einer Projektmappe gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ddda0-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="ddda0-108">Verwenden von Skriptprojekten und Projektmappen</span><span class="sxs-lookup"><span data-stu-id="ddda0-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="ddda0-109">So erstellen Sie ein Skriptprojekt und eine Projektmappe</span><span class="sxs-lookup"><span data-stu-id="ddda0-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="ddda0-110">Öffnen Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], und stellen Sie eine Verbindung mit einem Server her, auf dem Objekt-Explorer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ddda0-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ddda0-111">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="ddda0-112">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddda0-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ddda0-113">Geben Sie im Textfeld **Name** den Namen **StatusCheck**ein, klicken Sie unter **Vorlagen** auf **SQL Server-Skripts**, und klicken Sie dann auf **OK** , um eine neue Projektmappe und ein neues Skriptprojekt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ddda0-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="ddda0-114">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Verbindungen**, und klicken Sie anschließend auf **Neue Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="ddda0-115">Das Dialogfeld **Verbindung mit Server herstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ddda0-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="ddda0-116">Geben Sie im Listenfeld **Servername** den Namen Ihres Servers ein.</span><span class="sxs-lookup"><span data-stu-id="ddda0-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="ddda0-117">Klicken Sie auf **Optionen**, und klicken Sie dann auf die Registerkarte **Verbindungseigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="ddda0-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="ddda0-118">Wählen Sie im Dialogfeld **Verbindung mit Datenbank herstellen** die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank aus, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="ddda0-119">Dem Projekt werden die Verbindungsinformationen einschließlich der Datenbank hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ddda0-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="ddda0-120">Wenn das Eigenschaftenfenster nicht angezeigt wird, klicken Sie im Projektmappen-Explorer auf die neue Verbindung und drücken dann F4.</span><span class="sxs-lookup"><span data-stu-id="ddda0-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="ddda0-121">Daraufhin werden die Verbindungseigenschaften angezeigt, in denen als **Ausgangsdatenbank** die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Datenbank enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ddda0-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="ddda0-122">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf die Verbindung, und klicken Sie anschließend auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="ddda0-123">Eine neue Abfrage mit der Bezeichnung **SQLQuery1.sql** wird erstellt, für die eine Verbindung mit der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank auf Ihrem Server hergestellt wird und die Ihrem Skriptprojekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ddda0-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="ddda0-124">Geben Sie im Abfrage-Editor die folgende Abfrage ein, um festzustellen, bei wie vielen Aufträgen die Fälligkeitstermine vor den Startterminen der Aufträge liegen.</span><span class="sxs-lookup"><span data-stu-id="ddda0-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="ddda0-125">(Sie können den Code im Fenster des Lernprogramms kopieren und dann einfügen.)</span><span class="sxs-lookup"><span data-stu-id="ddda0-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddda0-126">Wenn Sie zum Eingeben der Abfrage mehr Platz brauchen, drücken Sie UMSCHALT+ALT+EINGABE, um in den Vollbildmodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ddda0-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="ddda0-127">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **SQLQuery1**und anschließend auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="ddda0-128">Geben Sie als neuen Namen für die Abfrage **Check Workorders. SQL** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="ddda0-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="ddda0-129">Zum Speichern Ihrer Projektmappe und Ihres Skriptprojekts klicken Sie im Menü **Datei** auf **Alles speichern**.</span><span class="sxs-lookup"><span data-stu-id="ddda0-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ddda0-130">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ddda0-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ddda0-131">Zusammenfassung: Projektmappen und Skriptprojekte</span><span class="sxs-lookup"><span data-stu-id="ddda0-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  
