---
title: 'Schritt 4: Bereitstellen des Pakets aus Lektion 6 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622784"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="388ed-102">Schritt 4: Bereitstellen des Pakets aus Lektion 6</span><span class="sxs-lookup"><span data-stu-id="388ed-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="388ed-103">Zum Bereitstellen des Pakets muss das Paket dem SSISDB-Katalog in Integration Services in einer Instanz von SQL Server hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="388ed-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="388ed-104">In dieser Lektion werden Sie dem SSISDB-Katalog das Paket aus Lektion 6 hinzufügen, den Parameter festlegen und das Paket ausführen.</span><span class="sxs-lookup"><span data-stu-id="388ed-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="388ed-105">Für diese Lektion werden Sie mithilfe von SQL Server Management Studio dem SSISDB-Katalog das Paket aus Lektion 6 hinzufügen und das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="388ed-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="388ed-106">Nach dem Bereitstellen des Pakets, ändern Sie den Parameter, um auf einen neuen Speicherort zu verweisen, und führen dann das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="388ed-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="388ed-107">In dieser Lektion führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="388ed-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="388ed-108">Hinzufügen des Pakets zum SSISDB-Katalog im SSIS-Knoten in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="388ed-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="388ed-109">Bereitstellen des Pakets.</span><span class="sxs-lookup"><span data-stu-id="388ed-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="388ed-110">Festlegen des Paketparameterwerts.</span><span class="sxs-lookup"><span data-stu-id="388ed-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="388ed-111">Ausführen des Pakets in SSMS.</span><span class="sxs-lookup"><span data-stu-id="388ed-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="388ed-112">So suchen Sie den SSISDB-Katalog oder fügen ihn hinzu</span><span class="sxs-lookup"><span data-stu-id="388ed-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="388ed-113">Klicken Sie auf "Start", zeigen Sie auf "Alle Programme" und auf "Microsoft SQL Server 2012", und klicken Sie anschließend auf "SQL Management Studio".</span><span class="sxs-lookup"><span data-stu-id="388ed-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="388ed-114">Überprüfen Sie im Dialogfeld "Verbindung mit dem Server herstellen" die Standardeinstellungen, und klicken Sie dann auf "Verbinden".</span><span class="sxs-lookup"><span data-stu-id="388ed-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="388ed-115">Damit die Verbindung hergestellt werden kann, muss das Feld "Servername" den Namen des Computers enthalten, auf dem SQL Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="388ed-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="388ed-116">Wenn es sich bei der Datenbank-Engine um eine benannte Instanz handelt, sollte das Feld „Servername“ zudem den Instanznamen im Format &lt;Computername&gt;\\&lt;Instanzname&gt; enthalten.</span><span class="sxs-lookup"><span data-stu-id="388ed-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="388ed-117">Erweitern Sie im Objekt-Explorer "Integration Services-Kataloge".</span><span class="sxs-lookup"><span data-stu-id="388ed-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="388ed-118">Wenn unter "Integration Services-Kataloge" keine Kataloge aufgeführt sind, fügen Sie dann den SSISDB-Katalog hinzu.</span><span class="sxs-lookup"><span data-stu-id="388ed-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="388ed-119">Um den SSISDB-Katalog hinzuzufügen, klicken Sie mit der rechten Maustaste auf "Integration Services-Kataloge", und klicken Sie dann auf "Katalog erstellen".</span><span class="sxs-lookup"><span data-stu-id="388ed-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="388ed-120">Wählen Sie im Dialogfeld "Katalog erstellen" die Option "CLR-Integration aktivieren" aus.</span><span class="sxs-lookup"><span data-stu-id="388ed-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="388ed-121">Geben Sie im Feld "Kennwort" ein neues Kennwort ein, und geben Sie es erneut im Feld "Kennwort erneut eingeben" ein.</span><span class="sxs-lookup"><span data-stu-id="388ed-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="388ed-122">Achten Sie darauf, dass Sie das eingegebene Kennwort nicht vergessen.</span><span class="sxs-lookup"><span data-stu-id="388ed-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="388ed-123">Klicken Sie auf "OK", um den SSISDB-Katalog hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="388ed-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="388ed-124">So fügen Sie das Paket dem SSISDB-Katalog hinzu</span><span class="sxs-lookup"><span data-stu-id="388ed-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="388ed-125">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf "SSISDB", und klicken Sie auf "Ordner erstellen".</span><span class="sxs-lookup"><span data-stu-id="388ed-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="388ed-126">Geben Sie im Dialogfeld "Ordner erstellen" in das Feld "Ordnername" den Namen "SSIS-Lernprogramm" ein, und klicken Sie auf "OK".</span><span class="sxs-lookup"><span data-stu-id="388ed-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="388ed-127">Erweitern Sie den Ordner "SSIS-Lernprogramm", klicken Sie mit der rechten Maustaste auf "Projekte" und dann auf "Pakete importieren".</span><span class="sxs-lookup"><span data-stu-id="388ed-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="388ed-128">Klicken Sie auf der Seite "Einführung" des Assistenten zum Konvertieren von Integration Services-Projekten auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="388ed-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="388ed-129">Stellen Sie auf der Seite "Pakete suchen" sicher, dass das Dateisystem in der Liste "Quelle" ausgewählt ist, und klicken Sie auf "Durchsuchen".</span><span class="sxs-lookup"><span data-stu-id="388ed-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="388ed-130">Navigieren Sie im Dialogfeld "Nach Ordner suchen" zum Ordner mit dem Projekt "SSIS-Lernprogramm", und klicken Sie dann auf "OK".</span><span class="sxs-lookup"><span data-stu-id="388ed-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="388ed-131">Klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="388ed-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="388ed-132">Auf der Seite "Pakete auswählen" sollten alle sechs Pakete aus dem SSIS-Lernprogramm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="388ed-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="388ed-133">Wählen Sie in der Liste "Pakete" die Datei "Lektion 6.dtsx" aus, und klicken Sie dann auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="388ed-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="388ed-134">Geben Sie auf der Seite "Ziel auswählen" in das Feld "Projektname" "SSIS-Lernprogrammbereitstellung" ein, und klicken Sie auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="388ed-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="388ed-135">Klicken Sie auf jedem der verbleibenden Seiten des Assistenten auf "Weiter", bis Sie zur Seite "Überprüfen" gelangen.</span><span class="sxs-lookup"><span data-stu-id="388ed-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="388ed-136">Klicken Sie auf der Seite "Überprüfen" auf "Konvertieren".</span><span class="sxs-lookup"><span data-stu-id="388ed-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="388ed-137">Wenn die Konvertierung abgeschlossen ist, klicken Sie auf "Schließen".</span><span class="sxs-lookup"><span data-stu-id="388ed-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="388ed-138">Wenn Sie den Assistenten zum Konvertieren von Integration Services-Projekten schließen, zeigt SSIS den Bereitstellungs-Assistenten für Integration Services an.</span><span class="sxs-lookup"><span data-stu-id="388ed-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="388ed-139">Verwenden Sie diesen Assistenten jetzt zur Bereitstellung des Pakets aus Lektion 6.</span><span class="sxs-lookup"><span data-stu-id="388ed-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="388ed-140">Überprüfen Sie auf der Seite "Einführung" des Bereitstellungs-Assistenten für Integration Services die Schritte zum Bereitstellen des Projekts, und klicken Sie dann auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="388ed-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="388ed-141">Stellen Sie auf der Seite "Ziel auswählen" sicher, dass der Servername die Instanz von SQL Server mit dem SSISDB-Katalog ist und dass der Pfad "SSIS-Lernprogrammbereitstellung" zeigt, und klicken Sie dann auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="388ed-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="388ed-142">Überprüfen Sie auf der Seite "Überprüfen" die Zusammenfassung, und klicken Sie auf "Bereitstellen".</span><span class="sxs-lookup"><span data-stu-id="388ed-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="388ed-143">Wenn die Bereitstellung abgeschlossen ist, klicken Sie auf "Schließen".</span><span class="sxs-lookup"><span data-stu-id="388ed-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="388ed-144">Klicken Sie mit der rechten Maustaste im Objekt-Explorer auf "Integration Services-Kataloge" und dann auf "Aktualisieren".</span><span class="sxs-lookup"><span data-stu-id="388ed-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="388ed-145">Erweitern Sie "Integration Services-Kataloge" und dann "SSISDB".</span><span class="sxs-lookup"><span data-stu-id="388ed-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="388ed-146">Erweitern Sie weiterhin die Struktur unter "SSIS-Lernprogramm", bis Sie das Projekt vollständig erweitert haben.</span><span class="sxs-lookup"><span data-stu-id="388ed-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="388ed-147">Unter dem Knoten "Pakete" des Knotens "SSIS-Lernprogrammbereitstellung" sollte "Lektion 6.dtsx" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="388ed-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="388ed-148">Um sicherzustellen, dass das Paket abgeschlossen ist, klicken Sie mit der rechten Maustaste auf "Lektion 6.dtsx", und klicken Sie auf "Konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="388ed-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="388ed-149">Wählen Sie im Dialogfeld "Konfigurieren" "Parameter" aus, und überprüfen Sie, ob es einen Eintrag mit "Lektion 6.dtsx" als Container, "VarFolderName" als Namen und dem Pfad zu "Neue Beispieldaten" als Wert vorhanden ist, und klicken Sie dann auf "Schließen".</span><span class="sxs-lookup"><span data-stu-id="388ed-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="388ed-150">Erstellen Sie vor dem Fortfahren einen neuen Beispieldatenordner, geben Sie ihm den Namen "Beispieldaten Zwei", und kopieren Sie alle drei der ursprünglichen Beispieldateien hinein.</span><span class="sxs-lookup"><span data-stu-id="388ed-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="388ed-151">So erstellen und füllen Sie einen neuen Beispieldatenordner</span><span class="sxs-lookup"><span data-stu-id="388ed-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="388ed-152">Erstellen Sie im Windows-Explorer im Stammverzeichnis Ihres Laufwerks (beispielsweise C:\\) einen neuen Ordner mit dem Namen „Beispieldaten Zwei“.</span><span class="sxs-lookup"><span data-stu-id="388ed-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="388ed-153">Öffnen Sie den Ordner "C:\Programme\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data", und kopieren Sie dann drei der Beispieldateien aus dem Ordner.</span><span class="sxs-lookup"><span data-stu-id="388ed-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="388ed-154">Fügen Sie die kopierten Dateien in den Ordner "Neue Beispieldaten" ein.</span><span class="sxs-lookup"><span data-stu-id="388ed-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="388ed-155">So ändern Sie den Paketparameter, um auf die neuen Beispieldaten zu verweisen</span><span class="sxs-lookup"><span data-stu-id="388ed-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="388ed-156">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf "Lektion 6.dtsx", und klicken Sie auf "Konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="388ed-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="388ed-157">Ändern Sie im Dialogfeld "Konfigurieren" den Parameterwert in den Pfad zu "Beispieldaten Zwei".</span><span class="sxs-lookup"><span data-stu-id="388ed-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="388ed-158">Zum Beispiel "C:\Beispieldaten Zwei", wenn Sie den neuen Ordner im Stammordner von Laufwerk C platziert haben.</span><span class="sxs-lookup"><span data-stu-id="388ed-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="388ed-159">Klicken Sie auf "OK", um das Dialogfeld "Konfigurieren" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="388ed-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="388ed-160">So testen Sie die Bereitstellung des Lektion 6-Pakets</span><span class="sxs-lookup"><span data-stu-id="388ed-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="388ed-161">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf "Lektion 6.dtsx", und klicken Sie auf "Ausführen".</span><span class="sxs-lookup"><span data-stu-id="388ed-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="388ed-162">Klicken Sie im Dialogfeld "Paket ausführen" auf "OK".</span><span class="sxs-lookup"><span data-stu-id="388ed-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="388ed-163">Klicken Sie im Dialogfeld "Meldung" auf "Ja", um den Übersichtsbericht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="388ed-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="388ed-164">Der Übersichtsbericht für das Paket wird mit dem Namen des Pakets und einer Statusübersicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="388ed-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="388ed-165">Der Abschnitt "Übersicht über die Ausführung" enthält das Ergebnis jeder Aufgabe im Paket, und der Abschnitt "Verwendete Parameter" zeigt die Namen und Werte aller Parameter an, die bei der Ausführung des Pakets verwendet werden, einschließlich "VarFolderName".</span><span class="sxs-lookup"><span data-stu-id="388ed-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
