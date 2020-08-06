---
title: Power Pivot-Konfiguration mit Windows PowerShell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4d83e53e-04f1-417d-9039-d9e81ae0483d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83b42da3e676a291bb021c02ee52e9a810207397
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621199"
---
# <a name="powerpivot-configuration-using-windows-powershell"></a><span data-ttu-id="348e0-102">PowerPivot-Konfiguration mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="348e0-102">PowerPivot Configuration using Windows PowerShell</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="348e0-103">enthält Windows PowerShell-Cmdlets, mit denen Sie eine Installation von [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="348e0-103">includes Windows PowerShell cmdlets that you can use to configure an installation of [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)].</span></span> <span data-ttu-id="348e0-104">Für die vollständige Konfiguration einer Installation mit PowerShell ist die Verwendung von SharePoint-Cmdlets und PowerPivot für SharePoint-Cmdlets erforderlich.</span><span class="sxs-lookup"><span data-stu-id="348e0-104">To fully configure an installation with PowerShell requires the use of both SharePoint cmdlets and PowerPivot for SharePoint cmdlets.</span></span> <span data-ttu-id="348e0-105">Ein Großteil der Konfiguration kann mithilfe eines der [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] -Tools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="348e0-105">A majority of configuration can be completed using one of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] tools.</span></span> <span data-ttu-id="348e0-106">Weitere Informationen zu den Tools finden Sie unter [Power Pivot-Konfigurationstools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="348e0-106">For more information on the tools, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="348e0-107">Für eine SharePoint 2010-Farm muss SharePoint 2010 SP1 installiert sein, bevor Sie PowerPivot für SharePoint oder eine SharePoint-Farm konfigurieren können, die einen [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]"-Datenbankserver verwendet.</span><span class="sxs-lookup"><span data-stu-id="348e0-107">For a SharePoint 2010 farm, SharePoint 2010 SP1 must be installed before you can configure either PowerPivot for SharePoint, or a SharePoint farm that uses a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] database server.</span></span> <span data-ttu-id="348e0-108">Wenn Sie das Service Pack noch nicht installiert haben, installieren Sie es, bevor Sie mit der Serverkonfiguration beginnen.</span><span class="sxs-lookup"><span data-stu-id="348e0-108">If you have not yet installed the service pack, install it before you begin configuring the server.</span></span>  
  
## <a name="benefits-of-configuring-powerpivot-for-sharepoint-using-powershell"></a><span data-ttu-id="348e0-109">Vorteile der Konfiguration von PowerPivot für SharePoint mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="348e0-109">Benefits of Configuring PowerPivot for SharePoint Using PowerShell</span></span>  
 <span data-ttu-id="348e0-110">Sie können Windows PowerShell-Skriptdateien (.ps1) erstellen, um Konfigurationstasks zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="348e0-110">You can build Windows PowerShell script (.ps1) files to automate configuration tasks.</span></span> <span data-ttu-id="348e0-111">Dieser Ansatz wird empfohlen, wenn Sie skriptbasierte Installation und Konfigurationsschritte benötigen, die Sie auf jedem Server ausführen können.</span><span class="sxs-lookup"><span data-stu-id="348e0-111">This approach is recommended if you require scripted installation and configuration steps that you can run on any server.</span></span> <span data-ttu-id="348e0-112">Sie benötigen ein solches Skript möglicherweise als Teil eines Notfallwiederherstellungsplans zum Neuerstellen eines Servers im Fall eines Hardwarefehlers.</span><span class="sxs-lookup"><span data-stu-id="348e0-112">You might require such a script as part of a disaster recovery plan for rebuilding a server in the event of a hardware failure.</span></span>  
  
## <a name="view-a-list-of-the-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="348e0-113">Anzeigen einer Liste der PowerPivot-Cmdlets auf einem Server</span><span class="sxs-lookup"><span data-stu-id="348e0-113">View a list of the PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="348e0-114">Informationen zu den Inhalten und Beispielen für die [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] Cmdlets finden Sie unter [PowerShell-Referenz für PowerPivot für SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span><span class="sxs-lookup"><span data-stu-id="348e0-114">To see content and examples of the [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] cmdlets, see [PowerShell Reference for PowerPivot for SharePoint](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint).</span></span>  
  
 <span data-ttu-id="348e0-115">So zeigen Sie mithilfe von PowerShell eine Liste der PowerPivot-Cmdlets an</span><span class="sxs-lookup"><span data-stu-id="348e0-115">To use PowerShell to view a list of the PowerPivot cmdlets:</span></span>  
  
1.  <span data-ttu-id="348e0-116">Öffnen Sie die SharePoint-Verwaltungsshell unter Verwendung der Option **Als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="348e0-116">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="348e0-117">Geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="348e0-117">Enter the following command:</span></span>  
  
    ```powershell
    Get-Help *powerpivot*  
    ```  
  
     <span data-ttu-id="348e0-118">Eine Liste von Cmdlets sollte angezeigt werden, die im Cmdlet-Namen PowerPivot enthalten.</span><span class="sxs-lookup"><span data-stu-id="348e0-118">You should see a list of cmdlets that include PowerPivot in the cmdlet name.</span></span> <span data-ttu-id="348e0-119">Beispiel: `Get-PowerPivotServiceApplication`.</span><span class="sxs-lookup"><span data-stu-id="348e0-119">For example `Get-PowerPivotServiceApplication`.</span></span> <span data-ttu-id="348e0-120">Wie viele Cmdlets verfügbar sind, hängt von der verwendeten Analysis Services-Version ab.</span><span class="sxs-lookup"><span data-stu-id="348e0-120">The number of cmdlets available depends on the version of Analysis Services you are using.</span></span>  
  
    -   <span data-ttu-id="348e0-121">10 Cmdlets mit SQL Server 2012 SP1 Analysis Services-Server, der im SharePoint-Modus konfiguriert ist, und SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="348e0-121">10 cmdlets with SQL Server 2012 SP1 Analysis Services server configured in SharePoint mode, and SharePoint 2013.</span></span> <span data-ttu-id="348e0-122">Die 2012 SP1-Version verwendet eine neue Architektur, die die Ausführung des Analysis-Servers außerhalb der SharePoint-Farm zulässt und weniger Windows PowerShell-Cmdlets für die Verwaltung erfordert.</span><span class="sxs-lookup"><span data-stu-id="348e0-122">The 2012 SP1 version utilizes a new architecture that allows the Analysis Server to run outside the SharePoint farm and requires fewer management Windows PowerShell cmdlets.</span></span>  
  
    -   <span data-ttu-id="348e0-123">17 Cmdlets mit SQL Server 2012 Analysis Services-Server, der im SharePoint-Modus konfiguriert ist, und SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="348e0-123">17 cmdlets with SQL Server 2012 Analysis Services server configured in SharePoint mode, and SharePoint 2010.</span></span>  
  
     <span data-ttu-id="348e0-124">Wenn keine Befehle in der Liste zurückgegeben werden oder eine Fehlermeldung wie "" angezeigt `get-help could not find *powerpivot* in a help file in this session.` wird, finden Sie im nächsten Abschnitt dieses Themas Anweisungen zum Aktivieren der Power Pivot-Cmdlets auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="348e0-124">If no commands are returned in the list or you see an error message similar to "`get-help could not find *powerpivot* in a help file in this session.`", see the next section in this topic for instructions on how to enable the PowerPivot cmdlets on the server.</span></span>  
  
     <span data-ttu-id="348e0-125">Alle Cmdlets verfügen über eine Onlinehilfe.</span><span class="sxs-lookup"><span data-stu-id="348e0-125">All cmdlets have online help.</span></span> <span data-ttu-id="348e0-126">Im folgenden Beispiel wird erläutert, wie die Onlinehilfe für das `New-PowerPivotServiceApplication`-Cmdlet angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="348e0-126">The following example shows how to view the online help for the `New-PowerPivotServiceApplication` cmdlet:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Full  
    ```  
  
     <span data-ttu-id="348e0-127">Oder verwenden Sie die folgende Syntax, um nur die Beispiele anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="348e0-127">Alternatively, to view just the examples, use the following syntax:</span></span>  
  
    ```powershell
    Get-Help new-powerpivotserviceapplication -Example  
    ```  
  
## <a name="enable-powerpivot-cmdlets-on-a-server"></a><span data-ttu-id="348e0-128">Aktivieren von Power Pivot-Cmdlets auf einem Server</span><span class="sxs-lookup"><span data-stu-id="348e0-128">Enable PowerPivot Cmdlets on a Server</span></span>  
 <span data-ttu-id="348e0-129">PowerPivot-Cmdlets sind verfügbar, nachdem Sie PowerPivot für SharePoint installiert und die Farmlösung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="348e0-129">PowerPivot cmdlets are available after you install PowerPivot for SharePoint and deploy the farm solution.</span></span> <span data-ttu-id="348e0-130">Die Lösungen werden bereitgestellt, wenn Sie das PowerPivot-Konfigurationstool ausführen.</span><span class="sxs-lookup"><span data-stu-id="348e0-130">The solutions are deployed when you ran the PowerPivot Configuration tool.</span></span> <span data-ttu-id="348e0-131">Führen Sie folgende Schritte aus, um die Verwendung von Cmdlets zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="348e0-131">Follow these steps to enable the use of cmdlets:</span></span>  
  
1.  <span data-ttu-id="348e0-132">Öffnen Sie die SharePoint-Verwaltungsshell unter Verwendung der Option **Als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="348e0-132">Open SharePoint Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="348e0-133">Führen Sie das erste Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="348e0-133">Run the first cmdlet:</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="348e0-134">Das Cmdlet gibt den Namen der Lösung, deren Lösungs-ID und "Deployed=False" zurück.</span><span class="sxs-lookup"><span data-stu-id="348e0-134">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="348e0-135">Im nächsten Schritt wird die Lösung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="348e0-135">In the next step, you deploy the solution.</span></span>  
  
3.  <span data-ttu-id="348e0-136">Führen Sie das zweite Cmdlet aus, um die Lösung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="348e0-136">Run the second cmdlet to deploy the solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
4.  <span data-ttu-id="348e0-137">Schließen Sie das Fenster.</span><span class="sxs-lookup"><span data-stu-id="348e0-137">Close the window.</span></span> <span data-ttu-id="348e0-138">Öffnen Sie es erneut mit der Option **Als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="348e0-138">Reopen it, again using the **Run as Administrator** option.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="348e0-139">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="348e0-139">Related Content</span></span>  
 [<span data-ttu-id="348e0-140">PowerPivot-Serververwaltung und -konfiguration in der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="348e0-140">PowerPivot Server Administration and Configuration in Central Administration</span></span>](power-pivot-server-administration-and-configuration-in-central-administration.md)  
  
 [<span data-ttu-id="348e0-141">PowerPivot Configuration Tools</span><span class="sxs-lookup"><span data-stu-id="348e0-141">PowerPivot Configuration Tools</span></span>](power-pivot-configuration-tools.md)  
  
 [<span data-ttu-id="348e0-142">PowerShell-Referenz für PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="348e0-142">PowerShell Reference for PowerPivot for SharePoint</span></span>](/sql/analysis-services/powershell/powershell-reference-for-power-pivot-for-sharepoint)  
