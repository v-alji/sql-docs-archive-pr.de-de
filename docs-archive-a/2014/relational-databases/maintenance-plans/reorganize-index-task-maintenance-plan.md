---
title: Task „Index neu organisieren“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.defrag.f1
helpviewer_keywords:
- Reorganize Index Task dialog box
ms.assetid: e9cbebbd-f36f-4176-9832-382a46ac946c
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bbb154045b781f8a92dfce9c9d2f6ee2d819c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616516"
---
# <a name="reorganize-index-task-maintenance-plan"></a><span data-ttu-id="76e02-102">Task 'Index neu organisieren' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="76e02-102">Reorganize Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="76e02-103">Verschieben Sie mithilfe des Dialogfelds **Task 'Index neu organisieren'** Indexseiten, sodass eine effizientere Suchreihenfolge entsteht.</span><span class="sxs-lookup"><span data-stu-id="76e02-103">Use the **ReorganizeIndex Task** dialog to move index pages into a more efficient search order.</span></span> <span data-ttu-id="76e02-104">Dieser Task verwendet die `ALTER INDEX REORGANIZE` -Anweisung mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="76e02-104">This task uses the `ALTER INDEX REORGANIZE` statement with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] databases.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76e02-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="76e02-105">Options</span></span>  
 <span data-ttu-id="76e02-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="76e02-106">**Connection**</span></span>  
 <span data-ttu-id="76e02-107">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76e02-107">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="76e02-108">**Neu**</span><span class="sxs-lookup"><span data-stu-id="76e02-108">**New**</span></span>  
 <span data-ttu-id="76e02-109">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="76e02-109">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="76e02-110">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76e02-110">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="76e02-111">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="76e02-111">**Databases**</span></span>  
 <span data-ttu-id="76e02-112">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="76e02-112">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="76e02-113">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="76e02-113">**All databases**</span></span>  
  
     <span data-ttu-id="76e02-114">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-114">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="76e02-115">**Alle Systemdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="76e02-115">**All system databases**</span></span>  
  
     <span data-ttu-id="76e02-116">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken außer **tempdb**ausführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-116">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except **tempdb**.</span></span> <span data-ttu-id="76e02-117">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-117">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="76e02-118">**Alle Benutzerdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="76e02-118">**All user databases**</span></span>  
  
     <span data-ttu-id="76e02-119">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-119">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="76e02-120">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-120">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="76e02-121">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="76e02-121">**These specific databases**</span></span>  
  
     <span data-ttu-id="76e02-122">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="76e02-122">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="76e02-123">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="76e02-123">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="76e02-124">**Object**</span><span class="sxs-lookup"><span data-stu-id="76e02-124">**Object**</span></span>  
 <span data-ttu-id="76e02-125">Begrenzt das Raster **Auswahl** auf die Anzeige von Tabellen, Sichten oder beides.</span><span class="sxs-lookup"><span data-stu-id="76e02-125">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="76e02-126">**Auswahl**</span><span class="sxs-lookup"><span data-stu-id="76e02-126">**Selection**</span></span>  
 <span data-ttu-id="76e02-127">Gibt die Tabellen oder Indizes an, auf die sich dieser Task auswirkt.</span><span class="sxs-lookup"><span data-stu-id="76e02-127">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="76e02-128">Nicht verfügbar, wenn im Feld **Objekt** der Eintrag **Tabellen und Sichten** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="76e02-128">Not available when **Tables and Views** is selected in the **Object** box.</span></span>  
  
 <span data-ttu-id="76e02-129">**Große Objekte komprimieren**</span><span class="sxs-lookup"><span data-stu-id="76e02-129">**Compact large objects**</span></span>  
 <span data-ttu-id="76e02-130">Hebt die Speicherplatzzuordnung für Tabellen und Sichten nach Möglichkeit auf.</span><span class="sxs-lookup"><span data-stu-id="76e02-130">Deallocate space for tables and views when possible.</span></span> <span data-ttu-id="76e02-131">Diese Option verwendet `ALTER INDEX LOB_COMPACTION = ON`.</span><span class="sxs-lookup"><span data-stu-id="76e02-131">This option uses `ALTER INDEX LOB_COMPACTION = ON`.</span></span>  
  
 <span data-ttu-id="76e02-132">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="76e02-132">**View T-SQL**</span></span>  
 <span data-ttu-id="76e02-133">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76e02-133">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76e02-134">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="76e02-134">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="76e02-135">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="76e02-135">New Connection Dialog Box</span></span>  
 <span data-ttu-id="76e02-136">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="76e02-136">**Connection name**</span></span>  
 <span data-ttu-id="76e02-137">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="76e02-137">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="76e02-138">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="76e02-138">**Select or enter a server name**</span></span>  
 <span data-ttu-id="76e02-139">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="76e02-139">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="76e02-140">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="76e02-140">**Refresh**</span></span>  
 <span data-ttu-id="76e02-141">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="76e02-141">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="76e02-142">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="76e02-142">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="76e02-143">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="76e02-143">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="76e02-144">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="76e02-144">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="76e02-145">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="76e02-145">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="76e02-146">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="76e02-146">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="76e02-147">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="76e02-147">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="76e02-148">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="76e02-148">This option is not available.</span></span>  
  
 <span data-ttu-id="76e02-149">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="76e02-149">**User name**</span></span>  
 <span data-ttu-id="76e02-150">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="76e02-150">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="76e02-151">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="76e02-151">This option is not available.</span></span>  
  
 <span data-ttu-id="76e02-152">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="76e02-152">**Password**</span></span>  
 <span data-ttu-id="76e02-153">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="76e02-153">Provide a password to use when authenticating.</span></span> <span data-ttu-id="76e02-154">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="76e02-154">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e02-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76e02-155">See Also</span></span>  
 <span data-ttu-id="76e02-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="76e02-156">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="76e02-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="76e02-157">DBCC INDEXDEFRAG &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-indexdefrag-transact-sql)  
  
  
