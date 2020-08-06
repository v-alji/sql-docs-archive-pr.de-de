---
title: Exportieren einer Datenebenenanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportdac.settings.f1
- sql12.swb. exportdac.settings.f1
- sql12.swb.exportdac.welcome.f1
- sql12.swb. exportdac.summary.f1
- sql12.swb.exportdac.progress.f1
- sql12.swb.exportdac.summary.f1
- sql12.swb.exportdac.results.f1
- sql12.swb. exportdac.results.f1
helpviewer_keywords:
- How to [DAC], export
- wizard [DAC], export
- export DAC
- data-tier application [SQL Server], export
ms.assetid: 61915bc5-0f5f-45ac-8cfe-3452bc185558
author: stevestein
ms.author: sstein
ms.openlocfilehash: d5e1bbfc5c38dee5e7f29598086d87b680880641
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620987"
---
# <a name="export-a-data-tier-application"></a><span data-ttu-id="11df3-102">Exportieren einer Datenebenenanwendung</span><span class="sxs-lookup"><span data-stu-id="11df3-102">Export a Data-tier Application</span></span>
  <span data-ttu-id="11df3-103">Beim Exportieren einer bereitgestellten Datenebenenanwendung (DAC) oder einer Datenbank wird eine Exportdatei erstellt, die sowohl die Definitionen der Objekte in der Datenbank als auch alle in den Tabellen enthaltenen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="11df3-103">Exporting a deployed data-tier application (DAC) or database creates an export file that includes both the definitions of the objects in the database and all of the data contained in the tables.</span></span> <span data-ttu-id="11df3-104">Die Exportdatei kann dann in eine andere Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]oder in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]importiert werden.</span><span class="sxs-lookup"><span data-stu-id="11df3-104">The export file can then be imported to another instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="11df3-105">Die Export-/Importvorgänge können kombiniert werden, um eine DAC zwischen Instanzen zu migrieren oder eine logische Sicherung zu erstellen oder um eine lokale Kopie einer in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] bereitgestellten Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11df3-105">The export-import operations can be combined to migrate a DAC between instances, to create a logical backup, or to create an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="11df3-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="11df3-106">Before You Begin</span></span>  
 <span data-ttu-id="11df3-107">Beim Exportvorgang wird in zwei Phasen eine DAC-Exportdatei erstellt.</span><span class="sxs-lookup"><span data-stu-id="11df3-107">The export process builds a DAC export file in two stages.</span></span>  
  
1.  <span data-ttu-id="11df3-108">Beim Export wird eine DAC-Definition in der Exportdatei (BACPAC-Datei) erstellt. Dieser Vorgang entspricht dem Erstellen einer DAC-Definition in einer DAC-Paketdatei durch einen DAC-Auszug.</span><span class="sxs-lookup"><span data-stu-id="11df3-108">The export builds a DAC definition in the export file - BACPAC file - in the same way a DAC extract builds a DAC definition in a DAC package file.</span></span> <span data-ttu-id="11df3-109">Die exportierte DAC-Definition enthält alle Objekte in der aktuellen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="11df3-109">The exported DAC definition includes all of the objects in the current database.</span></span> <span data-ttu-id="11df3-110">Wenn der Exportvorgang für die ursprünglich von einer DAC bereitgestellten Datenbank ausgeführt wird und nach der Bereitstellung Änderungen direkt an der Datenbank vorgenommen wurden, entspricht die exportierte Definition dem Objektsatz in der Datenbank und nicht dem in der ursprünglichen DAC festgelegten Inhalt.</span><span class="sxs-lookup"><span data-stu-id="11df3-110">If the export process is run against a database that was originally deployed from a DAC, and changes were made directly to the database after deployment, the exported definition matches the object set in the database, not what was defined in the original DAC.</span></span>  
  
2.  <span data-ttu-id="11df3-111">Beim Export werden die Daten per Massenkopieren aus allen Tabellen in der Datenbank kopiert und in die Exportdatei integriert.</span><span class="sxs-lookup"><span data-stu-id="11df3-111">The export bulk copies out the data from all of the tables in the database and incorporates the data into the export file.</span></span>  
  
 <span data-ttu-id="11df3-112">Beim Exportvorgang wird die DAC-Version auf 1.0.0.0 und die DAC-Beschreibung in der Exportdatei auf eine leere Zeichenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="11df3-112">The export process sets the DAC version to 1.0.0.0 and the DAC description in the export file to an empty string.</span></span> <span data-ttu-id="11df3-113">Wurde die Datenbank von einer DAC bereitgestellt, enthält die DAC-Definition in der Exportdatei den Namen der ursprünglichen DAC. Andernfalls wird der DAC-Name auf den Datenbanknamen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="11df3-113">If the database was deployed from a DAC, the DAC definition in the export file contains the name given to the original DAC, otherwise the DAC name is set to the database name.</span></span>  
  

###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="11df3-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11df3-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="11df3-115">Eine DAC oder Datenbank kann nur aus einer Datenbank in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]oder [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) oder höher exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="11df3-115">A DAC or database can only be exported from a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span>  
  
 <span data-ttu-id="11df3-116">Sie können keine Datenbank exportieren, die über in einer DAC nicht unterstützte Objekte oder eigenständige Benutzer verfügt.</span><span class="sxs-lookup"><span data-stu-id="11df3-116">You cannot export a database that has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="11df3-117">Weitere Informationen zu den in einer DAC unterstützten Objekttypen finden Sie unter [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="11df3-117">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="11df3-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="11df3-118">Permissions</span></span>  
 <span data-ttu-id="11df3-119">Zum Exportieren einer DAC sind mindestens die ALTER ANY LOGIN-Berechtigung und die VIEW DEFINITION-Berechtigung im Datenbankbereich sowie SELECT-Berechtigungen für **sys.sql_expression_dependencies**erforderlich.</span><span class="sxs-lookup"><span data-stu-id="11df3-119">Exporting a DAC requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, as well as SELECT permissions on **sys.sql_expression_dependencies**.</span></span> <span data-ttu-id="11df3-120">Zum Exportieren einer DAC sind nur Mitglieder der festen Serverrolle "securityadmin" berechtigt, die ebenfalls Mitglieder der festen Datenbankrolle "database_owner" in der Datenbank sind, aus der die DAC exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="11df3-120">Exporting a DAC can be done by members of the securityadmin fixed server role who are also members of the database_owner fixed database role in the database from which the DAC is exported.</span></span> <span data-ttu-id="11df3-121">Mitglieder der festen Serverrolle „sysadmin“ oder des integrierten SQL Server-Systemadministratorkontos **sa** sind ebenfalls berechtigt, eine DAC zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="11df3-121">Members of the sysadmin fixed server role or the built-in SQL Server system administrator account named **sa** can also export a DAC.</span></span>  
  
##  <a name="using-the-export-data-tier-application-wizard"></a><a name="UsingDeployDACWizard"></a><span data-ttu-id="11df3-122">Verwenden des Assistenten zum Exportieren von Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="11df3-122">Using the Export Data-tier Application Wizard</span></span>  
 <span data-ttu-id="11df3-123">**So exportieren Sie eine DAC mithilfe eines Assistenten**</span><span class="sxs-lookup"><span data-stu-id="11df3-123">**To Export a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="11df3-124">Stellen Sie entweder lokal oder in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]eine Verbindung zu einer Instanz von [!INCLUDE[ssSDS](../../includes/sssds-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="11df3-124">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="11df3-125">Erweitern Sie im **Objekt-Explorer** den Knoten für die Instanz, von der aus Sie die DAC exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="11df3-125">In **Object Explorer**, expand the node for the instance from which you want to export the DAC.</span></span>  
  
3.  <span data-ttu-id="11df3-126">Klicken Sie mit der rechten Maustaste auf den Datenbanknamen.</span><span class="sxs-lookup"><span data-stu-id="11df3-126">Right-click the database name.</span></span>  
  
4.  <span data-ttu-id="11df3-127">Klicken Sie auf **Tasks**, und wählen Sie dann **Exportieren von Datenebenenanwendungen** aus.</span><span class="sxs-lookup"><span data-stu-id="11df3-127">Click **Tasks** and then select **Export Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="11df3-128">Bearbeiten Sie die Dialogfenster des Assistenten:</span><span class="sxs-lookup"><span data-stu-id="11df3-128">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="11df3-129">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="11df3-129">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="11df3-130">Exporteinstellungen (Seite)</span><span class="sxs-lookup"><span data-stu-id="11df3-130">Export Settings Page</span></span>](#Export_settings)  
  
    -   [<span data-ttu-id="11df3-131">Überprüfung (Seite)</span><span class="sxs-lookup"><span data-stu-id="11df3-131">Validation Page</span></span>](#Validation)  
  
    -   [<span data-ttu-id="11df3-132">Seite "Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="11df3-132">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="11df3-133">Seite "Status"</span><span class="sxs-lookup"><span data-stu-id="11df3-133">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="11df3-134">Ergebnisse (Seite)</span><span class="sxs-lookup"><span data-stu-id="11df3-134">Results Page</span></span>](#Results)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="11df3-135">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="11df3-135">Introduction Page</span></span>  
 <span data-ttu-id="11df3-136">Auf dieser Seite werden die Schritte für den Assistenten zum Exportieren von Datenebenenanwendungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11df3-136">This page describes the steps for the Export Data-tier Application Wizard.</span></span>  
  
 <span data-ttu-id="11df3-137">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="11df3-137">**Options**</span></span>  
  
 <span data-ttu-id="11df3-138">**Diese Seite nicht mehr anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="11df3-138">**Do not show this page again.**</span></span> <span data-ttu-id="11df3-139">– Aktivieren Sie dieses Kontrollkästchen, damit die Einführungsseite in Zukunft nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="11df3-139">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="11df3-140">**Weiter** – Geht zur Seite **DAC-Paket auswählen** über.</span><span class="sxs-lookup"><span data-stu-id="11df3-140">**Next** - Proceeds to the **Select DAC Package** page.</span></span>  
  
 <span data-ttu-id="11df3-141">**Abbrechen** : bricht den Vorgang ab und schließt den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="11df3-141">**Cancel** - Cancels the operation and closes the Wizard.</span></span>  
  
##  <a name="export-settings-page"></a><a name="Export_settings"></a><span data-ttu-id="11df3-142">Seite "Einstellungen exportieren"</span><span class="sxs-lookup"><span data-stu-id="11df3-142">Export Settings Page</span></span>  
 <span data-ttu-id="11df3-143">Auf dieser Seite können Sie den Ort angeben, wo die BACPAC-Datei erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="11df3-143">Use this page to specify the location where you want the BACPAC file to be created.</span></span>  
  
-   <span data-ttu-id="11df3-144">**Auf lokalem Datenträger speichern** – Erstellt eine BACPAC-Datei in einem Verzeichnis auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="11df3-144">**Save to local disk** - Creates a BACPAC file in a directory on the local computer.</span></span> <span data-ttu-id="11df3-145">Klicken Sie auf **Durchsuchen...**, um den lokalen Computer zu durchsuchen oder um den Pfad im bereitgestellten Feld anzugeben.</span><span class="sxs-lookup"><span data-stu-id="11df3-145">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="11df3-146">Der Pfadname muss einen Dateinamen und die Erweiterung BACPAC enthalten.</span><span class="sxs-lookup"><span data-stu-id="11df3-146">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="11df3-147">**In Azure speichern** – Erstellt eine BACPAC-Datei in einem Azure-Container.</span><span class="sxs-lookup"><span data-stu-id="11df3-147">**Save to Azure** - Creates a BACPAC file in an Azure container.</span></span> <span data-ttu-id="11df3-148">Sie müssen eine Verbindung mit einem Azure-Container herstellen, um diese Option zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="11df3-148">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="11df3-149">Beachten Sie, dass diese Option auch erfordert, dass Sie ein lokales Verzeichnis für die temporäre Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="11df3-149">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="11df3-150">Beachten Sie, dass die temporäre Datei am angegebenen Speicherort erstellt wird und dort verbleibt, nachdem der Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="11df3-150">Note that the temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
 <span data-ttu-id="11df3-151">Um eine Teilmenge von zu exportierenden Tabellen anzugeben, verwenden Sie die Option **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="11df3-151">To specify a subset of tables to export, use the **Advanced** option.</span></span>  
  
##  <a name="validation-page"></a><a name="Validation"></a><span data-ttu-id="11df3-152">Validierungs Seite</span><span class="sxs-lookup"><span data-stu-id="11df3-152">Validation Page</span></span>  
 <span data-ttu-id="11df3-153">Verwenden Sie die Überprüfungsseite, um sämtliche Probleme zu überprüfen, die den Vorgang blockieren.</span><span class="sxs-lookup"><span data-stu-id="11df3-153">Use the validation page to review any issues that block the operation.</span></span> <span data-ttu-id="11df3-154">Beheben Sie zum Fortfahren die Blockierungsprobleme, und klicken Sie dann auf **Überprüfung erneut ausführen** , um sicherzustellen, dass die Überprüfung erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="11df3-154">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="11df3-155">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="11df3-155">To continue, click **Next**.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="11df3-156">Seite "Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="11df3-156">Summary Page</span></span>  
 <span data-ttu-id="11df3-157">Verwenden Sie diese Seite, um die angegebene Quelle und die Zieleinstellungen für den Vorgang zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="11df3-157">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="11df3-158">Klicken Sie auf **Fertig stellen**, um den Exportvorgang mithilfe der angegebenen Einstellungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="11df3-158">To complete the export operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="11df3-159">Klicken Sie auf **Abbrechen**, um den Exportvorgang abzubrechen und um den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="11df3-159">To cancel the export operation and exit the Wizard, click **Cancel**.</span></span>  
  
##  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="11df3-160">Status (Seite)</span><span class="sxs-lookup"><span data-stu-id="11df3-160">Progress Page</span></span>  
 <span data-ttu-id="11df3-161">Auf dieser Seite wird eine Statusanzeige angezeigt, die den Status des Vorgangs anzeigt.</span><span class="sxs-lookup"><span data-stu-id="11df3-161">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="11df3-162">Klicken Sie auf die Option **Details anzeigen** , um ausführliche Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11df3-162">To view detailed status, click the **View details** option.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="11df3-163">Seite "Ergebnisse"</span><span class="sxs-lookup"><span data-stu-id="11df3-163">Results Page</span></span>  
 <span data-ttu-id="11df3-164">Auf dieser Seite wird angegeben, ob der Exportvorgang erfolgreich war oder ob dabei Fehler auftraten, dabei werden die Ergebnisse jeder Aktion angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11df3-164">This page reports the success or failure of the export operation, showing the results of each action.</span></span> <span data-ttu-id="11df3-165">Für alle Aktionen, die fehlerhaft waren, ist in der Spalte **Ergebnis** ein Link enthalten.</span><span class="sxs-lookup"><span data-stu-id="11df3-165">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="11df3-166">Klicken Sie auf den Link, um einen Bericht des für diese Aktion aufgetretenen Fehlers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11df3-166">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="11df3-167">Klicken Sie auf **Fertig** stellen, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="11df3-167">Click **Finish** to close the Wizard.</span></span>  
  
##  <a name="using-a-net-framework-application"></a><a name="NetApp"></a><span data-ttu-id="11df3-168">Verwenden einer .NET Framework-Anwendung</span><span class="sxs-lookup"><span data-stu-id="11df3-168">Using a .Net Framework Application</span></span>  
 <span data-ttu-id="11df3-169">**So exportieren Sie eine DAC mithilfe der Export()-Methode in einer .NET Framework-Anwendung**</span><span class="sxs-lookup"><span data-stu-id="11df3-169">**To export a DAC using the Export() method in a .Net Framework application.**</span></span>  
  
 <span data-ttu-id="11df3-170">Laden Sie zum Anzeigen eines Codebeispiels die DAC-Beispielanwendung unter [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)herunter.</span><span class="sxs-lookup"><span data-stu-id="11df3-170">To view a code example, download the DAC sample application on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=219575)</span></span>  
  
1.  <span data-ttu-id="11df3-171">Erstellen Sie ein SMO-Serverobjekt, und legen Sie es auf die Instanz fest, die die zu exportierende DAC enthält.</span><span class="sxs-lookup"><span data-stu-id="11df3-171">Create a SMO Server object and set it to the instance that contains the DAC to be exported.</span></span>  
  
2.  <span data-ttu-id="11df3-172">Öffnen Sie ein `ServerConnection`-Objekt, und stellen Sie eine Verbindung mit derselben Instanz her.</span><span class="sxs-lookup"><span data-stu-id="11df3-172">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="11df3-173">Exportieren Sie die DAC mithilfe der `Export`-Methode des `Microsoft.SqlServer.Management.Dac.DacStore`-Typs.</span><span class="sxs-lookup"><span data-stu-id="11df3-173">Use the `Export` method of the `Microsoft.SqlServer.Management.Dac.DacStore` type to export the DAC.</span></span> <span data-ttu-id="11df3-174">Geben Sie den Namen der zu exportierenden DAC sowie den Pfad zum Ordner an, in dem die Exportdatei abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="11df3-174">Specify the name of the DAC to be exported, and the path to the folder where the export file is to be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11df3-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11df3-175">See Also</span></span>  
 <span data-ttu-id="11df3-176">[Datenebenenanwendungen](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="11df3-176">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="11df3-177">Extrahieren einer DAC aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="11df3-177">Extract a DAC From a Database</span></span>](extract-a-dac-from-a-database.md)  
  
  
