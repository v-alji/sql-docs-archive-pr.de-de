---
title: Navigieren in SQL Server PowerShell-Pfaden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724778"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="af908-102">Navigieren in SQL Server PowerShell-Pfaden</span><span class="sxs-lookup"><span data-stu-id="af908-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="af908-103">Der [!INCLUDE[ssDE](../includes/ssde-md.md)] -PowerShell-Anbieter macht den Satz von Objekten in einer Instanz von SQL Server in einer Struktur verfügbar, die einem Dateipfad ähnelt.</span><span class="sxs-lookup"><span data-stu-id="af908-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="af908-104">Sie können im Anbieterpfad mithilfe von Windows PowerShell-Cmdlets navigieren und benutzerdefinierte Laufwerke erstellen, um den Pfad zu kürzen, den Sie eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="af908-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="af908-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="af908-105">Before You Begin</span></span>  
 <span data-ttu-id="af908-106">Windows PowerShell implementiert Cmdlets, um in der Pfadstruktur zu navigieren, die die Hierarchie von Objekten darstellt, die von einem PowerShell-Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="af908-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="af908-107">Wenn Sie zu einem Knoten im Pfad navigiert haben, können Sie andere Cmdlets verwenden, um grundlegende Vorgänge für das aktuelle Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af908-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="af908-108">Da die Cmdlets häufig verwendet werden, haben sie kurze, kanonische Aliase.</span><span class="sxs-lookup"><span data-stu-id="af908-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="af908-109">Es gibt auch einen Satz von Aliasen, der die Cmdlets ähnlichen Eingabeaufforderungsbefehlen zuordnet, und einen weiteren Satz für UNIX-Shell-Befehle.</span><span class="sxs-lookup"><span data-stu-id="af908-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="af908-110">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter implementiert eine Teilmenge der Anbieter-Cmdlets, wie in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="af908-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="af908-111">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="af908-111">cmdlet</span></span>|<span data-ttu-id="af908-112">Kanonischer Alias</span><span class="sxs-lookup"><span data-stu-id="af908-112">Canonical alias</span></span>|<span data-ttu-id="af908-113">Cmd-Alias</span><span class="sxs-lookup"><span data-stu-id="af908-113">cmd alias</span></span>|<span data-ttu-id="af908-114">UNIX-Shell-Alias</span><span class="sxs-lookup"><span data-stu-id="af908-114">UNIX shell alias</span></span>|<span data-ttu-id="af908-115">Description</span><span class="sxs-lookup"><span data-stu-id="af908-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="af908-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="af908-116">**Get-Location**</span></span>|<span data-ttu-id="af908-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="af908-117">**gl**</span></span>|<span data-ttu-id="af908-118">**PWD**</span><span class="sxs-lookup"><span data-stu-id="af908-118">**pwd**</span></span>|<span data-ttu-id="af908-119">**PWD**</span><span class="sxs-lookup"><span data-stu-id="af908-119">**pwd**</span></span>|<span data-ttu-id="af908-120">Ruft den aktuellen Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="af908-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="af908-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="af908-121">**sl**</span></span>|<span data-ttu-id="af908-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="af908-122">**cd, chdir**</span></span>|<span data-ttu-id="af908-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="af908-123">**cd, chdir**</span></span>|<span data-ttu-id="af908-124">Ändert den aktuellen Knoten.</span><span class="sxs-lookup"><span data-stu-id="af908-124">Changes the current node.</span></span>|  
|<span data-ttu-id="af908-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="af908-125">**Get-ChildItem**</span></span>|<span data-ttu-id="af908-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="af908-126">**gci**</span></span>|<span data-ttu-id="af908-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="af908-127">**dir**</span></span>|<span data-ttu-id="af908-128">**ls**</span><span class="sxs-lookup"><span data-stu-id="af908-128">**ls**</span></span>|<span data-ttu-id="af908-129">Listet die am aktuellen Knoten gespeicherten Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="af908-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="af908-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="af908-130">**Get-Item**</span></span>|<span data-ttu-id="af908-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="af908-131">**gi**</span></span>|||<span data-ttu-id="af908-132">Gibt die Eigenschaften des aktuellen Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="af908-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="af908-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="af908-133">**Rename-Item**</span></span>|<span data-ttu-id="af908-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="af908-134">**rni**</span></span>|<span data-ttu-id="af908-135">**Mar**</span><span class="sxs-lookup"><span data-stu-id="af908-135">**rn**</span></span>|<span data-ttu-id="af908-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="af908-136">**ren**</span></span>|<span data-ttu-id="af908-137">Benennt ein Objekt um.</span><span class="sxs-lookup"><span data-stu-id="af908-137">Renames an object.</span></span>|  
|<span data-ttu-id="af908-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="af908-138">**Remove-Item**</span></span>|<span data-ttu-id="af908-139">**Volk**</span><span class="sxs-lookup"><span data-stu-id="af908-139">**ri**</span></span>|<span data-ttu-id="af908-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="af908-140">**del, rd**</span></span>|<span data-ttu-id="af908-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="af908-141">**rm, rmdir**</span></span>|<span data-ttu-id="af908-142">Entfernt ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="af908-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="af908-143">Einige [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Bezeichner (Objektnamen) enthalten Zeichen, die Windows PowerShell in Pfadnamen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="af908-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="af908-144">Weitere Informationen zum Verwenden von Namen, die diese Zeichen enthalten, finden Sie unter [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="af908-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="af908-145">Von Get-ChildItem zurückgegebene SQL Server-Informationen</span><span class="sxs-lookup"><span data-stu-id="af908-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="af908-146">Die von **Get-ChildItem** (oder den zugehörigen Aliasen **dir** und **ls** ) zurückgegebenen Informationen richten sich danach, wo Sie sich in einem SQLSERVER:-Pfad befinden.</span><span class="sxs-lookup"><span data-stu-id="af908-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="af908-147">Pfadposition</span><span class="sxs-lookup"><span data-stu-id="af908-147">Path location</span></span>|<span data-ttu-id="af908-148">Get-ChildItem-Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="af908-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="af908-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="af908-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="af908-150">Gibt den Namen des lokalen Computers zurück.</span><span class="sxs-lookup"><span data-stu-id="af908-150">Returns the name of the local computer.</span></span> <span data-ttu-id="af908-151">Wenn Sie die Verbindung mit Instanzen von [!INCLUDE[ssDE](../includes/ssde-md.md)] auf anderen Computern mithilfe von SMO oder WMI hergestellt haben, werden diese Computer ebenfalls aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="af908-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="af908-152">SQLSERVER:\SQL\\*Computername*</span><span class="sxs-lookup"><span data-stu-id="af908-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="af908-153">Die Liste der Instanzen von [!INCLUDE[ssDE](../includes/ssde-md.md)] auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="af908-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="af908-154">SQLServer: \ SQL \\ *Computername* \\ *instanceName*</span><span class="sxs-lookup"><span data-stu-id="af908-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="af908-155">Die Liste von Objekttypen der höchsten Ebene in der Instanz, wie Endpunkte, Zertifikate und Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="af908-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="af908-156">Objektklassenknoten, z. B. Datenbanken</span><span class="sxs-lookup"><span data-stu-id="af908-156">Object class node, such as Databases</span></span>|<span data-ttu-id="af908-157">Die Liste der Objekte dieses Typs, z. B. die Liste von Datenbanken: master, model, AdventureWorks20008R2.</span><span class="sxs-lookup"><span data-stu-id="af908-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="af908-158">Objektnamenknoten, z.B. AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="af908-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="af908-159">Die Liste von im Objekt enthaltenen Objekttypen.</span><span class="sxs-lookup"><span data-stu-id="af908-159">The list of object types contained within the object.</span></span> <span data-ttu-id="af908-160">Zum Beispiel würden in einer Datenbank Objekttypen wie Tabellen und Sichten aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af908-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="af908-161">Standardmäßig listet **Get-ChildItem** keine Systemobjekte auf.</span><span class="sxs-lookup"><span data-stu-id="af908-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="af908-162">Verwenden Sie den Parameter *Force* , um Systemobjekte anzuzeigen, wie z. B. die Objekte im **sys** -Schema.</span><span class="sxs-lookup"><span data-stu-id="af908-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="af908-163">Benutzerdefinierte Laufwerke</span><span class="sxs-lookup"><span data-stu-id="af908-163">Custom Drives</span></span>  
 <span data-ttu-id="af908-164">Mit Windows PowerShell können Benutzer virtuelle Laufwerke definieren, die als PowerShell-Laufwerke bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="af908-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="af908-165">Diese werden über die Startknoten einer Pfadanweisung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="af908-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="af908-166">Sie werden in der Regel verwendet, um Pfade, die häufig eingegeben werden, zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="af908-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="af908-167">SQLSERVER: Pfade können lang werden, somit viel Platz im Windows PowerShell-Fenster einnehmen und umfangreiche Eingaben erfordern.</span><span class="sxs-lookup"><span data-stu-id="af908-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="af908-168">Wenn Sie vorhaben, viel mit einem bestimmten Pfadknoten zu arbeiten, können Sie ein benutzerdefiniertes Windows PowerShell-Laufwerk definieren, das dem Knoten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="af908-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="af908-169">Verwenden von PowerShell-Cmdlet-Aliasen</span><span class="sxs-lookup"><span data-stu-id="af908-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="af908-170">**Verwenden eines Cmdlet-Alias**</span><span class="sxs-lookup"><span data-stu-id="af908-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="af908-171">Statt einen vollständigen Cmdlet-Namen einzugeben, geben Sie einen kürzeren Alias ein, oder geben Sie einen ein, der einem bekannten, an der Eingabeaufforderung einzugebenden Befehl entspricht.</span><span class="sxs-lookup"><span data-stu-id="af908-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="af908-172">Beispiel für einen Alias (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="af908-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="af908-173">Sie können beispielsweise einen der folgenden Sätze von Cmdlets oder Aliasen verwenden, um eine Auflistung der Ihnen zur Verfügung stehenden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanzen abzurufen, indem Sie zum "SQLSERVER:\SQL"-Ordner navigieren und die Liste der untergeordneten Elemente des Ordners anfordern:</span><span class="sxs-lookup"><span data-stu-id="af908-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="af908-174">Verwenden von Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="af908-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="af908-175">Zurückgeben von Informationen mit Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="af908-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="af908-176">Navigieren Sie zu dem Knoten, für den Sie eine Liste von untergeordneten Elementen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="af908-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="af908-177">Führen Sie Get-ChildItem aus, um die Liste abzurufen.</span><span class="sxs-lookup"><span data-stu-id="af908-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="af908-178">Beispiel für Get-ChildItem (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="af908-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="af908-179">In diesen Beispielen werden die von Get-ChildItem für andere Knoten in einem SQL Server-Anbieterpfad zurückgegebenen Informationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="af908-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="af908-180">Erstellen eines benutzerdefinierten Laufwerks</span><span class="sxs-lookup"><span data-stu-id="af908-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="af908-181">Erstellen und Verwenden eines benutzerdefinierten Laufwerks</span><span class="sxs-lookup"><span data-stu-id="af908-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="af908-182">Verwenden Sie `New-PSDrive`, um ein benutzerdefiniertes Laufwerk zu definieren.</span><span class="sxs-lookup"><span data-stu-id="af908-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="af908-183">Verwenden Sie den `Root`-Parameter, um den Pfad anzugeben, der durch den Namen des benutzerdefinierten Laufwerks dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="af908-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="af908-184">Verweisen Sie in Pfadnavigations-Cmdlets, wie z. B. `Set-Location`, auf den Namen des benutzerdefinierten Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="af908-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="af908-185">Beispiel für ein benutzerdefiniertes Laufwerk (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="af908-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="af908-186">In diesem Beispiel wird ein virtuelles Laufwerk mit dem Namen AWDB erstellt, das dem Knoten für eine bereitgestellte Kopie der Beispieldatenbank AdventureWorks2012 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="af908-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="af908-187">Das virtuelle Laufwerk wird dann verwendet, um zu einer Tabelle in der Datenbank zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="af908-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="af908-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af908-188">See Also</span></span>  
 <span data-ttu-id="af908-189">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="af908-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="af908-190">[Arbeiten mit SQL Server PowerShell Pfaden](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="af908-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="af908-191">[Konvertieren von URNs in SQL Server Anbieter Pfade](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="af908-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="af908-192">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="af908-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
