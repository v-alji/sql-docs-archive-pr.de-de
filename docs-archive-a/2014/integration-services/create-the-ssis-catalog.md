---
title: Erstellen des SSIS-Katalogs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609985"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="236d2-102">Erstellen des SSIS-Katalogs</span><span class="sxs-lookup"><span data-stu-id="236d2-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="236d2-103">Nachdem Sie Pakete in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]entworfen und getestet haben, können Sie die Projekte, die die Pakete enthalten, auf einem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="236d2-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="236d2-104">Bevor Sie die Projekte auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Server bereitstellen können, muss der `SSISDB`-Katalog auf dem Server vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="236d2-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="236d2-105">Der Katalog wird vom Installationsprogramm für [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] nicht automatisch erstellt, Sie müssen den Katalog nach folgenden Anweisungen manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="236d2-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="236d2-106">Sie können den SSISDB-Katalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="236d2-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="236d2-107">Sie können den Katalog auch programmgesteuert mit Windows PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="236d2-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="236d2-108">So erstellen Sie den SSISDB-Katalog in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="236d2-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="236d2-109">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="236d2-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="236d2-110">Stellen Sie eine Verbindung mit der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Datenbank-Engine her.</span><span class="sxs-lookup"><span data-stu-id="236d2-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="236d2-111">Erweitern Sie im Objekt-Explorer den Serverknoten, klicken Sie mit der rechten Maustaste auf den Knoten **Integration Services-Kataloge** , und klicken Sie dann auf **Katalog erstellen**.</span><span class="sxs-lookup"><span data-stu-id="236d2-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="236d2-112">Klicken Sie auf **CLR-Integration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="236d2-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="236d2-113">Für den Katalog werden gespeicherte CLR-Prozeduren verwendet.</span><span class="sxs-lookup"><span data-stu-id="236d2-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="236d2-114">Klicken Sie auf **Automatische Ausführung gespeicherter Integration Services-Prozeduren beim Starten von SQL Server aktivieren** , um die gespeicherte Prozedur [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) jedes Mal ausführen zu lassen, wenn die [!INCLUDE[ssIS](../includes/ssis-md.md)] -Serverinstanz neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="236d2-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="236d2-115">Durch die gespeicherte Prozedur wird der Status von Vorgängen für den SSISDB-Katalog verwaltet.</span><span class="sxs-lookup"><span data-stu-id="236d2-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="236d2-116">Dabei wird der Status aller Pakete korrigiert, die während des Ausfalls (falls zutreffend) der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Serverinstanz ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="236d2-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="236d2-117">Geben Sie ein Kennwort ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="236d2-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="236d2-118">Das Kennwort schützt den Datenbank-Hauptschlüssel, der zum Verschlüsseln der Katalogdaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="236d2-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="236d2-119">Bewahren Sie das Kennwort sicher auf.</span><span class="sxs-lookup"><span data-stu-id="236d2-119">Save the password in a secure location.</span></span> <span data-ttu-id="236d2-120">Es wird empfohlen, auch den Datenbank-Hauptschlüssel zu sichern.</span><span class="sxs-lookup"><span data-stu-id="236d2-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="236d2-121">Weitere Informationen finden Sie unter [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="236d2-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="236d2-122">So erstellen Sie den SSISDB-Katalog programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="236d2-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="236d2-123">Führen Sie das folgende PowerShell-Skript aus:</span><span class="sxs-lookup"><span data-stu-id="236d2-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="236d2-124">Weitere Beispiele zum Verwenden von Windows PowerShell und des <xref:Microsoft.SqlServer.Management.IntegrationServices>-Namespaces finden Sie auf blogs.msdn.com im Blogeintrag [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539) (SSIS und PowerShell in SQL Server 2012).</span><span class="sxs-lookup"><span data-stu-id="236d2-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="236d2-125">Eine Übersicht über den Namespace und Codebeispiele finden Sie im Blogeintrag [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892)(Übersicht über das SSIS-Katalogmodell verwalteter Objekte) auf „blogs.msdn.com“.</span><span class="sxs-lookup"><span data-stu-id="236d2-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="236d2-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="236d2-126">See Also</span></span>  
 <span data-ttu-id="236d2-127">[SSIS-Katalog](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="236d2-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="236d2-128">Sichern, Wiederherstellen und Verschieben des SSIS-Katalogs</span><span class="sxs-lookup"><span data-stu-id="236d2-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
