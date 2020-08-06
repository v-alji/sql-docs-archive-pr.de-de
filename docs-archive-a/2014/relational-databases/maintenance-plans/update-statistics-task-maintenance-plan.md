---
title: Task „Statistiken aktualisieren“ (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.statistics.f1
helpviewer_keywords:
- Updates Statistics Task dialog box
ms.assetid: 22902fd0-eb39-4f18-af94-3fcb69d2a3a4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 486ef2da96785ed200900f497435117ef6437cb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622634"
---
# <a name="update-statistics-task-maintenance-plan"></a><span data-ttu-id="691b7-102">Task 'Statistiken aktualisieren' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="691b7-102">Update Statistics Task (Maintenance Plan)</span></span>
  <span data-ttu-id="691b7-103">Verwenden Sie das Dialogfeld **Task „Statistiken aktualisieren“** , um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Informationen über die Daten in Tabellen und Indizes zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="691b7-103">Use the **Update Statistics Task** dialog to update [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] information about the data in the tables and indexes.</span></span> <span data-ttu-id="691b7-104">Dieser Task erstellt erneut die Verteilungsstatistik jedes für Benutzertabellen in der Datenbank erstellten Index mithilfe einer neuen Stichprobe.</span><span class="sxs-lookup"><span data-stu-id="691b7-104">This task resamples the distribution statistics of each index created on user tables in the database.</span></span> <span data-ttu-id="691b7-105">Die Verteilungsstatistiken werden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet, um die Navigation durch die Tabellen während der Verarbeitung von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="691b7-105">The distribution statistics are used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to optimize navigation through tables during the processing of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="691b7-106">Um die Verteilungsstatistiken automatisch zu erstellen, nimmt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für jeden Index in regelmäßigen Abständen Daten in der entsprechenden Tabelle als Stichprobe.</span><span class="sxs-lookup"><span data-stu-id="691b7-106">To build the distribution statistics automatically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] periodically samples the data in the corresponding table for each index.</span></span> <span data-ttu-id="691b7-107">Die Größe der Stichprobe basiert auf der Anzahl der Zeilen in der Tabelle und der Häufigkeit der an den Daten vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="691b7-107">This size of the sample is based on the number of rows in the table and the frequency of data modification.</span></span> <span data-ttu-id="691b7-108">Verwenden Sie diese Option, um mithilfe des angegebenen Prozentsatzes der Tabellendaten eine zusätzliche Stichprobe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="691b7-108">Use this option to perform an additional sampling using the specified percentage of data in the tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="691b7-109">erstellt mithilfe dieser Informationen bessere Abfragepläne.</span><span class="sxs-lookup"><span data-stu-id="691b7-109">uses this information to create better query plans.</span></span>  
  
 <span data-ttu-id="691b7-110">Dieser Task führt die UPDATE STATISTICS-Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="691b7-110">This task executes the UPDATE STATISTICS statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="691b7-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="691b7-111">Options</span></span>  
 <span data-ttu-id="691b7-112">**Connection**</span><span class="sxs-lookup"><span data-stu-id="691b7-112">**Connection**</span></span>  
 <span data-ttu-id="691b7-113">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="691b7-113">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="691b7-114">**Neu**</span><span class="sxs-lookup"><span data-stu-id="691b7-114">**New**</span></span>  
 <span data-ttu-id="691b7-115">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="691b7-115">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="691b7-116">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="691b7-116">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="691b7-117">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="691b7-117">**Databases**</span></span>  
 <span data-ttu-id="691b7-118">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="691b7-118">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="691b7-119">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="691b7-119">**All databases**</span></span>  
  
     <span data-ttu-id="691b7-120">Generieren Sie einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-120">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases, except tempdb.</span></span>  
  
-   <span data-ttu-id="691b7-121">**Alle Systemdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="691b7-121">**All system databases**</span></span>  
  
     <span data-ttu-id="691b7-122">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-122">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="691b7-123">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-123">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="691b7-124">**Alle Benutzerdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="691b7-124">**All user databases**</span></span>  
  
     <span data-ttu-id="691b7-125">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-125">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="691b7-126">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-126">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="691b7-127">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="691b7-127">**These specific databases**</span></span>  
  
     <span data-ttu-id="691b7-128">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-128">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="691b7-129">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="691b7-129">At least one database in the list must be selected if this option is chosen.</span></span>  
  
 <span data-ttu-id="691b7-130">**Hinweis:** Wartungspläne werden nur für Datenbanken mit Kompatibilitätsgrad 80 oder höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="691b7-130">**Note** Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="691b7-131">Datenbanken mit Kompatibilitätsgrad 70 oder niedriger werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="691b7-131">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="691b7-132">**Object**</span><span class="sxs-lookup"><span data-stu-id="691b7-132">**Object**</span></span>  
 <span data-ttu-id="691b7-133">Begrenzt das Raster **Auswahl** auf die Anzeige von Tabellen, Sichten oder beides.</span><span class="sxs-lookup"><span data-stu-id="691b7-133">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="691b7-134">**Auswahl**</span><span class="sxs-lookup"><span data-stu-id="691b7-134">**Selection**</span></span>  
 <span data-ttu-id="691b7-135">Gibt die Tabellen oder Indizes an, auf die sich dieser Task auswirkt.</span><span class="sxs-lookup"><span data-stu-id="691b7-135">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="691b7-136">Nicht verfügbar, wenn im Objektfeld der Eintrag **Tabellen und Sichten** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="691b7-136">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="691b7-137">**Alle vorhandenen Statistiken**</span><span class="sxs-lookup"><span data-stu-id="691b7-137">**All existing statistics**</span></span>  
 <span data-ttu-id="691b7-138">Aktualisiert alle Statistiken für Spalten und für Indizes.</span><span class="sxs-lookup"><span data-stu-id="691b7-138">Update statistics for both columns and indexes.</span></span>  
  
 <span data-ttu-id="691b7-139">**Nur Spaltenstatistiken**</span><span class="sxs-lookup"><span data-stu-id="691b7-139">**Column statistics only**</span></span>  
 <span data-ttu-id="691b7-140">Aktualisiert nur Spaltenstatistiken.</span><span class="sxs-lookup"><span data-stu-id="691b7-140">Only update column statistics.</span></span>  
  
 <span data-ttu-id="691b7-141">**Nur Indexstatistiken**</span><span class="sxs-lookup"><span data-stu-id="691b7-141">**Index statistics only**</span></span>  
 <span data-ttu-id="691b7-142">Aktualisiert nur Indexstatistiken.</span><span class="sxs-lookup"><span data-stu-id="691b7-142">Only update index statistics.</span></span>  
  
 <span data-ttu-id="691b7-143">**Scantyp**</span><span class="sxs-lookup"><span data-stu-id="691b7-143">**Scan type**</span></span>  
 <span data-ttu-id="691b7-144">Der Typ des Scanvorgangs, der zum Zusammenstellen von aktualisierten Statistiken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="691b7-144">Type of scan used to gather updated statistics.</span></span>  
  
 <span data-ttu-id="691b7-145">**Vollständiger Scan**</span><span class="sxs-lookup"><span data-stu-id="691b7-145">**Full scan**</span></span>  
 <span data-ttu-id="691b7-146">Liest zum Zusammenstellen der Statistiken alle Zeilen in der Tabelle oder Sicht.</span><span class="sxs-lookup"><span data-stu-id="691b7-146">Read all rows in the table or view to gather the statistics.</span></span>  
  
 <span data-ttu-id="691b7-147">**Stichprobe von**</span><span class="sxs-lookup"><span data-stu-id="691b7-147">**Sample by**</span></span>  
 <span data-ttu-id="691b7-148">Gibt den prozentualen Anteil der Tabelle oder der indizierten Sicht an bzw. die Anzahl der Zeilen, für die die Stichprobe vorgenommen werden soll, wenn Statistiken für größere Tabellen oder Sichten gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="691b7-148">Specify the percentage of the table or indexed view, or the number of rows to sample when collecting statistics for larger tables or views.</span></span>  
  
 <span data-ttu-id="691b7-149">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="691b7-149">**View T-SQL**</span></span>  
 <span data-ttu-id="691b7-150">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="691b7-150">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="691b7-151">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="691b7-151">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="691b7-152">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="691b7-152">New Connection Dialog Box</span></span>  
 <span data-ttu-id="691b7-153">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="691b7-153">**Connection name**</span></span>  
 <span data-ttu-id="691b7-154">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="691b7-154">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="691b7-155">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="691b7-155">**Select or enter a server name**</span></span>  
 <span data-ttu-id="691b7-156">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="691b7-156">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="691b7-157">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="691b7-157">**Refresh**</span></span>  
 <span data-ttu-id="691b7-158">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="691b7-158">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="691b7-159">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="691b7-159">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="691b7-160">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="691b7-160">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="691b7-161">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="691b7-161">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="691b7-162">Stellt mithilfe der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="691b7-162">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="691b7-163">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="691b7-163">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="691b7-164">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="691b7-164">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="691b7-165">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="691b7-165">This option is not available.</span></span>  
  
 <span data-ttu-id="691b7-166">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="691b7-166">**User name**</span></span>  
 <span data-ttu-id="691b7-167">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="691b7-167">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="691b7-168">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="691b7-168">This option is not available.</span></span>  
  
 <span data-ttu-id="691b7-169">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="691b7-169">**Password**</span></span>  
 <span data-ttu-id="691b7-170">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="691b7-170">Provide a password to use when authenticating.</span></span> <span data-ttu-id="691b7-171">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="691b7-171">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="691b7-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="691b7-172">See Also</span></span>  
 [<span data-ttu-id="691b7-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="691b7-173">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
