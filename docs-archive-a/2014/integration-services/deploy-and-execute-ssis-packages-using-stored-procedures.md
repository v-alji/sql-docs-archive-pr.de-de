---
title: Bereitstellen und Ausführen von SSIS-Paketen mit gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 60914b0c-1f65-45f8-8132-0ca331749fcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1570207dca6e944b54c553a1d83256d8f4fa3244
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724006"
---
# <a name="deploy-and-execute-ssis-packages-using-stored-procedures"></a><span data-ttu-id="da136-102">Bereitstellen und Ausführen von SSIS-Paketen mithilfe von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="da136-102">Deploy and Execute SSIS Packages using Stored Procedures</span></span>
  <span data-ttu-id="da136-103">Wenn Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt für die Verwendung des Projektbereitstellungsmodells konfigurieren, können Sie gespeicherte Prozeduren im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Katalog verwenden, um das Projekt bereitzustellen und die Pakete auszuführen.</span><span class="sxs-lookup"><span data-stu-id="da136-103">When you configure an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to use the project deployment model, you can use stored procedures in the [!INCLUDE[ssIS](../includes/ssis-md.md)] catalog to deploy the project and execute the packages.</span></span> <span data-ttu-id="da136-104">Informationen zum Projektbereitstellungsmodell finden Sie unter [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="da136-104">For information about the project deployment model, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="da136-105">Sie können auch [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] zum Bereitstellen des Projekts und zum Ausführen der Pakete verwenden.</span><span class="sxs-lookup"><span data-stu-id="da136-105">You can also use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to deploy the project and execute the packages.</span></span> <span data-ttu-id="da136-106">Weitere Informationen finden Sie in den im Abschnitt **Siehe auch** aufgeführten Themen.</span><span class="sxs-lookup"><span data-stu-id="da136-106">For more information, see the topics in the **See Also** section.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="da136-107">Die Transact-SQL-Anweisungen für die im nachstehenden Verfahren aufgelisteten gespeicherten Prozeduren – mit Ausnahme von catalog.deploy_project – können problemlos generiert werden, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="da136-107">You can easily generate the Transact-SQL statements for the stored procedures listed in the procedure below, with the exception of catalog.deploy_project, by doing the following:</span></span>  
> 
>  1.  <span data-ttu-id="da136-108">Erweitern Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]den Knoten **Integration Services-Kataloge** im Objekt-Explorer und navigieren Sie zu dem Paket, das Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="da136-108">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], expand the **Integration Services Catalogs** node in Object Explorer and navigate to the package you want to execute.</span></span>  
> 2.  <span data-ttu-id="da136-109">Klicken Sie mit der rechten Maustaste auf das Paket, und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="da136-109">Right-click the package, and then click **Execute**.</span></span>  
> 3.  <span data-ttu-id="da136-110">Legen Sie nach Bedarf Parameterwerte, Verbindungs-Manager-Eigenschaften und Optionen auf der Registerkarte **Erweitert** fest, zum Beispiel den Protokolliergrad.</span><span class="sxs-lookup"><span data-stu-id="da136-110">As needed, set parameters values, connection manager properties, and options in the **Advanced** tab such as the logging level.</span></span>  
> 
>      <span data-ttu-id="da136-111">Weitere Informationen zu Protokolliergraden finden Sie unter [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span><span class="sxs-lookup"><span data-stu-id="da136-111">For more information about logging levels, see [Enable Logging for Package Execution on the SSIS Server](../../2014/integration-services/enable-logging-for-package-execution-on-the-ssis-server.md).</span></span>  
> 4.  <span data-ttu-id="da136-112">Bevor Sie auf **OK** klicken, um das Paket auszuführen, klicken Sie auf **Skript**.</span><span class="sxs-lookup"><span data-stu-id="da136-112">Before clicking **OK** to execute the package, click **Script**.</span></span> <span data-ttu-id="da136-113">Die Transact-SQL-Anweisung wird in einem Fenster des Abfrage-Editors in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da136-113">The Transact-SQL appears in a Query Editor window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="to-deploy-and-execute-a-package-using-stored-procedures"></a><span data-ttu-id="da136-114">So stellen Sie ein Paket mit gespeicherten Prozeduren bereit und führen es aus</span><span class="sxs-lookup"><span data-stu-id="da136-114">To deploy and execute a package using stored procedures</span></span>  
  
1.  <span data-ttu-id="da136-115">Rufen Sie [catalog.deploy_project &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) auf, um das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt bereitzustellen, das das Paket für den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Server enthält.</span><span class="sxs-lookup"><span data-stu-id="da136-115">Call [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) to deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="da136-116">Um den binären Inhalt der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Projekt Bereitstellungs Datei abzurufen, verwenden Sie für den \* \@ project_stream\* -Parameter eine SELECT-Anweisung mit der OPENROWSET-Funktion und dem BULK-Rowsetanbieter.</span><span class="sxs-lookup"><span data-stu-id="da136-116">To retrieve the binary contents of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project deployment file, for the *\@project_stream* parameter, use a SELECT statement with the OPENROWSET function and the BULK rowset provider.</span></span> <span data-ttu-id="da136-117">Der BULK-Rowsetanbieter ermöglicht es Ihnen, Daten aus einer Datei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="da136-117">The BULK rowset provider enables you to read data from a file.</span></span> <span data-ttu-id="da136-118">Das SINGLE_BLOB-Argument für den BULK-Rowsetanbieter gibt den Inhalt der Datendatei als einzeiliges, einspaltiges Rowset vom Typ "varbinary(max)" zurück.</span><span class="sxs-lookup"><span data-stu-id="da136-118">The SINGLE_BLOB argument for the BULK rowset provider returns the contents of the data file as a single-row, single-column rowset of type varbinary(max).</span></span> <span data-ttu-id="da136-119">Weitere Informationen finden Sie unter [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="da136-119">For more information, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
     <span data-ttu-id="da136-120">Im folgenden Beispiel wird das SSISPackages_ProjectDeployment-Projekt im Ordner „SSIS-Pakete“ auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="da136-120">In the following example, the SSISPackages_ProjectDeployment project is deployed to the SSIS Packages folder on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="da136-121">Die Binärdaten werden aus der Projektdatei (SSISPackage_ProjectDeployment. ispac) gelesen und im \* \@ projectbinary\* -Parameter vom Typ "varbinary (max)" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="da136-121">The binary data is read from the project file (SSISPackage_ProjectDeployment.ispac) and is stored in the *\@ProjectBinary* parameter of type varbinary(max).</span></span> <span data-ttu-id="da136-122">Der \* \@ projectbinary\* -Parameterwert wird dem \* \@ project_stream\* -Parameter zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="da136-122">The *\@ProjectBinary* parameter value is assigned to the *\@project_stream* parameter.</span></span>  
  
    ```  
    DECLARE @ProjectBinary as varbinary(max)  
    DECLARE @operation_id as bigint  
    Set @ProjectBinary = (SELECT * FROM OPENROWSET(BULK 'C:\MyProjects\ SSISPackage_ProjectDeployment.ispac', SINGLE_BLOB) as BinaryData)  
  
    Exec catalog.deploy_project @folder_name = 'SSIS Packages', @project_name = 'DeployViaStoredProc_SSIS', @Project_Stream = @ProjectBinary, @operation_id = @operation_id out  
  
    ```  
  
2.  <span data-ttu-id="da136-123">Rufen Sie [catalog.create_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) auf, um eine Instanz der Paketausführung zu erstellen, und rufen Sie optional [catalog.set_execution_parameter_value &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) auf, um Laufzeitparameterwerte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="da136-123">Call [catalog.create_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database) to create an instance of the package execution, and optionally call [catalog.set_execution_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) to set runtime parameter values.</span></span>  
  
     <span data-ttu-id="da136-124">Im folgenden Beispiel erstellt catalog.create_execution eine Ausführungsinstanz für package.dtsx, das im SSISPackage_ProjectDeployment-Projekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="da136-124">In the following example, catalog.create_execution creates an instance of execution for package.dtsx that is contained in the SSISPackage_ProjectDeployment project.</span></span> <span data-ttu-id="da136-125">Das Projekt befindet sich im Ordner "SSIS-Pakete".</span><span class="sxs-lookup"><span data-stu-id="da136-125">The project is located in the SSIS Packages folder.</span></span> <span data-ttu-id="da136-126">Die von der gespeicherten Prozedur zurückgegebene execution_id wird im Aufruf von catalog.set_execution_parameter_value verwendet.</span><span class="sxs-lookup"><span data-stu-id="da136-126">The execution_id returned by the stored procedure is used in the call to catalog.set_execution_parameter_value.</span></span> <span data-ttu-id="da136-127">Die zweite gespeicherte Prozedur legt den LOGGING_LEVEL-Parameter auf 3 (ausführliche Protokollierung) und einen Paketparameter namens Parameter1 auf den Wert 1 fest.</span><span class="sxs-lookup"><span data-stu-id="da136-127">This second stored procedure sets the LOGGING_LEVEL parameter to 3 (verbose logging) and sets a package parameter named Parameter1 to a value of 1.</span></span>  
  
     <span data-ttu-id="da136-128">Für Parameter wie LOGGING_LEVEL hat object_type den Wert 50.</span><span class="sxs-lookup"><span data-stu-id="da136-128">For parameters such as LOGGING_LEVEL the object_type value is 50.</span></span> <span data-ttu-id="da136-129">Für Paketparameter hat object_type den Wert 30.</span><span class="sxs-lookup"><span data-stu-id="da136-129">For package parameters the object_type value is 30.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    GO  
  
    ```  
  
3.  <span data-ttu-id="da136-130">Rufen Sie [catalog.start_execution &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) auf, um das Paket auszuführen.</span><span class="sxs-lookup"><span data-stu-id="da136-130">Call [catalog.start_execution &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database) to execute the package.</span></span>  
  
     <span data-ttu-id="da136-131">Im folgenden Beispiel wird der Transact-SQL-Anweisung ein Aufruf von catalog.start_execution hinzugefügt, um die Paketausführung zu starten.</span><span class="sxs-lookup"><span data-stu-id="da136-131">In the following example, a call to catalog.start_execution is added to the Transact-SQL to start the package execution.</span></span> <span data-ttu-id="da136-132">Dabei wird die von der gespeicherten Prozedur catalog.create_execution zurückgegebene execution_id verwendet.</span><span class="sxs-lookup"><span data-stu-id="da136-132">The execution_id returned by the catalog.create_execution stored procedure is used.</span></span>  
  
    ```  
    Declare @execution_id bigint  
    EXEC [SSISDB].[catalog].[create_execution] @package_name=N'Package.dtsx', @execution_id=@execution_id OUTPUT, @folder_name=N'SSIS Packages', @project_name=N'SSISPackage_ProjectDeployment', @use32bitruntime=False, @reference_id=1  
  
    Select @execution_id  
    DECLARE @var0 smallint = 3  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=50, @parameter_name=N'LOGGING_LEVEL', @parameter_value=@var0  
  
    DECLARE @var1 int = 1  
    EXEC [SSISDB].[catalog].[set_execution_parameter_value] @execution_id,  @object_type=30, @parameter_name=N'Parameter1', @parameter_value=@var1  
  
    EXEC [SSISDB].[catalog].[start_execution] @execution_id  
    GO  
  
    ```  
  
## <a name="to-deploy-a-project-from-server-to-server-using-stored-procedures"></a><span data-ttu-id="da136-133">So stellen Sie ein Projekt mithilfe von gespeicherten Prozeduren zwischen Servern bereit</span><span class="sxs-lookup"><span data-stu-id="da136-133">To deploy a project from server to server using stored procedures</span></span>  
 <span data-ttu-id="da136-134">Sie können mit den gespeicherten Prozeduren [catalog.get_project &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) und [catalog.deploy_project &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) ein Projekt von Server zu Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="da136-134">You can deploy a project from server to server by using the [catalog.get_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-get-project-ssisdb-database) and [catalog.deploy_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-deploy-project-ssisdb-database) stored procedures.</span></span>  
  
 <span data-ttu-id="da136-135">Bevor Sie die gespeicherten Prozeduren ausführen, müssen Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="da136-135">You need to do the following before running the stored procedures.</span></span>  
  
-   <span data-ttu-id="da136-136">Erstellen Sie ein Verbindungsserverobjekt.</span><span class="sxs-lookup"><span data-stu-id="da136-136">Create a linked server object.</span></span> <span data-ttu-id="da136-137">Weitere Informationen finden Sie unter [Erstellen von Verbindungsservern &#40;SQL Server-Datenbank-Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da136-137">For more information, see [Create Linked Servers &#40;SQL Server Database Engine&#41;](../database-engine/sql-server-database-engine-overview.md).</span></span>  
  
     <span data-ttu-id="da136-138">Legen Sie auf der Seite **Serveroptionen** des Dialogfelds **Eigenschaften des Verbindungsservers** die Optionen **RPC** und **RPC-Ausgabe** auf **True**fest.</span><span class="sxs-lookup"><span data-stu-id="da136-138">On the **Server Options** page of the **Linked Server Properties** dialog box, set **RPC** and **RPC Out** to **True**.</span></span> <span data-ttu-id="da136-139">Legen Sie außerdem **Höherstufung von verteilten Transaktionen für RPC aktivieren** auf **False**fest.</span><span class="sxs-lookup"><span data-stu-id="da136-139">Also, set **Enable Promotion of Distributed Transactions for RPC** to **False**.</span></span>  
  
-   <span data-ttu-id="da136-140">Aktivieren Sie dynamische Parameter für den Anbieter, den Sie für den Verbindungsserver ausgewählt haben, indem Sie im Objekt-Explorer unter **Verbindungsserver** den Knoten **Anbieter** erweitern, mit der rechten Maustaste auf den Anbieter klicken und dann auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="da136-140">Enable dynamic parameters for the provider you selected for the linked server, by expanding the **Providers** node under **Linked Servers** in Object Explorer, right-clicking the provider, and then clicking **Properties**.</span></span> <span data-ttu-id="da136-141">Wählen Sie **Aktivieren** neben **Dynamischer Parameter**aus.</span><span class="sxs-lookup"><span data-stu-id="da136-141">Select **Enable** next to **Dynamic parameter.**</span></span>  
  
-   <span data-ttu-id="da136-142">Überprüfen Sie, ob der Distributed Transaction Coordinator (DTC) auf beiden Servern gestartet ist.</span><span class="sxs-lookup"><span data-stu-id="da136-142">Confirm that the Distributed Transaction Coordinator (DTC) is started on both servers.</span></span>  
  
 <span data-ttu-id="da136-143">Rufen Sie catalog.get_project auf, um die Binärdatei für das Projekt zurückzugeben, und rufen Sie dann catalog.deploy_project auf.</span><span class="sxs-lookup"><span data-stu-id="da136-143">Call catalog.get_project to return the binary for the project, and then call catalog.deploy_project.</span></span> <span data-ttu-id="da136-144">Der von catalog.get_project zurückgegebene Wert wird in eine Tabellenvariable des Typs "varbinary(max)" eingefügt.</span><span class="sxs-lookup"><span data-stu-id="da136-144">The value returned by catalog.get_project is inserted into a table variable of type varbinary(max).</span></span> <span data-ttu-id="da136-145">Der Verbindungsserver kann keine Ergebnisse vom Typ „varbinary(max)“ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="da136-145">The linked server can't return results that are varbinary(max).</span></span>  
  
 <span data-ttu-id="da136-146">Im folgenden Beispiel gibt catalog.get_project eine Binärdatei für das SSISPackages-Projekt auf dem Verbindungsserver zurück.</span><span class="sxs-lookup"><span data-stu-id="da136-146">In the following example, catalog.get_project returns a binary for the SSISPackages project on the linked server.</span></span> <span data-ttu-id="da136-147">Das catalog.deploy_project stellt das Projekt auf dem lokalen Server im Ordner DestFolder bereit.</span><span class="sxs-lookup"><span data-stu-id="da136-147">The catalog.deploy_project deploys the project to the local server, to the folder named DestFolder.</span></span>  
  
```  
declare @resultsTableVar table (  
project_binary varbinary(max)  
)  
  
INSERT @resultsTableVar (project_binary)  
EXECUTE [MyLinkedServer].[SSISDB].[catalog].[get_project] 'Packages', 'SSISPackages'  
  
declare @project_binary varbinary(max)  
select @project_binary = project_binary from @resultsTableVar  
  
exec [SSISDB].[CATALOG].[deploy_project] 'DestFolder', 'SSISPackages', @project_binary  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="da136-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da136-148">See Also</span></span>  
 <span data-ttu-id="da136-149">[Bereitstellen von Projekten auf Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span><span class="sxs-lookup"><span data-stu-id="da136-149">[Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md) </span></span>  
 <span data-ttu-id="da136-150">[Ausführen eines Pakets in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="da136-150">[Run a Package in SQL Server Data Tools](../../2014/integration-services/run-a-package-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="da136-151">Ausführen eines Pakets auf dem SSIS-Server mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da136-151">Run a Package on the SSIS Server Using SQL Server Management Studio</span></span>](run-a-package-on-the-ssis-server-using-sql-server-management-studio.md)  
  
  
