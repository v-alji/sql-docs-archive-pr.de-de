---
title: Überprüfen eines DAC-Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- data-tier application [SQL Server], validate
- data-tier application [SQL Server], compare
- validate DAC
- compare DACs
- data-tier application [SQL Server], view
- view DAC
ms.assetid: 726ffcc2-9221-424a-8477-99e3f85f03bd
author: stevestein
ms.author: sstein
ms.openlocfilehash: 078c7bfeef2ff8636243f4853c03de252c7b9289
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622165"
---
# <a name="validate-a-dac-package"></a><span data-ttu-id="fad4f-102">Überprüfen eines DAC-Pakets</span><span class="sxs-lookup"><span data-stu-id="fad4f-102">Validate a DAC Package</span></span>
  <span data-ttu-id="fad4f-103">Es wird empfohlen, den Inhalt eines DAC-Pakets vor der Bereitstellung in der Produktionsumgebung sowie die Upgradeaktionen vor dem Aktualisieren einer vorhandenen DAC zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-103">It is a good practice to review the contents of a DAC package before deploying it in production, and to validate the upgrade actions before upgrading an existing DAC.</span></span> <span data-ttu-id="fad4f-104">Dies gilt insbesondere für die Bereitstellung von Paketen, die nicht im Unternehmen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="fad4f-104">This is especially true when deploying packages that were not developed in your organization.</span></span>  
  
1.  <span data-ttu-id="fad4f-105">**Vorbereitungen:**  [Voraussetzungen](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="fad4f-105">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
2.  <span data-ttu-id="fad4f-106">**So aktualisieren Sie eine DAC:**  [Anzeigen des Inhalts einer DAC](#ViewDACContents), [Anzeigen der Datenbankänderungen](#ViewDBChanges), [Anzeigen der Upgradeaktionen](#ViewUpgradeActions), [Vergleichen von DACs](#CompareDACs)</span><span class="sxs-lookup"><span data-stu-id="fad4f-106">**To upgrade a DAC, using:**  [View the Contents of a DAC](#ViewDACContents), [View Database Changes](#ViewDBChanges), [View Upgrade Actions](#ViewUpgradeActions), [Compare DACs](#CompareDACs)</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="fad4f-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fad4f-107">Prerequisites</span></span>  
 <span data-ttu-id="fad4f-108">Das Bereitstellen eines DAC-Pakets aus unbekannten oder nicht vertrauenswürdigen Quellen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-108">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="fad4f-109">Solche DACs können schädlichen Code enthalten, der möglicherweise unbeabsichtigten [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code ausführt oder Fehler verursacht, indem er das Schema ändert.</span><span class="sxs-lookup"><span data-stu-id="fad4f-109">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="fad4f-110">Bevor Sie eine DAC aus einer unbekannten oder nicht vertrauenswürdigen Quelle verwenden, stellen Sie sie auf einer isolierten [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Testinstanz bereit, führen [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) für die Datenbank aus und überprüfen außerdem den Code, z. B. gespeicherte Prozeduren oder sonstigen benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="fad4f-110">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], run [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database, and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
##  <a name="view-the-contents-of-a-dac"></a><a name="ViewDACContents"></a> <span data-ttu-id="fad4f-111">Anzeigen des Inhalts einer DAC</span><span class="sxs-lookup"><span data-stu-id="fad4f-111">View the Contents of a DAC</span></span>  
 <span data-ttu-id="fad4f-112">Es gibt zwei Vorgehensweisen, um den Inhalt eines Datenebenenanwendungs-Pakets (DAC) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-112">There are two mechanisms for viewing the contents of a data-tier application (DAC) package.</span></span> <span data-ttu-id="fad4f-113">Sie können das DAC-Paket in ein DAC-Projekt in SQL Server Developer Tools importieren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-113">You can import the DAC package to a DAC project in SQL Server Developer Tools.</span></span> <span data-ttu-id="fad4f-114">Der Inhalt des Pakets kann in einen Ordner entpackt werden.</span><span class="sxs-lookup"><span data-stu-id="fad4f-114">You can unpack the contents of the package to a folder.</span></span>  
  
 <span data-ttu-id="fad4f-115">**Anzeigen einer DAC in SQL Server Developer Tools**</span><span class="sxs-lookup"><span data-stu-id="fad4f-115">**View a DAC in SQL Server Developer Tools**</span></span>  
  
1.  <span data-ttu-id="fad4f-116">Öffnen Sie das Menü **Datei**, und klicken Sie auf **Neu** und dann auf **Projekt...** .</span><span class="sxs-lookup"><span data-stu-id="fad4f-116">Open the **File** menu, select **New**, and then select **Project...**.</span></span>  
  
2.  <span data-ttu-id="fad4f-117">Wählen Sie die **SQL Server** -Projektvorlage aus, und geben Sie **Name**, **Speicherort**und **Projektmappenname**ein.</span><span class="sxs-lookup"><span data-stu-id="fad4f-117">Select the **SQL Server** project template, and specify a **Name**, **Location**, and **Solution name**.</span></span>  
  
3.  <span data-ttu-id="fad4f-118">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie dann **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="fad4f-118">In **Solution Explorer**, right click the project node and select **Properties...**.</span></span>  
  
4.  <span data-ttu-id="fad4f-119">Aktivieren Sie auf der Registerkarte **Projekteinstellungen** im Abschnitt **Ausgabetypen** das Kontrollkästchen **Datenebenenanwendung (DACPAC-Datei)** , und schließen Sie dann das Dialogfeld mit den Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fad4f-119">On the **Project Settings** tab, in the **Output Types** section, select the **Data-tier Application (.dacpac File)** check box, and then close the properties dialog.</span></span>  
  
5.  <span data-ttu-id="fad4f-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Datenebenenanwendung importieren** aus.</span><span class="sxs-lookup"><span data-stu-id="fad4f-120">In **Solution Explorer**, right click the project node and select **Import Data-tier Application...**.</span></span>  
  
6.  <span data-ttu-id="fad4f-121">Öffnen Sie mit dem **Projektmappen-Explorer** alle Dateien in der DAC, z. B. die Richtlinie zur Serverauswahl und die vor und nach der Bereitstellung auszuführenden Skripts.</span><span class="sxs-lookup"><span data-stu-id="fad4f-121">Use **Solution Explorer** to open all of the files in the DAC, such as the server selection policy and the pre- and post-deployment scripts.</span></span>  
  
7.  <span data-ttu-id="fad4f-122">Überprüfen Sie alle Objekte im Schema mithilfe der **Schemaansicht** , insbesondere auch den Code in Objekten wie Funktionen oder gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-122">Use the **Schema View** to review all of the objects in the schema, particularly reviewing the code in objects such as functions or stored procedures.</span></span>  
  
 <span data-ttu-id="fad4f-123">**Anzeigen einer DAC in einem Ordner**</span><span class="sxs-lookup"><span data-stu-id="fad4f-123">**View a DAC in a Folder**</span></span>  
  
-   <span data-ttu-id="fad4f-124">Entpacken Sie das DAC-Paket in einen Ordner anhand der Anweisungen unter [Unpack a DAC Package](unpack-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="fad4f-124">Unpack the DAC package into a folder by following the instructions in [Unpack a DAC Package](unpack-a-dac-package.md).</span></span>  
  
-   <span data-ttu-id="fad4f-125">Zeigen Sie den Inhalt der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts an, indem Sie sie im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]öffnen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-125">View the contents of the [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts by opening them in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
-   <span data-ttu-id="fad4f-126">Zeigen Sie den Inhalt der Textdateien in Tools an, z. B. im Editor.</span><span class="sxs-lookup"><span data-stu-id="fad4f-126">View the contents of the text files in tools such as notepad.</span></span>  
  
##  <a name="view-database-changes"></a><a name="ViewDBChanges"></a> <span data-ttu-id="fad4f-127">Anzeigen von Datenbankänderungen</span><span class="sxs-lookup"><span data-stu-id="fad4f-127">View Database Changes</span></span>  
 <span data-ttu-id="fad4f-128">Nach der Bereitstellung der aktuellen Version einer DAC in der Produktionsumgebung wurden möglicherweise Änderungen direkt an der zugeordneten Datenbank vorgenommen, die einen Konflikt mit dem in einer neuen Version der DAC definierten Schema verursachen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-128">After the current version of a DAC was deployed to production, changes may have been made directly to the associated database that might conflict with the schema defined in a new version of the DAC.</span></span> <span data-ttu-id="fad4f-129">Überprüfen Sie vor dem Upgrade auf eine neue Version der DAC, ob solche Änderungen an der Datenbank vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="fad4f-129">Before upgrading to a new version of the DAC, check to see if such changes have been made to the database.</span></span>  
  
 <span data-ttu-id="fad4f-130">**Anzeigen von Datenbankänderungen mit einem Assistenten**</span><span class="sxs-lookup"><span data-stu-id="fad4f-130">**View Database Changes by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="fad4f-131">Führen Sie den **Assistenten zum Aktualisieren von Datenebenenanwendungen** aus, und geben Sie die derzeit bereitgestellte DAC und das DAC-Paket mit der neuen Version der DAC an.</span><span class="sxs-lookup"><span data-stu-id="fad4f-131">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="fad4f-132">Überprüfen Sie auf der Seite **Änderung erkennen** den Bericht der an der Datenbank vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-132">On the **Detect Change** page, review the report of the changes that have been made to the database.</span></span>  
  
3.  <span data-ttu-id="fad4f-133">Wählen Sie **Abbrechen** , wenn Sie das Upgrade nicht fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="fad4f-133">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="fad4f-134">Weitere Informationen zur Verwendung des Assistenten finden Sie unter [Upgrade einer Datenebenenanwendung](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="fad4f-134">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
### <a name="view-database-changes-by-using-powershell"></a><span data-ttu-id="fad4f-135">Anzeigen von Datenbankänderungen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad4f-135">View Database Changes by Using PowerShell</span></span>
  
1.  <span data-ttu-id="fad4f-136">Erstellen Sie ein SMO-Serverobjekt, und legen Sie es auf die Instanz fest, die die anzuzeigende DAC enthält.</span><span class="sxs-lookup"><span data-stu-id="fad4f-136">Create a SMO Server object and set it to the instance that contains the DAC to be viewed.</span></span>  
  
2.  <span data-ttu-id="fad4f-137">Öffnen Sie ein `ServerConnection`-Objekt, und stellen Sie eine Verbindung mit derselben Instanz her.</span><span class="sxs-lookup"><span data-stu-id="fad4f-137">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="fad4f-138">Gibt den DAC-Namen in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="fad4f-138">Specify the DAC name in a variable.</span></span>  
  
4.  <span data-ttu-id="fad4f-139">Rufen Sie mit der `GetDatabaseChanges()`-Methode ein `ChangeResults`-Objekt ab, und übergeben Sie das Objekt an eine Textdatei, um einen einfachen Bericht der neuen, gelöschten und geänderten Objekte zu generieren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-139">Use the `GetDatabaseChanges()` method to retrieve a `ChangeResults` object, and pipe the object to a text file to generate a simple report of new, deleted, and changed objects.</span></span>  
  
### <a name="view-database-changes-example-powershell"></a><span data-ttu-id="fad4f-140">Anzeigen eines Beispiels für Datenbankänderungen (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="fad4f-140">View Database Changes Example (PowerShell)</span></span>
  
 <span data-ttu-id="fad4f-141">Im folgenden Beispiel werden alle Datenbankänderungen gemeldet, die in einer bereitgestellten DAC namens "MyApplicaiton" vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="fad4f-141">The following example reports any database changes that have been made in a deployed DAC named MyApplicaiton.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the change list and save to file.  
$dacChanges = $dacstore.GetDatabaseChanges($dacName) | Out-File -Filepath C:\DACScripts\MyApplicationChanges.txt  
```  
  
##  <a name="view-upgrade-actions"></a><a name="ViewUpgradeActions"></a> <span data-ttu-id="fad4f-142">Anzeigen von Upgradeaktionen</span><span class="sxs-lookup"><span data-stu-id="fad4f-142">View Upgrade Actions</span></span>  
 <span data-ttu-id="fad4f-143">Vor der Verwendung einer neuen Version eines DAC-Pakets zum Aktualisieren einer DAC, die aus einem früheren DAC-Paket bereitgestellt wurde, können Sie einen Bericht generieren, der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen enthält, die während des Upgrades ausgeführt werden, und die Anweisungen dann überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-143">Before using a new version of a DAC package to upgrade a DAC that was deployed from an earlier DAC package, you can generate a report that contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that will be run during the upgrade, and then review the statements.</span></span>  
  
 <span data-ttu-id="fad4f-144">**Melden von Upgradeaktionen mithilfe eines Assistenten**</span><span class="sxs-lookup"><span data-stu-id="fad4f-144">**Report Upgrade Actions by Using a Wizard**</span></span>  
  
1.  <span data-ttu-id="fad4f-145">Führen Sie den **Assistenten zum Aktualisieren von Datenebenenanwendungen** aus, und geben Sie die derzeit bereitgestellte DAC und das DAC-Paket mit der neuen Version der DAC an.</span><span class="sxs-lookup"><span data-stu-id="fad4f-145">Run the **Upgrade Data-tier Application** wizard, specifying the currently deployed DAC and the DAC package containing the new version of the DAC.</span></span>  
  
2.  <span data-ttu-id="fad4f-146">Überprüfen Sie auf der Seite **Zusammenfassung** den Bericht der Upgradeaktionen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-146">On the **Summary** page, review the report of the upgrade actions.</span></span>  
  
3.  <span data-ttu-id="fad4f-147">Wählen Sie **Abbrechen** , wenn Sie das Upgrade nicht fortsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="fad4f-147">Select **Cancel** if you do not want to continue with the upgrade.</span></span>  
  
4.  <span data-ttu-id="fad4f-148">Weitere Informationen zur Verwendung des Assistenten finden Sie unter [Upgrade einer Datenebenenanwendung](upgrade-a-data-tier-application.md).</span><span class="sxs-lookup"><span data-stu-id="fad4f-148">For more information on using the wizard, see [Upgrade a Data-tier Application](upgrade-a-data-tier-application.md).</span></span>  
  
 <span data-ttu-id="fad4f-149">**Melden von Upgradeaktionen mithilfe von PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fad4f-149">**Report Upgrade Actions by Using PowerShell**</span></span>  
  
1.  <span data-ttu-id="fad4f-150">Erstellen Sie ein SMO-Serverobjekt, und legen Sie es auf die Instanz fest, die die bereitgestellte DAC enthält.</span><span class="sxs-lookup"><span data-stu-id="fad4f-150">Create a SMO Server object and set it to the instance that contains the deployed DAC.</span></span>  
  
2.  <span data-ttu-id="fad4f-151">Öffnen Sie ein `ServerConnection`-Objekt, und stellen Sie eine Verbindung mit derselben Instanz her.</span><span class="sxs-lookup"><span data-stu-id="fad4f-151">Open a `ServerConnection` object and connect to the same instance.</span></span>  
  
3.  <span data-ttu-id="fad4f-152">Laden Sie die DAC-Paketdatei mithilfe von `System.IO.File`.</span><span class="sxs-lookup"><span data-stu-id="fad4f-152">Use `System.IO.File` to load the DAC package file.</span></span>  
  
4.  <span data-ttu-id="fad4f-153">Gibt den DAC-Namen in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="fad4f-153">Specify the DAC name in a variable.</span></span>  
  
5.  <span data-ttu-id="fad4f-154">Rufen Sie mithilfe der `GetIncrementalUpgradeScript()`-Methode eine Liste der Transact-SQL-Anweisungen ab, die bei einem Upgrade ausgeführt werden würden, und übergeben Sie die Liste an eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="fad4f-154">Use the `GetIncrementalUpgradeScript()` method to get a list of the Transact-SQL statements an upgrade would run, and pipe the list to a text file.</span></span>  
  
6.  <span data-ttu-id="fad4f-155">Schließen Sie den Dateidatenstrom, der zum Lesen der DAC-Paketdatei verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fad4f-155">Close the file stream used to read the DAC package file.</span></span>  
  
### <a name="view-upgrade-actions-example-powershell"></a><span data-ttu-id="fad4f-156">Anzeigen eines Beispiels für Upgradeaktionen (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="fad4f-156">View Upgrade Actions Example (PowerShell)</span></span>
  
 <span data-ttu-id="fad4f-157">Im folgenden Beispiel werden die Transact-SQL-Anweisungen gemeldet, die zum Aktualisieren der DAC "MyApplicaiton" auf das in einer MyApplicationVNext.dacpac-Datei definierte Schema ausgeführt werden würde.</span><span class="sxs-lookup"><span data-stu-id="fad4f-157">The following example reports the Transact-SQL statements that would be run to upgrading a DAC named MyApplicaiton to the schema defined in a MyApplicationVNext.dacpac file.</span></span>  
  
```powershell
## Set a SMO Server object to the default instance on the local computer.  
CD SQLSERVER:\SQL\localhost\DEFAULT  
$srv = Get-Item .  
  
## Open a Common.ServerConnection to the same instance.  
$serverconnection = New-Object Microsoft.SqlServer.Management.Common.ServerConnection($srv.ConnectionContext.SqlConnectionObject)  
$serverconnection.Connect()  
$dacstore = New-Object Microsoft.SqlServer.Management.Dac.DacStore($serverconnection)  
  
## Load the DAC package file.  
$dacpacPath = "C:\MyDACs\MyApplicationVNext.dacpac"  
$fileStream = [System.IO.File]::Open($dacpacPath,[System.IO.FileMode]::OpenOrCreate)  
$dacType = [Microsoft.SqlServer.Management.Dac.DacType]::Load($fileStream)  
  
## Specify the DAC instance name.  
$dacName  = "MyApplication"  
  
## Generate the upgrade script and save to file.  
$dacstore.GetIncrementalUpgradeScript($dacName, $dacType) | Out-File -Filepath C:\DACScripts\MyApplicationUpgrade.sql  
  
## Close the filestream to the new DAC package.  
$fileStream.Close()  
```  
  
##  <a name="compare-dacs"></a><a name="CompareDACs"></a><span data-ttu-id="fad4f-158">Vergleichen von DACs</span><span class="sxs-lookup"><span data-stu-id="fad4f-158">Compare DACs</span></span>  
 <span data-ttu-id="fad4f-159">Vor dem Aktualisieren einer DAC empfiehlt es sich, die Unterschiede in der Datenbank und in den Objekten auf Instanzebene zwischen der aktuellen und der neuen DAC zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="fad4f-159">Before upgrading a DAC, it is a good practice to review the differences in the database and instance-level objects between the current and new DACs.</span></span> <span data-ttu-id="fad4f-160">Wenn Sie über keine Kopie des Pakets für die aktuelle DAC verfügen, können Sie ein Paket aus der aktuellen Datenbank extrahieren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-160">If you do not have a copy of the package for the current DAC, you can extract a package from the current database.</span></span>  
  
 <span data-ttu-id="fad4f-161">Wenn Sie beide DAC-Pakete in DAC-Projekte in SQL Server Developer Tools importieren, können Sie das Tool "Schemavergleich" verwenden, um die Unterschiede zwischen den beiden DACs zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-161">If you import both DAC packages into DAC projects in SQL Server Developer Tools, you can use the Schema Compare tool to analyze the differences between the two DACs.</span></span>  
  
 <span data-ttu-id="fad4f-162">Entpacken Sie alternativ die DACs in separate Ordner.</span><span class="sxs-lookup"><span data-stu-id="fad4f-162">Alternatively, unpack the DACs into separate folders.</span></span> <span data-ttu-id="fad4f-163">Anschließend können Sie die Unterschiede mit einem Vergleichstool wie dem Hilfsprogramm "WinDiff" analysieren.</span><span class="sxs-lookup"><span data-stu-id="fad4f-163">You can then use a difference tool, such as the WinDiff utility, to analyze the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad4f-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fad4f-164">See Also</span></span>  
 <span data-ttu-id="fad4f-165">[Datenebenenanwendungen](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fad4f-165">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="fad4f-166">[Bereitstellen einer Datenebenenanwendung](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="fad4f-166">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="fad4f-167">Aktualisieren einer Datenebenenanwendung</span><span class="sxs-lookup"><span data-stu-id="fad4f-167">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
