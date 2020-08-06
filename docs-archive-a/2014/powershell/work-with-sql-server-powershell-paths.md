---
title: Verwenden von SQL Server PowerShell-Pfaden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: f31d8e2c-8d59-4fee-ac2a-324668e54262
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d2647251eb1c8843d4ab7a95d2c439e47f5bb6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699848"
---
# <a name="work-with-sql-server-powershell-paths"></a><span data-ttu-id="62ea4-102">Verwenden von SQL Server PowerShell-Pfaden</span><span class="sxs-lookup"><span data-stu-id="62ea4-102">Work With SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="62ea4-103">Nach der Navigation zu einem Knoten in einem [!INCLUDE[ssDE](../includes/ssde-md.md)] -Anbieterpfad können Sie mit den Methoden und Eigenschaften des [!INCLUDE[ssDE](../includes/ssde-md.md)] -Verwaltungsobjekts, das dem Knoten zugeordnet ist, Arbeiten ausführen oder Informationen abrufen.</span><span class="sxs-lookup"><span data-stu-id="62ea4-103">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform work or retrieve information by using the methods and properties from the [!INCLUDE[ssDE](../includes/ssde-md.md)] management object associated with the node.</span></span>  
  
1.  [<span data-ttu-id="62ea4-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="62ea4-104">Before You Begin</span></span>](#BeforeYouBegin)  
  
2.  <span data-ttu-id="62ea4-105">**So arbeiten Sie an einem Pfadknoten:**  [Auflisten von Methoden und Eigenschaften](#ListPropMeth), [Verwenden von Methoden und Eigenschaften](#UsePropMeth)</span><span class="sxs-lookup"><span data-stu-id="62ea4-105">**To work on a path node:**  [Listing Methods and Properties](#ListPropMeth), [Using Methods and Properties](#UsePropMeth)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62ea4-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="62ea4-106">Before You Begin</span></span>  
 <span data-ttu-id="62ea4-107">Nach der Navigation zu einem Knoten in einem [!INCLUDE[ssDE](../includes/ssde-md.md)] -Anbieterpfad können Sie zwei Arten von Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="62ea4-107">After you have navigated to a node in a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can perform two types of actions:</span></span>  
  
-   <span data-ttu-id="62ea4-108">Sie können Windows PowerShell-Cmdlets ausführen, die Vorgänge an Knoten durchführen, z.B. **Rename-Item**.</span><span class="sxs-lookup"><span data-stu-id="62ea4-108">You can run Windows PowerShell cmdlets that operate on nodes, such as **Rename-Item**.</span></span>  
  
-   <span data-ttu-id="62ea4-109">Sie können die Methoden vom zugeordneten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Modell des Verwaltungsobjekts aufrufen, z. B. SMO.</span><span class="sxs-lookup"><span data-stu-id="62ea4-109">You can call the methods from the associated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] management object model, such as SMO.</span></span> <span data-ttu-id="62ea4-110">Wenn Sie beispielsweise zum Knoten Databases in einem Pfad navigieren, können Sie die Methoden und Eigenschaften der <xref:Microsoft.SqlServer.Management.Smo.Database> -Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="62ea4-110">For example, if you navigate to the Databases node in a path, you can use the methods and properties of the <xref:Microsoft.SqlServer.Management.Smo.Database> class.</span></span>  
  
 <span data-ttu-id="62ea4-111">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter wird zum Verwalten der Objekte in einer Instanz von [!INCLUDE[ssDE](../includes/ssde-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="62ea4-111">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider is used to manage the objects in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="62ea4-112">Er wird nicht verwendet, um mit den Daten in Datenbanken zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="62ea4-112">It is not used to work with the data in databases.</span></span> <span data-ttu-id="62ea4-113">Wenn Sie zu einer Tabelle oder einer Sicht navigiert sind, können Sie den Anbieter nicht dazu verwenden, Daten auszuwählen, einzufügen, zu aktualisieren oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="62ea4-113">If you have navigated to a table or view, you cannot use the provider to select, insert, update, or delete data.</span></span> <span data-ttu-id="62ea4-114">Verwenden Sie das Cmdlet **Invoke-Sqlcmd** , um Daten in Tabellen und Sichten aus der Windows PowerShell-Umgebung abzufragen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="62ea4-114">Use the **Invoke-Sqlcmd** cmdlet to query or change data in tables and views from the Windows PowerShell environment.</span></span> <span data-ttu-id="62ea4-115">Weitere Informationen finden Sie unter [Cmdlet Invoke-Sqlcmd](../database-engine/invoke-sqlcmd-cmdlet.md).</span><span class="sxs-lookup"><span data-stu-id="62ea4-115">For more information, see [Invoke-Sqlcmd cmdlet](../database-engine/invoke-sqlcmd-cmdlet.md).</span></span>  
  
##  <a name="listing-methods-and-properties"></a><a name="ListPropMeth"></a><span data-ttu-id="62ea4-116">Auflisten von Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62ea4-116">Listing Methods and Properties</span></span>
  
 <span data-ttu-id="62ea4-117">Sie können das Cmdlet **Get-Member** verwenden, um die für bestimmte Objekte oder Objektklassen verfügbaren Methoden und Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="62ea4-117">To view the methods and properties available for specific objects or object classes, use the **Get-Member** cmdlet.</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="62ea4-118">Beispiele: Auflisten von Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62ea4-118">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="62ea4-119">In diesem Beispiel wird eine Windows PowerShell-Variable auf die <xref:Microsoft.SqlServer.Management.Smo.Database> -Klasse von SMO festgelegt und werden die Methoden und Eigenschaften aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="62ea4-119">This example sets a Windows PowerShell variable to the SMO <xref:Microsoft.SqlServer.Management.Smo.Database> class and lists the methods and properties:</span></span>  
  
```powershell
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar | Get-Member -Type Methods  
$MyDBVar | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="62ea4-120">Sie können **Get-Member** ebenfalls verwenden, um die dem Endknoten eines Windows PowerShell-Pfads zugeordneten Methoden und Eigenschaften aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="62ea4-120">You can also use **Get-Member** to list the methods and properties that are associated with the end node of a Windows PowerShell path.</span></span>  
  
 <span data-ttu-id="62ea4-121">In diesem Beispiel wird zum Knoten Databases in einem SQLSERVER:-Pfad navigiert, und die Auflistungseigenschaften werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="62ea4-121">This example navigates to the Databases node in a SQLSERVER: path and lists the collection properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-Item . | Get-Member -Type Properties  
```  
  
 <span data-ttu-id="62ea4-122">In diesem Beispiel wird zum Knoten AdventureWorks2012 in einem SQLSERVER:-Pfad navigiert, und die Objekteigenschaften werden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="62ea4-122">This example navigates to the AdventureWorks2012 node in a SQLSERVER: path and lists the object properties:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
Get-Item . | Get-Member -Type Properties  
```  
  
##  <a name="using-smo-methods-and-properties"></a><a name="UsePropMeth"></a><span data-ttu-id="62ea4-123">Verwenden von SMO-Methoden und-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62ea4-123">Using SMO Methods and Properties</span></span>  
  
 <span data-ttu-id="62ea4-124">Sie können SMO-Methoden und Eigenschaften dazu verwenden, Arbeiten an Objekten eines [!INCLUDE[ssDE](../includes/ssde-md.md)] -Anbieterpfads auszuführen.</span><span class="sxs-lookup"><span data-stu-id="62ea4-124">To perform work on objects from a [!INCLUDE[ssDE](../includes/ssde-md.md)] provider path, you can use SMO methods and properties.</span></span>  
  
### <a name="examples-using-methods-and-properties"></a><span data-ttu-id="62ea4-125">Beispiele: Verwenden von Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62ea4-125">Examples: Using Methods and Properties</span></span>  
 <span data-ttu-id="62ea4-126">In diesem Beispiel wird die **Schema** -Eigenschaft von SMO verwendet, um eine Liste der Tabellen aus dem Sales-Schema in AdventureWorks2012 abzurufen:</span><span class="sxs-lookup"><span data-stu-id="62ea4-126">This example uses the SMO **Schema** property to get a list of the tables from the Sales schema in AdventureWorks2012:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Tables  
Get-ChildItem | Where {$_.Schema -eq "Sales"}  
```  
  
 <span data-ttu-id="62ea4-127">In diesem Beispiel wird die SMO- **Skript** Methode verwendet, um ein Skript zu generieren, das die Anweisungen enthält, die `CREATE VIEW` Sie benötigen, um die Sichten in AdventureWorks2012 neu zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="62ea4-127">This example uses the SMO **Script** method to generate a script that contains the `CREATE VIEW` statements you must have to re-create the views in AdventureWorks2012:</span></span>  
  
```powershell
Remove-Item C:\PowerShell\CreateViews.sql  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012\Views  
foreach ($Item in Get-ChildItem) { $Item.Script() | Out-File -Filepath C:\PowerShell\CreateViews.sql -append }  
```  
  
 <span data-ttu-id="62ea4-128">In diesem Beispiel wird mit der Methode SMO **Create** eine Datenbank erstellt und dann mit der Eigenschaft **State** angezeigt, ob die Datenbank vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="62ea4-128">This example uses the SMO **Create** method to create a database, and then uses the **State** property to show whether the database exists:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
$MyDBVar = New-Object Microsoft.SqlServer.Management.SMO.Database  
$MyDBVar.Parent = (Get-Item ..)  
$MyDBVar.Name = "NewDB"  
$MyDBVar.Create()  
$MyDBVar.State  
```  
  
## <a name="see-also"></a><span data-ttu-id="62ea4-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62ea4-129">See Also</span></span>  
 <span data-ttu-id="62ea4-130">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="62ea4-130">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="62ea4-131">[Navigieren SQL Server PowerShell Pfaden](navigate-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="62ea4-131">[Navigate SQL Server PowerShell Paths](navigate-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="62ea4-132">[Konvertieren von URNs in SQL Server Anbieter Pfade](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="62ea4-132">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="62ea4-133">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="62ea4-133">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
