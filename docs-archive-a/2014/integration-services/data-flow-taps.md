---
title: Datenfluss Abzweigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2d847adf-4b3d-4949-a195-ef43de275077
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 053b34add45354d0df71fa73a72f8786cc706d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697037"
---
# <a name="data-flow-taps"></a><span data-ttu-id="1bde3-102">Datenflussabzweigungen</span><span class="sxs-lookup"><span data-stu-id="1bde3-102">Data Flow Taps</span></span>
  <span data-ttu-id="1bde3-103">In [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] wird eine neue Funktion eingeführt, über die Sie dem Datenflusspfad eines Pakets zur Laufzeit eine Datenabzweigung hinzufügen und die Ausgabe von der Datenabzweigung an eine externe Datei weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="1bde3-103">[!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] introduces a new feature that allows you to add a data tap on a data flow path of a package at runtime and direct the output from the data tap to an external file.</span></span> <span data-ttu-id="1bde3-104">Um diese Funktion verwenden zu können, müssen Sie das SSIS-Projekt mithilfe des Projektbereitstellungsmodells auf einem SSIS-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-104">To use this feature, you must deploy your SSIS project using the project deployment model to an SSIS Server.</span></span> <span data-ttu-id="1bde3-105">Nachdem Sie das Paket auf dem Server bereitgestellt haben, müssen Sie T-SQL-Skripts für die SSISDB-Datenbank ausführen, um vor der Paketausführung Datenabzweigungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-105">After you deploy the package to the server, you need to execute T-SQL scripts against the SSISDB database to add data taps before executing the package.</span></span> <span data-ttu-id="1bde3-106">Beispielszenario:</span><span class="sxs-lookup"><span data-stu-id="1bde3-106">Here is a sample scenario:</span></span>  
  
1.  <span data-ttu-id="1bde3-107">Erstellen Sie mithilfe der gespeicherten Prozedur [catalog.create_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) eine Paketausführungsinstanz.</span><span class="sxs-lookup"><span data-stu-id="1bde3-107">Create an execution instance of a package by using the [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) stored procedure.</span></span>  
  
2.  <span data-ttu-id="1bde3-108">Fügen Sie mithilfe einer der gespeicherten Prozeduren [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) bzw. [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) eine Datenabzweigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1bde3-108">Add a data tap by using either [catalog.add_data_tap](/sql/integration-services/system-stored-procedures/catalog-add-data-tap) or [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid) stored procedure.</span></span>  
  
3.  <span data-ttu-id="1bde3-109">Starten Sie die Paketausführungsinstanz mithilfe von [catalog.start_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="1bde3-109">Start the execution instance of the package by using the [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).</span></span>  
  
 <span data-ttu-id="1bde3-110">Im Folgenden ein SQL-Beispielskript, durch das die im vorangehenden Szenario beschriebenen Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="1bde3-110">Here is a sample SQL script that performs the steps described in the above scenario:</span></span>  
  
```  
  
Declare @execid bigint  
EXEC [SSISDB].[catalog].[create_execution] @folder_name=N'ETL Folder', @project_name=N'ETL Project', @package_name=N'Package.dtsx', @execution_id=@execid OUTPUT  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt'  
EXEC [SSISDB].[catalog].[start_execution] @execid  
  
```  
  
 <span data-ttu-id="1bde3-111">Die Parameter für die Ordner-, Projekt- und Paketnamen der gespeicherten Prozedur create_execution entsprechen den Ordner-, Projekt- und Paketnamen im Integration Services-Katalog.</span><span class="sxs-lookup"><span data-stu-id="1bde3-111">The folder name, project name, and package name parameters of the create_execution stored procedure correspond to the folder, project, and package names in the Integration Services catalog.</span></span> <span data-ttu-id="1bde3-112">Sie können die Ordner-, Projekt- und Paketnamen, die Sie im Aufruf von create_execution verwenden möchten, wie in der folgenden Abbildung dargestellt, aus SQL Server Management Studio abrufen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-112">You can get the folder, project, and package names to use in the create_execution call from the SQL Server Management Studio as shown in the following image.</span></span> <span data-ttu-id="1bde3-113">Wenn das SSIS-Projekt hier nicht angezeigt wird, wurde es möglicherweise noch nicht auf dem SSIS-Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1bde3-113">If you do not see your SSIS project here, you may not have deployed the project to SSIS server yet.</span></span> <span data-ttu-id="1bde3-114">Klicken Sie in Visual Studio mit der rechten Maustaste auf das SSIS-Projekt, und klicken Sie auf Bereitstellen, um das Projekt auf dem erwarteten SSIS-Server bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-114">Right-click on SSIS project in Visual Studio and click Deploy to deploy the project to the expected SSIS server.</span></span>  
  
 <span data-ttu-id="1bde3-115">Anstatt die SQL-Anweisungen einzugeben, können Sie das Skript zur Paketausführung anhand der folgenden Schritte generieren:</span><span class="sxs-lookup"><span data-stu-id="1bde3-115">Instead of typing the SQL statements, you can generate the execute package script by performing the following steps:</span></span>  
  
1.  <span data-ttu-id="1bde3-116">Klicken Sie mit der rechten Maustaste auf **Package.dtsx** , und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1bde3-116">Right-click **Package.dtsx** and click **Execute**.</span></span>  
  
2.  <span data-ttu-id="1bde3-117">Klicken Sie auf die Symbolleistenschaltfläche **Skript** , um das Skript zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1bde3-117">Click **Script** toolbar button to generate the script.</span></span>  
  
3.  <span data-ttu-id="1bde3-118">Fügen Sie dann die Anweisung add_data_tap vor dem Aufruf von start_execution hinzu.</span><span class="sxs-lookup"><span data-stu-id="1bde3-118">Now, add the add_data_tap statement before the start_execution call.</span></span>  
  
 <span data-ttu-id="1bde3-119">Der Parameter task_package_path der gespeicherten Prozedur add_data_tap entspricht der Eigenschaft PackagePath des Datenflusstasks in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1bde3-119">The task_package_path parameter of add_data_tap stored procedure corresponds to the PackagePath property of the data flow task in Visual Studio.</span></span> <span data-ttu-id="1bde3-120">Klicken Sie in Visual Studio mit der rechten Maustaste auf **Datenflusstask**, und klicken Sie auf **Eigenschaften** , um das Eigenschaftenfenster zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-120">In Visual Studio, right-click the **Data Flow Task**, and click **Properties** to launch the Properties window.</span></span>  <span data-ttu-id="1bde3-121">Notieren Sie sich den Wert der Eigenschaft **PackagePath** , um sie im Aufruf der gespeicherten Prozedur „add_data_tap“ als Wert für den Parameter „task_package_path“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bde3-121">Note the value of the **PackagePath** property to use it as a value for the task_package_path parameter for add_data_tap stored procedure call.</span></span>  
  
 <span data-ttu-id="1bde3-122">Der Parameter dataflow_path_id_string der gespeicherten Prozedur add_data_tap entspricht der Eigenschaft IdentificationString des Datenflusspfads, dem Sie eine Datenabzweigung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bde3-122">The dataflow_path_id_string  parameter of add_data_tap stored procedure corresponds to the IdentificationString property of the data flow path to which you want to add a data tap.</span></span> <span data-ttu-id="1bde3-123">Klicken Sie auf den Datenflusspfad (Pfeil zwischen den Tasks im Datenfluss), und notieren Sie sich den Wert der Eigenschaft **IdentificationString** im Eigenschaftenfenster, um „dataflow_path_id_string“ abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-123">To get the dataflow_path_id_string, click the data flow path (arrow between tasks in the data flow), and note the value of the **IdentificationString** property in the Properties window.</span></span>  
  
 <span data-ttu-id="1bde3-124">Wenn Sie das Skript ausführen, wird die Ausgabedatei unter „\<Program Files>\Microsoft SQL Server\110\DTS\DataDumps“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1bde3-124">When you execute the script, the output file is stored in \<Program Files>\Microsoft SQL Server\110\DTS\DataDumps.</span></span> <span data-ttu-id="1bde3-125">Wenn bereits eine Datei mit diesem Namen vorhanden ist, wird eine neue Datei mit einem Suffix erstellt (z. B. "output[1].txt").</span><span class="sxs-lookup"><span data-stu-id="1bde3-125">If a file with the name already exists, a new file with a suffix (for example: output[1].txt)  is created.</span></span>  
  
 <span data-ttu-id="1bde3-126">Wie oben erwähnt, können Sie anstelle der gespeicherten Prozedur „add_data_tap“ auch die gespeicherte Prozedur [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bde3-126">As mentioned earlier, you can also use [catalog.add_data_tap_by_guid](/sql/integration-services/system-stored-procedures/catalog-add-data-tap-by-guid)stored procedure instead of using add_data_tap stored procedure.</span></span> <span data-ttu-id="1bde3-127">Diese gespeicherte Prozedur verwendet anstelle von task_package_path die ID des Datenflusstasks als Parameter.</span><span class="sxs-lookup"><span data-stu-id="1bde3-127">This stored procedure takes the ID of data flow task as a parameter instead of task_package_path.</span></span> <span data-ttu-id="1bde3-128">Die ID des Datenflusstasks finden Sie im Eigenschaftenfenster in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1bde3-128">You can get the ID of data flow task from the properties window in Visual Studio.</span></span>  
  
## <a name="removing-a-data-tap"></a><span data-ttu-id="1bde3-129">Entfernen einer Datenabzweigung</span><span class="sxs-lookup"><span data-stu-id="1bde3-129">Removing a data tap</span></span>  
 <span data-ttu-id="1bde3-130">Bevor Sie die Ausführung starten, können Sie eine Datenabzweigung mithilfe der gespeicherten Prozedur [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) entfernen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-130">You can remove a data tap before starting the execution by using the [catalog.remove_data_tap](/sql/integration-services/system-stored-procedures/catalog-remove-data-tap) stored procedure.</span></span> <span data-ttu-id="1bde3-131">Diese gespeicherte Prozedur verwendet die ID der Datenabzweigung als Parameter, die Sie als Ausgabe der gespeicherten Prozedur add_data_tap abrufen können.</span><span class="sxs-lookup"><span data-stu-id="1bde3-131">This stored procedure takes the ID of data tap as a parameter, which you can get as an output of the add_data_tap stored procedure.</span></span>  
  
```  
  
DECLARE @tap_id bigint  
EXEC [SSISDB].[catalog].add_data_tap @execution_id = @execid, @task_package_path = '\Package\Data Flow Task', @dataflow_path_id_string = 'Paths[Flat File Source.Flat File Source Output]', @data_filename = 'output.txt' @data_tap_id=@tap_id OUTPUT  
EXEC [SSISDB].[catalog].remove_data_tap @tap_id  
  
```  
  
## <a name="listing-all-data-taps"></a><span data-ttu-id="1bde3-132">Auflisten aller Datenabzweigungen</span><span class="sxs-lookup"><span data-stu-id="1bde3-132">Listing all data taps</span></span>  
 <span data-ttu-id="1bde3-133">Sie können auch alle Datenabzweigungen mithilfe der Sicht catalog.execution_data_taps auflisten.</span><span class="sxs-lookup"><span data-stu-id="1bde3-133">You can also list all the data taps by using the catalog.execution_data_taps view.</span></span> <span data-ttu-id="1bde3-134">Im folgenden Beispiel werden Datenabzweigungen für die Instanz einer Spezifikationsausführung (ID: 54) extrahiert.</span><span class="sxs-lookup"><span data-stu-id="1bde3-134">The following example extracts data taps for a specification execution instance (ID: 54).</span></span>  
  
```  
select * from [SSISDB].[catalog].execution_data_taps where execution_id=@execid  
```  
  
## <a name="performance-consideration"></a><span data-ttu-id="1bde3-135">Leistungsaspekte</span><span class="sxs-lookup"><span data-stu-id="1bde3-135">Performance consideration</span></span>  
 <span data-ttu-id="1bde3-136">Wenn Sie den ausführlichen Protokolliergrad aktivieren und Datenabzweigungen hinzufügen, erhöhen sich die von der Datenintegrationslösung ausgeführten E/A-Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="1bde3-136">Enabling verbose logging level and adding data taps increase the I/O operations performed by your data integration solution.</span></span> <span data-ttu-id="1bde3-137">Daher wird empfohlen, Datenabzweigungen nur zur Problembehandlung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-137">Hence, we recommend that you add data taps only for troubleshooting purposes</span></span>  
  
## <a name="video"></a><span data-ttu-id="1bde3-138">Video</span><span class="sxs-lookup"><span data-stu-id="1bde3-138">Video</span></span>  
 <span data-ttu-id="1bde3-139">Das [Video auf TechNet](https://technet.microsoft.com/sqlserver/dn600163) zeigt, wie Sie Datenabzweigungen im SQL Server 2012 SSISDB-Katalog hinzufügen bzw. verwenden, die das programmgesteuerte Debuggen von Paketen und die Erfassung von Teilergebnissen zur Laufzeit unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1bde3-139">This [video on TechNet](https://technet.microsoft.com/sqlserver/dn600163) demonstrates how to add/use data taps in SQL Server 2012 SSISDB catalog that help with debugging packages programmatically and capturing the partial results at the runtime.</span></span> <span data-ttu-id="1bde3-140">Das Video zeigt außerdem, wie Sie diese Datenabzweigungen auflisten bzw. entfernen, und welche bewährten Methoden für Datenabzweigungen in SSIS-Paketen empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="1bde3-140">It also discusses how to list/ remove these data taps and best practices for using data taps in SSIS packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1bde3-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1bde3-141">Related Tasks</span></span>  
 [<span data-ttu-id="1bde3-142">Debuggen des Datenflusses</span><span class="sxs-lookup"><span data-stu-id="1bde3-142">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
 [<span data-ttu-id="1bde3-143">Behandlung von Problemen mit Paketausführungstools</span><span class="sxs-lookup"><span data-stu-id="1bde3-143">Troubleshooting Tools for Package Execution</span></span>](troubleshooting/troubleshooting-tools-for-package-execution.md)  
  
  
