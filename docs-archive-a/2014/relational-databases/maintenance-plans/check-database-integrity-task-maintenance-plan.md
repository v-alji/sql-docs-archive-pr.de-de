---
title: Task „Datenbankintegrität überprüfen“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.integrity.f1
- sql12.swb.maint.integrity.f1
helpviewer_keywords:
- Check Database Integrity Task dialog box
ms.assetid: 3534494a-5dfe-4738-b49a-e7fabd731c47
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f786755a3b7ed5d991b4cf0e32c067e355c111ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620361"
---
# <a name="check-database-integrity-task-maintenance-plan"></a><span data-ttu-id="6e8d3-102">Task 'Datenbankintegrität überprüfen' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="6e8d3-102">Check Database Integrity Task (Maintenance Plan)</span></span>
  <span data-ttu-id="6e8d3-103">Verwenden Sie das Dialogfeld **Task „Datenbankintegrität überprüfen“** , um die Zuordnung und die strukturelle Integrität von Benutzer- und Systemtabellen sowie Indizes in der Datenbank zu überprüfen, indem Sie die `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-103">Use the **Check Database Integrity Task** dialog to check the allocation and structural integrity of user and system tables, and indexes in the database, by running the `DBCC CHECKDB`[!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="6e8d3-104">Durch die Ausführung von `DBCC` wird sichergestellt, dass etwaige Integritätsprobleme in der Datenbank gemeldet werden und später vom Systemadministrator oder Datenbankbesitzer behoben werden können.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-104">Running `DBCC` ensures that any integrity problems with the database are reported, thereby allowing them to be addressed later by a system administrator or database owner.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6e8d3-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6e8d3-105">Options</span></span>  
 <span data-ttu-id="6e8d3-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-106">**Connection**</span></span>  
 <span data-ttu-id="6e8d3-107">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="6e8d3-108">**Neu**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-108">**New**</span></span>  
 <span data-ttu-id="6e8d3-109">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="6e8d3-110">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="6e8d3-111">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-111">**Databases**</span></span>  
 <span data-ttu-id="6e8d3-112">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="6e8d3-113">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-113">**All databases**</span></span>  
  
     <span data-ttu-id="6e8d3-114">Generieren Sie einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbanken außer **tempdb** ausführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except **tempdb**.</span></span>  
  
-   <span data-ttu-id="6e8d3-115">**Alle Systemdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-115">**All system databases**</span></span>  
  
     <span data-ttu-id="6e8d3-116">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken außer **tempdb**ausführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="6e8d3-117">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="6e8d3-118">**Alle Benutzerdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-118">**All user databases**</span></span>  
  
     <span data-ttu-id="6e8d3-119">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="6e8d3-120">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="6e8d3-121">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="6e8d3-122">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="6e8d3-123">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6e8d3-124">Wartungspläne werden nur für Datenbanken mit Kompatibilitätsgrad 80 oder höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-124">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="6e8d3-125">Datenbanken mit Kompatibilitätsgrad 70 oder niedriger werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-125">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="6e8d3-126">**Indizes einschließen**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-126">**Include indexes**</span></span>  
 <span data-ttu-id="6e8d3-127">Überprüft die Integrität aller Indexseiten und der Tabellendatenseiten.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-127">Check the integrity of all the index pages as well as the table data pages.</span></span>  
  
 <span data-ttu-id="6e8d3-128">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-128">**View T-SQL**</span></span>  
 <span data-ttu-id="6e8d3-129">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-129">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6e8d3-130">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-130">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="6e8d3-131">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="6e8d3-131">New Connection Dialog Box</span></span>  
 <span data-ttu-id="6e8d3-132">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-132">**Connection name**</span></span>  
 <span data-ttu-id="6e8d3-133">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-133">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="6e8d3-134">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-134">**Select or enter a server name**</span></span>  
 <span data-ttu-id="6e8d3-135">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-135">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="6e8d3-136">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-136">**Refresh**</span></span>  
 <span data-ttu-id="6e8d3-137">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-137">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="6e8d3-138">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-138">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="6e8d3-139">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-139">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="6e8d3-140">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-140">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="6e8d3-141">Stellt mithilfe der Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-141">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="6e8d3-142">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-142">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="6e8d3-143">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-143">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="6e8d3-144">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-144">This option is not available.</span></span>  
  
 <span data-ttu-id="6e8d3-145">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-145">**User name**</span></span>  
 <span data-ttu-id="6e8d3-146">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-146">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="6e8d3-147">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-147">This option is not available.</span></span>  
  
 <span data-ttu-id="6e8d3-148">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="6e8d3-148">**Password**</span></span>  
 <span data-ttu-id="6e8d3-149">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-149">Provide a password to use when authenticating.</span></span> <span data-ttu-id="6e8d3-150">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6e8d3-150">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8d3-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e8d3-151">See Also</span></span>  
 [<span data-ttu-id="6e8d3-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6e8d3-152">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
