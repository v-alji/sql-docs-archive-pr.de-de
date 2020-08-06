---
title: Bereitstellen einer SQL Server-Datenbank auf einem virtuellen Microsoft Azure-Computer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721486"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="4e7ca-102">Bereitstellen einer SQL Server-Datenbank auf einem virtuellen Microsoft Azure-Computer</span><span class="sxs-lookup"><span data-stu-id="4e7ca-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="4e7ca-103">Verwenden Sie den Assistenten zum Bereitstellen **einer SQL Server Datenbank in einer Azure-VM** , um eine Datenbank von einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] in auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] einem virtuellen Azure-Computer (VM) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="4e7ca-104">Der Assistent führt eine vollständige Datenbanksicherung durch und kopiert somit immer das vollständige Datenbankschema und alle Daten einer SQL Server-Benutzerdatenbank.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="4e7ca-105">Der Assistent übernimmt außerdem die gesamte Azure-VM-Konfiguration, sodass keine Vorkonfiguration der VM erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="4e7ca-106">Sie können den Assistenten nicht für differenzielle Sicherungen verwenden, da der Assistent keine vorhandene Datenbank überschreibt, die denselben Datenbanknamen hat.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="4e7ca-107">Um eine vorhandene Datenbank auf der VM zu ersetzen, müssen Sie zuerst die vorhandene Datenbank löschen oder den Datenbanknamen ändern.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="4e7ca-108">Falls ein Namenskonflikt zwischen dem Datenbanknamen eines aktiven Bereitstellungsvorgangs und dem einer vorhandenen Datenbank auf der VM auftritt, schlägt der Assistent ein Namenssuffix für den Namen der bereitzustellenden Datenbank vor, sodass der Vorgang erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="4e7ca-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-109">Before You Begin</span></span>  
 <span data-ttu-id="4e7ca-110">Für diesen Assistenten sind die folgenden Informationen und Konfigurationseinstellungen verfügbar sein:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="4e7ca-111">Die Microsoft-Konto Details, die Ihrem Azure-Abonnement zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="4e7ca-112">Ihr Azure-Veröffentlichungs Profil.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="4e7ca-113">SQL Server unterstützt derzeit die Version 2.0 des Veröffentlichungsprofils.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="4e7ca-114">Weitere Informationen zum Herunterladen der unterstützten Version des Veröffentlichungsprofils finden Sie unter [Herunterladen des Veröffentlichungsprofils 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="4e7ca-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="4e7ca-115">Das Verwaltungs Zertifikat, das in Ihr Azure-Abonnement hochgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="4e7ca-116">Das Verwaltungszertifikat wurde im persönlichen Zertifikatspeicher auf dem Computer gespeichert, auf dem der Assistent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="4e7ca-117">Ein temporärer Speicherort muss für den Computer verfügbar sein, auf dem die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="4e7ca-118">Der temporäre Speicherort muss zudem auch für den Computer verfügbar sein, auf der der Assistent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="4e7ca-119">Wenn Sie die Datenbank auf einer vorhandenen virtuellen Maschine bereitstellen, muss die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für das Abhören eines TCP/IP-Ports konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="4e7ca-120">Entweder für eine Azure-VM oder ein Katalog Image, das Sie für die Erstellung der VM verwenden möchten, muss die SQL Server konfiguriert Cloudadapter und ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="4e7ca-121">Sie müssen einen geöffneten Endpunkt für Ihre SQL Server Cloudadapter auf dem Azure-Gateway mit dem privaten Port 11435 konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="4e7ca-122">Wenn Sie Ihre Datenbank in einer vorhandenen Azure-VM bereitstellen möchten, müssen Sie außerdem Folgendes bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="4e7ca-123">Der DNS-Name des Cloud-Diensts, der die VM hostet.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="4e7ca-124">Administrator-Anmeldeinformationen für die VM.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="4e7ca-125">Anmeldeinformationen mit Sicherungsoperatorprivilegien für die bereitzustellende Datenbank, aus der Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7ca-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4e7ca-126">Weitere Informationen zum Ausführen von SQL Server auf virtuellen Azure-Computern finden Sie unter [Vorbereiten der Migration zu SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="4e7ca-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="4e7ca-127">Auf Computern, auf denen ein Windows Server-Betriebssystem ausgeführt wird, müssen Sie zur Ausführung dieses Assistenten die folgenden Konfigurationseinstellungen vornehmen:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="4e7ca-128">Deaktivieren Sie die verstärkte Sicherheitskonfiguration: Wählen Sie „Server-Manager > Lokaler Server“, und geben Sie für „Verstärkte Sicherheitskonfiguration für Internet Explorer“ den Wert **AUS** an.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="4e7ca-129">Aktivieren Sie JavaScript: Internet Explorer > Internetoptionen > Sicherheit > Stufe anpassen > Skripting > Active Scripting: **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="4e7ca-130">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4e7ca-131">Die Datenbankgröße für diesen Vorgang ist auf 1 TB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="4e7ca-132">Diese Bereitstellungsfunktion ist in SQL Server Management Studio für [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="4e7ca-133">Diese Bereitstellungsfunktion ist nur für die Verwendung mit Benutzerdatenbanken vorgesehen. Das Bereitstellen von Systemdatenbanken wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="4e7ca-134">Die Bereitstellungsfunktion unterstützt keine gehosteten Dienste, die einer Affinitätsgruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="4e7ca-135">Beispielsweise können Speicherkonten, die einer Affinitätsgruppe zugeordnet sind, nicht auf der Seite **Bereitstellungseinstellungen** dieses Assistenten nicht zur Verwendung ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="4e7ca-136">Die SQL Server-Version auf dem virtuellen Computer muss gleich oder höher sein als die SQL Server-Version des Quellservers.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="4e7ca-137">SQL Server von Daten Bank Versionen, die mithilfe dieses Assistenten auf einer Azure-VM bereitgestellt werden können:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="4e7ca-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="4e7ca-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="4e7ca-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4e7ca-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="4e7ca-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4e7ca-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="4e7ca-141">SQL Server Daten Bank Versionen, die in einer Azure-VM ausgeführt werden, können bereitgestellt werden für:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="4e7ca-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4e7ca-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="4e7ca-143">Falls ein Namenskonflikt zwischen dem Datenbanknamen eines aktiven Bereitstellungsvorgangs und dem einer vorhandenen Datenbank auf der VM auftritt, schlägt der Assistent ein Namenssuffix für den Namen der bereitzustellenden Datenbank vor, sodass der Vorgang erfolgreich abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="4e7ca-144">Überlegungen zur Bereitstellung einer FILESTREAM-aktivierten Datenbank in einer Azure-VM</span><span class="sxs-lookup"><span data-stu-id="4e7ca-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="4e7ca-145">Beachten Sie die folgenden Richtlinien und Einschränkungen, wenn Sie Datenbanken bereitstellen, in denen BLOBs in FILESTREAM-Objekten gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="4e7ca-146">Die Bereitstellungsfunktion kann eine FILESTREAM-aktivierte Datenbank nicht in einer neuen VM bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="4e7ca-147">Wenn FILESTREAM vor dem Ausführen des Assistenten in der VM nicht aktiviert wurde, schlägt der Vorgang zur Datenbankwiederherstellung fehl, und der Assistentenvorgang kann nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="4e7ca-148">Um eine Datenbank, die FILESTREAM verwendet, erfolgreich bereitzustellen, aktivieren Sie FILESTREAM in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf der Host-VM, bevor Sie den Assistenten starten.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="4e7ca-149">Weitere Informationen finden Sie unter [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="4e7ca-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="4e7ca-150">Wenn die Datenbank In-Memory OLTP verwendet, können Sie die Datenbank ohne Änderungen an der Datenbank in einer Azure-VM bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="4e7ca-151">Weitere Informationen finden Sie unter [In-Memory OLTP (Speicheroptimierung)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="4e7ca-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="4e7ca-152">Überlegungen zur geografischen Verteilung von Assets</span><span class="sxs-lookup"><span data-stu-id="4e7ca-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="4e7ca-153">Beachten Sie, dass sich die folgenden Ressourcen in der gleichen geografischen Region befinden müssen:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="4e7ca-154">Clouddienst</span><span class="sxs-lookup"><span data-stu-id="4e7ca-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="4e7ca-155">VM-Speicherort</span><span class="sxs-lookup"><span data-stu-id="4e7ca-155">VM Location</span></span>  
  
-   <span data-ttu-id="4e7ca-156">Datenträgerspeicherdienst</span><span class="sxs-lookup"><span data-stu-id="4e7ca-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="4e7ca-157">Wenn sich die oben genannten Ressourcen nicht in derselben Region befinden, kann der Assistent nicht erfolgreich abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a> <span data-ttu-id="4e7ca-158">Konfigurationseinstellungen des Assistenten</span><span class="sxs-lookup"><span data-stu-id="4e7ca-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="4e7ca-159">Verwenden Sie die folgenden Konfigurationsdetails, um die Einstellungen für eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankbereitstellung in einer Azure-VM zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="4e7ca-160">**Standardpfad für die Konfigurationsdatei** – %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span><span class="sxs-lookup"><span data-stu-id="4e7ca-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="4e7ca-161">**Struktur der Konfigurationsdatei**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="4e7ca-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="4e7ca-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="4e7ca-163">TraceLevel = "Debug"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="4e7ca-164">Backuppath = " \\ \\ [Servername] \\ [Volume] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4e7ca-165">Cleanupdeaktiviert = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="4e7ca-166"><publishprofile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="4e7ca-167">Certificate = "12a34b567890123abcd4ef567a8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4e7ca-168">Abonnement = "1a2b34c5-67d8-90EF-ab12-xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="4e7ca-169">Name = "mein Abonnement"\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="4e7ca-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="4e7ca-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="4e7ca-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="4e7ca-171">**Konfigurationsdateiwerte**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="4e7ca-172">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-172">Permissions</span></span>  
 <span data-ttu-id="4e7ca-173">Die bereitzustellende Datenbank muss sich in einem normalen Status befinden. Außerdem muss das Benutzerkonto, über das der Assistent ausgeführt wird, Zugriff auf die Datenbank haben und über die Berechtigung verfügen, einen Sicherungsvorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="4e7ca-174">Verwenden des Assistenten zum Bereitstellen einer Datenbank auf Azure-VMS</span><span class="sxs-lookup"><span data-stu-id="4e7ca-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="4e7ca-175">**Gehen Sie folgendermaßen vor, um den Assistenten zu starten:**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="4e7ca-176">Verbinden Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von SQL Server Management Studio mit der bereitzustellenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="4e7ca-177">Erweitern Sie im **Objekt-Explorer**den Instanznamen und dann den Knoten **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="4e7ca-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="4e7ca-178">Klicken Sie mit der rechten Maustaste auf die Datenbank, die Sie bereitstellen möchten, und wählen Sie **Tasks**und dann **Datenbank in Azure-VM bereitstellen...**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="4e7ca-179">Seite "Einführung"</span><span class="sxs-lookup"><span data-stu-id="4e7ca-179">Introduction Page</span></span>  
 <span data-ttu-id="4e7ca-180">Auf dieser Seite wird der Assistent zum Bereitstellen **einer SQL Server Datenbank in einer Azure-VM** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="4e7ca-181">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-181">**Options**</span></span>  
  
-   <span data-ttu-id="4e7ca-182">**Diese Seite nicht mehr anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-182">**Do not show this page again.**</span></span> <span data-ttu-id="4e7ca-183">– Aktivieren Sie dieses Kontrollkästchen, damit die Einführungsseite in Zukunft nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="4e7ca-184">Durch**Weiter** gelangen Sie zur Seite **Quelleinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="4e7ca-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="4e7ca-185">**Abbrechen** : bricht den Vorgang ab und schließt den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="4e7ca-186">**Hilfe** : Hiermit wird das MSDN-Hilfethema für den Assistenten gestartet.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="4e7ca-187">Quell Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-187">Source Settings</span></span>  
 <span data-ttu-id="4e7ca-188">Verwenden Sie diese Seite, um eine Verbindung mit der Instanz von herzustellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die die Datenbank hostet, die Sie der Azure-VM bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="4e7ca-189">Außerdem geben Sie einen temporären Speicherort für Dateien an, die auf dem lokalen Computer gespeichert werden sollen, bevor Sie an Azure übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="4e7ca-190">Dies kann ein freigegebener Netzwerkspeicherort sein.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="4e7ca-191">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-191">**Options**</span></span>  
  
-   <span data-ttu-id="4e7ca-192">Klicken Sie auf **verbinden...** , und geben Sie dann Verbindungsdetails für die Instanz von an, die die bereit zustellende [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank hostet.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="4e7ca-193">Wählen Sie in der Dropdownliste **Datenbank auswählen** diejenige Datenbank aus, die bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="4e7ca-194">Geben Sie im Feld **andere Einstellungen** einen freigegebenen Ordner an, auf den der Azure-VM-Dienst zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="4e7ca-195">Azure-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="4e7ca-195">Azure Sign-in</span></span>  
 <span data-ttu-id="4e7ca-196">Verwenden Sie diese Seite, um eine Verbindung mit Azure herzustellen und Verwaltungs Zertifikate bereitzustellen oder Profildetails zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="4e7ca-197">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-197">**Options**</span></span>  
  
-   <span data-ttu-id="4e7ca-198">**Verwaltungs Zertifikat** : Verwenden Sie diese Option, um ein Zertifikat aus dem lokalen Zertifikat Speicher anzugeben, das mit dem Verwaltungs Zertifikat von Azure übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="4e7ca-199">**Veröffentlichungs Profil** : Verwenden Sie diese Option, wenn Sie bereits ein Veröffentlichungs Profil auf Ihren Computer heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="4e7ca-200">**Anmelden** : Verwenden Sie diese Option, um sich mit einer Microsoft-Konto, z. b. einer Live ID oder einem Hotmail-Konto, bei Azure anzumelden, um ein neues Verwaltungs Zertifikat zu generieren und herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="4e7ca-201">Beachten Sie, dass die Anzahl von Zertifikaten pro Abonnement beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="4e7ca-202">**Abonnement** : Wählen Sie Ihre Azure-Abonnement-ID aus dem lokalen Zertifikat Speicher oder einem Veröffentlichungs Profil aus, geben Sie Sie ein, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="4e7ca-203">Seite mit Bereitstellungs Einstellungen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="4e7ca-204">Auf dieser Seite können Sie den Zielserver angeben sowie Details zur neuen Datenbank bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="4e7ca-205">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="4e7ca-205">**Options**</span></span>  
  
-   <span data-ttu-id="4e7ca-206">**Virtueller Azure-Computer** : Geben Sie Details für die VM an, die die SQL Server-Datenbank hostet:</span><span class="sxs-lookup"><span data-stu-id="4e7ca-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="4e7ca-207">**Name des clouddiensts** : Geben Sie den Namen des Diensts an, der die VM hostet.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="4e7ca-208">Um einen neuen Clouddienst zu erstellen, geben Sie einen Namen für den neuen Clouddienst an.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="4e7ca-209">**Name des virtuellen** Computers: Geben Sie den Namen des virtuellen Computers an, auf dem die SQL Server Datenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="4e7ca-210">Um einen neuen virtuellen Azure-Computer zu erstellen, geben Sie einen Namen für den neuen virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="4e7ca-211">**Einstellungen** : Verwenden Sie die Schaltfläche Einstellungen, um einen neuen virtuellen Computer zum Hosten der SQL Server Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="4e7ca-212">Wenn Sie eine vorhandene VM verwenden, werden die angegebenen Informationen verwendet, um Ihre Anmeldeinformationen zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="4e7ca-213">**Speicherkonto** : Wählen Sie in der Dropdown Liste das Speicherkonto aus.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="4e7ca-214">Um ein neues Speicherkonto zu erstellen, geben Sie einen Namen für das neue Konto an.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="4e7ca-215">Beachten Sie, dass Speicherkonten, die einer Affinitätsgruppe zugeordnet sind, nicht in der Dropdownliste verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="4e7ca-216">**Zieldatenbank** : Geben Sie Details für die Zieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="4e7ca-217">**Server Verbindung** : Verbindungsdetails für den Server.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="4e7ca-218">**Datenbank** : Geben Sie den Namen einer neuen Datenbank an, oder bestätigen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="4e7ca-219">Wenn der Datenbankname auf der SQL Server-Zielinstanz bereits vorhanden ist, wird empfohlen, einen anderen Datenbanknamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="4e7ca-220">Seite "Zusammenfassung"</span><span class="sxs-lookup"><span data-stu-id="4e7ca-220">Summary Page</span></span>  
 <span data-ttu-id="4e7ca-221">Auf dieser Seite können Sie die für den Vorgang angegebenen Einstellungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="4e7ca-222">Klicken Sie auf **Fertig stellen**, um den Bereitstellungsvorgang mithilfe der angegebenen Einstellungen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="4e7ca-223">Klicken Sie auf **Abbrechen**, um den Bereitstellungsvorgang abzubrechen und den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="4e7ca-224">Möglicherweise sind manuelle Schritte erforderlich, um Daten Bank Details in der SQL Server-Datenbank auf der Azure-VM bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="4e7ca-225">Diese Schritte werden detailliert für Sie beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="4e7ca-226">Seite "Ergebnisse"</span><span class="sxs-lookup"><span data-stu-id="4e7ca-226">Results Page</span></span>  
 <span data-ttu-id="4e7ca-227">Auf dieser Seite wird angegeben, ob der Bereitstellungsvorgang erfolgreich war oder ob dabei Fehler auftraten, dabei werden die Ergebnisse jeder Aktion angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="4e7ca-228">Für alle Aktionen, die fehlerhaft waren, wird dies in der Spalte **Ergebnis** entsprechend angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="4e7ca-229">Klicken Sie auf den Link, um einen Bericht des für diese Aktion aufgetretenen Fehlers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="4e7ca-230">Klicken Sie auf **Fertig stellen**, und beenden Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="4e7ca-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e7ca-231">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e7ca-231">See Also</span></span>  
 <span data-ttu-id="4e7ca-232">[Cloudadapter für SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="4e7ca-233">[Datenbank-Lebenszyklus Verwaltung](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="4e7ca-234">[Exportieren einer Datenebenenanwendung](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="4e7ca-235">[Importieren einer BacPac-Datei zum Erstellen einer neuen Benutzerdatenbank](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="4e7ca-236">[Sichern und Wiederherstellen von Azure SQL-Datenbanken](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="4e7ca-237">[SQL Server Bereitstellung in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="4e7ca-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="4e7ca-238">Bereit für die Migration zu SQL Server auf Azure-Virtuellen Computern</span><span class="sxs-lookup"><span data-stu-id="4e7ca-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
