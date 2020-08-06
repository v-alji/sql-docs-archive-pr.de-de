---
title: Aktivieren oder Deaktivieren eines Servernetzwerkprotokoll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], disabling
- remote connections [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], enabling using Configuration Manager
- protocols [SQL Server], disabling using Configuration Manager
- disabling network protocols, Configuration Manager
- network protocols [SQL Server], enabling
- enabling network protocols, Configuration Manager
- surface area configuration [SQL Server], connection protocols
- connections [SQL Server], enabling remote using Configuration Manager
ms.assetid: ec5ccb69-61c9-4576-8843-014b976fd46e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 737edae84ff284ed726ade69cb48e574b830611e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700214"
---
# <a name="enable-or-disable-a-server-network-protocol"></a><span data-ttu-id="32f36-102">Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="32f36-102">Enable or Disable a Server Network Protocol</span></span>
  <span data-ttu-id="32f36-103">Alle Netzwerkprotokolle werden vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setup installiert, sie können jedoch aktiviert oder nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="32f36-103">All network protocols are installed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, but may or may not be enabled.</span></span> <span data-ttu-id="32f36-104">In diesem Thema wird beschrieben, wie mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Configuration Manager oder PowerShell ein Servernetzwerkprotokoll in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktiviert oder deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="32f36-104">This topic describes how to enable or disable a server network protocol in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager or PowerShell.</span></span> <span data-ttu-id="32f36-105">[!INCLUDE[ssDE](../../includes/ssde-md.md)] muss beendet und neu gestartet werden, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="32f36-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be stopped and restarted for the change to take effect.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="32f36-106">Während des Setups von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] wird eine Anmeldung für die Gruppe BUILTIN\Users hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="32f36-106">During setup of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] a login is added for the BUILTIN\Users group.</span></span> <span data-ttu-id="32f36-107">Dies ermöglicht allen authentifizierten Benutzern des Computers den Zugriff auf die Instanz von [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] als Element der öffentlichen Rolle.</span><span class="sxs-lookup"><span data-stu-id="32f36-107">This allows all authenticated users of the computer to access the instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] as a member of the public role.</span></span> <span data-ttu-id="32f36-108">Die BUILTIN\Users-Anmeldung kann sicher entfernt werden, um den [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Zugriff auf Computerbenutzer zu beschränken, die eigene Logins besitzen oder Mitglieder anderer Windows-Gruppen mit Logins sind.</span><span class="sxs-lookup"><span data-stu-id="32f36-108">The BUILTIN\Users login can be safely removed to restrict [!INCLUDE[ssDE](../../includes/ssde-md.md)] access to computer users who have individual logins or are members of other Windows groups with logins.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="32f36-109">und [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützen TLS 1.0 und SSL 3.0.</span><span class="sxs-lookup"><span data-stu-id="32f36-109">and [!INCLUDE[msCoName](../../includes/msconame-md.md)] data providers for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support TLS 1.0 and SSL 3.0.</span></span> <span data-ttu-id="32f36-110">Wenn Sie ein anderes Protokoll (beispielsweise TLS 1.1 oder TLS 1.2) erzwingen, indem Sie Änderungen an der SChannel-Betriebssystemebene vornehmen, können Sie möglicherweise keine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="32f36-110">If you enforce a different protocol (such as TLS 1.1 or TLS 1.2) by making changes in the operating system SChannel layer, your connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might fail.</span></span>  
  
 <span data-ttu-id="32f36-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="32f36-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="32f36-112">**So aktivieren oder deaktivieren Sie ein Servernetzwerkprotokoll mit:**</span><span class="sxs-lookup"><span data-stu-id="32f36-112">**To enable or disable a server network protocol using:**</span></span>  
  
     [<span data-ttu-id="32f36-113">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="32f36-113">SQL Server Configuration Manager</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="32f36-114">PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f36-114">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="32f36-115">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="32f36-115">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-a-server-network-protocol"></a><span data-ttu-id="32f36-116">So aktivieren Sie ein Server-Netzwerkprotokoll</span><span class="sxs-lookup"><span data-stu-id="32f36-116">To enable a server network protocol</span></span>  
  
1.  <span data-ttu-id="32f36-117">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager im Konsolenbereich **SQL Server-Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="32f36-117">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the console pane, expand **SQL Server  Network Configuration**.</span></span>  
  
2.  <span data-ttu-id="32f36-118">Klicken Sie im Konsolenbereich auf **Protokolle für** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="32f36-118">In the console pane, click **Protocols for** *\<instance name>*.</span></span>  
  
3.  <span data-ttu-id="32f36-119">Klicken Sie im Detailbereich mit der rechten Maustaste auf das zu ändernde Protokoll, und klicken Sie dann auf **Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="32f36-119">In the details pane, right-click the protocol you want to change, and then click **Enable** or **Disable**.</span></span>  
  
4.  <span data-ttu-id="32f36-120">Klicken Sie im linken Bereich auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="32f36-120">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="32f36-121">Klicken Sie im Detailfenster mit der rechten Maustaste auf **SQL Server ( ***\<instance name>*** )**, und klicken Sie dann auf **neu starten**, um den Dienst zu starten und neu zu starten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32f36-121">In the details pane, right-click **SQL Server (***\<instance name>***)**, and then click **Restart**, to stop and restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
##  <a name="using-sql-server-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="32f36-122">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f36-122">Using SQL Server PowerShell</span></span>  
  
#### <a name="to-enable-a-server-network-protocol-using-powershell"></a><span data-ttu-id="32f36-123">So aktivieren Sie ein Server-Netzwerkprotokoll mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f36-123">To Enable a Server Network Protocol Using PowerShell</span></span>  
  
1.  <span data-ttu-id="32f36-124">Öffnen Sie eine Eingabeaufforderung unter Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="32f36-124">Using administrator permissions open a command prompt.</span></span>  
  
2.  <span data-ttu-id="32f36-125">Starten Sie Windows PowerShell 2.0 aus der Taskleiste, oder klicken Sie auf "Start", auf "Alle Programme", auf "Zubehör", auf "Windows PowerShell" und dann auf "Windows PowerShell".</span><span class="sxs-lookup"><span data-stu-id="32f36-125">Start Windows PowerShell 2.0 from the taskbar, or click Start, then All Programs, then Accessories, then Windows PowerShell, then Windows PowerShell.</span></span>  
  
3.  <span data-ttu-id="32f36-126">Importieren Sie das **sqlps** -Modul, indem Sie eingeben.`Import-Module "sqlps"`</span><span class="sxs-lookup"><span data-stu-id="32f36-126">Import the **sqlps** module by entering `Import-Module "sqlps"`</span></span>  
  
4.  <span data-ttu-id="32f36-127">Führen Sie die folgenden Anweisungen aus, um die Protokolle für TCP und Named Pipes zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="32f36-127">Execute the following statements to enable both the TCP and named pipes protocols.</span></span> <span data-ttu-id="32f36-128">Ersetzen Sie `<computer_name>` mit dem Namen des Computers, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32f36-128">Replace `<computer_name>` with the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="32f36-129">Wenn Sie eine benannte Instanz konfigurieren, ersetzen Sie `MSSQLSERVER` durch den Namen der Instanz.</span><span class="sxs-lookup"><span data-stu-id="32f36-129">If you are configuring a named instance, replace `MSSQLSERVER` with the instance name.</span></span>  
  
     <span data-ttu-id="32f36-130">Um die Protokolle zu deaktivieren, legen Sie die `IsEnabled` -Eigenschaften auf `$false`fest.</span><span class="sxs-lookup"><span data-stu-id="32f36-130">To disable protocols, set the `IsEnabled` properties to `$false`.</span></span>  
  
    ```powershell
    $smo = 'Microsoft.SqlServer.Management.Smo.'  
    $wmi = new-object ($smo + 'Wmi.ManagedComputer').  
  
    # List the object properties, including the instance names.  
    $Wmi  
  
    # Enable the TCP protocol on the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    $Tcp = $wmi.GetSmoObject($uri)  
    $Tcp.IsEnabled = $true  
    $Tcp.Alter()  
    $Tcp  
  
    # Enable the named pipes protocol for the default instance.  
    $uri = "ManagedComputer[@Name='<computer_name>']/ ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Np']"  
    $Np = $wmi.GetSmoObject($uri)  
    $Np.IsEnabled = $true  
    $Np.Alter()  
    $Np  
    ```  
  
#### <a name="to-configure-the-protocols-for-the-local-computer"></a><span data-ttu-id="32f36-131">So konfigurieren Sie die Protokolle für den lokalen Computer</span><span class="sxs-lookup"><span data-stu-id="32f36-131">To configure the protocols for the local computer</span></span>  
  
-   <span data-ttu-id="32f36-132">Wenn das Skript lokal ausgeführt wird und den lokalen Computer konfiguriert, kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell das Skript flexibler gestalten, indem der lokale Computernamen dynamisch festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="32f36-132">When the script is run locally and configures the local computer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell can make the script more flexible by dynamically determining the local computer name.</span></span> <span data-ttu-id="32f36-133">Um den lokalen Computernamen abzurufen, ersetzen Sie die Zeile, die die `$uri` -Variable festlegt, mit der folgenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="32f36-133">To retrieve the local computer name, replace the line setting the `$uri` variable with the following line.</span></span>  
  
    ```powershell
    $uri = "ManagedComputer[@Name='" + (Get-Item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
    ```  
  
#### <a name="to-restart-the-database-engine-by-using-sql-server-powershell"></a><span data-ttu-id="32f36-134">So starten Sie die Datenbank-Engine mit SQL Server PowerShell neu</span><span class="sxs-lookup"><span data-stu-id="32f36-134">To restart the Database Engine by using SQL Server PowerShell</span></span>  
  
-   <span data-ttu-id="32f36-135">Nachdem Sie Protokolle aktiviert oder deaktiviert haben, müssen Sie [!INCLUDE[ssDE](../../includes/ssde-md.md)] beenden und neu starten, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="32f36-135">After you enable or disable protocols, you must stop and restart the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for the change to take effect.</span></span> <span data-ttu-id="32f36-136">Führen Sie die folgenden Anweisungen aus, um die Standardinstanz mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell zu beenden und zu starten.</span><span class="sxs-lookup"><span data-stu-id="32f36-136">Execute the following statements to stop and start the default instance by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell.</span></span> <span data-ttu-id="32f36-137">Um eine benannte Instanz zu beenden und zu starten, ersetzen Sie `'MSSQLSERVER'` durch `'MSSQL$<instance_name>'`.</span><span class="sxs-lookup"><span data-stu-id="32f36-137">To stop and start a named instance replace `'MSSQLSERVER'` with `'MSSQL$<instance_name>'`.</span></span>  
  
    ```powershell
    # Get a reference to the ManagedComputer class.  
    CD SQLSERVER:\SQL\<computer_name>  
    $Wmi = (Get-Item .).ManagedComputer  
    # Get a reference to the default instance of the Database Engine.  
    $DfltInstance = $Wmi.Services['MSSQLSERVER']  
    # Display the state of the service.  
    $DfltInstance  
    # Stop the service.  
    $DfltInstance.Stop();  
    # Wait until the service has time to stop.  
    # Refresh the cache.  
    $DfltInstance.Refresh();   
    # Display the state of the service.  
    $DfltInstance  
    # Start the service again.  
    $DfltInstance.Start();  
    # Wait until the service has time to start.  
    # Refresh the cache and display the state of the service.  
    $DfltInstance.Refresh(); $DfltInstance  
    ```  
