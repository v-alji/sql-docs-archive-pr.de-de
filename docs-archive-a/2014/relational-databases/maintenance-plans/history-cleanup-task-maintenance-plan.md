---
title: Task „Verlaufscleanup“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.historycleanup.f1
helpviewer_keywords:
- History Cleanup Task dialog box
ms.assetid: 66bb6c39-958c-4053-a27f-b1118d2567f5
ms.reviewer: ''
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 03ff35b14fc13d2b4446b15501114489b52c421e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620353"
---
# <a name="history-cleanup-task-maintenance-plan"></a><span data-ttu-id="d6027-102">Task 'Verlaufscleanup' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="d6027-102">History Cleanup Task (Maintenance Plan)</span></span>

  <span data-ttu-id="d6027-103">Mithilfe des Dialogfelds **Task 'Verlaufscleanup'** können Sie alte Verlaufsdaten aus Tabellen in der msdb-Datenbank entfernen.</span><span class="sxs-lookup"><span data-stu-id="d6027-103">Use the **History Cleanup Task** dialog to discard old historical information from tables in the msdb database.</span></span> <span data-ttu-id="d6027-104">Dieser Task unterstützt das Löschen des Sicherungs- und Wiederherstellungsverlaufs, des Auftragsverlaufs des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents und des Wartungsplanverlaufs.</span><span class="sxs-lookup"><span data-stu-id="d6027-104">This task supports deleting backup and restore history, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Job history, and maintenance plan history.</span></span>  
  
 <span data-ttu-id="d6027-105">Diese Anweisung verwendet die **sp_purge_jobhistory** - und **sp_delete_backuphistory** -Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d6027-105">This statement uses the **sp_purge_jobhistory** and **sp_delete_backuphistory** statements.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d6027-106">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="d6027-106">UI element list</span></span>  
 <span data-ttu-id="d6027-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="d6027-107">**Connection**</span></span>  
 <span data-ttu-id="d6027-108">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6027-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="d6027-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="d6027-109">**New**</span></span>  
 <span data-ttu-id="d6027-110">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6027-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="d6027-111">Das Dialogfeld **Neue Verbindung** wird an einer späteren Stelle in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d6027-111">The **New Connection** dialog box is described later in this topic.</span></span>  
  
 <span data-ttu-id="d6027-112">**Sicherungs- und Wiederherstellungsverlauf**</span><span class="sxs-lookup"><span data-stu-id="d6027-112">**Backup and restore history**</span></span>  
 <span data-ttu-id="d6027-113">Das Beibehalten von Datensätzen, in denen festgehalten ist, wann Sicherungen erstellt wurden, kann für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beim Erstellen eines Wiederherstellungsplans hilfreich sein, wenn Sie eine Datenbank wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d6027-113">Retaining records of when recent backups were created can help [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] create a recovery plan when you want to restore a database.</span></span> <span data-ttu-id="d6027-114">Die Beibehaltungsdauer muss mindestens dem Intervall entsprechen, in dem vollständige Datenbanksicherungen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d6027-114">The retention period should be at least the frequency of full database back ups.</span></span>  
  
 <span data-ttu-id="d6027-115">**Auftragsverlauf des SQL Server-Agents**</span><span class="sxs-lookup"><span data-stu-id="d6027-115">**SQL Server Agent Job history**</span></span>  
 <span data-ttu-id="d6027-116">Dieser Verlauf kann Ihnen bei der Problembehandlung fehlgeschlagener Aufträge bzw. der Ermittlung der Ursache von Datenbankaktionen helfen.</span><span class="sxs-lookup"><span data-stu-id="d6027-116">This history can help you troubleshoot failed jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="d6027-117">**Wartungsplanverlauf**</span><span class="sxs-lookup"><span data-stu-id="d6027-117">**Maintenance plan history**</span></span>  
 <span data-ttu-id="d6027-118">Dieser Verlauf kann Ihnen bei der Problembehandlung fehlgeschlagener Wartungsplanaufträge bzw. der Ermittlung der Ursache von Datenbankaktionen helfen.</span><span class="sxs-lookup"><span data-stu-id="d6027-118">This history can help you troubleshoot failed maintenance plan jobs, or determine why database actions occurred.</span></span>  
  
 <span data-ttu-id="d6027-119">**Verlaufsdaten entfernen, die älter sind als**</span><span class="sxs-lookup"><span data-stu-id="d6027-119">**Remove historical data older than**</span></span>  
 <span data-ttu-id="d6027-120">Geben Sie das Alter an, in dem Elemente gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d6027-120">Specify age of items that you want to delete.</span></span>  
  
 <span data-ttu-id="d6027-121">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="d6027-121">**View T-SQL**</span></span>  
 <span data-ttu-id="d6027-122">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6027-122">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6027-123">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="d6027-123">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="d6027-124">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="d6027-124">New Connection Dialog Box</span></span>  
 <span data-ttu-id="d6027-125">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="d6027-125">**Connection name**</span></span>  
 <span data-ttu-id="d6027-126">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="d6027-126">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="d6027-127">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="d6027-127">**Select or enter a server name**</span></span>  
 <span data-ttu-id="d6027-128">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d6027-128">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="d6027-129">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="d6027-129">**Refresh**</span></span>  
 <span data-ttu-id="d6027-130">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="d6027-130">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="d6027-131">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="d6027-131">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="d6027-132">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="d6027-132">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="d6027-133">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="d6027-133">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="d6027-134">Stellt mithilfe der Microsoft Windows-Authentifizierung eine Verbindung zu einer Instanz von SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="d6027-134">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="d6027-135">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="d6027-135">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="d6027-136">Stellt eine Verbindung zu einer Instanz von SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] mit der SQL Server-Authentifizierung her.</span><span class="sxs-lookup"><span data-stu-id="d6027-136">Connect to an instance of the SQL Server [!INCLUDE[ssDE](../../includes/ssde-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="d6027-137">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6027-137">This option is not available.</span></span>  
  
 <span data-ttu-id="d6027-138">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="d6027-138">**User name**</span></span>  
 <span data-ttu-id="d6027-139">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="d6027-139">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="d6027-140">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6027-140">This option is not available.</span></span>  
  
 <span data-ttu-id="d6027-141">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="d6027-141">**Password**</span></span>  
 <span data-ttu-id="d6027-142">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="d6027-142">Provide a password to use when authenticating.</span></span> <span data-ttu-id="d6027-143">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6027-143">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6027-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6027-144">See Also</span></span>  
 <span data-ttu-id="d6027-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d6027-145">[sp_purge_jobhistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-purge-jobhistory-transact-sql) </span></span>  
 [<span data-ttu-id="d6027-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d6027-146">sp_delete_backuphistory &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql)  
  
  
