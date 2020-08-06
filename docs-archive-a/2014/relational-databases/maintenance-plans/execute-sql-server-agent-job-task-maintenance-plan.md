---
title: Task „Auftrag des SQL Server-Agents ausführen“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620354"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a><span data-ttu-id="0dacf-102">Task 'Auftrag des SQL Server-Agents ausführen' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="0dacf-102">Execute SQL Server Agent Job Task (Maintenance Plan)</span></span>
  <span data-ttu-id="0dacf-103">Verwenden Sie das Dialogfeld **Task 'Auftrag des SQL Server-Agents ausführen'** , um Aufträge des Microsoft SQL Server-Agents innerhalb eines Wartungsplans auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0dacf-103">Use the **Execute SQL Server Agent Job Task** dialog to execute Microsoft SQL Server Agent jobs within a maintenance plan.</span></span> <span data-ttu-id="0dacf-104">Diese Option ist nicht verfügbar, wenn für die ausgewählte Verbindung keine Aufträge des SQL Server-Agents vorliegen.</span><span class="sxs-lookup"><span data-stu-id="0dacf-104">This option will not be available if you have no SQL Server Agent jobs on the selected connection.</span></span>  
  
 <span data-ttu-id="0dacf-105">Dieser Task verwendet die Anweisung **.sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="0dacf-105">This task uses the **.sp_start_job** statement.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="0dacf-106">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="0dacf-106">UI element list</span></span>  
 <span data-ttu-id="0dacf-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="0dacf-107">**Connection**</span></span>  
 <span data-ttu-id="0dacf-108">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0dacf-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="0dacf-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="0dacf-109">**New**</span></span>  
 <span data-ttu-id="0dacf-110">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0dacf-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="0dacf-111">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0dacf-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="0dacf-112">**Verfügbare Aufträge des SQL Server-Agents**</span><span class="sxs-lookup"><span data-stu-id="0dacf-112">**Available SQL Agent jobs**</span></span>  
 <span data-ttu-id="0dacf-113">Wählen Sie den auszuführenden Auftrag aus.</span><span class="sxs-lookup"><span data-stu-id="0dacf-113">Select the job to execute.</span></span> <span data-ttu-id="0dacf-114">Im Raster werden **Auftragsname** und **Beschreibung** angezeigt, um die Aufträge zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0dacf-114">The grid provides the **Job name** and **Description** to identify the jobs.</span></span>  
  
 <span data-ttu-id="0dacf-115">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="0dacf-115">**View T-SQL**</span></span>  
 <span data-ttu-id="0dacf-116">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0dacf-116">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0dacf-117">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="0dacf-117">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="0dacf-118">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="0dacf-118">New Connection Dialog Box</span></span>  
 <span data-ttu-id="0dacf-119">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="0dacf-119">**Connection name**</span></span>  
 <span data-ttu-id="0dacf-120">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="0dacf-120">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="0dacf-121">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="0dacf-121">**Select or enter a server name**</span></span>  
 <span data-ttu-id="0dacf-122">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0dacf-122">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="0dacf-123">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="0dacf-123">**Refresh**</span></span>  
 <span data-ttu-id="0dacf-124">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="0dacf-124">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="0dacf-125">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="0dacf-125">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="0dacf-126">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="0dacf-126">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="0dacf-127">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="0dacf-127">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="0dacf-128">Stellt mithilfe der Microsoft Windows-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="0dacf-128">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="0dacf-129">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="0dacf-129">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="0dacf-130">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="0dacf-130">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="0dacf-131">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0dacf-131">This option is not available.</span></span>  
  
 <span data-ttu-id="0dacf-132">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="0dacf-132">**User name**</span></span>  
 <span data-ttu-id="0dacf-133">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="0dacf-133">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="0dacf-134">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0dacf-134">This option is not available.</span></span>  
  
 <span data-ttu-id="0dacf-135">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="0dacf-135">**Password**</span></span>  
 <span data-ttu-id="0dacf-136">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="0dacf-136">Provide a password to use when authenticating.</span></span> <span data-ttu-id="0dacf-137">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0dacf-137">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dacf-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dacf-138">See Also</span></span>  
 <span data-ttu-id="0dacf-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0dacf-139">[sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql) </span></span>  
 <span data-ttu-id="0dacf-140">[Erstellen eines Auftrags](../../ssms/agent/create-a-job.md) </span><span class="sxs-lookup"><span data-stu-id="0dacf-140">[Create a Job](../../ssms/agent/create-a-job.md) </span></span>  
 [<span data-ttu-id="0dacf-141">sp_start_job &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0dacf-141">sp_start_job &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
