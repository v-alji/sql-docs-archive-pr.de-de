---
title: Allgemein (Dialog Feld Datenbank wiederherstellen) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.restoredbdialog.f1
ms.assetid: 319e7ef5-c9c7-4e50-8690-02a90aed006f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25a49e17227fc2ed6b7b18d2e0964cd8812cbdcb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622281"
---
# <a name="general-restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="102b0-102">Allgemein (Dialogfeld Datenbank wiederherstellen) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="102b0-102">General (Restore Database Dialog Box) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="102b0-103">Auf der Seite **Allgemein** des Dialogfelds **Datenbank wiederherstellen** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie die Sicherungsdatei und die allgemeinen Einstellungen angeben, die beim Wiederherstellen einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="102b0-103">Use the **General** page of the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to specify the backup file and general settings to use when restoring an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="102b0-104">Für jede Sicherungsdatei muss der Benutzer, der den Wiederherstellungsbefehl ausführt, über die Berechtigung zum Lesen von dem für jede Datei angegebenen Sicherungsspeicherort verfügen.</span><span class="sxs-lookup"><span data-stu-id="102b0-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="102b0-105">Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank, die nicht auf dem Server installiert ist, muss der Benutzer zusätzlich Mitglied der Serverrolle für die betreffende [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="102b0-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="102b0-106">Zum Überschreiben einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank muss der Benutzer entweder Mitglied der Serverrolle für die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="102b0-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="102b0-107">Nach dem Wiederherstellen einer vorhandenen Datenbank verliert der Benutzer, der die Datenbank wiederhergestellt hat, möglicherweise den Zugriff auf diese Datenbank.</span><span class="sxs-lookup"><span data-stu-id="102b0-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="102b0-108">Dies ist u. U. der Fall, wenn der Benutzer zum Zeitpunkt der Sicherung kein Mitglied der Serverrolle oder der Datenbankrolle mit der Berechtigung "Vollzugriff (Administrator)" war.</span><span class="sxs-lookup"><span data-stu-id="102b0-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="102b0-109">**So zeigen Sie die Seite Allgemein im Dialogfeld Datenbank wiederherstellen an**</span><span class="sxs-lookup"><span data-stu-id="102b0-109">**To display the General page in the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="102b0-110">Klicken Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]mit der rechten Maustaste entweder auf den Ordner **Datenbanken** einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder auf eine Datenbank im **Objekt-Explorer**, klicken Sie auf **Wiederherstellen**, und unter **Seite auswählen**klicken Sie anschließend auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="102b0-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, click **Restore**, and then under **Select a page**, click **General**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="102b0-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="102b0-111">Options</span></span>  
 <span data-ttu-id="102b0-112">**Skript**</span><span class="sxs-lookup"><span data-stu-id="102b0-112">**Script**</span></span>  
 <span data-ttu-id="102b0-113">Erstellt ein Wiederherstellungsskript, das auf den im Dialogfeld aktivierten Optionen basiert.</span><span class="sxs-lookup"><span data-stu-id="102b0-113">Creates a restore script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="102b0-114">Das Wiederherstellungsskript wird in der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Skriptsprache (ASSL) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="102b0-114">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="102b0-115">Wenn Sie auf das Symbol **Skript** klicken, wird das Wiederherstellungsskript standardmäßig an ein neues Abfragefenster gesendet.</span><span class="sxs-lookup"><span data-stu-id="102b0-115">Clicking the **Script** icon sends the restore script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="102b0-116">Durch Klicken auf den Pfeil neben **Skript** wird ein Menü angezeigt, in dem Sie auswählen können, wohin das Wiederherstellungsskript geschickt werden soll:</span><span class="sxs-lookup"><span data-stu-id="102b0-116">Clicking the **Script** arrow displays a menu that allows you to choose where to send the restore script:</span></span>  
  
-   <span data-ttu-id="102b0-117">An ein neues Abfragefenster (Standard)</span><span class="sxs-lookup"><span data-stu-id="102b0-117">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="102b0-118">An eine Datei</span><span class="sxs-lookup"><span data-stu-id="102b0-118">To a file.</span></span>  
  
-   <span data-ttu-id="102b0-119">An die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="102b0-119">To the clipboard.</span></span>  
  
-   <span data-ttu-id="102b0-120">An einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="102b0-120">To a job.</span></span>  
  
 <span data-ttu-id="102b0-121">**Datenbank wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="102b0-121">**Restore database**</span></span>  
 <span data-ttu-id="102b0-122">Wählen Sie die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank aus, die wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="102b0-122">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to restore.</span></span>  
  
 <span data-ttu-id="102b0-123">**Aus Sicherungsdatei**</span><span class="sxs-lookup"><span data-stu-id="102b0-123">**From backup file**</span></span>  
 <span data-ttu-id="102b0-124">Wählen Sie die Sicherungsdatei aus, aus der die ausgewählte [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank wiederhergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="102b0-124">Select the backup file from which to restore the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="102b0-125">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="102b0-125">**Browse**</span></span>  
 <span data-ttu-id="102b0-126">Klicken Sie hier, um das Dialogfeld **Datenbankdateien suchen** anzuzeigen, und wählen Sie Pfad und Dateinamen der Sicherungsdatei aus, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="102b0-126">Click to display the **Locate Database Files** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="102b0-127">Weitere Informationen zum Dialogfeld **Datenbankdateien suchen** finden Sie unter [Dialogfeld „Datenbankdateien suchen“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="102b0-127">For more information about the **Locate Database Files** dialog box, see [Locate Database Files Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](locate-database-files-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="102b0-128">**Überschreiben der Datenbank zulassen**</span><span class="sxs-lookup"><span data-stu-id="102b0-128">**Allow database overwrite**</span></span>  
 <span data-ttu-id="102b0-129">Wählen Sie diese Option aus, damit beim Wiederherstellen durch [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] die vorhandenen Objekte in der ausgewählten [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank mit dem Inhalt der ausgewählten Sicherungsdatei überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="102b0-129">Select to allow [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to restore the contents of the selected backup file over any existing objects in the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="102b0-130">**Sicherheitsinformationen einschließen**</span><span class="sxs-lookup"><span data-stu-id="102b0-130">**Include security information**</span></span>  
 <span data-ttu-id="102b0-131">Wählen Sie diese Option aus, um alle Sicherheitsinformationen in die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank zu kopieren, die in der Sicherungsdatei gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="102b0-131">Select to copy any security information stored in the backup file to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="102b0-132">Wenn diese Option ausgewählt ist, können Sie den Umfang der Sicherheitsinformationen aus der dann verfügbaren Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="102b0-132">If this option is selected, you can choose the amount of security information from the drop-down list enabled by selecting this option.</span></span> <span data-ttu-id="102b0-133">Die folgenden Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="102b0-133">The following options are available:</span></span>  
  
|<span data-ttu-id="102b0-134">Option</span><span class="sxs-lookup"><span data-stu-id="102b0-134">Option</span></span>|<span data-ttu-id="102b0-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="102b0-135">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="102b0-136">**Alle kopieren**</span><span class="sxs-lookup"><span data-stu-id="102b0-136">**Copy All**</span></span>|<span data-ttu-id="102b0-137">Stellt die Datenbankrollen und die den Rollen zugeordneten Benutzerkonten wieder her, die in der Sicherungsdatei enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="102b0-137">Restores the database roles contained in the backup file, as well as the user accounts associated with the roles.</span></span>|  
|<span data-ttu-id="102b0-138">**Mitgliedschaft auslassen**</span><span class="sxs-lookup"><span data-stu-id="102b0-138">**Skip Membership**</span></span>|<span data-ttu-id="102b0-139">Stellt die Datenbankrollen wieder her, die in der Sicherungsdatei enthalten sind, nicht aber die den Rollen zugeordneten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="102b0-139">Restores the database roles contained in the backup file, but does not restore the user accounts associated with the roles.</span></span>|  
  
 <span data-ttu-id="102b0-140">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="102b0-140">**Password**</span></span>  
 <span data-ttu-id="102b0-141">Wenn die Sicherungsdatei verschlüsselt ist, geben Sie das Kennwort ein, dass zur Verschlüsselung der Sicherungsdatei verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="102b0-141">If the backup file is encrypted, type the password used to encrypt the backup file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102b0-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="102b0-142">See Also</span></span>  
 <span data-ttu-id="102b0-143">[Dialog Feld "Datenbank wiederherstellen" &#40;Analysis Services-Mehrdimensionale Daten&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="102b0-143">[Restore Database Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="102b0-144">[Partitionen &#40;Dialog Feld Datenbank wiederherstellen&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="102b0-144">[Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="102b0-145">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="102b0-145">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
