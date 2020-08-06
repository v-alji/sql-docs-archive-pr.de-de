---
title: Reporting Services SharePoint-Dienst und-Dienst Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630518"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="6e7c0-102">Reporting Services-SharePoint-Dienst und -Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="6e7c0-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="6e7c0-103">SharePoint-Modus basiert auf der SharePoint-Dienstarchitektur und verwendet einen SharePoint-Dienst sowie mindestens eine Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="6e7c0-104">Beim Erstellen einer Dienstanwendung wird der Dienst verfügbar gemacht und die Datenbank der Dienstanwendung generiert.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="6e7c0-105">Sie können mehrere Reporting Services-Dienstanwendungen erstellen, doch für die meisten Bereitstellungsszenarien ist eine Dienstanwendung ausreichend.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="6e7c0-106">Dieses Thema enthält folgende Informationen:</span><span class="sxs-lookup"><span data-stu-id="6e7c0-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="6e7c0-107">Erstellen einer Reporting Services-Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="6e7c0-108">Ändern der Zuordnungen der Dienst Anwendung mit einer Proxy Gruppe</span><span class="sxs-lookup"><span data-stu-id="6e7c0-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="6e7c0-109">Bearbeiten von Eigenschaften der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="6e7c0-110">So erstellen Sie eine Reporting Services-Dienstanwendung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e7c0-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="6e7c0-111">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6e7c0-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="6e7c0-112">Erstellen einer Reporting Services-Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="6e7c0-113">Sie können die SharePoint-Zentraladministrations- oder PowerShell-Skripts verwenden, um die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="6e7c0-114">Weitere Informationen zum Verwenden der SharePoint-Zentraladministration finden Sie im Abschnitt „Erstellen einer Reporting Services-Dienstanwendung“ in [Installieren des SharePoint-Modus von Reporting Services für SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="6e7c0-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="6e7c0-115">Lesen Sie den PowerShell-Abschnitt weiter unten in diesem Thema, um ein Beispiel zu einem PowerShell-Skript für die Erstellung von Dienstanwendungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a><span data-ttu-id="6e7c0-116">Ändern der Zuordnungen der Dienst Anwendung mit einer Proxy Gruppe</span><span class="sxs-lookup"><span data-stu-id="6e7c0-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="6e7c0-117">Die Seite Neu zum Erstellen einer Dienstanwendung enthält den Abschnitt **Zuordnung der Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="6e7c0-118">Dieser Abschnitt ermöglicht es Ihnen, die Dienstanwendung im Rahmen der Erstellung zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="6e7c0-119">Führen Sie die folgenden Schritte aus, um die Zuordnung zu ändern und der Dienstanwendung eine Kundenkonfiguration zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="6e7c0-120">Sie können dasselbe allgemeine Verfahren auch verwenden, um den Proxy der Standardgruppe hinzuzufügen, anstatt die Zuordnung der Dienstanwendung in eine benutzerdefinierte Gruppe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="6e7c0-121">Klicken Sie in der SharePoint-Zentraladministration in der Anwendungsverwaltung auf **Zuordnungen von Dienstanwendungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="6e7c0-122">Ändern Sie auf der Seite Zuordnungen von Dienstanwendungen die Ansicht in **Dienstanwendungen**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="6e7c0-123">Suchen und klicken Sie auf den Namen der neuen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="6e7c0-124">Sie können auch auf den Namen der Anwendungsproxygruppe **default** klicken, um den Proxy zur Standardgruppe hinzuzufügen, anstatt die folgenden Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="6e7c0-125">Wählen Sie im Auswahlfeld **Folgende Gruppe von Verbindungen bearbeiten** die Option **Benutzerdefiniert**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="6e7c0-126">Aktivieren Sie das Kontrollkästchen für den Proxy, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a><span data-ttu-id="6e7c0-127">Bearbeiten von Eigenschaften der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="6e7c0-128">Sie können die Eigenschaftenseite der Dienstanwendung erneut öffnen, um die Eigenschaften zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="6e7c0-129">Klicken Sie in der SharePoint-zentral Administration in der Gruppe Anwendungs Verwaltung auf **Dienst Anwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="6e7c0-130">Wählen Sie die Dienstanwendung aus, indem Sie zum Auswählen der ganzen Zeile auf die Typspalte klicken.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="6e7c0-131">Wenn Sie auf den Namen der Anwendung klicken, wird die Seite mit Verwaltungsoptionen für den Dienst und nicht die Eigenschaftenseite der Dienstanwendung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="6e7c0-132">Klicken Sie im Menüband Dienstanwendungen auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="6e7c0-133">So erstellen Sie eine Reporting Services-Dienst Anwendung mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e7c0-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="6e7c0-134">Sie können die Dienstanwendung und den Proxy mithilfe von PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="6e7c0-135">Im Beispiel unten wird davon ausgegangen, dass Sie wissen, welchen Anwendungspool Sie für die Dienstanwendung konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="6e7c0-136">Fügen Sie das Anwendungspoolobjekt des Anwendungspoolnamens einer Variablen hinzu, die an die neue Aktion übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="6e7c0-137">Erstellen Sie die Dienstanwendung mit einem von Ihnen angegebenen Namen und Anwendungspool.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="6e7c0-138">Rufen Sie das neue Dienstanwendungsobjekt ab, und übergeben Sie das Objekt in die Pipe des neuen Proxy-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="6e7c0-139">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6e7c0-139">Related Tasks</span></span>  
  
|<span data-ttu-id="6e7c0-140">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="6e7c0-140">Task</span></span>|<span data-ttu-id="6e7c0-141">Link</span><span class="sxs-lookup"><span data-stu-id="6e7c0-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="6e7c0-142">Verwalten der Einstellungen der Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="6e7c0-143">Verwalten einer Reporting Services SharePoint-Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6e7c0-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="6e7c0-144">Führen Sie für die Dienstanwendung (einschließlich zugehöriger Komponenten wie Verschlüsselungsschlüssel und Proxy) eine Sicherung und Wiederherstellung aus.</span><span class="sxs-lookup"><span data-stu-id="6e7c0-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="6e7c0-145">Sichern und Wiederherstellen von Reporting Services-SharePoint-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="6e7c0-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
