---
title: Bereitstellen von Power Pivot-Lösungen in SharePoint | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f202a2b7-34e0-43aa-90d5-c9a085a37c32
author: minewiskan
ms.author: owend
ms.openlocfilehash: 043647988598f932b70cc06e6bb5492d66864372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620012"
---
# <a name="deploy-powerpivot-solutions-to-sharepoint"></a><span data-ttu-id="4d775-102">Bereitstellen von PowerPivot-Lösungen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="4d775-102">Deploy PowerPivot Solutions to SharePoint</span></span>
  <span data-ttu-id="4d775-103">Verwenden Sie die folgenden Anweisungen, um zwei Lösungspakete, die einer SharePoint Server 2010-Umgebung PowerPivot-Funktionen hinzufügen, manuell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d775-103">Use the following instructions to manually deploy two solution packages that add PowerPivot features to a SharePoint Server 2010 environment.</span></span> <span data-ttu-id="4d775-104">Das Bereitstellen der Lösungen ist ein erforderlicher Schritt für die Konfiguration von PowerPivot für SharePoint auf einem SharePoint 2010-Server.</span><span class="sxs-lookup"><span data-stu-id="4d775-104">Deploying the solutions is a required step for configuring PowerPivot for SharePoint on a SharePoint 2010 server.</span></span> <span data-ttu-id="4d775-105">Die komplette Liste der erforderlichen Schritte finden Sie unter [Power Pivot-Server Verwaltung und-Konfiguration in der zentral Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="4d775-105">To view the complete list of required steps, see [PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md).</span></span>  
  
 <span data-ttu-id="4d775-106">Alternativ können Sie die Lösungen mithilfe des PowerPivot-Konfigurationstools bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d775-106">Alternatively, you can use the PowerPivot Configuration Tool to deploy the solutions.</span></span> <span data-ttu-id="4d775-107">Die Verwendung des Konfigurationstools ist für eine einzelne Serverinstallation einfacher und effizienter, aber vielleicht möchten Sie die Zentraladministration und PowerShell verwenden, wenn Sie es vorziehen, mit einem vertrauten Tool zu arbeiten oder wenn Sie mehrere Funktionen gleichzeitig konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4d775-107">Using the configuration tool is easier and more efficient for a single server installation, but you might want to use Central Administration and PowerShell if you prefer using a familiar tool or if you are configuring multiple features at the same time.</span></span> <span data-ttu-id="4d775-108">Weitere Informationen zur Verwendung des-Konfigurationstools finden Sie unter [Power Pivot-Konfigurationstools](power-pivot-configuration-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d775-108">For more information about using the configuration tool, see [PowerPivot Configuration Tools](power-pivot-configuration-tools.md).</span></span>  
  
 <span data-ttu-id="4d775-109">Vor dem Bereitstellen der Lösungen müssen Sie zuerst mithilfe der SQL Server 2012-Installationsmedien PowerPivot für SharePoint installieren.</span><span class="sxs-lookup"><span data-stu-id="4d775-109">Before deploying the solutions, you must first install PowerPivot for SharePoint using the SQL Server 2012 installation media.</span></span> <span data-ttu-id="4d775-110">SQL Server-Setup installiert die Lösungspakete, die Sie gleich bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="4d775-110">SQL Server Setup installs the solution packages that you are about to deploy.</span></span>  
  
 <span data-ttu-id="4d775-111">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="4d775-111">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="4d775-112">Voraussetzung: überprüfen, ob die Webanwendung Authentifizierung im klassischen Modus</span><span class="sxs-lookup"><span data-stu-id="4d775-112">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>](#bkmk_classic)  
  
 [<span data-ttu-id="4d775-113">Schritt 1: Bereitstellen der Farmlösung</span><span class="sxs-lookup"><span data-stu-id="4d775-113">Step 1: Deploy the Farm Solution</span></span>](#bkmk_farm)  
  
 [<span data-ttu-id="4d775-114">Schritt 2: Bereitstellen der PowerPivot-Webanwendungslösung in der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="4d775-114">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>](#deployCA)  
  
 [<span data-ttu-id="4d775-115">Schritt 3: Bereitstellen der PowerPivot-Webanwendungslösung auf anderen Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="4d775-115">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>](#deployUI)  
  
 [<span data-ttu-id="4d775-116">Erneutes Bereitstellen oder Zurückziehen der Lösung</span><span class="sxs-lookup"><span data-stu-id="4d775-116">Redeploy or retract the Solution</span></span>](#retract)  
  
 [<span data-ttu-id="4d775-117">Informationen zu den PowerPivot-Lösungen</span><span class="sxs-lookup"><span data-stu-id="4d775-117">About the PowerPivot Solutions</span></span>](#intro)  
  
##  <a name="prerequisite-verify-the-web-application-uses-classic-mode-authentication"></a><a name="bkmk_classic"></a> <span data-ttu-id="4d775-118">Voraussetzung: Überprüfen, ob die Webanwendung den klassischen Authentifizierungsmodus verwendet</span><span class="sxs-lookup"><span data-stu-id="4d775-118">Prerequisite: Verify the Web Application uses Classic Mode Authentication</span></span>  
 <span data-ttu-id="4d775-119">PowerPivot für SharePoint wird nur für Webanwendungen unterstützt, die den klassischen Authentifizierungsmodus in Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d775-119">PowerPivot for SharePoint is only supported for web applications that use Windows-classic mode authentication.</span></span> <span data-ttu-id="4d775-120">Um zu überprüfen, ob die Anwendung den klassischen Modus verwendet, führen Sie das folgende PowerShell-Cmdlet in der **SharePoint 2010-Verwaltungsshell**aus, und ersetzen Sie `http://<top-level site name>` dabei durch den Namen Ihrer SharePoint-Website:</span><span class="sxs-lookup"><span data-stu-id="4d775-120">To check whether the application uses Classic mode, run the following PowerShell cmdlet from the **SharePoint 2010 Management Shell**, replacing `http://<top-level site name>` with the name of your SharePoint site:</span></span>  
  
```powershell
Get-SPWebApplication http://<top-level site name> | Format-List UseClaimsAuthentication  
```  
  
 <span data-ttu-id="4d775-121">Der Rückgabewert sollte **FALSE**sein.</span><span class="sxs-lookup"><span data-stu-id="4d775-121">The return value should be **false**.</span></span> <span data-ttu-id="4d775-122">Wenn dies der **Fall**ist, können Sie mit dieser Webanwendung nicht auf Power Pivot-Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4d775-122">If it is **true**, you cannot access PowerPivot data with this web application.</span></span>  
  
##  <a name="step-1-deploy-the-farm-solution"></a><a name="bkmk_farm"></a><span data-ttu-id="4d775-123">Schritt 1: Bereitstellen der Farm Lösung</span><span class="sxs-lookup"><span data-stu-id="4d775-123">Step 1: Deploy the Farm Solution</span></span>  
 <span data-ttu-id="4d775-124">In diesem Abschnitt erfahren Sie, wie Sie Lösungen mithilfe der PowerShell bereitstellen können. Sie können aber auch das PowerPivot-Konfigurationstool verwenden, um diese Aufgabe abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4d775-124">This section shows you how to deploy solutions using PowerShell, but you can also use the PowerPivot Configuration Tool to complete this task.</span></span> <span data-ttu-id="4d775-125">Weitere Informationen finden Sie unter [konfigurieren oder reparieren PowerPivot für SharePoint 2010 &#40;Power Pivot-Konfigurationstools&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="4d775-125">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="4d775-126">Diese Aufgabe muss nur einmal ausgeführt werden, nachdem Sie PowerPivot für SharePoint installiert haben.</span><span class="sxs-lookup"><span data-stu-id="4d775-126">This task only needs to be performed once, after you install PowerPivot for SharePoint.</span></span>  
  
1.  <span data-ttu-id="4d775-127">Öffnen Sie auf einem Server mit einer Installation von PowerPivot für SharePoint eine SharePoint 2010-Verwaltungsshell mithilfe der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="4d775-127">On a server that has an installation of PowerPivot for SharePoint, open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="4d775-128">Führen Sie das folgende Cmdlet aus, um die Farmlösung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4d775-128">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotFarm.wsp"  
    ```  
  
     <span data-ttu-id="4d775-129">Das Cmdlet gibt den Namen der Lösung, deren Lösungs-ID und "Deployed=False" zurück.</span><span class="sxs-lookup"><span data-stu-id="4d775-129">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="4d775-130">Im nächsten Schritt wird die Lösung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d775-130">In the next step, you will deploy the solution.</span></span>  
  
3.  <span data-ttu-id="4d775-131">Führen Sie das nächste Cmdlet aus, um die Farmlösung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="4d775-131">Run the next cmdlet to deploy the farm solution:</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotFarm.wsp -GACDeployment -Force  
    ```  
  
##  <a name="step-2-deploy-the-powerpivot-web-application-solution-to-central-administration"></a><a name="deployCA"></a><span data-ttu-id="4d775-132">Schritt 2: Bereitstellen der Power Pivot-Webanwendungslösung in der zentral Administration</span><span class="sxs-lookup"><span data-stu-id="4d775-132">Step 2: Deploy the PowerPivot Web Application Solution to Central Administration</span></span>  
 <span data-ttu-id="4d775-133">Nach dem Bereitstellen der Farmlösung müssen Sie die Webanwendungslösung in der Zentraladministration bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4d775-133">After you deploy the farm solution, you must deploy the Web application solution to Central Administration.</span></span> <span data-ttu-id="4d775-134">Durch diesen Schritt wird das PowerPivot-Management-Dashboard der Zentraladministration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d775-134">This step adds the PowerPivot Management Dashboard to Central Administration.</span></span>  
  
1.  <span data-ttu-id="4d775-135">Öffnen Sie eine SharePoint 2010-Verwaltungsshell mithilfe der Option **Als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="4d775-135">Open a SharePoint 2010 Management Shell using the **Run as Administrator** option.</span></span>  
  
2.  <span data-ttu-id="4d775-136">Führen Sie das nächste Cmdlet aus, um einen Verweis auf die Zentraladministration zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4d775-136">Run the following cmdlet to create a reference to Central Administration:</span></span>  
  
    ```powershell
    $centralAdmin = $(Get-SPWebApplication -IncludeCentralAdministration | Where { $_.IsAdministrationWebApplication -eq $TRUE})  
    ```  
  
3.  <span data-ttu-id="4d775-137">Führen Sie das folgende Cmdlet aus, um die Farmlösung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4d775-137">Run the following cmdlet to add the farm solution.</span></span>  
  
    ```powershell
    Add-SPSolution -LiteralPath "C:\Program Files\Microsoft SQL Server\110\Tools\PowerPivotTools\ConfigurationTool\Resources\PowerPivotWebApp.wsp"  
    ```  
  
     <span data-ttu-id="4d775-138">Das Cmdlet gibt den Namen der Lösung, deren Lösungs-ID und "Deployed=False" zurück.</span><span class="sxs-lookup"><span data-stu-id="4d775-138">The cmdlet returns the name of the solution, its solution ID, and Deployed=False.</span></span> <span data-ttu-id="4d775-139">Im nächsten Schritt wird die Lösung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d775-139">In the next step, you will deploy the solution.</span></span>  
  
4.  <span data-ttu-id="4d775-140">Führen Sie das nächste Cmdlet aus, um die Webanwendungslösung in der Zentraladministration zu installieren.</span><span class="sxs-lookup"><span data-stu-id="4d775-140">Run the next cmdlet to install the web application solution to Central Administration.</span></span>  
  
    ```powershell
    Install-SPSolution -Identity PowerPivotWebApp.wsp -GACDeployment -Force -WebApplication $centralAdmin  
    ```  
  
 <span data-ttu-id="4d775-141">Da Sie nun die Webanwendungslösung in der Zentraladministration bereitgestellt haben, können Sie mithilfe der Zentraladministration alle verbleibenden Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d775-141">Now that the web application solution is deployed to Central Administration, you can use Central Administration to complete all remaining configuration steps.</span></span>  
  
##  <a name="step-3-deploy-the-powerpivot-web-application-solution-to-other-web-applications"></a><a name="deployUI"></a><span data-ttu-id="4d775-142">Schritt 3: Bereitstellen der Power Pivot-Webanwendungslösung in anderen Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="4d775-142">Step 3: Deploy the PowerPivot Web Application Solution to Other Web Applications</span></span>  
 <span data-ttu-id="4d775-143">In der vorherigen Aufgabe haben Sie powerpivotwebapp.wsp in der Zentraladministration bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d775-143">In the previous task, you deployed Powerpivotwebapp.wsp to Central Administration.</span></span> <span data-ttu-id="4d775-144">In diesem Abschnitt stellen Sie die Lösung "powerpivotwebapp.wsp" in jeder vorhandenen Webanwendung bereit, die PowerPivot-Datenzugriff unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4d775-144">In this section, you deploy the powerpivotwebapp.wsp on each existing web application that supports PowerPivot data access.</span></span> <span data-ttu-id="4d775-145">Wenn Sie später weitere Webanwendungen hinzufügen, wiederholen Sie unbedingt diesen Schritt für die zusätzlichen Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="4d775-145">If you add more web applications later, be sure to repeat this step for those additional web applications.</span></span>  
  
1.  <span data-ttu-id="4d775-146">Klicken Sie in der Zentraladministration unter Systemeinstellungen auf **Farmlösungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="4d775-146">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="4d775-147">Klicken Sie auf **powerpivotwebapp. wsp**.</span><span class="sxs-lookup"><span data-stu-id="4d775-147">Click **powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="4d775-148">Klicken Sie auf **Lösung bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="4d775-148">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="4d775-149">Wählen Sie unter Bereitstellen **für?** die SharePoint-Webanwendung aus, für die Sie die Power Pivot-Funktions Unterstützung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="4d775-149">In **Deploy To?**, select the SharePoint web application for which you want to add PowerPivot feature support.</span></span>  
  
5.  <span data-ttu-id="4d775-150">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d775-150">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="4d775-151">Wiederholen Sie die Schritte für andere SharePoint-Webanwendungen, die den PowerPivot-Datenzugriff ebenfalls unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4d775-151">Repeat for other SharePoint web applications that will also support PowerPivot data access.</span></span>  
  
##  <a name="redeploy-or-retract-the-solution"></a><a name="retract"></a><span data-ttu-id="4d775-152">Erneutes Bereitstellen oder zurückziehen der Lösung</span><span class="sxs-lookup"><span data-stu-id="4d775-152">Redeploy or retract the Solution</span></span>  
 <span data-ttu-id="4d775-153">Obwohl in der SharePoint-Zentraladministration das Zurückziehen der Lösung möglich ist, müssen Sie die Datei powerpivotwebapp.wsp nur entfernen, wenn Sie systematisch ein Installations- oder ein Patchbereitstellungsproblem behandeln.</span><span class="sxs-lookup"><span data-stu-id="4d775-153">Although SharePoint Central Administration provides solution retraction, you do not need to retract the powerpivotwebapp.wsp file unless you are systematically troubleshooting an installation or patch deployment problem.</span></span>  
  
1.  <span data-ttu-id="4d775-154">Klicken Sie in der SharePoint 2010-Zentraladministration in Systemeinstellungen auf **Farmlösungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="4d775-154">In SharePoint 2010 Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="4d775-155">Klicken Sie auf **Powerpivotwebapp.wsp**.</span><span class="sxs-lookup"><span data-stu-id="4d775-155">Click **Powerpivotwebapp.wsp**.</span></span>  
  
3.  <span data-ttu-id="4d775-156">Klicken Sie auf **Lösung zurückziehen**.</span><span class="sxs-lookup"><span data-stu-id="4d775-156">Click **Retract Solution**.</span></span>  
  
 <span data-ttu-id="4d775-157">Wenn Probleme bei der Server Bereitstellung auftreten, die Sie zur Farm Lösung zurückverfolgen, können Sie diese erneut bereitstellen, indem Sie im Power Pivot-Konfigurations Tool die Option **Reparieren** ausführen.</span><span class="sxs-lookup"><span data-stu-id="4d775-157">If you encounter server deployment issues that you trace back to the farm solution, you can redeploy it by running the **Repair** option in the PowerPivot Configuration Tool.</span></span> <span data-ttu-id="4d775-158">Es empfiehlt sich, Reparaturvorgänge über das Tool auszuführen, da Sie sich dadurch ein paar Schritte ersparen.</span><span class="sxs-lookup"><span data-stu-id="4d775-158">Repair operations via the tool is preferred because it requires fewer steps on your part.</span></span> <span data-ttu-id="4d775-159">Weitere Informationen finden Sie unter [konfigurieren oder reparieren PowerPivot für SharePoint 2010 &#40;Power Pivot-Konfigurationstools&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="4d775-159">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../configure-repair-powerpivot-sharepoint-2010.md).</span></span>  
  
 <span data-ttu-id="4d775-160">Wenn Sie immer noch alle Lösungen erneut bereitstellen möchten, gehen Sie dabei in folgender Reihenfolge vor:</span><span class="sxs-lookup"><span data-stu-id="4d775-160">If you still want to re-deploy all solutions, be sure to do so in this order:</span></span>  
  
1.  <span data-ttu-id="4d775-161">Ziehen Sie die PowerPivot-Webanwendungslösung aus allen SharePoint-Webanwendungen zurück, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d775-161">Retract the PowerPivot Web application solution from all SharePoint web applications that use it.</span></span>  
  
2.  <span data-ttu-id="4d775-162">Ziehen Sie die PowerPivot-Farmlösung zurück.</span><span class="sxs-lookup"><span data-stu-id="4d775-162">Retract the PowerPivot farm solution.</span></span>  
  
3.  <span data-ttu-id="4d775-163">Stellen Sie die PowerPivot-Farmlösung erneut bereit.</span><span class="sxs-lookup"><span data-stu-id="4d775-163">Redeploy the PowerPivot farm solution.</span></span>  
  
4.  <span data-ttu-id="4d775-164">Stellen Sie die PowerPivot-Webanwendungslösung erneut für alle SharePoint-Webanwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="4d775-164">Redeploy the PowerPivot Web application solution to all SharePoint web applications.</span></span>  
  
##  <a name="about-the-powerpivot-solutions"></a><a name="intro"></a><span data-ttu-id="4d775-165">Informationen zu den Power Pivot-Lösungen</span><span class="sxs-lookup"><span data-stu-id="4d775-165">About the PowerPivot Solutions</span></span>  
 <span data-ttu-id="4d775-166">PowerPivot für SharePoint verwendet zwei Lösungspakete, um Anwendungsseiten und Programmdateien für die Farm und einzelne Webanwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d775-166">PowerPivot for SharePoint uses two solution packages to deploy its application pages and program files to the farm and to individual web applications.</span></span>  
  
-   <span data-ttu-id="4d775-167">Die Farmlösung ist global.</span><span class="sxs-lookup"><span data-stu-id="4d775-167">The farm solution is global.</span></span> <span data-ttu-id="4d775-168">Sie wird einmal bereitgestellt und ist dann für jeden neuen Server mit PowerPivot für SharePoint automatisch verfügbar, den Sie der Farm später hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4d775-168">It is deployed once and then becomes automatically available to any new PowerPivot for SharePoint servers that you add to the farm later.</span></span>  
  
-   <span data-ttu-id="4d775-169">Die Webanwendungslösung ist anwendungsspezifisch und muss für jede Webanwendung in der Farm bereitgestellt werden, einschließlich der Zentraladministrationswebanwendung.</span><span class="sxs-lookup"><span data-stu-id="4d775-169">The web application solution is application-specific and must be deployed to each web application in the farm, including the Central Administration web application.</span></span>  
  
 <span data-ttu-id="4d775-170">Jede Lösung wird unterschiedlich bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4d775-170">Each solution is deployed differently.</span></span>  <span data-ttu-id="4d775-171">Die Farmlösung wird bereitgestellt, nachdem das erste PowerPivot für die SharePoint-Instanz installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4d775-171">The farm solution is deployed once, after the first PowerPivot for SharePoint instance is installed.</span></span> <span data-ttu-id="4d775-172">Verwenden Sie das PowerPivot-Konfigurationstool oder PowerShell-Cmdlets, um die Farmlösung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4d775-172">To deploy the farm solution, you use the PowerPivot Configuration Tool or PowerShell cmdlets.</span></span>  
  
 <span data-ttu-id="4d775-173">Die Webanwendungslösung wird anfänglich in der Zentraladministration bereitgestellt. Es folgen weitere Bereitstellungen für alle zusätzlichen Webanwendungen, die Anfragen für PowerPivot-Daten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4d775-173">The web application solution is initially deployed to Central Administration, followed by subsequent solution deployments to any additional web applications that will support requests for PowerPivot data.</span></span> <span data-ttu-id="4d775-174">Um die Webanwendungslösung in der zentral Administration bereitzustellen, müssen Sie das Power Pivot-Konfigurations Tool oder das PowerShell-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="4d775-174">To deploy the web application solution to Central Administration, you must use the PowerPivot Configuration Tool or PowerShell cmdlet.</span></span> <span data-ttu-id="4d775-175">Für alle anderen Webanwendungen können Sie die Webanwendungslösung manuell bereitstellen, und zwar mithilfe der Zentraladministration oder der PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d775-175">For all other web applications, you can deploy the web application solution manually using Central Administration or PowerShell.</span></span>  
  
|<span data-ttu-id="4d775-176">Lösung</span><span class="sxs-lookup"><span data-stu-id="4d775-176">Solution</span></span>|<span data-ttu-id="4d775-177">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d775-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4d775-178">Powerpivotfarm.wsp</span><span class="sxs-lookup"><span data-stu-id="4d775-178">Powerpivotfarm.wsp</span></span>|<span data-ttu-id="4d775-179">Der globalen Assembly wird Microsoft.AnalysisServices.SharePoint.Integration.dll hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d775-179">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="4d775-180">Der globalen Assembly wird Microsoft.AnalysisServices.ChannelTransport.dll hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d775-180">Adds Microsoft.AnalysisServices.ChannelTransport.dll to the global assembly.</span></span><br /><br /> <span data-ttu-id="4d775-181">Installiert Funktionen sowie Ressourcendateien und registriert Inhaltstypen.</span><span class="sxs-lookup"><span data-stu-id="4d775-181">Installs features and resources files, and registers content types.</span></span><br /><br /> <span data-ttu-id="4d775-182">Fügt Bibliotheksvorlagen für den PowerPivot-Katalog und Datenfeedbibliotheken hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d775-182">Adds library templates for PowerPivot Gallery and Data Feed libraries.</span></span><br /><br /> <span data-ttu-id="4d775-183">Anwendungsseiten für die Dienstanwendungskonfiguration, das PowerPivot-Management-Dashboard, die Datenaktualisierung und der PowerPivot-Katalog werden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d775-183">Adds application pages for service application configuration, PowerPivot Management Dashboard, data refresh, and PowerPivot Gallery.</span></span>|  
|<span data-ttu-id="4d775-184">powerpivotwebapp.wsp</span><span class="sxs-lookup"><span data-stu-id="4d775-184">Powerpivotwebapp.wsp</span></span>|<span data-ttu-id="4d775-185">Fügt dem Ordner für Webservererweiterungen auf dem Web-Front-End Microsoft.AnalysisServices.SharePoint.Integration.dll-Ressourcendateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d775-185">Adds Microsoft.AnalysisServices.SharePoint.Integration.dll resources files to the web server extensions folder on the Web front-end.</span></span><br /><br /> <span data-ttu-id="4d775-186">Fügt dem Web-Front-End den PowerPivot-Webdienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d775-186">Adds PowerPivot Web service to the Web-front end.</span></span><br /><br /> <span data-ttu-id="4d775-187">Fügt die Miniaturbildgenerierung für den PowerPivot-Katalog hinzu.</span><span class="sxs-lookup"><span data-stu-id="4d775-187">Adds thumbnail image generation for PowerPivot Gallery.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d775-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d775-188">See Also</span></span>  
 <span data-ttu-id="4d775-189">[UpgradePowerPivot für SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="4d775-189">[Upgrade PowerPivot for SharePoint](../../database-engine/install-windows/upgrade-power-pivot-for-sharepoint.md) </span></span>  
 <span data-ttu-id="4d775-190">[Power Pivot-Server Verwaltung und-Konfiguration in der zentral Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="4d775-190">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 [<span data-ttu-id="4d775-191">PowerPivot-Konfiguration mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d775-191">PowerPivot Configuration using Windows PowerShell</span></span>](power-pivot-configuration-using-windows-powershell.md)  
