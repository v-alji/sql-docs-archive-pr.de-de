---
title: Konfigurieren von SQL Server in SMO | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723678"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="424c9-102">Konfigurieren von SQL Server in SMO</span><span class="sxs-lookup"><span data-stu-id="424c9-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="424c9-103">In SMO enthalten das- <xref:Microsoft.SqlServer.Management.Smo.Information> Objekt, das <xref:Microsoft.SqlServer.Management.Smo.Settings> -Objekt, das <xref:Microsoft.SqlServer.Management.Smo.UserOptions> -Objekt und das- <xref:Microsoft.SqlServer.Management.Smo.Configuration> Objekt Einstellungen und Informationen für die Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="424c9-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="424c9-104">verfügt über zahlreiche Eigenschaften, die das Verhalten der installierten Instanz beschreiben.</span><span class="sxs-lookup"><span data-stu-id="424c9-104">has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="424c9-105">Die Eigenschaften beschreiben die Startoptionen, die Serverstandardwerte, Dateien und Verzeichnisse, System- und Prozessorinformationen, Produkt und Versionen, Verbindungsinformationen, Speicheroptionen, Sprach- und Sortierungsauswahl und den Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="424c9-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="424c9-106">SQL Server-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="424c9-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="424c9-107">Die <xref:Microsoft.SqlServer.Management.Smo.Information>-Objekteigenschaften enthalten Informationen über die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], wie z. B. Prozessor und Plattform.</span><span class="sxs-lookup"><span data-stu-id="424c9-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="424c9-108">Die <xref:Microsoft.SqlServer.Management.Smo.Settings>-Objekteigenschaften enthalten Informationen über die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="424c9-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="424c9-109">Die Standard-Datenbankdatei und das Standardverzeichnis können zusätzlich zum Mailprofil und Serverkonto geändert werden.</span><span class="sxs-lookup"><span data-stu-id="424c9-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="424c9-110">Diese Eigenschaften bleiben für die Dauer der Verbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="424c9-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="424c9-111">Die <xref:Microsoft.SqlServer.Management.Smo.UserOptions>-Objekteigenschaften enthalten Informationen über das aktuelle Verbindungsverhalten im Zusammenhang mit Arithmetik, ANSI-Standards und Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="424c9-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="424c9-112">Es gibt auch einen Satz an Konfigurationsoptionen, der durch das <xref:Microsoft.SqlServer.Management.Smo.Configuration>-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="424c9-113">Er enthält eine Eigenschaftengruppe, die die Optionen darstellt, die durch die gespeicherte Prozedur `sp_configure` geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="424c9-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="424c9-114">Optionen wie **Prioritäts Erhöhung**, **Wiederherstellungs Intervall** und **Netzwerk Paketgröße**steuern die Leistung der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="424c9-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="424c9-115">Viele dieser Optionen können dynamisch geändert werden. In einigen Fällen allerdings wird zunächst der Wert konfiguriert und dann geändert, wenn die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="424c9-116">Es gibt eine <xref:Microsoft.SqlServer.Management.Smo.Configuration>-Objekteigenschaft für jede Konfigurationsoption.</span><span class="sxs-lookup"><span data-stu-id="424c9-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="424c9-117">Durch die Verwendung des <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>-Objekts können Sie die globale Konfigurationseinstellung ändern.</span><span class="sxs-lookup"><span data-stu-id="424c9-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="424c9-118">Viele Eigenschaften verfügen über Maximal- und Minimalwerte, die auch als <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>-Eigenschaften gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="424c9-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="424c9-119">Diese Eigenschaften erfordern, dass die- <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> Methode die Änderung an die Instanz von übertragen muss [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="424c9-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="424c9-120">Alle Konfigurationsoptionen im <xref:Microsoft.SqlServer.Management.Smo.Configuration>-Objekt müssen vom Systemadministrator geändert werden.</span><span class="sxs-lookup"><span data-stu-id="424c9-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="424c9-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="424c9-121">Examples</span></span>  
 <span data-ttu-id="424c9-122">Für die folgenden Codebeispiele müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="424c9-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="424c9-123">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="424c9-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="424c9-124">Ändern von SQL Server-Konfigurationsoptionen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="424c9-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="424c9-125">Im Codebeispiel wird gezeigt, wie eine Konfigurationsoption in Visual Basic .NET aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="424c9-126">Weiterhin ruft es Informationen über Maximal- und Minimalwerte für die angegebene Konfigurationsoption ab und stellt diese dar.</span><span class="sxs-lookup"><span data-stu-id="424c9-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="424c9-127">Schließlich informiert das Programm den Benutzer, wenn die Änderung dynamisch vorgenommen wurde oder diese bis zum Neustart der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="424c9-128">Ändern von SQL Server-Einstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="424c9-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="424c9-129">Das Codebeispiel zeigt Informationen über die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> und an <xref:Microsoft.SqlServer.Management.Smo.Settings> und ändert Einstellungen in <xref:Microsoft.SqlServer.Management.Smo.Settings> -und- <xref:Microsoft.SqlServer.Management.Smo.UserOptions> Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="424c9-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="424c9-130">Im Beispiel verfügen sowohl das <xref:Microsoft.SqlServer.Management.Smo.UserOptions>-Objekt als auch das <xref:Microsoft.SqlServer.Management.Smo.Settings>-Objekt über eine <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="424c9-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="424c9-131">Sie können die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methoden für diese einzeln ausführen.</span><span class="sxs-lookup"><span data-stu-id="424c9-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="424c9-132">Ändern von SQL Server-Einstellungen in Visual C#</span><span class="sxs-lookup"><span data-stu-id="424c9-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="424c9-133">Das Codebeispiel zeigt Informationen über die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> und an <xref:Microsoft.SqlServer.Management.Smo.Settings> und ändert Einstellungen in <xref:Microsoft.SqlServer.Management.Smo.Settings> -und- <xref:Microsoft.SqlServer.Management.Smo.UserOptions> Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="424c9-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="424c9-134">Im Beispiel verfügen sowohl das <xref:Microsoft.SqlServer.Management.Smo.UserOptions>-Objekt als auch das <xref:Microsoft.SqlServer.Management.Smo.Settings>-Objekt über eine <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="424c9-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="424c9-135">Sie können die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methoden für diese einzeln ausführen.</span><span class="sxs-lookup"><span data-stu-id="424c9-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="424c9-136">Ändern von SQL Server-Einstellungen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="424c9-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="424c9-137">Das Codebeispiel zeigt Informationen über die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> und an <xref:Microsoft.SqlServer.Management.Smo.Settings> und ändert Einstellungen in <xref:Microsoft.SqlServer.Management.Smo.Settings> -und- <xref:Microsoft.SqlServer.Management.Smo.UserOptions> Objekteigenschaften.</span><span class="sxs-lookup"><span data-stu-id="424c9-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="424c9-138">Im Beispiel verfügen sowohl das <xref:Microsoft.SqlServer.Management.Smo.UserOptions>-Objekt als auch das <xref:Microsoft.SqlServer.Management.Smo.Settings>-Objekt über eine <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="424c9-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="424c9-139">Sie können die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>-Methoden für diese einzeln ausführen.</span><span class="sxs-lookup"><span data-stu-id="424c9-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="424c9-140">Ändern von SQL Server-Konfigurationsoptionen in PowerShell</span><span class="sxs-lookup"><span data-stu-id="424c9-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="424c9-141">Im Codebeispiel wird gezeigt, wie eine Konfigurationsoption in Visual Basic .NET aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="424c9-142">Weiterhin ruft es Informationen über Maximal- und Minimalwerte für die angegebene Konfigurationsoption ab und stellt diese dar.</span><span class="sxs-lookup"><span data-stu-id="424c9-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="424c9-143">Schließlich informiert das Programm den Benutzer, wenn die Änderung dynamisch vorgenommen wurde oder diese bis zum Neustart der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="424c9-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
