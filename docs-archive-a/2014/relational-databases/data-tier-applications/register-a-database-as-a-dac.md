---
title: Registrieren einer Datenbank als eine DAC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerdacwizard.registerdac.f1
- sql12.swb.registerdacwizard.summary.f1
- sql12.swb.registerdacwizard.introduction.f1
- sql12.swb.registerdacwizard.setproperties.f1
helpviewer_keywords:
- wizard [DAC], register
- How to [DAC], register
- register DAC
- data-tier application [SQL Server], register
ms.assetid: 08e52aa6-12f3-41dd-a793-14b99a083fd5
author: stevestein
ms.author: sstein
ms.openlocfilehash: c4e8061362d013dbfbd6cbaba47d0f2cb4d8e83b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622680"
---
# <a name="register-a-database-as-a-dac"></a><span data-ttu-id="4fc94-102">Registrieren einer Datenbank als eine DAC</span><span class="sxs-lookup"><span data-stu-id="4fc94-102">Register a Database As a DAC</span></span>
  <span data-ttu-id="4fc94-103">Verwenden Sie entweder den **Assistenten zum Registrieren von Datenebenenanwendungen** oder ein Windows PowerShell-Skript, um eine Definition für eine Datenebenenanwendung (DAC) zu erstellen, in der die Objekte in einer vorhandenen Datenbank beschrieben werden, und registrieren Sie die DAC-Definition in der `msdb` Systemdatenbank (**Master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="4fc94-103">Use either the **Register Data-tier Application Wizard** or a Windows PowerShell script to build a data-tier application (DAC) definition that describes the objects in an existing database, and register the DAC definition in the `msdb` system database (**master** in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)]).</span></span>  
  
-   <span data-ttu-id="4fc94-104">**Vorbereitungen:**  [Begrenzungen und Einschränkungen](#LimitationsRestrictions), [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4fc94-104">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="4fc94-105">**So aktualisieren Sie eine DAC:**  [dem Assistenten zum Registrieren von Datenschichtanwendungen](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span><span class="sxs-lookup"><span data-stu-id="4fc94-105">**To upgrade a DAC, using:**  [The Register Data-tier Application Wizard](#UsingRegisterDACWizard), [PowerShell](#RegisterDACPowerShell)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="4fc94-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4fc94-106">Before You Begin</span></span>  
 <span data-ttu-id="4fc94-107">Beim Registrierungsprozess wird eine DAC-Definition erstellt, die die Objekte in der Datenbank definiert.</span><span class="sxs-lookup"><span data-stu-id="4fc94-107">The registration process creates a DAC definition that defines the objects in the database.</span></span> <span data-ttu-id="4fc94-108">Eine DAC-Instanz setzt sich aus der Kombination von DAC-Definition und Datenbank zusammen.</span><span class="sxs-lookup"><span data-stu-id="4fc94-108">The combination of the DAC definition and the database form a DAC instance.</span></span> <span data-ttu-id="4fc94-109">Bei der Registrierung einer Datenbank als DAC in einer verwalteten Instanz der Datenbank-Engine wird die registrierte DAC in das SQL Server-Hilfsprogramm integriert, wenn der Hilfsprogramm-Sammlungssatz das nächste Mal von der Instanz an den Steuerungspunkt für das Hilfsprogramm gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4fc94-109">If you register a database as a DAC on a managed instance of the Database Engine, the registered DAC will be incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the Utility Control Point.</span></span> <span data-ttu-id="4fc94-110">Die DAC ist dann im Knoten **Bereitgestellte Datenebenenanwendungen** im [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]Hilfsprogramm-Explorer**von** vorhanden und wird auf der Detailseite **Bereitgestellte Datenebenenanwendungen** aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4fc94-110">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="4fc94-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4fc94-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4fc94-112">Die DAC-Registrierung kann nur für eine Datenbank in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]oder [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fc94-112">DAC registration can only be performed on a database in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="4fc94-113">Die DAC-Registrierung ist nicht möglich, wenn eine DAC bereits für die Datenbank registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4fc94-113">DAC registration cannot be performed if a DAC is already registered for the database.</span></span> <span data-ttu-id="4fc94-114">Wenn die Datenbank durch Bereitstellung einer DAC erstellt wurde, kann der **Assistent zum Registrieren von Datenschichtanwendungen**beispielsweise nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fc94-114">For example, if the database was created by deploying a DAC, you cannot run the **Register Data-tier Application Wizard**.</span></span>  
  
 <span data-ttu-id="4fc94-115">Es kann keine DAC registriert werden, wenn die Datenbank Objekte, die in einer DAC nicht unterstützt werden, oder enthaltene Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="4fc94-115">You cannot register a DAC if the database has objects that are not supported in a DAC, or contained users.</span></span> <span data-ttu-id="4fc94-116">Weitere Informationen zu den in einer DAC unterstützten Objekttypen finden Sie unter [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span><span class="sxs-lookup"><span data-stu-id="4fc94-116">For more information about the types of objects supported in a DAC, see [DAC Support For SQL Server Objects and Versions](dac-support-for-sql-server-objects-and-versions.md).</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fc94-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4fc94-117">Permissions</span></span>  
 <span data-ttu-id="4fc94-118">Zum Registrieren einer DAC in einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] sind mindestens die ALTER ANY LOGIN-Berechtigung und die VIEW DEFINITION-Berechtigung im Datenbankbereich sowie SELECT-Berechtigungen für **sys.sql_expression_dependencies**und die Mitgliedschaft in der festen Serverrolle **dbcreator** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4fc94-118">Registering a DAC in an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] requires at least ALTER ANY LOGIN and database scope VIEW DEFINITION permissions, SELECT permissions on **sys.sql_expression_dependencies**, and membership in the **dbcreator** fixed server role.</span></span> <span data-ttu-id="4fc94-119">Mitglieder der festen Serverrolle **sysadmin** oder des integrierten SQL Server-Systemadministratorkontos **sa** sind ebenfalls zum Registrieren einer DAC berechtigt.</span><span class="sxs-lookup"><span data-stu-id="4fc94-119">Members of the **sysadmin** fixed server role or the built-in SQL Server system administrator account named **sa** can also register a DAC.</span></span> <span data-ttu-id="4fc94-120">Zum Registrieren einer DAC, die keine Anmeldungen in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] enthält, müssen Sie Mitglied der Rollen **dbmanager** oder **serveradmin** sein.</span><span class="sxs-lookup"><span data-stu-id="4fc94-120">Registering a DAC that does not contain logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **dbmanager** or **serveradmin** roles.</span></span> <span data-ttu-id="4fc94-121">Zum Registrieren einer DAC, die Anmeldungen in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] enthält, müssen Sie Mitglied der Rollen **loginmanager** oder **serveradmin** sein.</span><span class="sxs-lookup"><span data-stu-id="4fc94-121">Registering a DAC that contains logins in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the **loginmanager** or **serveradmin** roles.</span></span>  
  
##  <a name="using-the-register-data-tier-application-wizard"></a><a name="UsingRegisterDACWizard"></a> <span data-ttu-id="4fc94-122">Verwenden des Assistenten zum Registrieren von Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="4fc94-122">Using the Register Data-tier Application Wizard</span></span>  
 <span data-ttu-id="4fc94-123">**So registrieren Sie eine DAC mithilfe eines Assistenten**</span><span class="sxs-lookup"><span data-stu-id="4fc94-123">**To Register a DAC Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="4fc94-124">Erweitern Sie im **Objekt-Explorer**den Knoten für die Instanz, die die Datenbank enthält, die als DAC registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4fc94-124">In **Object Explorer**, expand the node for the instance containing the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="4fc94-125">Erweitern Sie den Knoten **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="4fc94-125">Expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="4fc94-126">Klicken Sie mit der rechten Maustaste auf die zu registrierende Datenbank, zeigen Sie auf **Tasks**, und wählen Sie dann **Als Datenschichtanwendung registrieren…** aus.</span><span class="sxs-lookup"><span data-stu-id="4fc94-126">Right-click the database to be registered, point to **Tasks**, and then select **Register As Data-tier Application...**</span></span>  
  
4.  <span data-ttu-id="4fc94-127">Bearbeiten Sie die Dialogfenster des Assistenten:</span><span class="sxs-lookup"><span data-stu-id="4fc94-127">Complete the wizard dialogs:</span></span>  
  
    1.  [<span data-ttu-id="4fc94-128">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="4fc94-128">Introduction Page</span></span>](#Introduction)  
  
    2.  [<span data-ttu-id="4fc94-129">Seite "Eigenschaften festlegen"</span><span class="sxs-lookup"><span data-stu-id="4fc94-129">Set Properties Page</span></span>](#Set_properties)  
  
    3.  [<span data-ttu-id="4fc94-130">Seite "Überprüfung und Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="4fc94-130">Validation and Summary Page</span></span>](#Summary)  
  
    4.  [<span data-ttu-id="4fc94-131">Seite "DAC registrieren"</span><span class="sxs-lookup"><span data-stu-id="4fc94-131">Register DAC Page</span></span>](#Register)  
  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="4fc94-132">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="4fc94-132">Introduction Page</span></span>  
 <span data-ttu-id="4fc94-133">Auf dieser Seite werden die Schritte zum Registrieren einer Datenebenenanwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fc94-133">This page describes the steps for registering a data-tier application.</span></span>  
  
 <span data-ttu-id="4fc94-134">**Diese Seite nicht mehr anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="4fc94-134">**Do not show this page again.**</span></span> <span data-ttu-id="4fc94-135">– Aktivieren Sie dieses Kontrollkästchen, damit die Seite in Zukunft nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4fc94-135">- Click the check box to stop the page from being displayed in the future.</span></span>  
  
 <span data-ttu-id="4fc94-136">**Weiter >** – Geht zur Seite **Eigenschaften festlegen** über.</span><span class="sxs-lookup"><span data-stu-id="4fc94-136">**Next >** - Proceeds to the **Set Properties** page.</span></span>  
  
 <span data-ttu-id="4fc94-137">**Abbrechen** – Beendet den Assistenten, ohne eine DAC zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4fc94-137">**Cancel** - Terminates the wizard without registering a DAC.</span></span>  
  
##  <a name="set-properties-page"></a><a name="Set_properties"></a> <span data-ttu-id="4fc94-138">Seite "Eigenschaften festlegen"</span><span class="sxs-lookup"><span data-stu-id="4fc94-138">Set Properties Page</span></span>  
 <span data-ttu-id="4fc94-139">Verwenden Sie diese Seite, um Eigenschaften auf DAC-Ebene anzugeben, z. B. den Anwendungsnamen und die Version.</span><span class="sxs-lookup"><span data-stu-id="4fc94-139">Use this page to specify DAC-level properties such as the application name and version.</span></span>  
  
 <span data-ttu-id="4fc94-140">**Anwendungsname**</span><span class="sxs-lookup"><span data-stu-id="4fc94-140">**Application name.**</span></span> <span data-ttu-id="4fc94-141">– Eine Zeichenfolge mit dem Namen, der die DAC-Definition identifiziert. Das Feld enthält den Namen der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4fc94-141">- A string that specifies the name used to identify the DAC definition, the field is been populated with the database name.</span></span>  
  
 <span data-ttu-id="4fc94-142">**Version**.</span><span class="sxs-lookup"><span data-stu-id="4fc94-142">**Version.**</span></span> <span data-ttu-id="4fc94-143">– Ein numerischer Wert, der die Version der DAC identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4fc94-143">- A numeric value that identifies the version of the DAC.</span></span> <span data-ttu-id="4fc94-144">Die DAC-Version wird in Visual Studio verwendet, um die Version der DAC zu identifizieren, an der die Entwickler arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4fc94-144">The DAC version is used in Visual Studio to identify the version of the DAC that developers are working on.</span></span> <span data-ttu-id="4fc94-145">Beim Bereitstellen einer DAC wird die Version in der `msdb` -Datenbank gespeichert und kann später unter dem Knoten **Datenebenenanwendungen** in angezeigt werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fc94-145">When deploying a DAC, the version is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4fc94-146">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4fc94-146">**Description.**</span></span> <span data-ttu-id="4fc94-147">– Optional.</span><span class="sxs-lookup"><span data-stu-id="4fc94-147">- Optional.</span></span> <span data-ttu-id="4fc94-148">Ein Text, der den Zweck der DAC erläutert.</span><span class="sxs-lookup"><span data-stu-id="4fc94-148">Text that explains the purpose of the DAC.</span></span> <span data-ttu-id="4fc94-149">Beim Bereitstellen einer DAC wird die Beschreibung in der `msdb` -Datenbank gespeichert und kann später unter dem Knoten **Datenebenenanwendungen** in angezeigt werden [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fc94-149">When deploying a DAC, the description is stored in the `msdb` database and can later be viewed under the **Data-tier Applications** node in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="4fc94-150">Zurück \*\* \< : kehrt\*\* zur **Einführungs** Seite zurück.</span><span class="sxs-lookup"><span data-stu-id="4fc94-150">**\< Previous** - Returns you to the **Introduction** page.</span></span>  
  
 <span data-ttu-id="4fc94-151">**Weiter >** – Überprüft, ob eine DAC aus den in der Datenbank enthaltenen Objekten erstellt werden kann, und zeigt die Ergebnisse auf der Seite **Überprüfung und Zusammenfassung** an.</span><span class="sxs-lookup"><span data-stu-id="4fc94-151">**Next >** - Verifies that a DAC can be built from the objects in the database, and displays the results in the **Validation and Summary** page.</span></span>  
  
 <span data-ttu-id="4fc94-152">**Abbrechen** – Beendet den Assistenten, ohne die DAC zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4fc94-152">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="validation-and-summary-page"></a><a name="Summary"></a> <span data-ttu-id="4fc94-153">Seite "Überprüfung und Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="4fc94-153">Validation and Summary Page</span></span>  
 <span data-ttu-id="4fc94-154">Verwenden Sie diese Seite, um die Aktionen zu überprüfen, die der Assistent beim Registrieren der DAC ausführt.</span><span class="sxs-lookup"><span data-stu-id="4fc94-154">Use this page to review the actions the wizard will take when registering the DAC.</span></span> <span data-ttu-id="4fc94-155">Die Seite durchläuft drei Statusübergänge, während überprüft wird, ob eine DAC aus den in der Datenbank enthaltenen Objekten erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4fc94-155">The page transitions through three states as it verifies that a DAC can be built from the objects in the database.</span></span>  
  
### <a name="retrieving-objects"></a><span data-ttu-id="4fc94-156">Abrufen von Objekten</span><span class="sxs-lookup"><span data-stu-id="4fc94-156">Retrieving Objects</span></span>  
 <span data-ttu-id="4fc94-157">**Datenbank- und Serverobjekte werden abgerufen.**</span><span class="sxs-lookup"><span data-stu-id="4fc94-157">**Retrieving database and server objects.**</span></span> <span data-ttu-id="4fc94-158">– Zeigt eine Statusanzeige an, während der Assistent alle erforderlichen Objekte aus der Datenbank und der Instanz der Datenbank-Engine abruft.</span><span class="sxs-lookup"><span data-stu-id="4fc94-158">- Displays a progress bar as the wizard retrieves all of the required objects from the database and the instance of the Database Engine.</span></span>  
  
 <span data-ttu-id="4fc94-159">Zurück \*\* \< : kehrt\*\* zur Seite **Eigenschaften festlegen** zurück, um die Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4fc94-159">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="4fc94-160">**Weiter >** – Registriert die DAC und zeigt die Ergebnisse auf der Seite **DAC registrieren** an.</span><span class="sxs-lookup"><span data-stu-id="4fc94-160">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="4fc94-161">**Abbrechen** – Beendet den Assistenten, ohne die DAC zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4fc94-161">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="validating-objects"></a><span data-ttu-id="4fc94-162">Überprüfen von Objekten</span><span class="sxs-lookup"><span data-stu-id="4fc94-162">Validating Objects</span></span>  
 <span data-ttu-id="4fc94-163">**Überprüft:** _SchemaName_ **.**</span><span class="sxs-lookup"><span data-stu-id="4fc94-163">**Checking**  _SchemaName_ **.**</span></span> <span data-ttu-id="4fc94-164">_ObjectName_ **.**</span><span class="sxs-lookup"><span data-stu-id="4fc94-164">_ObjectName_ **.**</span></span> <span data-ttu-id="4fc94-165">– Zeigt eine Statusanzeige an, während der Assistent die Abhängigkeiten der abgerufenen Objekten überprüft und sicherstellt, dass sie alle für eine DAC gültig sind.</span><span class="sxs-lookup"><span data-stu-id="4fc94-165">- Displays a progress bar as the wizard verifies the dependencies of the retrieved objects, and verifies that they are all valid objects for a DAC.</span></span> <span data-ttu-id="4fc94-166">_SchemaName_ **.** _ObjectName_ gibt das derzeit überprüfte Objekt an.</span><span class="sxs-lookup"><span data-stu-id="4fc94-166">_SchemaName_**.**_ObjectName_ identify which object is currently being verified.</span></span>  
  
 <span data-ttu-id="4fc94-167">Zurück \*\* \< : kehrt\*\* zur Seite **Eigenschaften festlegen** zurück, um die Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4fc94-167">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="4fc94-168">**Weiter >** – Registriert die DAC und zeigt die Ergebnisse auf der Seite **DAC registrieren** an.</span><span class="sxs-lookup"><span data-stu-id="4fc94-168">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="4fc94-169">**Abbrechen** – Beendet den Assistenten, ohne die DAC zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4fc94-169">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
### <a name="summary"></a><span data-ttu-id="4fc94-170">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4fc94-170">Summary</span></span>  
 <span data-ttu-id="4fc94-171">**Die folgende Einstellung wird verwendet, um die DAC zu registrieren.**</span><span class="sxs-lookup"><span data-stu-id="4fc94-171">**The following setting will be used to register your DAC.**</span></span> <span data-ttu-id="4fc94-172">– Zeigt einen Bericht der Eigenschaften und Objekte an, die in der DAC enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4fc94-172">- Displays a report of the properties and objects that will be included in the DAC.</span></span>  
  
 <span data-ttu-id="4fc94-173">**Bericht speichern** – Klicken Sie auf diese Schaltfläche, um eine Kopie des Überprüfungsberichts in einer HTML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4fc94-173">**Save Report** - Select this button to save a copy of the validation report to an HTML file.</span></span> <span data-ttu-id="4fc94-174">Der Standardordner ist ein Ordner **SQL Server Management Studio\DAC Packages** im Ordner „Dokumente“ unter Ihrem Windows-Konto.</span><span class="sxs-lookup"><span data-stu-id="4fc94-174">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span>  
  
 <span data-ttu-id="4fc94-175">Zurück \*\* \< : kehrt\*\* zur Seite **Eigenschaften festlegen** zurück, um die Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4fc94-175">**\< Previous** - Returns you to the **Set Properties** page to change your entries.</span></span>  
  
 <span data-ttu-id="4fc94-176">**Weiter >** – Registriert die DAC und zeigt die Ergebnisse auf der Seite **DAC registrieren** an.</span><span class="sxs-lookup"><span data-stu-id="4fc94-176">**Next >** - Registers the DAC and displays the results in the **Register DAC** page.</span></span>  
  
 <span data-ttu-id="4fc94-177">**Abbrechen** – Beendet den Assistenten, ohne die DAC zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4fc94-177">**Cancel** - Terminates the wizard without registering the DAC.</span></span>  
  
##  <a name="register-dac-page"></a><a name="Register"></a> <span data-ttu-id="4fc94-178">Seite "DAC registrieren"</span><span class="sxs-lookup"><span data-stu-id="4fc94-178">Register DAC Page</span></span>  
 <span data-ttu-id="4fc94-179">Auf dieser Seite wird angegeben, ob der Registrierungsvorgang erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="4fc94-179">This page reports the success or failure of the registration.</span></span>  
  
 <span data-ttu-id="4fc94-180">**Die DAC wird registriert** – Gibt an, ob die einzelnen Aktionen zum Registrieren der DAC erfolgreich waren oder ob ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4fc94-180">**Registering the DAC** - Reports the success or failure of each action taken to register the DAC.</span></span> <span data-ttu-id="4fc94-181">Überprüfen Sie die Informationen, um zu bestimmen, ob die einzelnen Aktionen erfolgreich waren oder fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="4fc94-181">Review the information to determine the success or failure of each action.</span></span> <span data-ttu-id="4fc94-182">Für alle Aktionen, die fehlerhaft waren, ist in der Spalte **Ergebnis** ein Link enthalten.</span><span class="sxs-lookup"><span data-stu-id="4fc94-182">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="4fc94-183">Klicken Sie auf den Link, um einen Bericht des für diese Aktion aufgetretenen Fehlers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4fc94-183">Select the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="4fc94-184">**Bericht speichern** – Klicken Sie auf diese Schaltfläche, um den Registrierungsbericht in einer HTML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4fc94-184">**Save Report** - Select this button to save the registration report to an HTML file.</span></span> <span data-ttu-id="4fc94-185">In der Datei ist der Status der einzelnen Aktionen aufgeführt, einschließlich aller durch die Aktionen generierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="4fc94-185">The file reports the status of each action, including all errors generated by any of the actions.</span></span> <span data-ttu-id="4fc94-186">Der Standardordner ist ein Ordner **SQL Server Management Studio\DAC Packages** im Ordner „Dokumente“ unter Ihrem Windows-Konto.</span><span class="sxs-lookup"><span data-stu-id="4fc94-186">The default folder is a **SQL Server Management Studio\DAC Packages** folder in the Documents folder of your Windows account.</span></span> <span data-ttu-id="4fc94-187">Der Dateiname hat das Format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, wobei \<*DACPackageName*> dem Namen des bereitgestellten Pakets, *JJJJ* dem aktuellen Jahr, *MM* dem aktuellen Monat und *TT* dem aktuellen Tag entspricht.</span><span class="sxs-lookup"><span data-stu-id="4fc94-187">The file name is in the format \<DACPackageName>_RegisterDACReport_yyyymmdd.html, where \<*DACPackageName*> is the name of the package being deployed, *yyyy* = the current year, *mm* = the current month, and *dd* = the current day.</span></span>  
  
 <span data-ttu-id="4fc94-188">**Fertig stellen** – Beendet den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4fc94-188">**Finish** - Terminates the wizard.</span></span>  
  
##  <a name="register-a-dac-using-powershell"></a><a name="RegisterDACPowerShell"></a> <span data-ttu-id="4fc94-189">Registrieren einer DAC mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fc94-189">Register a DAC Using PowerShell</span></span>  
 <span data-ttu-id="4fc94-190">**So registrieren Sie eine DAC mithilfe der Methode „Register()“ in einem PowerShell-Skript**</span><span class="sxs-lookup"><span data-stu-id="4fc94-190">**To register a database as a DAC using the Register() method in a PowerShell script**</span></span>  
  
1.  <span data-ttu-id="4fc94-191">Erstellen Sie ein SMO-Serverobjekt, und legen Sie es auf die Instanz fest, die die als DAC zu registrierende Datenbank enthält.</span><span class="sxs-lookup"><span data-stu-id="4fc94-191">Create a SMO Server object and set it to the instance that contains the database to be registered as a DAC.</span></span>  
  
2.  <span data-ttu-id="4fc94-192">Fügen Sie eine Variable hinzu, die den Namen der Datenbank angibt.</span><span class="sxs-lookup"><span data-stu-id="4fc94-192">Add a variable that specifies the name of the database.</span></span>  
  
3.  <span data-ttu-id="4fc94-193">Geben Sie die Metadaten für die DAC an, z. B. DAC-Namen, Version und Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="4fc94-193">Specify the metadata for the DAC, such as the DAC name, version, and description.</span></span>  
  
4.  <span data-ttu-id="4fc94-194">Führen Sie die Register-Methode mit den oben angegebenen Informationen aus.</span><span class="sxs-lookup"><span data-stu-id="4fc94-194">Run the Register method with the information specified above.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="4fc94-195">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4fc94-195">Example (PowerShell)</span></span>  
 <span data-ttu-id="4fc94-196">Im folgenden Beispiel wird die Datenbank MyDB als DAC registriert.</span><span class="sxs-lookup"><span data-stu-id="4fc94-196">The following example registers a database named MyDB as a DAC.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Specify the database to register as a DAC.  
$dbname = "MyDB"  
  
## Specify the DAC metadata.  
$applicationname = "MyApplication"  
$version = "1.0.0.0"  
$description = "This DAC defines the database used by my application."  
  
## Register the DAC.  
$registerunit = New-Object Microsoft.SqlServer.Management.Dac.DacExtractionUnit($srv, $dbname, $applicationname, $version)  
$registerunit.Description = $description  
$registerunit.Register()  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fc94-197">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fc94-197">See Also</span></span>  
 [<span data-ttu-id="4fc94-198">Datenebenenanwendungen</span><span class="sxs-lookup"><span data-stu-id="4fc94-198">Data-tier Applications</span></span>](data-tier-applications.md)  
