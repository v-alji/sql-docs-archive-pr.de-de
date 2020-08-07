---
title: Task 'Wartungscleanup' (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618676"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="cd32e-102">Task 'Wartungscleanup' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="cd32e-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="cd32e-103">Mit dem **Task 'Wartungscleanup'** können Sie alte Dateien für Wartungspläne löschen, u. a. von Wartungsplänen und Datenbanksicherungsdateien erstellte Textberichte.</span><span class="sxs-lookup"><span data-stu-id="cd32e-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd32e-104">Dateien in den Unterordnern des angegebenen Verzeichnisses werden vom Task Wartungscleanup nicht automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cd32e-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="cd32e-105">Diese Funktion reduziert die Möglichkeit eines bösartigen Angriffs, der den Task Wartungscleanup zum Löschen von Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd32e-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="cd32e-106">Wenn Sie Dateien in Unterordnern auf oberster Ebene löschen möchten, müssen Sie **Unterordner auf oberster Ebene einschließen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="cd32e-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd32e-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="cd32e-107">Options</span></span>  
 <span data-ttu-id="cd32e-108">**Connection**</span><span class="sxs-lookup"><span data-stu-id="cd32e-108">**Connection**</span></span>  
 <span data-ttu-id="cd32e-109">Zeigt die aktuelle Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="cd32e-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="cd32e-110">**Neu**</span><span class="sxs-lookup"><span data-stu-id="cd32e-110">**New**</span></span>  
 <span data-ttu-id="cd32e-111">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd32e-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="cd32e-112">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd32e-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="cd32e-113">**Sicherungsdateien**</span><span class="sxs-lookup"><span data-stu-id="cd32e-113">**Backup files**</span></span>  
 <span data-ttu-id="cd32e-114">Löscht Sicherungsdateien.</span><span class="sxs-lookup"><span data-stu-id="cd32e-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="cd32e-115">**Textberichte für Wartungsplan**</span><span class="sxs-lookup"><span data-stu-id="cd32e-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="cd32e-116">Löscht Textberichte über zuvor ausgeführte Wartungspläne.</span><span class="sxs-lookup"><span data-stu-id="cd32e-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="cd32e-117">**Bestimmte Datei löschen**</span><span class="sxs-lookup"><span data-stu-id="cd32e-117">**Delete specific file**</span></span>  
 <span data-ttu-id="cd32e-118">Löscht die im Feld **Dateiname** angegebene Datei.</span><span class="sxs-lookup"><span data-stu-id="cd32e-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="cd32e-119">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="cd32e-119">**File name**</span></span>  
 <span data-ttu-id="cd32e-120">Pfad und Name der zu löschenden Datei.</span><span class="sxs-lookup"><span data-stu-id="cd32e-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="cd32e-121">**Ordner durchsuchen und Dateien anhand einer Erweiterung löschen**</span><span class="sxs-lookup"><span data-stu-id="cd32e-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="cd32e-122">Löscht alle Dateien mit der angegebenen Erweiterung im angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="cd32e-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="cd32e-123">Mithilfe dieser Option können Sie mehrere Dateien gleichzeitig löschen, z. B. alle Sicherungsdateien mit der Erweiterung .bak im ausgewählten Ordner.</span><span class="sxs-lookup"><span data-stu-id="cd32e-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="cd32e-124">**Ordner**</span><span class="sxs-lookup"><span data-stu-id="cd32e-124">**Folder**</span></span>  
 <span data-ttu-id="cd32e-125">Pfad und Name des Ordners, in dem die zu löschenden Dateien enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cd32e-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="cd32e-126">**Dateierweiterung**</span><span class="sxs-lookup"><span data-stu-id="cd32e-126">**File extension**</span></span>  
 <span data-ttu-id="cd32e-127">Geben Sie die Dateierweiterung der zu löschenden Dateien an.</span><span class="sxs-lookup"><span data-stu-id="cd32e-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="cd32e-128">**Unterordner auf oberster Ebene einschließen**</span><span class="sxs-lookup"><span data-stu-id="cd32e-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="cd32e-129">Löscht Dateien mit der für **Dateierweiterung** angegebenen Erweiterung aus den Unterordnern der obersten Ebene unter **Ordner**.</span><span class="sxs-lookup"><span data-stu-id="cd32e-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="cd32e-130">**Dateien anhand ihres Alters zur Tasklaufzeit löschen**</span><span class="sxs-lookup"><span data-stu-id="cd32e-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="cd32e-131">Geben Sie das Mindestalter der zu löschenden Dateien an, indem Sie im Feld **Dateien löschen, die älter sind als** eine Zahl und eine Zeiteinheit festlegen.</span><span class="sxs-lookup"><span data-stu-id="cd32e-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="cd32e-132">**Dateien löschen, die älter sind als**</span><span class="sxs-lookup"><span data-stu-id="cd32e-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="cd32e-133">Geben Sie das Mindestalter der zu löschenden Dateien an, in dem Sie eine Nummer und eine Zeiteinheit (Tag, Woche, Monat oder Jahr) festlegen.</span><span class="sxs-lookup"><span data-stu-id="cd32e-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="cd32e-134">Dateien, die älter sind als der angegebene Zeitrahmen, werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="cd32e-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="cd32e-135">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="cd32e-135">**View T-SQL**</span></span>  
 <span data-ttu-id="cd32e-136">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd32e-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cd32e-137">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="cd32e-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="cd32e-138">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="cd32e-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="cd32e-139">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="cd32e-139">**Connection name**</span></span>  
 <span data-ttu-id="cd32e-140">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="cd32e-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="cd32e-141">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="cd32e-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="cd32e-142">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cd32e-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="cd32e-143">**...**</span><span class="sxs-lookup"><span data-stu-id="cd32e-143">**...**</span></span>  
 <span data-ttu-id="cd32e-144">Wählen Sie diese Option aus, um die Liste der verfügbaren Server anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd32e-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="cd32e-145">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="cd32e-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="cd32e-146">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="cd32e-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="cd32e-147">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="cd32e-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="cd32e-148">Stellt mithilfe der Microsoft Windows-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="cd32e-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="cd32e-149">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="cd32e-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="cd32e-150">Stellt mithilfe der SQL Server-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="cd32e-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="cd32e-151">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd32e-151">This option is not available.</span></span>  
  
 <span data-ttu-id="cd32e-152">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="cd32e-152">**User name**</span></span>  
 <span data-ttu-id="cd32e-153">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="cd32e-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="cd32e-154">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd32e-154">This option is not available.</span></span>  
  
 <span data-ttu-id="cd32e-155">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="cd32e-155">**Password**</span></span>  
 <span data-ttu-id="cd32e-156">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="cd32e-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="cd32e-157">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd32e-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd32e-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd32e-158">See Also</span></span>  
 [<span data-ttu-id="cd32e-159">Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="cd32e-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
