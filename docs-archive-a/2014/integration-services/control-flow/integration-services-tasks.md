---
title: Integration Services-Tasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- scripts [Integration Services], tasks
- files [Integration Services], task options
- workflow tasks [Integration Services]
- Integration Services, tasks
- adding package tasks
- tasks [Integration Services], listed
- SSIS tasks
- SSIS, tasks
- control flow [Integration Services], tasks
- tasks [Integration Services]
- grouping tasks
- tasks [Integration Services], about tasks
- SQL Server Integration Services tasks
- data preparation tasks [Integration Services]
- directory operations [Integration Services]
ms.assetid: 75c8901d-6966-4af3-abe5-10af6dd9313b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5fa58dec1e05a0333c295efc7f00a1d6df935792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616624"
---
# <a name="integration-services-tasks"></a><span data-ttu-id="5c3b5-102">Integration Services-Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-102">Integration Services Tasks</span></span>
  <span data-ttu-id="5c3b5-103">Tasks sind Ablaufsteuerungselemente, mit denen Arbeitseinheiten definiert werden, die in einer Paketablaufsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-103">Tasks are control flow elements that define units of work that are performed in a package control flow.</span></span> <span data-ttu-id="5c3b5-104">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket besteht aus mindestens einem Task.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-104">An [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package is made up of one or more tasks.</span></span> <span data-ttu-id="5c3b5-105">Enthält das Paket mehrere Tasks, werden sie in der Ablaufsteuerung durch Rangfolgeneinschränkungen miteinander verbunden und angeordnet.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-105">If the package contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span>  
  
 <span data-ttu-id="5c3b5-106">Mit einer Programmiersprache, die COM unterstützt, wie z. B. Visual Basic, oder einer .NET-Programmiersprache, wie z. B. C#, können Sie auch benutzerdefinierte Tasks erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-106">You can also write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span>  
  
 <span data-ttu-id="5c3b5-107">Der [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer ist das grafische Tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] für das Arbeiten mit Paketen. Er stellt die Entwurfsoberfläche zum Erstellen von Paketablaufsteuerungen und benutzerdefinierte Editoren zum Konfigurieren von Tasks bereit.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the graphical tool in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] for working with packages, provides the design surface for creating package control flow, and provides custom editors for configuring tasks.</span></span> <span data-ttu-id="5c3b5-108">Darüber hinaus können Sie das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Objektmodell so programmieren, dass Pakete programmgesteuert erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-108">You can also program the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] object model to create packages programmatically.</span></span>  
  
## <a name="types-of-tasks"></a><span data-ttu-id="5c3b5-109">Tasktypen</span><span class="sxs-lookup"><span data-stu-id="5c3b5-109">Types of Tasks</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="5c3b5-110">schließt die folgenden Arten von Tasks ein.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-110">includes the following types of tasks.</span></span>  
  
 <span data-ttu-id="5c3b5-111">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="5c3b5-111">Data Flow Task</span></span>  
 <span data-ttu-id="5c3b5-112">Dieser Task führt Datenflüsse aus, um Daten zu extrahieren, Transformationen auf Spaltenebene anzuwenden und Daten zu laden.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-112">The task that runs data flows to extract data, apply column level transformations, and load data.</span></span>  
  
 <span data-ttu-id="5c3b5-113">Datenvorbereitungstasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-113">Data Preparation Tasks</span></span>  
 <span data-ttu-id="5c3b5-114">Mit diesen Tasks werden folgende Prozesse ausgeführt: Kopieren von Dateien und Verzeichnissen, Herunterladen von Dateien und Daten, Ausführen von Webmethoden, Übernehmen von Vorgängen für XML-Dokumente und Datenprofilerstellung zum Reinigen.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-114">These tasks do the following processes: copy files and directories; download files and data; run Web methods; apply operations to XML documents; and profile data for cleansing.</span></span>  
  
 <span data-ttu-id="5c3b5-115">Workflowtasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-115">Workflow Tasks</span></span>  
 <span data-ttu-id="5c3b5-116">Diese Tasks kommunizieren mit anderen Prozessen, um Pakete, Programme oder Batchdateien auszuführen, Nachrichten zwischen Paketen zu senden und zu empfangen, E-Mail-Nachrichten zu senden, WMI-Daten (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation) zu lesen und WMI-Ereignisse zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-116">The tasks that communicate with other processes to run packages, run programs or batch files, send and receive messages between packages, send e-mail messages, read Windows Management Instrumentation (WMI) data, and watch for WMI events.</span></span>  
  
 <span data-ttu-id="5c3b5-117">SQL Server-Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-117">SQL Server Tasks</span></span>  
 <span data-ttu-id="5c3b5-118">Mit diesen Tasks werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Objekte und -Daten geöffnet, kopiert, eingefügt, gelöscht und geändert.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-118">The tasks that access, copy, insert, delete, and modify [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects and data.</span></span>  
  
 <span data-ttu-id="5c3b5-119">Skripttasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-119">Scripting Tasks</span></span>  
 <span data-ttu-id="5c3b5-120">Diese Tasks erweitern die Paketfunktionalität mithilfe von Skripts.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-120">The tasks that extend package functionality by using scripts.</span></span>  
  
 <span data-ttu-id="5c3b5-121">Analysis Services-Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-121">Analysis Services Tasks</span></span>  
 <span data-ttu-id="5c3b5-122">Mit diesen Tasks werden [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Objekte erstellt, geändert, gelöscht und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-122">The tasks that create, modify, delete, and process [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="5c3b5-123">Wartungstasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-123">Maintenance Tasks</span></span>  
 <span data-ttu-id="5c3b5-124">Mit diesen Tasks werden administrative Funktionen ausgeführt, wie z. B. das Sichern und Verkleinern von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken, das erneute Erstellen und Organisieren von Indizes sowie das Ausführen von Aufträgen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-124">The tasks that perform administrative functions such as backing up and shrinking [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, rebuilding and reorganizing indexes, and running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs.</span></span>  
  
 <span data-ttu-id="5c3b5-125">Benutzerdefinierte Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-125">Custom Tasks</span></span>  
 <span data-ttu-id="5c3b5-126">Mit einer Programmiersprache, die COM unterstützt, wie z. B. Visual Basic, oder einer .NET-Programmiersprache, wie z. B. C#, können Sie außerdem benutzerdefinierte Tasks erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-126">Additionally, you can write custom tasks using a programming language that supports COM, such as Visual Basic, or a .NET programming language, such as C#.</span></span> <span data-ttu-id="5c3b5-127">Wenn Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer auf benutzerdefinierte Tasks zugreifen möchten, können Sie dafür eine Benutzeroberfläche erstellen und registrieren.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-127">If you want to access your custom task in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, you can create and register a user interface for the task.</span></span> <span data-ttu-id="5c3b5-128">Weitere Informationen finden Sie unter [Entwickeln eines benutzerdefinierten Tasks](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-128">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="configuration-of-tasks"></a><span data-ttu-id="5c3b5-129">Konfiguration von Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-129">Configuration of Tasks</span></span>  
 <span data-ttu-id="5c3b5-130">Ein Paket von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] kann einen einzelnen Task enthalten, wie z. B. einen Task SQL ausführen, der Datensätze in einer Datenbanktabelle löscht, wenn das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-130">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can contain a single task, such as an Execute SQL task that deletes records in a database table when the package runs.</span></span> <span data-ttu-id="5c3b5-131">Pakete enthalten jedoch normalerweise mehrere Tasks, und für jeden Task ist festgelegt, dass er im Kontext der Paketablaufsteuerung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-131">However, packages typically contain several tasks, and each task is set to run within the context of the package control flow.</span></span> <span data-ttu-id="5c3b5-132">Für Ereignishandler, bei denen es sich um Workflows handelt, die als Antwort auf Laufzeitereignisse ausgeführt werden, sind ebenfalls Tasks möglich.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-132">Event handlers, which are workflows that run in response to run-time events, can also have tasks.</span></span>  
  
 <span data-ttu-id="5c3b5-133">Weitere Informationen zum Hinzufügen eines Tasks zu einem Paket mit [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer finden Sie unter [Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-133">For more information about adding a task to a package using [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add or Delete a Task or a Container in a Control Flow](add-or-delete-a-task-or-a-container-in-a-control-flow.md).</span></span>  
  
 <span data-ttu-id="5c3b5-134">Weitere Informationen zum programmgesteuerten Hinzufügen eines Tasks zu einem Paket finden Sie unter [Programmgesteuertes Hinzufügen von Tasks](../building-packages-programmatically/adding-tasks-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-134">For more information about adding a task to a package programmatically, see [Adding Tasks Programmatically](../building-packages-programmatically/adding-tasks-programmatically.md).</span></span>  
  
 <span data-ttu-id="5c3b5-135">Jeder Task kann einzeln mithilfe der benutzerdefinierten Dialogfelder für die verschiedenen Tasks des [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designers konfiguriert werden oder mithilfe des Eigenschaftenfensters von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c3b5-135">Each task can be configured individually using the custom dialog boxes for each task that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides, or the Properties window included in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="5c3b5-136">In einem Paket können mehrere Tasks desselben Typs vorhanden sein, z.B. sechs Tasks vom Typ SQL ausführen, wobei jeder Task unterschiedlich konfiguriert sein kann.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-136">A package can include multiple tasks of the same type-for example, six Execute SQL tasks-and each task can be configured differently.</span></span> <span data-ttu-id="5c3b5-137">Weitere Informationen finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-137">For more information, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="tasks-connections-and-groups"></a><span data-ttu-id="5c3b5-138">Tasks "Verbindungen" und "Gruppen"</span><span class="sxs-lookup"><span data-stu-id="5c3b5-138">Tasks Connections and Groups</span></span>  
 <span data-ttu-id="5c3b5-139">Wenn mehrere Tasks vorhanden sind, werden sie in der Ablaufsteuerung durch Rangfolgeneinschränkungen miteinander verbunden und angeordnet.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-139">If the task contains more than one task, they are connected and sequenced in the control flow by precedence constraints.</span></span> <span data-ttu-id="5c3b5-140">Weitere Informationen finden Sie unter [Rangfolgeneinschränkungen](precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-140">For more information, see [Precedence Constraints](precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="5c3b5-141">Tasks können gruppiert und als eine einzelne Arbeitseinheit ausgeführt oder in einer Schleife wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="5c3b5-141">Tasks can be grouped together and performed as a single unit of work, or repeated in a loop.</span></span> <span data-ttu-id="5c3b5-142">Weitere Informationen finden Sie unter [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md)und [Sequence Container](sequence-container.md).</span><span class="sxs-lookup"><span data-stu-id="5c3b5-142">For more information, see [Foreach Loop Container](foreach-loop-container.md), [For Loop Container](for-loop-container.md), and [Sequence Container](sequence-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5c3b5-143">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5c3b5-143">Related Tasks</span></span>  
 [<span data-ttu-id="5c3b5-144">Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="5c3b5-144">Add or Delete a Task or a Container in a Control Flow</span></span>](add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
  
