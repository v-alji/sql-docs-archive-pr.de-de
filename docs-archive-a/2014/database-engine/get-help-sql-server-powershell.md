---
title: Aufrufen der SQL Server PowerShell-Hilfe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701583"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="c2bd5-102">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2bd5-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="c2bd5-103">Es stehen mehrere Informationsquellen zur Verwendung des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieters für Windows PowerShell und Cmdlets zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="c2bd5-104">Dazu gehört auch die Hilfe, die in der Windows PowerShell-Umgebung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="c2bd5-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c2bd5-105">Before You Begin</span></span>  
 <span data-ttu-id="c2bd5-106">Informationen zu Windows PowerShell finden Sie unter [Erste Schritte mit Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="c2bd5-107">Eine Übersicht über die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Cmdlets und -Anbieter finden Sie unter [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="c2bd5-108">Hilfe in der Windows PowerShell-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c2bd5-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="c2bd5-109">Verwenden Sie das Cmdlet **Get-Help** , um Hilfe in der Windows PowerShell-Umgebung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="c2bd5-110">**Get-Help** stellt grundlegende Hilfe zur Windows PowerShell-Sprache und den verschiedenen in Windows PowerShell verfügbaren Cmdlets und Anbietern bereit.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="c2bd5-111">Weitere Informationen zur Verwendung von **Get-Help**finden Sie unter [Abrufen von Hilfeinformationen: Get-Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="c2bd5-112">SQL Server PowerShell-Anbieterhilfe</span><span class="sxs-lookup"><span data-stu-id="c2bd5-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="c2bd5-113">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Anbieter implementiert mehrere Ordner auf einem virtuellen SQLSERVER-Laufwerk, z. B. die Ordner SQLSERVER:\SQL und SQLSERVER:\DAC.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="c2bd5-114">Jeder Ordner ist einem der SQL Server-Verwaltbarkeitsobjektmodelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="c2bd5-115">Während Sie die jedem Knoten zugeordneten Methoden und Eigenschaften in einem SQL Server-Pfad auflisten können, können Sie dafür keine Hilfe in der PowerShell-Umgebung abrufen.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="c2bd5-116">Eine Tabelle mit den Ordnern mit Links zur zugeordneten Referenzdokumentation zur Programmierung finden Sie unter [SQL Server PowerShell-Anbieter](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="c2bd5-117">Invoke-Sqlcmd-Hilfe</span><span class="sxs-lookup"><span data-stu-id="c2bd5-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="c2bd5-118">Das Cmdlet **Invoke-Sqlcmd** akzeptiert alle Abfragen oder Skriptdateien als Eingabe, die vom **sqlcmd** -Hilfsprogramm ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="c2bd5-119">Sie können mit **Get-Help** Informationen zu **Invoke-Sqlcmd** und den zugehörigen Parametern abrufen. **Get-Help** kann jedoch nicht für die **sqlcmd** -Abfragen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="c2bd5-120">Die Eingaben *-Query* oder *-QueryFromFile* können Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="c2bd5-121">**sqlcmd** -Variablen und -Befehle.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="c2bd5-122">Informationen zu diesen Variablen und Befehlen finden Sie unter [sqlcmd (Hilfsprogramm)](../tools/sqlcmd-utility.md)im Abschnitt „Hinweise“.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="c2bd5-123">-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-123">statements.</span></span> <span data-ttu-id="c2bd5-124">Weitere Informationen über die [!INCLUDE[tsql](../includes/tsql-md.md)]-Sprache finden Sie unter [Transact-SQL-Referenz &#40;Datenbank-Engine&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="c2bd5-125">XQuery-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-125">XQuery statements.</span></span> <span data-ttu-id="c2bd5-126">Weitere Informationen zu der von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] unterstützten XQuery-Sprache finden Sie unter [XQuery-Sprachreferenz &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="c2bd5-127">Aufrufen von Hilfe für ein SQL Server-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c2bd5-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="c2bd5-128">**So erhalten Sie Hilfe zu einem Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c2bd5-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="c2bd5-129">Führen Sie "Get-Help" aus, und geben Sie dabei den Namen des Cmdlet und die Ebene der Hilfe an, die zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="c2bd5-130">Beispiel: Cmdlet Get-Help</span><span class="sxs-lookup"><span data-stu-id="c2bd5-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="c2bd5-131">In den folgenden Beispielen werden verschiedene Ebenen der Hilfe für **Invoke-Sqlcmd**zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="c2bd5-132">Abrufen einer Liste von Anbietern</span><span class="sxs-lookup"><span data-stu-id="c2bd5-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="c2bd5-133">So rufen Sie eine Liste aktiver Anbieter ab</span><span class="sxs-lookup"><span data-stu-id="c2bd5-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="c2bd5-134">Führen Sie "Get-Help" aus, und geben Sie dabei die Anbieterkategorie an.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="c2bd5-135">Weitere Informationen darüber, wie Sie in Windows PowerShell Hilfe zu den Anbietern erhalten können, finden Sie unter [Laufwerke und Anbieter](https://go.microsoft.com/fwlink/?LinkId=102137).</span><span class="sxs-lookup"><span data-stu-id="c2bd5-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="c2bd5-136">Beispiel: Abrufen einer Liste von Anbietern</span><span class="sxs-lookup"><span data-stu-id="c2bd5-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="c2bd5-137">Mit diesem Code wird eine Liste der Anbieter, die gerade in der Windows PowerShell-Sitzung aktiviert sind, zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="c2bd5-138">Aufrufen von Hilfe zum SQL Server-Anbieter</span><span class="sxs-lookup"><span data-stu-id="c2bd5-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="c2bd5-139">**So rufen Sie Hilfe zum Anbieter auf**</span><span class="sxs-lookup"><span data-stu-id="c2bd5-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="c2bd5-140">Ausführen von "Get-Help" mit Angabe des Namens "SQLServer"</span><span class="sxs-lookup"><span data-stu-id="c2bd5-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="c2bd5-141">Beispiel: Aufrufen von Hilfe zum SQL Server-Anbieter</span><span class="sxs-lookup"><span data-stu-id="c2bd5-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="c2bd5-142">In diesem Beispiel werden grundlegende Informationen zum [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieter zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="c2bd5-143">Auflisten von Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c2bd5-143">List Methods and Properties</span></span>  
 <span data-ttu-id="c2bd5-144">**So listen Sie die Methoden und die Eigenschaften für einen Knoten in einem SQL Server-Anbieterpfad auf**</span><span class="sxs-lookup"><span data-stu-id="c2bd5-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="c2bd5-145">Verweisen Sie mit CD auf einen Knoten im SQL Server-Pfad, oder erstellen Sie einen Variablensatz zu diesem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="c2bd5-146">Führen **Sie das Get-Member** -Cmdlet mit dem-Type-Parameter entweder auf Methoden oder Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="c2bd5-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="c2bd5-147">Beispiele: Auflisten von Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c2bd5-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="c2bd5-148">In diesem Beispiel sind die für den Datenbankknoten unterstützten Methoden aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="c2bd5-149">In diesem Beispiel werden die Eigenschaften für eine Variable aufgelistet, die auf ein SMO-Tabellenobjekt festgelegt wurde:</span><span class="sxs-lookup"><span data-stu-id="c2bd5-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2bd5-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2bd5-150">See Also</span></span>  
 <span data-ttu-id="c2bd5-151">[SQL Server PowerShell Anbieter](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="c2bd5-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="c2bd5-152">Verwenden der Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c2bd5-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
