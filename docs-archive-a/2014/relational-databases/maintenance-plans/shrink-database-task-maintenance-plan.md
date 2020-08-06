---
title: Task 'Datenbank verkleinern' (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.shrink.f1
- Shrink Database Task
- Shrink Database(s) Task
helpviewer_keywords:
- Shrink Database Task dialog box
ms.assetid: a9874cac-cded-4145-9c38-8aafd267dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8ee6060a4ee6ca3272434cf3d9115638a675e62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699536"
---
# <a name="shrink-database-task-maintenance-plan"></a><span data-ttu-id="c5733-102">Task 'Datenbank verkleinern' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="c5733-102">Shrink Database Task (Maintenance Plan)</span></span>
  <span data-ttu-id="c5733-103">Im Dialogfeld **Task 'Datenbank verkleinern'** erstellen Sie einen Task, mit dem versucht wird, die Größe der ausgewählten Datenbanken zu verkleinern.</span><span class="sxs-lookup"><span data-stu-id="c5733-103">Use the **Shrink Database Task** dialog to create a task that attempts to reduce the size of the selected databases.</span></span> <span data-ttu-id="c5733-104">Legen Sie mithilfe der folgenden Optionen die Menge des nicht verwendeten Speicherplatzes fest, der in der Datenbank zur Verfügung stehen soll, nachdem diese verkleinert wurde (je höher der Prozentsatz, desto geringer der Spielraum für die Verkleinerung der Datenbank).</span><span class="sxs-lookup"><span data-stu-id="c5733-104">Use the options below to determine the amount of unused space to remain in the database after the database is shrunk (the larger the percentage, the less the database can shrink).</span></span> <span data-ttu-id="c5733-105">Der Wert basiert auf dem Prozentsatz der tatsächlichen Daten in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c5733-105">The value is based on the percentage of the actual data in the database.</span></span> <span data-ttu-id="c5733-106">So würde z. B. eine 100-MB-Datenbank mit 60 MB Daten und 40 MB freiem Speicherplatz und einem Prozentsatz von 50 für den freien Speicherplatz zu folgendem Ergebnis führen: 60 MB Daten und 30 MB freier Speicherplatz (da 50 % von 60 MB einen Wert von 30 MB ergibt).</span><span class="sxs-lookup"><span data-stu-id="c5733-106">For example, a 100-MB database containing 60 MB of data and 40 MB of free space, with a free space percentage of 50 percent, would result in 60 MB of data and 30 MB of free space (because 50 percent of 60 MB is 30 MB).</span></span> <span data-ttu-id="c5733-107">Es wird lediglich überschüssiger Speicherplatz aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="c5733-107">Only excess space in the database is eliminated.</span></span> <span data-ttu-id="c5733-108">Die gültigen Werte sind 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="c5733-108">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="c5733-109">Mit dem Verkleinern von Datendateien wird Platz gewonnen, indem Datenseiten vom Ende der Datei an nicht belegten Platz weiter am Dateianfang verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-109">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="c5733-110">Wurde am Ende der Datei ausreichend Platz geschaffen, kann die Zuordnung der Datenseiten am Ende der Datei aufgehoben und die Datenseiten können ins Dateisystem zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-110">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="c5733-111">Die zum Verkleinern einer Datei verschobenen Daten können an beliebigen freien Platz in der Datei verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-111">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="c5733-112">Dies führt zur Indexfragmentierung und kann die Leistung von Abfragen, die einen Bereich des Indexes suchen, verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="c5733-112">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="c5733-113">Zur Vermeidung von Fragmentierung sollten die Dateiindizes nach der Verkleinerung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-113">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
 <span data-ttu-id="c5733-114">Dieser Task führt die DBCC SHRINKDATABASE-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="c5733-114">This task executes the DBCC SHRINKDATABASE statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c5733-115">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c5733-115">Options</span></span>  
 <span data-ttu-id="c5733-116">**Connection**</span><span class="sxs-lookup"><span data-stu-id="c5733-116">**Connection**</span></span>  
 <span data-ttu-id="c5733-117">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5733-117">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="c5733-118">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c5733-118">**New**</span></span>  
 <span data-ttu-id="c5733-119">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5733-119">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="c5733-120">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5733-120">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="c5733-121">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="c5733-121">**Databases**</span></span>  
 <span data-ttu-id="c5733-122">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c5733-122">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="c5733-123">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="c5733-123">**All databases**</span></span>  
  
     <span data-ttu-id="c5733-124">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-124">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="c5733-125">**Alle Systemdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="c5733-125">**All system databases**</span></span>  
  
     <span data-ttu-id="c5733-126">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-126">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="c5733-127">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-127">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="c5733-128">**Alle Benutzerdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="c5733-128">**All user databases**</span></span>  
  
     <span data-ttu-id="c5733-129">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-129">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="c5733-130">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-130">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="c5733-131">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="c5733-131">**These databases**</span></span>  
  
     <span data-ttu-id="c5733-132">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-132">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="c5733-133">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-133">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5733-134">Wartungspläne werden nur für Datenbanken mit Kompatibilitätsgrad 80 oder höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5733-134">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="c5733-135">Datenbanken mit Kompatibilitätsgrad 70 oder niedriger werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5733-135">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="c5733-136">**Datenbank verkleinern, wenn sie folgende Größe überschreitet**</span><span class="sxs-lookup"><span data-stu-id="c5733-136">**Shrink database when it grows beyond**</span></span>  
 <span data-ttu-id="c5733-137">Gibt die Größe in Megabytes an, die zur Ausführung des Tasks führt.</span><span class="sxs-lookup"><span data-stu-id="c5733-137">Specify the size in megabytes that causes the task to execute.</span></span>  
  
 <span data-ttu-id="c5733-138">**Menge des freien Speicherplatzes nach dem Verkleinern**</span><span class="sxs-lookup"><span data-stu-id="c5733-138">**Amount of free space to remain after shrink**</span></span>  
 <span data-ttu-id="c5733-139">Beendet das Verkleinern, wenn der freie Speicherplatz in der Datenbankdatei diesen Wert erreicht.</span><span class="sxs-lookup"><span data-stu-id="c5733-139">Stop shrinking when free space in database files reaches this size.</span></span>  
  
 <span data-ttu-id="c5733-140">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="c5733-140">**View T-SQL**</span></span>  
 <span data-ttu-id="c5733-141">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c5733-141">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5733-142">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="c5733-142">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="c5733-143">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="c5733-143">New Connection Dialog Box</span></span>  
 <span data-ttu-id="c5733-144">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="c5733-144">**Connection name**</span></span>  
 <span data-ttu-id="c5733-145">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="c5733-145">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="c5733-146">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="c5733-146">**Select or enter a server name**</span></span>  
 <span data-ttu-id="c5733-147">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5733-147">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="c5733-148">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="c5733-148">**Refresh**</span></span>  
 <span data-ttu-id="c5733-149">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="c5733-149">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="c5733-150">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="c5733-150">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="c5733-151">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="c5733-151">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="c5733-152">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="c5733-152">**Use Windows NT Integrated security**</span></span>  
 <span data-ttu-id="c5733-153">Stellt mithilfe der [!INCLUDE[msCoName](../../includes/msconame-md.md)]-Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="c5733-153">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="c5733-154">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="c5733-154">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="c5733-155">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="c5733-155">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="c5733-156">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5733-156">This option is not available.</span></span>  
  
 <span data-ttu-id="c5733-157">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="c5733-157">**User name**</span></span>  
 <span data-ttu-id="c5733-158">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="c5733-158">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="c5733-159">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5733-159">This option is not available.</span></span>  
  
 <span data-ttu-id="c5733-160">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="c5733-160">**Password**</span></span>  
 <span data-ttu-id="c5733-161">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="c5733-161">Provide a password to use when authenticating.</span></span> <span data-ttu-id="c5733-162">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5733-162">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5733-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5733-163">See Also</span></span>  
 [<span data-ttu-id="c5733-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5733-164">DBCC SHRINKDATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql)  
  
  
