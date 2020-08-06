---
title: Installieren von Power Pivot über die Eingabeaufforderung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7f1f2b28-c9f5-49ad-934b-02f2fa6b9328
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 54f30142cdc2e39b3ec565d4f965fdad675405e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621825"
---
# <a name="install-powerpivot-from-the-command-prompt"></a><span data-ttu-id="c564b-102">Installieren von PowerPivot über die Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="c564b-102">Install PowerPivot from the Command Prompt</span></span>
  <span data-ttu-id="c564b-103">Sie können Setup in der Befehlszeile ausführen, um SQL Server PowerPivot für SharePoint zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-103">You can run Setup from the command line to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="c564b-104">Sie müssen den `/ROLE`-Parameter in den Befehl einschließen und den `/FEATURES`-Parameter ausschließen.</span><span class="sxs-lookup"><span data-stu-id="c564b-104">You must include the `/ROLE` parameter in your command and exclude the `/FEATURES` parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c564b-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c564b-105">Prerequisites</span></span>  
 <span data-ttu-id="c564b-106">SharePoint Server 2010 Enterprise Edition mit Service Pack 1 (SP1) muss installiert sein.</span><span class="sxs-lookup"><span data-stu-id="c564b-106">SharePoint Server 2010 enterprise edition with Service Pack 1 (SP1) must be installed.</span></span>  
  
 <span data-ttu-id="c564b-107">Sie müssen über Domänenbenutzerkonten verfügen, um Analysis Services bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c564b-107">You must use domain accounts to provision Analysis Services.</span></span>  
  
 <span data-ttu-id="c564b-108">Der Computer muss der gleichen Domäne wie die SharePoint-Farm hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c564b-108">The computer must be joined to the same domain as the SharePoint farm.</span></span>  
  
##  <a name="role-based-installation-options"></a><a name="Commands"></a><span data-ttu-id="c564b-109">/Role basierte Installationsoptionen</span><span class="sxs-lookup"><span data-stu-id="c564b-109">/ROLE based installation options</span></span>  
 <span data-ttu-id="c564b-110">Für PowerPivot für SharePoint-Bereitstellungen wird der `/ROLE`-Parameter anstelle des `/FEATURES`-Parameters verwendet.</span><span class="sxs-lookup"><span data-stu-id="c564b-110">For PowerPivot for SharePoint deployments, the `/ROLE` parameter is used in place of the `/FEATURES` parameter.</span></span> <span data-ttu-id="c564b-111">Gültige Werte:</span><span class="sxs-lookup"><span data-stu-id="c564b-111">Valid values include:</span></span>  
  
-   `SPI_AS_ExistingFarm`  
  
-   `SPI_AS_NewFarm`  
  
 <span data-ttu-id="c564b-112">Beide Rollen installieren Anwendungs-, Konfigurations- und Bereitstellungsdateien, die die Ausführung von PowerPivot für SharePoint in einer SharePoint-Farm ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c564b-112">Both roles install application, configuration, and deployment files that enable a PowerPivot for SharePoint to run in a SharePoint farm.</span></span> <span data-ttu-id="c564b-113">Die Angabe von beiden Rolle bewirkt, dass Setup Hardware- und Softwareanforderungen für die SharePoint-Integration überprüft.</span><span class="sxs-lookup"><span data-stu-id="c564b-113">Specifying either role will cause Setup to check for hardware and software requirements necessary for SharePoint integration.</span></span>  
  
 <span data-ttu-id="c564b-114">Die vorhandene Farmoption geht davon aus, dass eine SharePoint-Farm bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c564b-114">The existing farm option assumes that a SharePoint farm is already in place.</span></span> <span data-ttu-id="c564b-115">Bei der Option "neue Farm" wird davon ausgegangen, dass Sie eine neue Farm erstellen. Sie unterstützt das Hinzufügen einer Datenbank-Engine Instanz in der Befehlszeilen Syntax, damit Sie die Datenbank-Engine Instanz als Datenbankserver der Farm verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c564b-115">The new farm option assumes that you will create a new farm; it supports the addition of a Database Engine instance in the command line syntax so that you can use the Database Engine instance as the farm's database server.</span></span>  
  
 <span data-ttu-id="c564b-116">Im Gegensatz zu den vorherigen Versionen werden alle Serverkonfigurationstasks nach der Installation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c564b-116">In contrast with the previous releases, all server configuration tasks are performed as post-installation tasks.</span></span> <span data-ttu-id="c564b-117">Wenn Sie Installations- und Konfigurationsschritte automatisieren, können Sie den Server mithilfe von PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-117">If you are automating installation and configuration steps, you can use PowerShell to configure the server.</span></span> <span data-ttu-id="c564b-118">Weitere Informationen finden Sie unter [Power Pivot-Konfiguration mit Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="c564b-118">For more information, see [PowerPivot Configuration using Windows PowerShell](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-configuration-using-windows-powershell).</span></span>  
  
## <a name="example-commands"></a><span data-ttu-id="c564b-119">Beispielbefehle</span><span class="sxs-lookup"><span data-stu-id="c564b-119">Example Commands</span></span>  
 <span data-ttu-id="c564b-120">Die folgenden Beispiele veranschaulichen die Verwendung jeder Option.</span><span class="sxs-lookup"><span data-stu-id="c564b-120">The following examples illustrate the usage of each option.</span></span> <span data-ttu-id="c564b-121">Beispiel 1 zeigt `SPI_AS_ExistingFarm` .</span><span class="sxs-lookup"><span data-stu-id="c564b-121">Example 1 shows `SPI_AS_ExistingFarm`.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
 <span data-ttu-id="c564b-122">Beispiel 2 zeigt `SPI_AS_NewFarm`.</span><span class="sxs-lookup"><span data-stu-id="c564b-122">Example 2 shows `SPI_AS_NewFarm`.</span></span> <span data-ttu-id="c564b-123">Beachten Sie, dass es Parameter zum Bereitstellen der Datenbank-Engine einschließt.</span><span class="sxs-lookup"><span data-stu-id="c564b-123">Notice that it includes parameters for provisioning the Database Engine.</span></span>  
  
```cmd
Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_NewFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/SQLSVCACCOUNT=<DomainName\UserName> /SQLSVCPASSWORD=<StrongPassword> /SQLSYSADMINACCOUNTS=<DomainName\UserName> /AGTSVCACCOUNT=<DomainName\UserName> /AGTSVCPASSWORD=<StrongPassword> /ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
```  
  
##  <a name="modifying-the-command-syntax"></a><a name="Join"></a><span data-ttu-id="c564b-124">Ändern der Befehlssyntax</span><span class="sxs-lookup"><span data-stu-id="c564b-124">Modifying the command syntax</span></span>  
 <span data-ttu-id="c564b-125">Ändern Sie die Beispielbefehlssyntax mithilfe der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="c564b-125">Use the following steps to modify the example command syntax.</span></span>  
  
1.  <span data-ttu-id="c564b-126">Kopieren Sie den folgenden Befehl in Editor:</span><span class="sxs-lookup"><span data-stu-id="c564b-126">Copy the following command into Notepad:</span></span>  
  
    ```cmd
    Setup.exe /q /IAcceptSQLServerLicenseTerms /ACTION=install /ROLE=SPI_AS_ExistingFarm /INSTANCENAME=PowerPivot /INDICATEPROGRESS/ASSVCACCOUNT=<DomainName\UserName> /ASSVCPASSWORD=<StrongPassword> /ASSYSADMINACCOUNTS=<DomainName\UserName>   
    ```  
  
     <span data-ttu-id="c564b-127">Der `/q`-Parameter führt Setup im stillen Modus aus, beim dem die Benutzeroberfläche unterdrückt wird.</span><span class="sxs-lookup"><span data-stu-id="c564b-127">The `/q` parameter runs Setup in quiet mode, which suppresses the user interface.</span></span>  
  
     <span data-ttu-id="c564b-128">`/IAcceptSQLServerLicenseTerms` wird benötigt, wenn der `/q`-Parameter oder der `/qs`-Parameter für nicht beaufsichtigte Installationen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c564b-128">The `/IAcceptSQLServerLicenseTerms` is required when the `/q` or `/qs` parameter is specified for un-attended installations.</span></span>  
  
     <span data-ttu-id="c564b-129">Der `/action`-Parameter weist Setup an, eine Installation auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c564b-129">The `/action` parameter instructs Setup to perform an installation.</span></span>  
  
     <span data-ttu-id="c564b-130">Der `/role`-Parameter weist Setup an, das Analysis Services-Programm und die für PowerPivot für SharePoint erforderlichen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-130">The `/role` parameter instructs Setup to install the Analysis Services program and configuration files required for PowerPivot for SharePoint.</span></span> <span data-ttu-id="c564b-131">Diese Rolle erkennt auch die vorhandenen Farmkonnektivitätsinformationen und verwendet sie, um auf die SharePoint-Konfigurationsdatenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c564b-131">This role also detects and uses the existing farm connectivity information to access the SharePoint configuration database.</span></span> <span data-ttu-id="c564b-132">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c564b-132">This parameter is required.</span></span> <span data-ttu-id="c564b-133">Verwenden Sie ihn statt des `/features`-Parameters, um die zu installierenden Komponenten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c564b-133">Use it instead of the `/features` parameter to specify the components to install.</span></span>  
  
     <span data-ttu-id="c564b-134">Der `/instancename`-Parameter gibt 'PowerPivot' als benannte Instanz an.</span><span class="sxs-lookup"><span data-stu-id="c564b-134">The `/instancename` parameter specifies 'PowerPivot' as a named instance.</span></span> <span data-ttu-id="c564b-135">Dieser Wert ist hartcodiert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c564b-135">This value is hard-coded and cannot be changed.</span></span> <span data-ttu-id="c564b-136">Er wird im Befehl zu pädagogischen Zwecken angegeben, damit Sie wissen, wie der Dienst installiert wird.</span><span class="sxs-lookup"><span data-stu-id="c564b-136">It is specified in the command for educational purposes so that you know how the service is installed.</span></span>  
  
     <span data-ttu-id="c564b-137">Mit dem `/indicateprogress`-Parameter können Sie den Status im Eingabeaufforderungsfenster überwachen.</span><span class="sxs-lookup"><span data-stu-id="c564b-137">The `/indicateprogress` parameter allows you to monitor progress in the command prompt window.</span></span>  
  
2.  <span data-ttu-id="c564b-138">Der `PID`-Parameter wird im Befehl weggelassen, was bewirkt, dass die Evaluation Edition installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c564b-138">The `PID` parameter is omitted from the command, which causes the Evaluation edition to be installed.</span></span> <span data-ttu-id="c564b-139">Wenn Sie die Enterprise Edition installieren möchten, fügen Sie dem Setup-Befehl die PID hinzu und geben Sie einen gültigen Product Key ein.</span><span class="sxs-lookup"><span data-stu-id="c564b-139">If you want to install the Enterprise edition, add the PID to your Setup command and provide a valid product key.</span></span>  
  
    ```  
    /PID=<product key for an Enterprise installation>  
    ```  
  
3.  <span data-ttu-id="c564b-140">Ersetzen Sie die Platzhalter für \<domain\username> und \<StrongPassword> durch gültige Benutzerkonten und Kenn Wörter.</span><span class="sxs-lookup"><span data-stu-id="c564b-140">Replace the placeholders for \<domain\username> and \<StrongPassword>with valid user accounts and passwords.</span></span>  
  
     <span data-ttu-id="c564b-141">Der `/assvaccount` -Parameter und der **/assvcpassword** -Parameter werden verwendet, um die- [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] Instanz auf dem Anwendungsserver zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-141">The `/assvaccount` and **/assvcpassword** parameters are used to configure the [!INCLUDE[ssGeminiSrv](../../includes/ssgeminisrv-md.md)] instance on the application server.</span></span> <span data-ttu-id="c564b-142">Ersetzen Sie diese Platzhalter durch gültige Kontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="c564b-142">Replace these placeholders with valid account information.</span></span>  
  
     <span data-ttu-id="c564b-143">Der **/assysadminaccounts** -Parameter muss auf die Identität des Benutzers festgelegt werden, der SQL Server-Setup ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c564b-143">The **/assysadminaccounts** parameter must be set to the identity of the user who is running SQL Server Setup.</span></span> <span data-ttu-id="c564b-144">Sie müssen wenigstens einen Systemadministrator angeben.</span><span class="sxs-lookup"><span data-stu-id="c564b-144">You must specify at least one system administrator.</span></span> <span data-ttu-id="c564b-145">Beachten Sie, dass SQL Server-Setup keine automatischen sysadmin-Berechtigungen für Mitglieder der integrierten Gruppe "Administratoren" gewährt.</span><span class="sxs-lookup"><span data-stu-id="c564b-145">Note that SQL Server Setup no long grants automatic sysadmin permissions to members of the built-in Administrators group.</span></span>  
  
4.  <span data-ttu-id="c564b-146">Entfernen Sie Zeilenumbrüche.</span><span class="sxs-lookup"><span data-stu-id="c564b-146">Remove line breaks.</span></span>  
  
5.  <span data-ttu-id="c564b-147">Wählen Sie den gesamten Befehl aus, und klicken Sie dann im Menü Bearbeiten auf **Kopieren** .</span><span class="sxs-lookup"><span data-stu-id="c564b-147">Select the entire command and then click **Copy** on the Edit menu.</span></span>  
  
6.  <span data-ttu-id="c564b-148">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="c564b-148">Open an administrator command prompt.</span></span> <span data-ttu-id="c564b-149">Klicken Sie hierzu auf **Start**, klicken Sie mit der rechten Maustaste auf die Eingabeaufforderung, und wählen Sie **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="c564b-149">To do this, click **Start**, right-click the command prompt, and select **Run as administrator**.</span></span>  
  
7.  <span data-ttu-id="c564b-150">Navigieren Sie zum Laufwerk oder dem freigegebenem Ordner, der die SQL Server-Installationsmedien enthält.</span><span class="sxs-lookup"><span data-stu-id="c564b-150">Navigate to the drive or shared folder that contains the SQL Server installation media.</span></span>  
  
8.  <span data-ttu-id="c564b-151">Fügen Sie den überarbeiteten Befehl in die Befehlszeile ein.</span><span class="sxs-lookup"><span data-stu-id="c564b-151">Paste the revised command into the command line.</span></span> <span data-ttu-id="c564b-152">Klicken Sie hierzu auf das Symbol in der oberen linken Ecke des Eingabe Aufforderungs Fensters, zeigen Sie auf **Bearbeiten**, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="c564b-152">To do this, click the icon in the top left corner of the command prompt window, point to **Edit**, and then click **Paste**.</span></span>  
  
9. <span data-ttu-id="c564b-153">Drücken **Sie die Eingabe** Taste, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c564b-153">Press **Enter** to run the command.</span></span> <span data-ttu-id="c564b-154">Warten Sie, bis Setup abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c564b-154">Wait for setup to complete.</span></span> <span data-ttu-id="c564b-155">Sie können den Status von Setup im Eingabeaufforderungsfenster überwachen.</span><span class="sxs-lookup"><span data-stu-id="c564b-155">You can monitor Setup's progress in the command prompt window.</span></span>  
  
10. <span data-ttu-id="c564b-156">Um die Installation zu überprüfen, öffnen Sie die Datei summary.txt unter \Programme\SQL Server\120\Setup Bootstrap\Log.</span><span class="sxs-lookup"><span data-stu-id="c564b-156">To verify installation, check the summary.txt file at \Program Files\SQL Server\120\Setup Bootstrap\Log.</span></span> <span data-ttu-id="c564b-157">Das Endergebnis sollte "Erfolgreich" lauten, wenn der Server ohne Fehler installiert hat.</span><span class="sxs-lookup"><span data-stu-id="c564b-157">Final result should say "Passed" if the server installed without errors.</span></span>  
  
11. <span data-ttu-id="c564b-158">Konfigurieren Sie den Server.</span><span class="sxs-lookup"><span data-stu-id="c564b-158">Configure the server.</span></span> <span data-ttu-id="c564b-159">Sie müssen Lösungen bereitstellen, eine Dienstanwendung erstellen und die Funktion für jede Websitesammlung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c564b-159">At a minimum, you must deploy solutions, create a service application, and enable the feature for each site collection.</span></span> <span data-ttu-id="c564b-160">Weitere Informationen finden Sie unter [konfigurieren oder reparieren PowerPivot für SharePoint 2010 &#40;Power Pivot-Konfigurationstools&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) oder [Power Pivot-Server Verwaltung und-Konfiguration in der zentral Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span><span class="sxs-lookup"><span data-stu-id="c564b-160">For more information, see [Configure or Repair PowerPivot for SharePoint 2010 &#40;PowerPivot Configuration Tool&#41;](../../../2014/analysis-services/configure-repair-powerpivot-sharepoint-2010.md) or [PowerPivot Server Administration and Configuration in Central Administration](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c564b-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c564b-161">See Also</span></span>  
 <span data-ttu-id="c564b-162">[Konfigurieren von Power Pivot-Dienst Konten](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span><span class="sxs-lookup"><span data-stu-id="c564b-162">[Configure PowerPivot Service Accounts](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/configure-power-pivot-service-accounts) </span></span>  
 [<span data-ttu-id="c564b-163">PowerPivot für SharePoint 2010-Installation</span><span class="sxs-lookup"><span data-stu-id="c564b-163">PowerPivot for SharePoint 2010 Installation</span></span>](../../../2014/sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
