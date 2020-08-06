---
title: Dialog Feld ' Datenbank sichern ' (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Backup.f1
ms.assetid: 7811ce7d-6c37-4189-bfa6-ef36fb4932db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 48cf094353c53213864dae656af94ae791442105
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610360"
---
# <a name="backup-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="96b85-102">Dialogfeld Sicherungsdatenbank (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="96b85-102">Backup Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="96b85-103">Im Dialogfeld **Datenbank sichern** von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank in einer Sicherungsdatei im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Sicherungsdateiformat (\*.abf) sichern.</span><span class="sxs-lookup"><span data-stu-id="96b85-103">Use the **Backup Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to back up an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database to a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="96b85-104">Für jede Sicherungsdatei muss der Benutzer, der den Sicherungsbefehl ausführt, über die Berechtigung zum Schreiben in den für jede Datei angegebenen Sicherungsspeicherort verfügen.</span><span class="sxs-lookup"><span data-stu-id="96b85-104">For each backup file, the user who runs the backup command must have permission to write to the backup location specified for each file.</span></span> <span data-ttu-id="96b85-105">Dem Benutzer muss zudem eine der folgenden Rollen zugewiesen worden sein: Mitglied einer Serverrolle für die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank.</span><span class="sxs-lookup"><span data-stu-id="96b85-105">Also, the user must have one of the following roles: a member of a server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be backed up.</span></span>  
  
 <span data-ttu-id="96b85-106">**So zeigen Sie das Dialogfeld Datenbank sichern an**</span><span class="sxs-lookup"><span data-stu-id="96b85-106">**To display the Backup Database dialog box**</span></span>  
  
-   <span data-ttu-id="96b85-107">Klicken Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]mit der rechten Maustaste entweder auf den Ordner **Datenbanken** einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder auf eine Datenbank im **Objekt-Explorer**, und klicken Sie dann auf **Sichern**.</span><span class="sxs-lookup"><span data-stu-id="96b85-107">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Backup**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="96b85-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="96b85-108">Options</span></span>  
 <span data-ttu-id="96b85-109">**Skript**</span><span class="sxs-lookup"><span data-stu-id="96b85-109">**Script**</span></span>  
 <span data-ttu-id="96b85-110">Erstellt ein Sicherungsskript, das auf den im Dialogfeld aktivierten Optionen basiert.</span><span class="sxs-lookup"><span data-stu-id="96b85-110">Creates a backup script that is based on the options selected in the dialog box.</span></span> <span data-ttu-id="96b85-111">Das Wiederherstellungsskript wird in der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Skriptsprache (ASSL) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="96b85-111">The restore script is written in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Scripting Language (ASSL).</span></span>  
  
 <span data-ttu-id="96b85-112">Wenn Sie auf das Symbol **Skript** klicken, wird das Sicherungsskript standardmäßig an ein neues Abfragefenster gesendet.</span><span class="sxs-lookup"><span data-stu-id="96b85-112">Clicking the **Script** icon sends the backup script into a new query window, by default.</span></span>  
  
 <span data-ttu-id="96b85-113">Durch Klicken auf den Pfeil neben **Skript** wird ein Menü angezeigt, in dem Sie auswählen können, wohin das Sicherungsskript geschickt werden soll:</span><span class="sxs-lookup"><span data-stu-id="96b85-113">Clicking the **Script** arrow displays a menu that allows you to choose where to send the backup script:</span></span>  
  
-   <span data-ttu-id="96b85-114">An ein neues Abfragefenster (Standard)</span><span class="sxs-lookup"><span data-stu-id="96b85-114">To a new query window (default).</span></span>  
  
-   <span data-ttu-id="96b85-115">An eine Datei</span><span class="sxs-lookup"><span data-stu-id="96b85-115">To a file.</span></span>  
  
-   <span data-ttu-id="96b85-116">An die Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="96b85-116">To the clipboard.</span></span>  
  
-   <span data-ttu-id="96b85-117">An einen Auftrag</span><span class="sxs-lookup"><span data-stu-id="96b85-117">To a job.</span></span>  
  
 <span data-ttu-id="96b85-118">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="96b85-118">**Database**</span></span>  
 <span data-ttu-id="96b85-119">Zeigt den Namen der aktuell ausgewählten Datenbank von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="96b85-119">Displays the name of the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="96b85-120">**Sicherungsdatei**</span><span class="sxs-lookup"><span data-stu-id="96b85-120">**Backup file**</span></span>  
 <span data-ttu-id="96b85-121">Geben Sie den vollständigen Pfad und Dateinamen der Sicherungsdatei ein, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="96b85-121">Type the full path and file name of the backup file to use.</span></span>  
  
 <span data-ttu-id="96b85-122">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="96b85-122">**Browse**</span></span>  
 <span data-ttu-id="96b85-123">Klicken Sie hier, um das Dialogfeld **Datei speichern unter** anzuzeigen, und wählen Sie Pfad und Dateinamen der Sicherungsdatei aus, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="96b85-123">Click to display the **Save File As** dialog box and select the path and file name of the backup file to use.</span></span> <span data-ttu-id="96b85-124">Weitere Informationen zum Dialogfeld **Speichern unter** finden Sie unter [Dialogfeld „Datei speichern unter“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="96b85-124">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="96b85-125">**Überschreiben von Dateien zulassen**</span><span class="sxs-lookup"><span data-stu-id="96b85-125">**Allow file overwrite**</span></span>  
 <span data-ttu-id="96b85-126">Wählen Sie diese Option aus, um eine gegebenenfalls vorhandene Sicherungsdatei oder eine Remotesicherungsdatei zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="96b85-126">Select to overwrite an existing backup file or remote backup file, if one exists.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b85-127"> Wenn diese Option nicht ausgewählt ist und die in einem der Felder **Sicherungsdatei** oder **Remotesicherungsdatei** angegebene Sicherungsdatei vorhanden ist, wird ein Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="96b85-127">If this option is not selected and the backup file specified in **Backup file** or a remote backup file specified in **Remote backup file** exists, an error occurs.</span></span>  
  
 <span data-ttu-id="96b85-128">**Komprimierung anwenden**</span><span class="sxs-lookup"><span data-stu-id="96b85-128">**Apply compression**</span></span>  
 <span data-ttu-id="96b85-129">Wählen Sie diese Option aus, um den Inhalt der Sicherungsdatei und gegebenenfalls vorhandener Remotesicherungsdateien zu komprimieren.</span><span class="sxs-lookup"><span data-stu-id="96b85-129">Select to compress the contents of the backup file and, if specified, remote backup files.</span></span>  
  
 <span data-ttu-id="96b85-130">**Sicherungsdatei verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="96b85-130">**Encrypt backup file**</span></span>  
 <span data-ttu-id="96b85-131">Wählen Sie diese Option aus, um die Sicherungsdatei mithilfe des im Feld **Kennwort**bereitgestellten Kennworts zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="96b85-131">Select to encrypt the backup file using the password supplied in **Password**.</span></span>  
  
 <span data-ttu-id="96b85-132">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="96b85-132">**Password**</span></span>  
 <span data-ttu-id="96b85-133">Geben Sie das Kennwort ein, das beim Verschlüsseln der Sicherungsdatei und gegebenenfalls vorhandener Remotesicherungsdateien verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="96b85-133">Type the password to use when encrypting the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b85-134"> Diese Option ist nur bei Auswahl von **Sicherungsdatei verschlüsseln** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96b85-134">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="96b85-135">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="96b85-135">**Confirm Password**</span></span>  
 <span data-ttu-id="96b85-136">Geben Sie das im Feld **Kennwort** eingegebene Kennwort ein, um das Kennwort für die Sicherungsdatei und für gegebenenfalls vorhandene Remotesicherungsdateien zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="96b85-136">Type the password entered in **Password** to confirm the password for the backup file and, if specified, remote backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b85-137"> Diese Option ist nur bei Auswahl von **Sicherungsdatei verschlüsseln** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96b85-137">This option is enabled only if **Encrypt backup file** is selected.</span></span>  
  
 <span data-ttu-id="96b85-138">**Remotepartition(en) sichern**</span><span class="sxs-lookup"><span data-stu-id="96b85-138">**Backup remote partition(s)**</span></span>  
 <span data-ttu-id="96b85-139">Wählen Sie diese Option aus, um Informationen zum Speicherort sowie die Daten der Remotepartitionen in der Sicherungsdatei zu sichern.</span><span class="sxs-lookup"><span data-stu-id="96b85-139">Select to include location information and data for remote partitions in the backup file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b85-140">Diese Option ist nur dann aktiviert, wenn für die aktuell ausgewählte [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank Remotepartitionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96b85-140">This option is enabled only if the currently selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database uses remote partitions.</span></span>  
  
 <span data-ttu-id="96b85-141">**Speicherort für Remotepartitionssicherungen**</span><span class="sxs-lookup"><span data-stu-id="96b85-141">**Remote partition backup location**</span></span>  
 <span data-ttu-id="96b85-142">Zeigt den Speicherort der Remotepartitionen an, die der ausgewählten Datenbank zugeordnet sind, sowie die Remotesicherungsdatei, in der die Daten und Metadaten der Remotepartitionen gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="96b85-142">Displays the location of remote partitions associated with the selected database, as well as the remote backup file used to back up the data and metadata for the remote partitions.</span></span> <span data-ttu-id="96b85-143">Folgende Spalten sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="96b85-143">The following columns are available:</span></span>  
  
|<span data-ttu-id="96b85-144">Spalte</span><span class="sxs-lookup"><span data-stu-id="96b85-144">Column</span></span>|<span data-ttu-id="96b85-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="96b85-145">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="96b85-146">**Server**</span><span class="sxs-lookup"><span data-stu-id="96b85-146">**Server**</span></span>|<span data-ttu-id="96b85-147">Zeigt die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] an, die die Remotepartitionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="96b85-147">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that manages the remote partitions.</span></span>|  
|<span data-ttu-id="96b85-148">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="96b85-148">**Database**</span></span>|<span data-ttu-id="96b85-149">Zeigt die Datenbank von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] an, zu der die Remotepartitionen gehören.</span><span class="sxs-lookup"><span data-stu-id="96b85-149">Displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that contains the remote partitions.</span></span>|  
|<span data-ttu-id="96b85-150">**Partitionsliste**</span><span class="sxs-lookup"><span data-stu-id="96b85-150">**Partition List**</span></span>|<span data-ttu-id="96b85-151">Zeigt die Liste der Remotepartitionen an, die zu der im Feld **Datenbank**angegebenen Datenbank gehören.</span><span class="sxs-lookup"><span data-stu-id="96b85-151">Displays the list of remote partitions contained by the database displayed in **Database**.</span></span>|  
|<span data-ttu-id="96b85-152">**Remotesicherungsdatei**</span><span class="sxs-lookup"><span data-stu-id="96b85-152">**Remote backup file**</span></span>|<span data-ttu-id="96b85-153">Geben Sie den vollständigen Pfad und Dateinamen der Remotesicherungsdatei ein, die verwendet werden soll. Wahlweise können Sie auch auf die Schaltfläche mit den Auslassungspunkten (**...**) klicken, um das Dialogfeld **Datei speichern unter** anzuzeigen und dort den Pfad und Dateinamen der betreffenden Remotesicherungsdatei auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="96b85-153">Type the full path and file name of the remote backup file to use, or click the ellipsis button (**...**) to display the **Save File As** dialog box and select the path and file name of the remote backup file to use.</span></span> <span data-ttu-id="96b85-154">Weitere Informationen zum Dialogfeld **Speichern unter** finden Sie unter [Dialogfeld „Datei speichern unter“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="96b85-154">For more information about the **Save File As** dialog box, see [Save File As Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](save-file-as-dialog-box-analysis-services-multidimensional-data.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96b85-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="96b85-155">See Also</span></span>  
 <span data-ttu-id="96b85-156">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="96b85-156">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="96b85-157">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="96b85-157">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
