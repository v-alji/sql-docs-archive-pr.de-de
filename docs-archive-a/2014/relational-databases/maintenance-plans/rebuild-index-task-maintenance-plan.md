---
title: Task 'Index neu erstellen' (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.reindex.f1
- reindex
helpviewer_keywords:
- Rebuild Index Task dialog box
ms.assetid: 33e2940b-139f-4563-b0cb-5683f08bd879
author: rothja
ms.author: jroth
ms.openlocfilehash: bc9d7c85a72c34cee1ef7af8cb4b4f25f918a3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616518"
---
# <a name="rebuild-index-task-maintenance-plan"></a><span data-ttu-id="4076f-102">Task 'Index neu erstellen' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="4076f-102">Rebuild Index Task (Maintenance Plan)</span></span>
  <span data-ttu-id="4076f-103">Mithilfe des Dialogfelds **Task „Index neu erstellen“** können Sie Indizes für Tabellen in der Datenbank mit einem neuen Füllfaktor neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4076f-103">Use the **Rebuild Index Task** dialog to re-create the indexes on the tables in the database with a new fill factor.</span></span> <span data-ttu-id="4076f-104">Der Füllfaktor bestimmt die Menge an leeren Speicherplatz auf jeder Seite im Index, der Platz für zukünftige Erweiterungen bieten soll.</span><span class="sxs-lookup"><span data-stu-id="4076f-104">The fill factor determines the amount of empty space on each page in the index, to accommodate future expansion.</span></span> <span data-ttu-id="4076f-105">Wenn der Tabelle Daten hinzugefügt werden, wird der freie Speicherplatz aufgefüllt, da der Wert für den Füllfaktor nicht beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4076f-105">As data is added to the table, the free space fills because the fill factor is not maintained.</span></span> <span data-ttu-id="4076f-106">Der freie Speicherplatz kann durch Neuorganisieren der Daten- und Indexseiten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4076f-106">Reorganizing data and index pages can re-establish the free space.</span></span>  
  
 <span data-ttu-id="4076f-107">**Task „Index neu erstellen“** verwendet die ALTER INDEX-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4076f-107">The **Rebuild Index Task** uses the ALTER INDEX statement.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4076f-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4076f-108">Options</span></span>  
 <span data-ttu-id="4076f-109">**Connection**</span><span class="sxs-lookup"><span data-stu-id="4076f-109">**Connection**</span></span>  
 <span data-ttu-id="4076f-110">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4076f-110">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="4076f-111">**Neu**</span><span class="sxs-lookup"><span data-stu-id="4076f-111">**New**</span></span>  
 <span data-ttu-id="4076f-112">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4076f-112">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="4076f-113">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4076f-113">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="4076f-114">**Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="4076f-114">**Databases**</span></span>  
 <span data-ttu-id="4076f-115">Gibt die Datenbanken an, die von dieser Aufgabe betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="4076f-115">Specify the databases affected by this task.</span></span>  
  
-   <span data-ttu-id="4076f-116">**Alle Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="4076f-116">**All databases**</span></span>  
  
     <span data-ttu-id="4076f-117">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-117">Generate a maintenance plan that runs maintenance tasks against all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases except tempdb.</span></span>  
  
-   <span data-ttu-id="4076f-118">**Alle Systemdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="4076f-118">**All system databases**</span></span>  
  
     <span data-ttu-id="4076f-119">Generiert einen Wartungsplan, der Wartungstasks für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken außer tempdb ausführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-119">Generate a maintenance plan that runs maintenance tasks against each of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases except tempdb.</span></span> <span data-ttu-id="4076f-120">Für benutzerdefinierte Datenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-120">No maintenance tasks are run against user-created databases.</span></span>  
  
-   <span data-ttu-id="4076f-121">**Alle Benutzerdatenbanken**</span><span class="sxs-lookup"><span data-stu-id="4076f-121">**All user databases**</span></span>  
  
     <span data-ttu-id="4076f-122">Generiert einen Wartungsplan, der Wartungstasks für alle benutzerdefinierten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-122">Generate a maintenance plan that runs maintenance tasks against all user-created databases.</span></span> <span data-ttu-id="4076f-123">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemdatenbanken werden keine Wartungstasks ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-123">No maintenance tasks are run against the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system databases.</span></span>  
  
-   <span data-ttu-id="4076f-124">**Diese Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="4076f-124">**These specific databases**</span></span>  
  
     <span data-ttu-id="4076f-125">Generiert einen Wartungsplan, der Wartungstasks nur für die ausgewählten Datenbanken ausführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-125">Generate a maintenance plan that runs maintenance tasks against only those databases that are selected.</span></span> <span data-ttu-id="4076f-126">Wenn diese Option ausgewählt wird, muss mindestens eine Datenbank in der Liste ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="4076f-126">At least one database in the list must be selected if this option is chosen.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4076f-127">Wartungspläne werden nur für Datenbanken mit Kompatibilitätsgrad 80 oder höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4076f-127">Maintenance plans only run against databases set to compatibility level 80 or higher.</span></span> <span data-ttu-id="4076f-128">Datenbanken mit Kompatibilitätsgrad 70 oder niedriger werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4076f-128">Databases set to compatibility level 70 or lower are not displayed.</span></span>  
  
 <span data-ttu-id="4076f-129">**Object**</span><span class="sxs-lookup"><span data-stu-id="4076f-129">**Object**</span></span>  
 <span data-ttu-id="4076f-130">Begrenzt das Raster **Auswahl** auf die Anzeige von Tabellen, Sichten oder beides.</span><span class="sxs-lookup"><span data-stu-id="4076f-130">Limit the **Selection** grid to display tables, views, or both.</span></span>  
  
 <span data-ttu-id="4076f-131">**Auswahl**</span><span class="sxs-lookup"><span data-stu-id="4076f-131">**Selection**</span></span>  
 <span data-ttu-id="4076f-132">Gibt die Tabellen oder Indizes an, auf die sich dieser Task auswirkt.</span><span class="sxs-lookup"><span data-stu-id="4076f-132">Specify the tables or indexes affected by this task.</span></span> <span data-ttu-id="4076f-133">Nicht verfügbar, wenn im Objektfeld der Eintrag **Tabellen und Sichten** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4076f-133">Not available when **Tables and Views** is selected in the Object box.</span></span>  
  
 <span data-ttu-id="4076f-134">**Seiten mit der standardmäßigen freien Speicherplatzmenge neu organisieren**</span><span class="sxs-lookup"><span data-stu-id="4076f-134">**Reorganize pages with the default amount of free space**</span></span>  
 <span data-ttu-id="4076f-135">Löscht die Indizes für die Tabellen in der Datenbank und erstellt sie mit dem Füllfaktor, der beim Erstellen der Indizes angegeben wurde, neu.</span><span class="sxs-lookup"><span data-stu-id="4076f-135">Drop the indexes on the tables in the database and re-create them with the fill factor that was specified when the indexes were created.</span></span>  
  
 <span data-ttu-id="4076f-136">**Ändern des freien Speicherplatzes pro Seiten Prozentsatz in**</span><span class="sxs-lookup"><span data-stu-id="4076f-136">**Change free space per page percentage to**</span></span>  
 <span data-ttu-id="4076f-137">Löscht die Indizes für die Tabellen in der Datenbank und erstellt sie mit einem neuen, automatisch berechneten Füllfaktor neu. Auf diese Weise wird der angegebene freie Speicherplatz auf den Indexseiten reserviert.</span><span class="sxs-lookup"><span data-stu-id="4076f-137">Drop the indexes on the tables in the database and re-create them with a new, automatically calculated fill factor, thereby reserving the specified amount of free space on the index pages.</span></span> <span data-ttu-id="4076f-138">Ein höherer Prozentsatz bedeutet, dass mehr freier Speicherplatz auf den Indexseiten reserviert wird und der Index entsprechend wachsen kann.</span><span class="sxs-lookup"><span data-stu-id="4076f-138">The higher the percentage, the more free space is reserved on the index pages, and the larger the index grows.</span></span> <span data-ttu-id="4076f-139">Die gültigen Werte sind 0 bis 100.</span><span class="sxs-lookup"><span data-stu-id="4076f-139">Valid values are from 0 through 100.</span></span>  
  
 <span data-ttu-id="4076f-140">**Ergebnisse in 'tempdb' sortieren**</span><span class="sxs-lookup"><span data-stu-id="4076f-140">**Sort results in tempdb**</span></span>  
 <span data-ttu-id="4076f-141">Verwenden Sie die- `SORT_IN_TEMPDB` Option, die bestimmt, wo die während der Indexerstellung generierten Zwischenergebnisse der Sortierung temporär gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="4076f-141">Use the `SORT_IN_TEMPDB`option, which determines where the intermediate sort results, generated during index creation, are temporarily stored.</span></span> <span data-ttu-id="4076f-142">Wenn ein Sortiervorgang nicht erforderlich ist oder im Arbeitsspeicher ausgeführt werden kann, wird die Option `SORT_IN_TEMPDB`ignoriert.</span><span class="sxs-lookup"><span data-stu-id="4076f-142">If a sort operation is not required, or if the sort can be performed in memory, the `SORT_IN_TEMPDB`option is ignored.</span></span>  
  
 <span data-ttu-id="4076f-143">**Index online während Neuindizierung**</span><span class="sxs-lookup"><span data-stu-id="4076f-143">**Keep index online while reindexing**</span></span>  
 <span data-ttu-id="4076f-144">Die Option `ONLINE` ermöglicht es Benutzern, während Indexvorgängen auf die zugrunde liegenden Tabellen- bzw. gruppierten Indexdaten und alle zugehörigen nicht gruppierten Indizes zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4076f-144">Use the `ONLINE` option which allows users to access the underlying table or clustered index data and any associated nonclustered indexes during index operations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4076f-145">Onlineindexvorgänge sind nicht in jeder Edition von [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4076f-145">Online index operations are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4076f-146">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="4076f-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="4076f-147">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="4076f-147">**View T-SQL**</span></span>  
 <span data-ttu-id="4076f-148">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4076f-148">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4076f-149">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="4076f-149">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="4076f-150">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="4076f-150">New Connection Dialog Box</span></span>  
 <span data-ttu-id="4076f-151">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="4076f-151">**Connection name**</span></span>  
 <span data-ttu-id="4076f-152">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="4076f-152">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="4076f-153">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="4076f-153">**Select or enter a server name**</span></span>  
 <span data-ttu-id="4076f-154">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4076f-154">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="4076f-155">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="4076f-155">**Refresh**</span></span>  
 <span data-ttu-id="4076f-156">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="4076f-156">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="4076f-157">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="4076f-157">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="4076f-158">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="4076f-158">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="4076f-159">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="4076f-159">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="4076f-160">Stellt mithilfe der Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="4076f-160">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Windows Authentication.</span></span>  
  
 <span data-ttu-id="4076f-161">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="4076f-161">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="4076f-162">Stellt mithilfe der [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="4076f-162">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4076f-163">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4076f-163">This option is not available.</span></span>  
  
 <span data-ttu-id="4076f-164">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="4076f-164">**User name**</span></span>  
 <span data-ttu-id="4076f-165">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="4076f-165">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="4076f-166">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4076f-166">This option is not available.</span></span>  
  
 <span data-ttu-id="4076f-167">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="4076f-167">**Password**</span></span>  
 <span data-ttu-id="4076f-168">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="4076f-168">Provide a password to use when authenticating.</span></span> <span data-ttu-id="4076f-169">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4076f-169">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4076f-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4076f-170">See Also</span></span>  
 <span data-ttu-id="4076f-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4076f-171">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="4076f-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4076f-172">[DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql) </span></span>  
 <span data-ttu-id="4076f-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4076f-173">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="4076f-174">[SORT_IN_TEMPDB-Option für Indizes](../indexes/indexes.md) </span><span class="sxs-lookup"><span data-stu-id="4076f-174">[SORT_IN_TEMPDB Option For Indexes](../indexes/indexes.md) </span></span>  
 <span data-ttu-id="4076f-175">[Richtlinien für Onlineindexvorgänge](../indexes/guidelines-for-online-index-operations.md) </span><span class="sxs-lookup"><span data-stu-id="4076f-175">[Guidelines for Online Index Operations](../indexes/guidelines-for-online-index-operations.md) </span></span>  
 <span data-ttu-id="4076f-176">[Funktionsweise von Onlineindexvorgängen](../indexes/how-online-index-operations-work.md) </span><span class="sxs-lookup"><span data-stu-id="4076f-176">[How Online Index Operations Work](../indexes/how-online-index-operations-work.md) </span></span>  
 [<span data-ttu-id="4076f-177">Ausführen von Onlineindexvorgängen</span><span class="sxs-lookup"><span data-stu-id="4076f-177">Perform Index Operations Online</span></span>](../indexes/perform-index-operations-online.md)  
  
  
