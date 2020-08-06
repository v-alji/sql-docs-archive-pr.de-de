---
title: Verwalten der Authentifizierung in PowerShell der Datenbank-Engine | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696906"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="4c935-102">Verwalten der Authentifizierung in PowerShell der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="4c935-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="4c935-103">Standardmäßig wird von den [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Komponenten beim Herstellen einer Verbindung mit einer [!INCLUDE[ssDE](../includes/ssde-md.md)]-Instanz die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4c935-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="4c935-104">Sie können die SQL Server-Authentifizierung verwenden, indem Sie entweder ein virtuelles PowerShell-Laufwerk definieren oder für `-Username` die Parameter `-Password` und `Invoke-Sqlcmd` angeben.</span><span class="sxs-lookup"><span data-stu-id="4c935-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="4c935-105">**Vorbereitungen:**  [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="4c935-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="4c935-106">**Festlegen der Authentifizierung mit:**  [einem virtuellen Laufwerk](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="4c935-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c935-107">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4c935-107">Permissions</span></span>  
 <span data-ttu-id="4c935-108">Alle Aktionen, die Sie in einer [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz ausführen können, werden über die Berechtigungen gesteuert, die den beim Verbinden mit der Instanz verwendeten Authentifizierungsinformationen erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="4c935-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="4c935-109">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter und Cmdlets verwenden standardmäßig das Windows-Konto, unter dem sie ausgeführt werden, um eine Windows-Authentifizierungsverbindung mit [!INCLUDE[ssDE](../includes/ssde-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c935-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4c935-110">Zum Herstellen einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierungsverbindung müssen Sie eine Anmelde-ID und ein Kennwort für die SQL Server-Authentifizierung angeben.</span><span class="sxs-lookup"><span data-stu-id="4c935-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="4c935-111">Wenn Sie den- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Anbieter verwenden, müssen Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Anmelde Informationen einem virtuellen Laufwerk zuordnen und dann den Befehl zum Ändern des Verzeichnisses () verwenden, `cd` um eine Verbindung mit diesem Laufwerk herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c935-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="4c935-112">In Windows PowerShell können Sicherheitsanmeldeinformationen nur virtuellen Laufwerken zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="4c935-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a><span data-ttu-id="4c935-113">SQL Server Authentifizierung mithilfe eines virtuellen Laufwerks</span><span class="sxs-lookup"><span data-stu-id="4c935-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="4c935-114">**So erstellen Sie ein virtuelles Laufwerk mit Zuordnung zu einer SQL Server-Authentifizierungsanmeldung**</span><span class="sxs-lookup"><span data-stu-id="4c935-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="4c935-115">Erstellen Sie eine Funktion, auf die Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="4c935-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="4c935-116">Sie verfügt über Parameter für den Namen, der dem virtuellen Laufwerk zugeordnet werden soll, für die Anmelde-ID und für den Anbieterpfad, der dem virtuellen Laufwerk zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c935-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="4c935-117">Sie verwendet `read-host`, um den Benutzer zur Eingabe des Kennworts aufzufordern.</span><span class="sxs-lookup"><span data-stu-id="4c935-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="4c935-118">Sie verwendet `new-object`, um ein Anmeldeinformationenobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c935-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="4c935-119">Sie verwendet `new-psdrive`, um ein virtuelles Laufwerk mit den angegebenen Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c935-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="4c935-120">Rufen Sie die Funktion auf, um ein virtuelles Laufwerk mit den angegebenen Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c935-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="4c935-121">Beispiel (virtuelles Laufwerk)</span><span class="sxs-lookup"><span data-stu-id="4c935-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="4c935-122">In diesem Beispiel wird eine Funktion mit dem Namen **sqldrive** erstellt, mit der Sie ein virtuelles Laufwerk erstellen können, das mit dem angegebenen Anmeldenamen für die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung und der angegebenen Instanz verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="4c935-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="4c935-123">Sie werden von der Funktion **sqldrive** zur Eingabe des Kennworts für Ihren Anmeldenamen aufgefordert. Das Kennwort wird bei der Eingabe maskiert.</span><span class="sxs-lookup"><span data-stu-id="4c935-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="4c935-124">Wenn Sie dann den Befehl zum Ändern des Verzeichnisses ( `cd` ) verwenden, um mithilfe des Namens des virtuellen Laufwerks eine Verbindung mit einem Pfad herzustellen, werden alle Vorgänge mithilfe der Anmelde Informationen für die-Authentifizierung ausgeführt, die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Sie beim Erstellen des Laufwerks angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="4c935-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a><span data-ttu-id="4c935-125">SQL Server Authentifizierung mithilfe von "aufrufen-sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="4c935-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="4c935-126">**So verwenden Sie Invoke-Sqlcmd mit der SQL Server-Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="4c935-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="4c935-127">Verwenden Sie den `-Username`-Parameter, um eine Anmelde-ID anzugeben, und den `-Password`-Parameter, um das zugeordnete Kennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4c935-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="4c935-128">Beispiel (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="4c935-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="4c935-129">In diesem Beispiel wird das "read-host"-Cmdlet verwendet, um den Benutzer zur Eingabe des Kennworts aufzufordern, und dann unter Verwendung der SQL Server-Authentifizierung eine Verbindung hergestellt.</span><span class="sxs-lookup"><span data-stu-id="4c935-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c935-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c935-130">See Also</span></span>  
 <span data-ttu-id="4c935-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="4c935-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="4c935-132">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="4c935-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="4c935-133">Invoke-Sqlcmd-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4c935-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
