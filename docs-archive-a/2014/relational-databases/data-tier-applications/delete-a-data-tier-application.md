---
title: Löschen einer Datenebenenanwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.deletedacwizard.introduction.f1
- sql12.swb.deletedacwizard.deletedac.f1
- sql12.swb.deletedacwizard.summary.f1
- sql12.swb.deletedacwizard.choosemethod.f1
helpviewer_keywords:
- How to [DAC], delete
- data-tier application [SQL Server], delete
- wizard [DAC], delete
- delete DAC
ms.assetid: 16fe1c18-4486-424d-81d6-d276ed97482f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 602256c287a8c7bcf9d3fa5597b2fec2085c626c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721489"
---
# <a name="delete-a-data-tier-application"></a><span data-ttu-id="f14b4-102">Löschen einer Datenebenenanwendung</span><span class="sxs-lookup"><span data-stu-id="f14b4-102">Delete a Data-tier Application</span></span>
  <span data-ttu-id="f14b4-103">Sie können eine Datenebenenanwendung entweder mit dem Assistenten zum Löschen von Datenebenenanwendungen oder mit einem Windows PowerShell-Skript löschen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-103">You can delete a data-tier application by using either the Delete Data-tier Application wizard or a Windows PowerShell script.</span></span> <span data-ttu-id="f14b4-104">Sie können angeben, ob die zugeordnete Datenbank beibehalten, getrennt oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="f14b4-104">You can specify whether the associated database is retained, detached, or dropped.</span></span>  
  
-   <span data-ttu-id="f14b4-105">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="f14b4-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="f14b4-106">**So aktualisieren Sie eine DAC:**  [dem Assistenten zum Registrieren von Datenschichtanwendungen](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="f14b4-106">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingDeleteDACWizard), [PowerShell](#DeleteDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f14b4-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f14b4-107">Before You Begin</span></span>  
 <span data-ttu-id="f14b4-108">Wenn Sie eine Instanz einer Datenebenenanwendung (Data-Tier Application, DAC) löschen, legen Sie mit einer von drei Optionen fest, wie mit der der Datenebenenanwendung zugeordneten Datenbank verfahren werden soll.</span><span class="sxs-lookup"><span data-stu-id="f14b4-108">When you delete a data-tier application (DAC) instance, you choose one of three options specifying what is to be done with the database associated with the data-tier application.</span></span> <span data-ttu-id="f14b4-109">Durch alle drei Optionen werden die Metadaten der DAC-Definition gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f14b4-109">All three options delete the DAC definition metadata.</span></span> <span data-ttu-id="f14b4-110">Die Optionen unterscheiden sich in der Art, wie mit der Datenbank, die der Datenebenenanwendung zugeordnet ist, verfahren wird.</span><span class="sxs-lookup"><span data-stu-id="f14b4-110">The options differ in what they do with the database associated with the data-tier application.</span></span> <span data-ttu-id="f14b4-111">Der Assistent löscht keine der Objekte auf Instanzebene, wie Anmeldenamen, die der DAC oder Datenbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f14b4-111">The wizard does not delete any of the instance-level objects associated with the DAC or database, such as logins.</span></span>  
  
|<span data-ttu-id="f14b4-112">Option</span><span class="sxs-lookup"><span data-stu-id="f14b4-112">Option</span></span>|<span data-ttu-id="f14b4-113">Datenbankaktionen</span><span class="sxs-lookup"><span data-stu-id="f14b4-113">Database actions</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="f14b4-114">Registrierung löschen</span><span class="sxs-lookup"><span data-stu-id="f14b4-114">Delete registration</span></span>|<span data-ttu-id="f14b4-115">Die zugeordnete Datenbank bleibt intakt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-115">The associated database remains intact.</span></span>|  
|<span data-ttu-id="f14b4-116">Datenbank trennen</span><span class="sxs-lookup"><span data-stu-id="f14b4-116">Detach database</span></span>|<span data-ttu-id="f14b4-117">Die zugeordnete Datenbank wird getrennt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-117">The associated database is detached.</span></span> <span data-ttu-id="f14b4-118">Die Instanz der Datenbank-Engine kann nicht auf die Datenbank verweisen, die Daten und Protokolldateien bleiben jedoch intakt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-118">The instance of the Database Engine cannot reference the database, but the data and log files are intact.</span></span>|  
|<span data-ttu-id="f14b4-119">Datenbank löschen</span><span class="sxs-lookup"><span data-stu-id="f14b4-119">Delete database</span></span>|<span data-ttu-id="f14b4-120">Die zugeordnete Datenbank wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f14b4-120">The associated database is dropped.</span></span> <span data-ttu-id="f14b4-121">Die Daten und Protokolldateien werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f14b4-121">The data and log files are deleted.</span></span>|  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="f14b4-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f14b4-122">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f14b4-123">Nach dem Löschen einer DAC gibt es keinen automatischen Mechanismus zum Wiederherstellen der Metadaten der DAC-Definition oder -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f14b4-123">There is no automatic mechanism to restore the DAC definition metadata or the database after you delete a DAC.</span></span> <span data-ttu-id="f14b4-124">Es hängt von der Löschoption ab, wie Sie die DAC-Instanz manuell neu erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f14b4-124">How you can manually rebuild the DAC instance depends on the delete option.</span></span>  
  
|<span data-ttu-id="f14b4-125">Option</span><span class="sxs-lookup"><span data-stu-id="f14b4-125">Option</span></span>|<span data-ttu-id="f14b4-126">Wiederherstellen der DAC-Instanz</span><span class="sxs-lookup"><span data-stu-id="f14b4-126">How to Rebuild the DAC Instance</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="f14b4-127">Registrierung löschen</span><span class="sxs-lookup"><span data-stu-id="f14b4-127">Delete registration</span></span>|<span data-ttu-id="f14b4-128">Registrieren Sie eine DAC von der Datenbank, die nicht gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="f14b4-128">Register a DAC from the database left in place.</span></span>|  
|<span data-ttu-id="f14b4-129">Datenbank trennen</span><span class="sxs-lookup"><span data-stu-id="f14b4-129">Detach database</span></span>|<span data-ttu-id="f14b4-130">Fügen Sie die Datenbank erneut mit **sp_attachdb** oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]an, und registrieren Sie anschließend eine neue DAC-Instanz von der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f14b4-130">Re-attach the database by using **sp_attachdb** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then register a new DAC instance from the database.</span></span>|  
|<span data-ttu-id="f14b4-131">Datenbank löschen</span><span class="sxs-lookup"><span data-stu-id="f14b4-131">Delete database</span></span>|<span data-ttu-id="f14b4-132">Stellen Sie die Datenbank von einer vollständigen Sicherung, die vor dem Löschen der DAC erstellt wurde, wieder her, und registrieren Sie dann eine neue DAC-Instanz von der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f14b4-132">Restore the database from a full backup made before the DAC was deleted, and then register a new DAC instance from the database.</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="f14b4-133">Wenn Sie eine DAC-Instanz wiederherstellen, indem Sie eine DAC von einer wiederhergestellten oder erneut angefügten Datenbank registrieren, werden einige Teile der ursprünglichen DAC, z. B. die Richtlinie zur Serverauswahl, nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-133">Rebuilding a DAC instance by registering a DAC from a restored or re-attached database will not recreate some parts of the original DAC, such as the server selection policy.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f14b4-134">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f14b4-134">Permissions</span></span>  
 <span data-ttu-id="f14b4-135">Eine DAC kann nur von Mitgliedern der festen Serverrollen **sysadmin** bzw. **serveradmin** oder vom Datenbankbesitzer gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f14b4-135">A DAC can only be deleted by members of the **sysadmin** or **serveradmin** fixed server roles, or by the database owner.</span></span> <span data-ttu-id="f14b4-136">Außerdem kann das integrierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Systemadministratorkonto mit der Bezeichnung **sa** zum Starten des Assistenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f14b4-136">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also launch the wizard.</span></span>  
  
##  <a name="using-the-delete-data-tier-application-wizard"></a><a name="UsingDeleteDACWizard"></a> <span data-ttu-id="f14b4-137">Verwenden des Assistenten zum Löschen von Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="f14b4-137">Using the Delete Data-tier Application Wizard</span></span>  
 <span data-ttu-id="f14b4-138">**So löschen Sie eine DAC mithilfe eines Assistenten**</span><span class="sxs-lookup"><span data-stu-id="f14b4-138">**To Delete a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="f14b4-139">Erweitern Sie im **Objekt-Explorer**den Knoten für die Instanz, die die zu löschende DAC enthält.</span><span class="sxs-lookup"><span data-stu-id="f14b4-139">In **Object Explorer**, expand the node for the instance containing the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="f14b4-140">Erweitern Sie den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="f14b4-140">Expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="f14b4-141">Erweitern Sie den Knoten **Datenebenenanwendungen** .</span><span class="sxs-lookup"><span data-stu-id="f14b4-141">Expand the **Data-tier Applications** node.</span></span>  
  
4.  <span data-ttu-id="f14b4-142">Klicken Sie mit der rechten Maustaste auf die zu löschende DAC, und wählen Sie anschließend **Datenebenenanwendung löschen...** aus.</span><span class="sxs-lookup"><span data-stu-id="f14b4-142">Right-click the DAC to be deleted, and then select **Delete Data-tier Application...**</span></span>  
  
5.  <span data-ttu-id="f14b4-143">Bearbeiten Sie die Dialogfenster des Assistenten:</span><span class="sxs-lookup"><span data-stu-id="f14b4-143">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="f14b4-144">Einführung</span><span class="sxs-lookup"><span data-stu-id="f14b4-144">Introduction</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="f14b4-145">Methode auswählen</span><span class="sxs-lookup"><span data-stu-id="f14b4-145">Choose Method</span></span>](#Choose_method)  
  
    3.  [<span data-ttu-id="f14b4-146">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="f14b4-146">Summary</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="f14b4-147">Datenebenenanwendung löschen</span><span class="sxs-lookup"><span data-stu-id="f14b4-147">Delete Data-tier Application</span></span>](#Delete_datatier_application)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="f14b4-148">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="f14b4-148">Introduction Page</span></span>  
 <span data-ttu-id="f14b4-149">Auf dieser Seite werden die Schritte zum Löschen einer Datenebenenanwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f14b4-149">This page describes the steps for deleting a data-tier application.</span></span>  
  
 <span data-ttu-id="f14b4-150">**Diese Seite nicht mehr anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="f14b4-150">**Do not show this page again.**</span></span> <span data-ttu-id="f14b4-151">– Aktivieren Sie dieses Kontrollkästchen, damit die Seite in Zukunft nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f14b4-151">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="f14b4-152">**Weiter >** – Geht zur Seite **Methode auswählen** über.</span><span class="sxs-lookup"><span data-stu-id="f14b4-152">**Next >** - Proceeds to the **Choose Method** page.</span></span>  
  
 <span data-ttu-id="f14b4-153">**Abbrechen** – Beendet den Assistenten, ohne eine Datenebenenanwendung oder Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-153">**Cancel** - Ends the wizard without deleting a data-tier application or database.</span></span>  
  
##  <a name="choose-method-page"></a><a name="Choose_method"></a> <span data-ttu-id="f14b4-154">Seite "Methode auswählen"</span><span class="sxs-lookup"><span data-stu-id="f14b4-154">Choose Method Page</span></span>  
 <span data-ttu-id="f14b4-155">Auf dieser Seite können Sie die Option zum Behandeln der der zu löschenden DAC zugeordneten Datenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="f14b4-155">Use this page to specify the option for handling the database associated with the DAC to be deleted.</span></span>  
  
 <span data-ttu-id="f14b4-156">**Registrierung löschen** – Entfernt die Metadaten, die die Datenebenenanwendung definieren, während die zugeordnete Datenbank intakt bleibt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-156">**Delete registration** - Removes the metadata defining the data-tier application, but leaves the associated database intact.</span></span>  
  
 <span data-ttu-id="f14b4-157">**Datenbank trennen** – Entfernt die Metadaten, die die Datenebenenanwendung definieren, und trennt die zugeordnete Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f14b4-157">**Detach database** - Removes the metadata defining the data-tier application and detaches the associated database.</span></span>  
  
 <span data-ttu-id="f14b4-158">Von dieser [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz kann nicht mehr auf die Datenbank verwiesen werden, während die Daten und Protokolldateien jedoch intakt bleiben.</span><span class="sxs-lookup"><span data-stu-id="f14b4-158">The database can no longer be referenced by that instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], but the data and log files remain intact.</span></span>  
  
 <span data-ttu-id="f14b4-159">**Datenbank löschen** – Entfernt die Metadaten, die die DAC definieren, und löscht die zugeordnete Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f14b4-159">**Delete database** - Removes the metadata defining the DAC and drops the associated database.</span></span>  
  
 <span data-ttu-id="f14b4-160">Die Daten und Protokolldateien für die Datenbank werden dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f14b4-160">The data and log files for the database are permanently deleted.</span></span>  
  
 <span data-ttu-id="f14b4-161">\*\* \< Previous\*\* : kehrt zur **Einführungs** Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="f14b4-161">**\< Previous** - Returns to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="f14b4-162">**Weiter >**: Geht zur Seite **Zusammenfassung** über.</span><span class="sxs-lookup"><span data-stu-id="f14b4-162">**Next >** - Proceeds to the **Summary** page.</span></span>  
  
 <span data-ttu-id="f14b4-163">**Abbrechen** – Beendet den Assistenten, ohne die DAC oder Datenbank zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-163">**Cancel** - Ends the wizard without deleting the DAC or database.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="f14b4-164">Seite "Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="f14b4-164">Summary Page</span></span>  
 <span data-ttu-id="f14b4-165">Verwenden Sie diese Seite, um die Aktionen zu überprüfen, die der Assistent beim Löschen der DAC-Instanz ausführt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-165">Use this page to review the actions the wizard will take when deleting the DAC instance.</span></span>  
  
 <span data-ttu-id="f14b4-166">**Überprüfen Sie Ihre Auswahl** – Überprüfen Sie die DAC, Datenbank und Löschmethode, die im Feld angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f14b4-166">**Review your selection summary** - Review the DAC, database, and deletion method displayed in the box.</span></span> <span data-ttu-id="f14b4-167">Wenn die Informationen richtig sind, wählen Sie entweder **Weiter** oder **Fertig stellen** aus, um die DAC zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-167">If the information is correct, select either **Next** or **Finish** to delete the DAC.</span></span> <span data-ttu-id="f14b4-168">Falls die DAC und die Datenbankinformationen nicht richtig sind, klicken Sie auf **Abbrechen** und wählen dann die richtige DAC aus.</span><span class="sxs-lookup"><span data-stu-id="f14b4-168">If the DAC and database information is not correct, select **Cancel** and select the correct DAC.</span></span> <span data-ttu-id="f14b4-169">Wenn die Löschmethode nicht richtig ist, wählen Sie **Zurück** aus, um zur Seite **Methode auswählen** zurückzukehren, und wählen eine andere Methode aus.</span><span class="sxs-lookup"><span data-stu-id="f14b4-169">If the deletion method is not correct, select **Previous** to return to the **Choose Method** page and select a different method.</span></span>  
  
 <span data-ttu-id="f14b4-170">\*\* \< Previous\*\* : kehrt zur Seite **Methode auswählen** zurück, um eine andere Löschmethode auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-170">**\< Previous** - Returns to the **Choose Method** page to choose a different delete method.</span></span>  
  
 <span data-ttu-id="f14b4-171">**Weiter >** – Löscht die DAC-Instanz unter Verwendung der auf der vorherigen Seite ausgewählten Methode und geht zur Seite **Datenebenenanwendung löschen** über.</span><span class="sxs-lookup"><span data-stu-id="f14b4-171">**Next >** - Deletes the DAC instance using the method you chose on the previous page, and proceeds to the **Delete Data-tier Application** page.</span></span>  
  
 <span data-ttu-id="f14b4-172">**Abbrechen** – Beendet den Assistenten, ohne die DAC-Instanz zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-172">**Cancel** - Ends the wizard without deleting the DAC instance.</span></span>  
  
##  <a name="delete-data-tier-application-page"></a><a name="Delete_datatier_application"></a><span data-ttu-id="f14b4-173">Seite "Datenebenenanwendung löschen"</span><span class="sxs-lookup"><span data-stu-id="f14b4-173">Delete Data-tier Application Page</span></span>  
 <span data-ttu-id="f14b4-174">Auf dieser Seite wird angegeben, ob der Löschvorgang erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="f14b4-174">This page reports the success or failure of the delete operation.</span></span>  
  
 <span data-ttu-id="f14b4-175">**Die DAC wird gelöscht** – Gibt an, ob die Aktionen zum Löschen der DAC-Instanz erfolgreich waren oder fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="f14b4-175">**Deleting the DAC** - Reports the success or failure of each action taken to delete the DAC instance.</span></span> <span data-ttu-id="f14b4-176">Überprüfen Sie die Informationen, um zu bestimmen, ob die einzelnen Aktionen erfolgreich waren oder fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="f14b4-176">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="f14b4-177">Für alle Aktionen, die fehlerhaft waren, ist in der Spalte **Ergebnis** ein Link enthalten.</span><span class="sxs-lookup"><span data-stu-id="f14b4-177">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="f14b4-178">Klicken Sie auf den Link, um einen Bericht des für diese Aktion aufgetretenen Fehlers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-178">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="f14b4-179">**Bericht speichern** – Klicken Sie auf diese Schaltfläche, um den Löschbericht in einer HTML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f14b4-179">**Save Report** - Select this button to save the deletion report to an HTML file.</span></span> <span data-ttu-id="f14b4-180">In der Datei ist der Status der einzelnen Aktionen aufgeführt, einschließlich aller durch die Aktionen generierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="f14b4-180">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="f14b4-181">Der Standardordner entspricht dem Ordner "SQL Server Management Studio\DAC Packages" im Ordner "Dokumente" unter Ihrem Windows-Konto.</span><span class="sxs-lookup"><span data-stu-id="f14b4-181">The default folder is a SQL Server Management Studio\DAC Packages folder in the Documents folder of your Windows account..</span></span>  
  
 <span data-ttu-id="f14b4-182">**Fertig stellen** – Beendet den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="f14b4-182">**Finish** - Ends the wizard.</span></span>  
  
##  <a name="delete-a-dac-using-powershell"></a><a name="DeleteDACPowerShell"></a><span data-ttu-id="f14b4-183">Löschen einer DAC mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="f14b4-183">Delete a DAC Using PowerShell</span></span>  
 <span data-ttu-id="f14b4-184">**So löschen Sie eine DAC mit einem PowerShell-Skript**</span><span class="sxs-lookup"><span data-stu-id="f14b4-184">**To delete a DAC using a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="f14b4-185">Erstellen Sie ein SMO-Serverobjekt, und legen Sie es auf die Instanz fest, die die zu löschende DAC enthält.</span><span class="sxs-lookup"><span data-stu-id="f14b4-185">Create a SMO Server object and set it to the instance that contains the DAC to be deleted.</span></span>  
  
2.  <span data-ttu-id="f14b4-186">Öffnen Sie ein `ServerConnection`-Objekt, und stellen Sie eine Verbindung mit derselben Instanz her.</span><span class="sxs-lookup"><span data-stu-id="f14b4-186">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="f14b4-187">Verwenden Sie `add_DacActionStarted` und `add_DacActionFinished`, um die DAC-Aktualisierungsereignisse zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="f14b4-187">Use `add_DacActionStarted` and `add_DacActionFinished` to subscribe to the DAC upgrade events.</span></span>  
  
4.  <span data-ttu-id="f14b4-188">Geben Sie die zu löschende DAC an.</span><span class="sxs-lookup"><span data-stu-id="f14b4-188">Specify the DAC to delete.</span></span>  
  
5.  <span data-ttu-id="f14b4-189">Verwenden Sie je nach geeigneter Löschoption einen dieser drei Codesätze:</span><span class="sxs-lookup"><span data-stu-id="f14b4-189">Use one of these three sets of code, depending on which delete option is appropriate:</span></span>  
  
    -   <span data-ttu-id="f14b4-190">Verwenden Sie die `Unmanage()`-Methode, um die DAC-Registrierung zu löschen, während die Datenbank intakt bleibt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-190">To delete the DAC registration but leave the database intact, use the `Unmanage()` method.</span></span>  
  
    -   <span data-ttu-id="f14b4-191">Verwenden Sie die `Uninstall()`-Methode, und geben Sie `DetachDatabase` an, um die DAC-Registrierung zu löschen und die Datenbank zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-191">To delete the DAC registration and detach the database, use the `Uninstall()` method and specify `DetachDatabase`.</span></span>  
  
    -   <span data-ttu-id="f14b4-192">Verwenden Sie die `Uninstall()`-Methode, und geben Sie `DropDatabase` an, um die DAC-Registrierung zu löschen und die Datenbank zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f14b4-192">To delete the DAC registration and drop the database, use the `Uninstall()` method and specify `DropDatabase`.</span></span>  
  
### <a name="example-deleting-the-dac-but-leaving-the-database-powershell"></a><span data-ttu-id="f14b4-193">Beispiel für das Löschen der DAC und Belassen der Datenbank (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f14b4-193">Example Deleting the DAC but Leaving the Database (PowerShell)</span></span>  
 <span data-ttu-id="f14b4-194">Im folgenden Beispiel wird die DAC MyApplication mithilfe der `Unmanage()`-Methode gelöscht. Dabei wird die DAC gelöscht, die Datenbank bleibt jedoch intakt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-194">The following example deletes a DAC named MyApplication using the `Unmanage()` method to delete the DAC but leave the database intact.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Only delete the DAC definition from msdb, the associated database remains active.  
$dacstore.Unmanage($dacName)  
```  
  
### <a name="example-deleting-the-dac-and-detaching-the-database-powershell"></a><span data-ttu-id="f14b4-195">Beispiel für das Löschen einer DAC und Trennen der Datenbank (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f14b4-195">Example Deleting the DAC and Detaching the Database (PowerShell)</span></span>  
 <span data-ttu-id="f14b4-196">Im folgenden Beispiel wird die DAC MyApplication mithilfe der `Uninstall()`-Methode gelöscht und die Datenbank getrennt.</span><span class="sxs-lookup"><span data-stu-id="f14b4-196">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and detach the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = get-item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and detach the associated database.  
$dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DetachDatabase)  
```  
  
### <a name="example-deleting-the-dac-and-dropping-the-database-powershell"></a><span data-ttu-id="f14b4-197">Beispiel für das Löschen einer DAC und Löschen der Datenbank (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="f14b4-197">Example Deleting the DAC and Dropping the Database (PowerShell)</span></span>  
 <span data-ttu-id="f14b4-198">Im folgenden Beispiel wird die DAC MyApplication mithilfe der `Uninstall()`-Methode gelöscht. Die Datenbank wird ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f14b4-198">The following example deletes a DAC named MyApplication using the `Uninstall()` method to delete the DAC and drop the database.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Subscribe to the DAC delete events.  
$dacstore.add_DacActionStarted({Write-Host `n`nStarting at $(get-date) :: $_.Description})  
$dacstore.add_DacActionFinished({Write-Host Completed at $(get-date) :: $_.Description})  
  
## Specify the DAC to delete.  
$dacName  = "MyApplication"  
  
## Delete the DAC definition from msdb and drop the associated database.  
## $dacstore.Uninstall($dacName, [Microsoft.SqlServer.Management.Dac.DacUninstallMode]::DropDatabase)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f14b4-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f14b4-199">See Also</span></span>  
 <span data-ttu-id="f14b4-200">[Datenebenenanwendungen](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f14b4-200">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="f14b4-201">[Datenebenenanwendungen](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f14b4-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="f14b4-202">[Bereitstellen einer Datenebenenanwendung](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="f14b4-202">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="f14b4-203">[Registrieren einer Datenbank als DAC](register-a-database-as-a-dac.md) </span><span class="sxs-lookup"><span data-stu-id="f14b4-203">[Register a Database As a DAC](register-a-database-as-a-dac.md) </span></span>  
 <span data-ttu-id="f14b4-204">[Sichern und Wiederherstellen von SQL Server-Datenbanken](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="f14b4-204">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="f14b4-205">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f14b4-205">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
