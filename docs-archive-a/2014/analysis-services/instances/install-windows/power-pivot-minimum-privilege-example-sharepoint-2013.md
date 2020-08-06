---
title: Beispiel für eine Konfiguration mit minimalen Berechtigungen für PowerPivot für SharePoint 2013 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c1e09e6c-52d3-48ab-8c70-818d5d775087
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0188f314e4c354b33d03e6e7948aed1ba4cf8be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697277"
---
# <a name="example-of-a-minimum-privilege-configuration-for-powerpivot-for-sharepoint-2013"></a><span data-ttu-id="053dc-102">Beispiel für eine PowerPivot für SharePoint 2013-Konfiguration mit Mindestberechtigungen</span><span class="sxs-lookup"><span data-stu-id="053dc-102">Example of a Minimum-Privilege Configuration for PowerPivot for SharePoint 2013</span></span>
  <span data-ttu-id="053dc-103">In diesem Thema wird eine PowerPivot für SharePoint 2013-Konfiguration mit Mindestberechtigungen anhand eines Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="053dc-103">This topic describes an example PowerPivot for SharePoint 2013 configuration with minimum privileges.</span></span> <span data-ttu-id="053dc-104">Bei der Konfiguration wird für jede der drei Komponenten ein anderes Konto verwendet, von denen jedes über Mindestberechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="053dc-104">The configuration utilizes a different account for each of the three components and each account has the minimum level of privileges.</span></span>  
  
## <a name="summary-of-accounts"></a><span data-ttu-id="053dc-105">Übersicht der Konten</span><span class="sxs-lookup"><span data-stu-id="053dc-105">Summary of Accounts</span></span>  
 <span data-ttu-id="053dc-106">PowerPivot für SharePoint 2013 unterstützt die Verwendung des Netzwerkdienstkontos für das Analysis Services-Dienstkonto.</span><span class="sxs-lookup"><span data-stu-id="053dc-106">PowerPivot for SharePoint 2013 supports the use of the Network Service account for the Analysis Services service account.</span></span> <span data-ttu-id="053dc-107">Das Netzwerkdienstkonto ist kein unterstütztes Szenario unter SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="053dc-107">The Network Service account is not a supported scenario with SharePoint 2010.</span></span> <span data-ttu-id="053dc-108">Weitere Informationen zu Dienst Konten finden Sie unter [Konfigurieren von Windows-Dienst Konten und-Berechtigungen](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) ( https://msdn.microsoft.com/library/ms143504.aspx) .</span><span class="sxs-lookup"><span data-stu-id="053dc-108">For more information on Service accounts, see [Configure Windows Service Accounts and Permissions](../../../database-engine/configure-windows/configure-windows-service-accounts-and-permissions.md) (https://msdn.microsoft.com/library/ms143504.aspx).</span></span>  
  
 <span data-ttu-id="053dc-109">In der folgenden Tabelle werden die Eigenschaften der drei Konten zusammengefasst, die in diesem Beispiel für eine Konfiguration mit Mindestberechtigungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="053dc-109">The following table summarizes the three accounts used in this example of a minimum privileged configuration.</span></span>  
  
|<span data-ttu-id="053dc-110">`Scope`</span><span class="sxs-lookup"><span data-stu-id="053dc-110">Scope</span></span>|<span data-ttu-id="053dc-111">Name</span><span class="sxs-lookup"><span data-stu-id="053dc-111">Name</span></span>|  
|-----------|----------|  
|<span data-ttu-id="053dc-112">SharePoint-Administratorkonto</span><span class="sxs-lookup"><span data-stu-id="053dc-112">SharePoint Administrator account</span></span>|<span data-ttu-id="053dc-113">**SPAdmin**</span><span class="sxs-lookup"><span data-stu-id="053dc-113">**SPAdmin**</span></span>|  
|<span data-ttu-id="053dc-114">SharePoint-Farmkonto</span><span class="sxs-lookup"><span data-stu-id="053dc-114">SharePoint Farm account</span></span>|<span data-ttu-id="053dc-115">**SPFarm**</span><span class="sxs-lookup"><span data-stu-id="053dc-115">**SPFarm**</span></span>|  
|<span data-ttu-id="053dc-116">Analysis Services-Dienstkonto</span><span class="sxs-lookup"><span data-stu-id="053dc-116">Analysis Services service account</span></span>|<span data-ttu-id="053dc-117">**SPsvc**</span><span class="sxs-lookup"><span data-stu-id="053dc-117">**SPsvc**</span></span>|  
  
### <a name="the-sharepoint-administrator-account-spadmin"></a><span data-ttu-id="053dc-118">Das SharePoint-Administratorkonto (SpAdmin)</span><span class="sxs-lookup"><span data-stu-id="053dc-118">The SharePoint Administrator account (SpAdmin)</span></span>  
 <span data-ttu-id="053dc-119">**SPAdmin** ist ein Domänenkonto, das Sie zum Installieren und Konfigurieren der Farm verwenden.</span><span class="sxs-lookup"><span data-stu-id="053dc-119">**SPAdmin** is a domain account you use to install and configure the farm.</span></span> <span data-ttu-id="053dc-120">Dabei handelt es sich um das Konto, mit dem der SharePoint-Konfigurations-Assistent und das Power Pivot-Konfigurations Tool für SharePoint 2013 ausgeführt werden. das **SPAdmin** -Konto ist das einzige Konto, für das lokale Administrator Rechte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="053dc-120">It is the account used to run the SharePoint Configuration Wizard and the PowerPivot Configuration Tool for SharePoint 2013.The **SPAdmin** account is the only account that requires local Administrator rights.</span></span> <span data-ttu-id="053dc-121">Vor dem Ausführen des Power Pivot-Konfigurationstools gewähren Sie dem **SPAdmin** -Konto Berechtigungen für die SQL Server-Daten Bank Instanz, auf der SharePoint Inhalts-und Konfigurations Datenbanken erstellt.</span><span class="sxs-lookup"><span data-stu-id="053dc-121">Before running the PowerPivot Configuration tool, grant the **SPAdmin** account privileges to the SQL Server database instance where SharePoint creates content and configuration databases.</span></span> <span data-ttu-id="053dc-122">Damit Sie das SPAdmin-Konto in einem Szenario mit Mindestberechtigungen konfigurieren können, muss es Mitglied in den Rollen **securityadmin** und **dbcreator**sein.</span><span class="sxs-lookup"><span data-stu-id="053dc-122">To configure the SPAdmin account in a minimum privilege scenario, it should be a member of the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-farm-account-spfarm"></a><span data-ttu-id="053dc-123">Das Farmkonto (SPFarm)</span><span class="sxs-lookup"><span data-stu-id="053dc-123">The Farm account (SPFarm)</span></span>  
 <span data-ttu-id="053dc-124">**SPFarm** ist ein Domänenkonto, das der SharePoint-Timerdienst und die Webanwendung der Zentraladministration für den Zugriff auf die SharePoint-Inhaltsdatenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="053dc-124">**SPFarm** is a domain account that the SharePoint Timer service and the web application for Central Administration use to access the SharePoint content database.</span></span> <span data-ttu-id="053dc-125">Dieses Konto muss nicht als lokaler Administrator eingerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="053dc-125">This account does not need to be a local administrator.</span></span> <span data-ttu-id="053dc-126">Der SharePoint-Konfigurations-Assistent gewährt die entsprechenden Mindestberechtigungen in der SQL Server-Back-End-Datenbank. Die Mindestberechtigung für die SQL Server-Konfiguration ist die Mitgliedschaft in den Rollen **securityadmin** und **dbcreator**.</span><span class="sxs-lookup"><span data-stu-id="053dc-126">The SharePoint configuration wizard grants the proper minimal privilege in the back-end SQL Server database.The minimum SQL Server privilege configuration is membership in the roles **securityadmin** and **dbcreator**.</span></span>  
  
### <a name="the-service-account-for-powerpivot-service-spsvc"></a><span data-ttu-id="053dc-127">Das Dienstkonto für den PowerPivot-Dienst (SPsvc)</span><span class="sxs-lookup"><span data-stu-id="053dc-127">The Service Account for PowerPivot Service (SPsvc)</span></span>  
 <span data-ttu-id="053dc-128">Wenn eine neue SharePoint-Farm vor dem Ausführen des PowerPivot-Konfigurationstools noch nicht konfiguriert wurde, werden standardmäßig folgende Anwendungen vom PowerPivot-Konfigurationstool erstellt:</span><span class="sxs-lookup"><span data-stu-id="053dc-128">If a new SharePoint farm is not configured before you run the PowerPivot Configuration tool, then by default the PowerPivot Configuration tool will create the following:</span></span>  
  
-   <span data-ttu-id="053dc-129">Power Pivot-Dienst Anwendung.</span><span class="sxs-lookup"><span data-stu-id="053dc-129">PowerPivot Service application.</span></span>  
  
-   <span data-ttu-id="053dc-130">Excel Services-Anwendung</span><span class="sxs-lookup"><span data-stu-id="053dc-130">Excel Services application.</span></span>  
  
-   <span data-ttu-id="053dc-131">Secure Storage-Anwendung</span><span class="sxs-lookup"><span data-stu-id="053dc-131">Secure Store application.</span></span>  
  
 <span data-ttu-id="053dc-132">Das PowerPivot-Konfigurationstool konfiguriert alle drei Dienstanwendungen im Standardanwendungspool.</span><span class="sxs-lookup"><span data-stu-id="053dc-132">The PowerPivot configuration tool configures all three of the service applications in the default application pool.</span></span> <span data-ttu-id="053dc-133">Dieser Anwendungspool ist normalerweise für die Ausführung als SPFarm-Konto konfiguriert, das Zugriff auf viele Ressourcen hat, die von einem Dienstkonto jedoch nicht benötigt werden. Um eine Umgebung mit Mindestberechtigungen zu erhalten, konfigurieren Sie ein neues Domänenkonto, das vom betreffenden Anwendungspool und der betreffenden Webanwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="053dc-133">That application pool is typically configured to run as the SPFarm account, which has access to many resources that a service account does not require.To make the environment a minimum-privileged environment, configure a new domain account to be use by the appropriate application pool and web application.</span></span>  
  
 <span data-ttu-id="053dc-134">**So erstellen Sie ein neues SPsvc-Domänenkonto, das als SharePoint-Dienstkonto verwendet werden soll**</span><span class="sxs-lookup"><span data-stu-id="053dc-134">**To create a new domain account SPsvc to be used as a SharePoint Service account:**</span></span>  
  
1.  <span data-ttu-id="053dc-135">Klicken Sie in der SharePoint-zentral Administration auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="053dc-135">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="053dc-136">Klicken Sie auf **Dienst Konten konfigurieren** .</span><span class="sxs-lookup"><span data-stu-id="053dc-136">Click **Configure Service Accounts**</span></span>  
  
3.  <span data-ttu-id="053dc-137">Klicken Sie auf **Neues verwaltetes Konto registrieren**.</span><span class="sxs-lookup"><span data-stu-id="053dc-137">Click **Register new managed account**.</span></span>  
  
 <span data-ttu-id="053dc-138">Das **SPSvc** -Konto verfügt über keine lokalen Administratorberechtigungen, und SPsvc verfügt über keine Berechtigungen in der SharePoint-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="053dc-138">The **SPSvc** account has no local administrator privileges and SPsvc will not have any privileges in the SharePoint database.</span></span> <span data-ttu-id="053dc-139">Die einzigen Berechtigungen, die SPsvc erfordert, sind Administratorrechte für die PowerPivot-Instanz von Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="053dc-139">The only privileges SPsvc requires is administrative rights to the PowerPivot Instance of the Analysis Services.</span></span>  
  
 <span data-ttu-id="053dc-140">**So konfigurieren Sie den entsprechenden Anwendungspool für die Verwendung des SPsvc-Kontos**</span><span class="sxs-lookup"><span data-stu-id="053dc-140">**To configure the appropriate application pool to use the SPsvc account :**</span></span>  
  
1.  <span data-ttu-id="053dc-141">Klicken Sie in der SharePoint-zentral Administration auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="053dc-141">In SharePoint Central Administration, click **Security**.</span></span>  
  
2.  <span data-ttu-id="053dc-142">Klicken Sie auf **Dienst Konten konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="053dc-142">Click **Configure Service Accounts**.</span></span>  
  
3.  <span data-ttu-id="053dc-143">Wählen Sie den von der PowerPivot-Dienstanwendung verwendeten Dienstanwendungspool aus.</span><span class="sxs-lookup"><span data-stu-id="053dc-143">Select the service application pool used by the PowerPivot Service application.</span></span> <span data-ttu-id="053dc-144">Wählen Sie dann das SPSvc-Konto aus.</span><span class="sxs-lookup"><span data-stu-id="053dc-144">Then select the SPSvc account.</span></span>  
  
 <span data-ttu-id="053dc-145">**So gewähren Sie Zugriff auf die Webanwendung mit PowerShell**</span><span class="sxs-lookup"><span data-stu-id="053dc-145">**To Grant access to the web application with PowerShell:**</span></span>  
  
1.  <span data-ttu-id="053dc-146">Führen Sie die SharePoint 2013-Verwaltungsshell mit Administratorberechtigungen aus.</span><span class="sxs-lookup"><span data-stu-id="053dc-146">Run the SharePoint 2013 Management Shell with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="053dc-147">Führen Sie den folgenden PowerShell-Code aus:</span><span class="sxs-lookup"><span data-stu-id="053dc-147">Run the following PowerShell code:</span></span>  
  
    ```powershell
    $webApp = Get-SPWebApplication "http://<servername>"  
    $webApp.GrantAccessToProcessIdentity("DOMAIN\<ServiceAccountName>")
    ```  
