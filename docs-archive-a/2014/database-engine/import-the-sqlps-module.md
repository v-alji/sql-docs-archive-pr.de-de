---
title: Importieren des SQLPS-Moduls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718703"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="9b707-102">Importieren des SQLPS-Moduls</span><span class="sxs-lookup"><span data-stu-id="9b707-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="9b707-103">Es wird empfohlen, zur Verwaltung von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] über PowerShell das `sqlps`-Modul in eine Windows PowerShell 2.0-Umgebung zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9b707-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="9b707-104">Das Modul lädt und registriert die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Snap-Ins und -Verwaltbarkeitsassemblys.</span><span class="sxs-lookup"><span data-stu-id="9b707-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="9b707-105">Vorbereitungen **:**[Sicherheit](#Security)  </span><span class="sxs-lookup"><span data-stu-id="9b707-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="9b707-106">**So laden Sie das Modul:**  [Laden des sqlps-Moduls](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="9b707-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="9b707-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9b707-107">Before You Begin</span></span>  
 <span data-ttu-id="9b707-108">Nach dem Importieren des `sqlps`-Moduls in Windows PowerShell stehen Ihnen folgende Möglichkeiten zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="9b707-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="9b707-109">Interaktives Ausführen von Windows PowerShell-Befehlen</span><span class="sxs-lookup"><span data-stu-id="9b707-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="9b707-110">Ausführen von Windows PowerShell-Skriptdateien</span><span class="sxs-lookup"><span data-stu-id="9b707-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="9b707-111">Ausführen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9b707-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="9b707-112">Verwenden Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anbieterpfade, um durch die Hierarchie der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="9b707-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="9b707-113">Verwenden Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Verwaltbarkeit-Objektmodelle (z. B. Microsoft.SqlServer.Management.Smo), um [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Objekte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9b707-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b707-114">Die in den Namen von zwei SQL Server-Cmdlets (`Encode-Sqlname` und `Decode-Sqlname`) verwendeten Verben entsprechen nicht den genehmigten Verben für Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b707-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="9b707-115">Dies hat keine Auswirkungen auf den Vorgang, aber von Windows PowerShell wird eine Warnung ausgegeben, wenn das `sqlps`-Modul in eine Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="9b707-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b707-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9b707-116">Security</span></span>  
 <span data-ttu-id="9b707-117">Standardmäßig wird Windows PowerShell mit auf **Restricted**festgelegter Skriptausführungsrichtlinie ausgeführt. Dadurch wird die Ausführung von Windows PowerShell-Skripts verhindert.</span><span class="sxs-lookup"><span data-stu-id="9b707-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="9b707-118">Zum Laden des `sqlps`-Moduls können Sie das `Set-ExecutionPolicy`-Cmdlet verwenden, um die Ausführung signierter Skripts oder beliebiger anderer Skripts zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9b707-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="9b707-119">Führen Sie nur Skripts aus vertrauenswürdigen Quellen aus, und sichern Sie alle Eingabe- und Ausgabedateien, indem Sie die geeigneten NTFS-Berechtigungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b707-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="9b707-120">Weitere Informationen zum Aktivieren von Windows PowerShell-Skripts finden Sie unter [Ausführen der Windows PowerShell-Skripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span><span class="sxs-lookup"><span data-stu-id="9b707-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a><span data-ttu-id="9b707-121">Laden des sqlps-Moduls</span><span class="sxs-lookup"><span data-stu-id="9b707-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="9b707-122">So laden Sie das sqlps-Modul in Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b707-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="9b707-123">Verwenden Sie das `Set-ExecutionPolicy`-Cmdlet, um die entsprechende Skriptausführungsrichtlinie festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9b707-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="9b707-124">Verwenden `Import-Module` Sie das Cmdlet, um das sqlps-Modul zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9b707-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="9b707-125">Geben Sie den `DisableNameChecking`-Parameter an, wenn Sie die Warnung zu `Encode-Sqlname` und `Decode-Sqlname` unterdrücken möchten.</span><span class="sxs-lookup"><span data-stu-id="9b707-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="9b707-126">Beispiel (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="9b707-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="9b707-127">In diesem Beispiel wird das `sqlps`-Modul bei deaktivierter Namensüberprüfung geladen.</span><span class="sxs-lookup"><span data-stu-id="9b707-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="9b707-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b707-128">See Also</span></span>  
 <span data-ttu-id="9b707-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="9b707-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="9b707-130">[SQL Server PowerShell Anbieter](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="9b707-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="9b707-131">Verwenden der Datenbank-Engine-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9b707-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
